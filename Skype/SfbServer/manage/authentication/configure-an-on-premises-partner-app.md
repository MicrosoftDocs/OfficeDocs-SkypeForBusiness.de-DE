---
title: Konfigurieren einer lokalen Partneranwendung für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 696f2b26-e5d0-42b5-9785-a26c2ce25bb7
description: 'Zusammenfassung: Konfigurieren einer lokalen Partneranwendung für Skype for Business Server.'
ms.openlocfilehash: 8f735de5c988dfea0da1adacdc4a77200d3a663d
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992342"
---
# <a name="configure-an-on-premises-partner-application-for-skype-for-business-server"></a>Konfigurieren einer lokalen Partneranwendung für Skype for Business Server
 
**Zusammenfassung:** Konfigurieren Sie eine lokale Partneranwendung für Skype for Business Server.
  
Nachdem Sie das OAuthTokenIssuer-Zertifikat zugewiesen haben, müssen Sie Ihre Skype for Business Server-Partneranwendungen konfigurieren. (Das Verfahren, das besprochen werden soll, konfiguriert sowohl Microsoft Exchange Server 2013 als auch SharePoint als Partneranwendungen, was optional ist.) Wenn Sie eine lokale Partneranwendung konfigurieren möchten, müssen Sie zunächst das folgende Windows PowerShell-Skript kopieren und den Code in Notepad (oder einen beliebigen anderen Text-Editor) einfügen:
  
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

Nachdem Sie den Code kopiert haben, speichern Sie das Skript mit einem. PS1-Dateierweiterung (beispielsweise C:\Scripts\ServerToServerAuth.ps1). Beachten Sie, dass Sie vor dem Ausführen dieses Skripts die Metadaten-URLs https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 und die http://atl-sharepoint-001.litwareinc.com/_layouts/15/metadata/json/1 von Ihren Exchange 2013-und SharePoint-Servern verwendeten Metadaten-URLs ersetzen müssen. Informationen dazu, wie Sie die Metadaten-URL des jeweiligen Produkts identifizieren können, finden Sie in der Produktdokumentation für Exchange 2013 und SharePoint.
  
In der letzten Zeile des Skripts werden Sie bemerken, dass das Cmdlet „Set-CsOAuthConfiguration“ mit der folgenden Syntax aufgerufen wird:
  
```PowerShell
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000
```

Da beim Aufrufen von „Set-CsOAuthConfiguration“ der Parameter „Realm“ nicht verwendet wurde, wird als Bereich automatisch der vollqualifizierte Domänenname (FQDN) Ihrer Organisation festgelegt (z. B. litwareinc.com). Wenn der Bereichsname anders als Ihr Organisationsname lautet, sollten Sie den Bereichsnamen wie folgt mit angeben:
  
```PowerShell
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"
```

Nachdem Sie diese Änderungen vorgenommen haben, können Sie das Skript ausführen und sowohl Exchange 2013 als auch SharePoint als Partneranwendungen konfigurieren, indem Sie die Skriptdatei innerhalb der Skype for Business Server-Verwaltungsshell ausführen. Beispiel:
  
```PowerShell
C:\Scripts\ServerToServerAuth.ps1
```

Beachten Sie, dass Sie dieses Skript auch dann ausführen können, wenn Exchange 2013 und SharePoint Server nicht installiert sind: Es werden keine Probleme auftreten, wenn Sie beispielsweise SharePoint Server als Partneranwendung konfigurieren, obwohl SharePoint Server nicht installiert ist.
  
Bei Ausführung des Skripts würden Sie dann eine Fehlermeldung erhalten, die wie folgt aussieht:
  
```PowerShell
New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."
```

Diese Fehlermeldung hat meist zwei Bedeutungen: 1.) Eine der im Skript angegebenen URLs ist ungültig (d. h. eine Ihrer Metadaten-URLs ist tatsächlich keine Metadaten-URL) oder 2.) eine der Metadaten-URLs konnte nicht kontaktiert werden. In diesem Fall sollten Sie überprüfen, ob die URLs korrekt geschrieben sind und auf sie zugegriffen werden kann, und das Skript danach erneut ausführen.
  
Nachdem Sie die Partneranwendung für Skype for Business Server erstellt haben, müssen Sie Skype for Business Server so konfigurieren, dass es sich um eine Partneranwendung für Exchange 2013 handelt. Sie können Partneranwendungen für Exchange 2013 konfigurieren, indem Sie das Skript configure-EnterprisePartnerApplication. ps1 ausführen. Sie müssen lediglich die Metadaten-URL für Skype for Business Server angeben und darauf hinweisen, dass es sich bei Skype for Business Server um die neue Partneranwendung handelt. 
  
Wenn Sie Skype for Business Server als Partneranwendung für Exchange konfigurieren möchten, öffnen Sie die Exchange-Verwaltungsshell, und führen Sie einen ähnlichen Befehl wie den folgenden aus:
  
```PowerShell
"c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://SkypePro.contoso.com/metadata/json/1" -ApplicationType "Lync"
```


