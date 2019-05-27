---
title: Konfigurieren der Desktopfreigabe in Microsoft Teams
author: LolaJacobsen
ms.author: Lolaj
manager: serdars
ms.reviewer: jastark
ms.date: 03/22/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Konfigurieren einer Besprechungsrichtlinie, damit Benutzer ihre Desktops in Teams-Chats oder-Besprechungen freigeben können
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0bf213b919ee0bea344807f932e16240587b2b84
ms.sourcegitcommit: b92b673e718e34b6ebda6de57ad69eb6651faa98
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2019
ms.locfileid: "34433239"
---
<a name="configure-desktop-sharing-in-microsoft-teams"></a><span data-ttu-id="bd336-103">Konfigurieren der Desktopfreigabe in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bd336-103">Configure desktop sharing in Microsoft Teams</span></span>
============================================

<span data-ttu-id="bd336-104">Mit der Desktop Freigabe können Benutzer während einer Besprechung oder eines Chats einen Bildschirm oder eine APP präsentieren.</span><span class="sxs-lookup"><span data-stu-id="bd336-104">Desktop sharing lets users present a screen or app during a meeting or chat.</span></span> <span data-ttu-id="bd336-105">Administratoren können die Bildschirmfreigabe in Microsoft Teams so konfigurieren, dass Benutzer einen ganzen Bildschirm, eine APP oder eine Datei freigeben können.</span><span class="sxs-lookup"><span data-stu-id="bd336-105">Admins can configure screen sharing in Microsoft Teams to let users share an entire screen, an app, or a file.</span></span> <span data-ttu-id="bd336-106">Sie können zulassen, dass Benutzer die Steuerung erteilen oder anfordern, PowerPoint-Freigabe zulassen, ein Whiteboard hinzufügen und freigegebene Notizen zulassen.</span><span class="sxs-lookup"><span data-stu-id="bd336-106">You can let users give or request control, allow PowerPoint sharing, add a whiteboard, and allow shared notes.</span></span> <span data-ttu-id="bd336-107">Sie können auch konfigurieren, ob anonyme oder externe Benutzer die Steuerung des freigegebenen Bildschirms anfordern können.</span><span class="sxs-lookup"><span data-stu-id="bd336-107">You can also configure whether anonymous or external users can request control of the shared screen.</span></span>

<span data-ttu-id="bd336-108">Wenn Sie die Bildschirmfreigabe konfigurieren möchten, erstellen Sie eine neue Besprechungsrichtlinie, und weisen Sie diese den Benutzern zu, die Sie verwalten möchten.</span><span class="sxs-lookup"><span data-stu-id="bd336-108">To configure screen sharing, you create a new meetings policy and then assign it to the users you want to manage.</span></span>

<span data-ttu-id="bd336-109">**Im Microsoft Teams Admin Center**</span><span class="sxs-lookup"><span data-stu-id="bd336-109">**In the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="bd336-110">Wählen \*\*\*\* > Sie**Besprechungsrichtlinien**für Besprechungen aus.</span><span class="sxs-lookup"><span data-stu-id="bd336-110">Select **Meetings** > **Meeting policies**.</span></span>

    ![Screenshot mit ausgewählten Besprechungsrichtlinien](media/configure-desktop-sharing-image1.png)

2. <span data-ttu-id="bd336-112">Wählen Sie auf der Seite **Besprechungsrichtlinien** die Option **neue Richtlinie**aus.</span><span class="sxs-lookup"><span data-stu-id="bd336-112">On the **Meeting policies** page, select **New policy**.</span></span>

    ![Screenshot mit der Nachricht "Besprechungsrichtlinien"](media/configure-desktop-sharing-image2.png)

3. <span data-ttu-id="bd336-114">Geben Sie Ihrer Richtlinie einen eindeutigen Titel, und geben Sie eine kurze Beschreibung ein.</span><span class="sxs-lookup"><span data-stu-id="bd336-114">Give your policy a unique title and enter a brief description.</span></span>

4. <span data-ttu-id="bd336-115">Wählen Sie unter **Inhaltsfreigabe**einen **Bildschirmfreigabe Modus** aus der Dropdownliste aus:</span><span class="sxs-lookup"><span data-stu-id="bd336-115">Under **Content sharing**, choose a **Screen sharing mode** from the drop-down list:</span></span>

   - <span data-ttu-id="bd336-116">**Ganzer Bildschirm** – ermöglicht Benutzern das Freigeben Ihres gesamten Desktops.</span><span class="sxs-lookup"><span data-stu-id="bd336-116">**Entire screen** – lets users share their entire desktop.</span></span>
   - <span data-ttu-id="bd336-117">**Einzelne Anwendung** – ermöglicht Benutzern, die Bildschirmfreigabe auf eine einzelne aktive Anwendung zu begrenzen.</span><span class="sxs-lookup"><span data-stu-id="bd336-117">**Single application** – lets users limit screen sharing to a single active application.</span></span>
   - <span data-ttu-id="bd336-118">**Deaktiviert** – deaktiviert die Bildschirmfreigabe.</span><span class="sxs-lookup"><span data-stu-id="bd336-118">**Disabled** – Turns off screen sharing.</span></span>

    ![Screenshot mit Optionen für den Freigabemodus](media/configure-desktop-sharing-image3.png)

5. <span data-ttu-id="bd336-120">Aktivieren oder deaktivieren Sie die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="bd336-120">Turn the following settings on or off:</span></span>

    - <span data-ttu-id="bd336-121">**Zulassen, dass ein Teilnehmer die Steuerung erteilt oder anfordert** – ermöglicht es Mitgliedern des Teams, die Steuerung des Desktops oder der Anwendung des Referenten zu erteilen oder anzufordern.</span><span class="sxs-lookup"><span data-stu-id="bd336-121">**Allow a participant to give or request control** – lets members of the team give or request control of the presenter’s desktop or application.</span></span>
    - <span data-ttu-id="bd336-122">**Einem externen Teilnehmer erlauben, die Kontrolle zu erteilen oder anzufordern** – ermöglicht es Gästen und externen (verbundenen) Benutzern, die Steuerung des Desktops oder der Anwendung des Referenten zu erteilen oder anzufordern.</span><span class="sxs-lookup"><span data-stu-id="bd336-122">**Allow an external participant to give or request control** – lets guests and external (federated) users give or request control of the presenter’s desktop or application.</span></span>
    - <span data-ttu-id="bd336-123">**PowerPoint-Freigabe zulassen** – ermöglicht Benutzern das Erstellen von Besprechungen, mit denen PowerPoint-Präsentationen hochgeladen und freigegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="bd336-123">**Allow PowerPoint sharing** - lets users create meetings that allow PowerPoint presentations to be uploaded and shared.</span></span>
    - <span data-ttu-id="bd336-124">**Whiteboard zulassen** – ermöglicht Benutzern das Freigeben eines Whiteboards.</span><span class="sxs-lookup"><span data-stu-id="bd336-124">**Allow whiteboard** – lets users share a whiteboard.</span></span>
    - <span data-ttu-id="bd336-125">**Freigegebene Notizen zulassen** – ermöglicht Benutzern die Freigabe von Notizen.</span><span class="sxs-lookup"><span data-stu-id="bd336-125">**Allow shared notes** – lets users take shared notes.</span></span>

6. <span data-ttu-id="bd336-126">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="bd336-126">Click **Save**.</span></span>

## <a name="use-powershell-to-configure-shared-desktop"></a><span data-ttu-id="bd336-127">Verwenden von PowerShell zum Konfigurieren des freigegebenen Desktops</span><span class="sxs-lookup"><span data-stu-id="bd336-127">Use PowerShell to configure shared desktop</span></span>

<span data-ttu-id="bd336-128">Sie können auch das Cmdlet " [Satz-CsTeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) " verwenden, um die Desktopfreigabe zu steuern.</span><span class="sxs-lookup"><span data-stu-id="bd336-128">You can also use the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) cmdlet to control desktop sharing.</span></span> <span data-ttu-id="bd336-129">Setzen Sie die folgenden Parameter:</span><span class="sxs-lookup"><span data-stu-id="bd336-129">Set the following parameters:</span></span>

- <span data-ttu-id="bd336-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bd336-130">Description</span></span>
- <span data-ttu-id="bd336-131">ScreenSharingMode</span><span class="sxs-lookup"><span data-stu-id="bd336-131">ScreenSharingMode</span></span>
- <span data-ttu-id="bd336-132">AllowParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="bd336-132">AllowParticipantGiveRequestControl</span></span>
- <span data-ttu-id="bd336-133">AllowExternalParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="bd336-133">AllowExternalParticipantGiveRequestControl</span></span>
- <span data-ttu-id="bd336-134">AllowPowerPointSharing</span><span class="sxs-lookup"><span data-stu-id="bd336-134">AllowPowerPointSharing</span></span>
- <span data-ttu-id="bd336-135">AllowWhiteboard</span><span class="sxs-lookup"><span data-stu-id="bd336-135">AllowWhiteboard</span></span>
- <span data-ttu-id="bd336-136">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="bd336-136">AllowSharedNotes</span></span>

<span data-ttu-id="bd336-137">[Weitere Informationen zur Verwendung des csTeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="bd336-137">[Learn more about using the csTeamsMeetingPolicy cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span></span>

