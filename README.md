# Flexisip Deployment with External Database and Domain Migration

This project demonstrates how to deploy a SIP proxy using Flexisip with an external database backend and how to support domain migration or domain changes for SIP users.

The objective of this repository is to illustrate how a SIP infrastructure can:

• store SIP registrations in an external database
• support multiple SIP domains
• migrate users between domains
• maintain compatibility with existing SIP clients

The deployment is based on:

* Flexisip SIP Proxy
* External database (MySQL / PostgreSQL)
* Linux server environment
* SIP clients such as Linphone

---

# Use Case

Many VoIP providers change SIP domains during infrastructure migrations.

Example:

Old domain

```
sip.example.com
```

New domain

```
sip.yourdoamin.com
```

Users previously registered with:

```
user@sip.example.com
```

must be redirected or migrated to:

```
user@sip.yourdomain.com
```

Flexisip can manage this by using an external database to resolve user locations and route calls appropriately.

---

# Architecture Overview

```
SIP Client
    |
    v
Flexisip Proxy
    |
    v
External Database
    |
    v
User Location / Domain Mapping
```

Flexisip handles SIP signaling while the external database maintains user and domain mapping information.

---

# Repository Structure

```
flexisip-external-db-domain-routing
│
├── README.md
│
├── docs
│   ├── architecture.md
│   ├── installation.md
│   ├── database-schema.md
│   ├── domain-migration.md
│   └── troubleshooting.md
│
├── configs
│   └── flexisip.conf
│
├── database
│   └── schema.sql
│
└── diagrams
    └── flexisip-domain-architecture.png
```

---

# Features

External SIP user database
Multi-domain SIP support
Domain migration support
User location storage
Scalable SIP routing

---

# Documentation

Detailed documentation is available in the `docs` directory.

* architecture
* installation
* database schema
* domain migration process
* troubleshooting

---

# License

