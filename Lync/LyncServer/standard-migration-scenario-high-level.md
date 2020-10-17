---
title: Standard Migrationsszenario – High-Level
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Standard migration scenario - high-level
ms:assetid: e768a7ca-44e3-4969-a6d9-7ed3e7029c5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205354(v=OCS.15)
ms:contentKeyID: 48185709
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 62a557d8b5a0f2a3e1e0f248b01795e75c02b3a1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529802"
---
# <a name="standard-migration-scenario---high-level"></a><span data-ttu-id="09607-102">Standard Migrationsszenario – High-Level</span><span class="sxs-lookup"><span data-stu-id="09607-102">Standard migration scenario - high-level</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="09607-103">_**Letztes Änderungsstand des Themas:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="09607-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="09607-104">Verwenden Sie die folgenden Elemente als Ausgangspunkt für die Migration lync Server 2010, Gruppenchats oder Office Communications Server 2007 R2 Gruppenchats zu lync Server 2013 persistent Chat Server.</span><span class="sxs-lookup"><span data-stu-id="09607-104">Use the following items as a starting point when migrating Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="09607-105">Der standardmäßige lync Server 2013 Migrationspfad lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="09607-105">The standard Lync Server 2013 migration path is as follows:</span></span>

  - <span data-ttu-id="09607-106">Ihre Organisation hat zuvor lync Server 2010, Gruppenchat oder Office Communications Server 2007 R2 Gruppenchat bereitgestellt und Sie möchten lync Server 2013 Server für beständigen Chat bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="09607-106">Your organization has previously deployed Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat, and you want to deploy Lync Server 2013, Persistent Chat Server.</span></span>

  - <span data-ttu-id="09607-107">Stellen Sie lync Server 2013 bereit, und stellen Sie dann den Server Pool für beständigen Chat bereit.</span><span class="sxs-lookup"><span data-stu-id="09607-107">Deploy Lync Server 2013, and then deploy Persistent Chat Server pool(s).</span></span>

  - <span data-ttu-id="09607-108">Vorbereiten und Planen der Migration Ihrer beständigen Chatrooms und bestimmen eines geeigneten Zeitraums zum Herunterfahren des Systems für die Migration.</span><span class="sxs-lookup"><span data-stu-id="09607-108">Prepare and plan for migration of your Persistent Chat rooms, and determine an appropriate time to shut down the system for migration.</span></span>

  - <span data-ttu-id="09607-109">Führen Sie die Windows PowerShell-Cmdlets für die Migration aus (**Export-CsPersistentChatData** und **Import-CsPersistentChatData**), um Inhalte auf den Server für beständigen Chat zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="09607-109">Run the Windows PowerShell cmdlets for migration (**Export-CsPersistentChatData** and **Import-CsPersistentChatData**) to move content to Persistent Chat Server.</span></span>

  - <span data-ttu-id="09607-110">Stellen Sie sicher, dass die Migration erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="09607-110">Verify that migration has succeeded.</span></span>

  - <span data-ttu-id="09607-111">Außer Betrieb Ihrer Legacy-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="09607-111">Decommission your legacy deployment.</span></span>

  - <span data-ttu-id="09607-112">Konfigurieren Sie den Server für beständigen Chat, damit ältere Clients eine Verbindung mit lync Server 2013, beständigen Chat Server herstellen können.</span><span class="sxs-lookup"><span data-stu-id="09607-112">Configure Persistent Chat Server so that legacy clients can connect to Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="09607-113">Dies ist erforderlich, da die Bereitstellungneuer Clients Zeit in Anspruch nimmt und Sie möchten, dass vorhandene Benutzer mit älteren Clients so schnell wie möglich auf Ihre Chatrooms zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="09607-113">This is necessary because it takes time to deploy new clients, and you want to enable existing users with legacy clients to have access to their chat rooms as soon as possible.</span></span>

  - <span data-ttu-id="09607-114">Stellen Sie neue Clients bereit, und stellen Sie sicher, dass Mitarbeiter mit Legacy Gruppenchat (Clients) in Ihre Chatrooms gelangen können.</span><span class="sxs-lookup"><span data-stu-id="09607-114">Deploy new clients, while continuing to help ensure that workers with legacy Group Chat (clients) can get to their chat rooms.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

