---
title: Konfigurieren der Desktopfreigabe in Microsoft Teams
author: LolaJacobsen
ms.author: Lolaj
manager: serdars
ms.reviewer: jastark
ms.date: 12/07/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Konfigurieren Sie eine besprechungsrichtlinie, damit die Benutzer ihren Desktop in Teams Chats oder Besprechungen freigeben können
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: fcc76f79d288844611e17154359e8c9c3ab4ed23
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2019
ms.locfileid: "29754768"
---
<a name="configure-desktop-sharing-in-microsoft-teams"></a><span data-ttu-id="839e0-103">Konfigurieren der Desktopfreigabe in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="839e0-103">Configure desktop sharing in Microsoft Teams</span></span>
============================================

<span data-ttu-id="839e0-104">Desktopfreigabe kann Benutzer eine Bildschirm oder app während einer Besprechung oder Chat darstellen.</span><span class="sxs-lookup"><span data-stu-id="839e0-104">Desktop sharing lets users present a screen or app during a meeting or chat.</span></span> <span data-ttu-id="839e0-105">Administratoren können Bildschirmfreigabe in Microsoft-Teams können Benutzer einen ganzen Bildschirm, einer app oder eine Datei freizugeben, konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="839e0-105">Admins can configure screen sharing in Microsoft Teams to let users share an entire screen, an app, or a file.</span></span> <span data-ttu-id="839e0-106">Sie können anderen Benutzern erteilen oder Steuerung anfordern, PowerPoint-Freigabe ermöglichen, ein Whiteboard hinzuzufügen und freigegebene Notizen zulassen.</span><span class="sxs-lookup"><span data-stu-id="839e0-106">You can let users give or request control, allow PowerPoint sharing, add a whiteboard, and allow shared notes.</span></span> <span data-ttu-id="839e0-107">Sie können auch konfigurieren, ob anonyme oder externe Benutzer Steuerung des freigegebenen Bildschirms anfordern können.</span><span class="sxs-lookup"><span data-stu-id="839e0-107">You can also configure whether anonymous or external users can request control of the shared screen.</span></span>

<span data-ttu-id="839e0-108">So konfigurieren die Bildschirmfreigabe, erstellen Sie eine neue Richtlinie für Besprechungen und weisen Sie es den Benutzern, den Sie verwalten möchten.</span><span class="sxs-lookup"><span data-stu-id="839e0-108">To configure screen sharing, you create a new meetings policy and then assign it to the users you want to manage.</span></span>

<span data-ttu-id="839e0-109">**In der Verwaltungskonsole von Microsoft-Teams**</span><span class="sxs-lookup"><span data-stu-id="839e0-109">**In the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="839e0-110">Wählen Sie **Besprechungen** > **Besprechungsrichtlinien**.</span><span class="sxs-lookup"><span data-stu-id="839e0-110">Select **Meetings** > **Meeting policies**.</span></span>

    ![Wählen Sie Besprechungsrichtlinien](media/configure-desktop-sharing-image1.png)

2. <span data-ttu-id="839e0-112">Wählen Sie auf der Seite **Besprechungsrichtlinien** **neue Richtlinie**aus.</span><span class="sxs-lookup"><span data-stu-id="839e0-112">On the **Meeting policies** page, select **New policy**.</span></span>

    ![Wählen Sie neue Richtlinie](media/configure-desktop-sharing-image2.png)

3. <span data-ttu-id="839e0-114">Geben Sie Ihre Richtlinie einen eindeutigen Titel, und geben Sie eine kurze Beschreibung ein.</span><span class="sxs-lookup"><span data-stu-id="839e0-114">Give your policy a unique title and enter a brief description.</span></span>

4. <span data-ttu-id="839e0-115">Wählen Sie unter **gemeinsame Nutzung von Inhalten**aus der Dropdown Liste einer **Bildschirmfreigabe Modus** :</span><span class="sxs-lookup"><span data-stu-id="839e0-115">Under **Content sharing**, choose a **Screen sharing mode** from the drop-down list:</span></span>

   - <span data-ttu-id="839e0-116">**Gesamten Bildschirm** – können Benutzer ihren gesamten Desktop freigeben.</span><span class="sxs-lookup"><span data-stu-id="839e0-116">**Entire screen** – lets users share their entire desktop.</span></span>
   - <span data-ttu-id="839e0-117">**Einzelne Anwendung** – ermöglicht Benutzern Grenzwert Bildschirmfreigabe auf eine einzelne aktive Anwendung.</span><span class="sxs-lookup"><span data-stu-id="839e0-117">**Single application** – lets users limit screen sharing to a single active application.</span></span>
   - <span data-ttu-id="839e0-118">**Disabled** – deaktiviert Bildschirmfreigabe.</span><span class="sxs-lookup"><span data-stu-id="839e0-118">**Disabled** – Turns off screen sharing.</span></span>

    ![Wählen Sie einen Modus für die Bildschirmfreigabe](media/configure-desktop-sharing-image3.png)

5. <span data-ttu-id="839e0-120">Aktivieren Sie oder Deaktivieren der folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="839e0-120">Turn the following settings on or off:</span></span>

    - <span data-ttu-id="839e0-121">**Ermöglichen ein Teilnehmers zu gewähren oder Anfordern der Steuerung** – können Mitglieder des Teams gewähren oder Anfordern der Steuerung des Desktops der Referent oder der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="839e0-121">**Allow a participant to give or request control** – lets members of the team give or request control of the presenter’s desktop or application.</span></span>
    - <span data-ttu-id="839e0-122">Gäste können **einen externen Teilnehmer zu gewähren oder Anfordern der Steuerung zulassen** – und externe (Verbundbenutzer) gewähren oder Anfordern der Steuerung des Desktops oder der Anwendung der Referent.</span><span class="sxs-lookup"><span data-stu-id="839e0-122">**Allow an external participant to give or request control** – lets guests and external (federated) users give or request control of the presenter’s desktop or application.</span></span>
    - <span data-ttu-id="839e0-123">**Zulassen von PowerPoint-Freigabe** - können Benutzer Besprechungen erstellen, mit denen PowerPoint-Präsentationen hochgeladen und gemeinsam genutzt werden können.</span><span class="sxs-lookup"><span data-stu-id="839e0-123">**Allow PowerPoint sharing** - lets users create meetings that allow PowerPoint presentations to be uploaded and shared.</span></span>
    - <span data-ttu-id="839e0-124">**Whiteboard zulassen** – ermöglicht dem Benutzer, die ein Whiteboard zu teilen.</span><span class="sxs-lookup"><span data-stu-id="839e0-124">**Allow whiteboard** – lets users share a whiteboard.</span></span>
    - <span data-ttu-id="839e0-125">**Freigegebene Notizen zulassen** – ermöglicht Benutzern das freigegebene Notizen machen.</span><span class="sxs-lookup"><span data-stu-id="839e0-125">**Allow shared notes** – lets users take shared notes.</span></span>

6. <span data-ttu-id="839e0-126">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="839e0-126">Click **Save**.</span></span>

## <a name="use-powershell-to-configure-shared-desktop"></a><span data-ttu-id="839e0-127">Verwenden von PowerShell zum Konfigurieren des freigegebenen Desktops</span><span class="sxs-lookup"><span data-stu-id="839e0-127">Use PowerShell to configure shared desktop</span></span>

<span data-ttu-id="839e0-128">Sie können auch das Cmdlet [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) zur Steuerung der Desktopfreigabe verwenden.</span><span class="sxs-lookup"><span data-stu-id="839e0-128">You can also use the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) cmdlet to control desktop sharing.</span></span> <span data-ttu-id="839e0-129">Festlegen Sie die folgenden Parameter:</span><span class="sxs-lookup"><span data-stu-id="839e0-129">Set the following parameters:</span></span>

- <span data-ttu-id="839e0-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="839e0-130">Description</span></span>
- <span data-ttu-id="839e0-131">ScreenSharingMode</span><span class="sxs-lookup"><span data-stu-id="839e0-131">ScreenSharingMode</span></span>
- <span data-ttu-id="839e0-132">AllowParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="839e0-132">AllowParticipantGiveRequestControl</span></span>
- <span data-ttu-id="839e0-133">AllowExternalParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="839e0-133">AllowExternalParticipantGiveRequestControl</span></span>
- <span data-ttu-id="839e0-134">AllowPowerPointSharing</span><span class="sxs-lookup"><span data-stu-id="839e0-134">AllowPowerPointSharing</span></span>
- <span data-ttu-id="839e0-135">AllowWhiteboard</span><span class="sxs-lookup"><span data-stu-id="839e0-135">AllowWhiteboard</span></span>
- <span data-ttu-id="839e0-136">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="839e0-136">AllowSharedNotes</span></span>

<span data-ttu-id="839e0-137">[Erfahren Sie mehr über die Verwendung des CsTeamsMeetingPolicy-Cmdlets](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="839e0-137">[Learn more about using the csTeamsMeetingPolicy cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span></span>

