---
title: 'Lync Server 2013: Zurückgeben von A/V-Edgeserver Konfigurationsinformationen'
description: 'Lync Server 2013: gibt A/V-Edgeserver Konfigurationsinformationen zurück.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Return A/V Edge Server configuration information
ms:assetid: b041f5a4-2387-4075-846c-ec4f99640903
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721850(v=OCS.15)
ms:contentKeyID: 49733783
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f4f72fccfe51b946dc0dc285aee12a07e59c844b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575441"
---
# <a name="return-av-edge-server-configuration-information-in-lync-server-2013"></a><span data-ttu-id="a9a6e-103">Zurückgeben von A/V-Edgeserver Konfigurationsinformationen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9a6e-103">Return A/V Edge Server configuration information in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a9a6e-104">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="a9a6e-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="a9a6e-p101">Der A/V-Edgeserverdienst bietet eine Möglichkeit für Ihre internen Benutzer (in Ihrem Organisationsnetzwerk angemeldete Benutzer), Audio- und Videodateien für externe Benutzer (nicht in Ihrem Organisationsnetzwerk angemeldete Benutzer) freizugeben. Der A/V-Edgeserverdienst wird primär durch die Verwendung von A/V-Edge-Konfigurationseinstellungen verwaltet; Einstellung, die über die Standort- oder die Dienstebene konfiguriert werden kann (d. h., sie kann für einen einzelnen A/V-Edgeserver konfiguriert werden).</span><span class="sxs-lookup"><span data-stu-id="a9a6e-p101">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network). The A/V Edge service is primarily managed by using A/V Edge configuration settings, setting that can be configured at the site scope or at the service scope (that is, can be configured for an individual A/V Edge server).</span></span>

<span data-ttu-id="a9a6e-107">Wenn Sie Informationen zu den in Ihrer Organisation verwendeten A/V-Edge-Konfigurationseinstellungen zurückgeben möchten, müssen Sie Windows PowerShell und das Get-CsAVEdgeConfiguration-Cmdlet verwenden.</span><span class="sxs-lookup"><span data-stu-id="a9a6e-107">To return information about the A/V Edge configuration settings in use in your organization, you must use Windows PowerShell and the Get-CsAVEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="a9a6e-108">Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Get-CsAVEdgeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAVEdgeConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="a9a6e-108">For more information, see the help topic for the [Get-CsAVEdgeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAVEdgeConfiguration) cmdlet.</span></span>

<span data-ttu-id="a9a6e-109">Vom Cmdlet Get-CsAVEdgeConfiguration zurückgegebene Informationen sehen in etwa so aus:</span><span class="sxs-lookup"><span data-stu-id="a9a6e-109">Information returned from the Get-CsAVEdgeConfiguration cmdlet will look similar to this:</span></span>

    Identity              : Global
    MaxTokenLifetime      : 08:00:00
    MaxBandwidthPerUserKb : 10000
    MaxBandwidthPerPortKb : 3000

<div>

## <a name="to-return-information-for-all-your-av-edge-configuration-settings"></a><span data-ttu-id="a9a6e-110">So geben Sie Informationen zu allen A/V-Edge-Konfigurationseinstellungen zurück</span><span class="sxs-lookup"><span data-stu-id="a9a6e-110">To return information for all your A/V Edge configuration settings</span></span>

  - <span data-ttu-id="a9a6e-111">Der folgende Befehl gibt Informationen über alle derzeit in Ihrer Organisation verwendeten A/V-Edge-Konfigurationseinstellungen zurück:</span><span class="sxs-lookup"><span data-stu-id="a9a6e-111">The following command returns information about all the A/V Edge configuration settings currently in use in your organization:</span></span>
    
        Get-CsAVEdgeConfiguration

</div>

<div>

## <a name="to-return-information-for-site-scoped-av-edge-configuration-settings"></a><span data-ttu-id="a9a6e-112">So geben Sie Informationen zu den standortbezogenen A/V-Edge-Konfigurationseinstellungen zurück</span><span class="sxs-lookup"><span data-stu-id="a9a6e-112">To return information for site-scoped A/V Edge configuration settings</span></span>

  - <span data-ttu-id="a9a6e-p103">Geben Sie zum Zurückgeben von Informationen über eine bestimmte Sammlung von A/V-Edge-Konfigurationseinstellungen die Identität der Sammlung an, wenn das Cmdlet Get-CsAVEdgeConfiguration ausgeführt wird. Beispielsweise gibt dieser Befehl nur Informationen für die Einstellungen zurück, die im Standort Redmond angewendet wurden:</span><span class="sxs-lookup"><span data-stu-id="a9a6e-p103">To return information about a specific collection of A/V Edge configuration settings, specify the Identity of that collection when running the Get-CsAVEdgeConfiguration cmdlet. For example, this command returns information only for the settings applied to the Redmond site:</span></span>
    
        Get-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-return-information-for-service-scoped-av-edge-configuration-settings"></a><span data-ttu-id="a9a6e-115">So geben Sie Informationen zu Dienstbereichs bezogenen A/V-Edge-Konfigurationseinstellungen zurück</span><span class="sxs-lookup"><span data-stu-id="a9a6e-115">To return information for service-scoped A/V Edge configuration settings</span></span>

  - <span data-ttu-id="a9a6e-116">Und dieser Befehl gibt nur Informationen für Einstellungen zurück, die auf einem bestimmten A/V-Edgeserver angewendet wurden:</span><span class="sxs-lookup"><span data-stu-id="a9a6e-116">And this command returns information only for settings applied the a specific A/V Edge server:</span></span>
    
        Get-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a9a6e-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a9a6e-117">See Also</span></span>


[<span data-ttu-id="a9a6e-118">Erstellen oder Ändern einer Sammlung von a/V-Edgeserver Konfigurationseinstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9a6e-118">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  
[<span data-ttu-id="a9a6e-119">Löschen einer vorhandenen Auflistung von A/V-Edgeserver Konfigurationseinstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9a6e-119">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[<span data-ttu-id="a9a6e-120">Audio/Video-Edgeserver (A/V) in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9a6e-120">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>](lync-server-2013-audio-video-a-v-edge-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

