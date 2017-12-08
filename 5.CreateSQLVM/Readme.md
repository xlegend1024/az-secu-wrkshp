# 5. Create SQL Server Vritual Machine

```bash
az vm extension set --publisher Microsoft.Compute \
                    --version 1.8 --name CustomScriptExtension \
                    --vm-name sqlserver2016 \
                    --resource-group az-secu-wrkshp \
                    --settings '{"commandToExecute":"powershell.exe Add-WindowsFeature Web-Server,Web-Asp-Net45,NET-Framework-Features"}'
```

Donwload sample asp.net website from [here](https://raw.githubusercontent.com/xlegend1024/az-secu-wrkshp/master/SampleWebApp/SampleWebApp.zip). Unzip SampleWebApp.zip and copy files to 'C:\inetpub\wwwroot\'.

---

[>> NEXT](https://github.com/xlegend1024/az-secu-wrkshp/tree/master/6.EncryptDB/Readme.md)
