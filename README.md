# RETO 1
# NOTAS:

# CLIENTS
- presentacion de posibles consumidores de los servicios expuestos en AWS

# FRONTEND 
- Definicion de elementos de ruteo (Route 53)
- Disponibilizacion de sitio web Angular utilizando S3 Bucket como almacenador de sitio estatico
- Amazon Cloudfront para definir el dominio de exposicion y TLS para cifrado de comunicacion.

# SECURITY
- WAF y Shield para proteccion de ataques hacia el sitio web y los microservicios para disponibilizar la informacion de los clientes
- IAM, asignacion de permisos y roles a los usuarios que deben tener accesos a configuraciones de EKS Clusters, ECs y demas recursos en AWS
- Cloudwatch para el manejo de trazabilidad y logs en los microservicios en cluster
- Disponibilizacion de SQS para manejo de servicios por eventos
- Elastic Cache para el manejo de rendimiento de consultas a la base de datos (Redis)
- Seguridad para acceso a los microservicios por medio de Cognito para solicitud de Access Token


# BACKEND
- API Gateway para el control de acceso (Validacion de access token) hacia el EKS Cluster
- Definicion de EKS cluster para contenedor de Kubernetes para disponibilizacion de pods de alta disponibilidad, con minimo de 2 hasta 8 pods de autoescalado horizontal.
- Servicio mesh para conectar servicios, supervisar las comunicaciones entre sus aplicaciones y controlar el tráfico de red y seguridad
- Fargate para el manejo de infraestructura a utilizar en el EKs Cluster, encargado de actualizaciones y parches requeridas para el entorno, control de pods y escalado de las instancias EC2   

# ON-PREMISE
- Se crea VPC para el control y manejo de comunacion de red con VPN para mayor seguridad entre microservicios y servicios on-premises
- Solicitud de capa de seguridad en servicios on-premises para determinar que usuarios tendran acceso a la informacion de los servicios de cada pais

# THIRD-PARTY
- API Gateway para el manejo de acceso a internet del cluster

# DB
- Creacion de base de datos RDS para la persistencia de datos
- Elastic Cache Redis para el manejo de rendimiento en consultas y disponibilizacion de datos al cliente para mejorar el rendimiento de la DB
- Amazon DynamoDB para el manejo de configuraciones estaticas en caso de ser requerido.

# Esquema de diagrama regional (Replicacion y disponibilidad en dos regiones)

# Tecnologias
- Angular 19
- Spring boot
- Tomcat
- Kubernetes (Contenedor de aplicaciones)
- Uso de clustes y pods para manejo de escalibilidad y disponibilidad de la aplicacion

*************************

# RETO 2
# NOTAS:

# CLIENTS
- Representacion de consumidores de aplicacion

# Security
- uso de cognito para el acceso a los servicios

# BACKEND
- Uso de EKS Cluster, pod kubernetes, fargate, para el control y manejo de pods
- Segmentacion de trabajos realizados en la aplicaciones para mejorar el rendimiendo y evitar problemas de disponibilidad al realizar cambios en procesos especificos
- Uso de BFF como orquestador de micro servicios expuestos en frontEnd
- Uso de componente event o lambda para el manejo de informacion y actualizacion de cache para mejorar el rendimiento en DB
- Uso de MESH para el control y seguridad de comunicacion entre microservicios

# CACHING
- Uso de Elastic Cache Redis para obtener la informacion de manerja eficiente y evitar saturaciones a la base de datos
- Elastic Search para mejorar el rendimiendo de busquedas indexando las consultas hacia la BD

# EVENT-DRIVEN
- Uso de SQS o Kafka para el envio de eventos para normalizacion y transformacion de datos hacia elastic Search  y enviar al componente o funcion lambda para la replicacion de datos.

# DB

## CONCLUSION
# Beneficios de Usar Elasticsearch en Esta Arquitectura
- Consultas rápidas: Elasticsearch está diseñado para búsquedas full-text y análisis en tiempo real.
- Reducción de carga a la base de datos principal: Reduce la cantidad de consultas directas a RDS
- Escalabilidad: Maneja grandes volúmenes de datos con facilidad.
- Búsquedas avanzadas: Permite búsquedas por filtros, agregaciones, análisis de logs y más.
- Indexación eficiente: Permite organizar los datos de forma que las consultas sean más eficientes.
- La segmentacion de componentes de la aplicacion permite un mejor manejo y actualizacion de servicios evitando posibles errores de codificacion

