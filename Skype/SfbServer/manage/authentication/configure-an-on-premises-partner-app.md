---
title: Konfigurieren einer lokalen Partneranwendung für Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 696f2b26-e5d0-42b5-9785-a26c2ce25bb7
description: 'Zusammenfassung: Konfigurieren einer lokalen Partneranwendung für Skype for Business Server.'
---

# <a name="configure-an-on-premises-partner-application-for-skype-for-business-server"></a>Konfigurieren einer lokalen Partneranwendung für Skype for Business Server
 
**Zusammenfassung:** Konfigurieren Sie eine lokale Partneranwendung für Skype for Business Server.
  
Nachdem Sie das OAuthTokenIssuer-Zertifikat zugewiesen haben, müssen Sie ihre Skype for Business Server Partneranwendungen konfigurieren. (Das zu besprechende Verfahren konfiguriert sowohl Microsoft Exchange Server 2013 als auch SharePoint als Partneranwendungen, was optional ist.) Um eine lokale Partneranwendung zu konfigurieren, müssen Sie zunächst das folgende Windows PowerShell Skript kopieren und den Code in Editor (oder einen anderen Text-Editor) einfügen:
  
```PowerShell
if ((Get-CsPartnerApplication -ErrorAction SilentlyContinue) -ne $Null)
   {
       Remove-CsPartnerApplication app
   }

$exch = Get-CsPartnerApplication microsoft.exchange -ErrorAction SilentlyContinue
        
if ($exch -eq $null)
   {
      New-CsPartnerApplication -Identity microsoft.exchange -MetadataUrl https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 -ApplicationTrustLevel Full 
    }
else
    {
       if ($exch.ApplicationIdentifier -ne "00000002-0000-0ff1-ce00-000000000000")
          {
             Remove-CsPartnerApplication microsoft.exchange
New-CsPartnerApplication -Identity microsoft.exchange -MetadataUrl https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 -ApplicationTrustLevel Full 
           }
        else
           {
             Set-CsPartnerApplication -Identity microsoft.exchange -ApplicationTrustLevel Full 
           }
     }

$shp = Get-CsPartnerApplication microsoft.sharepoint -ErrorAction SilentlyContinue
        
if ($shp -eq $null)
   {
      New-CsPartnerApplication -Identity microsoft.sharepoint -MetadataUrl http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx -ApplicationTrustLevel Full 
    }
else
    {
       if ($shp.ApplicationIdentifier -ne "00000003-0000-0ff1-ce00-000000000000")
          {
             Remove-CsPartnerApplication microsoft.sharepoint
  
             New-CsPartnerApplication -Identity microsoft.sharepoint -MetadataUrl https://atl-sharepoint-001.litwareinc.com/_layouts/15/metadata/json/1 -ApplicationTrustLevel Full 
           }
        else
           {
             Set-CsPartnerApplication -Identity microsoft.sharepoint -ApplicationTrustLevel Full 
            }
   }

Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000
```

Speichern Sie das Skript nach dem Kopieren des Codes mithilfe einer .PS1 Dateierweiterung (z. B. C:\Scripts\ServerToServerAuth.ps1). Beachten Sie, dass Sie vor dem Ausführen dieses Skripts die Metadaten-URLs `https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1` bzw`http://atl-sharepoint-001.litwareinc.com/_layouts/15/metadata/json/1`. die Metadaten-URLs ersetzen müssen, die von Ihren Exchange 2013- bzw. SharePoint-Servern verwendet werden. Informationen dazu, wie Sie die Metadaten-URL des jeweiligen Produkts identifizieren können, finden Sie in der Produktdokumentation für Exchange 2013 und SharePoint.
  
In der letzten Zeile des Skripts werden Sie bemerken, dass dort ein Set-CsOAuthConfiguration-Cmdlet mit der folgenden Syntax aufgerufen wird:
  
```PowerShell
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000
```

Da beim Aufruf des Set-CsOAuthConfiguration-Cmdlet der Realm-Parameter nicht verwendet wurde, wird als Bereich automatisch der FQDN (Fully Qualified Domain Name) Ihrer Organisation festgelegt (z. B. litwareinc.com). Wenn der Bereichsname anders als Ihr Organisationsname lautet, sollten Sie den Bereichsnamen wie folgt mit angeben:
  
```PowerShell
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"
```

Nachdem Sie diese Änderungen vorgenommen haben, können Sie das Skript ausführen und sowohl Exchange 2013 als auch SharePoint als Partneranwendungen konfigurieren, indem Sie die Skriptdatei in der Skype for Business Server Verwaltungsshell ausführen. Beispiel:
  
```PowerShell
C:\Scripts\ServerToServerAuth.ps1
```

Beachten Sie, dass Sie dieses Skript auch dann ausführen können, wenn Sie nicht sowohl Exchange 2013 als auch SharePoint Server installiert haben:, es treten keine Probleme auf, wenn Sie beispielsweise SharePoint Server als Partneranwendung konfigurieren, obwohl SharePoint Server nicht installiert ist.
  
Bei Ausführung des Skripts würden Sie dann eine Fehlermeldung erhalten, die wie folgt aussieht:
  
```PowerShell
New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."
```

Diese Fehlermeldung hat meist zwei Bedeutungen: 1.) Eine der im Skript angegebenen URLs ist ungültig (d. h. eine Ihrer metadata-URLs ist keine echte metadata-URL); oder 2.) Eine der metadata-URLs konnte nicht kontaktiert werden. In diesem Fall sollten Sie überprüfen, ob die URLs korrekt geschrieben und zugreifbar sind, und Sie sollten das Skript danach erneut ausführen.
  
Nachdem Sie die Partneranwendung für Skype for Business Server erstellt haben, müssen Sie Skype for Business Server als Partneranwendung für Exchange 2013 konfigurieren. Sie können Partneranwendungen für Exchange 2013 konfigurieren, indem Sie das Skript Configure-EnterprisePartnerApplication.ps1 ausführen. Sie müssen lediglich die Metadaten-URL für Skype for Business Server angeben und angeben, dass Skype for Business Server die neue Partneranwendung ist. 
  
Um Skype for Business Server als Partneranwendung für Exchange zu konfigurieren, öffnen Sie die Exchange-Verwaltungsshell, und führen Sie einen Befehl wie den folgenden aus.
  
```PowerShell
"c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://SkypePro.contoso.com/metadata/json/1" -ApplicationType "Lync"
```


