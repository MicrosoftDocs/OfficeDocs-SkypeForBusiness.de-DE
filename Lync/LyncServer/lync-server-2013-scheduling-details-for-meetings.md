---
title: 'Lync Server 2013: Planen von Details für Besprechungen'
description: 'Lync Server 2013: Planen von Details für Besprechungen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scheduling details
ms:assetid: 39ca6fff-2c15-4347-9f1f-6c8687a39a49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204823(v=OCS.15)
ms:contentKeyID: 48183910
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef7a6907aedbc880731b3fb474c9294c1c111b80
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561981"
---
# <a name="scheduling-details-for-meetings-in-lync-server-2013"></a><span data-ttu-id="c05cc-103">Planungsdetails für Besprechungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c05cc-103">Scheduling details for meetings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c05cc-104">_**Letztes Änderungsstand des Themas:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="c05cc-104">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="c05cc-105">Nachdem Sie überprüft haben, um sicherzustellen, dass keine andere Besprechung zum gewünschten Zeitpunkt geplant ist, plant der große Besprechungs Mitarbeiter, der die Anforderung verarbeitet, die Besprechung im großen Besprechungs Pool.</span><span class="sxs-lookup"><span data-stu-id="c05cc-105">After checking to ensure that no other meeting is scheduled at the requested time, the large meeting support staff that handles the request schedules the meeting on the large-meeting pool.</span></span> <span data-ttu-id="c05cc-106">Verwenden Sie das Online-Besprechungs-Add-in für lync, das mit dem lync Server 2013-Client installiert ist, um diese Aufgabe auszuführen, wobei die Anmeldeinformationen eines Benutzers verwendet werden, der für lync Server im dedizierten großen Besprechungs Pool aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="c05cc-106">Use the Online Meeting Add-in for Lync that is installed with the Lync Server 2013 client to perform this task, using the credentials of a user enabled for Lync Server in the dedicated large-meeting pool.</span></span>

<span data-ttu-id="c05cc-107">Um die bestmögliche Benutzerfreundlichkeit zu erzielen, ist es wichtig, die große Besprechung mit den richtigen Zugriffsebenen und Besprechungseinstellungen zu planen, die den Bedürfnissen des Besprechungsorganisators entsprechen.</span><span class="sxs-lookup"><span data-stu-id="c05cc-107">To ensure the best user experience, it is important to schedule the large meeting with the right access levels and meeting settings that are appropriate to the meeting organizer’s needs.</span></span> <span data-ttu-id="c05cc-108">Wir empfehlen die folgenden Planungseinstellungen, die in lync-Besprechungsoptionen konfiguriert sind:</span><span class="sxs-lookup"><span data-stu-id="c05cc-108">We recommend the following scheduling settings configured in Lync Meeting options:</span></span>

  - <span data-ttu-id="c05cc-109">Verwenden Sie einen neuen Besprechungsraum für jede große Besprechung, anstatt den dedizierten Besprechungsraum erneut zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="c05cc-109">Use a new meeting space for each large meeting instead of reusing the dedicated meeting space.</span></span>

  - <span data-ttu-id="c05cc-110">Geben Sie die Zugriffsebene für die Besprechung wie folgt an:</span><span class="sxs-lookup"><span data-stu-id="c05cc-110">Specify the meeting access level as follows:</span></span>
    
      - <span data-ttu-id="c05cc-p103">Wenn mindestens ein eingeladener Benutzer nicht zur Organisation gehört, legen Sie den Zugriffstyp für die Besprechung auf **Alle Personen (keine Einschränkungen)** fest. Dadurch vermeiden Sie, dass sie während der laufenden Besprechung einen möglicherweise großen Wartebereich verwalten müssen.</span><span class="sxs-lookup"><span data-stu-id="c05cc-p103">If at least one invitee is external to the organization, set the meeting access type to **Anyone (no restrictions**. This enables you to avoid having to manage a potentially large lobby when the meeting is in progress.</span></span>
    
      - <span data-ttu-id="c05cc-113">Wenn die Besprechung nur intern ist, legen Sie den Zugriffstyp für die Besprechung auf **Jeder innerhalb meiner Organisation** fest.</span><span class="sxs-lookup"><span data-stu-id="c05cc-113">If the meeting is an internal-only meeting, set the meeting access type to **Anyone from my organization**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="c05cc-114">Vermeiden Sie es, den Zugriffstyp für die Besprechung auf <STRONG>Von mir eingeladene Personen in meinem Unternehmen</STRONG> festzulegen. Wenn Sie diese Einstellung verwenden, müssen Besprechungsorganisatoren die E-Mail-Adressen aller Benutzer zur Eingeladenenliste hinzufügen, und Sie können keine Verteilergruppe einladen.</span><span class="sxs-lookup"><span data-stu-id="c05cc-114">Avoid setting the meeting access type to <STRONG>People I invite from my company</STRONG> because when you use this setting, organizers must add all user email addresses to the invitee list and you cannot invite a distribution group.</span></span><BR><span data-ttu-id="c05cc-p104">Vermeiden Sie es, den Zugriffstyp für die Besprechung auf <STRONG>Nur ich, der Besprechungsorganisator</STRONG> festzulegen, da diese Einstellung erfordert, dass jeder Besprechungsteilnehmer, auch die Referenten, zur Laufzeit der Besprechung zum Wartebereich hinzugefügt werden muss. Der Verantwortliche für die Durchführung der großen Besprechung muss dann ständig die Wartebereichsliste überwachen und neue Benutzer im Wartebereich zur Besprechung zulassen.</span><span class="sxs-lookup"><span data-stu-id="c05cc-p104">Avoid setting the meeting access type to <STRONG>Only me, the meeting organizer</STRONG> because this setting requires that every meeting participant, including presenters, must be put in the lobby at meeting run time. The person responsible for running the large meeting must then constantly monitor the lobby roster and admit new users who are in the lobby.</span></span>

        
        </div>

  - <span data-ttu-id="c05cc-117">Wenn Sie die Option **Anrufer erhalten direkten Zugang** aktivieren, können Benutzer, die sich per Telefon einwählen, automatisch der Besprechung beitreten.</span><span class="sxs-lookup"><span data-stu-id="c05cc-117">Allow users who dial-in from phones to enter the meeting automatically by checking the **Callers get in directly** setting.</span></span>

  - <span data-ttu-id="c05cc-118">Laden Sie folgende Benutzer explizit ein:</span><span class="sxs-lookup"><span data-stu-id="c05cc-118">Explicitly invite the following users:</span></span>
    
      - <span data-ttu-id="c05cc-119">Besprechungsorganisator und Delegat (anfordernde Person)</span><span class="sxs-lookup"><span data-stu-id="c05cc-119">Meeting organizer and delegate (requester)</span></span>
    
      - <span data-ttu-id="c05cc-120">Die von der eine Besprechung anfordernden Person vorgelegte Liste mit Referenten</span><span class="sxs-lookup"><span data-stu-id="c05cc-120">The list of presenters provided by a meeting requester</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c05cc-121">Wenn der Zugriffstyp der Besprechung auf <STRONG>Von mir ausgewählte Personen</STRONG> festgelegt ist, müssen Sie jeden Teilnehmer einer großen Besprechung explizit als eingeladenen Benutzer hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="c05cc-121">If the meeting access type is set to <STRONG>People I choose</STRONG>, you need to explicitly add each participant of a large meeting as an invitee of the meeting.</span></span>

    
    </div>

  - <span data-ttu-id="c05cc-p105">Verwalten Sie die Referenten explizit, anstatt die Referenten-Option auf einen der Werte für automatische Hochstufung festzulegen. Stellen Sie sicher, dass folgende Benutzer als Referenten hinzugefügt werden:</span><span class="sxs-lookup"><span data-stu-id="c05cc-p105">Explicitly manage presenters, instead of setting the presenter option to one of the auto-promote values. Be sure to add the following users as presenters:</span></span>
    
      - <span data-ttu-id="c05cc-124">Besprechungsorganisator und Delegat (anfordernde Person)</span><span class="sxs-lookup"><span data-stu-id="c05cc-124">Meeting organizer and delegate (requester)</span></span>
    
      - <span data-ttu-id="c05cc-125">Die von eine große Besprechung anfordernden Personen vorgelegte Liste mit Referenten</span><span class="sxs-lookup"><span data-stu-id="c05cc-125">The list of presenters provided by large meeting requesters</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c05cc-p106">Indem Sie die Referenten explizit verwalten, können Sie ihre Anzahl steuern und auf eine so kleine Zahl begrenzen, dass eine effektive große Besprechung möglich ist. Wenn die Mehrheit der Besprechungsteilnehmer nur eine Teilnehmerrolle hat, verringert sich die Wahrscheinlichkeit, dass Personen versehentlich die Steuerung der Präsentation übernehmen, eine PowerPoint-Präsentation löschen, Referenten stummschalten bzw. die Stummschaltung aufheben oder die Besprechung auf andere Weise stören.</span><span class="sxs-lookup"><span data-stu-id="c05cc-p106">By explicitly managing presenters, you can control the number of presenters, so that you can limit presenters to a small enough number to make it possible to have an effective large meeting. If the majority of meeting participants have the attendee role, it helps reduce the chance of people accidentally taking control of the presentation, deleting a PowerPoint presentation, muting/unmuting presenters, and other disruptions to the meeting.</span></span>

    
    </div>

  - <span data-ttu-id="c05cc-128">Aktivieren Sie die Option **Alle Teilnehmer stummschalten**, um sicherzustellen, dass nur Referenten Audioinhalte in die Besprechung übertragen können.</span><span class="sxs-lookup"><span data-stu-id="c05cc-128">Check the **Mute all attendees** setting to make sure that only presenters can broadcast audio into the meeting.</span></span>

  - <span data-ttu-id="c05cc-129">Aktivieren Sie die Option **Video von Teilnehmern blockieren**, um sicherzustellen, dass nur Referenten Videoinhalte in die Besprechung übertragen können.</span><span class="sxs-lookup"><span data-stu-id="c05cc-129">Check the **Block attendees’ video** setting to make sure only presenters can broadcast video into the meeting.</span></span>

<span data-ttu-id="c05cc-130">In der folgenden Abbildung sind die empfohlenen Einstellungen für das Online-Besprechungs-Add-in für lync dargestellt.</span><span class="sxs-lookup"><span data-stu-id="c05cc-130">The following figure shows the recommended settings for the Online Meeting Add-in for Lync.</span></span>

<span data-ttu-id="c05cc-131">![54e4e70d-06b0-45cd-8d94-bab649cd5dc0](images/JJ204823.54e4e70d-06b0-45cd-8d94-bab649cd5dc0(OCS.15).jpg "54e4e70d-06b0-45cd-8d94-bab649cd5dc0")</span><span class="sxs-lookup"><span data-stu-id="c05cc-131">![54e4e70d-06b0-45cd-8d94-bab649cd5dc0](images/JJ204823.54e4e70d-06b0-45cd-8d94-bab649cd5dc0(OCS.15).jpg "54e4e70d-06b0-45cd-8d94-bab649cd5dc0")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

