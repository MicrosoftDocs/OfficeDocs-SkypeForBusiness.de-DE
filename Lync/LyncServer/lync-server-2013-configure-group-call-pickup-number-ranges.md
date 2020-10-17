---
title: 'Lync Server 2013: Konfigurieren der Nummernbereiche für die gruppenanrufannahme'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Group Call Pickup number ranges
ms:assetid: f15f75f6-f965-4558-b612-f40cecdd5d8c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945657(v=OCS.15)
ms:contentKeyID: 51541529
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d63ec2dcd4190be810d6296ffdafe58759efb68
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507682"
---
# <a name="configure-group-call-pickup-number-ranges-in-lync-server-2013"></a><span data-ttu-id="7c56a-102">Konfigurieren von Gruppenanruf-Pickup-Nummernbereichen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c56a-102">Configure Group Call Pickup number ranges in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c56a-103">_**Letztes Änderungsstand des Themas:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="7c56a-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="7c56a-104">Die gruppenanrufannahme basiert auf dem Anwendung zum Parken von anrufen.</span><span class="sxs-lookup"><span data-stu-id="7c56a-104">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="7c56a-105">Wenn Sie die gruppenanrufannahme bereitstellen, konfigurieren Sie die Orbit-Tabelle für das Parken von Anrufen mit Bereichen von Telefonnummern, die als Nummern für die Anrufannahme Gruppe festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="7c56a-105">When you deploy Group Call Pickup, you configure the call park orbit table with ranges of phone numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="7c56a-106">Bei diesen Gruppennummern handelt es sich um die Nummern, die Benutzer wählen, um Anrufe abzuholen, die für einen anderen Benutzer Klingeln.</span><span class="sxs-lookup"><span data-stu-id="7c56a-106">These group numbers are the numbers that users dial to pick up calls that are ringing for another user.</span></span>

<span data-ttu-id="7c56a-107">Wie die Umlaufbahn Nummern für die Anrufannahme müssen Gruppennummern für die Anrufannahme virtuelle Erweiterungen sein, denen kein Benutzer oder Telefon zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="7c56a-107">Like call park orbit numbers, call pickup group numbers need to be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="7c56a-108">Jede Front-End-Pool, in der Sie die gruppenanrufannahme bereitstellen, kann über einen oder mehrere Bereiche der Anrufannahme Gruppennummern verfügen.</span><span class="sxs-lookup"><span data-stu-id="7c56a-108">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="7c56a-109">Die Gruppennummern Bereiche müssen in der lync Server-Bereitstellung global eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="7c56a-109">The group number ranges must be globally unique across the Lync Server deployment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7c56a-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="7c56a-110">In This Section</span></span>

  - [<span data-ttu-id="7c56a-111">Erstellen oder Ändern eines Nummernbereichs für die gruppenanrufannahme in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c56a-111">Create or modify a Group Call Pickup number range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-group-call-pickup-number-range.md)

  - [<span data-ttu-id="7c56a-112">Löschen eines Gruppenanruf-Pickup-Nummernbereichs in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c56a-112">Delete a Group Call Pickup number range in Lync Server 2013</span></span>](lync-server-2013-delete-a-group-call-pickup-number-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

