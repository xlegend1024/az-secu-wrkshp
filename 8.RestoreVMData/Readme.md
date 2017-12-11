# 8. Restore VM / Data

Protect SQL Server Virtual Machine using Azure Backup Service.

## Architecture

![lab8](./images/lab8.png)

## Review Restore Options

1. Search Recovery Service Vault and click the service on the result list.

    ![restore](./images/8.1.png)

1. Find 'Backup Items' on the lift lists and click 'Backup Items'

    ![restore](./images/8.2.png)

    Click Azure Virtual Machine.

    ![restore](./images/8.3.png)

    Click backup item.

    ![restore](./images/8.4.png)

1. You'll see two options on the menu

    ![restore](./images/8.5.png)

    * __Restore VM__

        You can create a Virtual Machine from the backup.
        ![restore](./images/8.6.png)

    * __File Recovery__

        You can restore some files from the backup withou restoreing whole entire Virtual Machine.
        ![restore](./images/8.7.png)

## Restore Files

File recovery option is a quick and easy way to revoer some files from the backup.

1. Select __File Recovery__ option

    ![restore](./images/8.5.png)

1. Download Executeable 

    * Click 'Download executeable'

    ![restore](./images/8.7.png)

    * Run the download file as administrator

    ![restore](./images/8.8.png)

1. Use password to mount disk to your local computer

1. Access disks

    You can restore some files from backup without restoring a Virtual Machine.

    ![restore](./images/8.9.png)

1. When you finished file recovery work, unmount the disks from your local computer.

    ![restore](./images/8.10.png)

---

[>> NEXT](https://github.com/xlegend1024/az-secu-wrkshp/tree/master/9.RemoveResources/Readme.md)
