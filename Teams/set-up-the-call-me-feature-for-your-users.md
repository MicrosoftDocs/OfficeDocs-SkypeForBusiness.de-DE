---
title: Einrichten der Funktion "anrufen" für Ihre Benutzer
author: LanaChin
ms.author: v-lanac
ms.reviewer: macai
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Hier erfahren Sie, wie Sie die Funktion "anrufen" in Microsoft Teams einrichten, damit Benutzer in Szenarien, in denen die Verwendung Ihres Computers für Audio möglicherweise nicht möglich ist, über das Telefon teilnehmen können.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3f1ffee416b1d5674e831fda4c5bb15a89c510f4
ms.sourcegitcommit: 1ddd29e3839e50387efb4ec7b9d2154991bb2642
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2019
ms.locfileid: "35432135"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a><span data-ttu-id="67a0d-103">Einrichten der Funktion "anrufen" für Ihre Benutzer</span><span class="sxs-lookup"><span data-stu-id="67a0d-103">Set up the Call me feature for your users</span></span>

<span data-ttu-id="67a0d-104">In Microsoft Teams bietet die Funktion " **anrufen** " Benutzern eine Möglichkeit, den Audioteil einer Besprechung per Telefon anzunehmen.</span><span class="sxs-lookup"><span data-stu-id="67a0d-104">In Microsoft Teams, the **Call me** feature gives users a way to join the audio portion of a meeting by phone.</span></span> <span data-ttu-id="67a0d-105">Dies ist praktisch in Szenarien, in denen die Verwendung eines Computers für Audio möglicherweise nicht möglich ist.</span><span class="sxs-lookup"><span data-stu-id="67a0d-105">This is handy in scenarios when using a computer for audio might not be possible.</span></span> <span data-ttu-id="67a0d-106">Benutzer erhalten den Audioteil der Besprechung über Ihr Mobiltelefon oder Ihre Festnetz-und den Inhaltsbereich der Besprechung&mdash;, beispielsweise, wenn ein anderer Besprechungsteilnehmer seinen Bildschirm freigibt&mdash;oder ein Video über seinen Computer abspielt.</span><span class="sxs-lookup"><span data-stu-id="67a0d-106">Users get the audio portion of the meeting through their cell phone or land line and the content portion of the meeting&mdash;such when another meeting participant shares their screen or plays a video&mdash;through their computer.</span></span>

## <a name="the-user-experience"></a><span data-ttu-id="67a0d-107">Die Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="67a0d-107">The user experience</span></span>

<span data-ttu-id="67a0d-108">Klicken Sie auf **Teil** nehmen, um an einer Besprechung teilzunehmen, und klicken Sie dann auf der Seite **Wählen Sie Ihre Audio-und Videoeinstellungen aus** auf **Telefon-Audio** .</span><span class="sxs-lookup"><span data-stu-id="67a0d-108">Click **Join** to join a meeting, and then click **Phone audio** on the  **Choose your audio and video settings** screen.</span></span> <span data-ttu-id="67a0d-109">Von hier aus können Benutzer den Besprechungs Anruf führen und an der Besprechung teilnehmen oder sich manuell einwählen.</span><span class="sxs-lookup"><span data-stu-id="67a0d-109">From here, users can have the meeting call and join them or dial in manually to the meeting.</span></span>

![Screenshot der Option "Telefon Audio"](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

<span data-ttu-id="67a0d-111">**Besprechung des Anrufs für Teams**</span><span class="sxs-lookup"><span data-stu-id="67a0d-111">**Let the Teams meeting call**</span></span>

<span data-ttu-id="67a0d-112">Auf dem Bildschirm " **Telefon für Audio verwenden** " gibt der Benutzer seine Telefonnummer ein und klickt dann auf " **anrufen**".</span><span class="sxs-lookup"><span data-stu-id="67a0d-112">On the **Use phone for audio** screen, the user enters their phone number, and then clicks **Call me**.</span></span> <span data-ttu-id="67a0d-113">Die Besprechung Ruft den Benutzer an und verknüpft ihn mit der Besprechung.</span><span class="sxs-lookup"><span data-stu-id="67a0d-113">The meeting calls the user and joins them to the meeting.</span></span>

![Screenshot der Option "anrufen" auf dem Bildschirm "Telefon für Audio verwenden"](media/set-up-the-call-me-feature-for-your-users-call-me.png)

<span data-ttu-id="67a0d-115">**Manuell einwählen**</span><span class="sxs-lookup"><span data-stu-id="67a0d-115">**Dial in manually**</span></span>

<span data-ttu-id="67a0d-116">Eine weitere Möglichkeit, sich anzumelden, besteht darin, sich direkt in die Besprechung einzuwählen.</span><span class="sxs-lookup"><span data-stu-id="67a0d-116">Another way to join is to dial in directly to the meeting.</span></span> <span data-ttu-id="67a0d-117">Klicken Sie auf dem Bildschirm **Telefon für Audio verwenden** auf **manuell einwählen** , um eine Liste der Telefonnummern zu erhalten, die Sie für die Einwahl in die Besprechung verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="67a0d-117">On the **Use phone for audio** screen, click **Dial in manually** to get a list of phone numbers to use to dial in to the meeting.</span></span>

![Screenshot der Option "manuell einwählen"](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

## <a name="set-up-the-call-me-feature"></a><span data-ttu-id="67a0d-119">Einrichten der Funktion "anrufen"</span><span class="sxs-lookup"><span data-stu-id="67a0d-119">Set up the Call me feature</span></span>

<span data-ttu-id="67a0d-120">Um die Funktion "anrufen" für Benutzer in Ihrer Organisation zu aktivieren, muss Folgendes konfiguriert sein:</span><span class="sxs-lookup"><span data-stu-id="67a0d-120">To enable the Call me feature for users in your organization, the following must be configured:</span></span>

- <span data-ttu-id="67a0d-121">Audiokonferenzen sind für Benutzer in Ihrer Organisation aktiviert, die Besprechungen planen (Besprechungsorganisatoren).</span><span class="sxs-lookup"><span data-stu-id="67a0d-121">Audio Conferencing is enabled for users in your organization who schedule meetings (meeting organizers).</span></span> <span data-ttu-id="67a0d-122">Weitere Informationen finden Sie unter [Einrichten von Audiokonferenzen für Teams](set-up-audio-conferencing-in-teams.md) und [Verwalten der Einstellungen für Audiokonferenzen für einen Benutzer in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="67a0d-122">To learn more, see [Set up Audio Conferencing for Teams](set-up-audio-conferencing-in-teams.md) and [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

- <span data-ttu-id="67a0d-123">Benutzer können aus Besprechungen wählen.</span><span class="sxs-lookup"><span data-stu-id="67a0d-123">Users can dial out from meetings.</span></span> <span data-ttu-id="67a0d-124">Weitere Informationen finden Sie unter [Verwalten der Einstellungen für Audiokonferenzen für einen Benutzer in Microsoft Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="67a0d-124">To learn more, see [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

<span data-ttu-id="67a0d-125">Wenn ein Benutzer die Option "Besprechungen" nicht aktiviert hat, steht die Option " **anrufen** " nicht zur Verfügung, und der Benutzer erhält keinen Anruf, um an der Besprechung teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="67a0d-125">If a user doesn't have dial out from meetings enabled, the **Call me** option isn't available and the user won't receive a call to join them to the meeting.</span></span> <span data-ttu-id="67a0d-126">Stattdessen sieht der Benutzer auf dem Bildschirm " **Telefon für Audio verwenden** " eine Liste mit Telefonnummern, mit denen er sich manuell in die Besprechung auf seinem Telefon einwählen kann.</span><span class="sxs-lookup"><span data-stu-id="67a0d-126">Instead, the user sees a list of phone numbers on the **Use phone for audio** screen that they can use to dial in manually to the meeting on their phone.</span></span>

