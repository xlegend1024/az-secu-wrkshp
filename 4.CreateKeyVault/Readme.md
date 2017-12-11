# 4. Create Key Vault

Create Azure Key Vault and create a key that will be used for SQL Server TDE key protection.

## Architecture

![lab4](./images/lab4.png)

## Set up an Azure Active Directory Service Principal

Before set up a Azure AD Service Principal, open notepad and copy following text and paste it into the notepad.
```
AppID:
ObjID:
spKey:
KeyVaultURL:
```

![key vault note](./images/4.1.png)

1. Search Azure Active and click the service

    ![app reg](./images/4.2.png)

1. Select 'App registration'

    ![app reg](./images/4.3.png)

1. Click '+ New application registration'

    ![app reg](./images/4.4.png)

1. Type name and sign-on URL.

    |Name|Application Type|Sign-on URL|
    |---|---|---|
    |securityworkshop###|Web app / API|http://contosoworkshop###.com|

    > Note: Please replace ### into random 3 digit.

    ![app reg](./images/4.5.png)

    Click to finish the application registration.

1. Click your application

    ![app reg](./images/4.6.png)

1. Copy Applicatoin ID and Object ID and paste them to your notepad

    ![app reg](./images/4.7.png)

1. To create a key, click the 'Keys'

    ![app reg](./images/4.8.png)

1. Type descriotion and select expires as 'In 1 year' and click 'Save'

    ![app reg](./images/4.9.png)

1. When a key is saved, you'll see password on the screen. Copy the vaule and paste it to your notepad.

    ![app reg](./images/4.10.png)

1. When application registration is done, please make sure you have AppID, ObjID and the password vaule on your note.

    ![app reg](./images/4.11.png)

## Create a Key Vault

1. Click  '+ New' and search Key Vault. And click "Create'

1. Type new key vault name and select your resource group.

    |Name|Subscription|Resource Group|Location|Pricing tier|Access policies|
    |---|---|---|---|---|---|
    |safevault###|*yoursubscription*|workshop-###|west us|Standard|1 principal selected|

    ![app reg](./images/4.12.png)

1. Click 'Access policies' and click '+ Add new'

    ![app reg](./images/4.13.png)

1. Select 'Key, Secret, & Certificate Management'

    ![app reg](./images/4.14.png)

1. Click 'Select principal'. And then search 'securityworkshop###' and click service principal fomr the result.

    ![app reg](./images/4.15.png)

1. Check cryptographic operation 'Decrypt', 'Encrypt', 'Unwrap Key', 'Wrap Key', 'Verify' and 'Sign'.

    ![app reg](./images/4.16.png)

1. Click 'OK'

    ![app reg](./images/4.17.png)

1. Click 'Create'

    ![app reg](./images/4.18.png)

1. When a Key Vault is created, copy Key Vault DNS Name and paste it to your note.

    ![app reg](./images/4.19.png)

    Your note should have all four vaules like following.

    ![app reg](./images/4.20.png)

## Add a Key

1.  Click 'Keys' and then click '+ Add'

    ![app reg](./images/4.21.png)

1. Type name to create an new key. Please name it as '__securityworkshopkey__'. And then click 'Create'

    ![app reg](./images/4.22.png)


---

[>> NEXT](https://github.com/xlegend1024/az-secu-wrkshp/tree/master/5.CreateSQLVM/Readme.md)
