##Componentes


- **Node manager**: Responsible for managing the lifecycle of the nodes and making sure the are running.
- **Storage**: Stores information about the system, what are the SLAs, nodes and usage metrics.
- **Worker**: Performs work for a given SLA.
- **API**: Coordinates the work between the node manager and the storage. It exposes an API for the **Web** to consume
- **Web**: Displays the information about the system and allows an administrator to take actions
