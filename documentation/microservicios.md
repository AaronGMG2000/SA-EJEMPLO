# MICROSERVICIOS

## 1. USUARIOS
Este cuenta con toda la gestión de usuarios dividos por un crud con los siguientes lineamientos
- Creación de usuarios
    - Administrador
    - Turista
    - Renta de autos
    - Hotel
- Obtención de cada usuario por un identificador

## 2. Pasaporte Covid
Contara con acciones para la gestión de pasaporte COVID para lo que es necesario las siguientes acciones
- Creación de pasaporte COVID por turista
- Creación de esquemas de vacunación
- Descarga pdf de pasaporte COVID

## 3. HOTELES
Este microservicio será el encargado de gestionar todos los servicios que puede ofrecer un hotel para los cuales se tendrán las siguientes acciones:
- Reservación de habitación
- Creación de calendarización
- Reseña de servicio de hotel
- Carga Masiva de habitaciones

## 3. RENTA DE AUTOS
Este microservicio será el encargado de gestionar todos los servicios que puede ofrecer un usuario tipo renta de autos para los cuales se tendrán las siguientes acciones:
- Reservación de autos
- Reseña de servicio por la renta de un auto
- Carga Masiva de autos
- Creación de auto

## 4. VUELOS
Este microservicio será el encargado de gestionar todos los servicios que puede ofrecer el sistema para vuelos con las siguientes acciones:
- Creación de vuelo 
    - Solo ida
    - Ida y vuelta
- Compra de vuelo

## 5. PAGOS
Debido a que todo el sistema estará integrado con pagos de banco mediante una tarjeta de crédito y se reutilizara muchas veces, se ha tomado la decisión de aislarlo y este microservicio tendrá las siguientes acciones:
- Verificación de existencia de tarjeta de crédito
- Pago con tarjeta de crédito

## 6. Multi Factor Authentication
Este microservicio será el encargado de gestionar todos los servicios que puede ofrecer el sistema para la autenticación de usuarios con los siguientes lineamientos:
- Identificación de usuario por medio de foto

## 7. Esquemas de vacunación
Este microservicio será el encargado de gestionar todos los servicios que puede ofrecer el sistema para la gestión de esquemas de vacunación con las siguientes acciones:
- Creación de esquema de vacunación
- Creación de vacunas
- Creación de dosis
- Creación de esquema de vacunación por dosis
- Anexar esquema de vacunación a una país
