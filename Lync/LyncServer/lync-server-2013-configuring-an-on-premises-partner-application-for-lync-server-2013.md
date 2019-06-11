---
title: Konfigurieren einer lokalen Partneranwendung für lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring an on-premises partner application for Lync Server 2013
ms:assetid: 696f2b26-e5d0-42b5-9785-a26c2ce25bb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204975(v=OCS.15)
ms:contentKeyID: 48184412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c396415dd6bd3bda99254f30b0223f1ff672a01f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839292"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-an-on-premises-partner-application-for-microsoft-lync-server-2013"></a><span data-ttu-id="d98ce-102">Konfigurieren einer lokalen Partneranwendung für Microsoft lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d98ce-102">Configuring an on-premises partner application for Microsoft Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d98ce-103">_**Letztes Änderungsdatum des Themas:** 2013-02-04_</span><span class="sxs-lookup"><span data-stu-id="d98ce-103">_**Topic Last Modified:** 2013-02-04_</span></span>

<span data-ttu-id="d98ce-104">Nachdem Sie das OAuthTokenIssuer-Zertifikat zugewiesen haben, müssen Sie Ihre Microsoft lync Server 2013-Partneranwendungen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="d98ce-104">After you have assigned the OAuthTokenIssuer certificate you must then configure your Microsoft Lync Server 2013 partner applications.</span></span> <span data-ttu-id="d98ce-105">(Das Verfahren, das besprochen werden soll, konfiguriert sowohl Microsoft Exchange Server 2013 als auch Microsoft SharePoint, um als Partneranwendungen zu fungieren.) Wenn Sie eine lokale Partneranwendung konfigurieren möchten, müssen Sie zunächst das folgende Windows PowerShell-Skript kopieren und den Code in Notepad (oder einen beliebigen anderen Text-Editor) einfügen:</span><span class="sxs-lookup"><span data-stu-id="d98ce-105">(The procedure about to be discussed configures both Microsoft Exchange Server 2013 and Microsoft SharePoint to act as partner applications.) To configure an on-premises partner application, you must start by copying the following Windows PowerShell script and pasting the code into Notepad (or any other text editor):</span></span>

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
      
                 New-CsPartnerApplication -Identity microsoft.sharepoint -MetadataUrl http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx -ApplicationTrustLevel Full 
               }
            else
               {
                 Set-CsPartnerApplication -Identity microsoft.sharepoint -ApplicationTrustLevel Full 
                }
       }
    
    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000

<span data-ttu-id="d98ce-106">Nachdem Sie den Code kopiert haben, speichern Sie das Skript mit einem. PS1-Dateierweiterung (beispielsweise C:\\Skripts\\ServerToServerAuth. ps1).</span><span class="sxs-lookup"><span data-stu-id="d98ce-106">After copying the code, save the script using a .PS1 file extension (for example, C:\\Scripts\\ServerToServerAuth.ps1).</span></span> <span data-ttu-id="d98ce-107">Beachten Sie, dass Sie vor dem Ausführen dieses Skripts die Metadaten-URLs https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 und die http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx von Ihren Exchange 2013-und SharePoint-Servern verwendeten Metadaten-URLs ersetzen müssen.</span><span class="sxs-lookup"><span data-stu-id="d98ce-107">Note that, before you run this script, you must replace the metadata URLs https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 and http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx with the metadata URLs used by your Exchange 2013 and SharePoint servers, respectively.</span></span> <span data-ttu-id="d98ce-108">Informationen dazu, wie Sie die Metadaten-URL des jeweiligen Produkts identifizieren können, finden Sie in der Produktdokumentation für Exchange 2013 und SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d98ce-108">See the product documentation for Exchange 2013 and SharePoint for information on how you can identify the respective product's metadata URL.</span></span>

<span data-ttu-id="d98ce-109">In der letzten Zeile des Skripts werden Sie bemerken, dass das Cmdlet „Set-CsOAuthConfiguration“ mit der folgenden Syntax aufgerufen wird:</span><span class="sxs-lookup"><span data-stu-id="d98ce-109">If you look at the last line of the script you will notice that the Set-CsOAuthConfiguration cmdlet is called using this syntax:</span></span>

    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000

<span data-ttu-id="d98ce-p103">Da beim Aufrufen von „Set-CsOAuthConfiguration“ der Parameter „Realm“ nicht verwendet wurde, wird als Bereich automatisch der vollqualifizierte Domänenname (FQDN) Ihrer Organisation festgelegt (z. B. litwareinc.com). Wenn der Bereichsname anders als Ihr Organisationsname lautet, sollten Sie den Bereichsnamen wie folgt mit angeben:</span><span class="sxs-lookup"><span data-stu-id="d98ce-p103">Because the Realm parameter was not used when calling Set-CsOAuthConfiguration the realm will automatically be set to the fully qualified domain name (FQDN) of your organization (for example, litwareinc.com). If your realm name is different from your organization name then you should include the realm name, like this:</span></span>

    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"

<span data-ttu-id="d98ce-112">Nachdem Sie diese Änderungen vorgenommen haben, können Sie das Skript ausführen und sowohl Exchange 2013 als auch SharePoint als Partneranwendungen konfigurieren, indem Sie die Skriptdatei in der lync Server 2013-Verwaltungsshell ausführen.</span><span class="sxs-lookup"><span data-stu-id="d98ce-112">After making these changes you can then execute the script, and configure both Exchange 2013 and SharePoint as partner applications, by running the script file from within the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="d98ce-113">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d98ce-113">For example:</span></span>

    C:\Scripts\ServerToServerAuth.ps1

<span data-ttu-id="d98ce-114">Beachten Sie, dass Sie dieses Skript auch dann ausführen können, wenn Exchange 2013 und SharePoint Server nicht installiert sind: Es werden keine Probleme auftreten, wenn Sie beispielsweise SharePoint Server als Partneranwendung konfigurieren, obwohl SharePoint Server nicht installiert ist.</span><span class="sxs-lookup"><span data-stu-id="d98ce-114">Note that you can run this script even if you do not have both Exchange 2013 and SharePoint Server installed:, no problems will occur if you, say, configure SharePoint Server as a partner application even though you do not have SharePoint Server installed.</span></span>

<span data-ttu-id="d98ce-115">Bei Ausführung des Skripts würden Sie dann eine Fehlermeldung erhalten, die wie folgt aussieht:</span><span class="sxs-lookup"><span data-stu-id="d98ce-115">When you run this script you might receive an error message similar to the following:</span></span>

    New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."

<span data-ttu-id="d98ce-p105">Diese Fehlermeldung hat meist zwei Bedeutungen: 1.) Eine der im Skript angegebenen URLs ist ungültig (d. h. eine Ihrer Metadaten-URLs ist tatsächlich keine Metadaten-URL) oder 2.) eine der Metadaten-URLs konnte nicht kontaktiert werden. In diesem Fall sollten Sie überprüfen, ob die URLs korrekt geschrieben sind und auf sie zugegriffen werden kann, und das Skript danach erneut ausführen.</span><span class="sxs-lookup"><span data-stu-id="d98ce-p105">This error message typically means one of two things: 1) that one of the URLs specified in the script is not valid (that is, one of your metadata URLs is not an actual metadata URL); or, 2) one of the metadata URLs could not be contacted. If this happens, verify that the URLs are correct and are accessible, and the re-run the script.</span></span>

<span data-ttu-id="d98ce-118">Nachdem Sie die Partneranwendung für lync Server 2013 erstellt haben, müssen Sie lync Server so konfigurieren, dass es sich um eine Partneranwendung für Exchange 2013 handelt.</span><span class="sxs-lookup"><span data-stu-id="d98ce-118">After creating the partner application for Lync Server 2013 you must then configure Lync Server to be a partner application for Exchange 2013.</span></span> <span data-ttu-id="d98ce-119">Sie können Partneranwendungen für Exchange 2013 konfigurieren, indem Sie das Skript configure-EnterprisePartnerApplication. ps1 ausführen. Sie müssen lediglich die Metadaten-URL für lync Server angeben und darauf hinweisen, dass es sich bei lync Server um die neue Partneranwendung handelt.</span><span class="sxs-lookup"><span data-stu-id="d98ce-119">You can configure partner applications for Exchange 2013 by running the script Configure-EnterprisePartnerApplication.ps1; all you need to do is specify the metadata URL for Lync Server and indicate that Lync Server is the new partner application.</span></span>

<span data-ttu-id="d98ce-120">Wenn Sie lync Server als Partneranwendung für Exchange konfigurieren möchten, öffnen Sie die Exchange-Verwaltungsshell, und führen Sie einen ähnlichen Befehl wie den folgenden aus:</span><span class="sxs-lookup"><span data-stu-id="d98ce-120">To configure Lync Server as a partner application for Exchange, open the Exchange Management Shell and run a command similar to this</span></span>

    "c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://lync.contoso.com/metadata/json/1" -ApplicationType "Lync"

</div>

<span> </span>

</div>

</div>

</div>

