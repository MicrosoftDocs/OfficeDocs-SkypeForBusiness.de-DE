---
title: 'Lync Server 2013: Konfigurieren des Parkens von Anrufen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Call Park
ms:assetid: e4c5da53-7f6c-4535-bc9b-9da2026caec8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399014(v=OCS.15)
ms:contentKeyID: 48185732
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 750ea65da2b5507099f097b31044673c474bfc7c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758343"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-call-park-in-lync-server-2013"></a><span data-ttu-id="338d1-102">Konfigurieren des Parkens von Anrufen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="338d1-102">Configuring Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="338d1-103">_**Letztes Änderungsdatum des Themas:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="338d1-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="338d1-104">Der Anruf Park ermöglicht es einem Enterprise-VoIP-Nutzer, einen Anruf von einem Telefon aus zu halten und den Anruf später abzurufen, indem er von einem beliebigen Telefon aus eine interne Rufnummer (sog. Call Park *Orbit*) wählt.</span><span class="sxs-lookup"><span data-stu-id="338d1-104">Call Park enables an Enterprise Voice user to put a call on hold from one telephone and then retrieve the call later by dialing an internal number (known as a Call Park *orbit*) from any telephone.</span></span>

<span data-ttu-id="338d1-105">Die Komponenten, die von Park verwendet werden, werden beim Bereitstellen von Enterprise-VoIP automatisch auf dem Front-End-Server oder Standard Edition-Server installiert und aktiviert.</span><span class="sxs-lookup"><span data-stu-id="338d1-105">The components that Call Park uses are automatically installed and enabled on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="338d1-106">Sie müssen jedoch den Anruf Park konfigurieren, bevor er für die Benutzer verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="338d1-106">However, you must configure Call Park before it is available to users.</span></span>

<span data-ttu-id="338d1-107">Dieser Abschnitt führt Sie durch die Konfiguration des Anruf Parks.</span><span class="sxs-lookup"><span data-stu-id="338d1-107">This section guides you through the configuration of Call Park.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="338d1-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="338d1-108">In This Section</span></span>

  - [<span data-ttu-id="338d1-109">Anforderungen und Benutzerrechte für die Konfiguration zum Parken von Anrufen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="338d1-109">Call Park configuration prerequisites and user rights in Lync Server 2013</span></span>](lync-server-2013-call-park-configuration-prerequisites-and-user-rights.md)

  - [<span data-ttu-id="338d1-110">Bereitstellungsprozess für den Parken von Anrufen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="338d1-110">Deployment process for Call Park in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-call-park.md)

  - [<span data-ttu-id="338d1-111">Konfigurieren der Orbittabelle für das Parken von Anrufen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="338d1-111">Configure the Call Park orbit table in Lync Server 2013</span></span>](lync-server-2013-configure-the-call-park-orbit-table.md)

  - [<span data-ttu-id="338d1-112">Konfigurieren von Einstellungen für den Anruf Park in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="338d1-112">Configure Call Park settings in Lync Server 2013</span></span>](lync-server-2013-configure-call-park-settings.md)

  - [<span data-ttu-id="338d1-113">Anpassen der Musik zum Parken von Anrufen im Wartebereich in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="338d1-113">Customize Call Park music on hold in Lync Server 2013</span></span>](lync-server-2013-customize-call-park-music-on-hold.md)

  - [<span data-ttu-id="338d1-114">Aktivieren des Anruf Parks für Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="338d1-114">Enable Call Park for users in Lync Server 2013</span></span>](lync-server-2013-enable-call-park-for-users.md)

  - [<span data-ttu-id="338d1-115">Überprüfen von Normalisierungsregeln für den Parken von Anrufen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="338d1-115">Verify normalization rules for Call Park in Lync Server 2013</span></span>](lync-server-2013-verify-normalization-rules-for-call-park.md)

  - [<span data-ttu-id="338d1-116">Optional Überprüfen der Bereitstellung des Anruf Parks in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="338d1-116">(Optional) Verify Call Park deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-call-park-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

