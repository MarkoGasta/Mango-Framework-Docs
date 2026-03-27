# MangoClient
## Description
This is the main point of interaction for your client modules. It's the module manager that requires and caches modules dependencies.

## Usage

## API

## Configuration
Values up for configuration

- **MODULE_WAIT_TIMEOUT**: *number* -- Time that MangoClient will wait for a module before declaring it missing.
- **MODULE_CONTAINERS**: *{[number] = Instance}* -- Every container that MangoClient will grab top-level modules from, it will never grab descendants of those modules.