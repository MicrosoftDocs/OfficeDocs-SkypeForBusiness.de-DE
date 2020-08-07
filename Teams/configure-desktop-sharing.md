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
description: Hier erfahren Sie, wie Sie eine Besprechungsrichtlinie so konfigurieren, dass Benutzer ihre Desktops in Team-Chats oder Besprechungen freigeben können.
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 857c9c4d830cb3264a83a41b555d26ee004751de
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2020
ms.locfileid: "46581746"
---
<a name="configure-desktop-sharing-in-microsoft-teams"></a><span data-ttu-id="fcc82-103">Konfigurieren der Desktopfreigabe in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fcc82-103">Configure desktop sharing in Microsoft Teams</span></span>
============================================

<span data-ttu-id="fcc82-104">Die Desktopfreigabe ermöglicht es Benutzern, während einer Besprechung oder eines Chats einen Bildschirm oder eine App anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="fcc82-104">Desktop sharing lets users present a screen or app during a meeting or chat.</span></span> <span data-ttu-id="fcc82-105">Administratoren können die Bildschirmfreigabe in Microsoft Teams so konfigurieren, dass Benutzer einen gesamten Bildschirm, eine App oder eine Datei freigeben können.</span><span class="sxs-lookup"><span data-stu-id="fcc82-105">Admins can configure screen sharing in Microsoft Teams to let users share an entire screen, an app, or a file.</span></span> <span data-ttu-id="fcc82-106">Sie können zulassen, dass Benutzer die Steuerung ermöglichen oder anfordern können, die PowerPoint-Freigabe zulassen, ein Whiteboard hinzufügen und das Freigebe zulassen.</span><span class="sxs-lookup"><span data-stu-id="fcc82-106">You can let users give or request control, allow PowerPoint sharing, add a whiteboard, and allow shared notes.</span></span> <span data-ttu-id="fcc82-107">Sie können auch festlegen, ob anonyme oder externe Benutzer die Steuerung des freigegebenen Bildschirms anfordern können.</span><span class="sxs-lookup"><span data-stu-id="fcc82-107">You can also configure whether anonymous or external users can request control of the shared screen.</span></span>

<span data-ttu-id="fcc82-108">Um die Bildschirmfreigabe zu konfigurieren, erstellen Sie eine neue Besprechungsrichtlinie und weisen Sie diese dann den Benutzern zu, die Sie verwalten möchten.</span><span class="sxs-lookup"><span data-stu-id="fcc82-108">To configure screen sharing, you create a new meetings policy and then assign it to the users you want to manage.</span></span>

<span data-ttu-id="fcc82-109">**Im [Microsoft Teams Admin Center](https://admin.teams.microsoft.com/)**</span><span class="sxs-lookup"><span data-stu-id="fcc82-109">**In the [Microsoft Teams admin center](https://admin.teams.microsoft.com/)**</span></span>

1. <span data-ttu-id="fcc82-110">Wählen Sie **Besprechungen** > **Besprechungsrichtlinien**.</span><span class="sxs-lookup"><span data-stu-id="fcc82-110">Select **Meetings** > **Meeting policies**.</span></span>

    ![Screenshot mit Besprechungsrichtlinien ausgewählt](media/configure-desktop-sharing-image1.png)

2. <span data-ttu-id="fcc82-112">Wählen Sie auf der Seite **Besprechungsrichtlinien** die Option **Neue Richtlinie** aus.</span><span class="sxs-lookup"><span data-stu-id="fcc82-112">On the **Meeting policies** page, select **New policy**.</span></span>

    ![Screenshot mit der Nachricht „Besprechungsrichtlinien“](media/configure-desktop-sharing-image2.png)

3. <span data-ttu-id="fcc82-114">Weisen Sie Ihrer Richtlinie einen eindeutigen Titel zu und geben Sie eine kurze Beschreibung ein.</span><span class="sxs-lookup"><span data-stu-id="fcc82-114">Give your policy a unique title and enter a brief description.</span></span>

4. <span data-ttu-id="fcc82-115">Wählen Sie aus der Dropdownliste unter **Inhaltsfreigabe** die gewünschte Option für den **Bildschirmfreigabemodus** aus:</span><span class="sxs-lookup"><span data-stu-id="fcc82-115">Under **Content sharing**, choose a **Screen sharing mode** from the drop-down list:</span></span>

   - <span data-ttu-id="fcc82-116">**Gesamter Bildschirm**: Ermöglicht Benutzern die Freigabe des gesamten Bildschirms.</span><span class="sxs-lookup"><span data-stu-id="fcc82-116">**Entire screen** – lets users share their entire desktop.</span></span>
   - <span data-ttu-id="fcc82-117">**Einzelne Anwendung**: Ermöglicht Benutzern die Beschränkung der Bildschirmfreigabe auf eine einzelne aktive Anwendung.</span><span class="sxs-lookup"><span data-stu-id="fcc82-117">**Single application** – lets users limit screen sharing to a single active application.</span></span>
   - <span data-ttu-id="fcc82-118">**Deaktiviert** – Deaktiviert die Bildschirmfreigabe.</span><span class="sxs-lookup"><span data-stu-id="fcc82-118">**Disabled** – Turns off screen sharing.</span></span>

    ![Screenshot mit Optionen für den Freigabemodus](media/configure-desktop-sharing-image3.png)

5. <span data-ttu-id="fcc82-120">Aktivieren oder deaktivieren Sie die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="fcc82-120">Turn the following settings on or off:</span></span>

    - <span data-ttu-id="fcc82-121">**Zulassen, dass ein Teilnehmer die Steuerung erteilt oder anfordert** – ermöglicht es Mitgliedern des Teams, die Steuerung des Desktops oder der Anwendung des Referenten zu erteilen oder anzufordern.</span><span class="sxs-lookup"><span data-stu-id="fcc82-121">**Allow a participant to give or request control** – lets members of the team give or request control of the presenter's desktop or application.</span></span>
    - <span data-ttu-id="fcc82-122">**Einem externen Teilnehmer erlauben, die Kontrolle zu erteilen oder anzufordern** – Dies ist eine Richtlinie pro Benutzer.</span><span class="sxs-lookup"><span data-stu-id="fcc82-122">**Allow an external participant to give or request control** – This is a per-user policy.</span></span> <span data-ttu-id="fcc82-123">Ob diese Gruppe für einen Benutzer von einer Organisation eingerichtet wurde, steuert nicht, was externe Teilnehmer tun können, unabhängig davon, was der Besprechungsorganisator festgestellt hat.</span><span class="sxs-lookup"><span data-stu-id="fcc82-123">Whether an organization has this set for a user doesn't control what external participants can do, regardless of what the meeting organizer has set.</span></span> <span data-ttu-id="fcc82-124">Dieser Parameter steuert, ob externen Teilnehmern die Kontrolle über den Bildschirm des Mitarbeiters gewährt werden kann, je nachdem, was der freigaber innerhalb der Besprechungsrichtlinien Ihrer Organisation festgesetzt hat.</span><span class="sxs-lookup"><span data-stu-id="fcc82-124">This parameter controls whether external participants can be given control or request control of the sharer's screen, depending on what the sharer has set within their organization's meeting policies.</span></span>
    - <span data-ttu-id="fcc82-125">**PowerPoint-Freigabe zulassen**: Ermöglicht Benutzern das Erstellen von Besprechungen, die das Hochladen und Freigeben von PowerPoint-Präsentationen zulassen.</span><span class="sxs-lookup"><span data-stu-id="fcc82-125">**Allow PowerPoint sharing** - lets users create meetings that allow PowerPoint presentations to be uploaded and shared.</span></span>
    - <span data-ttu-id="fcc82-126">**Whiteboard zulassen**: Ermöglicht Benutzern die Freigabe eines Whiteboards.</span><span class="sxs-lookup"><span data-stu-id="fcc82-126">**Allow whiteboard** – lets users share a whiteboard.</span></span>
    - <span data-ttu-id="fcc82-127">**Freigabe von Notizen zulassen**: Ermöglicht Benutzern, freigegebene Notizen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fcc82-127">**Allow shared notes** – lets users take shared notes.</span></span>

6. <span data-ttu-id="fcc82-128">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="fcc82-128">Click **Save**.</span></span>

## <a name="use-powershell-to-configure-shared-desktop"></a><span data-ttu-id="fcc82-129">Verwenden von PowerShell zum Konfigurieren des freigegebenen Desktops</span><span class="sxs-lookup"><span data-stu-id="fcc82-129">Use PowerShell to configure shared desktop</span></span>

<span data-ttu-id="fcc82-130">Sie können auch das Cmdlet [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) verwenden, um die Desktopfreigabe zu steuern.</span><span class="sxs-lookup"><span data-stu-id="fcc82-130">You can also use the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) cmdlet to control desktop sharing.</span></span> <span data-ttu-id="fcc82-131">Legen Sie die folgenden Parameter fest:</span><span class="sxs-lookup"><span data-stu-id="fcc82-131">Set the following parameters:</span></span>

- <span data-ttu-id="fcc82-132">Description</span><span class="sxs-lookup"><span data-stu-id="fcc82-132">Description</span></span>
- <span data-ttu-id="fcc82-133">ScreenSharingMode</span><span class="sxs-lookup"><span data-stu-id="fcc82-133">ScreenSharingMode</span></span>
- <span data-ttu-id="fcc82-134">AllowParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="fcc82-134">AllowParticipantGiveRequestControl</span></span>
- <span data-ttu-id="fcc82-135">AllowExternalParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="fcc82-135">AllowExternalParticipantGiveRequestControl</span></span>
- <span data-ttu-id="fcc82-136">AllowPowerPointSharing</span><span class="sxs-lookup"><span data-stu-id="fcc82-136">AllowPowerPointSharing</span></span>
- <span data-ttu-id="fcc82-137">AllowWhiteboard</span><span class="sxs-lookup"><span data-stu-id="fcc82-137">AllowWhiteboard</span></span>
- <span data-ttu-id="fcc82-138">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="fcc82-138">AllowSharedNotes</span></span>

<span data-ttu-id="fcc82-139">[Erfahren Sie mehr über das csTeamsMeetingPolicy-Cmdlet ](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="fcc82-139">[Learn more about using the csTeamsMeetingPolicy cmdlet](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span></span>

