---
title: 'Lync Server 2013: Zurückgeben von A/V-Edgeserver-Konfigurationsinformationen'
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
ms.openlocfilehash: 2ea7d7ed1ef74c092dac60ecfb2f009219564455
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733075"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="return-av-edge-server-configuration-information-in-lync-server-2013"></a><span data-ttu-id="c5b8f-102">Zurückgeben von A/V-Edgeserver-Konfigurationsinformationen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5b8f-102">Return A/V Edge Server configuration information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5b8f-103">_**Letztes Änderungsdatum des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="c5b8f-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="c5b8f-104">Der a/V-Edgedienst bietet internen Benutzern (Benutzern, die bei Ihrem Unternehmensnetzwerk angemeldet sind) die Möglichkeit, Audio und Video für externe Benutzer freizugeben (Benutzer, die nicht bei Ihrem Organisationsnetzwerk angemeldet sind).</span><span class="sxs-lookup"><span data-stu-id="c5b8f-104">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network).</span></span> <span data-ttu-id="c5b8f-105">Der a/v-Edgedienst wird in erster Linie mithilfe von a/v-Edge-Konfigurationseinstellungen verwaltet, die für den Website Bereich oder den Dienstbereich konfiguriert werden können (d. h., Sie können für einen einzelnen a/v-Edgeserver konfiguriert werden).</span><span class="sxs-lookup"><span data-stu-id="c5b8f-105">The A/V Edge service is primarily managed by using A/V Edge configuration settings, setting that can be configured at the site scope or at the service scope (that is, can be configured for an individual A/V Edge server).</span></span>

<span data-ttu-id="c5b8f-106">Wenn Sie Informationen zu den A/V-Edge-Konfigurationseinstellungen zurückgeben möchten, die in Ihrer Organisation verwendet werden, müssen Sie Windows PowerShell und das Cmdlet Get-CsAVEdgeConfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="c5b8f-106">To return information about the A/V Edge configuration settings in use in your organization, you must use Windows PowerShell and the Get-CsAVEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="c5b8f-107">Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Get-CsAVEdgeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAVEdgeConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="c5b8f-107">For more information, see the help topic for the [Get-CsAVEdgeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAVEdgeConfiguration) cmdlet.</span></span>

<span data-ttu-id="c5b8f-108">Informationen, die vom Cmdlet "Get-CsAVEdgeConfiguration" zurückgegeben werden, sehen wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="c5b8f-108">Information returned from the Get-CsAVEdgeConfiguration cmdlet will look similar to this:</span></span>

    Identity              : Global
    MaxTokenLifetime      : 08:00:00
    MaxBandwidthPerUserKb : 10000
    MaxBandwidthPerPortKb : 3000

<div>

## <a name="to-return-information-for-all-your-av-edge-configuration-settings"></a><span data-ttu-id="c5b8f-109">So geben Sie Informationen zu allen ihren A/V-Edge-Konfigurationseinstellungen zurück</span><span class="sxs-lookup"><span data-stu-id="c5b8f-109">To return information for all your A/V Edge configuration settings</span></span>

  - <span data-ttu-id="c5b8f-110">Mit dem folgenden Befehl werden Informationen zu allen A/V-Edge-Konfigurationseinstellungen zurückgegeben, die derzeit in Ihrer Organisation verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="c5b8f-110">The following command returns information about all the A/V Edge configuration settings currently in use in your organization:</span></span>
    
        Get-CsAVEdgeConfiguration

</div>

<div>

## <a name="to-return-information-for-site-scoped-av-edge-configuration-settings"></a><span data-ttu-id="c5b8f-111">So geben Sie Informationen zu Konfigurationseinstellungen für den Website Bereich A/V-Edge zurück</span><span class="sxs-lookup"><span data-stu-id="c5b8f-111">To return information for site-scoped A/V Edge configuration settings</span></span>

  - <span data-ttu-id="c5b8f-112">Wenn Sie Informationen zu einer bestimmten Sammlung von a/V-Edge-Konfigurationseinstellungen zurückgeben möchten, geben Sie die Identität dieser Sammlung an, wenn Sie das Cmdlet "Get-CsAVEdgeConfiguration" ausführen.</span><span class="sxs-lookup"><span data-stu-id="c5b8f-112">To return information about a specific collection of A/V Edge configuration settings, specify the Identity of that collection when running the Get-CsAVEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="c5b8f-113">Dieser Befehl gibt beispielsweise nur Informationen für die Einstellungen zurück, die auf die Redmond-Website angewendet wurden:</span><span class="sxs-lookup"><span data-stu-id="c5b8f-113">For example, this command returns information only for the settings applied to the Redmond site:</span></span>
    
        Get-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-return-information-for-service-scoped-av-edge-configuration-settings"></a><span data-ttu-id="c5b8f-114">So geben Sie Informationen für die Konfigurationseinstellungen des Dienstbereichs A/V-Edge zurück</span><span class="sxs-lookup"><span data-stu-id="c5b8f-114">To return information for service-scoped A/V Edge configuration settings</span></span>

  - <span data-ttu-id="c5b8f-115">Und dieser Befehl gibt nur Informationen für Einstellungen zurück, auf die ein bestimmter a/V-Edgeserver angewendet wurde:</span><span class="sxs-lookup"><span data-stu-id="c5b8f-115">And this command returns information only for settings applied the a specific A/V Edge server:</span></span>
    
        Get-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c5b8f-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c5b8f-116">See Also</span></span>


[<span data-ttu-id="c5b8f-117">Erstellen oder Ändern einer Sammlung von a/V-Edgeserver-Konfigurationseinstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5b8f-117">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  
[<span data-ttu-id="c5b8f-118">Löschen einer vorhandenen Sammlung von A/V-Edgeserver-Konfigurationseinstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5b8f-118">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[<span data-ttu-id="c5b8f-119">Audio/Video-Edgeserver (A/V) in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5b8f-119">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>](lync-server-2013-audio-video-a-v-edge-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

