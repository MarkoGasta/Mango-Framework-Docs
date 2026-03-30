# Services
## Description
Similar to Controllers, it's a folder used for storing server-sided module scripts. The modules from this folder are automatically required and initialized by the server runtime.

## Service Structure Template
You can copy this and use it as a template, though you don't have to. Try to follow the outlined structure for the framework to work as indented.
```lua
local Service = {}

--[=[
    The construction method is the first method that is called
    immediately after the service has been required by the
    runtime script.

    This method is intended to wrap the whole scope of the 
    service so try to avoid placing anything outside of it.

    This wrapping is done to prevent the possibility of
    recursive requiring of modules from throwing errors.

    The method name can be redefined in the RuntimeSettings
    module located at ReplicatedStorage.Settings.RuntimeSettings
]=]--
function Service.__Construct()

    --[=[
        This is the initialization function, it's purpose is to handle any
        code that might require dependencies that couldn't be loaded
        in the construction method call.

        It is called only when all other services have been constructed.

        I found only rare cases when this is actually necessary, but in case
        those cases appear it's there.

        Locally you can call it whatever, but the actual exported name of
        the function can be changed in the RuntimeSettings.
    ]=]--
    local function Init()

    end

    --[=[
        Exporting the init script.
    ]=]--
    Service.__Init = Init
end

return Service
```