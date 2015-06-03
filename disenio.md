This page shows the detailed design for each component

Agent

The following diagram shows how the detailed design of the agent component:

![agent design](https://raw.githubusercontent.com/ringo-unicen/documentation/master/images/detailed-design-agent.png)






Node Manager operations (pseudocode)

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


