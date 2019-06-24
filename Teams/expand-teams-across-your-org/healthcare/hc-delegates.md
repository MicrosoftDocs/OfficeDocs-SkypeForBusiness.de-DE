---
title: Nachrichten Delegierung
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.reviewer: acolonna
description: Ein Benutzer kann einen anderen Benutzer explizit als Stellvertretung in seiner Statusmeldung einrichten.
ms.openlocfilehash: 451577ce033f9a67bbc13ebbe2361083ab035e48
ms.sourcegitcommit: 66213b972920b4e09faf7d7e732c4bfe7b322ac4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/21/2019
ms.locfileid: "35131504"
---
# <a name="message-delegation"></a><span data-ttu-id="850e7-103">Nachrichten Delegierung</span><span class="sxs-lookup"><span data-stu-id="850e7-103">Message delegation</span></span>

<span data-ttu-id="850e7-104">Ein Benutzer kann seinen Status bereits explizit auf "Abwesend" oder "nicht stören" festlegen und benutzerdefinierten Text bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="850e7-104">A user can already explicitly set their status to Away or Do not Disturb, and provide custom text.</span></span> <span data-ttu-id="850e7-105">Das Feature Nachrichten Delegierung funktioniert wie folgt:</span><span class="sxs-lookup"><span data-stu-id="850e7-105">The message delegation feature works as follows:</span></span>

1. <span data-ttu-id="850e7-106">Ein Benutzer @username einen anderen Benutzer in einem Teil einer Text Statusnachricht erwähnt, was darauf hindeutet, dass Personen, die Sie kontaktieren möchten, sich stattdessen an den @username genannten Nutzer wenden können.</span><span class="sxs-lookup"><span data-stu-id="850e7-106">A user @username mentions another user in part of a text status message, suggesting that while they are unavailable people who want to contact them instead contact the @username mentioned user.</span></span>
2. <span data-ttu-id="850e7-107">Die Person, die als Stellvertretung zugewiesen wurde, wird benachrichtigt, dass Sie als Stellvertretung nominiert wurde.</span><span class="sxs-lookup"><span data-stu-id="850e7-107">The person who has been assigned as a delegate is notified that they were nominated to be a delegate.</span></span>
3. <span data-ttu-id="850e7-108">Eine Person, die versucht, sich mit dem ersten Benutzer in Verbindung zu setzen, kann dann mit dem Mauszeiger auf den nominierten Stellvertreter zeigen</span><span class="sxs-lookup"><span data-stu-id="850e7-108">Someone trying to contact the first user can then hover over the nominated delegate and easily message the delegate instead.</span></span>  

<span data-ttu-id="850e7-109">Hierbei handelt es sich um einen vom Benutzer initiierten Prozess im Client, und es ist keine Einbindung des Administrators erforderlich, um das Feature zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="850e7-109">This is a user-initiated process in the client, and no Admin involvement is required to enable the feature.</span></span> 

## <a name="delegation-use-scenario-in-healthcare"></a><span data-ttu-id="850e7-110">Szenario für die Delegierungs Nutzung in Healthcare</span><span class="sxs-lookup"><span data-stu-id="850e7-110">Delegation use scenario in Healthcare</span></span>

<span data-ttu-id="850e7-111">*Verwendungsbeispiel ohne Festlegen von Delegaten:*  Dr. Franco Piccio ist in der Radiologie-Abteilung auf Abruf.</span><span class="sxs-lookup"><span data-stu-id="850e7-111">*Usage example without setting delegates:*  Dr. Franco Piccio is on-call at the radiology department.</span></span> <span data-ttu-id="850e7-112">Er erhält einen dringenden persönlichen Anruf und muss für die nächsten paar Stunden fortfahren.</span><span class="sxs-lookup"><span data-stu-id="850e7-112">He receives an urgent personal call and has to step away for the next couple of hours.</span></span> <span data-ttu-id="850e7-113">Er bittet einen seiner Kollegen in der Radiologie-Abteilung, Dr. Lena Ehrle, ihn zu bedecken, während er verschwunden ist.</span><span class="sxs-lookup"><span data-stu-id="850e7-113">He asks one of his peers in the radiology department, Dr. Lena Ehrle, to cover for him while he is gone.</span></span> <span data-ttu-id="850e7-114">Er händigt seinen Pager an Dr. Ehrle aus, der auf dringende Nachrichten und Pings auf den Pager wartet und Ihnen im Namen von Dr. Piccio zusätzlich zu ihren derzeitigen Aufgaben antwortet.</span><span class="sxs-lookup"><span data-stu-id="850e7-114">He informally hands over his pager to Dr. Ehrle, who is listening for urgent messages and pings on the pager and responds to them on behalf of Dr. Piccio in addition to her current responsibilities.</span></span> <span data-ttu-id="850e7-115">Andere Personen im Team erkennen möglicherweise nicht, dass die informelle Delegation stattgefunden hat, und Verwirrung erfolgt mit der Fürsorge des Patienten.</span><span class="sxs-lookup"><span data-stu-id="850e7-115">Others on the team may not realize the informal delegation happened, and confusion ensues with a patient's care.</span></span>

<span data-ttu-id="850e7-116">*Verwendungsbeispiel mit Stellvertretungen:* Dr. Franco Piccio ist in der Radiologie-Abteilung auf Abruf.</span><span class="sxs-lookup"><span data-stu-id="850e7-116">*Usage example with setting delegates:* Dr. Franco Piccio is on-call at the radiology department.</span></span> <span data-ttu-id="850e7-117">Er erhält einen dringenden persönlichen Anruf und muss für die nächsten paar Stunden fortfahren.</span><span class="sxs-lookup"><span data-stu-id="850e7-117">He receives an urgent personal call and has to step away for the next couple of hours.</span></span> <span data-ttu-id="850e7-118">Er fragt einen seiner Kollegen in der Radiologie-Abteilung, Dr. Lena Ehrle, um ihn zu bedecken, während er Weg ist.</span><span class="sxs-lookup"><span data-stu-id="850e7-118">He asks one of his peers in the radiology department, Dr. Lena Ehrle to cover for him while he is gone.</span></span> <span data-ttu-id="850e7-119">Er ändert seine benutzerdefinierte Statusnachricht, um etwas ähnliches wie "Ich bin für die nächsten Stunden nicht verfügbar" zu sagen.</span><span class="sxs-lookup"><span data-stu-id="850e7-119">He changes his custom status message to say something similar to "I am unavailable for the next few hours.</span></span> <span data-ttu-id="850e7-120">Bitte wenden Sie sich für Notfälle an @DrEhrle. "</span><span class="sxs-lookup"><span data-stu-id="850e7-120">Please contact @DrEhrle for any emergencies."</span></span>  <span data-ttu-id="850e7-121">Andere im Team erkennen, dass die Delegation beim Versuch, Dr. Piccio zu kontaktieren, passiert ist, damit Sie jetzt wissen, dass Sie in der Zwischenzeit mit Dr. Ehrle Kontakt aufnehmen möchten.</span><span class="sxs-lookup"><span data-stu-id="850e7-121">Others on the team realize the delegation happened as they're attempting to contact Dr. Piccio, so they now know to contact Dr. Ehrle in the meantime.</span></span> <span data-ttu-id="850e7-122">Bei der Behandlung durch den Patienten entsteht kaum Verwirrung.</span><span class="sxs-lookup"><span data-stu-id="850e7-122">Little to no confusion ensues with a patient's care.</span></span>

## <a name="impact-of-co-existence-modes-on-user-status-in-the-teams-client"></a><span data-ttu-id="850e7-123">Auswirkungen der Koexistenzmodus auf den Benutzerstatus im Team-Client</span><span class="sxs-lookup"><span data-stu-id="850e7-123">Impact of co-existence modes on user status in the Teams client</span></span>

<span data-ttu-id="850e7-124">Administratoren sollten beachten, dass Statushinweise und das Verhalten der Delegierungs Erwähnung teilweise vom Koexistenzmodus des Benutzers abhängig sind.</span><span class="sxs-lookup"><span data-stu-id="850e7-124">Admins should be aware that status notes and delegation mention behaviors will depend partly on a user’s co-existence mode.</span></span> <span data-ttu-id="850e7-125">Diese Matrix zeigt die folgenden Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="850e7-125">This matrix shows the possibilities:</span></span>

|<span data-ttu-id="850e7-126">Koexistenzmodus</span><span class="sxs-lookup"><span data-stu-id="850e7-126">Co-Existence Mode</span></span> | <span data-ttu-id="850e7-127">Erwartetes Verhalten</span><span class="sxs-lookup"><span data-stu-id="850e7-127">Expected Behavior</span></span>|
|---|---|
|<span data-ttu-id="850e7-128">TeamsOnly</span><span class="sxs-lookup"><span data-stu-id="850e7-128">TeamsOnly</span></span> |<span data-ttu-id="850e7-129">Benutzer können eine Notiz nur von Teams aus einrichten.</span><span class="sxs-lookup"><span data-stu-id="850e7-129">Users can set a note only from Teams.</span></span> <br> <span data-ttu-id="850e7-130">Die Notizen des Benutzers für Teams sind in Teams #a0 SFB sichtbar.</span><span class="sxs-lookup"><span data-stu-id="850e7-130">User’s Teams note is visible in Teams & SfB.</span></span> |
|<span data-ttu-id="850e7-131">Inseln</span><span class="sxs-lookup"><span data-stu-id="850e7-131">Islands</span></span> | <span data-ttu-id="850e7-132">Die Notiz des Benutzers wird in Teams, die nur in Teams sichtbar sind, festgesetzt.</span><span class="sxs-lookup"><span data-stu-id="850e7-132">User’s note set in Teams visible only in Teams.</span></span> <br> <span data-ttu-id="850e7-133">Die Notizen des Benutzers, die in SFB festgesetzt sind, werden nur in SFB angezeigt</span><span class="sxs-lookup"><span data-stu-id="850e7-133">User’s note set in SfB visible only in SfB</span></span> |
|<span data-ttu-id="850e7-134">SFB \*-Modi</span><span class="sxs-lookup"><span data-stu-id="850e7-134">SfB\* modes</span></span> | <span data-ttu-id="850e7-135">Benutzer können eine Notiz nur in SFB einrichten.</span><span class="sxs-lookup"><span data-stu-id="850e7-135">Users can set a note only from SfB.</span></span> <br> <span data-ttu-id="850e7-136">Die SFB-Notiz des Benutzers ist in den SFB-#a0 Teams sichtbar.</span><span class="sxs-lookup"><span data-stu-id="850e7-136">User’s SfB note is visible in SfB & Teams.</span></span>  |
|||

<span data-ttu-id="850e7-137">Ein Benutzer kann in Teams nur dann eine Notiz setzen, wenn sein Modus TeamsOnly oder Islands ist.</span><span class="sxs-lookup"><span data-stu-id="850e7-137">A user can only set a note in Teams if their mode is TeamsOnly or Islands.</span></span>  

### <a name="displaying-notes-set-in-skype-for-business"></a><span data-ttu-id="850e7-138">Anzeigen von Notizen, die in Skype for Business festgesetzt sind</span><span class="sxs-lookup"><span data-stu-id="850e7-138">Displaying notes set in Skype for Business</span></span>
  
<span data-ttu-id="850e7-139">Es gibt keinen visuellen Hinweis darauf, dass eine Notiz in Skype for Business festgesetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="850e7-139">There is no visual indication that a note was set from Skype for Business.</span></span>

<span data-ttu-id="850e7-140">Skype for Business erzwingt keine Zeichenbeschränkung für Status Notizen.</span><span class="sxs-lookup"><span data-stu-id="850e7-140">Skype for Business doesn’t enforce a character limit on status notes.</span></span> <span data-ttu-id="850e7-141">In Microsoft Teams werden nur die ersten 280-Zeichen einer Notizen Gruppe in Skype for Business angezeigt.</span><span class="sxs-lookup"><span data-stu-id="850e7-141">Microsoft Teams will only display the first 280 characters of a note set from Skype for Business.</span></span> <span data-ttu-id="850e7-142">Eine Ellipse (...) am Ende einer Notiz zeigt die Kürzung an.</span><span class="sxs-lookup"><span data-stu-id="850e7-142">An ellipse (…) at the end of a note indicates truncation.</span></span>
  
<span data-ttu-id="850e7-143">Skype for Business unterstützt keine Ablaufzeiten für Notizen.</span><span class="sxs-lookup"><span data-stu-id="850e7-143">Skype for Business doesn’t support expiry times for notes.</span></span>

<span data-ttu-id="850e7-144">Die Migration von Notizen von Skype for Business zu Teams wird nicht unterstützt, wenn ein Benutzer auf den TeamsOnly-Modus aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="850e7-144">Migration of notes from Skype for Business to Teams is not supported when a user is upgraded to TeamsOnly mode.</span></span>

## <a name="related-topics"></a><span data-ttu-id="850e7-145">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="850e7-145">Related topics</span></span>

[<span data-ttu-id="850e7-146">Koexistenz mit Skype for Business</span><span class="sxs-lookup"><span data-stu-id="850e7-146">Coexistence with Skype for Business</span></span>](../../coexistence-chat-calls-presence.md)
