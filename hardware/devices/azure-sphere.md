# Azure Sphere


#### Overview

- Avnet MT - Azure Sphere
- Bought the device Oct 2019 via element14 India Online Shop
- Realized, It supports only Windows 10
- Currently Supports C++ and No Support for Modern language like Python or NodeJS
- Its meant for Manufactures to Securely Develop and Deploy App via Edge Computing

#### Challenges

- Recently Microsoft Released Azure SDK for Linux
- They have changed the Platform Auth Setup and We need to Migrate Tenant to work Properly
- Unfortuantely, I deleted the Azure Subscriptions and Unable to use the Device anymore as i am getting error "The device is already claimed by a different tenant"

Nov 14 2020 :
- As of today, the support team still investigating to solve this issue

#### How am i going to use ?
- Create a micro-python app and make this as a Home Bridge to send commands to NodeRED via http. (It has a Wifi Enabled Chip)
