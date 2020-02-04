---
title: 'Lync Server 2013: Importieren von Geräte Update Regeln'
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
ms.openlocfilehash: 872f729584f14011d18920a676c32205d38c7f62
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763849"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="import-device-update-rules-in-lync-server-2013"></a><span data-ttu-id="eee93-102">Importieren von geräteaktualisierungsregeln in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eee93-102">Import Device Update rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eee93-103">_**Letztes Änderungsdatum des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="eee93-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="eee93-104">Geräteaktualisierungsregeln können nur mithilfe von Windows PowerShell und dem Cmdlet " **Import-CsDeviceUpdate** " importiert werden.</span><span class="sxs-lookup"><span data-stu-id="eee93-104">Device update rules can be imported only by using Windows PowerShell and the **Import-CsDeviceUpdate** cmdlet.</span></span> <span data-ttu-id="eee93-105">Dieses Cmdlet kann entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="eee93-105">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="eee93-106">Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="eee93-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


<div>

## <a name="to-import-device-update-rules-to-a-single-web-server"></a><span data-ttu-id="eee93-107">So importieren Sie geräteaktualisierungsregeln auf einen einzelnen Webserver</span><span class="sxs-lookup"><span data-stu-id="eee93-107">To import device update rules to a single web server</span></span>

  - <span data-ttu-id="eee93-108">Mit dem folgenden Befehl werden geräteaktualisierungsregeln auf den Webserver ATL-CS-001.litwareinc.com importiert:</span><span class="sxs-lookup"><span data-stu-id="eee93-108">The following command imports device update rules to the Web server atl-cs-001.litwareinc.com:</span></span>
    
        Import-CsDeviceUpdate -Identity "service:WebServer:atl-cs-001.litwareinc.com" -FileName C:\Updates\UCUpdates.cab

</div>

<div>

## <a name="to-import-device-update-rules-to-all-your-web-servers"></a><span data-ttu-id="eee93-109">So importieren Sie geräteaktualisierungsregeln auf alle Ihre Webserver</span><span class="sxs-lookup"><span data-stu-id="eee93-109">To import device update rules to all your web servers</span></span>

  - <span data-ttu-id="eee93-110">In diesem Beispiel werden geräteaktualisierungsregeln in alle Webserver importiert, die in Ihrer Organisation bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="eee93-110">In this example, device update rules are imported to all the Web servers deployed in your organization.</span></span> <span data-ttu-id="eee93-111">Damit dieser Befehl funktioniert, müssen die Ordner \\ \\-\\ATL-FS-001.litwareinc.com-Updates freigegeben und allen Webservern zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="eee93-111">For this command to work, the folder \\\\atl-fs-001.litwareinc.com\\Updates must be shared and available to all the Web servers.</span></span>
    
        Get-CsService -WebServer | ForEach-Object {Import-CsDeviceUpdate -Identity $_.Identity -FileName \\atl-fs-001.litwareinc.com\Updates\UCUpdates.cab}

</div>

<span data-ttu-id="eee93-112">Ausführliche Informationen finden Sie im Hilfethema zum Cmdlet " [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) ".</span><span class="sxs-lookup"><span data-stu-id="eee93-112">For details, see the Help topic for the [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="eee93-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eee93-113">See Also</span></span>


[<span data-ttu-id="eee93-114">Anzeigen von Informationen zu Geräte Update Regeln in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eee93-114">View information about Device Update rules in Lync Server 2013</span></span>](lync-server-2013-view-information-about-device-update-rules.md)  
[<span data-ttu-id="eee93-115">Genehmigen einer geräteaktualisierungsregel in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eee93-115">Approve a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

