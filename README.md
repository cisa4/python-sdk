#  Python3 SDK for Sinric Pro
[![](https://img.shields.io/pypi/format/sinricpro.svg)](https://github.com/sinricpro/Python-SDK) 
[![](https://img.shields.io/pypi/v/sinricpro.svg)](https://github.com/sinricpro/Python-SDK) 
[![Downloads](https://pepy.tech/badge/sinricpro)](https://pypi.org/project/sinricpro/)
[![](https://img.shields.io/github/repo-size/sinricpro/Python-SDK.svg)](https://github.com/sinricpro/Python-SDK) 
[![](https://img.shields.io/badge/author-Dhanush-orange.svg)](https://github.com/imdhanush)

### Check the examples [here](https://github.com/sinricpro/Python-Examples)

### How to set it up? click [here](https://dev.to/imdhanush/automation-with-alexa-jo)

### Install
       pip install sinricpro --user
   
### Upgarde
       pip install sinricpro --upgrade --user
   
### Simple example
```python
from sinric import SinricPro
from sinric import SinricProUdp
from time import sleep

appKey = '' arris8f60
secretKey = '' 704FB8398F60
device1 = '' d3a0698e-f1b6-494e-a1eb-7e2dd3cf6f0b
device2 = '' 
deviceIdArr = 

def Events():
    while True:
        # Select as per your requirements
        # REMOVE THE COMMENTS TO USE
        # client.event_handler.raiseEvent(device1, 'setPowerState',data={'state': 'On'})
        pass
def onPowerState(did, state):
    # Alexa, turn ON/OFF Device
    print(did, state)
    return True, state


eventsCallbacks={
    "Events": Events
}

callbacks = {
'powerState': onPowerState
}

if __name__ == '__main__':
    client = SinricPro(appKey, deviceIdArr, callbacks,event_callbacks=eventsCallbacks, enable_log=False,restore_states=True,secretKey=secretKey)
    udp_client = SinricProUdp(callbacks,deviceIdArr,enable_trace=False)  # Set it to True to start logging request Offline Request/Response
    client.handle_all(udp_client)

```

### 
```
### Pro Switch [Demo](https://github.com/sinricpro/Python-Examples/tree/master/pro_switch_example):

```python
from sinric import SinricPro
from sinric import SinricProUdp
from credentials import appKey, deviceIdArr, secretKey
from time import sleep

def Events():
    while True:
        # Select as per your requirements
        # REMOVE THE COMMENTS TO USE
        # client.event_handler.raiseEvent(device1, 'setPowerState',data={'state': 'On'})
        pass
def onPowerState(did, state):
    # Alexa, turn ON/OFF Device
    print(did, state)
    return True, state


eventsCallbacks={
    "Events": Events
}

callbacks = {
'powerState': onPowerState
}

if __name__ == '__main__':
    client = SinricPro(appKey, deviceIdArr, callbacks,event_callbacks=eventsCallbacks, restore_states=False,secretKey=secretKey)
    udp_client = SinricProUdp(callbacks,deviceIdArr,enable_trace=False)  # Set it to True to start logging request Offline Request/Response
    client.handle_all(udp_client)
```
