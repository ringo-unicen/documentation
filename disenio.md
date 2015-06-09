
Agente 

![agente](https://raw.githubusercontent.com/ringo-unicen/documentation/master/images/Disenio.%20Agent.png)

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

![node manager](https://raw.githubusercontent.com/ringo-unicen/documentation/master/images/Disenio.%20Node%20Manager.png)

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

Api

Operations (pseudocode)

POST /node 
```javascript
var id = storage.persist(node);
var info = nodeManager.create(id, node.type);
node.vmInfo = info;
storage.update(node);
```

POST /node/{id}/created
```javascript
var node = storage.get(id);
var prev = storage.get(node.previous);
var next = storage.get(node.next);
next.previous = id;
prev.next = id;
storage.update(prev);
storage.update(next);

nodeManager.config(id, {prev: prev.id, next: next: next.id});
nodeManager.start(id);
nodeManager.config(prev.id, {next: id});

//More updates?
```

PUT /node/{id}
```javascript
var node = storage.get(id);
node.configuration = config;
nodeManager.config(id, config);
storage.update(node);
```

GET /node/{id}
```javascript
return storage.get(id);
```

GET /node
```javascript
return storage.list();
```

Modelo

![modelo](https://raw.githubusercontent.com/ringo-unicen/documentation/master/images/Disenio.%20Model.png)

