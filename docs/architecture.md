# Flexisip Architecture with External Database

Flexisip acts as a SIP proxy and registrar while storing user registration data in an external database.

## Architecture

```
SIP Client
    |
    v
Flexisip Proxy
    |
    v
Authentication Module
    |
    v
External Database
```

## Components

### Flexisip Proxy

Handles:

* SIP signaling
* SIP routing
* SIP registration

### External Database

Stores:

* user credentials
* domain mapping
* registration location

### SIP Client

Registers using SIP credentials and communicates through Flexisip.
