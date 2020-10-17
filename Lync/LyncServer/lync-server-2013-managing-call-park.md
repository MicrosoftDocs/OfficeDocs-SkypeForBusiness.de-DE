---
title: 'Lync Server 2013: Parken von Anrufen'
description: 'Lync Server 2013: Verwalten des Anruf Parks.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Call Park
ms:assetid: 9554cdf6-8e7c-48c8-94dd-f28e2befefdc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688140(v=OCS.15)
ms:contentKeyID: 49733740
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6540cc6d4df06b3eaadd78dce8fe01990928045a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569161"
---
# <a name="managing-call-park-in-lync-server-2013"></a><span data-ttu-id="2b9e1-103">Verwalten des Parkens von Anrufen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b9e1-103">Managing Call Park in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b9e1-104">_**Letztes Änderungsstand des Themas:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="2b9e1-104">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="2b9e1-105">Mit dem Anwendung zum Parken von anrufen kann ein Enterprise-VoIP-Benutzer einen Anruf an einem Telefon halten und den Anruf später von einem beliebigen Telefon aus abrufen.</span><span class="sxs-lookup"><span data-stu-id="2b9e1-105">The Call Park application enables an Enterprise Voice user to put a call on hold from one telephone and then retrieve the call later from any telephone.</span></span> <span data-ttu-id="2b9e1-106">Wenn der Benutzer einen Anruf parkt, übergibt lync Server den Anruf an eine temporäre Nummer, die als *Orbit*bezeichnet wird, wobei der Anruf angehalten wird, bis er von einem Benutzer abgerufen wird oder ein Timeout auftritt.</span><span class="sxs-lookup"><span data-stu-id="2b9e1-106">When the user parks a call, Lync Server transfers the call to a temporary number, called an *orbit*, where the call is held until someone retrieves it or it times out.</span></span>

<span data-ttu-id="2b9e1-107">Die Themen in diesem Abschnitt bieten schrittweise Anleitungen für Aufgaben, die Sie ausführen können, um die Anwendung zum Parken von Anrufen in Ihrer Bereitstellung anzupassen und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="2b9e1-107">Topics in this section provide step-by-step procedures for tasks that you can perform to customize and maintain the Call Park application in your deployment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2b9e1-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="2b9e1-108">In This Section</span></span>

  - [<span data-ttu-id="2b9e1-109">Konfigurieren von Durchwahlnummern für das Parken von Anrufen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b9e1-109">Configure phone number extensions for parking calls in Lync Server 2013</span></span>](lync-server-2013-configure-phone-number-extensions-for-parking-calls.md)

  - [<span data-ttu-id="2b9e1-110">Konfigurieren von Einstellungen für das Parken von Anrufen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b9e1-110">Configure Call Park settings in Lync Server 2013</span></span>](lync-server-2013-configure-call-park-settings.md)

  - [<span data-ttu-id="2b9e1-111">Anpassen der Wartemusik für das Parken von Anrufen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b9e1-111">Customize Call Park music on hold in Lync Server 2013</span></span>](lync-server-2013-customize-call-park-music-on-hold.md)

  - [<span data-ttu-id="2b9e1-112">Verwalten des Anruf Parks während der Notfallwiederherstellung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b9e1-112">Manage Call Park during disaster recovery in Lync Server 2013</span></span>](lync-server-2013-manage-call-park-during-disaster-recovery.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

