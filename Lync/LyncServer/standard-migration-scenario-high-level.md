---
title: Standardmigrationsszenario – Übersicht
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Standard migration scenario - high-level
ms:assetid: e768a7ca-44e3-4969-a6d9-7ed3e7029c5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205354(v=OCS.15)
ms:contentKeyID: 48185709
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69349b90c6845d8a3f3d5ed13544da4fe4832eb8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846993"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="standard-migration-scenario---high-level"></a><span data-ttu-id="78ca4-102">Standardmigrationsszenario – Übersicht</span><span class="sxs-lookup"><span data-stu-id="78ca4-102">Standard migration scenario - high-level</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78ca4-103">_**Letztes Änderungsdatum des Themas:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="78ca4-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="78ca4-104">Verwenden Sie die folgenden Elemente als Ausgangspunkt für die Migration von lync Server 2010, Gruppen-Chat oder Office Communications Server 2007 R2-Gruppenchat zu lync Server 2013, beständiger Chat Server.</span><span class="sxs-lookup"><span data-stu-id="78ca4-104">Use the following items as a starting point when migrating Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="78ca4-105">Der Standard-Migrationspfad für lync Server 2013 lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="78ca4-105">The standard Lync Server 2013 migration path is as follows:</span></span>

  - <span data-ttu-id="78ca4-106">Ihre Organisation hat zuvor lync Server 2010, Gruppen-Chat oder Office Communications Server 2007 R2-Gruppen-Chat bereitgestellt, und Sie möchten lync Server 2013, beständiger Chat Server bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="78ca4-106">Your organization has previously deployed Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat, and you want to deploy Lync Server 2013, Persistent Chat Server.</span></span>

  - <span data-ttu-id="78ca4-107">Stellen Sie lync Server 2013 bereit, und stellen Sie dann den Server Pool für beständigen Chat bereit.</span><span class="sxs-lookup"><span data-stu-id="78ca4-107">Deploy Lync Server 2013, and then deploy Persistent Chat Server pool(s).</span></span>

  - <span data-ttu-id="78ca4-108">Vorbereiten und planen Sie die Migration Ihrer beständigen Chatrooms, und bestimmen Sie einen geeigneten Zeitpunkt für das Herunterfahren des Systems für die Migration.</span><span class="sxs-lookup"><span data-stu-id="78ca4-108">Prepare and plan for migration of your Persistent Chat rooms, and determine an appropriate time to shut down the system for migration.</span></span>

  - <span data-ttu-id="78ca4-109">Führen Sie die Windows PowerShell-Cmdlets für die Migration aus (**Export-CsPersistentChatData** und **Import-CsPersistentChatData**), um Inhalte in den beständigen Chat Server zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="78ca4-109">Run the Windows PowerShell cmdlets for migration (**Export-CsPersistentChatData** and **Import-CsPersistentChatData**) to move content to Persistent Chat Server.</span></span>

  - <span data-ttu-id="78ca4-110">Überprüfen Sie, ob die Migration erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="78ca4-110">Verify that migration has succeeded.</span></span>

  - <span data-ttu-id="78ca4-111">Außerbetriebnahme Ihrer Legacy Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="78ca4-111">Decommission your legacy deployment.</span></span>

  - <span data-ttu-id="78ca4-112">Konfigurieren Sie den Server für beständigen Chat, damit Legacyclients eine Verbindung mit lync Server 2013, persistent Chat Server herstellen können.</span><span class="sxs-lookup"><span data-stu-id="78ca4-112">Configure Persistent Chat Server so that legacy clients can connect to Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="78ca4-113">Dies ist erforderlich, da es Zeit braucht, um neue Clients bereitzustellen, und Sie möchten, dass vorhandene Benutzer mit älteren Clients so schnell wie möglich auf Ihre Chatrooms zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="78ca4-113">This is necessary because it takes time to deploy new clients, and you want to enable existing users with legacy clients to have access to their chat rooms as soon as possible.</span></span>

  - <span data-ttu-id="78ca4-114">Stellen Sie neue Clients bereit, während Sie weiterhin sicherstellen, dass Mitarbeiter mit Legacy-Gruppen-Chats (Clients) in Ihre Chatrooms gelangen können.</span><span class="sxs-lookup"><span data-stu-id="78ca4-114">Deploy new clients, while continuing to help ensure that workers with legacy Group Chat (clients) can get to their chat rooms.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

