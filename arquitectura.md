##Arquitectura

###Componentes

- **Node manager**: Responsible for managing the lifecycle of the nodes and making sure the are running.
- **Storage**: Stores information about the system, what are the SLAs, nodes and usage metrics.
- **Worker**: Performs work for a given SLA.
- **API**: Coordinates the work between the node manager and the storage. It exposes an API for the **Web** to consume
- **Web**: Displays the information about the system and allows an administrator to take actions

![Logic view](./images/Arquitectura.%20Vista%20Logica.png)

###Escenarios
####Node: Crear

![Logic view](./images/Arquitectura.%20Vista%20Dinamica.%20Manage%20Node.%20Create.png)

####Node: Edit & Query

![Logic view](./images/Arquitectura.%20Vista%20Dinamica.%20Manage%20Node.%20Edit%20&%20Query.png)

####Node: Delete

![Logic view](./images/Arquitectura.%20Vista%20Dinamica.%20Manage%20Node.%20Delete.png)

####Node Type

![Logic view](./images/Arquitectura.%20Vista%20Dinamica.%20Manage%20Node%20Type.png)

####Sla

![Logic view](./images/Arquitectura.%20Vista%20Dinamica.%20Manage%20Sla.png)

####Metrics

![Logic view](./images/Arquitectura.%20Vista%20Dinamica.%20Metrics.png)

####Policies

![Logic view](./images/Arquitectura.%20Vista%20Dinamica.%20Policies.png)
