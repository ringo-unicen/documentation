
Agente 

![agente](https://raw.githubusercontent.com/ringo-unicen/documentation/master/images/Disenio.%20Agent.png)

Node Manager 

![node manager](https://raw.githubusercontent.com/ringo-unicen/documentation/master/images/Disenio.%20Node%20Manager.png)

Api

Modelo

![modelo](https://raw.githubusercontent.com/ringo-unicen/documentation/master/images/Disenio.%20Model.png)






This page shows the detailed design for each component

Agent

The following diagram shows how the detailed design of the agent component:

![agent design](https://raw.githubusercontent.com/ringo-unicen/documentation/master/images/detailed-design-agent.png)

Operations (pseudocode)

configure (info: Object)
```javascript
configuration.write(info);
if (info.active) {
  router.activate();
} else {
  router.delegate();
}
```

start
```javascript
router.start();
collector.start():
```
stop
```javascript
router.stop();
collector.stop():
```






Node Manager 

Component design

![Node Manager design](https://raw.githubusercontent.com/ringo-unicen/documentation/master/images/detailed-design-nodemanager.png)

Operations (pseudocode)

create (type: String)
```javascript
var vminfo = vmmanager.create(type);
vmmanager.run(vminfo)
return vminfo;
```

start (id: String)
```javascript
var vminfo = vmmanager.get(id);
var agent = new Agent(vminfo);
agent.start();
```

stop (id: String)
```javascript
var vminfo = vmmanager.get(id);
var agent = new Agent(vminfo);
agent.stop();
```

config(id: String, options: Object)
```javascript
var vminfo = vmmanager.get(id);
var agent = new Agent(vminfo);
agent.config(options);
```

terminate(id: String)
```javascript
vmmanager.terminate(id);
```


