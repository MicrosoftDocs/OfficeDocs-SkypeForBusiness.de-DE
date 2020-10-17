---
title: Benutzermodell für lync Server 2013 Konferenz
description: Lync Server 2013 Konferenzbenutzer Modell.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: The conferencing user model
ms:assetid: ba4bbba9-f2e3-4cab-8eba-b51f12133cab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205199(v=OCS.15)
ms:contentKeyID: 48185229
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 699f41303b82f4d8fd2864cbf1b29a1c601b826e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555981"
---
# <a name="the-conferencing-user-model-in-lync-server-2013"></a><span data-ttu-id="cf455-103">Das Benutzermodell für Konferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cf455-103">The conferencing user model in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf455-104">_**Letztes Änderungsstand des Themas:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="cf455-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="cf455-105">Ein wichtiger Bestandteil des Benutzermodells für lync Server Konferenzen ist die Besprechungsgröße.</span><span class="sxs-lookup"><span data-stu-id="cf455-105">A critical part of the Lync Server conferencing user model is meeting size.</span></span> <span data-ttu-id="cf455-106">Nach dem Erfassen der Daten von den verschiedenen Datenpunkten (wie im vorigen Abschnitt beschrieben) wurde Folgendes ermittelt:</span><span class="sxs-lookup"><span data-stu-id="cf455-106">After collecting data from the multiple data points (as described in the previous section), we determined the following:</span></span>

  - <span data-ttu-id="cf455-107">Im Durchschnitt weisen die meisten Besprechungen eine Teilnehmerzahl von vier bis sechs Personen auf</span><span class="sxs-lookup"><span data-stu-id="cf455-107">Most meetings are actually small collaborative meetings with an average of four to six participants</span></span>

  - <span data-ttu-id="cf455-108">Circa 80 Prozent der Besprechungen haben weniger als 20 Teilnehmer.</span><span class="sxs-lookup"><span data-stu-id="cf455-108">Approximately 80 percent of meetings have fewer than 20 participants.</span></span>

  - <span data-ttu-id="cf455-109">99,98 Prozent der Besprechungen haben weniger als 100 Teilnehmer.</span><span class="sxs-lookup"><span data-stu-id="cf455-109">99.98 percent of meetings have fewer than 100 participants.</span></span>

<span data-ttu-id="cf455-110">Neben dem Besprechungsumfang berücksichtigt das Konferenzbenutzermodell auch eine Reihe von Faktoren, wie zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="cf455-110">In addition to meeting size, the conferencing user model also takes into account a variety of factors, such as:</span></span>

  - <span data-ttu-id="cf455-111">**Gleichzeitige Besprechungen**     Wie viele Benutzer werden in Besprechungen gleichzeitig erwartet?</span><span class="sxs-lookup"><span data-stu-id="cf455-111">**Concurrent meetings**   How many users are expected to be in meetings at the same time?</span></span>

  - <span data-ttu-id="cf455-112">**Medienmischung**     Welche Arten von Medien sind verfügbar und sollen von Benutzern in Besprechungen verwendet werden?</span><span class="sxs-lookup"><span data-stu-id="cf455-112">**Media mix**   What types of media are available and expected to be used by users in meetings?</span></span>

  - <span data-ttu-id="cf455-113">**Benutzertypen**     Sind Benutzer interne Benutzer, Remotebenutzer, Verbundbenutzer oder anonyme Benutzer?</span><span class="sxs-lookup"><span data-stu-id="cf455-113">**User types**   Are users internal users, remote users, federated users, or anonymous users?</span></span>

  - <span data-ttu-id="cf455-114">**Besprechungs Rampen-Zeit**     Wie lange dauert es, bis alle Benutzer einer Besprechung an einer Besprechung teilnehmen?</span><span class="sxs-lookup"><span data-stu-id="cf455-114">**Meeting ramp up time**   How long does it take for all users of a meeting to join a meeting?</span></span>

<span data-ttu-id="cf455-115">Ausführliche Informationen zum Benutzermodell finden Sie unter [Benutzermodelle in lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="cf455-115">For details about the user model, see [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

<span data-ttu-id="cf455-116">Zur Ermittlung der Anzahl von Besprechungen und Benutzern, die für den Test verwendet wurden, wurde wie folgt vorgegangen:</span><span class="sxs-lookup"><span data-stu-id="cf455-116">To determine the number of meetings and users to use for testing, we did the following:</span></span>

  - <span data-ttu-id="cf455-117">Die Gesamtzahl der Benutzer in einer Organisation (zum Beispiel 80.000 Benutzer) wurde mit der Gleichzeitigkeitsrate von Besprechungen (zum Beispiel 5 % aller Benutzer) multipliziert, um die Gesamtzahl der Benutzer zu ermitteln, die erwartungsgemäß zur gleichen Zeit an Besprechungen teilnehmen (in diesem Beispiel 4.000 Benutzer).</span><span class="sxs-lookup"><span data-stu-id="cf455-117">Took the total number of users in an organization (for example, 80,000 users) and multiplied it by the meeting concurrency rate (for example, 5% of all users) to determine the total number of users expected to be in meetings at the same time (in this example, 4000 users).</span></span>

  - <span data-ttu-id="cf455-118">Die Gesamtzahl der Benutzer wurde durch die Anzahl der lync Server 2013, Front-End-Server in der Bereitstellung (beispielsweise 8 Server) dividiert, um die geschätzte Anzahl der Besprechungsteilnehmer pro Front-End-Server zu ermitteln (in diesem Beispiel 500 Benutzer pro Front-End-Server).</span><span class="sxs-lookup"><span data-stu-id="cf455-118">Divided the total number of users by the number of Lync Server 2013, Front End Servers in the deployment (for example, 8 servers) to determine the estimated number of meeting participants per Front End Server (in this example, 500 users per Front End Server).</span></span>

  - <span data-ttu-id="cf455-119">Die Anzahl der Benutzer pro Front-End-Server wurde durch die durchschnittliche Besprechungsgröße (beispielsweise 4 Benutzer) dividiert, um die geschätzte durchschnittliche Anzahl von Besprechungen pro Front-End-Server zu ermitteln (in diesem Beispiel 125 Besprechungen pro Front-End-Server).</span><span class="sxs-lookup"><span data-stu-id="cf455-119">Divided the number of users per Front End Server by the average meeting size (for example, 4 users) to determine the estimated average number of meetings per Front End Server (in this example, 125 meetings per Front End Server).</span></span>

  - <span data-ttu-id="cf455-120">Um die pro-Medien-Last auf jeder Front-End-Server zu erhalten, schätzten wir die Medienmischung.</span><span class="sxs-lookup"><span data-stu-id="cf455-120">To get the per media load on each Front End Server, we estimated the media mix.</span></span> <span data-ttu-id="cf455-121">Wenn beispielsweise 75% der Besprechungen mehr als nur Audiounterstützung erfordern und 50% dieser Besprechungen Anwendungsfreigabe erfordern, verbinden sich durchschnittlich 47 Besprechungen und 188 Benutzer gleichzeitig mit jedem Front-End-Server für die Anwendungsfreigabe.</span><span class="sxs-lookup"><span data-stu-id="cf455-121">For example, assuming that 75% of the meetings require more than just audio support and 50% of those meetings require application sharing, an average of 47 meetings and 188 users connect concurrently to each Front End Server for application sharing.</span></span>

  - <span data-ttu-id="cf455-122">Es wurden verschiedene Besprechungsgrößen getestet (auf Basis des Modells mit bis zu 250 Benutzern in einem freigegebenen Pool), um die Serverskalierbarkeit zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="cf455-122">Tested a variety of meeting sizes (based our user model of up to 250 users in a shared pool) to ensure server scalability.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

