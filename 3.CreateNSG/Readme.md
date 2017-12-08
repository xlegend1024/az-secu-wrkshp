# 3. Create Network Security Group

Create a Network Security Group and assign the NSG to the subnet in your Virtual Network.

## Architecture

## Create Network Security Group

1. Click '+ New' and search Network Security Group.

    Click 'Create' button.

    ![new nsg](./images/3.1.png)

1. Name to your new Network Security Group and create.

    Type name and select your resource group. And please check 'Pin to dashboard'.

    ![new nsg](./images/3.2.png)

    |Name|Subscription|Resource Group|Location|
    |---|---|---|---|
    |dev-wus-nsg|*yoursubscription*|workshop-###|*West US*|

## Add Inbound Security Rules

1. Click Netowkr Security Group.

    ![nsg img](./images/3.3.png)

1. Click 'Inbound Security rules' to add new rule.

    ![nsg img](./images/3.4.png)

1. Click 'Add'.

    ![nsg img](./images/3.5.png)

1. Click 'Basic'.

    ![nsg img](./images/3.6.png)

1. Select 'RDP' from the Service list.

    ![nsg img](./images/3.7.png)

1. Click 'OK'.

    ![nsg img](./images/3.8.png)

1. One update is done, you'll see port 3389 TCP is added as RDP on the inbound security rule.

    ![nsg img](./images/3.9.png)

## Apply the rules to subnet

1. Open your Network Security Group.

    ![nsg img](./images/3.3.png)

1. Click 'Subnets' and then click '+ Associate'.

    ![nsg img](./images/3.10.png)

1. Click '1.Virtual Network' and then choose your virtual network.

    ![nsg img](./images/3.11.png)

1. Choose 'Default' subnet.

    ![nsg img](./images/3.12.png)

1. Confirm your selected options and click 'OK' to continue.

    ![nsg img](./images/3.13.png)

1. Once update is done, you'll see the subnet on the associated list.

    ![nsg img](./images/3.14.png)
---

[>> NEXT](https://github.com/xlegend1024/az-secu-wrkshp/tree/master/4.CreateKeyVault/Readme.md)
