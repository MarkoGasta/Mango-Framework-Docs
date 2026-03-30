# MangoClient
## Description
This is the main point of interaction for your client modules. It's the module manager that requires and caches modules dependencies. This is the only module you will actually call require() on since all the other modules are cached by it and accessible with a method. It also ensures, to a certain extent, that modules dependencies are constructed before the module. It does this by constructing the dependency modules itself, making it a kind of automatic priority system.

## Usage
### Adding a dependency
If you want to add a dependency (ie. add access to controller B from controller A) you can call within the construct method of a controller:
```lua
-- Controller A:
local MangoClient = require(ReplicatedStorage.MangoClient)
local ControllerB = MangoClient.Require("ControllerB")
```

## API
### .Require()
Used for requiring dependencies from controllers.
```lua
MangoClient.Require(moduleName: string): (string) -> any
```

### .LockModule()
Prevents the module from being accessed again by .Require() making it's scope safe from outside calls.
```lua
MangoClient.LockModule(moduleName: string): (string) -> nil
```

## Configuration
Values up for configuration (located at the top of MangoClient):

```luau
- MODULE_WAIT_TIMEOUT: number -- Time that MangoClient will wait for a module before declaring it missing.
- MODULE_CONTAINERS: { [number] = Instance } -- Every container that MangoClient will grab top-level modules from, it will never grab descendants of those modules.
```