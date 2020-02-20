---
title: 'Lync Server 2013: Definieren der Anforderungen für den Server für beständigen Chat'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organization's requirements for Persistent Chat Server
ms:assetid: 568674fb-c08a-4170-ac38-e2f8428c69e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398372(v=OCS.15)
ms:contentKeyID: 48184166
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 15beb7728525fa3e4bb6b75dfc46fb46335d1063
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154677"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-your-organizations-requirements-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="0c7da-102">Definieren der Anforderungen Ihrer Organisation für den Server für beständigen Chat in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c7da-102">Defining your organization's requirements for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c7da-103">_**Letztes Änderungsstand des Themas:** 2014-01-15_</span><span class="sxs-lookup"><span data-stu-id="0c7da-103">_**Topic Last Modified:** 2014-01-15_</span></span>

<span data-ttu-id="0c7da-104">Bevor Sie den Server für beständigen Chat für Ihre Organisation bereitstellen, müssen Sie unbedingt die folgenden wichtigen Fragen zur Optimierung Ihrer Bereitstellung behandeln:</span><span class="sxs-lookup"><span data-stu-id="0c7da-104">Before you deploy Persistent Chat Server for your organization, it’s essential to consider the following key questions to optimize your deployment:</span></span>

  - <span data-ttu-id="0c7da-105">Wer (Benutzerprofil) sollte für den Server für beständigen Chat aktiviert werden?</span><span class="sxs-lookup"><span data-stu-id="0c7da-105">Who (user profile) should be enabled for Persistent Chat Server?</span></span> <span data-ttu-id="0c7da-106">Der Server für beständigen Chat wird durch eine Richtlinie aktiviert, die auf globaler, Standort-, Pool-oder Benutzerebene festgelegt werden kann.</span><span class="sxs-lookup"><span data-stu-id="0c7da-106">Persistent Chat Server is enabled by a policy that can be set at a Global, Site, Pool or User level.</span></span>

  - <span data-ttu-id="0c7da-107">Wie viele Benutzer (Skalierung) sollten für den Server für beständigen Chat aktiviert werden?</span><span class="sxs-lookup"><span data-stu-id="0c7da-107">How many users (scale) should be enabled for Persistent Chat Server?</span></span> <span data-ttu-id="0c7da-108">Der Server für beständigen Chat unterstützt 150.000-Benutzer (aktiviert nach Richtlinie) und maximal 80.000 gleichzeitige Benutzer mit persistent Chat Server.</span><span class="sxs-lookup"><span data-stu-id="0c7da-108">Persistent Chat Server supports 150,000 provisioned users (enabled by policy), and a maximum of 80,000 concurrent users using Persistent Chat Server.</span></span> <span data-ttu-id="0c7da-109">Ein einzelner Server für beständigen Chat kann 20.000 verbundene Benutzer unterstützen, und ein einzelner Serverpool für beständigen Chat kann bis zu 4 aktive Server für insgesamt 80.000 gleichzeitig verbundene Benutzer haben.</span><span class="sxs-lookup"><span data-stu-id="0c7da-109">A single Persistent Chat Server can support 20,000 connected users, and a single Persistent Chat Server pool can have up to 4 active servers for a total of 80,000 concurrently connected users.</span></span>

  - <span data-ttu-id="0c7da-110">Migrieren Sie von einer früheren Version des Gruppen Chat Servers oder stellen Sie den Server für beständigen Chat zum ersten Mal bereit?</span><span class="sxs-lookup"><span data-stu-id="0c7da-110">Are you migrating from a previous version of Group Chat Server, or are you deploying Persistent Chat Server for the first time?</span></span>

  - <span data-ttu-id="0c7da-111">Gibt es Compliance-Anforderungen?</span><span class="sxs-lookup"><span data-stu-id="0c7da-111">Are there compliance requirements?</span></span> <span data-ttu-id="0c7da-112">Der Server für beständigen Chat unterstützt die Kompatibilität.</span><span class="sxs-lookup"><span data-stu-id="0c7da-112">Persistent Chat Server supports compliance.</span></span> <span data-ttu-id="0c7da-113">Der Kompatibilitätsdienst wird auf dem Server für beständigen Chat Front-End-Server im Gegensatz zur Anforderung eines separaten Computers in früheren Gruppenchatserver-Bereitstellungen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="0c7da-113">The compliance service runs collocated on the Persistent Chat Server Front End Server, as opposed to the requirement for a separate computer in previous Group Chat Server deployments.</span></span> <span data-ttu-id="0c7da-114">Compliance ist optional und erfordert, falls ausgewählt, eine Kompatibilitätsdatenbank, die zum Speichern von Kompatibilitätsdaten und-Ereignissen konfiguriert werden muss.</span><span class="sxs-lookup"><span data-stu-id="0c7da-114">Compliance is optional, and if chosen, requires a compliance database that must be configured to store compliance data and events.</span></span> <span data-ttu-id="0c7da-115">Möglicherweise möchten Sie auch einen Adapter konfigurieren, um die Daten aus der Kompatibilitätsdatenbank zu übernehmen und in ein anderes Format (beispielsweise XML-Dateien oder in Exchange gehostete Archive) zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="0c7da-115">You may want to also configure an adapter to take the data from the compliance database and convert to another format (such as XML files or Exchange-hosted archives).</span></span>

  - <span data-ttu-id="0c7da-p104">Wie sollen Bereiche, ethische Grenzen und Zugriffsmöglichkeiten kontrolliert werden? Mithilfe von **Kategorien** können Sie diese Grenzen ziehen und auswählen, welche Benutzer auf die Räume zugreifen können, die in den einzelnen Kategorien erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="0c7da-p104">How do you want to control scopes, ethical boundaries, and access? You can define **Categories** to segregate these boundaries, and choose who is allowed to be in rooms that are created in each of these categories.</span></span>

  - <span data-ttu-id="0c7da-p105">Wie soll kontrolliert werden, welche Benutzer Räume erstellen dürfen? Sie können unter Berücksichtigung Ihrer Kategorien **Ersteller** konfigurieren, die Räume erstellen dürfen. Ersteller können darüber hinaus andere Mitglieder für die laufende Verwaltung der Räume (Hinzufügen oder Entfernen von Mitgliedern) als **Chatroomanager** einsetzen. Die Grundlage hierfür ist der Bereich für **AllowedMembers/DeniedMembers**, der durch die jeweilige Kategorie festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="0c7da-p105">How do you want to control who can create rooms? You can configure **Creators**, appropriate to your categories, who can create rooms. Creators can assign other members as **Chat Room Managers** for ongoing management of the rooms (adding or removing additional members), according to the scope for **AllowedMembers/DeniedMembers** configured by the category.</span></span>

  - <span data-ttu-id="0c7da-121">Wie möchten Sie Räume erstellen?</span><span class="sxs-lookup"><span data-stu-id="0c7da-121">How do you want to create rooms?</span></span> <span data-ttu-id="0c7da-122">Der Server für beständigen Chat stellt eine webbasierte Funktion zum Erstellen und Verwalten von Räumen bereit.</span><span class="sxs-lookup"><span data-stu-id="0c7da-122">Persistent Chat Server provides a web-based feature for room creation and management.</span></span> <span data-ttu-id="0c7da-123">Dies kann über den lync 2013-Client gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="0c7da-123">This can be launched from the Lync 2013 client.</span></span> <span data-ttu-id="0c7da-124">Sie können eine benutzerdefinierte Lösung (mit dem Server Software Development Kit (SDK) für beständigen Chat) definieren, die Ihre geschäftlichen Anforderungen und Workflows implementiert, und den Server für beständigen Chat so konfigurieren, dass Benutzer zu Ihrer benutzerdefinierten Lösung geleitet werden.</span><span class="sxs-lookup"><span data-stu-id="0c7da-124">You can choose to define a custom solution (by using the Persistent Chat Server Software Development Kit (SDK)) that implements your business requirements and workflows, and configures Persistent Chat Server to direct users to your custom solution.</span></span>

  - <span data-ttu-id="0c7da-125">Welche Arten von Add-Ins möchten Sie bereitstellen?</span><span class="sxs-lookup"><span data-stu-id="0c7da-125">What kind of add-ins do you want to provision?</span></span> <span data-ttu-id="0c7da-126">**Add-ins** verbessern die in-Room-Erfahrung durch die Nutzung des Erweiterungsbereichs im lync 2013-Client, um für den raumrelevante Kontext bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="0c7da-126">**Add-ins** enhance the in-room experience by leveraging the extensibility pane in the Lync 2013 client to provide context that is relevant to the room.</span></span> <span data-ttu-id="0c7da-127">Sie können die allgemeinen Add-Ins auswählen, die Ihnen (beispielsweise im Hinblick auf Ihre Unternehmenswebsite oder Dokumente für die interne Zusammenarbeit) am hilfreichsten erscheinen.</span><span class="sxs-lookup"><span data-stu-id="0c7da-127">You can choose what general add-ins might be most useful (for example, your company website, internal collaboration documents, and so on).</span></span> <span data-ttu-id="0c7da-128">Chatroom-Manager können bei Bedarf eines der registrierten Add-Ins auswählen und ihren Räumen zuordnen.</span><span class="sxs-lookup"><span data-stu-id="0c7da-128">Chat room managers can choose one of the registered add-ins and associate it with their rooms, if desired.</span></span>

  - <span data-ttu-id="0c7da-129">Welche Vorkehrungen wurden bezüglich der Anforderungen an die Hochverfügbarkeit sowie der Notfallwiederherstellung getroffen?</span><span class="sxs-lookup"><span data-stu-id="0c7da-129">What kind of high availability and disaster recovery requirements do you have?</span></span> <span data-ttu-id="0c7da-130">Der Server für beständigen Chat unterstützt SQL Server Spiegelung und SQL Server Clustering für hohe Verfügbarkeit und unterstützt bis zu 8 Server (4 aktive und 4 Standby) in einem gestreckten Pool mit SQL Server Protokollversand für die Notfallwiederherstellung.</span><span class="sxs-lookup"><span data-stu-id="0c7da-130">Persistent Chat Server supports SQL Server mirroring and SQL Server clustering for high availability and supports up to 8 servers (4 active and 4 standby) in a stretched pool with SQL Server log shipping for disaster recovery.</span></span>

  - <span data-ttu-id="0c7da-131">Gibt es regulatorische Anforderungen?</span><span class="sxs-lookup"><span data-stu-id="0c7da-131">Are there regulatory requirements?</span></span> <span data-ttu-id="0c7da-132">Wenn sich Ihr Unternehmen in einem Land/einer Region befindet, in dem Daten innerhalb des Landes aufbewahrt werden müssen, müssen Sie möglicherweise mehrere Server Pools für beständigen Chat bereitstellen, die jeweils lokal in einer bestimmten geografischen Umgebung liegen.</span><span class="sxs-lookup"><span data-stu-id="0c7da-132">If your company is in a country/region where data needs to be kept within the country, you may need to deploy multiple Persistent Chat Server pools, each local to a specific geography.</span></span> <span data-ttu-id="0c7da-133">Ein Raum, eine Kategorie oder ein Add-in umfasst keine Pools – es gehört nur zu einem Server Pool für beständigen Chat.</span><span class="sxs-lookup"><span data-stu-id="0c7da-133">A room, category, or add-in does not span pools—it belongs to only one Persistent Chat Server pool.</span></span> <span data-ttu-id="0c7da-134">Sie können die Gruppe von Kategorien, Add-Ins und Chatrooms für jeden Server Pool für beständigen Chat verwalten.</span><span class="sxs-lookup"><span data-stu-id="0c7da-134">You can manage the set of categories, add-ins and rooms for each Persistent Chat Server pool.</span></span> <span data-ttu-id="0c7da-135">Benutzer können so konfiguriert werden, dass Sie den Zugriff auf Chatrooms in einem oder mehreren Pools mithilfe des Bereichs oder der Mitgliedschafts Bereiche der Kategorie AllowedMembers, je nachdem, wie Sie Ihre Kategorien entwerfen.</span><span class="sxs-lookup"><span data-stu-id="0c7da-135">Users can be configured to have access to rooms in one or more pools using the category AllowedMembers scope or Room’s membership scope, depending on how you design your categories.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="0c7da-136">Wenn Sie über mehrere Server Pools für beständigen Chat verfügen, erhalten Sie keinen größeren Maßstab (Sie können weiterhin nur 80.000 gleichzeitig verbundene Benutzer über alle Ihre Server Pools für beständigen Chat verfügen).</span><span class="sxs-lookup"><span data-stu-id="0c7da-136">Having multiple Persistent Chat Server pools does not give you more scale (you can still have only 80,000 concurrently connected users across all your Persistent Chat Server pools).</span></span> <span data-ttu-id="0c7da-137">Der Hauptgrund für die Unterstützung mehrerer Server Pools für beständigen Chat besteht darin, regulatorische Belange zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="0c7da-137">The primary reason for supporting multiple Persistent Chat Server pools is to support regulatory concerns.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

