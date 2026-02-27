## David Santiago Cajamarca Cadena / Grupo 02

![img.png](docs/images/img.png)
![img_1.png](docs/images/img_1.png)

## PUNTO 1:

![DiagramaContextoParcial.jpg](docs%2Fimages%2FDiagramaContextoParcial.jpg)

## PUNTO 2:

- **FACTORY METHOD/creacional:** Elijo este patron debido que el enunciado dice textualmente 
"Cada proveedor expone la información de forma distinta y maneja sus propios
  campos obligatorios. El sistema interno de la Escuela NO puede depender de
  ninguna implementación específica." Este patron me aprece ideal debido que 
proporciona una interfaz para crear objetos en una super clase, mientras permite
a las subclases el tipo de objetos que crearian en este caso sus propios formularios
y campos obligatorios.

- **MEDIATOR/coportamiento:** Eleji este patron debido que en el enunciaco de menciona 
"El sistema debe permitir cambiar de proveedor sin modificar el código del
  proceso principal de pago. Cada tipo de medio de pago puede usar un
  proveedor diferente. El sistema debe unificar la respuesta en un solo formato
  institucional" Y el metodo mediator permite justamente reducir las dependencias 
caoticas entre objetos pues el patron restinge las comunicaciones directas entre objetos
forzandolos a colaborar unicamente atravez de un objeto mediador. Esto nos va a permitir 
mantener un solo formato de salida y el poder cambiar de objetos sin caos.

## PUNTO 3:

- **Funcionales:**
  - Guardar la informacion de pago en AWS Mongo Atlas
  - Guardar los certificados academicos asosiados en AWS S3 Bucket
  - Permitir que se pueda usar cualquier proveedor externo de los disponibles (Este usaria el patron Mediator)
- **No Funcionales:**
  - La interfaz de la app web debe tener la paleta de colores correspondiente a la escuela.
  - La app debe ser responsive.

## PUNTO 4:

![DiagramaUso.jpg](docs%2Fimages%2FDiagramaUso.jpg)

## punto 5: Análisis de requerimientos

## Código
RF-01

## Nombre
Guardar informacion de pago en AWS Mongo Atlas

## Descripción
La app web debe enviar la informacion de pago (cuenta de donde viene la transaccion, fecha, nombre titular, etc...)
a AWS Mongo Atlas y permitir que u usuario logueado consulte esta informacion desde la pagina.
## Cómo se ejecutará
1. El usuario ingresa a la página.
2. La pagina tiene un apartado de facturas al que el usuario accede.
3. El usuario completa los campos de confirmacion de identidad requeridos.
4. El aspirante envía la solicitud.
5. El sistema valida datos, registra la inscripción y confirma el resultado.

## Actor principal
Aspirante, es decir una persona interesada en inscribirse a la carrera.

## Precondiciones
- El aspirante tiene acceso a internet y a la página de la escuela.
- El formulario de inscripción está disponible para la carrera y periodo académico vigente.
- El aspirante cuenta con la información personal y académica requerida.

## Datos de entrada
- Datos personales: nombres, apellidos, tipo y número de documento, fecha de nacimiento.
- Servicio institucional elegido: Inscripción a Bootcamp, pago de certificados academicos, etc...

## Datos de salida
- Número de solicitud.
  - Estado.
- Mensajes de validación.
- Resumen de la solicitud registrada.

## Flujo básico
1. El aspirante ingresa a la sección Inscripción a la carrera.
2. El sistema presenta el formulario con los campos requeridos.
3. El aspirante diligencia los datos solicitados.
4. El aspirante adjunta documentos si el formulario lo solicita.
5. El aspirante confirma que la información es correcta y acepta términos.
6. El aspirante envía la inscripción.
7. El sistema valida obligatoriedad y formato de los campos.
8. El sistema registra la solicitud de inscripción.
9. El sistema muestra confirmación con el código de inscripción y el resumen.

## Flujo alterno
A1. Campos obligatorios incompletos
- En el paso 7, el sistema detecta campos obligatorios vacíos.
- El sistema muestra mensajes indicando qué campos faltan.
- El aspirante corrige y reintenta el envío.

A2. Formato inválido
- En el paso 7, el sistema detecta algun formato incorrecto.
- El sistema informa el error por campo y no registra la solicitud.
- El aspirante corrige y reenvía.

A3. Periodo o carrera no disponible
- En el paso 2 o 7, el sistema detecta que la carrerano está habilitada.
- El sistema muestra mensaje y no permite finalizar la inscripción.

A4. Fallo al guardar o falla del sistema
- En el paso 8, ocurre un error de persistencia o indisponibilidad.
- El sistema muestra un mensaje de error general y sugiere reintentar.
- La solicitud no queda registrada hasta completar el proceso correctamente. 
