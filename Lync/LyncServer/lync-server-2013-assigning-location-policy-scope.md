---
title: 'Lync Server 2013: Zuweisen eines Standortrichtlinien Bereichs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assigning location policy scope
ms:assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205360(v=OCS.15)
ms:contentKeyID: 48185734
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 090c0d4e7ce65f633458860f0c488e4257d15b5a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499422"
---
# <a name="assigning-location-policy-scope-in-lync-server-2013"></a><span data-ttu-id="44d2e-102">Zuweisen eines Standortrichtlinien Bereichs in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44d2e-102">Assigning location policy scope in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44d2e-103">_**Letztes Änderungsstand des Themas:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="44d2e-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="44d2e-104">Wie bei anderen lync Server-Richtlinien können ortungsrichtlinien auf mehreren Bereichsebenen zugewiesen werden: Global, Standort und Benutzer.</span><span class="sxs-lookup"><span data-stu-id="44d2e-104">As with other Lync Server policies, location policies can be assigned at multiple scope levels: global, site, and user.</span></span> <span data-ttu-id="44d2e-105">Der Bereich der ortungsrichtlinien auf Benutzerebene verhält sich jedoch etwas anders als bei anderen lync Server-Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="44d2e-105">However, the scope of user-level location policies behaves a bit differently than with other Lync Server policies.</span></span> <span data-ttu-id="44d2e-106">Es können nicht nur benutzerspezifische ortungsrichtlinien auf Endpunkt Objekte angewendet werden (wie Benutzer und Kontaktobjekte für gemeinsame Bereiche), sondern Sie können auch auf lync Server Netzwerkstandorten angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="44d2e-106">Not only can per-user location policies be applied to endpoint objects (such as Users and Common Area Phone contact objects), they can also be applied to Lync Server network sites.</span></span> <span data-ttu-id="44d2e-107">Netzwerkstandorte sind Gruppierungen von Client-Subnetzen, die einem geografischen Standort zugeordnet sind (jedoch muss es sich nicht zwingend um alle Subnetze an einem zentralen Standort oder in einer Zweigniederlassung handeln).</span><span class="sxs-lookup"><span data-stu-id="44d2e-107">Network sites are groupings of client subnets associated with a geographical location (but may not necessarily be all subnets in an entire central site or branch site).</span></span> <span data-ttu-id="44d2e-108">Alle Clients, die mit den Subnetzen an einem Netzwerkstandort verbunden sind, übernehmen automatisch die Standortrichtlinie, die dem jeweiligen Netzwerkstandort zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="44d2e-108">Any clients connected to the subnets in a network site automatically pick up the location policy assigned to that network site.</span></span> <span data-ttu-id="44d2e-109">Wenn eine Standortrichtlinie auf Benutzerebene sowohl einem Benutzer als auch einem Netzwerkstandort zugewiesen ist, hat die auf dem Netzwerkstandort basierende Standortrichtlinie Vorrang vor jeglichen benutzerspezifischen Richtlinieneinstellungen.</span><span class="sxs-lookup"><span data-stu-id="44d2e-109">In cases where a user-level location policy is assigned both to a user and to a network site, the network site-based location policy overrides any per-user policy setting.</span></span>

<span data-ttu-id="44d2e-110">Jedem Netzwerkstandort ist eine Standortrichtlinie zugewiesen, und jeder Richtlinie sind andere Werte für PSTN-Verwendungen, Benachrichtigungs-URIs und Konferenz-URIs zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="44d2e-110">Each network site has a location policy assigned to it, and each policy will have different PSTN Usages, Notification URIs, and Conference URIs values assigned to it.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="44d2e-111">Der Grund für dieses spezielle Richtlinienverhalten ist, dass, wenn ein Benutzer, der einem Pool an einem Bürostandort angehört, einen anderen Standort besucht und einen Notruf tätigen muss, die Einstellungen für die E9-1-1-Anrufumleitung für diesen Netzwerkstandort unabhängig davon gelten, welchem Pool oder welchem Standort der Benutzer zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="44d2e-111">The reason for this special policy scoping behavior is so that when a user homed on a pool at one office site visits another site and has to make an emergency call, the E9-1-1 call routing settings appropriate to that network site will apply no matter what pool or site the user is assigned to.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

