Priorities of controllers and services can be changed. This means you can change the order in which they get constructed and initialized. This allows you to, with even higher precision, control which modules have access to what code.

The priorities of modules can be set in the **src/ReplicatedStorage/Settings/RuntimeSettings.luau** file.

There are two fields in this file:

```luau
CONTROLLER_PRIORITIES: { [string]: number }
SERVICE_PRIORITIES: { [string]: number }
```

Each field is a dictionary which has the module name as the key and the priority as the value.
Next to those, there is also a field which holds the value all modules will default to if not specified.

```luau
DEFAULT_PRIORITY: number
```