# Shelly

SHELLY: The go-to access control app.

This Python library provides convenient access to the Shelly cloud API, allowing you to manage your relays, rollers and lights.


[Shelly Shop](https://www.shelly.com/en/products/shop)<br>

Request Feature/Suggestion: https://forms.gle/efGD5DuTpWsX96GG7

[//]: # ([![Downloads]&#40;https://static.pepy.tech/badge/kisi&#41;]&#40;https://pepy.tech/project/kisi&#41;)
## Installation
```console
pip install shelly
```
Shelly supports Python 3+.

## Usage
#### Default
```python
import shelly
```

#### Authentication

Before making requests, you need to authenticate using your Shelly API key. Initialize the `Connect` class with your API key:

```python
from shelly import Connect

base_url = "Your Cloud Server Address"
api_key = "Your Authorization cloud key"
sh = Connect(base_url,api_key)
```
OR
```python
import shelly 

base_url = "Your Cloud Server Address"
api_key = "Your Authorization cloud key"
sh = shelly.Connect(base_url,api_key)
```
Get Key & Server address from here [Shelly Control Cloud Dashboard](https://control.shelly.cloud/#/settings/user)

### Relay
#### Fetch Devices
```python
# Fetch device status
sh.get_device('device_id')

```

#### Control Devices
```python
# Control device
sh.control_device(channel , 'on'/'off' , device_id)

```
#### Bulk Control Devices
```python
# Bulk Control device
sh.bulk_control_relays('devices')

# Parameters:
#        - devices (list of dict): List of devices to control, each device should be a dictionary with keys:
#            - "id" (int): ID of the device.
#            - "channel" (int): Index of the relay or switch component.
```

### Rollers
#### Control Roller Direction
```python
# Control Roller
sh.control_roller_direction(direction , device_id)

```

#### Control Roller Position
```python
# Control Roller
sh.control_roller_position(position , device_id)

```

#### Bulk Control Roller
```python
# Bulk Control Roller
sh.bulk_control_rollers(device_id)

```

### Lights
#### Control Lights
```python
# Bulk Control Roller
sh.control_light(turn=None , white=None , red=None , green=None , blue=None , gain=None , device_id=None)

```