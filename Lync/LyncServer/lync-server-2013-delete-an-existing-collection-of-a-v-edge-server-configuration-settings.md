---
title: Löschen einer vorhandenen Auflistung von A/V-Edgeserver Konfigurationseinstellungen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of A/V Edge Server configuration settings
ms:assetid: 668d3613-e464-4b68-967a-cfff90b9ce4b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688077(v=OCS.15)
ms:contentKeyID: 49733673
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 80a90e58c1dee8aacae052f916c6fdf6e260b7ba
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514692"
---
# <a name="delete-an-existing-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="bb5f3-102">Löschen einer vorhandenen Auflistung von A/V-Edgeserver Konfigurationseinstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bb5f3-102">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb5f3-103">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="bb5f3-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="bb5f3-p101">Der A/V-Edgeserverdienst bietet eine Möglichkeit für Ihre internen Benutzer (in Ihrem Organisationsnetzwerk angemeldete Benutzer), Audio- und Videodateien für externe Benutzer (nicht in Ihrem Organisationsnetzwerk angemeldete Benutzer) freizugeben. Der A/V-Edgeserverdienst wird primär durch die Verwendung von A/V-Edge-Konfigurationseinstellungen verwaltet; Einstellung, die über die Standort- oder die Dienstebene konfiguriert werden kann (d. h., sie kann für einen einzelnen A/V-Edgeserver konfiguriert werden).</span><span class="sxs-lookup"><span data-stu-id="bb5f3-p101">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network). The A/V Edge service is primarily managed by using A/V Edge configuration settings, setting that can be configured at the site scope or at the service scope (that is, can be configured for an individual A/V Edge server).</span></span>

<span data-ttu-id="bb5f3-106">Wenn Sie lync Server installieren, wird eine globale Sammlung von a/V-Edge-Konfigurationseinstellungen für Sie erstellt.</span><span class="sxs-lookup"><span data-stu-id="bb5f3-106">When you install Lync Server, a global collection of A/V Edge configuration settings is created for you.</span></span> <span data-ttu-id="bb5f3-107">Diese globale Auflistung kann nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="bb5f3-107">This global collection cannot be deleted.</span></span> <span data-ttu-id="bb5f3-108">Sie können jedoch die Windows PowerShell und das Remove-CsAVEdgeConfiguration-Cmdlet verwenden, um die globale Auflistung zurückzusetzen. Das bedeutet einfach, dass alle Eigenschaftswerte in der globalen Auflistung auf ihren Standardwert zurückgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="bb5f3-108">However, you can use the Windows PowerShell and the Remove-CsAVEdgeConfiguration cmdlet to "reset" the global collection; that simply means that all the property values in the global collection will be reset to their default value.</span></span> <span data-ttu-id="bb5f3-109">Wenn Sie beispielsweise die MaxTokenLifetime-Eigenschaft auf 16 Stunden festgelegt haben, wird diese Eigenschaft auf den Standardwert von 8 Stunden zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="bb5f3-109">For example, if you have set the MaxTokenLifetime property for 16 hours, that property will be reset to its default value of 8 hours.</span></span>

<span data-ttu-id="bb5f3-p103">Ihre auf Standort- oder Dienstebene erstellten benutzerdefinierten Einstellungsauflistungen können Sie jedoch mit dem Remove-CsAVEdgeConfiguration-Cmdlet löschen. Wenn Sie Standorteinstellungen löschen, werden die an diesem Standort befindlichen A/V-Edgeserver anhand der globalen Einstellungen verwaltet. Wenn Sie auf Dienstebene festgelegte Einstellungen löschen, wird der Server dann gemäß den Einstellungen für seinen Standort oder (wenn diese nicht vorhanden sind) anhand der globalen Einstellungen verwaltet.</span><span class="sxs-lookup"><span data-stu-id="bb5f3-p103">However, custom settings collections that you have created at either the site scope or the service scope can be deleted by using the Remove-CsAVEdgeConfiguration cmdlet. If you delete site settings then A/V Edge servers in that site will be managed by the global settings. If you delete service-scope settings,, that server will then be managed by its site settings, if they exist, or by the global settings if no site settings are available.</span></span>

<span data-ttu-id="bb5f3-113">Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="bb5f3-113">For more information, see the help topic for the [Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15)) cmdlet.</span></span>

<div>

## <a name="to-reset-the-global-collection"></a><span data-ttu-id="bb5f3-114">So setzen Sie die globale Auflistung zurück</span><span class="sxs-lookup"><span data-stu-id="bb5f3-114">To reset the global collection</span></span>

  - <span data-ttu-id="bb5f3-115">Mit dem folgenden Befehl wird die globale Auflistung von A/V-Edge-Konfigurationseinstellungen zurückgesetzt:</span><span class="sxs-lookup"><span data-stu-id="bb5f3-115">The following command resets the global collection of A/V Edge configuration settings:</span></span>
    
        Remove-CsAVEdgeConfiguration -Identity "global"

</div>

<div>

## <a name="to-remove-a-collection-from-the-site-scope"></a><span data-ttu-id="bb5f3-116">So entfernen Sie eine Sammlung aus dem Website Bereich</span><span class="sxs-lookup"><span data-stu-id="bb5f3-116">To remove a collection from the site scope</span></span>

  - <span data-ttu-id="bb5f3-117">Mit diesem Befehl werden die A/V-Edge-Konfigurationseinstellungen entfernt, die für den Standort "Redmond" gelten:</span><span class="sxs-lookup"><span data-stu-id="bb5f3-117">This command removes the A/V Edge configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-a-collection-from-the-service-scope"></a><span data-ttu-id="bb5f3-118">So entfernen Sie eine Auflistung aus dem Dienstbereich</span><span class="sxs-lookup"><span data-stu-id="bb5f3-118">To remove a collection from the service scope</span></span>

  - <span data-ttu-id="bb5f3-119">Mit diesem Befehl werden die Einstellungen entfernt, die für den A/V-Edgeserver "atl-edge-001.litwareinc.com" gelten:</span><span class="sxs-lookup"><span data-stu-id="bb5f3-119">This command removes the settings applied to the A/V Edge server atl-edge-001.litwareinc.com:</span></span>
    
        Remove-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bb5f3-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bb5f3-120">See Also</span></span>


[<span data-ttu-id="bb5f3-121">Zurückgeben von A/V-Edgeserver Konfigurationsinformationen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bb5f3-121">Return A/V Edge Server configuration information in Lync Server 2013</span></span>](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[<span data-ttu-id="bb5f3-122">Erstellen oder Ändern einer Sammlung von a/V-Edgeserver Konfigurationseinstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bb5f3-122">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  


[<span data-ttu-id="bb5f3-123">Audio/Video-Edgeserver (A/V) in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bb5f3-123">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>](lync-server-2013-audio-video-a-v-edge-servers.md)  
<span data-ttu-id="bb5f3-124">[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="bb5f3-124">[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

