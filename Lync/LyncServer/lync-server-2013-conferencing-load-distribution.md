---
title: Lync Server 2013 der Verteilung von Konferenz Lasten
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferencing load distribution
ms:assetid: 5901a076-1b6f-4720-8837-95fc7f3c37f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204922(v=OCS.15)
ms:contentKeyID: 48184233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 38f7b2d759ec9370bbf7eeeb2844edd3511ba0f1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499202"
---
# <a name="conferencing-load-distribution-in-lync-server-2013"></a><span data-ttu-id="25166-102">Verteilung von Konferenz Lasten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25166-102">Conferencing load distribution in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25166-103">_**Letztes Änderungsstand des Themas:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="25166-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="25166-104">Im Gegensatz zu anderen dedizierten Konferenzlösungen ist lync Server Architektur ein freigegebenes Hardwaremodell.</span><span class="sxs-lookup"><span data-stu-id="25166-104">Unlike some other dedicated conferencing solutions, Lync Server architecture is a shared-hardware model.</span></span> <span data-ttu-id="25166-105">Dies bedeutet, dass die gleiche Hardware von vielen Softwarekomponenten gemeinsam genutzt wird, von denen jede andere Echtzeitkommunikation unterstützt.</span><span class="sxs-lookup"><span data-stu-id="25166-105">This means that the same hardware is shared by many software components, each of which supports different real-time communications.</span></span> <span data-ttu-id="25166-106">Jeder Typ von Echtzeitkommunikation stellt bestimmte Lasten auf den Servern.</span><span class="sxs-lookup"><span data-stu-id="25166-106">Each type of real-time communications places specific loads on the servers.</span></span> <span data-ttu-id="25166-107">Beispielsweise können die Front-End-Server die SIP-Routingkomponenten (Session Initiation Protocol), Webanwendungen (wie Adressbuchsuche), Webkonferenzdienst, A/V-Konferenzdienst, Enterprise-VoIP-Anwendungen (beispielsweise Konferenzzentrale und Reaktionsgruppenanwendung) und Vermittlungsserver ausführen.</span><span class="sxs-lookup"><span data-stu-id="25166-107">For example, the Front End Server can run the Session Initiation Protocol (SIP) routing components, web applications (such as Address Book search), Web Conferencing service, A/V Conferencing service, Enterprise Voice applications (for example, Conferencing Attendant application and Response Group application), and Mediation Server.</span></span> <span data-ttu-id="25166-108">Eine Gruppe von Datenbanken im Front-End-Server bieten auch Speicherung und Verarbeitung für Benutzer-, Kontakt-, Anwesenheits-, Konferenz-und VoIP-Routingdaten.</span><span class="sxs-lookup"><span data-stu-id="25166-108">A set of databases on the Front End Server also provide storage and processing for user, contact, presence, conferencing, and voice routing data.</span></span> <span data-ttu-id="25166-109">Mit dieser Hardware Teilung konkurrieren Komponenten, Dienste und Prozesse um CPU-und Arbeitsspeicherressourcen, sodass nicht-Konferenz Arbeitslasten direkte Auswirkungen auf die Server Skalierung haben.</span><span class="sxs-lookup"><span data-stu-id="25166-109">With this hardware sharing, components, services, and processes compete for CPU and memory resources, so non-conferencing workloads have a direct impact on server scaling.</span></span>

<span data-ttu-id="25166-110">Im Vergleich zu anderen Konferenzlösungen mit Port basierter Hardware ist lync Server Konferenz Architektur kein Reservierungs Modell.</span><span class="sxs-lookup"><span data-stu-id="25166-110">Compared to other hardware port-based conferencing solutions, Lync Server conferencing architecture is a no-reservation model.</span></span> <span data-ttu-id="25166-111">Wenn ein Benutzer eine Besprechung plant, erstellt lync Server einen Datensatz in der Konferenzdatenbank, in dem Konferenzdaten gespeichert werden, reserviert jedoch keine Hardwareressourcen für die geplante Besprechung im voraus.</span><span class="sxs-lookup"><span data-stu-id="25166-111">When a user schedules a meeting, Lync Server creates a record in the conferencing database, which stores conferencing data, but does not reserve any hardware resources for the scheduled meeting ahead of time.</span></span> <span data-ttu-id="25166-112">Stattdessen verfügt lync Server über integrierte Lastenausgleichs Logik zum dynamischen Zuordnen von Konferenzressourcen auf Front-End-Servern auf eine Weise, die Lasten gleichmäßig auf alle Front-End-Server im Pool verteilt.</span><span class="sxs-lookup"><span data-stu-id="25166-112">Instead, Lync Server has built-in load balancing logic to dynamically allocate conferencing resources on Front End Servers in a way that distributes loads equally across all Front End Servers in the pool.</span></span> <span data-ttu-id="25166-113">Dadurch werden Hardwareressourcen effektiv bereitgestellt und verwendet, es stellt jedoch eine Herausforderung dar, sehr große Besprechungen (insbesondere ohne entsprechende Planung) zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="25166-113">This effectively provisions and utilizes hardware resources, but makes it challenging to support very large meetings (especially without appropriate planning).</span></span> <span data-ttu-id="25166-114">Wenn beispielsweise ein lync Server 2013-Pool knapp an seiner Spitzenkapazität liegt, kann jeder Front-End-Server ungefähr 125 Besprechungen mit durchschnittlicher Größe hosten.</span><span class="sxs-lookup"><span data-stu-id="25166-114">For example, when a Lync Server 2013 pool is running close to its top capacity, each Front End Server might host approximately 125 average-size meetings.</span></span> <span data-ttu-id="25166-115">Das Hinzufügen einer weiteren kleinen Besprechung wäre kein Problem, aber das Hinzufügen einer Besprechung für 1000 Benutzer würde ein Problem sein, da die Front-End-Server eine solche große Besprechung möglicherweise nicht gleichzeitig mit den anderen 125-Besprechungen unterstützen können.</span><span class="sxs-lookup"><span data-stu-id="25166-115">Adding another small meeting would not be a problem, but adding a meeting for 1000 users would be a problem because the Front End Servers would probably not be able to support such a large meeting at the same time as the other 125 meetings.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

