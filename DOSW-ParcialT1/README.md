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