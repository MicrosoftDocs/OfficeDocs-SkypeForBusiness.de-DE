---
title: Konfigurieren der Desktopfreigabe in Microsoft Teams
author: LolaJacobsen
ms.author: Lolaj
manager: serdars
ms.reviewer: jastark
ms.date: 03/22/2019
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Konfigurieren einer Besprechungsrichtlinie, damit Benutzer ihre Desktops in Teams-Chats oder Besprechungen freigeben können
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f36804fc4d7c28f08ca383ddb09f22ee52f804e7
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236933"
---
<a name="configure-desktop-sharing-in-microsoft-teams"></a><span data-ttu-id="6354a-103">Konfigurieren der Desktopfreigabe in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6354a-103">Configure desktop sharing in Microsoft Teams</span></span>
============================================

<span data-ttu-id="6354a-104">Die Desktopfreigabe ermöglicht es Benutzern, während einer Besprechung oder eines Chats einen Bildschirm oder eine App anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="6354a-104">Desktop sharing lets users present a screen or app during a meeting or chat.</span></span> <span data-ttu-id="6354a-105">Administratoren können die Bildschirmfreigabe in Microsoft Teams so konfigurieren, dass Benutzer einen gesamten Bildschirm, eine App oder eine Datei freigeben können.</span><span class="sxs-lookup"><span data-stu-id="6354a-105">Admins can configure screen sharing in Microsoft Teams to let users share an entire screen, an app, or a file.</span></span> <span data-ttu-id="6354a-106">Sie können zulassen, dass Benutzer die Steuerung ermöglichen oder anfordern können, die PowerPoint-Freigabe zulassen, ein Whiteboard hinzufügen und das Freigebe zulassen.</span><span class="sxs-lookup"><span data-stu-id="6354a-106">You can let users give or request control, allow PowerPoint sharing, add a whiteboard, and allow shared notes.</span></span> <span data-ttu-id="6354a-107">Sie können auch festlegen, ob anonyme oder externe Benutzer die Steuerung des freigegebenen Bildschirms anfordern können.</span><span class="sxs-lookup"><span data-stu-id="6354a-107">You can also configure whether anonymous or external users can request control of the shared screen.</span></span>

<span data-ttu-id="6354a-108">Um die Bildschirmfreigabe zu konfigurieren, erstellen Sie eine neue Besprechungsrichtlinie und weisen Sie diese dann den Benutzern zu, die Sie verwalten möchten.</span><span class="sxs-lookup"><span data-stu-id="6354a-108">To configure screen sharing, you create a new meetings policy and then assign it to the users you want to manage.</span></span>

<span data-ttu-id="6354a-109">**Im Microsoft Teams Admin Center**</span><span class="sxs-lookup"><span data-stu-id="6354a-109">**Manage teams in the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="6354a-110">Wählen Sie **Besprechungen** > **Besprechungsrichtlinien**.</span><span class="sxs-lookup"><span data-stu-id="6354a-110">Select **Meetings** > **Meeting policies**.</span></span>

    ![Screenshot mit ausgewählten Besprechungsrichtlinien](media/configure-desktop-sharing-image1.png)

2. <span data-ttu-id="6354a-112">Wählen Sie auf der Seite **Besprechungsrichtlinien** die Option **Neue Richtlinie** aus.</span><span class="sxs-lookup"><span data-stu-id="6354a-112">On the **Meeting policies** page, select **New policy**.</span></span>

    ![Screenshot mit der Nachricht "Besprechungsrichtlinien"](media/configure-desktop-sharing-image2.png)

3. <span data-ttu-id="6354a-114">Weisen Sie Ihrer Richtlinie einen eindeutigen Titel zu und geben Sie eine kurze Beschreibung ein.</span><span class="sxs-lookup"><span data-stu-id="6354a-114">Give your policy a unique title and enter a brief description.</span></span>

4. <span data-ttu-id="6354a-115">Wählen Sie aus der Dropdownliste unter **Inhaltsfreigabe** die gewünschte Option für den **Bildschirmfreigabemodus** aus:</span><span class="sxs-lookup"><span data-stu-id="6354a-115">Under **Content sharing**, choose a **Screen sharing mode** from the drop-down list:</span></span>

   - <span data-ttu-id="6354a-116">**Gesamter Bildschirm**: Ermöglicht Benutzern die Freigabe des gesamten Bildschirms.</span><span class="sxs-lookup"><span data-stu-id="6354a-116">**Entire screen** – lets users share their entire desktop.</span></span>
   - <span data-ttu-id="6354a-117">**Einzelne Anwendung**: Ermöglicht Benutzern die Beschränkung der Bildschirmfreigabe auf eine einzelne aktive Anwendung.</span><span class="sxs-lookup"><span data-stu-id="6354a-117">**Single application** – lets users limit screen sharing to a single active application.</span></span>
   - <span data-ttu-id="6354a-118">**Deaktiviert**: Deaktiviert die Bildschirmfreigabe.</span><span class="sxs-lookup"><span data-stu-id="6354a-118">**Disabled** – Turns off screen sharing.</span></span>

    ![Screenshot mit Optionen für den Freigabemodus](media/configure-desktop-sharing-image3.png)

5. <span data-ttu-id="6354a-120">Aktivieren oder deaktivieren Sie die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="6354a-120">Turn the following settings on or off:</span></span>

    - <span data-ttu-id="6354a-121">**Teilnehmer können Kontrolle zulassen oder anfordern**: Ermöglicht Mitgliedern des Teams die Steuerung des Desktops oder der Anwendung des Referenten zuzulassen oder anzufordern.</span><span class="sxs-lookup"><span data-stu-id="6354a-121">**Allow a participant to give or request control** – lets members of the team give or request control of the presenter’s desktop or application.</span></span>
    - <span data-ttu-id="6354a-122">**Externe Teilnehmer können Kontrolle zulassen oder anfordern**: Ermöglicht Gästen und externen (Partner-) Benutzern die Steuerung des Desktops oder der Anwendung des Referenten zuzulassen oder anzufordern.</span><span class="sxs-lookup"><span data-stu-id="6354a-122">**Allow an external participant to give or request control** – lets guests and external (federated) users give or request control of the presenter’s desktop or application.</span></span>
    - <span data-ttu-id="6354a-123">**PowerPoint-Freigabe zulassen**: Ermöglicht Benutzern das Erstellen von Besprechungen, die das Hochladen und Freigeben von PowerPoint-Präsentationen zulassen.</span><span class="sxs-lookup"><span data-stu-id="6354a-123">**Allow PowerPoint sharing** - lets users create meetings that allow PowerPoint presentations to be uploaded and shared.</span></span>
    - <span data-ttu-id="6354a-124">**Whiteboard zulassen**: Ermöglicht Benutzern die Freigabe eines Whiteboards.</span><span class="sxs-lookup"><span data-stu-id="6354a-124">**Allow whiteboard** – lets users share a whiteboard.</span></span>
    - <span data-ttu-id="6354a-125">**Freigabe von Notizen zulassen**: Ermöglicht Benutzern, freigegebene Notizen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="6354a-125">**Allow shared notes** – lets users take shared notes.</span></span>

6. <span data-ttu-id="6354a-126">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="6354a-126">Click **Save**.</span></span>

## <a name="use-powershell-to-configure-shared-desktop"></a><span data-ttu-id="6354a-127">Verwenden von PowerShell zum Konfigurieren des freigegebenen Desktops</span><span class="sxs-lookup"><span data-stu-id="6354a-127">Use PowerShell to configure shared desktop</span></span>

<span data-ttu-id="6354a-128">Sie können auch das Cmdlet [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/de-DE/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) verwenden, um die Desktopfreigabe zu steuern.</span><span class="sxs-lookup"><span data-stu-id="6354a-128">You can also use the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) cmdlet to control desktop sharing.</span></span> <span data-ttu-id="6354a-129">Legen Sie die folgenden Parameter fest:</span><span class="sxs-lookup"><span data-stu-id="6354a-129">Set the following parameters:</span></span>

- <span data-ttu-id="6354a-130">Description</span><span class="sxs-lookup"><span data-stu-id="6354a-130">Description</span></span>
- <span data-ttu-id="6354a-131">ScreenSharingMode</span><span class="sxs-lookup"><span data-stu-id="6354a-131">ScreenSharingMode</span></span>
- <span data-ttu-id="6354a-132">AllowParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="6354a-132">AllowParticipantGiveRequestControl</span></span>
- <span data-ttu-id="6354a-133">AllowExternalParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="6354a-133">AllowExternalParticipantGiveRequestControl</span></span>
- <span data-ttu-id="6354a-134">AllowPowerPointSharing</span><span class="sxs-lookup"><span data-stu-id="6354a-134">AllowPowerPointSharing</span></span>
- <span data-ttu-id="6354a-135">AllowWhiteboard</span><span class="sxs-lookup"><span data-stu-id="6354a-135">AllowWhiteboard</span></span>
- <span data-ttu-id="6354a-136">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="6354a-136">AllowSharedNotes</span></span>

<span data-ttu-id="6354a-137">
  [Erfahren Sie mehr über das csTeamsMeetingPolicy-Cmdlet ](https://docs.microsoft.com/de-DE/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="6354a-137">[Learn more about using the csTeamsMeetingPolicy cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span></span>

