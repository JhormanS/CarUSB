# CarUSB

Aplicación **Car Clicker** organizada bajo el patrón **MVC (Modelo–Vista–Controlador)**, separando los datos, la presentación y la lógica de interacción en componentes independientes que se comunican entre sí.

## Conformación

- **Modelo (`model/`)**
  Representa el estado de la aplicación. Mantiene la colección de autos y sus atributos (nombre, imagen y contador de clicks), así como la referencia al auto actualmente seleccionado. No conoce nada sobre la interfaz.

- **Vistas (`view/`)**
  Se encargan exclusivamente de renderizar la información en pantalla y de capturar las interacciones del usuario.
  - **Vista de lista:** muestra el listado de autos disponibles y notifica cuál fue seleccionado.
  - **Vista de detalle:** muestra el auto seleccionado junto con su contador y propaga los clicks realizados sobre él.

- **Controlador (`controller/`)**
  Actúa como intermediario entre el modelo y las vistas. Inicializa la aplicación, expone los datos que las vistas necesitan, actualiza el estado del modelo ante cada interacción y solicita a las vistas que se vuelvan a renderizar.

El flujo es unidireccional y desacoplado: las vistas notifican eventos al controlador → el controlador actualiza el modelo → el controlador pide a las vistas que re-rendericen con el nuevo estado.

## Rama principal

`main`