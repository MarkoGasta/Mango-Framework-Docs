# Settings
## Description
This is a folder which contains all your settings / config files. They are available to both the client and the server.

You can bunch them up or, as I like to, name them based on their relation to controller-service systems (RoundService + RoundController -> RoundSettings)

## Structure
Ideally the settings files should contain to actual code, only field values. By this the standard structure of a settings file should just be:
```luau
return {
    SOME_KEY = "SOME_VALUE"
}
```