---
title: Migrieren des Vermittlungsservers
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate Mediation Server
ms:assetid: b0b77121-2c8f-413e-b276-dbf1038361d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205173(v=OCS.15)
ms:contentKeyID: 48185117
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3478bb3bb837e44ed33597f72738b181b4c67561
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762913"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-mediation-server"></a><span data-ttu-id="3cc69-102">Migrieren des Vermittlungsservers</span><span class="sxs-lookup"><span data-stu-id="3cc69-102">Migrate Mediation Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3cc69-103">_**Letztes Änderungsdatum des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="3cc69-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="3cc69-104">Wenn Sie den Zusammenführungs-Assistenten ausführen, wird Ihr Vermittlungsserver mit ihrer lync Server 2013-Pilot Topologie verbunden.</span><span class="sxs-lookup"><span data-stu-id="3cc69-104">Your Mediation Server is merged into your Lync Server 2013 pilot topology when you run the Merge wizard.</span></span> <span data-ttu-id="3cc69-105">Sie konfigurieren den lync Server 2013-Vermittlungsserver allerdings, nachdem alle Benutzer migriert wurden, weil ein Office Communications Server 2007 R2-Pool nicht mit einem lync Server 2013-Vermittlungsserver kommunizieren kann.</span><span class="sxs-lookup"><span data-stu-id="3cc69-105">You configure the Lync Server 2013 Mediation Server, however, after all users are migrated because an Office Communications Server 2007 R2 pool cannot communicate with a Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="3cc69-106">Während der parallelen Migration kommuniziert der lync Server 2013-Pool mit dem Office Communications Server 2007 R2-Vermittlungsserver.</span><span class="sxs-lookup"><span data-stu-id="3cc69-106">During the side-by-side migration, the Lync Server 2013 pool communicates with the Office Communications Server 2007 R2 Mediation Server.</span></span>

<span data-ttu-id="3cc69-107">Wenn Sie Ihren lync Server 2013-Vermittlungsserver konfigurieren, müssen Sie auch Ihre Office Communications Server 2007 R2-Gateways aktualisieren oder ersetzen.</span><span class="sxs-lookup"><span data-stu-id="3cc69-107">When you configure your Lync Server 2013 Mediation Server, you must also upgrade or replace your Office Communications Server 2007 R2 gateways.</span></span> <span data-ttu-id="3cc69-108">Office Communications Server 2007 R2-Gateways unterstützen keinen lync Server 2013-Vermittlungsserver.</span><span class="sxs-lookup"><span data-stu-id="3cc69-108">Office Communications Server 2007 R2 gateways do not support Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="3cc69-109">Sie müssen Gateways bereitstellen, die für lync Server 2013 zertifiziert sind, und Sie dem lync Server 2013-Vermittlungsserver zuordnen.</span><span class="sxs-lookup"><span data-stu-id="3cc69-109">You need to deploy gateways that are certified for Lync Server 2013 and associate them with the Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="3cc69-110">Dieser Schritt ist erforderlich, bevor Sie Ihre Office Communications Server 2007 R2-Bereitstellung vollständig außer Dienststellen können.</span><span class="sxs-lookup"><span data-stu-id="3cc69-110">This step is required before you can completely decommission your Office Communications Server 2007 R2 deployment.</span></span>

<span data-ttu-id="3cc69-111">Die Themen in diesem Abschnitt beschreiben Konfigurationsaufgaben, die Sie ausführen müssen, nachdem Sie die Migration von lync Server 2013-Vermittlungsserver abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="3cc69-111">The topics in this section describe configuration tasks that you need to perform after you have completed your migration of Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="3cc69-112">Der Übergang des beiliegenden Vermittlungsservers zu einem eigenständigen Vermittlungsserver ist eine optionale Aufgabe.</span><span class="sxs-lookup"><span data-stu-id="3cc69-112">Transitioning the collocated Mediation Server to a stand-alone Mediation Server is an optional task.</span></span>

  - [<span data-ttu-id="3cc69-113">Konfigurieren des Vermittlungsservers</span><span class="sxs-lookup"><span data-stu-id="3cc69-113">Configure Mediation Server</span></span>](configure-mediation-server.md)

  - [<span data-ttu-id="3cc69-114">Ändern von VoIP-Routen zur Verwendung des neuen lync Server 2013-Vermittlungsservers</span><span class="sxs-lookup"><span data-stu-id="3cc69-114">Change voice routes to use the new Lync Server 2013 Mediation Server</span></span>](change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md)

  - [<span data-ttu-id="3cc69-115">Umstieg auf einen bereitstehenden Vermittlungsserver zu einem eigenständigen Vermittlungsserver (optional)</span><span class="sxs-lookup"><span data-stu-id="3cc69-115">Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)</span></span>](transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional.md)

</div>

<span> </span>

</div>

</div>

</div>

