---
title: Konfigurieren einer lokalen partneranwendung für Skype für Business Server
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 696f2b26-e5d0-42b5-9785-a26c2ce25bb7
description: 'Zusammenfassung: Konfigurieren einer lokalen partneranwendung für Skype für Business Server.'
ms.openlocfilehash: 1377957797108f3cbc8e290b7750e9fba489cbf8
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "21009725"
---
# <a name="configure-an-on-premises-partner-application-for-skype-for-business-server"></a><span data-ttu-id="7bb6f-103">Konfigurieren einer lokalen partneranwendung für Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="7bb6f-103">Configure an on-premises partner application for Skype for Business Server</span></span>
 
<span data-ttu-id="7bb6f-104">**Zusammenfassung:** Konfigurieren einer lokalen partneranwendung für Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="7bb6f-104">**Summary:** Configure an on-premises partner application for Skype for Business Server.</span></span>
  
<span data-ttu-id="7bb6f-105">Nachdem Sie das Zertifikat OAuthTokenIssuer zugewiesen haben, müssen Sie klicken Sie dann Ihre Skype für partneranwendungen Business Server konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="7bb6f-105">After you have assigned the OAuthTokenIssuer certificate you must then configure your Skype for Business Server partner applications.</span></span> <span data-ttu-id="7bb6f-106">(Die Prozedur, die erläutert werden konfiguriert sowohl Microsoft Exchange Server 2013 und SharePoint als partneranwendungen, der optional ist). Um einer lokalen partneranwendung zu konfigurieren, müssen Sie starten durch Kopieren des folgenden Windows PowerShell-Skripts und den Code in Editor (oder einem anderen Texteditor) einfügen:</span><span class="sxs-lookup"><span data-stu-id="7bb6f-106">(The procedure about to be discussed configures both Microsoft Exchange Server 2013 and SharePoint to act as partner applications, which is optional.) To configure an on-premises partner application, you must start by copying the following Windows PowerShell script and pasting the code into Notepad (or any other text editor):</span></span>
  
```
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

<span data-ttu-id="7bb6f-107">Nach dem Kopieren des Codes, speichern Sie das Skript mithilfe einer. Erweiterung der ps1 (beispielsweise C:\Scripts\ServerToServerAuth.ps1).</span><span class="sxs-lookup"><span data-stu-id="7bb6f-107">After copying the code, save the script using a .PS1 file extension (for example, C:\Scripts\ServerToServerAuth.ps1).</span></span> <span data-ttu-id="7bb6f-108">Beachten Sie, dass Sie, bevor Sie dieses Skript ausführen, müssen Sie die Metadaten-URLs ersetzen https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 und http://atl-sharepoint-001.litwareinc.com/_layouts/15/metadata/json/1 mit den Metadaten-URLs, die jeweils von der Exchange 2013 und SharePoint Server verwendet.</span><span class="sxs-lookup"><span data-stu-id="7bb6f-108">Note that, before you run this script, you must replace the metadata URLs https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 and http://atl-sharepoint-001.litwareinc.com/_layouts/15/metadata/json/1 with the metadata URLs used by your Exchange 2013 and SharePoint servers, respectively.</span></span> <span data-ttu-id="7bb6f-109">Finden Sie in der Produktdokumentation für Exchange 2013 und SharePoint Informationen auf, wie Sie Metadaten-URL für das betreffende Produkt identifizieren können.</span><span class="sxs-lookup"><span data-stu-id="7bb6f-109">See the product documentation for Exchange 2013 and SharePoint for information on how you can identify the respective product's metadata URL.</span></span>
  
<span data-ttu-id="7bb6f-110">In der letzten Zeile des Skripts werden Sie bemerken, dass das Cmdlet „Set-CsOAuthConfiguration“ mit der folgenden Syntax aufgerufen wird:</span><span class="sxs-lookup"><span data-stu-id="7bb6f-110">If you look at the last line of the script you will notice that the Set-CsOAuthConfiguration cmdlet is called using this syntax:</span></span>
  
```
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="7bb6f-p103">Da beim Aufrufen von „Set-CsOAuthConfiguration“ der Parameter „Realm“ nicht verwendet wurde, wird als Bereich automatisch der vollqualifizierte Domänenname (FQDN) Ihrer Organisation festgelegt (z. B. litwareinc.com). Wenn der Bereichsname anders als Ihr Organisationsname lautet, sollten Sie den Bereichsnamen wie folgt mit angeben:</span><span class="sxs-lookup"><span data-stu-id="7bb6f-p103">Because the Realm parameter was not used when calling Set-CsOAuthConfiguration the realm will automatically be set to the fully qualified domain name (FQDN) of your organization (for example, litwareinc.com). If your realm name is different from your organization name then you should include the realm name, like this:</span></span>
  
```
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"
```

<span data-ttu-id="7bb6f-113">Nach dem Ändern dieser Änderungen können Sie anschließend führen Sie das Skript und Konfigurieren von Exchange 2013 und SharePoint als partneranwendungen, durch die Skriptdatei aus innerhalb der Skype für Business Server-Verwaltungsshell ausführen.</span><span class="sxs-lookup"><span data-stu-id="7bb6f-113">After making these changes you can then execute the script, and configure both Exchange 2013 and SharePoint as partner applications, by running the script file from within the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="7bb6f-114">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="7bb6f-114">For example:</span></span>
  
```
C:\Scripts\ServerToServerAuth.ps1
```

<span data-ttu-id="7bb6f-115">Beachten Sie, dass Sie dieses Skript ausführen können, selbst wenn Sie keinen sowohl Exchange 2013 und SharePoint Server installiert:, keine Probleme tritt auf, wenn Sie, sagen, SharePoint Server als partneranwendung konfigurieren, auch wenn Sie keine SharePoint Server installiert.</span><span class="sxs-lookup"><span data-stu-id="7bb6f-115">Note that you can run this script even if you do not have both Exchange 2013 and SharePoint Server installed:, no problems will occur if you, say, configure SharePoint Server as a partner application even though you do not have SharePoint Server installed.</span></span>
  
<span data-ttu-id="7bb6f-116">Bei Ausführung des Skripts würden Sie dann eine Fehlermeldung erhalten, die wie folgt aussieht:</span><span class="sxs-lookup"><span data-stu-id="7bb6f-116">When you run this script you might receive an error message similar to the following:</span></span>
  
```
New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."
```

<span data-ttu-id="7bb6f-p105">Diese Fehlermeldung hat meist zwei Bedeutungen: 1.) Eine der im Skript angegebenen URLs ist ungültig (d. h. eine Ihrer Metadaten-URLs ist tatsächlich keine Metadaten-URL) oder 2.) eine der Metadaten-URLs konnte nicht kontaktiert werden. In diesem Fall sollten Sie überprüfen, ob die URLs korrekt geschrieben sind und auf sie zugegriffen werden kann, und das Skript danach erneut ausführen.</span><span class="sxs-lookup"><span data-stu-id="7bb6f-p105">This error message typically means one of two things: 1) that one of the URLs specified in the script is not valid (that is, one of your metadata URLs is not an actual metadata URL); or, 2) one of the metadata URLs could not be contacted. If this happens, verify that the URLs are correct and are accessible, and the re-run the script.</span></span>
  
<span data-ttu-id="7bb6f-119">Nach dem Erstellen der partneranwendung für Skype für Business Server müssen Sie Skype für Business Server werden als partneranwendung für Exchange 2013 konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="7bb6f-119">After creating the partner application for Skype for Business Server you must then configure Skype for Business Server to be a partner application for Exchange 2013.</span></span> <span data-ttu-id="7bb6f-120">Sie können durch Ausführen des Skripts konfigurieren EnterprisePartnerApplication.ps1 partneranwendungen für Exchange 2013 konfigurieren. müssen Sie nur die Metadaten-URL für Skype für Business Server angeben und anzugeben, dass Skype für Business Server die neue partneranwendung ist.</span><span class="sxs-lookup"><span data-stu-id="7bb6f-120">You can configure partner applications for Exchange 2013 by running the script Configure-EnterprisePartnerApplication.ps1; all you need to do is specify the metadata URL for Skype for Business Server and indicate that Skype for Business Server is the new partner application.</span></span> 
  
<span data-ttu-id="7bb6f-121">Zum Konfigurieren von Skype für Business Server als partneranwendung für Exchange, öffnen Sie die Exchange-Verwaltungsshell, und führen Sie einen Befehl wie den folgenden</span><span class="sxs-lookup"><span data-stu-id="7bb6f-121">To configure Skype for Business Server as a partner application for Exchange, open the Exchange Management Shell and run a command similar to this</span></span>
  
```
"c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://SkypePro.contoso.com/metadata/json/1" -ApplicationType "Lync"
```


