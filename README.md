# Description

This is the design blueprints of aktos message passing library for distributed controller systems to build huge systems by following microservices architecture.

### Design Principles

This design is created to match with the following requirements: 

* Easy debugging of distributed systems (eg. with `nc` by a human readable data format, JSON)
* Easy re-implementation (for another language)
* Interoperable with both server-side and client-side (browser) applications. 
* Provide authentication and authorization layers out of the box
* Easily understandable for adapting new team members 
* Easily extendable to support new protocols

# Contents

* [Message Format](./message-format.md)
* [Message Routing](./message-routing.md)
* [Actor Design](./actor-design.md)
* [Authentication](./authentication.md)
* [Authorization](./authorization.md)


# Implementations

## v2.x

* [aktos-dcs-node](https://github.com/aktos-io/aktos-dcs-node)
  * Language: NodeJS/Javascript (in Livescript)
  * aktos-dcs version: 2.x
  * aktos-dcs implementation status: Complete
  * Additional Features: 
    * CouchDCS driver: Enables using CouchDB in DCS network
    * Protocols: 
      * Siemens S7
      * Omron Hostlink, FINS
      * Raspberry GPIo

## v1.x

> NOTE: v1.x will be deprecated in the near future.

* [aktos-dcs-python](https://github.com/aktos-io/aktos-dcs-python) : Python implementation.
* [aktos-dcs-cs](https://github.com/aktos-io/aktos-dcs-cs) : C# implementation both visual and command line examples 
