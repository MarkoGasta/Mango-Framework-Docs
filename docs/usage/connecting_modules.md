# Connecting Modules
## Limits
**Mango Framework** makes connection modules really simple. As long as the modules you are connection are within the same scope:

- Client -> Client
- Server -> Server
- Client & Server -> Shared

## Client
To find where the manager is pulling modules from, you can check out the configuration section on it's [docs page](../../docs/internal/ReplicatedStorage/mango_client/#configuration).

```luau
-- ControllerA:
local ReplicatedSTorage = game:GetService("ReplicatedStorage")
local MangoClient = require(ReplicatedStorage.MangoClient)
local ControllerB = MangoClient.Require("ControllerB")
local Utils = MangoClient.Require("Utils")
```

## Server
```luau
-- ServiceA:
local ServerStorage = game:GetService("ServerStorage")
local MangoServer = require(ServerStorage.MangoServer)
local ServiceB = MangoServer.Require("ServiceB")
local Utils = MangoServer.Require("Utils")
```