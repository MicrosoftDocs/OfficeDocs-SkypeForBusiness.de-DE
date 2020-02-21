---
title: 'Lync Server 2013: Konfigurieren der gruppenanrufannahme'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Group Call Pickup
ms:assetid: b4b0a9a0-91c6-43a5-9e2b-a086caeb3f94
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945645(v=OCS.15)
ms:contentKeyID: 51541505
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef62fc903e70c0ff60cd86d124fbd092d9b394c1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206401"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="dd13e-102">Konfigurieren der gruppenanrufannahme in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd13e-102">Configuring Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dd13e-103">_**Letztes Änderungsstand des Themas:** 2013-02-01_</span><span class="sxs-lookup"><span data-stu-id="dd13e-103">_**Topic Last Modified:** 2013-02-01_</span></span>

<span data-ttu-id="dd13e-104">Kumulatives Update für lync Server 2013: Februar 2013 bietet eine Einführung in die gruppenanrufannahme als neue Enterprise-VoIP-Funktion.</span><span class="sxs-lookup"><span data-stu-id="dd13e-104">Cumulative update for Lync Server 2013: February 2013 introduces Group Call Pickup as a new Enterprise Voice feature.</span></span> <span data-ttu-id="dd13e-105">Bei der gruppenanrufannahme können Benutzer Anrufe abholen, die für einen anderen Benutzer Klingeln, indem Sie eine Rufnummer für die Anrufannahme Gruppe wählen.</span><span class="sxs-lookup"><span data-stu-id="dd13e-105">Group Call Pickup lets users pick up calls that are ringing for another user by dialing a call pickup group number.</span></span>

<span data-ttu-id="dd13e-106">Die Komponenten, die für die gruppenanrufannahme verwendet werden, werden automatisch auf dem Front-End-Server oder Standard Edition-Server installiert und aktiviert, wenn Sie Enterprise-VoIP bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="dd13e-106">The components that Group Call Pickup uses are automatically installed and enabled on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="dd13e-107">Sie müssen jedoch die gruppenanrufannahme konfigurieren, bevor Sie für die Benutzer verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="dd13e-107">However, you must configure Group Call Pickup before it is available to users.</span></span>

<span data-ttu-id="dd13e-108">Dieser Abschnitt führt Sie durch die Konfiguration der gruppenanrufannahme.</span><span class="sxs-lookup"><span data-stu-id="dd13e-108">This section guides you through the configuration of Group Call Pickup.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="dd13e-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="dd13e-109">In This Section</span></span>

[<span data-ttu-id="dd13e-110">Konfigurieren von Voraussetzungen und Benutzerrechten für Gruppenanruf Pickups in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd13e-110">Group Call Pickup configuration prerequisites and user rights in Lync Server 2013</span></span>](lync-server-2013-group-call-pickup-configuration-prerequisites-and-user-rights.md)

[<span data-ttu-id="dd13e-111">Bereitstellungsprozess für die Gruppenanruf Abholung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd13e-111">Deployment process for Group Call Pickup in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-group-call-pickup.md)

[<span data-ttu-id="dd13e-112">Bereitstellen des SEFAUtil-Tools in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd13e-112">Deploy the SEFAUtil tool in Lync Server 2013</span></span>](lync-server-2013-deploy-the-sefautil-tool.md)

[<span data-ttu-id="dd13e-113">Konfigurieren von Nummern für die Anrufannahme Gruppe in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd13e-113">Configure call pickup group numbers in Lync Server 2013</span></span>](lync-server-2013-configure-call-pickup-group-numbers.md)

[<span data-ttu-id="dd13e-114">Aktivieren der gruppenanrufannahme für Benutzer in lync Server 2013 und Zuweisen einer Gruppennummer</span><span class="sxs-lookup"><span data-stu-id="dd13e-114">Enable Group Call Pickup for users in Lync Server 2013 and assign a group number</span></span>](lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md)

[<span data-ttu-id="dd13e-115">Mitteilen von Gruppenanruf-Pickup-Zuweisungen an Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd13e-115">Communicate Group Call Pickup assignments to users in Lync Server 2013</span></span>](lync-server-2013-communicate-group-call-pickup-assignment-to-users.md)

[<span data-ttu-id="dd13e-116">Optional Überprüfen der Gruppenanruf-Pickup-Bereitstellung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd13e-116">(Optional) Verify the Group Call Pickup deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-the-group-call-pickup-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

