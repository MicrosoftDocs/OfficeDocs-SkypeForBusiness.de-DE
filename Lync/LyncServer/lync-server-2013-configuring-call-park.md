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
ms.openlocfilehash: 2932053e8224b751c124c80152c097d9da82e517
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043887"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-call-park-in-lync-server-2013"></a><span data-ttu-id="eac9f-102">Konfigurieren des Parkens von Anrufen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eac9f-102">Configuring Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eac9f-103">_**Letztes Änderungsstand des Themas:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="eac9f-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="eac9f-104">Das Parken von Anrufen ermöglicht einem Enterprise-VoIP-Benutzer, von einem Telefon aus einen Anruf zu tätigen und den Anruf dann später abzurufen, indem er von einem beliebigen Telefon aus eine interne Rufnummer (als *Orbit*für das Parken von Anrufen bezeichnet) wählt.</span><span class="sxs-lookup"><span data-stu-id="eac9f-104">Call Park enables an Enterprise Voice user to put a call on hold from one telephone and then retrieve the call later by dialing an internal number (known as a Call Park *orbit*) from any telephone.</span></span>

<span data-ttu-id="eac9f-105">Die Komponenten, die der Anruf Park verwendet, werden automatisch auf dem Front-End-Server oder Standard Edition-Server installiert und aktiviert, wenn Sie Enterprise-VoIP bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="eac9f-105">The components that Call Park uses are automatically installed and enabled on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="eac9f-106">Sie müssen jedoch das Parken von anrufen konfigurieren, bevor es für Benutzer verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="eac9f-106">However, you must configure Call Park before it is available to users.</span></span>

<span data-ttu-id="eac9f-107">Dieser Abschnitt führt Sie durch die Konfiguration des Parkens von anrufen.</span><span class="sxs-lookup"><span data-stu-id="eac9f-107">This section guides you through the configuration of Call Park.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="eac9f-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="eac9f-108">In This Section</span></span>

  - [<span data-ttu-id="eac9f-109">Voraussetzungen und Benutzerrechte für die Konfiguration des Anruf Parks in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eac9f-109">Call Park configuration prerequisites and user rights in Lync Server 2013</span></span>](lync-server-2013-call-park-configuration-prerequisites-and-user-rights.md)

  - [<span data-ttu-id="eac9f-110">Bereitstellungsprozess für das Parken von Anrufen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eac9f-110">Deployment process for Call Park in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-call-park.md)

  - [<span data-ttu-id="eac9f-111">Konfigurieren der Orbit-Tabelle für das Parken von Anrufen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eac9f-111">Configure the Call Park orbit table in Lync Server 2013</span></span>](lync-server-2013-configure-the-call-park-orbit-table.md)

  - [<span data-ttu-id="eac9f-112">Konfigurieren von Einstellungen für das Parken von Anrufen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eac9f-112">Configure Call Park settings in Lync Server 2013</span></span>](lync-server-2013-configure-call-park-settings.md)

  - [<span data-ttu-id="eac9f-113">Anpassen der Wartemusik für das Parken von Anrufen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eac9f-113">Customize Call Park music on hold in Lync Server 2013</span></span>](lync-server-2013-customize-call-park-music-on-hold.md)

  - [<span data-ttu-id="eac9f-114">Parken von Anrufen für Benutzer in lync Server 2013 aktivieren</span><span class="sxs-lookup"><span data-stu-id="eac9f-114">Enable Call Park for users in Lync Server 2013</span></span>](lync-server-2013-enable-call-park-for-users.md)

  - [<span data-ttu-id="eac9f-115">Überprüfen der Normalisierungsregeln für das Parken von Anrufen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eac9f-115">Verify normalization rules for Call Park in Lync Server 2013</span></span>](lync-server-2013-verify-normalization-rules-for-call-park.md)

  - [<span data-ttu-id="eac9f-116">Optional Überprüfen der Bereitstellung des Anruf Parks in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eac9f-116">(Optional) Verify Call Park deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-call-park-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

