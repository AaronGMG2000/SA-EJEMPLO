# Pipelines

## Stages

Los stage a utilizar son:
  - build
  - testing
  - publish
  - deploy

### build
Stage donde se construirán las imagenes de los contenedores con sus respectivas variables de entorno

Ejemplo:

```yml
build-development:
  stage: build
  only:
    - "develop" #indica en que rama se va a ejecutar al momento de un commit o merge
  tags: #son los tags que ingresamos al momento del registro del runner
    - sa
  before_script:
    - cd app
    - echo "REACT_APP_BACKEND_URI=$DEV_IP_BACKEND" >> .env
    - cd ..
    - docker-compose down --rmi all
  script:
    - docker-compose up --build -d
  after_script:
    - echo "Construcción y despliegue de contenedores de desarrollo terminada"
```

### testing
Stage donde se corren las pruebas unitarias, de integración y e2e

Ejemplo:

```yml
unit-testing:
  stage: testing
  only:
    - "develop"
  tags:
    - sa
  variables:
    TEST_URL: "$DEV_IP_BACKEND"
  before_script:
    - sleep 120 && echo "Iniciando test unitarios"
    - cd server/test
    - npm install
  script:
    - npm run test
  after_script:
    - echo "Tests unitarios realizados"
```

### publish
Stage donde pasadas las pruebas se construyen las imagenes con las variables de entorno de producción, 
para su próximo despliegue.

Ejemplo:

```yml
publish: #  Publicando las imagenes a un repositorio
  stage: publish
  only:
    - "main" #indica en que rama se va a ejecutar al momento de un commit o merge
  tags: #son los tags que ingresamos al momento del registro del runner
    - sa
  before_script:
    - docker login -u $DOCKERHUB_USER -p $DOCKERHUB_ACCESS_TOKEN
    - echo "$CI_COMMIT_SHORT_SHA"
  script:
    - cd app
    - echo "REACT_APP_BACKEND_URI=$LB_IP_BACKEND" >> .env
    - docker build -t sa-frontend-f3:$CI_COMMIT_SHORT_SHA .
    - docker push sa-frontend-f3:$CI_COMMIT_SHORT_SHA
    - cd ..
    - cd server
    - docker build -t sa-backend-f3:$CI_COMMIT_SHORT_SHA .
    - docker push sa-backend-f3:$CI_COMMIT_SHORT_SHA
    - cd ..
  after_script:
    - echo "Publicacion de imagenes realizada"
```


### deploy
Stage donde se descargan las imagenes y se despliega la aplicación en producción

Ejemplo:

```yml
deploy: # Utilizando kubernetes
  stage: deploy
  only:
    - "main" #indica en que rama se va a ejecutar al momento de un commit o merge
  tags: #son los tags que ingresamos al momento del registro del runner
    - sas
  before_script:
    - docker login -u $DOCKERHUB_USER -p $DOCKERHUB_ACCESS_TOKEN
    - gcloud container clusters get-credentials cluster-aydrive --zone us-central1-c --project third-anvil-324122
  script:
    - cd kubernetes
    - sed -e 's|CI_COMMIT_SHORT_SHA|'"$CI_COMMIT_SHORT_SHA"'|g' deployment.yaml | kubectl apply -f -
    - sleep 120 && echo "Desplegando el cluster"
  after_script:
    - echo "Deploy realizado"
```



