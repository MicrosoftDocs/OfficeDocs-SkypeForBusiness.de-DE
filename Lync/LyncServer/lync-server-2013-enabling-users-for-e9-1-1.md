---
title: 'Lync Server 2013: Aktivieren von Benutzern für E9-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling users for E9-1-1
ms:assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425892(v=OCS.15)
ms:contentKeyID: 48183884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5550ec608b34b66a3e47ceb4535dd23ca7c9a7f1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146348"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-users-for-e9-1-1-in-lync-server-2013"></a><span data-ttu-id="13e01-102">Aktivieren von Benutzern für E9-1-1 in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13e01-102">Enabling users for E9-1-1 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="13e01-103">_**Letztes Änderungsstand des Themas:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="13e01-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="13e01-104">Während der Clientregistrierung verwendet lync Server eine ortungsrichtlinie, um die E9-1-1-Eigenschaften für Enterprise-VoIP-aktivierte Benutzer zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="13e01-104">During client registration, Lync Server uses a location policy to configure the E9-1-1 properties for Enterprise Voice-enabled users.</span></span> <span data-ttu-id="13e01-105">Diese Richtlinie enthält die Einstellungen, die definieren, wie E9-1-1 implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="13e01-105">This policy contains the settings that define how E9-1-1 is implemented.</span></span> <span data-ttu-id="13e01-106">Die ortungsrichtlinie enthält beispielsweise Informationen wie die Notrufnummern Zeichenfolge und gibt an, ob ein Benutzer einen Speicherort manuell eingeben muss, wenn der Standortinformationsdienst nicht automatisch einen Ort bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="13e01-106">For example, the location policy contains information such as the emergency dial string, and whether or not a user is required to manually enter a location if the Location Information service does not automatically provide one.</span></span> <span data-ttu-id="13e01-107">Eine vollständige Definition einer ortungsrichtlinie finden Sie unter [Definieren der ortungsrichtlinie für lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span><span class="sxs-lookup"><span data-stu-id="13e01-107">For a complete definition of a location policy, see [Defining the location policy for Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span></span>

<span data-ttu-id="13e01-108">Lync Server können Clients basierend auf dem Subnetz oder Benutzern basierend auf einer globalen, Standort-oder benutzerbezogenen Richtlinie eine ortungsrichtlinie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="13e01-108">Lync Server can assign a location policy to clients based on subnet, or to users based on a global, per-site, or per-user policy.</span></span> <span data-ttu-id="13e01-109">Beantworten Sie zunächst die folgenden Fragen, bevor Sie sich für eine Methode zum Aktivieren der Benutzer für E9-1-1 entscheiden.</span><span class="sxs-lookup"><span data-stu-id="13e01-109">To help decide how you will enable users, you should first answer the following questions.</span></span>

  - <span data-ttu-id="13e01-110">**Planen Sie die Aktivierung für alle Benutzer, oder soll die Unterstützung auf spezifische geografische Bereiche innerhalb des Unternehmens beschränkt werden?**</span><span class="sxs-lookup"><span data-stu-id="13e01-110">**Do you plan to enable all users, or limit support to specific geographic areas of the enterprise?**</span></span>  
    <span data-ttu-id="13e01-111">Sie können allen Benutzern in Ihrem Unternehmen einen Standort zuweisen, indem Sie eine globale Ortungsrichtlinie verwenden.</span><span class="sxs-lookup"><span data-stu-id="13e01-111">You can assign a location to all users in your enterprise by using a global location policy.</span></span> <span data-ttu-id="13e01-112">Durch das Zuweisen einer ortungsrichtlinie zu einem lync Server Netzwerkstandort und das anschließende Hinzufügen von Subnetzen zum Standort können Sie die E9-1 -1-Unterstützung jedoch auf ausgewählte Standorte innerhalb des Unternehmens beschränken und das Routingverhalten für E9-1-1 pro Standort angeben.</span><span class="sxs-lookup"><span data-stu-id="13e01-112">However, by assigning a location policy to a Lync Server network site and then adding subnets to the site, you can limit E9-1-1 support to selected locations within the enterprise and specify E9-1-1 routing behavior on a per-site basis.</span></span>

<!-- end list -->

  - <span data-ttu-id="13e01-113">**Planen Sie die Aktivierung einzelner Benutzer über eine Benutzerrichtlinie?**</span><span class="sxs-lookup"><span data-stu-id="13e01-113">**Do you plan to enable individual users through a user policy?**</span></span>  
    <span data-ttu-id="13e01-114">Sie können bestimmten Benutzern oder Kontaktobjekten von Telefonen in öffentlichen Bereichen direkt Ortungsrichtlinien zuweisen, wenn Sie die E9-1-1-Unterstützung anpassen möchten.</span><span class="sxs-lookup"><span data-stu-id="13e01-114">You can assign location policies directly to specific users or common area phone contact objects if you want to customize their E9-1-1 support.</span></span>

<!-- end list -->

  - <span data-ttu-id="13e01-115">**Sollen Clients auch dann für E9-1-1 aktiviert werden, wenn sie sich außerhalb des Netzwerks bewegen oder sich von einem undefinierten Subnetz aus verbinden?**</span><span class="sxs-lookup"><span data-stu-id="13e01-115">**When clients roam outside the network or connect from an undefined subnet, should the clients still be enabled for E9-1-1?**</span></span>  
    <span data-ttu-id="13e01-116">Wenn Benutzern eine globale Standort-, Standort-oder benutzerspezifische ortungsrichtlinie zugewiesen ist, kann Sie zur manuellen Eingabe eines Standorts in den Client verpflichtet werden, wenn sich der Client nicht in einem definierten Subnetz befindet oder wenn der Standortinformationsdienst keinen Ort gefunden hat.</span><span class="sxs-lookup"><span data-stu-id="13e01-116">If users are assigned a global, site, or per-user location policy, they can be required to manually enter a location into the client if the client is not located within a defined subnet or no location has been found by the Location Information service.</span></span> <span data-ttu-id="13e01-117">Ausführliche Informationen finden Sie unter [Definieren der Benutzeroberfläche für den manuellen Erwerb eines Standorts in lync Server 2013](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md).</span><span class="sxs-lookup"><span data-stu-id="13e01-117">For details, see [Defining the user experience for manually acquiring a location in Lync Server 2013](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

