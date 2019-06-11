---
title: 'Lync Server 2013: netzwerkregionen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Network regions
ms:assetid: 1818e9d2-bbb7-420a-93ea-4c3da3a55ad3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687979(v=OCS.15)
ms:contentKeyID: 49733567
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f9a2fd8ce5de11f592d010615ddee9c253913c4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826430"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="network-regions-in-lync-server-2013"></a><span data-ttu-id="1596d-102">Netzwerkregionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1596d-102">Network regions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1596d-103">_**Letztes Änderungsdatum des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="1596d-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="1596d-104">*Netzwerkregionen* sind die Netzwerkhubs oder Backbones, die in der Konfiguration der Anruf Zulassungs Steuerung, E9-1-1 und medienumgehung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1596d-104">*Network regions* are the network hubs or backbones used in the configuration of call admission control, E9-1-1, and media bypass.</span></span> <span data-ttu-id="1596d-105">Gehen Sie wie folgt vor, um netzwerkregionen anzuzeigen, zu erstellen oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="1596d-105">Use the following procedures to view, create, or modify network regions.</span></span> <span data-ttu-id="1596d-106">Wenn Sie beispielsweise bereits netzwerkregionen für ein Sprachfeature erstellt haben, müssen Sie keine neuen netzwerkregionen erstellen. für andere erweiterte Enterprise-VoIP-Features werden dieselben netzwerkregionen verwendet.</span><span class="sxs-lookup"><span data-stu-id="1596d-106">For example, if you have already created network regions for one Voice feature, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span> <span data-ttu-id="1596d-107">Sie müssen jedoch möglicherweise eine vorhandene Definition einer Netzwerkregion ändern, um funktionsspezifische Einstellungen anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="1596d-107">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="1596d-108">Wenn Sie z. B. Netzwerkregionen für E9-1-1 erstellt haben (denen kein zentraler Standort zugeordnet werden muss) und Sie zu einem späteren Zeitpunkt die Anrufsteuerung bereitstellen, müssen Sie die Definitionen der Netzwerkregionen ändern und einen zentralen Standort angeben.</span><span class="sxs-lookup"><span data-stu-id="1596d-108">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span> <span data-ttu-id="1596d-109">Ausführliche Informationen finden Sie unter [Konfigurieren von netzwerkregionen für CAC in lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md).</span><span class="sxs-lookup"><span data-stu-id="1596d-109">For details, see [Configure network regions for CAC in Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1596d-110">Alle funktionsspezifischen Anforderungen für Netzwerkbereichs Definitionen sind in den Bereitstellungsthemen für das Feature dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="1596d-110">Any feature-specific requirements for network region definitions are documented in the Deployment topics for the feature.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="1596d-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="1596d-111">In This Section</span></span>

  - [<span data-ttu-id="1596d-112">Anzeigen von Netzwerk Regionsinformationen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1596d-112">Viewing network region information in Lync Server 2013</span></span>](lync-server-2013-viewing-network-region-information.md)

  - [<span data-ttu-id="1596d-113">Erstellen oder Ändern von netzwerkregionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1596d-113">Creating or modifying network regions in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-regions.md)

  - [<span data-ttu-id="1596d-114">Löschen vorhandener netzwerkregionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1596d-114">Deleting existing network regions in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-regions.md)

</div>

<div>

## <a name="reference"></a><span data-ttu-id="1596d-115">Referenz</span><span class="sxs-lookup"><span data-stu-id="1596d-115">Reference</span></span>

[<span data-ttu-id="1596d-116">Bereitstellen von erweiterten Enterprise-VoIP-Features in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1596d-116">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

