---
title: 'Lync Server 2013: Verwenden von Anrufen bei mit einem lync-fähigen Telefon'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Call Me At with a Lync-enabled phone
ms:assetid: 975a1df8-a159-4aa4-a991-5972a535998e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn383570(v=OCS.15)
ms:contentKeyID: 56470326
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc89ac5038d367a57b791546c287e515bfd3c7bf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847351"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-call-me-at-with-a-lync-enabled-phone-and-lync-server-2013"></a><span data-ttu-id="ed0e7-102">Verwenden von "rufen Sie mich an" mit einem lync-fähigen Telefon und lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed0e7-102">Using Call Me At with a Lync-enabled phone and Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed0e7-103">_**Letztes Änderungsdatum des Themas:** 2013-08-09_</span><span class="sxs-lookup"><span data-stu-id="ed0e7-103">_**Topic Last Modified:** 2013-08-09_</span></span>

<span data-ttu-id="ed0e7-104">Das Feature "mich anrufen" in lync bietet Benutzern eine Möglichkeit, mit einem Mobiltelefon, "Festnetz" oder einem anderen Gerät, das mit dem öffentlichen Telefonnetz (PSTN) verbunden ist, dem Audioteil einer Konferenz beizutreten.</span><span class="sxs-lookup"><span data-stu-id="ed0e7-104">The Call Me At feature in Lync provides a way for users to join the audio portion of a conference by using a cell phone, “land line,” or other device connected to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="ed0e7-105">Wenn Sie versuchen, mithilfe von lync an einer Besprechung teilzunehmen, wird normalerweise das Dialogfeld **an Besprechungs-Audio teilnehmen** angezeigt:</span><span class="sxs-lookup"><span data-stu-id="ed0e7-105">When you attempt to join a meeting by using Lync, you will typically be presented with the **Join Meeting Audio** dialog box:</span></span>

<span data-ttu-id="ed0e7-106">![Verwenden von lync zum teilnehmen an der Besprechung] des Audiofensters (images/Dn383570.e28f17f0-9f17-44ef-b893-f4ef132f47ac(OCS.15).png "Verwenden von lync zum teilnehmen an der Besprechung") des Audiofensters</span><span class="sxs-lookup"><span data-stu-id="ed0e7-106">![Use Lync to join meeting audio window screenshot](images/Dn383570.e28f17f0-9f17-44ef-b893-f4ef132f47ac(OCS.15).png "Use Lync to join meeting audio window screenshot")</span></span>

<span data-ttu-id="ed0e7-107">Wenn Sie **mich anrufen**, können Sie eine Telefonnummer aus der Dropdown-Liste auswählen.</span><span class="sxs-lookup"><span data-stu-id="ed0e7-107">If you select **Call me at**, you can then pick a phone number from the dropdown list.</span></span> <span data-ttu-id="ed0e7-108">Lync Server 2013 führt einen Telefonanruf an die ausgewählte Nummer, und Sie können dann das Telefon verwenden, um am Audioteil der Konferenz teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="ed0e7-108">Lync Server 2013 will place a phone call to the selected number, and you can then use that phone to participate in the audio portion of the conference.</span></span>

<span data-ttu-id="ed0e7-109">Die Dropdownliste wird mit den Telefonnummern (für Mobiltelefone, privat Telefone oder andere Telefone) gefüllt, die Sie im Dialogfeld **lync – Optionen** auf der Registerkarte **Telefone** eingegeben haben:</span><span class="sxs-lookup"><span data-stu-id="ed0e7-109">The dropdown list is populated by the phone numbers (for mobile phone, home phone, or other phone) that you have entered on the **Phones** tab in the **Lync – Options** dialog box:</span></span>

<span data-ttu-id="ed0e7-110">![Screenshot der Option "lync-Telefone einrichten] " (images/Dn383570.03d2f25d-49e2-47b4-b1e9-b1614fc0c11c(OCS.15).png "Screenshot der Option \"lync-Telefone einrichten") "</span><span class="sxs-lookup"><span data-stu-id="ed0e7-110">![Lync Phones set up options screenshot](images/Dn383570.03d2f25d-49e2-47b4-b1e9-b1614fc0c11c(OCS.15).png "Lync Phones set up options screenshot")</span></span>

<span data-ttu-id="ed0e7-111">Wenn Sie keine Telefonnummern auf dem Reiter " **Telefone** " eingegeben haben, stehen Ihnen im Dropdown-Feld keine Nummern zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="ed0e7-111">If you have not entered any phone numbers on the **Phones** tab then you will not have any numbers available in the dropdown box.</span></span> <span data-ttu-id="ed0e7-112">Sie können jedoch jederzeit auf **neue Rufnummer** klicken und lync Server an eine beliebige Telefonnummer anwählen, die Sie wünschen:</span><span class="sxs-lookup"><span data-stu-id="ed0e7-112">However, you can always click **New Number** and have Lync Server dial out to any phone number you wish:</span></span>

<span data-ttu-id="ed0e7-113">![Screenshot des lync-Dialogfensters "an Besprechung teilnehmen"] (images/Dn383570.27f2ac7a-cc1c-465c-b145-202ad03af4f2(OCS.15).png "Screenshot des lync-Dialogfensters \"an Besprechung teilnehmen\"")</span><span class="sxs-lookup"><span data-stu-id="ed0e7-113">![Lync join meeting audio call me window screenshot](images/Dn383570.27f2ac7a-cc1c-465c-b145-202ad03af4f2(OCS.15).png "Lync join meeting audio call me window screenshot")</span></span>

<span data-ttu-id="ed0e7-114">Das Feature "mich anrufen" funktioniert hervorragend, vorausgesetzt, dass Sie es in der beabsichtigten Weise verwenden: Wenn lync Server eine PSTN-Telefonnummer anruft.</span><span class="sxs-lookup"><span data-stu-id="ed0e7-114">The Call Me At feature works extremely well provided that you use it in the way it was intended: by having Lync Server call a PSTN phone number.</span></span> <span data-ttu-id="ed0e7-115">Sie können jedoch eine weniger optimale Nutzung erreichen, wenn Sie von lync Server aufgefordert werden, Sie an einem lync-fähigen Endpunkt anzurufen (beispielsweise ein Telefon in einem Konferenzraum).</span><span class="sxs-lookup"><span data-stu-id="ed0e7-115">However, you can run into a less-than-optimal experience if you ask Lync Server to call you at a Lync-enabled endpoint (for example, a phone in a conference room).</span></span> <span data-ttu-id="ed0e7-116">Im folgenden finden Sie das Problem, auf das Sie möglicherweise stoßen, und zwei Möglichkeiten, um das Problem zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="ed0e7-116">Following is the issue you might run into, as well as two ways to work around the problem.</span></span>

<span data-ttu-id="ed0e7-117">Um zu beginnen, gehen Sie wie folgt vor, wenn Sie das Feature "anrufen unter" mit der Telefonnummer eines lync-fähigen Telefons angeben.</span><span class="sxs-lookup"><span data-stu-id="ed0e7-117">To begin, here’s what happens when you provide the Call Me At feature with the phone number of a Lync-enabled phone.</span></span> <span data-ttu-id="ed0e7-118">Angenommen, Ken Myers versucht, an einer Besprechung teilzunehmen, indem lync Server ihn bei 1-206-555-1219, einer lync Server-fähigen Telefonnummer, anruft.</span><span class="sxs-lookup"><span data-stu-id="ed0e7-118">Suppose Ken Myer tries to join a meeting by having Lync Server call him at 1-206-555-1219, a Lync Server-enabled phone number.</span></span> <span data-ttu-id="ed0e7-119">Ken wird zunächst mit der Besprechung verbunden sein, aber nach ein paar Sekunden zeigt lync an, dass der Nachrichten **Anruf nicht abgeschlossen oder beendet**wurde, und Ken wird anscheinend aus der Besprechung gestrichen:</span><span class="sxs-lookup"><span data-stu-id="ed0e7-119">Ken will initially be connected to the meeting, but after a few seconds Lync will display the message **Call was not completed or has ended**, and Ken will appear to have been dropped from the meeting:</span></span>

<span data-ttu-id="ed0e7-120">Screenshot ![des lync-Anruf Konferenz Fensters] Screenshot (images/Dn383570.c2a81727-8751-41b5-946a-03a1b75b9d95(OCS.15).png "des lync-Anruf Konferenz Fensters")</span><span class="sxs-lookup"><span data-stu-id="ed0e7-120">![Screen shot of Lync call conferencing window](images/Dn383570.c2a81727-8751-41b5-946a-03a1b75b9d95(OCS.15).png "Screen shot of Lync call conferencing window")</span></span>

<span data-ttu-id="ed0e7-121">Beachten Sie jedoch, dass es im lync-Unterhaltungsfenster eine Diskrepanz gibt.</span><span class="sxs-lookup"><span data-stu-id="ed0e7-121">Notice, however, that there is a discrepancy within the Lync conversation window.</span></span> <span data-ttu-id="ed0e7-122">Ken Myers ist der einzige Name, der unter der Überschrift " **Teilnehmer** " aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="ed0e7-122">Ken Myer is the only name listed under the **Participants** heading.</span></span> <span data-ttu-id="ed0e7-123">Wenn Sie jedoch in der Titelleiste des Fensters Suchen, sehen Sie, dass die Konferenz insgesamt 4 Teilnehmer enthält.</span><span class="sxs-lookup"><span data-stu-id="ed0e7-123">However, if you look in the title bar of the window, you’ll see that the conference contains a total of 4 participants.</span></span>

<span data-ttu-id="ed0e7-124">Auch wenn Sie im Unterhaltungsfenster eines anderen Konferenzteilnehmers suchen, wird Ken Myers nirgendwo aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="ed0e7-124">Likewise, if you look in the conversation window of any of the other conference participants you will not see Ken Myer listed anywhere:</span></span>

<span data-ttu-id="ed0e7-125">![Screenshot des Fensters "lync-Teilnehmerliste"] (images/Dn383570.fa5990cf-2694-402c-ac06-946aa66b6837(OCS.15).png "Screenshot des Fensters \"lync-Teilnehmerliste\"")</span><span class="sxs-lookup"><span data-stu-id="ed0e7-125">![Lync participant list window screenshot](images/Dn383570.fa5990cf-2694-402c-ac06-946aa66b6837(OCS.15).png "Lync participant list window screenshot")</span></span>

<span data-ttu-id="ed0e7-126">Gleichzeitig kann Ken Myers aber auch über sein lync-fähiges Telefon am Audioteil des Anrufs teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="ed0e7-126">And yet, at the same time, Ken Myer will be able to participate in the audio portion of the call by using his Lync-enabled phone.</span></span> <span data-ttu-id="ed0e7-127">Das Feature "mich anrufen" hat tatsächlich funktioniert, aber die Benutzeroberfläche ist weniger als optimal.</span><span class="sxs-lookup"><span data-stu-id="ed0e7-127">The Call Me At feature has actually worked, but the user experience is less than optimal.</span></span>

<span data-ttu-id="ed0e7-128">Es gibt mindestens zwei Möglichkeiten, dieses Problem zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="ed0e7-128">There are at least two ways to work around this problem.</span></span> <span data-ttu-id="ed0e7-129">Wenn Sie bereits an einer Konferenz teilgenommen haben (wie Ken Myers), können Sie das Problem in der Regel beheben, indem Sie sich an einer anderen Modalität beteiligen.</span><span class="sxs-lookup"><span data-stu-id="ed0e7-129">If you have already joined a conference in this fashion (like Ken Myer did), you can typically resolve the issue by engaging in a different modality.</span></span> <span data-ttu-id="ed0e7-130">Wenn Sie beispielsweise eine Chatnachricht senden, werden im Unterhaltungsfenster nun alle Konferenzteilnehmer angezeigt, einschließlich ihrer selbst:</span><span class="sxs-lookup"><span data-stu-id="ed0e7-130">For example, if you send an instant message the conversation window will now show all the conference participants, including yourself:</span></span>

<span data-ttu-id="ed0e7-131">![Screenshot der lync-Unterhaltung und Teilnehmerliste] (images/Dn383570.9b5ff6d6-9f73-467c-99a7-ef3aa8bd7e7a(OCS.15).png "Screenshot der lync-Unterhaltung und Teilnehmerliste")</span><span class="sxs-lookup"><span data-stu-id="ed0e7-131">![Lync conversation and participant list screenshot](images/Dn383570.9b5ff6d6-9f73-467c-99a7-ef3aa8bd7e7a(OCS.15).png "Lync conversation and participant list screenshot")</span></span>

<span data-ttu-id="ed0e7-132">An diesem Punkt sollten Sie in der Lage sein, an der Besprechung in der erwarteten Weise teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="ed0e7-132">At this point you should be able to participate in the meeting in the expected fashion.</span></span>

<span data-ttu-id="ed0e7-133">Sie können dieses Problem aber auch ganz vermeiden, indem Sie die Art und Weise ändern, wie Sie an der Besprechung teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="ed0e7-133">Alternatively, you can avoid this issue altogether by changing the way you join the meeting.</span></span> <span data-ttu-id="ed0e7-134">Wenn lync Server ein lync Server-fähiges Telefon anrufen soll, sollten Sie mit der Teilnahme an der Besprechung ohne eine Audioverbindung beginnen.</span><span class="sxs-lookup"><span data-stu-id="ed0e7-134">If you need to have Lync Server call a Lync Server-enabled phone, you should begin by joining the meeting without an audio connection.</span></span> <span data-ttu-id="ed0e7-135">Wählen Sie dazu im Dialogfeld "an Besprechung teilnehmen" die Option "nicht an Audio teilnehmen" aus:</span><span class="sxs-lookup"><span data-stu-id="ed0e7-135">To do that, select Don’t join audio when presented with the Join Meeting Audio dialog box:</span></span>

<span data-ttu-id="ed0e7-136">![Screenshot von lync an der Besprechung des Audiofensters nicht teilnehmen] (images/Dn383570.280a148d-cce5-4b02-87f9-9f78f17a81c1(OCS.15).png "Screenshot von lync an der Besprechung des Audiofensters nicht teilnehmen")</span><span class="sxs-lookup"><span data-stu-id="ed0e7-136">![Lync don't join meeting audio window screenshot](images/Dn383570.280a148d-cce5-4b02-87f9-9f78f17a81c1(OCS.15).png "Lync don't join meeting audio window screenshot")</span></span>

<span data-ttu-id="ed0e7-137">Nachdem Sie erfolgreich eine Verbindung mit der Besprechung hergestellt haben, können Sie nun das lync Server-fähige Telefon "einladen", auch an der Besprechung teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="ed0e7-137">After you have successfully connected to the meeting, you can now “invite” the Lync Server-enabled phone to join the meeting as well.</span></span> <span data-ttu-id="ed0e7-138">Setzen Sie dazu den Mauszeiger auf das Symbol Personen, und klicken Sie dann auf **weitere Personen einladen**:</span><span class="sxs-lookup"><span data-stu-id="ed0e7-138">To do that, place the mouse over the People icon and then click **Invite More People**:</span></span>

<span data-ttu-id="ed0e7-139">![Screenshot des Fensters "Weitere Teilnehmer einladen"] (images/Dn383570.69b81b29-d1d2-4ed3-acb6-e37dd18e3d86(OCS.15).png "Screenshot des Fensters \"Weitere Teilnehmer einladen\"")</span><span class="sxs-lookup"><span data-stu-id="ed0e7-139">![Lync invite more participants window screenshot](images/Dn383570.69b81b29-d1d2-4ed3-acb6-e37dd18e3d86(OCS.15).png "Lync invite more participants window screenshot")</span></span>

<span data-ttu-id="ed0e7-140">Dadurch wird das Dialogfeld **Chat senden** eingeblendet.</span><span class="sxs-lookup"><span data-stu-id="ed0e7-140">That will bring up the **Send an IM** dialog box.</span></span> <span data-ttu-id="ed0e7-141">Ignorieren Sie den Titel des Dialogfelds (Sie senden keine Sofortnachricht), und geben Sie die Telefonnummer des lync-fähigen Telefons ein:</span><span class="sxs-lookup"><span data-stu-id="ed0e7-141">Ignore the dialog box title (you’re not actually sending an instant message) and type the phone number of the Lync-enabled phone:</span></span>

<span data-ttu-id="ed0e7-142">![Screenshot des Dialogfelds "Chatnachricht senden] " (images/Dn383570.cd67a3f0-06d8-41ba-a808-c067f64bec9f(OCS.15).png "Screenshot des Dialogfelds \"Chatnachricht senden") "</span><span class="sxs-lookup"><span data-stu-id="ed0e7-142">![Send an IM dialog box screenshot](images/Dn383570.cd67a3f0-06d8-41ba-a808-c067f64bec9f(OCS.15).png "Send an IM dialog box screenshot")</span></span>

<span data-ttu-id="ed0e7-143">Nachdem Sie auf **OK**geklickt haben, ruft lync Server die im Dialogfeld eingegebene Nummer ab.</span><span class="sxs-lookup"><span data-stu-id="ed0e7-143">After you click **OK**, Lync Server will call the number entered in the dialog box.</span></span> <span data-ttu-id="ed0e7-144">Wenn die Verbindung hergestellt wurde, verfügen Sie über das lync-fähige Telefon über vollständige Audiofunktionen, und Sie können die vollständige Konferenzliste anzeigen und mit ihnen interagieren.</span><span class="sxs-lookup"><span data-stu-id="ed0e7-144">When the connection is made, you will have full audio capabilities through the Lync-enabled phone, and you will be able to see and interact with the full conference roster.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

