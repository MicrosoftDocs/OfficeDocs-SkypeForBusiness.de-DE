---
title: Einrichten der Funktion „Rückruf“ für Ihre Benutzer
author: LanaChin
ms.author: v-lanac
ms.reviewer: macai, phedry
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Hier erfahren Sie, wie Sie die Funktion "anrufen" in Microsoft Teams einrichten, damit Benutzer den Audioanteil per Telefon teilnehmen können, wenn Ihr Computer für Audio möglicherweise nicht möglich ist.
localization_priority: Normal
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d29a517b8df194fe19b9e16554f7c57964177c90
ms.sourcegitcommit: 70b80892a152f86a6d596f0f5b58cf391bc29098
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2020
ms.locfileid: "45138015"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a><span data-ttu-id="0f7e8-103">Einrichten der Funktion „Rückruf“ für Ihre Benutzer</span><span class="sxs-lookup"><span data-stu-id="0f7e8-103">Set up the Call me feature for your users</span></span>

<span data-ttu-id="0f7e8-104">In Microsoft Teams bietet die Funktion " **anrufen** " Benutzern eine Möglichkeit, den Audioteil einer Besprechung per Telefon anzunehmen.</span><span class="sxs-lookup"><span data-stu-id="0f7e8-104">In Microsoft Teams, the **Call me** feature gives users a way to join the audio portion of a meeting by phone.</span></span> <span data-ttu-id="0f7e8-105">Dies ist praktisch in Szenarien, in denen die Verwendung eines Computers für Audio möglicherweise nicht möglich ist.</span><span class="sxs-lookup"><span data-stu-id="0f7e8-105">This is handy in scenarios when using a computer for audio might not be possible.</span></span> <span data-ttu-id="0f7e8-106">Benutzer erhalten den Audioteil der Besprechung über Ihr Mobiltelefon oder Ihre Festnetz-und den Inhaltsteil der Besprechung, &mdash; beispielsweise wenn ein anderer Besprechungsteilnehmer seinen Bildschirm freigibt oder ein Video &mdash; über seinen Computer abspielt.</span><span class="sxs-lookup"><span data-stu-id="0f7e8-106">Users get the audio portion of the meeting through their cell phone or land line and the content portion of the meeting&mdash;such as when another meeting participant shares their screen or plays a video&mdash;through their computer.</span></span>

> [!IMPORTANT]
> 
> <span data-ttu-id="0f7e8-107">In Zeiten hoher Besprechungs Volumina (die wir in Verbindung mit dem COVID-19-Ausbruch erlebt haben) empfehlen wir, dass Benutzer an Besprechungen teilnehmen, indem Sie auf die Schaltfläche " <strong>an Teams teilnehmen</strong> " klicken, anstatt sich über die PSTN-Konferenznummern oder mithilfe von " <strong>anrufen unter" zu</strong>wählen.</span><span class="sxs-lookup"><span data-stu-id="0f7e8-107">During periods of high meeting volume (which we've been experiencing in conjunction with the COVID-19 outbreak), we recommend that users join meetings by clicking the <strong>Join Teams Meeting</strong> button rather than dialing in by using the PSTN conference numbers or by using <strong>Call me at</strong>.</span></span> <span data-ttu-id="0f7e8-108">Auf diese Weise wird die Audioqualität in Zeiten gewährleistet, in denen das PSTN-Netzwerk mit einem hohen Besprechungs Volumen Überlastung verursacht.</span><span class="sxs-lookup"><span data-stu-id="0f7e8-108">This helps ensure quality audio during times when high meeting volume is causing congestion on the PSTN network.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="0f7e8-109">Während der Dauer des COVID-19-Ausbruchs empfehlen wir, dass Benutzer an Besprechungen teilnehmen, indem Sie auf die Schaltfläche **An Teams-Besprechung teilnehmen** klicken, anstatt sich über die Rufnummern der PSTN-Konferenz einzuwählen oder **Rückruf unter**</strong> zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="0f7e8-109">During the duration of the COVID-19 outbreak, we recommend that users join meetings by clicking the **Join Teams Meeting** button rather than dialing in by using the PSTN conference numbers or by using **Call me at**</strong>.</span></span> <span data-ttu-id="0f7e8-110">Grund hierfür ist in erster Linie die Überlastung der Telefonie-Infrastrukturen in den von COVID-19 betroffenen Ländern.</span><span class="sxs-lookup"><span data-stu-id="0f7e8-110">This is primarily because of congestion in the telephony infrastructures of countries impacted by COVID-19.</span></span> <span data-ttu-id="0f7e8-111">Wenn Sie Anrufe über das Telefonfestnetz vermeiden, werden Sie wahrscheinlich eine bessere Tonqualität feststellen.</span><span class="sxs-lookup"><span data-stu-id="0f7e8-111">By avoiding PSTN calls, you'll likely experience better audio quality.</span></span> 

## <a name="the-user-experience"></a><span data-ttu-id="0f7e8-112">Die Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="0f7e8-112">The user experience</span></span>

### <a name="join-a-meeting-by-using-phone-for-audio"></a><span data-ttu-id="0f7e8-113">Teilnehmen an einer Besprechung mithilfe des Telefons für Audio</span><span class="sxs-lookup"><span data-stu-id="0f7e8-113">Join a meeting by using phone for audio</span></span>

<span data-ttu-id="0f7e8-114">Klicken Sie auf **Teil** nehmen, um an einer Besprechung teilzunehmen, und klicken Sie dann auf der Seite **Wählen Sie Ihre Audio-und Videoeinstellungen aus** auf **Telefon-Audio** .</span><span class="sxs-lookup"><span data-stu-id="0f7e8-114">Click **Join** to join a meeting, and then click **Phone audio** on the  **Choose your audio and video settings** screen.</span></span> <span data-ttu-id="0f7e8-115">Von hier aus können Benutzer den Besprechungs Anruf führen und an der Besprechung teilnehmen oder sich manuell einwählen.</span><span class="sxs-lookup"><span data-stu-id="0f7e8-115">From here, users can have the meeting call and join them or dial in manually to the meeting.</span></span>

![Screenshot der Option "Telefon Audio"](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

<span data-ttu-id="0f7e8-117">**Besprechung des Anrufs für Teams**</span><span class="sxs-lookup"><span data-stu-id="0f7e8-117">**Let the Teams meeting call**</span></span>

<span data-ttu-id="0f7e8-118">Auf dem Bildschirm " **Telefon für Audio verwenden** " gibt der Benutzer seine Telefonnummer ein und klickt dann auf " **anrufen**".</span><span class="sxs-lookup"><span data-stu-id="0f7e8-118">On the **Use phone for audio** screen, the user enters their phone number, and then clicks **Call me**.</span></span> <span data-ttu-id="0f7e8-119">Die Besprechung Ruft den Benutzer an und verknüpft ihn mit der Besprechung.</span><span class="sxs-lookup"><span data-stu-id="0f7e8-119">The meeting calls the user and joins them to the meeting.</span></span>

![Screenshot der Option "anrufen" auf dem Bildschirm "Telefon für Audio verwenden"](media/set-up-the-call-me-feature-for-your-users-call-me.png)

<span data-ttu-id="0f7e8-121">**Manuell einwählen**</span><span class="sxs-lookup"><span data-stu-id="0f7e8-121">**Dial in manually**</span></span>

<span data-ttu-id="0f7e8-122">Eine weitere Möglichkeit, sich anzumelden, besteht darin, sich direkt in die Besprechung einzuwählen.</span><span class="sxs-lookup"><span data-stu-id="0f7e8-122">Another way to join is to dial in directly to the meeting.</span></span> <span data-ttu-id="0f7e8-123">Klicken Sie auf dem Bildschirm **Telefon für Audio verwenden** auf **manuell einwählen** , um eine Liste der Telefonnummern zu erhalten, die Sie für die Einwahl in die Besprechung verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="0f7e8-123">On the **Use phone for audio** screen, click **Dial in manually** to get a list of phone numbers to use to dial in to the meeting.</span></span>

![Screenshot der Option "manuell einwählen"](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a><span data-ttu-id="0f7e8-125">Rufen Sie zurück, wenn während einer Besprechung etwas schief geht.</span><span class="sxs-lookup"><span data-stu-id="0f7e8-125">Get a call back when something goes wrong with audio during a meeting</span></span>

<span data-ttu-id="0f7e8-126">Wenn ein Benutzer bei der Nutzung seines Computers während einer Besprechung Audioprobleme hat, kann der Benutzer einfach zur Verwendung seines Telefons für Audio wechseln.</span><span class="sxs-lookup"><span data-stu-id="0f7e8-126">If a user experiences audio issues when using their computer during a meeting, the user can easily switch to using their phone for audio.</span></span> <span data-ttu-id="0f7e8-127">Teams erkennt, wenn ein Audio-oder Geräteproblem auftritt, und leitet den Benutzer zur Verwendung des Telefons ein, indem die Option **Rückruf zurück** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="0f7e8-127">Teams detects when an audio or device issue occurs and redirects the user to use their phone by displaying a **Call me back** option.</span></span>

<span data-ttu-id="0f7e8-128">Nachfolgend finden Sie ein Beispiel für die Nachricht und die Option **Rückruf zurück** , die angezeigt wird, wenn Teams kein Mikrofon erkennen.</span><span class="sxs-lookup"><span data-stu-id="0f7e8-128">Here's an example of the message and the **Call me back** option that's displayed when Teams doesn't detect a microphone.</span></span>

![Screenshot der Option "Rückruf zurück"](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

<span data-ttu-id="0f7e8-130">Der Benutzer klickt auf **Rückruf zurück**, wodurch der Bildschirm " **Telefon für Audio verwenden** " angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="0f7e8-130">The user clicks **Call me back**, which brings up the **Use phone for audio** screen.</span></span> <span data-ttu-id="0f7e8-131">Von hier aus können Sie Ihre Telefonnummer eingeben und die Teams für Besprechungen anrufen und an der Besprechung teilnehmen oder sich manuell in die Besprechung einwählen.</span><span class="sxs-lookup"><span data-stu-id="0f7e8-131">From here, they can enter their phone number and have the Teams meeting call and join them to the meeting or dial in manually to the meeting.</span></span>

## <a name="set-up-the-call-me-feature"></a><span data-ttu-id="0f7e8-132">Einrichten der Funktion "anrufen"</span><span class="sxs-lookup"><span data-stu-id="0f7e8-132">Set up the Call me feature</span></span>

<span data-ttu-id="0f7e8-133">Um die Funktion "anrufen" für Benutzer in Ihrer Organisation zu aktivieren, muss Folgendes konfiguriert sein:</span><span class="sxs-lookup"><span data-stu-id="0f7e8-133">To enable the Call me feature for users in your organization, the following must be configured:</span></span>

- <span data-ttu-id="0f7e8-134">Audiokonferenzen sind für Benutzer in Ihrer Organisation aktiviert, die Besprechungen planen (Besprechungsorganisatoren).</span><span class="sxs-lookup"><span data-stu-id="0f7e8-134">Audio Conferencing is enabled for users in your organization who schedule meetings (meeting organizers).</span></span> <span data-ttu-id="0f7e8-135">Weitere Informationen finden Sie unter [Einrichten von Audiokonferenzen für Teams](set-up-audio-conferencing-in-teams.md) und [Verwalten der Einstellungen für Audiokonferenzen für einen Benutzer in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="0f7e8-135">To learn more, see [Set up Audio Conferencing for Teams](set-up-audio-conferencing-in-teams.md) and [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

- <span data-ttu-id="0f7e8-136">Benutzer können aus Besprechungen wählen.</span><span class="sxs-lookup"><span data-stu-id="0f7e8-136">Users can dial out from meetings.</span></span> <span data-ttu-id="0f7e8-137">Weitere Informationen finden Sie unter [Verwalten der Einstellungen für Audiokonferenzen für einen Benutzer in Microsoft Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="0f7e8-137">To learn more, see [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

<span data-ttu-id="0f7e8-138">Wenn ein Benutzer die Option "Besprechungen" nicht aktiviert hat, steht die Option " **anrufen** " nicht zur Verfügung, und der Benutzer erhält keinen Anruf, um an der Besprechung teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="0f7e8-138">If a user doesn't have dial out from meetings enabled, the **Call me** option isn't available and the user won't receive a call to join them to the meeting.</span></span> <span data-ttu-id="0f7e8-139">Stattdessen sieht der Benutzer auf dem Bildschirm " **Telefon für Audio verwenden** " eine Liste mit Telefonnummern, mit denen er sich manuell in die Besprechung auf seinem Telefon einwählen kann.</span><span class="sxs-lookup"><span data-stu-id="0f7e8-139">Instead, the user sees a list of phone numbers on the **Use phone for audio** screen that they can use to dial in manually to the meeting on their phone.</span></span>
