# FusionInventory 

!!! info
    You can find information about FusionInventory on the website: [fusioninventory.org](https://www.fusioninventory.org)

## Features implemented

All features of FusionInventory are not yet implemented into FusionResolveIT.

This is the features:

| Feature | Implemented |
| ------- | ----------- |
| Local inventory (computer / server) | yes |
| Network discovery (scan network) | no |
| Network inventory (inventory by SNMP of switches, routers, printers) | no |
| Software deployment | no |


## Agents

When installing the agent, in the installer, or in the configuration file (part with *server = *), it's required to define the URL of the server FusionResolveIT.

This is needed to communicate with the server and to send inventory data to it.

**The url is your FusionResolveIT URL + */api/v1/fusioninventory***

!!! example
    For an url like *https://support.local/*, the URL will be *https://support.local/api/v1/fusioninventory*
