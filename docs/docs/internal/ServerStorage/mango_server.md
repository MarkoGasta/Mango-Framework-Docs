# Mango Server
## Description
The core functionality of MangoServer is similar to [MangoClient](../../ReplicatedStorage/mango_client), though there are additional functions that MangoServer introduces.

## Usage
### Adding a dependency
The call to get a dependency exactly matches the call you make to the MangoClient manager:
```luau
-- Service A:
local ServerStorage = game:GetService("ServerStorage")
local MangoServer = require(ServerStorage.MangoServer)
local ServiceB = MangoServer.Require("ServiceB")
```

### Caching for Players
MangoServer adds an internally managed field of values, created for each player. This prevents the need of creating cache tables in each service to store player associated values.
```luau
MangoServer.SetCacheField("timesJumped", 42)
warn(MangoServer.GetCacheField("timesJumped")) --> 42
```

### General Cache Handlers
There are additional sub-handlers included in the manager. It allows for applying general cache field values automatically as soon as the game starts. These values are intended to be universally used. They exist so no one service is responsible for creating globally accessible values. (for example, a value for the time a player joined)

More documentation can be found in the *TEMPLATE.luau* file provided in the handler container.

## API
### .Require()
Used for requiring dependencies from services.
```luau
MangoServer.Require(moduleName: string): (string) -> any
```

### .SetCacheField()
Caches a value for an internally managed field of values, created for each player. 
```luau
MangoServer.SetCacheField(fieldName: string, newValue: any?): (string, any?) -> nil
```

### .GetCacheField()
Fetches the value of a field item in the previously mentioned field of cached per-player values.
```luau
MangoServer.GetCacheField(fieldName: string): (string) -> any?
```