# 6. Encrypt Database

##

##

```sql
-- Use the EKM to open the asymmetric KEK that was previously created in the Key Vault
CREATE ASYMMETRIC KEY TDE_KEY -- Give the asymmetric KEK a name in SQL Server 
	FROM PROVIDER AzureKeyVault_EKM_Prov WITH
	PROVIDER_KEY_NAME = 'securityworkshopkey', -- The name of the asymmetric KEK in Azure Key Vault
	CREATION_DISPOSITION = OPEN_EXISTING -- To indicate that this is an existing key in Azure Key Vault
```

```sql
CREATE LOGIN TDE_Login 
FROM ASYMMETRIC KEY TDE_KEY ;
GO
```

```sql
-- Alter the TDE Login to add this Credential for use by the Database Engine to access the Key Vault
ALTER LOGIN TDE_Login 
ADD CREDENTIAL sqlCred;
GO
```

```sql
CREATE DATABASE [sampledb]
 CONTAINMENT = NONE
 ON  PRIMARY 
( NAME = N'sampledb', FILENAME = N'F:\Data\sampledb.mdf' , SIZE = 8192KB , FILEGROWTH = 65536KB )
 LOG ON 
( NAME = N'sampledb_log', FILENAME = N'F:\Log\sampledb_log.ldf' , SIZE = 8192KB , FILEGROWTH = 65536KB )
```

```sql
USE [sampledb];
GO
CREATE DATABASE ENCRYPTION KEY  
WITH ALGORITHM  = AES_256  
ENCRYPTION BY SERVER ASYMMETRIC KEY TDE_KEY;
GO
```

```sql
-- Alter the database to enable transparent data encryption.
-- This uses the asymmetric KEK you imported from Azure Key Vault to wrap your DEK.
ALTER DATABASE [sampledb] 
SET ENCRYPTION ON ;
GO
```

```sql
USE [sampledb]
GO

CREATE TABLE [dbo].[tblTemp](
	[idx] [int] IDENTITY(1,1) NOT NULL,
	[name] [nchar](10) NULL
) ON [PRIMARY]
GO

INSERT INTO [dbo].tblTemp VALUES ('workshop')
GO

SELECT * FROM [dbo].[tblTemp]
GO
```

---

[>> NEXT](https://github.com/xlegend1024/az-secu-wrkshp/tree/master/7.BackupVM/Readme.md)
