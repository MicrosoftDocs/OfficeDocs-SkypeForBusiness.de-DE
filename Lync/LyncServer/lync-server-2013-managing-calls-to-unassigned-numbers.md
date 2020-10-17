---
title: 'Lync Server 2013: Verwalten von Anrufen an nicht zugewiesene Nummern'
description: 'Lync Server 2013: Verwalten von Anrufen an nicht zugewiesene Nummern.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing calls to unassigned numbers
ms:assetid: a45a7546-5ee6-4c1e-ab13-20a71a058f80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688167(v=OCS.15)
ms:contentKeyID: 49733772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a91c1ec30ea1e942fa3ea27fbcd369572884a52a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569151"
---
# <a name="managing-calls-to-unassigned-numbers-in-lync-server-2013"></a><span data-ttu-id="865a6-103">Verwalten von Anrufen an nicht zugewiesene Nummern in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="865a6-103">Managing calls to unassigned numbers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="865a6-104">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="865a6-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="865a6-105">In lync Server können Sie die Verarbeitung eingehender Anrufe konfigurieren, wenn die gewählte Nummer für Ihre Organisation gültig ist, aber keinem Benutzer oder Telefon zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="865a6-105">Lync Server lets you configure the handling of incoming phone calls when the dialed number is valid for your organization, but is not assigned to a user or phone.</span></span> <span data-ttu-id="865a6-106">Sie können die Ankündigungsanwendung verwenden, um diese Anrufe an ein vorab festgelegtes Ziel (Telefonnummer, SIP-URI oder Voicemail) zu übertragen oder eine Audioansage oder beides wiederzugeben.</span><span class="sxs-lookup"><span data-stu-id="865a6-106">You can use the Announcement application to transfer these calls to a predetermined destination (phone number, SIP URI, or voice mail), or play an audio announcement, or both.</span></span> <span data-ttu-id="865a6-107">Sie können diese Anrufe auch an eine Exchange UM-Rufnummer der automatischen Telefonzentrale durchstellen.</span><span class="sxs-lookup"><span data-stu-id="865a6-107">You can also transfer these calls to an Exchange UM Auto Attendant phone number.</span></span> <span data-ttu-id="865a6-108">Durch die Verarbeitung von Anrufen für nicht zugewiesene Nummern anhand einer dieser Methoden können Sie die Situationen vermeiden, in denen sich ein Anrufer verwählt und dann ein Besetztzeichen hört oder in denen der SIP-Client eine Fehlermeldung erhält.</span><span class="sxs-lookup"><span data-stu-id="865a6-108">Handling calls to unassigned numbers in one of these ways helps you avoid the situations in which a caller misdials and then hears a busy tone, or the SIP client receives an error message.</span></span>

<span data-ttu-id="865a6-p102">In diesem Abschnitt wird die Verwaltung von Bereichen nicht zugewiesener Nummern für die Vearbeitung von Anrufen für nicht zugewiesene Telefonnummern beschrieben. Zudem wird in diesem Abschnitt die Verwaltung von Ansagen bei Notfallwiederherstellungen beschrieben, sofern Sie diese Funktionalität während eines Ausfalls verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="865a6-p102">This section describes how to manage unassigned number ranges to handle calls to unassigned phone numbers. The section also describes how to manage Announcements during disaster recovery if you want this functionality during an outage.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="865a6-111">Die Verwendung der Verarbeitung nicht zugewiesener Nummern während eines Ausfalls ist optional.</span><span class="sxs-lookup"><span data-stu-id="865a6-111">Using unassigned number handling during an outage is optional.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="865a6-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="865a6-112">In This Section</span></span>

  - [<span data-ttu-id="865a6-113">Erstellen einer Ansage in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="865a6-113">Create an announcement in Lync Server 2013</span></span>](lync-server-2013-create-an-announcement.md)

  - [<span data-ttu-id="865a6-114">Konfigurieren von nicht zugewiesenen Telefonnummern in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="865a6-114">Configure unassigned phone numbers in Lync Server 2013</span></span>](lync-server-2013-configure-unassigned-phone-numbers.md)

  - [<span data-ttu-id="865a6-115">Verwalten von Ankündigungen während der Notfallwiederherstellung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="865a6-115">Manage announcements during disaster recovery in Lync Server 2013</span></span>](lync-server-2013-manage-announcements-during-disaster-recovery.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

