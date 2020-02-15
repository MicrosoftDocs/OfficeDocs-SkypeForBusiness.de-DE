---
title: 'Lync Server 2013: Planungsprozess für große Besprechungen'
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
ms.openlocfilehash: 3ccbe1735d92d510f4e5016cc2e52b62e1c82bb7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034977"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="large-meeting-scheduling-process-in-lync-server-2013"></a><span data-ttu-id="d108b-102">Planungsprozess für große Besprechungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d108b-102">Large-meeting scheduling process in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d108b-103">_**Letztes Änderungsstand des Themas:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="d108b-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="d108b-104">Da jeweils nur eine große Besprechung im dedizierten großen Besprechungs Pool unterstützt wird, wird die Implementierung eines umfangreichen Besprechungs Planungsprozesses empfohlen, um große Besprechungs Konflikte zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="d108b-104">Because only one large meeting at a time is supported on the dedicated large meeting pool, we recommend implementing a large meeting scheduling process to help prevent large meeting conflicts.</span></span> <span data-ttu-id="d108b-105">Der Zweck dieses Planungsprozesses besteht darin, das Einrichten großer Besprechungen zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="d108b-105">The purpose of such the scheduling process is to facilitate setting up large meetings.</span></span> <span data-ttu-id="d108b-106">Diese Funktion wird nicht direkt von lync Server-oder lync Server-Clients bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="d108b-106">Such capability is not provided directly by Lync Server or Lync Server clients.</span></span> <span data-ttu-id="d108b-107">Eine Möglichkeit zum Implementieren eines solchen Prozesses besteht darin, das Ticket System des Support Teams Ihres Unternehmens zu verwenden, sofern verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d108b-107">One way to implement such a process is to use your organization’s support team’s ticketing system, if available.</span></span>

<span data-ttu-id="d108b-108">Für Organisatoren großer Besprechungen umfasst die Planung einer großen Besprechung die folgenden Schritte:</span><span class="sxs-lookup"><span data-stu-id="d108b-108">For organizers of large meetings, scheduling a large meeting involves completing the following steps:</span></span>

1.  <span data-ttu-id="d108b-109">Der Besprechungsorganisator oder die Stellvertretung bestimmt neben der Liste der Referenten die Zeit, die Dauer und die Größe einer bevorstehenden Besprechung.</span><span class="sxs-lookup"><span data-stu-id="d108b-109">The meeting organizer or delegate determines the time, duration, and size of an upcoming meeting, in addition to the list of presenters.</span></span> <span data-ttu-id="d108b-110">Wenn die erwartete Besprechungsgröße 250 Benutzer überschreitet oder die beste Benutzerfreundlichkeit für eine Besprechung mit weniger als 250 Benutzern sichergestellt wird, sendet der Organisator oder der Stellvertreter eine Anforderung für eine große Besprechung.</span><span class="sxs-lookup"><span data-stu-id="d108b-110">If the anticipated meeting size exceeds 250 users or to ensure the best user experience for a meeting of fewer than 250 users, the organizer or the delegate submits a request for a large meeting.</span></span>

2.  <span data-ttu-id="d108b-111">Die Mitarbeiter der Zeitplanung prüfen, ob das angeforderte Datum und die angeforderte Uhrzeit verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="d108b-111">The scheduling staff checks to see whether the requested date and time is available.</span></span> <span data-ttu-id="d108b-112">Da wir nur eine einzelne große Besprechung im dedizierten Pool gleichzeitig unterstützen, muss das Planungs Personal den großen Besprechungs Kalender überprüfen, um zu bestimmen, ob eine andere Besprechung für das angeforderte Datum und die angeforderte Uhrzeit geplant ist.</span><span class="sxs-lookup"><span data-stu-id="d108b-112">Since we support only a single large meeting on the dedicated pool at a time, the scheduling staff needs to check the large-meeting calendar to determine whether there is another meeting scheduled for the requested date and time.</span></span> <span data-ttu-id="d108b-113">Wenn die angeforderte Zeit zur Verfügung steht, genehmigt das Personal die Besprechungsanfrage.</span><span class="sxs-lookup"><span data-stu-id="d108b-113">If the requested time is available, the staff approves the meeting request.</span></span>

3.  <span data-ttu-id="d108b-114">Wenn die Anforderung genehmigt wird, verwendet das Planungs Personal (mithilfe von Anmeldeinformationen im dedizierten Pool) das Online Besprechungs-Add-in für lync 2013 mit Outlook, um eine Besprechung im dedizierten großen Besprechungs Pool einzurichten.</span><span class="sxs-lookup"><span data-stu-id="d108b-114">If the request is approved, the scheduling staff (using credentials on the dedicated pool) uses Online Meeting Add-in for Lync 2013 with Outlook to set up a meeting on the dedicated large-meeting pool.</span></span> <span data-ttu-id="d108b-115">Die URL, die für die Teilnahme an der Besprechung verwendet werden soll, wird dem anfordernden im Rahmen der Genehmigungsbenachrichtigung zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="d108b-115">The URL to be used to join the meeting is provided to the requester as part of the approval notice.</span></span>

4.  <span data-ttu-id="d108b-116">Der Besprechungsorganisator oder die Stellvertretung verwendet Outlook, um die bevorstehende Besprechung zu planen, wobei die URL für die Teilnahme an der Besprechung der Besprechungseinladung hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="d108b-116">The meeting organizer or delegate uses Outlook to schedule the upcoming meeting, adding the URL for joining the meeting to the meeting invitation.</span></span> <span data-ttu-id="d108b-117">Der Besprechungsorganisator oder die Stellvertretung gibt dann die Benutzer an, die eingeladen werden sollen, und sendet die Besprechungseinladung aus.</span><span class="sxs-lookup"><span data-stu-id="d108b-117">The meeting organizer or delegate then specifies the users to be invited and sends out the meeting invitation.</span></span>
    
    <span data-ttu-id="d108b-118">In der folgenden Abbildung wird ein typischer Anforderungs-und Genehmigungsworkflow zum Planen großer Besprechungen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="d108b-118">The following figure illustrates a typical request and approval workflow for scheduling large meetings.</span></span>
    
    <span data-ttu-id="d108b-119">![5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d](images/JJ205334.5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d(OCS.15).jpg "5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d")</span><span class="sxs-lookup"><span data-stu-id="d108b-119">![5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d](images/JJ205334.5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d(OCS.15).jpg "5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d")</span></span>  

</div>

<span> </span>

</div>

</div>

</div>

