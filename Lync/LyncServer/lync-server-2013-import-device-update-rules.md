---
title: 'Lync Server 2013: Importieren von geräteaktualisierungsregeln'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Import Device Update rules
ms:assetid: 919e9c87-912b-4bc9-92e7-5998fc2e0bf0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994056(v=OCS.15)
ms:contentKeyID: 51803967
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5436be837af75045d75b8feee31886aaaf324f0b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196728"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="import-device-update-rules-in-lync-server-2013"></a><span data-ttu-id="8b2c0-102">Importieren von geräteaktualisierungsregeln in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b2c0-102">Import Device Update rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b2c0-103">_**Letztes Änderungsstand des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="8b2c0-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="8b2c0-104">Geräteaktualisierungsregeln können nur mit Windows PowerShell und dem Cmdlet **Import-CsDeviceUpdate** importiert werden.</span><span class="sxs-lookup"><span data-stu-id="8b2c0-104">Device update rules can be imported only by using Windows PowerShell and the **Import-CsDeviceUpdate** cmdlet.</span></span> <span data-ttu-id="8b2c0-105">Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="8b2c0-105">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8b2c0-106">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>mithilfe von Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="8b2c0-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


<div>

## <a name="to-import-device-update-rules-to-a-single-web-server"></a><span data-ttu-id="8b2c0-107">So importieren Sie geräteaktualisierungsregeln auf einen einzelnen Webserver</span><span class="sxs-lookup"><span data-stu-id="8b2c0-107">To import device update rules to a single web server</span></span>

  - <span data-ttu-id="8b2c0-108">Der folgende Befehl importiert geräteaktualisierungsregeln auf den Webserver ATL-CS-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="8b2c0-108">The following command imports device update rules to the Web server atl-cs-001.litwareinc.com:</span></span>
    
        Import-CsDeviceUpdate -Identity "service:WebServer:atl-cs-001.litwareinc.com" -FileName C:\Updates\UCUpdates.cab

</div>

<div>

## <a name="to-import-device-update-rules-to-all-your-web-servers"></a><span data-ttu-id="8b2c0-109">So importieren Sie geräteaktualisierungsregeln auf alle Webserver</span><span class="sxs-lookup"><span data-stu-id="8b2c0-109">To import device update rules to all your web servers</span></span>

  - <span data-ttu-id="8b2c0-110">In diesem Beispiel werden geräteaktualisierungsregeln auf alle in Ihrer Organisation bereitgestellten Webserver importiert.</span><span class="sxs-lookup"><span data-stu-id="8b2c0-110">In this example, device update rules are imported to all the Web servers deployed in your organization.</span></span> <span data-ttu-id="8b2c0-111">Damit dieser Befehl funktioniert, müssen die Ordner \\ \\ATL-FS-001.litwareinc.com\\-Updates freigegeben und für alle Webserver verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="8b2c0-111">For this command to work, the folder \\\\atl-fs-001.litwareinc.com\\Updates must be shared and available to all the Web servers.</span></span>
    
        Get-CsService -WebServer | ForEach-Object {Import-CsDeviceUpdate -Identity $_.Identity -FileName \\atl-fs-001.litwareinc.com\Updates\UCUpdates.cab}

</div>

<span data-ttu-id="8b2c0-112">Ausführliche Informationen finden Sie im Hilfethema zum [Import-CsDeviceUpdate-](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8b2c0-112">For details, see the Help topic for the [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8b2c0-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8b2c0-113">See Also</span></span>


[<span data-ttu-id="8b2c0-114">Anzeigen von Informationen zu geräteaktualisierungsregeln in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b2c0-114">View information about Device Update rules in Lync Server 2013</span></span>](lync-server-2013-view-information-about-device-update-rules.md)  
[<span data-ttu-id="8b2c0-115">Genehmigen einer geräteaktualisierungsregel in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b2c0-115">Approve a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

