##Arquitectura
- [Overview](#overview)
- [Componentes](#componentes)
- [Escenarios](#escenarios)
  - [Node: Crear](#node-crear)
  - [Node: Edit & Query](#node-edit--query)
  - [Node: Delete](#node-delete)
  - [Node Type](#node-type)
  - [Sla](#sla)
  - [Metrics](#metrics)
  - [Policies](#policies)

###Overview

The system architecture is modeled as a ring of nodes, where each node runs a particular service and an agent. The agent knows which service the node provides, and what are the previous and next nodes in the ring.

When a system needs to use a service, it will call any given node in the ring. If the node provides the given service, then the agent will just act as a proxy for the service in the node, the service complete the request and the response is returned to the caller.

If the node does not provide the service, then the agent will forward the call to the agent in the next node in the ring. This behavior continues until a node can fulfill the request or the request completes a full ring, in which case an error will be returned to the caller.

![Logic view](./images/Arquitectura.%20Overview.png)
  
###Componentes

- **Node manager**: Responsible for managing the lifecycle of the nodes and making sure they are running.
- **Storage**: Stores information about the system, what are the SLAs, nodes and usage metrics.
- **Worker**: Performs work for a given SLA.
- **API**: Coordinates the work between the node manager and the storage. It exposes an API for the **Web** to consume
- **Web**: Displays the information about the system and allows an administrator to take actions
- **Policy Evaluator**: Base on policies, evaluate metrics and take actions according those

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
