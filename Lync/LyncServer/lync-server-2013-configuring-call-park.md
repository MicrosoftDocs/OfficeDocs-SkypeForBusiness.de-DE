---
title: 'Lync Server 2013: Konfigurieren des Parkens von Anrufen'
description: 'Lync Server 2013: Konfigurieren des Anruf Parks.'
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
ms.openlocfilehash: 1d2708f26fae5706afc31aa195b9fdb82536247b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568751"
---
# <a name="configuring-call-park-in-lync-server-2013"></a><span data-ttu-id="65dc1-103">Konfigurieren des Parkens von Anrufen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65dc1-103">Configuring Call Park in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="65dc1-104">_**Letztes Änderungsstand des Themas:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="65dc1-104">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="65dc1-105">Das Parken von Anrufen ermöglicht einem Enterprise-VoIP-Benutzer, von einem Telefon aus einen Anruf zu tätigen und den Anruf dann später abzurufen, indem er von einem beliebigen Telefon aus eine interne Rufnummer (als *Orbit*für das Parken von Anrufen bezeichnet) wählt.</span><span class="sxs-lookup"><span data-stu-id="65dc1-105">Call Park enables an Enterprise Voice user to put a call on hold from one telephone and then retrieve the call later by dialing an internal number (known as a Call Park *orbit*) from any telephone.</span></span>

<span data-ttu-id="65dc1-106">Die Komponenten, die der Anruf Park verwendet, werden automatisch auf dem Front-End-Server oder Standard Edition-Server installiert und aktiviert, wenn Sie Enterprise-VoIP bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="65dc1-106">The components that Call Park uses are automatically installed and enabled on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="65dc1-107">Sie müssen jedoch das Parken von anrufen konfigurieren, bevor es für Benutzer verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="65dc1-107">However, you must configure Call Park before it is available to users.</span></span>

<span data-ttu-id="65dc1-108">Dieser Abschnitt führt Sie durch die Konfiguration des Parkens von anrufen.</span><span class="sxs-lookup"><span data-stu-id="65dc1-108">This section guides you through the configuration of Call Park.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="65dc1-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="65dc1-109">In This Section</span></span>

  - [<span data-ttu-id="65dc1-110">Voraussetzungen und Benutzerrechte für die Konfiguration des Anruf Parks in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65dc1-110">Call Park configuration prerequisites and user rights in Lync Server 2013</span></span>](lync-server-2013-call-park-configuration-prerequisites-and-user-rights.md)

  - [<span data-ttu-id="65dc1-111">Bereitstellungsprozess für das Parken von Anrufen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65dc1-111">Deployment process for Call Park in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-call-park.md)

  - [<span data-ttu-id="65dc1-112">Konfigurieren der Orbit-Tabelle für das Parken von Anrufen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65dc1-112">Configure the Call Park orbit table in Lync Server 2013</span></span>](lync-server-2013-configure-the-call-park-orbit-table.md)

  - [<span data-ttu-id="65dc1-113">Konfigurieren von Einstellungen für das Parken von Anrufen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65dc1-113">Configure Call Park settings in Lync Server 2013</span></span>](lync-server-2013-configure-call-park-settings.md)

  - [<span data-ttu-id="65dc1-114">Anpassen der Wartemusik für das Parken von Anrufen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65dc1-114">Customize Call Park music on hold in Lync Server 2013</span></span>](lync-server-2013-customize-call-park-music-on-hold.md)

  - [<span data-ttu-id="65dc1-115">Parken von Anrufen für Benutzer in lync Server 2013 aktivieren</span><span class="sxs-lookup"><span data-stu-id="65dc1-115">Enable Call Park for users in Lync Server 2013</span></span>](lync-server-2013-enable-call-park-for-users.md)

  - [<span data-ttu-id="65dc1-116">Überprüfen der Normalisierungsregeln für das Parken von Anrufen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65dc1-116">Verify normalization rules for Call Park in Lync Server 2013</span></span>](lync-server-2013-verify-normalization-rules-for-call-park.md)

  - [<span data-ttu-id="65dc1-117">Optional Überprüfen der Bereitstellung des Anruf Parks in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65dc1-117">(Optional) Verify Call Park deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-call-park-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

