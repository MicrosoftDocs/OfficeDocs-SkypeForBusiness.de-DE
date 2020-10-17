---
title: 'Lync Server 2013: netzwerkregionen'
description: 'Lync Server 2013: netzwerkregionen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Network regions
ms:assetid: 1818e9d2-bbb7-420a-93ea-4c3da3a55ad3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687979(v=OCS.15)
ms:contentKeyID: 49733567
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3506f3c543c0728f27bd091b9cd63991c4633da7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561481"
---
# <a name="network-regions-in-lync-server-2013"></a><span data-ttu-id="adf6b-103">Netzwerkregionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="adf6b-103">Network regions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="adf6b-104">_**Letztes Änderungsstand des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="adf6b-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="adf6b-105">Bei einer *Netzwerkregion* handelt es sich um den Netzwerkhub oder Netzwerkbackbone, der in der Konfiguration von Anrufsteuerung, E9-1-1 und Medienumgehung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="adf6b-105">*Network regions* are the network hubs or backbones used in the configuration of call admission control, E9-1-1, and media bypass.</span></span> <span data-ttu-id="adf6b-106">Verwenden Sie die folgenden Verfahren, um Netzwerkregionen anzuzeigen, zu erstellen oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="adf6b-106">Use the following procedures to view, create, or modify network regions.</span></span> <span data-ttu-id="adf6b-107">Wenn Sie beispielsweise bereits Netzwerkregionen für eine VoIP-Funktion erstellt haben, müssen Sie keine neuen Netzwerkregionen erstellen, da dieselben Netzwerkregionen für weitere Enterprise VoIP-Funktionen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="adf6b-107">For example, if you have already created network regions for one Voice feature, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span> <span data-ttu-id="adf6b-108">Sie müssen jedoch möglicherweise eine vorhandene Definition einer Netzwerkregion ändern, um funktionsspezifische Einstellungen anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="adf6b-108">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="adf6b-109">Wenn Sie z. B. Netzwerkregionen für E9-1-1 erstellt haben (denen kein zentraler Standort zugeordnet werden muss) und Sie zu einem späteren Zeitpunkt die Anrufsteuerung bereitstellen, müssen Sie die Definitionen der Netzwerkregionen ändern und einen zentralen Standort angeben.</span><span class="sxs-lookup"><span data-stu-id="adf6b-109">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span> <span data-ttu-id="adf6b-110">Ausführliche Informationen finden Sie unter [configure Network Regions for CAC in lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md).</span><span class="sxs-lookup"><span data-stu-id="adf6b-110">For details, see [Configure network regions for CAC in Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="adf6b-111">Funktionsspezifische Anforderungen für die Netzwerkregionendefinitionen sind in den Bereitstellungsthemen der jeweiligen Funktion dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="adf6b-111">Any feature-specific requirements for network region definitions are documented in the Deployment topics for the feature.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="adf6b-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="adf6b-112">In This Section</span></span>

  - [<span data-ttu-id="adf6b-113">Anzeigen von Informationen zur netzwerkregion in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="adf6b-113">Viewing network region information in Lync Server 2013</span></span>](lync-server-2013-viewing-network-region-information.md)

  - [<span data-ttu-id="adf6b-114">Erstellen oder Ändern von netzwerkregionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="adf6b-114">Creating or modifying network regions in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-regions.md)

  - [<span data-ttu-id="adf6b-115">Löschen vorhandener netzwerkregionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="adf6b-115">Deleting existing network regions in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-regions.md)

</div>

<div>

## <a name="reference"></a><span data-ttu-id="adf6b-116">Referenz</span><span class="sxs-lookup"><span data-stu-id="adf6b-116">Reference</span></span>

[<span data-ttu-id="adf6b-117">Bereitstellen von erweiterten Enterprise-VoIP-Funktionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="adf6b-117">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

