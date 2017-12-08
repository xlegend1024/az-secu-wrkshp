# 2. Create Virtual Network

## Architecture

Create first resource in the resource group.

![alt text](./images/3.1.png)

1. Create Virtual network

    Click '+ new' and search 'Virtual Network'.

    Leave deployment model as 'Resource Manager'.

    ![alt text](./images/3.1.3.png)

    Use following name and location for the lab.

    |Name|Address Space|Subscription|Resource Group|Location|Subnet Name|Subnet range|
    |---|---|---|---|---|---|---|
    |workshop-###|10.0.0.0/16|*yoursubscription*|*yourresourcegroup*|West US|sqldev|10.0.1.0/24|

    It'll be look like following.

    ![alt text](./images/3.1.4.png)

    Click 'Create'.

---

[>> NEXT](https://github.com/xlegend1024/az-secu-wrkshp/tree/master/3.CreateNSG/Readme.md)
