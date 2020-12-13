---
title: Konfigurieren der Desktopfreigabe in Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.reviewer: jastark
ms.date: 03/22/2019
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
description: Erfahren Sie, wie Sie eine Besprechungsrichtlinie konfigurieren, damit Benutzer ihre Desktops in Teams-Chats oder Besprechungen freigeben können.
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: d75e540de7e40206f0b1dd15e26adc62d6f6baa7
ms.sourcegitcommit: d27b97f012d0cb3f1690d3673d50bbaa0caae16f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2020
ms.locfileid: "47652472"
---
<a name="configure-desktop-sharing-in-microsoft-teams"></a><span data-ttu-id="883a6-103">Konfigurieren der Desktopfreigabe in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="883a6-103">Configure desktop sharing in Microsoft Teams</span></span>
============================================

<span data-ttu-id="883a6-104">Die Desktopfreigabe ermöglicht es Benutzern, während einer Besprechung oder eines Chats einen Bildschirm oder eine App anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="883a6-104">Desktop sharing lets users present a screen or app during a meeting or chat.</span></span> <span data-ttu-id="883a6-105">Administratoren können die Bildschirmfreigabe in Microsoft Teams so konfigurieren, dass Benutzer einen gesamten Bildschirm, eine App oder eine Datei freigeben können.</span><span class="sxs-lookup"><span data-stu-id="883a6-105">Admins can configure screen sharing in Microsoft Teams to let users share an entire screen, an app, or a file.</span></span> <span data-ttu-id="883a6-106">Sie können zulassen, dass Benutzer die Steuerung ermöglichen oder anfordern können, die PowerPoint-Freigabe zulassen, ein Whiteboard hinzufügen und das Freigebe zulassen.</span><span class="sxs-lookup"><span data-stu-id="883a6-106">You can let users give or request control, allow PowerPoint sharing, add a whiteboard, and allow shared notes.</span></span> <span data-ttu-id="883a6-107">Sie können auch festlegen, ob anonyme oder externe Benutzer die Steuerung des freigegebenen Bildschirms anfordern können.</span><span class="sxs-lookup"><span data-stu-id="883a6-107">You can also configure whether anonymous or external users can request control of the shared screen.</span></span> <span data-ttu-id="883a6-108">Externe Teilnehmer an Microsoft Teams-Besprechungen können wie folgt kategorisiert werden:</span><span class="sxs-lookup"><span data-stu-id="883a6-108">External participants in Teams meetings can be categorized as follows:</span></span>

- <span data-ttu-id="883a6-109">Anonymer Benutzer</span><span class="sxs-lookup"><span data-stu-id="883a6-109">Anonymous user</span></span>
- <span data-ttu-id="883a6-110">Gastbenutzer</span><span class="sxs-lookup"><span data-stu-id="883a6-110">Guest users</span></span>
- <span data-ttu-id="883a6-111">B2B-Benutzer</span><span class="sxs-lookup"><span data-stu-id="883a6-111">B2B user</span></span>
- <span data-ttu-id="883a6-112">Verbundbenutzer</span><span class="sxs-lookup"><span data-stu-id="883a6-112">Federated user</span></span>

<span data-ttu-id="883a6-113">Um die Bildschirmfreigabe zu konfigurieren, erstellen Sie eine neue Besprechungsrichtlinie und weisen Sie diese dann den Benutzern zu, die Sie verwalten möchten.</span><span class="sxs-lookup"><span data-stu-id="883a6-113">To configure screen sharing, you create a new meetings policy and then assign it to the users you want to manage.</span></span>

<span data-ttu-id="883a6-114">**Im [Microsoft Teams Admin Center](https://admin.teams.microsoft.com/)**</span><span class="sxs-lookup"><span data-stu-id="883a6-114">**In the [Microsoft Teams admin center](https://admin.teams.microsoft.com/)**</span></span>

1. <span data-ttu-id="883a6-115">Wählen Sie **Besprechungen** > **Besprechungsrichtlinien**.</span><span class="sxs-lookup"><span data-stu-id="883a6-115">Select **Meetings** > **Meeting policies**.</span></span>

    ![Ausgewählte Besprechungsrichtlinien](media/configure-desktop-sharing-image1.png)

2. <span data-ttu-id="883a6-117">Wählen Sie auf der Seite **Besprechungsrichtlinien** die Option **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="883a6-117">On the **Meeting policies** page, select **Add**.</span></span>

    ![Die Besprechungsrichtlinienmeldung](media/addMeeting.png)

3. <span data-ttu-id="883a6-119">Weisen Sie Ihrer Richtlinie einen eindeutigen Titel zu und geben Sie eine kurze Beschreibung ein.</span><span class="sxs-lookup"><span data-stu-id="883a6-119">Give your policy a unique title and enter a brief description.</span></span>

4. <span data-ttu-id="883a6-120">Wählen Sie aus der Dropdownliste unter **Inhaltsfreigabe** die gewünschte Option für den **Bildschirmfreigabemodus** aus:</span><span class="sxs-lookup"><span data-stu-id="883a6-120">Under **Content sharing**, choose a **Screen sharing mode** from the drop-down list:</span></span>

   - <span data-ttu-id="883a6-121">**Gesamter Bildschirm**: Ermöglicht Benutzern die Freigabe des gesamten Bildschirms.</span><span class="sxs-lookup"><span data-stu-id="883a6-121">**Entire screen** – lets users share their entire desktop.</span></span>
   - <span data-ttu-id="883a6-122">**Einzelne Anwendung**: Ermöglicht Benutzern die Beschränkung der Bildschirmfreigabe auf eine einzelne aktive Anwendung.</span><span class="sxs-lookup"><span data-stu-id="883a6-122">**Single application** – lets users limit screen sharing to a single active application.</span></span>
   - <span data-ttu-id="883a6-123">**Deaktiviert** – Deaktiviert die Bildschirmfreigabe.</span><span class="sxs-lookup"><span data-stu-id="883a6-123">**Disabled** – Turns off screen sharing.</span></span>

    ![Die Freigabemodusoptionen](media/configure-desktop-sharing-image3.png)

  > [!Note]
  > <span data-ttu-id="883a6-125">Sie brauchen die Anrufrichtlinie nicht zu aktivieren, damit Benutzer die Bildschirmfreigabe vom Chat aus verwenden können.</span><span class="sxs-lookup"><span data-stu-id="883a6-125">You don't have to enable the calling policy in order for users to use screen share from chat.</span></span> <span data-ttu-id="883a6-126">Der Ton wird jedoch ausgeschaltet, bis sie die Stummschaltung selbst aufheben.</span><span class="sxs-lookup"><span data-stu-id="883a6-126">However, their audio is turned off until they unmute themselves.</span></span> <span data-ttu-id="883a6-127">Darüber hinaus kann der Benutzer, der den Bildschirm freigibt, auf **Audio hinzufügen** klicken, um Audio zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="883a6-127">In addition, the user sharing the screen can click **Add Audio** to enable audio.</span></span> <span data-ttu-id="883a6-128">Ist die Anrufrichtlinie deaktiviert, können Benutzer der Bildschirmfreigabe aus einer Chatsitzung heraus kein Audio hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="883a6-128">If the calling policy is disabled, users won't be able to add audio to the screen share from a chat session.</span></span>

5. <span data-ttu-id="883a6-129">Aktivieren oder deaktivieren Sie die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="883a6-129">Turn the following settings on or off:</span></span>

    - <span data-ttu-id="883a6-130">**Zulassen, dass ein Teilnehmer die Steuerung erteilt oder anfordert**: Ermöglicht Mitgliedern des Teams die Steuerung des Desktops oder der Anwendung des Referenten zuzulassen oder anzufordern.</span><span class="sxs-lookup"><span data-stu-id="883a6-130">**Allow a participant to give or request control** – lets members of the team give or request control of the presenter's desktop or application.</span></span>
    - <span data-ttu-id="883a6-131">**Zulassen, dass ein externer Teilnehmer die Steuerung erteilt oder anfordert**: Hierbei handelt es sich um eine benutzerspezifische Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="883a6-131">**Allow an external participant to give or request control** – This is a per-user policy.</span></span> <span data-ttu-id="883a6-132">Wenn dies von einer Organisation für einen Benutzer festgelegt wurde, wird dadurch nicht gesteuert, was externe Teilnehmer tun können – unabhängig davon, was der Besprechungsorganisator festgelegt hat.</span><span class="sxs-lookup"><span data-stu-id="883a6-132">Whether an organization has this set for a user doesn't control what external participants can do, regardless of what the meeting organizer has set.</span></span> <span data-ttu-id="883a6-133">Über diesen Parameter wird gesteuert, ob externen Teilnehmern die Steuerung des von jemand anderen freigegebenen Bildschirms übergeben werden kann bzw. ob sie dies anfordern können, je nachdem, was der freigebende Benutzer in den Besprechungsrichtlinien seiner Organisation festgelegt hat.</span><span class="sxs-lookup"><span data-stu-id="883a6-133">This parameter controls whether external participants can be given control or request control of the sharer's screen, depending on what the sharer has set within their organization's meeting policies.</span></span>
    - <span data-ttu-id="883a6-134">**PowerPoint-Freigabe zulassen**: Ermöglicht Benutzern das Erstellen von Besprechungen, die das Hochladen und Freigeben von PowerPoint-Präsentationen zulassen.</span><span class="sxs-lookup"><span data-stu-id="883a6-134">**Allow PowerPoint sharing** - lets users create meetings that allow PowerPoint presentations to be uploaded and shared.</span></span>
    - <span data-ttu-id="883a6-135">**Whiteboard zulassen**: Ermöglicht Benutzern die Freigabe eines Whiteboards.</span><span class="sxs-lookup"><span data-stu-id="883a6-135">**Allow whiteboard** – lets users share a whiteboard.</span></span>
    - <span data-ttu-id="883a6-136">**Freigabe von Notizen zulassen**: Ermöglicht Benutzern, freigegebene Notizen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="883a6-136">**Allow shared notes** – lets users take shared notes.</span></span>

6. <span data-ttu-id="883a6-137">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="883a6-137">Click **Save**.</span></span>

## <a name="use-powershell-to-configure-shared-desktop"></a><span data-ttu-id="883a6-138">Verwenden von PowerShell zum Konfigurieren des freigegebenen Desktops</span><span class="sxs-lookup"><span data-stu-id="883a6-138">Use PowerShell to configure shared desktop</span></span>

<span data-ttu-id="883a6-139">Sie können auch das Cmdlet [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) verwenden, um die Desktopfreigabe zu steuern.</span><span class="sxs-lookup"><span data-stu-id="883a6-139">You can also use the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) cmdlet to control desktop sharing.</span></span> <span data-ttu-id="883a6-140">Legen Sie die folgenden Parameter fest:</span><span class="sxs-lookup"><span data-stu-id="883a6-140">Set the following parameters:</span></span>

- <span data-ttu-id="883a6-141">Description</span><span class="sxs-lookup"><span data-stu-id="883a6-141">Description</span></span>
- <span data-ttu-id="883a6-142">ScreenSharingMode</span><span class="sxs-lookup"><span data-stu-id="883a6-142">ScreenSharingMode</span></span>
- <span data-ttu-id="883a6-143">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="883a6-143">AllowPrivateCalling</span></span>
- <span data-ttu-id="883a6-144">AllowParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="883a6-144">AllowParticipantGiveRequestControl</span></span>
- <span data-ttu-id="883a6-145">AllowExternalParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="883a6-145">AllowExternalParticipantGiveRequestControl</span></span>
- <span data-ttu-id="883a6-146">AllowPowerPointSharing</span><span class="sxs-lookup"><span data-stu-id="883a6-146">AllowPowerPointSharing</span></span>
- <span data-ttu-id="883a6-147">AllowWhiteboard</span><span class="sxs-lookup"><span data-stu-id="883a6-147">AllowWhiteboard</span></span>
- <span data-ttu-id="883a6-148">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="883a6-148">AllowSharedNotes</span></span>

<span data-ttu-id="883a6-149">[Erfahren Sie mehr über das csTeamsMeetingPolicy-Cmdlet ](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="883a6-149">[Learn more about using the csTeamsMeetingPolicy cmdlet](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span></span>
