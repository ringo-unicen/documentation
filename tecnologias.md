##Technologies

The different components are going to be implemented in the technologies described below

####Nodes

The nodes are going to be implemented as __docker__ containers based on custom images

####Agent

The agent component is going to use several different technologies for the different aspects of its behavior

- node.js + express: The Agent API is going to be exposed as REST services using this stack
- logstash: Logstash is going to be used for metrics colletion from the different logs
- iptables: The routing component is going to use iptables to route the calls at the network level.

####Storage

Storage is going to be implemented using __elastic search__, which provides flexible, document oriented, persistence, has full text search capabilities and a very powerful query language that includes faceted searches.

####Api

The API is going to use __node.js__ + __expressjs__ for publishing RESTful services.

####Node Manager

Similar to the other APIs in the architecture, node manager's API is going to be exposed using __node.js__ and __expressjs__. Since the node manager is going to be managing the __docker__ nodes, it's going to use a node.js docker client called __dockerode-promise__ 

####Web

The web application is going to be created using __angularjs__, it will be an front end only application that will consume the services exposed by the API.

####Policy Evaluator 

Besides using __node.js__ for the runtime environment (and exposing anyservices), the policy evaluator will use __nools__ as the rule engine.

