# architecture_system_bank

se debe incluir los siguientes diagramas en el diseño solicitado:

- Diagrama de contexto: Para usuarios no técnicos, muestra sistemas internos y externos con actores clave, breves descripciones y conexiones explicativas
- Diagrama de Contenedores: Para técnicos, representa aplicaciones, servicios, base de datos y mensajería, incluyendo componentes cloud sin mucho detalle, conexiones con descripciones breves:
- Diagrama de Componentes: Mayor detalle técnico. Incluye microservicios, patrones arquitectónicos y protocolos de comunicación con seguridad, destaca el uso de los componentes cloud.

Descripción del ejercicio:

Usted ha sido contratado por una entidad llamada BP como arquitecto de soluciones para diseñar un sistema de banca por internet , en  este sistema los usuarios podrán acceder al histórico de sus movimientos, realizar transferencias y pagos entre cuentas propias e interbancarias.

Toda la información referente al cliente se tomara de 2 sistemas, una plataforma CORE que contiene información básica de cliente, movimientos, productos y un sistema independiente que complementa la información del cliente cuando los datos se requieren en detalle. 

debido a que la norma exige que los usuarios sean notificados sobre los movimientos realizados, el sistema utiliza sistemas externos o propios para envio de notificaciones, mínimo 2 (email, SMS)

este sistema contara con 2 aplicaciones en front, una SPA y una aplicación móvil desarrollada en framework multiplataforma (justificar porque flutter y react native)

Ambas aplicaciones autenticaran a los usuarios mediante un servicio que usa el estándar Oauth2.0 para el cual no requiere implementar toda la lógica, ya que la compañía cuenta con un producto que puede ser configurado para este fin, sin embardo, debe dar recomendaciones sobre cuál es el mejor flujo de autenticación que se debería usar según el estándar.

tenga en cuenta que el sistema de onboarning para nuevos clientes en la aplicación móvil usa reconocimiento facial , por tanto, su arquitectura deberá considerarlo como parte del flujo de automatización y autenticación, a partir del onboarding el nuevo usuario podrá ingresar al sistema mediante usuario y clave, huella o algún otro método especifique alguno de los anteriores dentro de la arquitectura, también puede recomendar herramientas de  industria que realicen estas tareas y robustezca su aplicación.

El sistema utiliza una base de datos de auditoria que registra todas la acciones del cliente y cuenta con un mecanismo de persistencia de información para clientes recuentes, para este caso proponga una alternativa basada en patrones de diseño que relacioné los componentes que debería interactuar para conseguir el objetivo.

para obtener los datos del cliente el sistema pasa por una capa de integración compuesta por un api Gateway y consume los servicios necesarios de acuerdo con el tipo de transacción, inicialmente usted cuenta con 3 servicios principales, consulta de datos básicos, consulta de movimientos y transferencia que realiza llamados a servicios externos dependiendo del tipo, si considera que debería agregar mas servicios para mejorar el rendimiento de su arquitectura o agregar mas servicios para mejorar la respuesta de información de cliente, es libre de hacerlo.

Consideraciones:

Para este reto, mencione aquellos elementos normativos que considere importantes a tener en cuenta para entidades financieras, Ejemplo ley de datos personales, seguridad, etc....

Garantice en su arquitectura, alta disponibilidad (HA), tolerancia a fallos, recuperacion ante desastres (DR), seguridad y monitoreo, excelencia operativa y auto-healing.

si lo considera necesaria, su arquitectura puede contener elemnentos de infraestructura en nube, Azure u AWS, garantice baja latencia, cuenta con presupuesto para esto.

En lo posible plantee una arquitectura desacoplata con elementos y reutilizables y cohesionados ara otros componentes puedan adicionarse en el futuro.

El modelo debe ser desarollado bajo modelo C4 (Modelo de contexto, modelo de aplicación o contenedores y componentes), describa hasta el modelo que componentes