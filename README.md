# ConvertMS365SSO


## ติดตั้ง Module
Install-Module Microsoft.Graph.Authentication -Scope CurrentUser -Force

## เชื่อมต่อกับ MS Graph แล้ว Log in ด้วย User ที่เป็น Global Admin
Connect-MgGraph -Scopes "Directory.AccessAsUser.All"

## ตรวจสอบสถานะของแต่ละ Domain name
Get-MgDomain | Select-Object Id, IsVerified, IsDefault, AuthenticationType


## ปิด SSO สำหรับ Domain name : paocloud.co.th จากนั้นให้กดเป็น Primary ได้จากหน้า Azure
Update-MgDomain -DomainId "paocloud.co.th" -AuthenticationType Managed


