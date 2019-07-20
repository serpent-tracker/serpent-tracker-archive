# Serpent Tracker Microservices
The code for all services of serpent tracker

# Creating A Secure Secret Key

```
import binascii
import os
binascii.hexlify(os.urandom(24))
```
Exit the shell and then set it as a ENV var where deploying:

`export SECRET_KEY=XXX`

# Running Tests
**Ensure you also set a secret key using above steps**

**Ensure you set REACT_APP_USERS_SERVICE_URL=http://localhost**

Tests can be ran with `sh test.sh`