---
title: Migrieren des Vermittlungsservers
description: Migrieren von Vermittlungsserver.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Mediation Server
ms:assetid: b0b77121-2c8f-413e-b276-dbf1038361d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205173(v=OCS.15)
ms:contentKeyID: 48185117
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31cc4c95f0e9c86b48594238218db22f3ec1a387
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570331"
---
# <a name="migrate-mediation-server"></a><span data-ttu-id="326c8-103">Migrieren des Vermittlungsservers</span><span class="sxs-lookup"><span data-stu-id="326c8-103">Migrate Mediation Server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="326c8-104">_**Letztes Änderungsstand des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="326c8-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="326c8-105">Wenn Sie den Merge-Assistenten ausführen, wird Ihr Vermittlungsserver mit der lync Server 2013 Pilot Topologie zusammengeführt.</span><span class="sxs-lookup"><span data-stu-id="326c8-105">Your Mediation Server is merged into your Lync Server 2013 pilot topology when you run the Merge wizard.</span></span> <span data-ttu-id="326c8-106">Sie konfigurieren die lync Server 2013 Vermittlungsserver jedoch, nachdem alle Benutzer migriert wurden, da ein Office Communications Server 2007 R2 Pool nicht mit einem lync Server 2013 Vermittlungsserver kommunizieren kann.</span><span class="sxs-lookup"><span data-stu-id="326c8-106">You configure the Lync Server 2013 Mediation Server, however, after all users are migrated because an Office Communications Server 2007 R2 pool cannot communicate with a Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="326c8-107">Während der parallelen Migration kommuniziert der lync Server 2013 Pool mit dem Office Communications Server 2007 R2 Vermittlungsserver.</span><span class="sxs-lookup"><span data-stu-id="326c8-107">During the side-by-side migration, the Lync Server 2013 pool communicates with the Office Communications Server 2007 R2 Mediation Server.</span></span>

<span data-ttu-id="326c8-108">Wenn Sie Ihre lync Server 2013 Vermittlungsserver konfigurieren, müssen Sie auch Ihre Office Communications Server 2007 R2 Gateways aktualisieren oder ersetzen.</span><span class="sxs-lookup"><span data-stu-id="326c8-108">When you configure your Lync Server 2013 Mediation Server, you must also upgrade or replace your Office Communications Server 2007 R2 gateways.</span></span> <span data-ttu-id="326c8-109">Lync Server 2013 Vermittlungsserver werden von Office Communications Server 2007 R2 Gateways nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="326c8-109">Office Communications Server 2007 R2 gateways do not support Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="326c8-110">Sie müssen Gateways bereitstellen, die für lync Server 2013 zertifiziert sind, und Sie dem lync Server 2013 Vermittlungsserver zuordnen.</span><span class="sxs-lookup"><span data-stu-id="326c8-110">You need to deploy gateways that are certified for Lync Server 2013 and associate them with the Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="326c8-111">Dieser Schritt ist erforderlich, bevor Sie Ihre Office Communications Server 2007 R2-Bereitstellung vollständig außer Betrieb nehmen können.</span><span class="sxs-lookup"><span data-stu-id="326c8-111">This step is required before you can completely decommission your Office Communications Server 2007 R2 deployment.</span></span>

<span data-ttu-id="326c8-112">In den Themen in diesem Abschnitt werden Konfigurationsaufgaben beschrieben, die Sie nach Abschluss der Migration von lync Server 2013 Vermittlungsserver ausführen müssen.</span><span class="sxs-lookup"><span data-stu-id="326c8-112">The topics in this section describe configuration tasks that you need to perform after you have completed your migration of Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="326c8-113">Der Übergang des verbundenen Vermittlungsservers in einen eigenständigen Vermittlungsserver ist eine optionale Aufgabe.</span><span class="sxs-lookup"><span data-stu-id="326c8-113">Transitioning the collocated Mediation Server to a stand-alone Mediation Server is an optional task.</span></span>

  - [<span data-ttu-id="326c8-114">Konfigurieren von Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="326c8-114">Configure Mediation Server</span></span>](configure-mediation-server.md)

  - [<span data-ttu-id="326c8-115">Ändern der VoIP-Routen für die Verwendung der neuen lync Server 2013 Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="326c8-115">Change voice routes to use the new Lync Server 2013 Mediation Server</span></span>](change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md)

  - [<span data-ttu-id="326c8-116">Übergang einer verbundenen Vermittlungsserver zu einem eigenständigen Vermittlungsserver (optional)</span><span class="sxs-lookup"><span data-stu-id="326c8-116">Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)</span></span>](transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional.md)

</div>

<span> </span>

</div>

</div>

</div>

