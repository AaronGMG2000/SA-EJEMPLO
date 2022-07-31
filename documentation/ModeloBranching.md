# Modelo de Branching

Se utilizará el modelo de Branching de Git Flow esta posee distintos tipos de ramas las cuales son: 

1. Main 
1. Develop 
1. Feature 
4. Release 
4. Hotfix 

## **Ramas principales** 

**Main**: Esta rama se crea desde el inicio, esta rama es la de producción que posee todo el código que se encuentra listo para ser implementando, esta rama posee varios tags que son las diferentes versiones que se van realizando cuando más ramas son combinadas con esta. 

**Develop**: Esta rama se crea igualmente desde un inicio esta posee código que se encuentra en desarrollo, características que serán implementadas y en proceso de ser testeadas, toda nueva característica debe estar basada en esta rama y tiene que volver a combinarse con esta igualmente una vez finalizada. 

## **Ramas de Soporte** 

**Feature:** Estas ramas son las más comunes en Git Flow, tiene una corta duración de vida y es creada cuando se necesita realizar una nueva característica, estás inician en el punto actual en el que se encuentre la rama develop, y una vez completadas comúnmente son eliminadas y combinadas nuevamente con la rama develop 

**Release:** Estos tipos de ramas son creadas cuando se esta a punto de crear una nueva versión para producción del software, en estas normalmente se tocan pequeños bugs, y cambios menores que se necesitan para poder poner en producción el software. 

**Hotfix:** Estos tipos de rama se crean a partir de la rama main, estas normalmente se crean cuando se desean realizar algún tipo de arreglo de bugs críticos del software que no pueden esperar a la siguiente versión del software. 