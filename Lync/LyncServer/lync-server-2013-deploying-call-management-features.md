---
title: 'Lync Server 2013: Bereitstellen von Funktionen für die Anrufverwaltung'
description: 'Lync Server 2013: Bereitstellen von Funktionen für die Anrufverwaltung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying call management features
ms:assetid: 1667cfe4-76fa-4e10-91bb-b3efbedbf759
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204706(v=OCS.15)
ms:contentKeyID: 48183504
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa89b75dbcae9de1069daf99986076b66e0411cc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570681"
---
# <a name="deploying-call-management-features-in-lync-server-2013"></a><span data-ttu-id="b5458-103">Bereitstellen von anrufverwaltungsfunktionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5458-103">Deploying call management features in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b5458-104">_**Letztes Änderungsstand des Themas:** 2012-12-18_</span><span class="sxs-lookup"><span data-stu-id="b5458-104">_**Topic Last Modified:** 2012-12-18_</span></span>

<span data-ttu-id="b5458-105">Enterprise-VoIP-anrufverwaltungsfunktionen steuern, wie eingehende Anrufe weitergeleitet und beantwortet werden.</span><span class="sxs-lookup"><span data-stu-id="b5458-105">Enterprise Voice call management features control how incoming calls are routed and answered.</span></span> <span data-ttu-id="b5458-106">Lync Server 2013 bietet die folgenden Funktionen für die Anrufverwaltung:</span><span class="sxs-lookup"><span data-stu-id="b5458-106">Lync Server 2013 provides the following call management features:</span></span>

  - <span data-ttu-id="b5458-107">**Parken von anrufen:** Ermöglicht VoIP-Benutzern das vorübergehende Parken eines Anrufs und das anschließende abholen über dasselbe Telefon oder ein anderes Telefon.</span><span class="sxs-lookup"><span data-stu-id="b5458-107">**Call Park:** Enables voice users to temporarily park a call and then pick it up from the same phone or another phone.</span></span>

  - <span data-ttu-id="b5458-108">**Gruppen Abholung:** Ermöglicht Benutzern, Anrufe an einen anderen Benutzer zu beantworten, der einer Pickup-Gruppe zugewiesen ist, indem er die Nummer der Anrufannahme Gruppe wählt.</span><span class="sxs-lookup"><span data-stu-id="b5458-108">**Group Pickup:** Enables users to answer calls made to another user who is assigned to a pickup group by dialing the call pickup group number.</span></span>

  - <span data-ttu-id="b5458-109">**Reaktionsgruppe:** Leitet eingehende Anrufe an Gruppen von Agents mithilfe von Sammelanschlüssen oder interaktiven Sprachantwort-Fragen und-Antworten weiter.</span><span class="sxs-lookup"><span data-stu-id="b5458-109">**Response Group:** Routes incoming calls to groups of agents by using hunt groups or interactive voice response (IVR) questions and answers.</span></span>

  - <span data-ttu-id="b5458-110">**Ansage:** Gibt eine Nachricht für Anrufe an, die an eine nicht zugewiesene Nummer gesendet werden, oder leitet den Anruf an einer anderen Stelle oder beides weiter.</span><span class="sxs-lookup"><span data-stu-id="b5458-110">**Announcement:** Plays a message for calls made to an unassigned number, or routes the call elsewhere, or both.</span></span>

<span data-ttu-id="b5458-111">In diesem Abschnitt wird beschrieben, wie Sie diese anrufverwaltungsfunktionen während einer Enterprise-VoIP-Bereitstellung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b5458-111">This section describes how to configure these call management features during an Enterprise Voice deployment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b5458-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="b5458-112">In This Section</span></span>

  - [<span data-ttu-id="b5458-113">Konfigurieren des Parkens von Anrufen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5458-113">Configuring Call Park in Lync Server 2013</span></span>](lync-server-2013-configuring-call-park.md)

  - [<span data-ttu-id="b5458-114">Konfigurieren der gruppenanrufannahme in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5458-114">Configuring Group Call Pickup in Lync Server 2013</span></span>](lync-server-2013-configuring-group-call-pickup.md)

  - [<span data-ttu-id="b5458-115">Konfigurieren der Reaktionsgruppe in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5458-115">Configuring Response Group in Lync Server 2013</span></span>](lync-server-2013-configuring-response-group.md)

  - [<span data-ttu-id="b5458-116">Konfigurieren von Ankündigungen für nicht zugewiesene Nummern in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5458-116">Configuring announcements for unassigned numbers in Lync Server 2013</span></span>](lync-server-2013-configuring-announcements-for-unassigned-numbers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

