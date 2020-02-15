---
title: 'Lync Server 2013: Konfigurieren von Nummern für die Anrufannahme Gruppe'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure call pickup group numbers
ms:assetid: 5cc67f0b-d70d-446a-8db1-befda8671121
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945631(v=OCS.15)
ms:contentKeyID: 51541479
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 42023f82240e99695678bc25f1f38b7a20234d37
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028706"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-call-pickup-group-numbers-in-lync-server-2013"></a><span data-ttu-id="b8476-102">Konfigurieren von Nummern für die Anrufannahme Gruppe in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8476-102">Configure call pickup group numbers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b8476-103">_**Letztes Änderungsstand des Themas:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="b8476-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="b8476-104">Die gruppenanrufannahme basiert auf dem Anwendung zum Parken von anrufen.</span><span class="sxs-lookup"><span data-stu-id="b8476-104">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="b8476-105">Wenn Sie die gruppenanrufannahme bereitstellen, konfigurieren Sie die Orbit-Tabelle für das Parken von Anrufen mit Bereichen von Telefonnummern, die als Nummern für die Anrufannahme Gruppe festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="b8476-105">When you deploy Group Call Pickup, you configure the call park orbit table with ranges of phone numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="b8476-106">Bei diesen Gruppennummern handelt es sich um die Nummern, die Benutzer wählen, um Anrufe abzuholen, die für einen anderen Benutzer Klingeln.</span><span class="sxs-lookup"><span data-stu-id="b8476-106">These group numbers are the numbers that users dial to pick up calls that are ringing for another user.</span></span>

<span data-ttu-id="b8476-107">Wie die Umlaufbahn Nummern für die Anrufannahme müssen Gruppennummern für die Anrufannahme virtuelle Erweiterungen sein, denen kein Benutzer oder Telefon zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="b8476-107">Like call park orbit numbers, call pickup group numbers need to be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="b8476-108">Jede Front-End-Pool, in der Sie die gruppenanrufannahme bereitstellen, kann über einen oder mehrere Bereiche der Anrufannahme Gruppennummern verfügen.</span><span class="sxs-lookup"><span data-stu-id="b8476-108">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="b8476-109">Die Gruppennummern Bereiche müssen in der lync Server-Bereitstellung global eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="b8476-109">The group number ranges must be globally unique across the Lync Server deployment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b8476-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="b8476-110">In This Section</span></span>

[<span data-ttu-id="b8476-111">Erstellen oder Ändern eines Nummernbereichs für die gruppenanrufannahme in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8476-111">Create or modify a Group Call Pickup number range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-group-call-pickup-number-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

