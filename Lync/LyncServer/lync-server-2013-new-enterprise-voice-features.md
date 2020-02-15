---
title: 'Lync Server 2013: neue Enterprise-VoIP-Funktionen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Enterprise Voice features
ms:assetid: db0ad7b9-e469-4c29-89d9-52fed018ef08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398964(v=OCS.15)
ms:contentKeyID: 48185591
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14f3f2429183e76a120fed1ef7437f18bdb8639f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042362"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-enterprise-voice-features-in-lync-server-2013"></a><span data-ttu-id="acb9c-102">Neue Enterprise-VoIP-Funktionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="acb9c-102">New Enterprise Voice features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="acb9c-103">_**Letztes Änderungsstand des Themas:** 2013-05-01_</span><span class="sxs-lookup"><span data-stu-id="acb9c-103">_**Topic Last Modified:** 2013-05-01_</span></span>

<span data-ttu-id="acb9c-104">In lync Server 2013 werden mehrere neue Routing-und Anruf Verwaltungsfeatures eingeführt, die Enterprise-VoIP verbessern.</span><span class="sxs-lookup"><span data-stu-id="acb9c-104">Lync Server 2013 introduces several new routing and call management features that enhance Enterprise Voice.</span></span>

<span data-ttu-id="acb9c-105">Lync Server 2013 unterstützt mehrere Trunks zwischen Vermittlungsservern und Gateways.</span><span class="sxs-lookup"><span data-stu-id="acb9c-105">Lync Server 2013 supports multiple trunks between Mediation Servers and gateways.</span></span> <span data-ttu-id="acb9c-106">Ein *trunk* ist eine logische Zuordnung zwischen einer Portnummer und Vermittlungsserver mit einer Portnummer und einem Gateway.</span><span class="sxs-lookup"><span data-stu-id="acb9c-106">A *trunk* is a logical association between a port number and Mediation Server with a port number and gateway.</span></span> <span data-ttu-id="acb9c-107">Das bedeutet, dass ein Vermittlungsserver mehrere Trunks zu unterschiedlichen Gateways haben kann und ein Gateway mehrere Trunks zu unterschiedlichen Vermittlungsservern haben kann.</span><span class="sxs-lookup"><span data-stu-id="acb9c-107">This means that a Mediation Server can have multiple trunks to different gateways, and a gateway can have multiple trunks to different Mediation Servers.</span></span> <span data-ttu-id="acb9c-108">Das intertrunk-Routing ermöglicht lync Server 2013, eine IP-Nebenstellenanlage mit einem PSTN-Gateway (Public Switched Telephone Network) zu verbinden oder mehrere IP-PBX-Systeme miteinander zu verbinden.</span><span class="sxs-lookup"><span data-stu-id="acb9c-108">Intertrunk routing makes it possible for Lync Server 2013 to interconnect an IP-PBX to a public switched telephone network (PSTN) gateway or to interconnect multiple IP-PBX systems.</span></span> <span data-ttu-id="acb9c-109">Lync Server 2013 dient als Klebstoff (also die Verbindung) zwischen verschiedenen Telefonsystemen.</span><span class="sxs-lookup"><span data-stu-id="acb9c-109">Lync Server 2013 serves as the glue (that is, the interconnection) between different telephony systems.</span></span>

<span data-ttu-id="acb9c-110">Microsoft lync Server 2013 Verbesserungen in den Bereichen Anrufweiterleitung, gleichzeitiges Klingeln, Voicemail-Verarbeitung und Anrufer-ID-Präsentation.</span><span class="sxs-lookup"><span data-stu-id="acb9c-110">Microsoft Lync Server 2013 makes improvements in the areas of call forwarding, simultaneous ringing, voice mail handling, and caller ID presentation.</span></span> <span data-ttu-id="acb9c-111">Diese Features bereichern die Enterprise-VoIP-Anruf Erfahrung.</span><span class="sxs-lookup"><span data-stu-id="acb9c-111">These features enrich the Enterprise Voice call experience.</span></span>

<span data-ttu-id="acb9c-112">In lync Server 2013 werden die folgenden neuen Verbesserungen für Enterprise-VoIP eingeführt:</span><span class="sxs-lookup"><span data-stu-id="acb9c-112">Lync Server 2013 introduces the following new enhancements to Enterprise Voice:</span></span>

  - [<span data-ttu-id="acb9c-113">Neue Anruffunktionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="acb9c-113">New call features in Lync Server 2013</span></span>](lync-server-2013-new-call-features.md)

  - [<span data-ttu-id="acb9c-114">Neue Funktion für Anrufer-ID in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="acb9c-114">New caller ID feature in Lync Server 2013</span></span>](lync-server-2013-new-caller-id-feature.md)

  - [<span data-ttu-id="acb9c-115">Neues Voicemail-Feature in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="acb9c-115">New voice mail feature in Lync Server 2013</span></span>](lync-server-2013-new-voice-mail-feature.md)

  - [<span data-ttu-id="acb9c-116">Neue trunk Funktion in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="acb9c-116">New trunk feature in Lync Server 2013</span></span>](lync-server-2013-new-trunk-feature.md)

  - [<span data-ttu-id="acb9c-117">Neues intertrunk-Feature in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="acb9c-117">New intertrunk feature in Lync Server 2013</span></span>](lync-server-2013-new-intertrunk-feature.md)

  - [<span data-ttu-id="acb9c-118">Neue Funktionen für die Anrufverwaltung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="acb9c-118">New call management features in Lync Server 2013</span></span>](lync-server-2013-new-call-management-features.md)

</div>

<span> </span>

</div>

</div>

</div>

