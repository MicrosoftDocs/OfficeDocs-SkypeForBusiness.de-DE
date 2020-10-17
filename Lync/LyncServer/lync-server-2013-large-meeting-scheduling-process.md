---
title: 'Lync Server 2013: Planungsprozess für große Besprechungen'
description: 'Lync Server 2013: Planungsprozess für große Besprechungen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Large-meeting scheduling process
ms:assetid: de267458-885f-4176-a8d7-1a218e67640e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205334(v=OCS.15)
ms:contentKeyID: 48185639
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96d383b6da96fb7d36e031485feac2ff927df347
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557591"
---
# <a name="large-meeting-scheduling-process-in-lync-server-2013"></a><span data-ttu-id="c4deb-103">Planungsprozess für große Besprechungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c4deb-103">Large-meeting scheduling process in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c4deb-104">_**Letztes Änderungsstand des Themas:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="c4deb-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="c4deb-105">Da jeweils nur eine große Besprechung im dedizierten großen Besprechungs Pool unterstützt wird, wird die Implementierung eines umfangreichen Besprechungs Planungsprozesses empfohlen, um große Besprechungs Konflikte zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="c4deb-105">Because only one large meeting at a time is supported on the dedicated large meeting pool, we recommend implementing a large meeting scheduling process to help prevent large meeting conflicts.</span></span> <span data-ttu-id="c4deb-106">Der Zweck dieses Planungsprozesses besteht darin, das Einrichten großer Besprechungen zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="c4deb-106">The purpose of such the scheduling process is to facilitate setting up large meetings.</span></span> <span data-ttu-id="c4deb-107">Diese Funktion wird nicht direkt von lync Server-oder lync Server-Clients bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="c4deb-107">Such capability is not provided directly by Lync Server or Lync Server clients.</span></span> <span data-ttu-id="c4deb-108">Eine Möglichkeit zum Implementieren eines solchen Prozesses besteht darin, das Ticket System des Support Teams Ihres Unternehmens zu verwenden, sofern verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c4deb-108">One way to implement such a process is to use your organization’s support team’s ticketing system, if available.</span></span>

<span data-ttu-id="c4deb-109">Für Organisatoren großer Besprechungen umfasst die Planung einer großen Besprechung die folgenden Schritte:</span><span class="sxs-lookup"><span data-stu-id="c4deb-109">For organizers of large meetings, scheduling a large meeting involves completing the following steps:</span></span>

1.  <span data-ttu-id="c4deb-110">Der Besprechungsorganisator oder die Stellvertretung bestimmt neben der Liste der Referenten die Zeit, die Dauer und die Größe einer bevorstehenden Besprechung.</span><span class="sxs-lookup"><span data-stu-id="c4deb-110">The meeting organizer or delegate determines the time, duration, and size of an upcoming meeting, in addition to the list of presenters.</span></span> <span data-ttu-id="c4deb-111">Wenn die erwartete Besprechungsgröße 250 Benutzer überschreitet oder die beste Benutzerfreundlichkeit für eine Besprechung mit weniger als 250 Benutzern sichergestellt wird, sendet der Organisator oder der Stellvertreter eine Anforderung für eine große Besprechung.</span><span class="sxs-lookup"><span data-stu-id="c4deb-111">If the anticipated meeting size exceeds 250 users or to ensure the best user experience for a meeting of fewer than 250 users, the organizer or the delegate submits a request for a large meeting.</span></span>

2.  <span data-ttu-id="c4deb-112">Die Mitarbeiter der Zeitplanung prüfen, ob das angeforderte Datum und die angeforderte Uhrzeit verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="c4deb-112">The scheduling staff checks to see whether the requested date and time is available.</span></span> <span data-ttu-id="c4deb-113">Da wir nur eine einzelne große Besprechung im dedizierten Pool gleichzeitig unterstützen, muss das Planungs Personal den großen Besprechungs Kalender überprüfen, um zu bestimmen, ob eine andere Besprechung für das angeforderte Datum und die angeforderte Uhrzeit geplant ist.</span><span class="sxs-lookup"><span data-stu-id="c4deb-113">Since we support only a single large meeting on the dedicated pool at a time, the scheduling staff needs to check the large-meeting calendar to determine whether there is another meeting scheduled for the requested date and time.</span></span> <span data-ttu-id="c4deb-114">Wenn die angeforderte Zeit zur Verfügung steht, genehmigt das Personal die Besprechungsanfrage.</span><span class="sxs-lookup"><span data-stu-id="c4deb-114">If the requested time is available, the staff approves the meeting request.</span></span>

3.  <span data-ttu-id="c4deb-115">Wenn die Anforderung genehmigt wird, verwendet das Planungs Personal (mithilfe von Anmeldeinformationen im dedizierten Pool) das Online Besprechungs-Add-in für lync 2013 mit Outlook, um eine Besprechung im dedizierten großen Besprechungs Pool einzurichten.</span><span class="sxs-lookup"><span data-stu-id="c4deb-115">If the request is approved, the scheduling staff (using credentials on the dedicated pool) uses Online Meeting Add-in for Lync 2013 with Outlook to set up a meeting on the dedicated large-meeting pool.</span></span> <span data-ttu-id="c4deb-116">Die URL, die für die Teilnahme an der Besprechung verwendet werden soll, wird dem anfordernden im Rahmen der Genehmigungsbenachrichtigung zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="c4deb-116">The URL to be used to join the meeting is provided to the requester as part of the approval notice.</span></span>

4.  <span data-ttu-id="c4deb-117">Der Besprechungsorganisator oder die Stellvertretung verwendet Outlook, um die bevorstehende Besprechung zu planen, wobei die URL für die Teilnahme an der Besprechung der Besprechungseinladung hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="c4deb-117">The meeting organizer or delegate uses Outlook to schedule the upcoming meeting, adding the URL for joining the meeting to the meeting invitation.</span></span> <span data-ttu-id="c4deb-118">Der Besprechungsorganisator oder die Stellvertretung gibt dann die Benutzer an, die eingeladen werden sollen, und sendet die Besprechungseinladung aus.</span><span class="sxs-lookup"><span data-stu-id="c4deb-118">The meeting organizer or delegate then specifies the users to be invited and sends out the meeting invitation.</span></span>
    
    <span data-ttu-id="c4deb-119">In der folgenden Abbildung wird ein typischer Anforderungs-und Genehmigungsworkflow zum Planen großer Besprechungen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="c4deb-119">The following figure illustrates a typical request and approval workflow for scheduling large meetings.</span></span>
    
    <span data-ttu-id="c4deb-120">![5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d](images/JJ205334.5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d(OCS.15).jpg "5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d")</span><span class="sxs-lookup"><span data-stu-id="c4deb-120">![5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d](images/JJ205334.5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d(OCS.15).jpg "5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d")</span></span>  

</div>

<span> </span>

</div>

</div>

</div>

