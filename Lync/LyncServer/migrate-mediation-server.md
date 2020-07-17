---
title: Migrieren des Vermittlungsservers
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
ms.openlocfilehash: 80c6dbc55e41324ad9c3e7d83bb593d8b8e93c64
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756956"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-mediation-server"></a><span data-ttu-id="0a784-102">Migrieren des Vermittlungsservers</span><span class="sxs-lookup"><span data-stu-id="0a784-102">Migrate Mediation Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0a784-103">_**Letztes Änderungsstand des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="0a784-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="0a784-104">Wenn Sie den Merge-Assistenten ausführen, wird Ihr Vermittlungsserver mit der lync Server 2013 Pilot Topologie zusammengeführt.</span><span class="sxs-lookup"><span data-stu-id="0a784-104">Your Mediation Server is merged into your Lync Server 2013 pilot topology when you run the Merge wizard.</span></span> <span data-ttu-id="0a784-105">Sie konfigurieren die lync Server 2013 Vermittlungsserver jedoch, nachdem alle Benutzer migriert wurden, da ein Office Communications Server 2007 R2 Pool nicht mit einem lync Server 2013 Vermittlungsserver kommunizieren kann.</span><span class="sxs-lookup"><span data-stu-id="0a784-105">You configure the Lync Server 2013 Mediation Server, however, after all users are migrated because an Office Communications Server 2007 R2 pool cannot communicate with a Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="0a784-106">Während der parallelen Migration kommuniziert der lync Server 2013 Pool mit dem Office Communications Server 2007 R2 Vermittlungsserver.</span><span class="sxs-lookup"><span data-stu-id="0a784-106">During the side-by-side migration, the Lync Server 2013 pool communicates with the Office Communications Server 2007 R2 Mediation Server.</span></span>

<span data-ttu-id="0a784-107">Wenn Sie Ihre lync Server 2013 Vermittlungsserver konfigurieren, müssen Sie auch Ihre Office Communications Server 2007 R2 Gateways aktualisieren oder ersetzen.</span><span class="sxs-lookup"><span data-stu-id="0a784-107">When you configure your Lync Server 2013 Mediation Server, you must also upgrade or replace your Office Communications Server 2007 R2 gateways.</span></span> <span data-ttu-id="0a784-108">Lync Server 2013 Vermittlungsserver werden von Office Communications Server 2007 R2 Gateways nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0a784-108">Office Communications Server 2007 R2 gateways do not support Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="0a784-109">Sie müssen Gateways bereitstellen, die für lync Server 2013 zertifiziert sind, und Sie dem lync Server 2013 Vermittlungsserver zuordnen.</span><span class="sxs-lookup"><span data-stu-id="0a784-109">You need to deploy gateways that are certified for Lync Server 2013 and associate them with the Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="0a784-110">Dieser Schritt ist erforderlich, bevor Sie Ihre Office Communications Server 2007 R2-Bereitstellung vollständig außer Betrieb nehmen können.</span><span class="sxs-lookup"><span data-stu-id="0a784-110">This step is required before you can completely decommission your Office Communications Server 2007 R2 deployment.</span></span>

<span data-ttu-id="0a784-111">In den Themen in diesem Abschnitt werden Konfigurationsaufgaben beschrieben, die Sie nach Abschluss der Migration von lync Server 2013 Vermittlungsserver ausführen müssen.</span><span class="sxs-lookup"><span data-stu-id="0a784-111">The topics in this section describe configuration tasks that you need to perform after you have completed your migration of Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="0a784-112">Der Übergang des verbundenen Vermittlungsservers in einen eigenständigen Vermittlungsserver ist eine optionale Aufgabe.</span><span class="sxs-lookup"><span data-stu-id="0a784-112">Transitioning the collocated Mediation Server to a stand-alone Mediation Server is an optional task.</span></span>

  - [<span data-ttu-id="0a784-113">Konfigurieren von Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="0a784-113">Configure Mediation Server</span></span>](configure-mediation-server.md)

  - [<span data-ttu-id="0a784-114">Ändern der VoIP-Routen für die Verwendung der neuen lync Server 2013 Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="0a784-114">Change voice routes to use the new Lync Server 2013 Mediation Server</span></span>](change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md)

  - [<span data-ttu-id="0a784-115">Übergang einer verbundenen Vermittlungsserver zu einem eigenständigen Vermittlungsserver (optional)</span><span class="sxs-lookup"><span data-stu-id="0a784-115">Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)</span></span>](transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional.md)

</div>

<span> </span>

</div>

</div>

</div>

