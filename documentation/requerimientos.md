# REQUERIMIENTOS FUNCIONALES
## Usuarios
1. El sistema permitirá generar nuevos registros de usuarios de tipo turista, hotel y renta de autos desde la página web. Usuarios de tipo administrador solo se podrán generar a partir de otra cuenta con rol de administrador.

    <table>
    <tr>
        <th colspan="2">CU001</th>
    </tr>
    <tr>
        <td>Nombre</td>
        <td>Registro de usuario</td>
    </tr>
    <tr>
        <td>Autor</td>
        <td>Jose Moran </td>
    </tr>

    <tr>
        <td>Actores</td>
        <td>Usuario</td>
    </tr>
    <tr>
        <td colspan="2">Precondiciones: <br>
        El usuario no debe estar registrado en el sistema
        </td>
    </tr>

    <tr>
        <td colspan="2">Flujo normal: <br>
        1. Ingresa nombre completo<br>
        2. Ingresa correo electrónico<br>
        3. Ingresa contraseña<br>
        4. Confirma contraseña<br>
        5. Selecciona tipo de usuario<br>
        6. Presiona el botón de registrar<br>
        7. Se valida que el correo no haya sido utilizado previamente<br>
        8. Se retorna una respuesta de registro correcto<br>
        9. Se redirige al usuario a la página correspondiente según el tipo seleccionado
        </td>
    </tr>

    <tr>
        <td colspan="2">Flujo Alternativo: <br>
        8. Se retorna una respuesta de que ya existe una cuenta para dicho correo<br>
    </tr>

    <tr>
        <td colspan="2">Postcondiciones: <br>
        Se envian los datos del usuario registrado<br>
    </tr>
    </table>

2. El sistema enviara un correo con un código de autorización a la persona que intento realizar el inicio de sesión, el usuario deberá ingresar el código y posteriormente el sistema aprobara o denegara el acceso.

    <table>
    <tr>
        <th colspan="2">CU002</th>
    </tr>
    <tr>
        <td>Nombre</td>
        <td>Inicio de sesión</td>
    </tr>
    <tr>
        <td>Autor</td>
        <td>Jose Moran </td>
    </tr>

    <tr>
        <td>Actores</td>
        <td>Usuario</td>
    </tr>
    <tr>
        <td colspan="2">Precondiciones: <br>
        El usuario no debe tener sesión iniciada en el sistema
        </td>
    </tr>

    <tr>
        <td colspan="2">Flujo normal: <br>
        1. Ingresa correo electrónico<br>
        2. Ingresa contraseña<br>
        3. Presiona el botón de iniciar sesión<br>
        4. Tomar foto y enviar.<br>
        6. Se retorna una respuesta de inicio de sesión correcto<br>
        7. Se redirige al usuario a la página correspondiente según el tipo seleccionado
        </td>
    </tr>

    <tr>
        <td colspan="2">Flujo Alternativo: <br>
        6. Se retorna una respuesta de que el usuario no ha sido encontrado<br>
    </tr>

    <tr>
        <td colspan="2">Postcondiciones: <br>
        Se envian los datos del usuario registrado<br>
    </tr>
    </table>

## Hoteles
1. El sistema permitirá al usuario tipo hotel crear un calendario con las fechas que tiene a disposición para realizar reservaciones.

    <table>
    <tr>
        <th colspan="2">CU003</th>
    </tr>
    <tr>
        <td>Nombre</td>
        <td>Crear calendarizacion de reservaciones</td>
    </tr>
    <tr>
        <td>Autor</td>
        <td>Jose Moran </td>
    </tr>

    <tr>
        <td>Actores</td>
        <td>Usuario de tipo hotel</td>
    </tr>
    <tr>
        <td colspan="2">Precondiciones: <br>
        El usuario debe tener sesión iniciada en el sistema
        </td>
    </tr>

    <tr>
        <td colspan="2">Flujo normal: <br>
        1. Seleccionar fecha<br>
        2. Si el usuario desea ingresar otra fecha regresa al paso 1<br>
        3. Presiona el botón de crear<br>
        4. Se retorna una respuesta de calendario creado correctamente<br>
        </td>
    </tr>

    <tr>
        <td colspan="2">Postcondiciones: <br>
        El usuario tipo turista puede realizar reservaciones en las fechas ingresadads <br>
    </tr>
    </table>


2. El usuario tipo turista podrá realizar búsquedas en cascada de hoteles, la cual debe tener los siguientes filtros opcionales:
    - País
    - Ciudad
    - Cantidad de personas
    - Rango de fechas
    - Rango de precios

    <table>
        <tr>
            <th colspan="2">CU004</th>
        </tr>
    <tr>
        <td>Nombre</td>
        <td>Búsqueda de hotel</td>
    </tr>
    <tr>
        <td>Autor</td>
        <td>Jose Moran </td>
    </tr>

    <tr>
        <td>Actores</td>
        <td>Usuario de tipo turista</td>
    </tr>
    <tr>
        <td colspan="2">Precondiciones: <br>
        El usuario debe tener sesión iniciada en el sistema
        </td>
    </tr>

    <tr>
        <td colspan="2">Flujo normal: <br>
        1. El usuario elige el filtro<br>
        2. Ingresa el valor del filtro seleccionado<br>
        3. El sistema retorna los hoteles filtrados<br>
        4. Si el usuario desea agregar otro filtro regresa al paso 1
        </td>
    </tr>

    <tr>
        <td colspan="2">Postcondiciones: <br>
        El usuario podrá realizar reservaciones de una manera sencilla<br>
    </tr>
    </table>


3. El sistema permitirá al usuario tipo turista realizar reservaciones en hoteles, para que la reservación sea válida el usuario tipo turista debe ingresar una tarjeta de crédito.

    <table>
    <tr>
        <th colspan="2">CU005</th>
    </tr>
    <tr>
        <td>Nombre</td>
        <td>Reservación de hotel</td>
    </tr>
    <tr>
        <td>Autor</td>
        <td>Jose Moran </td>
    </tr>

    <tr>
        <td>Actores</td>
        <td>Usuario tipo turista</td>
    </tr>
    <tr>
        <td colspan="2">Precondiciones: <br>
        1. El usuario no debe tener sesión iniciada en el sistema<br>
        2. Haber realizado una búsqueda de hotel.
        </td>
    </tr>

    <tr>
        <td colspan="2">Flujo normal: <br>
        1. Selecciona el hotel<br>
        2. Elige la fecha de reservación<br>
        3. Elige el tipo de habitación<br>
        4. Ingresa su tarjeta de crédito<br>
        5. Presiona el botón de reservar<br>
        6. El sistema valida que se encuentre disponible la fecha seleccionada. <br>
        7. El sistema realiza el proceso de pago, detallado posteriormente. <br>
        8. El sistema muestra una respuesta de reservación completada
        </td>
    </tr>

    <tr>
        <td colspan="2">Flujo Alternativo: <br>
        6. El sistema muestra un mensaje de fecha no disponible<br>
        7. El sistema muestra un mensaje de problema con pago
    </tr>

    <tr>
        <td colspan="2">Postcondiciones: <br>
        Ninguno<br>
    </tr>
    </table>


## Renta de Autos
1. El sistema debe permitir al usuario de tipo renta de autos nuevos registros de autos por medio de un formulario

    <table>
    <tr>
        <th colspan="2">CU006</th>
    </tr>
    <tr>
        <td>Nombre</td>
        <td>Regristro de auto nuevos por formulario</td>
    </tr>
    <tr>
        <td>Autor</td>
        <td>Jose Moran </td>
    </tr>

    <tr>
        <td>Actores</td>
        <td>Usuario tipo renta de autos</td>
    </tr>
    <tr>
        <td colspan="2">Precondiciones: <br>
        El usuario no debe tener sesión iniciada en el sistema
        </td>
    </tr>

    <tr>
        <td colspan="2">Flujo normal: <br>
        1. Ingresa el modelo del auto<br>
        2. Ingresa la linea del auto<br>
        3. Ingresa la marca del auto<br>
        4. Subir la foto del auto<br>
        5. Ingresa el valor por el cual se renta<br>
        6. Presiona el botón de registrar<br>
        7. El sistema retorna una respuesta de registro completado
    </tr>

    <tr>
        <td colspan="2">Flujo Alternativo: <br>
        6. El sistema retorna una respuesta de error debido a que el auto no cumple con los requisitos para ser rentado<br>
    </tr>

    <tr>
        <td colspan="2">Postcondiciones: <br>
        El auto puede ser rentado por un turista<br>
    </tr>
    </table>

2. El sistema debe permitir al usuario de tipo renta de autos nuevos registros de autos por medio de carga masiva

    <table>
    <tr>
        <th colspan="2">CU007</th>
    </tr>
    <tr>
        <td>Nombre</td>
        <td>Regristro de auto nuevos por carga masiva</td>
    </tr>
    <tr>
        <td>Autor</td>
        <td>Jose Moran </td>
    </tr>

    <tr>
        <td>Actores</td>
        <td>Usuario tipo renta de autos</td>
    </tr>
    <tr>
        <td colspan="2">Precondiciones: <br>
        El usuario debe tener sesión iniciada en el sistema
        </td>
    </tr>

    <tr>
        <td colspan="2">Flujo normal: <br>
        1. Presiona el botón de carga masiva<br>
        2. Carga el archivo con información de carga masiva<br>
        3. Presiona el botón de registrar<br>
        4. El sistema retorna una respuesta de registro completado
    </tr>

    <tr>
        <td colspan="2">Flujo Alternativo: <br>
        4. El sistema retorna una respuesta de error debido a que el archivo no cumple con el formato establecido<br>
    </tr>

    <tr>
        <td colspan="2">Postcondiciones: <br>
        Se creará un nuevo registro de renta con el usuario y el auto<br>
    </tr>
    </table>

3. El sistema debe permitir al usuario de tipo turista reservar autos en una fecha en específico y realizar el pago con una tarjeta de crédito.

    <table>
    <tr>
        <th colspan="2">CU008</th>
    </tr>
    <tr>
        <td>Nombre</td>
        <td>Reservación de autos</td>
    </tr>
    <tr>
        <td>Autor</td>
        <td>Jose Moran </td>
    </tr>

    <tr>
        <td>Actores</td>
        <td>Usuario tipo turista</td>
    </tr>
    <tr>
        <td colspan="2">Precondiciones: <br>
        El usuario no debe tener sesión iniciada en el sistema
        </td>
    </tr>

    <tr>
        <td colspan="2">Flujo normal: <br>
        1. Elige el auto<br>
        2. Elige fecha de reservación o elige opción de rentar hoy<br>
        3. Ingresa su tarjeta de crédito<br>
        4. Presiona el botón de reservar<br>
        5. El sistema valida que se encuentre disponible la fecha seleccionada. <br>
        6. El sistema realiza el proceso de pago, detallado posteriormente. <br>
        7. El sistema muestra una respuesta de reservación completada
        </td>
    </tr>

    <tr>
        <td colspan="2">Flujo Alternativo: <br>
        6. El sistema muestra un mensaje de fecha no disponible<br>
        7. El sistema muestra un mensaje de problema con pago
    </tr>
    <tr>
        <td colspan="2">Postcondiciones: <br>
        El auto puede ser rentado por un turista<br>
    </tr>
    </table>

## Pasaporte COVID

1. El sistema deberá permitir al usuario tipo turista registrar su pasaporte COVID, dicho pasaporte cuenta con los siguientes atributos mínimos:
    - Tipo de Vacuna
    - Numero de dosis colocadas
    - Fecha de cada vacuna

    <table>
    <tr>
        <th colspan="2">CU009</th>
    </tr>
    <tr>
        <td>Nombre</td>
        <td>Registro pasaporte COVID</td>
    </tr>
    <tr>
        <td>Autor</td>
        <td>Jose Moran </td>
    </tr>

    <tr>
        <td>Actores</td>
        <td>Usuario tipo turista</td>
    </tr>
    <tr>
        <td colspan="2">Precondiciones: <br>
        El usuario no debe tener sesión iniciada en el sistema
        </td>
    </tr>

    <tr>
        <td colspan="2">Flujo normal: <br>
        1. Selecciona el tipo de vacuna<br>
        2. Ingresa el número de dosis colocadas<br>
        3. Ingresa la fecha de vacunación<br>
        4. Si el número de dosis es mayor al número de fechas ingresadas regresa al paso 3<br>
        5. Presiona el botón de registrar <br>
        6. El sistema retorna respuesta de registro correcto <br>
    </tr>

    <tr>
        <td colspan="2">Postcondiciones: <br>
        El turista puede viajar a diferentes países<br>
    </tr>
    </table>

2.  El sistema permitirá descargar un certificado digital con un código QR del pasaporte COVID de cada usuario tipo turista registrado.

    <table>
    <tr>
        <th colspan="2">CU010</th>
    </tr>
    <tr>
        <td>Nombre</td>
        <td>Descarga de pasaporte COVID</td>
    </tr>
    <tr>
        <td>Autor</td>
        <td>Jose Moran </td>
    </tr>

    <tr>
        <td>Actores</td>
        <td>Usuario</td>
    </tr>
    <tr>
        <td colspan="2">Precondiciones: <br>
        Ninguna
        </td>
    </tr>

    <tr>
        <td colspan="2">Flujo normal: <br>
        1. El usuario escaneara el código QR <br>
        2. Su dispositivo lo redireccionara a la página web <br>
        3. El usuario podrá descargar el pasaporte COVID de la persona a quien le corresponde dicho código QR
    </tr>
    </table>

3. EL sistema deberá permitir al administrador crear nuevos esquemas de vacunación, debe realizar validaciones que este no exista.

    <table>
    <tr>
        <th colspan="2">CU011</th>
    </tr>
    <tr>
        <td>Nombre</td>
        <td>Crear esquema de vacunación </td>
    </tr>
    <tr>
        <td>Autor</td>
        <td>Jose Moran </td>
    </tr>

    <tr>
        <td>Actores</td>
        <td>Usuario tipo administrador</td>
    </tr>
    <tr>
        <td colspan="2">Precondiciones: <br>
        El usuario no debe tener sesión iniciada en el sistema
        </td>
    </tr>

    <tr>
        <td colspan="2">Flujo normal: <br>
        1. Ingresa el tipo de vacuna<br>
        2. Ingresa el número de dosis para completar el esquema<br>
        3. Presiona el botón de registrar <br>
        4. El sistema retorna respuesta de registro correcto <br>
    </tr>

    <tr>
        <td colspan="2">Flujo Alternativo: <br>
        4. El sistema retorna una respuesta de error debido a que dicho esquema ya existe<br>
    </tr>
    </table>

4. El sistema permitiría al administrador modificar el número de dosis para un esquema en específico.

   <table>
    <tr>
        <th colspan="2">CU012</th>
    </tr>
    <tr>
        <td>Nombre</td>
        <td>Modificar esquema de vacunación </td>
    </tr>
    <tr>
        <td>Autor</td>
        <td>Jose Moran </td>
    </tr>

    <tr>
        <td>Actores</td>
        <td>Usuario tipo administrador</td>
    </tr>
    <tr>
        <td colspan="2">Precondiciones: <br>
        El usuario no debe tener sesión iniciada en el sistema
        </td>
    </tr>

    <tr>
        <td colspan="2">Flujo normal: <br>
        1. Selecciona el esquema a modificar<br>
        2. Ingresa el número de dosis para completar el esquema<br>
        3. Presiona el botón de modificar <br>
        4. El sistema retorna respuesta de modificación correcta <br>
    </tr>
    </table>

## Vuelos
1. El sistema deberá permitir al usuario administrador crear vuelos de forma manual.

    <table>
    <tr>
        <th colspan="2">CU013</th>
    </tr>
    <tr>
        <td>Nombre</td>
        <td>Registró de vuelos por formulario</td>
    </tr>
    <tr>
        <td>Autor</td>
        <td>Jose Moran </td>
    </tr>

    <tr>
        <td>Actores</td>
        <td>Usuario tipo administrador</td>
    </tr>
    <tr>
        <td colspan="2">Precondiciones: <br>
        El usuario no debe tener sesión iniciada en el sistema
        </td>
    </tr>

    <tr>
        <td colspan="2">Flujo normal: <br>
        1. Ingresa el origen del vuelo<br>
        2. Ingresa el destino del vuelo<br>
        3. Ingresa el precio del vuelo<br>
        4. Marca si es ida y vuelta<br>
        5. Ingresa el tipo de boleto (Ejecutivo, primera clase, etc.)<br>
        7. Presiona el botón de registrar<br>
        8. El sistema retorna una respuesta de registro completado
    </tr>

    <tr>
        <td colspan="2">Postcondiciones: <br>
        Se crea el un nuevo vuelo<br>
    </tr>
    </table>

2. El sistema deberá permitir al usuario administrador crear vuelos en carga masiva.

    <table>
    <tr>
        <th colspan="2">CU014</th>
    </tr>
    <tr>
        <td>Nombre</td>
        <td>Registro de vuelos por carga masiva</td>
    </tr>
    <tr>
        <td>Autor</td>
        <td>Jose Moran </td>
    </tr>

    <tr>
        <td>Actores</td>
        <td>Usuario tipo administrador</td>
    </tr>
    <tr>
        <td colspan="2">Precondiciones: <br>
        El usuario debe tener sesión iniciada en el sistema
        </td>
    </tr>

    <tr>
        <td colspan="2">Flujo normal: <br>
        1. Presiona el botón de carga masiva<br>
        2. Carga el archivo con información de carga masiva<br>
        3. Presiona el botón de registrar<br>
        4. El sistema retorna una respuesta de registro completado
    </tr>

    <tr>
        <td colspan="2">Flujo Alternativo: <br>
        4. El sistema retorna una respuesta de error debido a que el archivo no cumple con el formato establecido<br>
    </tr>

    <tr>
        <td colspan="2">Postcondiciones: <br>
        El sistema crea todos los vuelos ingresados en el archivo de carga<br>
    </tr>
    </table>

3. El sistema deberá permitir al usuario tipo turista comprar vuelos con una tarjeta de crédito.

    <table>
    <tr>
        <th colspan="2">CU016</th>
    </tr>
    <tr>
        <td>Nombre</td>
        <td>Compra de vuelos con tarjeta de crédito</td>
    </tr>
    <tr>
        <td>Autor</td>
        <td>Jose Moran </td>
    </tr>

    <tr>
        <td>Actores</td>
        <td>Usuario tipo turista</td>
    </tr>
    <tr>
        <td colspan="2">Precondiciones: <br>
        El usuario debe tener sesión iniciada en el sistema
        </td>
    </tr>

    <tr>
        <td colspan="2">Flujo normal: <br>
        1. Elige el vuelo<br>
        2. Ingresa su tarjeta de crédito<br>
        3. Presiona el botón de reservar<br>
        4. El sistema valida que se encuentre disponible la fecha seleccionada. <br>
        5. El sistema realiza el proceso de pago, detallado posteriormente. <br>
        6. El sistema muestra una respuesta de reservación completada
        </td>
    </tr>

    <tr>
        <td colspan="2">Flujo Alternativo: <br>
        5. El sistema muestra un mensaje de fecha no disponible<br>
        6. El sistema muestra un mensaje de problema con pago
    </tr>
    <tr>
        <td colspan="2">Postcondiciones: <br>
        Se crea un nuevo registro de compra de boleto<br>
    </tr>
    </table>

## Banco
1. El sistema deberá ser capaz de emitir pagos con tarjeta de crédito, se debe contar con los siguientes datos:
    - Nombre
    - Fecha de caducidad
    - CVV
    
    se debe validar que los datos sean correctos y que dicha tarjeta cuente con fondos. El monto total para pagar al banco será calculado de la siguiente manera:
    ```
    totalBanco = totalCompra + totalCompra * 0.04
    ```  

    <table>
    <tr>
        <th colspan="2">CU016</th>
    </tr>
    <tr>
        <td>Nombre</td>
        <td>Realizar pagos con tarjeta de credito</td>
    </tr>
    <tr>
        <td>Autor</td>
        <td>Jose Moran </td>
    </tr>

    <tr>
        <td>Actores</td>
        <td>Usuario tipo turista</td>
    </tr>
    <tr>
        <td colspan="2">Precondiciones: <br>
        El usuario debe tener sesión iniciada en el sistema
        </td>
    </tr>

    <tr>
        <td colspan="2">Flujo normal: <br>
        1. Ingresa el nombre<br>
        2. Ingresa la fecha de caducidad<br>
        3. Ingresa el CVV<br>
        4. Presiona el botón de realizar pago<br>
        5. El sistema responde con mensaje de pago satisfactorio<br>
    </tr>

    <tr>
        <td colspan="2">Flujo Alternativo: <br>
        5. El sistema muestra un mensaje de datos incorrectos<br>
        6. El sistema muestra un mensaje de fondos insuficientes
    </tr>
    <tr>
        <td colspan="2">Postcondiciones: <br>
        Se crea un nuevo registro de pago<br>
    </tr>
    </table>

## Reseñas
1. El sistema deberá permitir al usuario tipo turista crear calificaciones con una escala de 5 estrellas, siendo 5 la mejor puntación. Además, el usuario puede complementar con un comentario su calificación.

    <table>
    <tr>
        <th colspan="2">CU017</th>
    </tr>
    <tr>
        <td>Nombre</td>
        <td>Registro de reseña</td>
    </tr>
    <tr>
        <td>Autor</td>
        <td>Jose Moran </td>
    </tr>

    <tr>
        <td>Actores</td>
        <td>Usuario tipo turista</td>
    </tr>
    <tr>
        <td colspan="2">Precondiciones: <br>
        El usuario debe tener sesión iniciada en el sistema
        </td>
    </tr>

    <tr>
        <td colspan="2">Flujo normal: <br>
        1. Selecciona el servicio que se brindó<br>
        2. Ingresa la valoración que le dara<br>
        3. Ingresa un comentario (opcional)<br>
        4. Presiona el botón de publicar<br>
        5. El sistema responde con mensaje de reseña publicada satisfactoriamente<br>
    </tr>

    <tr>
        <td colspan="2">Postcondiciones: <br>
        Se crea una nueva reseña para el servicio seleccionado<br>
    </tr>
    </table>

2. El sistema deberá permitir al usuario tipo turista y al administrador ver las calificaciones por negocios, es decir, por hotel o renta de autos.

    <table>
    <tr>
        <th colspan="2">CU018</th>
    </tr>
    <tr>
        <td>Nombre</td>
        <td>Ver reseñas por negocio</td>
    </tr>
    <tr>
        <td>Autor</td>
        <td>Jose Moran </td>
    </tr>

    <tr>
        <td>Actores</td>
        <td>Usuario tipo turista y administrador</td>
    </tr>
    <tr>
        <td colspan="2">Precondiciones: <br>
        El usuario debe tener sesión iniciada en el sistema
        </td>
    </tr>

    <tr>
        <td colspan="2">Flujo normal: <br>
        1. Selecciona el negocio<br>
        2. El sistema mostrara todas las reseñas<br>
    </tr>

    

    <tr>
        <td colspan="2">Flujo Alternativo: <br>
        3. Si el usuario lo desea puede ordenar las reseñas por puntuación<br>
    </tr>
    </table>

# REQUERIMIENTOS NO FUNCIONALES

1.  El sistema debe ser cross-plataform: web y móvil, la aplicación móvil está enfocada exclusivamente a turistas por lo que únicamente debe contar con:
    - Generar unas rentas de autos
    - Realizar reservaciones en hoteles
    - Compra de vuelos
    - Generar reseñas y lectura de reseñas

    <table>
    <tr>
        <th>
        Atributo de calidad
        </th>
        <td>
        Movilidad y Modularidad
        </td>
    </tr>
    <tr>
        <th>
        Estimulo
        </th>
        <td>
        Facil accesibilidad
        </td>
    </tr>
    
    <tr>
        <th>
        Fuente del estímulo 
        </th>
        <td>
        Turistas
        </td>
    </tr>
    <tr>
        <th>
        Ambiente 
        </th>
        <td>
        Ejecucion en un lugar remoto
        </td>
    </tr>
    <tr>
        <th>
        Respuesta 
        </th>
        <td>
        El sistema es capaz de funcionar en dispositivos móviles y páginas web
        </td>
    </tr>
    </table>

2. Para cada inicio de sesión, tanto en la página web como en la aplicación móvil se debe de
generar un sistema que garantice que el usuario que inicia sesión si es quien dice ser
    <table>
    <tr>
        <th>
        Atributo de calidad
        </th>
        <td>
        Seguridad
        </td>
    </tr>
    <tr>
        <th>
        Estimulo
        </th>
        <td>
        Garantizar la seguridad del sistema
        </td>
    </tr>
    <tr>
        <th>
        Fuente del estímulo 
        </th>
        <td>
        Usuarios
        </td>
    </tr>
    <tr>
        <th>
        Ambiente 
        </th>
        <td>
        Pagina de inicio de sesión del sistema
        </td>
    </tr>
    <tr>
        <th>
        Respuesta 
        </th>
        <td>
        El sistema debe garantizar que la persona que inicio sesión es quien dice ser
        </td>
    </tr>
    <tr>
        <th>
        Medida de respuesta 
        </th>
        <td>
        El usuario es capaz de ingresar el código enviado a su correo y se verifica que es quien dice ser
        </td>
    </tr>
    </table>

3. El diseño de la aplicación debe de ser capaz de
adaptarse a cualquier dispositivo, brindar la mejor experiencia de usuario al utilizar el producto y tener una apariencia eficaz y agradable.
    <table>
    <tr>
        <th>
        Atributo de calidad
        </th>
        <td>
        Diseño y Usabilidad
        </td>
    </tr>
    <tr>
        <th>
        Estimulo
        </th>
        <td>
        Brindar la mejor experiencia de usuario siendo eficaz y agradable
        </td>
    </tr>
    <tr>
        <th>
        Fuente del estímulo 
        </th>
        <td>
        Usuarios
        </td>
    </tr>
    <tr>
        <th>
        Ambiente 
        </th>
        <td>
        Sistema Full Trip
        </td>
    </tr>
    <tr>
        <th>
        Respuesta 
        </th>
        <td>
        Uso frecuente de aplicación para viajes, renta de autos y hospedaje
        </td>
    </tr>
    <tr>
        <th>
        Medida de respuesta 
        </th>
        <td>
        Alta demanda de los usuarios en ambas presentaciones de la aplicación (Móvil y Web)
        </td>
    </tr>
    </table>

4. El sistema debe ser capaz de comunicarse entre diferentes microservicios siguiendo el contrato establecido entre las diferentes entidades que desarrollen, es decir, puede consumir microservicios de otras organizaciones sin tener fallos.

    <table>
    <tr>
        <th>
        Atributo de calidad
        </th>
        <td>
        Interoperabilidad
        </td>
    </tr>
    <tr>
        <th>
        Estimulo
        </th>
        <td>
        Mantener la integridad del sistema
        </td>
    </tr>
    <tr>
        <th>
        Fuente del estímulo 
        </th>
        <td>
        Informacion envida a diferentes microservicios
        </td>
    </tr>
    <tr>
        <th>
        Ambiente 
        </th>
        <td>
        Sistema
        </td>
    </tr>
    <tr>
        <th>
        Respuesta 
        </th>
        <td>
        El sistema es capaz de mantener la integridad sin presentar fallos a la hora de cambiar fuente de servicios
        </td>
    </tr>
    <tr>
        <th>
        Medida de respuesta 
        </th>
        <td>
        Alta demanda de la aplicación ante cambio de microservicios
        </td>
    </tr>
    </table>

5. El sistema debe ser construido en base a SOA con el fin de mantener una alta disponibilidad y resistencia a fallos.

    <table>
    <tr>
        <th>
        Atributo de calidad
        </th>
        <td>
        Disponibilidad
        </td>
    </tr>
    <tr>
        <th>
        Estimulo
        </th>
        <td>
        Mantener el sistema siempre disponible para los usuarios
        </td>
    </tr>
    <tr>
        <th>
        Fuente del estímulo 
        </th>
        <td>
        Consistencia de información
        </td>
    </tr>
    <tr>
        <th>
        Ambiente 
        </th>
        <td>
        Sistema
        </td>
    </tr>
    <tr>
        <th>
        Respuesta 
        </th>
        <td>
        El sistema debe ser capaz de mantener la consistencia de información ante caídas de algún servicio
        </td>
    </tr>
    <tr>
        <th>
        Medida de respuesta 
        </th>
        <td>
        Información consistente y persistente después de un fallo
        </td>
    </tr>
    </table>

