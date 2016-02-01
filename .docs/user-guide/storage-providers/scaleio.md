#ScaleIO

Scale-out with simplified storage management

---

## Overview
The ScaleIO registers a storage driver named `scaleio` with the `REX-Ray`
driver manager and is used to connect and manage ScaleIO storage.

## Configuration
The following is an example configuration of the ScaleIO driver.

```yaml
scaleio:
    endpoint:             https://[scaleio gateway IP]:443/api
    insecure:             false
    useCerts:             true
    userName:             gatewayuser
    password:             gatewaypassword
    systemID:             0
    systemName:           scaleio_systemname
    protectionDomainID:   0
    protectionDomainName: corp
    storagePoolID:        0
    storagePoolName:      gold
```

For information on the equivalent environment variable and CLI flag names
please see the section on how non top-level configuration properties are
[transformed](./config/#all-other-properties).

## Activating the Driver
To activate the ScaleIO driver please follow the instructions for
[activating storage drivers](/user-guide/config#activating-storage-drivers),
using `scaleio` as the driver name.

## Examples
Below is a '/etc/rexray/config.yml'
```yaml

rexray:
 storageDrivers:
  - ScaleIO
ScaleIO:
  endpoint: https://192.168.2.193:443/api #<<- /API is mandatory here !
  insecure: true
  userName: admin
  password: Password123!
  systemName: ScaleIO@EMCDEBlog
  protectionDomainName: PD_EMCDEBlog
  storagePoolName: PoolEMCDEBlog
```




Below is a full `rexray.yml` file that works with ScaleIO.

```yaml
rexray:
  storageDrivers:
  - scaleio
scaleio:
  endpoint: endpoint
  insecure: true
  userName: username
  password: password
  systemName: tenantName
  protectionDomainName: protectionDomainName
  storagePoolName: storagePoolName
```
