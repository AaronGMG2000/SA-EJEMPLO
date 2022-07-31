# Seguridad

## JWT
Este es un token que permite propagar de manera segura la identidad de un usuario de un lado a otro, garantizando que únicamente el usuario es quien tenga acceso a los datos que desee, siempre y cuando este tenga los permisos necesarios para accederlos.

Este utiliza un formato JSON y garantizara que nuestra aplicación siempre sepa la identidad de la persona que desea obtener los servicios.

## ¿Qué es un JWT (JSON WEB TOKEN)?
JWT (JSON Web Token) es un estándar abierto (publicado en el RFC 7519) que define un método compacto y autocontenido para encapsular y compartir aserciones (claims) sobre una entidad (subject) de manera segura entre distintas partes mediante el uso de objetos JSON. Se puede confiar y verificar el contenido del token cuando este está firmado digitalmente (JWS, RFC 7515). 

La firma se puede generar usando claves simétricas (HMAC) o claves asimétricas (RSA o ECDSA). Adicionalmente los JWT pueden contener también datos cifrados (JWE, RFC 7516) para proteger datos sensibles, aunque este tipo de tokens no son objeto de este estudio.

## Red Interna
Docker Compose nos provee varios servicios y mediante la configuración de estos se pueden generar ips internas que no son accesibles al público, haciendo que la comunicación entre servicos sea la mas rapida y segura posible.

