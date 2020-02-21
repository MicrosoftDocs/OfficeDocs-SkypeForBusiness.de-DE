---
title: 'Lync Server 2013: Bereitstellung erweiterter Enterprise-VoIP-Funktionen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying advanced Enterprise Voice features
ms:assetid: 286d9c0b-9442-448f-a6e5-95b3034278fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425753(v=OCS.15)
ms:contentKeyID: 48183675
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f825a39650dc535dbb9d432214226169f4451a0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197338"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-advanced-enterprise-voice-features-in-lync-server-2013"></a><span data-ttu-id="5811c-102">Bereitstellen von erweiterten Enterprise-VoIP-Funktionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5811c-102">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5811c-103">_**Letztes Änderungsstand des Themas:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="5811c-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="5811c-104">Nachdem Sie die grundlegende Enterprise-VoIP-Funktionalität für Ihre Organisation konfiguriert haben, können Sie optional eine oder mehrere erweiterte Enterprise-VoIP-Funktionen bereitstellen. Verwenden Sie hierzu die Verfahren in diesem Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="5811c-104">After you have configured basic Enterprise Voice functionality for your organization, you can optionally deploy one or more advanced Enterprise Voice features by following the procedures in this section.</span></span>

<span data-ttu-id="5811c-105">Ausführliche Informationen zu den erweiterten Enterprise-VoIP-Funktionen finden Sie in den folgenden Abschnitten der Dokumentation zur [Planung von lync Server 2013](lync-server-2013-planning.md) :</span><span class="sxs-lookup"><span data-stu-id="5811c-105">For details about the advanced Enterprise Voice features, see the following sections of the [Planning for Lync Server 2013](lync-server-2013-planning.md) documentation:</span></span>

  - [<span data-ttu-id="5811c-106">Planung der Anrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5811c-106">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)

  - [<span data-ttu-id="5811c-107">Planung von Notrufdiensten (E9-1-1) in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5811c-107">Planning for emergency services (E9-1-1) in Lync Server 2013</span></span>](lync-server-2013-planning-for-emergency-services-e9-1-1.md)

  - [<span data-ttu-id="5811c-108">Planen der medienumgehung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5811c-108">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)

<div>

## <a name="in-this-section"></a><span data-ttu-id="5811c-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="5811c-109">In This Section</span></span>

  - [<span data-ttu-id="5811c-110">Informationen zu netzwerkregionen, Standorten und Subnetzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5811c-110">About network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-about-network-regions-sites-and-subnets.md)

  - [<span data-ttu-id="5811c-111">Erstellen oder Ändern einer netzwerkregion in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5811c-111">Create or modify a network region in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-region.md)

  - [<span data-ttu-id="5811c-112">Erstellen oder Ändern eines Netzwerkstandorts in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5811c-112">Create or modify a network site in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-site.md)

  - [<span data-ttu-id="5811c-113">Zuordnen eines Subnetzes zu einem Netzwerkstandort in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5811c-113">Associate a subnet with a network site in Lync Server 2013</span></span>](lync-server-2013-associate-a-subnet-with-a-network-site.md)

  - [<span data-ttu-id="5811c-114">Konfigurieren der Anrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5811c-114">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)

  - [<span data-ttu-id="5811c-115">Konfigurieren von Enhanced 9-1-1 in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5811c-115">Configure Enhanced 9-1-1 in Lync Server 2013</span></span>](lync-server-2013-configure-enhanced-9-1-1.md)

  - [<span data-ttu-id="5811c-116">Konfigurieren der medienumgehung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5811c-116">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

