[![License: Apache2](https://img.shields.io/badge/License-Apache2-green.svg)](https://opensource.org/licenses/Apache-2.0)

# B1 Assistant Lite
A small Alexa Skill integration with SAP Business One for the SMB Summit Hackathon
[![SAP](https://i.imgur.com/80Ohjn6.png)](http://cloudplatform.sap.com/)

## Description
A sample [Alexa Skill](https://www.amazon.co.uk/b?ie=UTF8&node=10068517031) to demonstrate the integration between Amazon Echo x SAP Business One

## Requirements
* [Amazon developer account](https://developer.amazon.com/)
* [SAP Cloud Platform Trial Account With Cloud Foundry enviroment](https://developers.sap.com/tutorials/hcp-create-trial-account.html)


## Installation - 
### Step 1 - Deployment of the Backend
* Download or clone this repository.
* Update the hostname and other parameters on the [MANIFEST](manifest.yml) file.
* From the root directory of this app. Execute:
```sh
$ cf push --random-route
```
At the end of the process, Cloud Platform should return a Route as shown below. We will need it later.
![SAP](https://i.imgur.com/exuU9vu.png)

### Step 2 - Creation of Alexa Skill
* Follow [these steps to create a new Alexa Skill](https://developer.amazon.com/docs/devconsole/create-a-skill-and-choose-the-interaction-model.html#create-a-new-skill)
* When asked for a *Model* choose *Custom*.
* Once the skill is created, look for the [option JSON Editor in the skill menu](https://i.imgur.com/TO1FOvG.png). Replace its content [with our model](skill/IntentSchema.json)
* On the skills endpoit, set it with the route showed previously.
* For the certificate option choose *My development endpoints is a sub-domain...*
* You are ready to test your skill

## Test
<img src="https://i.imgur.com/xkw6lXx.png" alt="drawing" width="600"/>

* You can test your skill from the development console (as shown above)
* Or from your Amazon Device, as long as it is logged with the same account you used on Amazon Developer
* There is also a [Postman Collection](test/Alexa.postman_collection.json) that you can use to test your backend. You can use it against your SAP Cloud Platform app Route OR with a local environment (on your machine) and long as you set the environment variables. Full list of variables available in the [MANIFEST](manifest.yml) file.

## Support and Contributions  
This repository is provided "as-is". With no Warranty or support. Feel free to open issues.

## License
Copyright (c) 2020 SAP SE or an SAP affiliate company. All rights reserved. This project is licensed under the Apache Software License, version 2.0 except as noted otherwise in the [LICENSE](LICENSES/Apache-2.0.txt) file.

