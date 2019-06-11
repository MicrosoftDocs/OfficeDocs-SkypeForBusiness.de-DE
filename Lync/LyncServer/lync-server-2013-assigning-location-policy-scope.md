---
title: 'Lync Server 2013: Zuweisen von Standortrichtlinien Bereich'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assigning location policy scope
ms:assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205360(v=OCS.15)
ms:contentKeyID: 48185734
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c44bef383690856d873d64ab6218b0f14219e73
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839870"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assigning-location-policy-scope-in-lync-server-2013"></a><span data-ttu-id="6ebc6-102">Zuweisen von Standortrichtlinien Bereich in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6ebc6-102">Assigning location policy scope in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6ebc6-103">_**Letztes Änderungsdatum des Themas:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="6ebc6-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="6ebc6-104">Wie bei anderen lync-Server Richtlinien können Standortrichtlinien auf mehreren Bereichsebenen zugewiesen werden: Global, Website und Benutzer.</span><span class="sxs-lookup"><span data-stu-id="6ebc6-104">As with other Lync Server policies, location policies can be assigned at multiple scope levels: global, site, and user.</span></span> <span data-ttu-id="6ebc6-105">Der Bereich der Standortrichtlinien auf Benutzerebene verhält sich jedoch etwas anders als bei anderen lync-Server Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="6ebc6-105">However, the scope of user-level location policies behaves a bit differently than with other Lync Server policies.</span></span> <span data-ttu-id="6ebc6-106">Auf Endpunkt Objekte (wie Benutzer und Telefon Kontaktobjekte im öffentlichen Bereich) können nicht nur Orts Richtlinien für einzelne Benutzer angewendet werden, sondern auch auf lync Server-Netzwerk Websites angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="6ebc6-106">Not only can per-user location policies be applied to endpoint objects (such as Users and Common Area Phone contact objects), they can also be applied to Lync Server network sites.</span></span> <span data-ttu-id="6ebc6-107">Netzwerkstandorte sind Gruppierungen von Client-Subnetzen, die einem geografischen Standort zugeordnet sind (jedoch muss es sich nicht zwingend um alle Subnetze an einem zentralen Standort oder in einer Zweigniederlassung handeln).</span><span class="sxs-lookup"><span data-stu-id="6ebc6-107">Network sites are groupings of client subnets associated with a geographical location (but may not necessarily be all subnets in an entire central site or branch site).</span></span> <span data-ttu-id="6ebc6-108">Alle Clients, die mit den Subnetzen an einem Netzwerkstandort verbunden sind, übernehmen automatisch die Standortrichtlinie, die dem jeweiligen Netzwerkstandort zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="6ebc6-108">Any clients connected to the subnets in a network site automatically pick up the location policy assigned to that network site.</span></span> <span data-ttu-id="6ebc6-109">Wenn eine Standortrichtlinie auf Benutzerebene sowohl einem Benutzer als auch einem Netzwerkstandort zugewiesen ist, hat die auf dem Netzwerkstandort basierende Standortrichtlinie Vorrang vor allen benutzerspezifischen Richtlinieneinstellungen.</span><span class="sxs-lookup"><span data-stu-id="6ebc6-109">In cases where a user-level location policy is assigned both to a user and to a network site, the network site-based location policy overrides any per-user policy setting.</span></span>

<span data-ttu-id="6ebc6-110">Jedem Netzwerkstandort ist eine Standortrichtlinie zugewiesen und jeder Richtlinie sind andere Werte für PSTN-Verwendungen, Benachrichtigungs-URIs und Konferenz-URIs zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="6ebc6-110">Each network site has a location policy assigned to it, and each policy will have different PSTN Usages, Notification URIs, and Conference URIs values assigned to it.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6ebc6-111">Dieses spezielle Richtlinienverhalten hat folgenden Grund: Wenn ein Benutzer, der einem Pool an einem Bürostandort angehört, einen anderen Standort besucht und einen Notruf tätigen muss, gelten die Einstellungen für die E9-1-1-Anrufumleitung für diesen Netzwerkstandort unabhängig davon, welchem Pool oder welchem Standort der Benutzer zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="6ebc6-111">The reason for this special policy scoping behavior is so that when a user homed on a pool at one office site visits another site and has to make an emergency call, the E9-1-1 call routing settings appropriate to that network site will apply no matter what pool or site the user is assigned to.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

