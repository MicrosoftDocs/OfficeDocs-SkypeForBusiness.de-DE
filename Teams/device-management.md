---
title: Verwalten von Geräten in Microsoft-Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 11/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: kelsawi
f1keywords: ms.teamsadmincenter.devicemanagement.overview
description: Erfahren Sie, wie mit Teams in Ihrer Organisation verwendeten Geräte verwalten.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 97fd4b8d7f613c6d3f435f2d505bbd2cf99d4b10
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2018
ms.locfileid: "26531777"
---
# <a name="manage-your-devices-in-microsoft-teams"></a><span data-ttu-id="6cb38-103">Verwalten von Geräten in Microsoft-Teams</span><span class="sxs-lookup"><span data-stu-id="6cb38-103">Manage your devices in Microsoft Teams</span></span>

 <span data-ttu-id="6cb38-104">Als Administrator verwalten Sie alle Geräte mit Teams in Ihrer Organisation aus dem Microsoft-Teams & Skype für Business-Verwaltungskonsole verwendet.</span><span class="sxs-lookup"><span data-stu-id="6cb38-104">As an admin, you manage all devices used with Teams in your organization from the Microsoft Teams & Skype for Business admin center.</span></span> <span data-ttu-id="6cb38-105">Anzeigen und Verwalten der Geräteübersicht für Ihre Organisation, und führen Aufgaben wie das Update, neu und Monitordiagnose für Geräte.</span><span class="sxs-lookup"><span data-stu-id="6cb38-105">You can view and manage the device inventory for your organization and do tasks such as update, restart, and monitor diagnostics for devices.</span></span> <span data-ttu-id="6cb38-106">Sie können auch ein Gerät oder Gerätegruppen Konfigurationsprofile zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="6cb38-106">You can also create and assign configuration profiles to a device or groups of devices.</span></span> 

## <a name="what-devices-can-you-manage"></a><span data-ttu-id="6cb38-107">Welche Geräte können Sie verwalten?</span><span class="sxs-lookup"><span data-stu-id="6cb38-107">What devices can you manage?</span></span>
<span data-ttu-id="6cb38-108">Geräte müssen für Teams zertifiziert und Teams registriert werden.</span><span class="sxs-lookup"><span data-stu-id="6cb38-108">Devices must be certified for Teams and enrolled in Teams.</span></span> <span data-ttu-id="6cb38-109">Ein Gerät wird automatisch beim ersten registriert, die ein Benutzer bei Teams auf dem Gerät anmeldet.</span><span class="sxs-lookup"><span data-stu-id="6cb38-109">A device is automatically enrolled the first time a user signs in to Teams on the device.</span></span> 

> [!NOTE]
> <span data-ttu-id="6cb38-110">Wenn Sie Microsoft Intune verfügen, werden automatisch Geräte Intune registriert.</span><span class="sxs-lookup"><span data-stu-id="6cb38-110">If you have Microsoft Intune, devices are automatically enrolled in Intune.</span></span> <span data-ttu-id="6cb38-111">Nachdem ein Gerät registriert, Gerät Compliance bestätigt wurde, und bedingte Zugriffsrichtlinien auf das Gerät angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="6cb38-111">After a device is enrolled, device compliance is confirmed and conditional access policies are applied to the device.</span></span> 

## <a name="manage-devices-in-teams"></a><span data-ttu-id="6cb38-112">Verwalten von Geräten in Teams</span><span class="sxs-lookup"><span data-stu-id="6cb38-112">Manage devices in Teams</span></span>

![Teams-Logo-30x30.png](media/teams-logo-30x30.png) <span data-ttu-id="6cb38-114">Verwenden die Microsoft-Teams & Skype für Business Administrationscenter</span><span class="sxs-lookup"><span data-stu-id="6cb38-114">Using the Microsoft Teams & Skype for Business admin center</span></span>

1. <span data-ttu-id="6cb38-115">Wechseln Sie im linken Navigationsbereich auf **Geräte** > **Geräte verwalten**.</span><span class="sxs-lookup"><span data-stu-id="6cb38-115">In the left navigation, go to **Devices** > **Manage Devices**.</span></span>
2. <span data-ttu-id="6cb38-116">Wählen Sie **alle Geräte**aus.</span><span class="sxs-lookup"><span data-stu-id="6cb38-116">Select **All devices**.</span></span>  

 <span data-ttu-id="6cb38-117">Von hier aus können Sie anzeigen und verwalten alle Geräte in Ihrer Organisation in Teams registriert.</span><span class="sxs-lookup"><span data-stu-id="6cb38-117">From here, you can view and manage all devices enrolled in Teams in your organization.</span></span> <span data-ttu-id="6cb38-118">Informationen, die Sie für jedes Gerät sehen enthält Gerätename, Hersteller, Modell, Benutzer, Status, Aktion, letzten angezeigt und Verlauf.</span><span class="sxs-lookup"><span data-stu-id="6cb38-118">Information that you'll see for each device includes device name, manufacturer, model, user, status, action, last seen, and history.</span></span> <span data-ttu-id="6cb38-119">Sie können die Ansicht, um die Informationen anzeigen, die Ihren Anforderungen entspricht anpassen.</span><span class="sxs-lookup"><span data-stu-id="6cb38-119">You can customize the view to show the information that fits your needs.</span></span>

 <span data-ttu-id="6cb38-120">Nachfolgend finden Sie einige Beispiele, wie Sie Teams Geräte in Ihrer Organisation verwalten können.</span><span class="sxs-lookup"><span data-stu-id="6cb38-120">Here's some examples of how you can manage Teams devices in your organization.</span></span>  
    
|<span data-ttu-id="6cb38-121">Hierzu...</span><span class="sxs-lookup"><span data-stu-id="6cb38-121">To do this...</span></span>  |<span data-ttu-id="6cb38-122">Aktion...</span><span class="sxs-lookup"><span data-stu-id="6cb38-122">Do this</span></span> |
|---------|---------|
|<span data-ttu-id="6cb38-123">Geräteinformationen ändern</span><span class="sxs-lookup"><span data-stu-id="6cb38-123">Change device information</span></span>   | <span data-ttu-id="6cb38-124">Wählen Sie ein Gerät > **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="6cb38-124">Select a device > **Edit**.</span></span> <span data-ttu-id="6cb38-125">Sie können Bearbeiten der Details wie Gerätename, Benutzerinformationen, Asset-Tags und Notizen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="6cb38-125">You can edit details such as device name, user information, asset tag, and add notes.</span></span>     |
|<span data-ttu-id="6cb38-126">Verwalten von Softwareupdates</span><span class="sxs-lookup"><span data-stu-id="6cb38-126">Manage software updates</span></span>   |<span data-ttu-id="6cb38-127">Wählen Sie ein Gerät > **Update**.</span><span class="sxs-lookup"><span data-stu-id="6cb38-127">Select a device > **Update**.</span></span> <span data-ttu-id="6cb38-128">Sie können die Liste der Software- und Firmwareupdates Updates für das Gerät anzeigen, und wählen Sie zur Installation der Updates.</span><span class="sxs-lookup"><span data-stu-id="6cb38-128">You can view the list of software and firmware updates available for the device and choose the updates to install.</span></span>    |
|<span data-ttu-id="6cb38-129">Neustart eines Geräts</span><span class="sxs-lookup"><span data-stu-id="6cb38-129">Restart a device</span></span>   |<span data-ttu-id="6cb38-130">Wählen Sie ein Gerät > **neu zu starten**.</span><span class="sxs-lookup"><span data-stu-id="6cb38-130">Select a device > **Restart**.</span></span>          |
|<span data-ttu-id="6cb38-131">Gerät-Historie anzeigen</span><span class="sxs-lookup"><span data-stu-id="6cb38-131">View device history</span></span>  | <span data-ttu-id="6cb38-132">Wählen Sie ein Gerät > **Verlauf**.</span><span class="sxs-lookup"><span data-stu-id="6cb38-132">Select a device > **History**.</span></span> <span data-ttu-id="6cb38-133">Sie können den Updateverlauf für das Gerät anzeigen.</span><span class="sxs-lookup"><span data-stu-id="6cb38-133">You can view the update history for the device.</span></span>     |
|<span data-ttu-id="6cb38-134">Ansicht Diagnose</span><span class="sxs-lookup"><span data-stu-id="6cb38-134">View diagnostics</span></span>  | <span data-ttu-id="6cb38-135">Wählen Sie ein Gerät > **Diagnose**.</span><span class="sxs-lookup"><span data-stu-id="6cb38-135">Select a device > **Diagnostics**.</span></span>        |

## <a name="use-configuration-profiles-in-teams"></a><span data-ttu-id="6cb38-136">Verwenden Sie Konfigurationsprofile in Teams</span><span class="sxs-lookup"><span data-stu-id="6cb38-136">Use configuration profiles in Teams</span></span>

<span data-ttu-id="6cb38-137">Verwenden Sie Konfigurationsprofile, um Einstellungen und Features für Teams Geräte in Ihrer Organisation zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="6cb38-137">Use configuration profiles to manage settings and features for Teams devices in your organization.</span></span> <span data-ttu-id="6cb38-138">Sie können erstellen oder Hochladen Konfigurationsprofile zum Einschließen von Einstellungen und Features zu aktivieren oder deaktivieren, und weisen Sie einem Profil ein Gerät oder Gruppen von Geräten.</span><span class="sxs-lookup"><span data-stu-id="6cb38-138">You can create or upload configuration profiles to include settings and features you want to enable or disable and then assign a profile to a device or groups of devices.</span></span> 

### <a name="create-a-configuration-profile"></a><span data-ttu-id="6cb38-139">Erstellen Sie ein Konfigurationsprofil</span><span class="sxs-lookup"><span data-stu-id="6cb38-139">Create a configuration profile</span></span>

![Teams-Logo-30x30.png](media/teams-logo-30x30.png) <span data-ttu-id="6cb38-141">Verwenden die Microsoft-Teams & Skype für Business Administrationscenter</span><span class="sxs-lookup"><span data-stu-id="6cb38-141">Using the Microsoft Teams & Skype for Business admin center</span></span>

1. <span data-ttu-id="6cb38-142">Wechseln Sie im linken Navigationsbereich auf **Geräte** > **Geräte verwalten**.</span><span class="sxs-lookup"><span data-stu-id="6cb38-142">In the left navigation, go to **Devices** > **Manage Devices**.</span></span>
2. <span data-ttu-id="6cb38-143">Wählen Sie **Konfigurationsprofile**aus, und wählen Sie dann auf **neues Konfigurationsprofil**.</span><span class="sxs-lookup"><span data-stu-id="6cb38-143">Select **Configuration profiles**, and then select **New configuration profile**.</span></span>
3. <span data-ttu-id="6cb38-144">Geben Sie einen Namen für das Profil, und wenn Sie möchten, fügen Sie eine benutzerfreundliche Beschreibung.</span><span class="sxs-lookup"><span data-stu-id="6cb38-144">Enter a name for the profile and if you want, add a friendly description.</span></span>
4. <span data-ttu-id="6cb38-145">Geben Sie die Einstellungen, die Sie für das Profil verwenden möchten, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="6cb38-145">Specify the settings you want for the profile, and then click **Save**.</span></span>

### <a name="assign-a-configuration-profile"></a><span data-ttu-id="6cb38-146">Zuweisen eines Konfigurationsprofils</span><span class="sxs-lookup"><span data-stu-id="6cb38-146">Assign a configuration profile</span></span>

![Teams-Logo-30x30.png](media/teams-logo-30x30.png) <span data-ttu-id="6cb38-148">Verwenden die Microsoft-Teams & Skype für Business Administrationscenter</span><span class="sxs-lookup"><span data-stu-id="6cb38-148">Using the Microsoft Teams & Skype for Business admin center</span></span>

1. <span data-ttu-id="6cb38-149">Wechseln Sie im linken Navigationsbereich auf **Geräte** > **Geräte verwalten**.</span><span class="sxs-lookup"><span data-stu-id="6cb38-149">In the left navigation, go to **Devices** > **Manage Devices**.</span></span>
2. <span data-ttu-id="6cb38-150">Wählen Sie **Konfigurationsprofil**aus, und klicken Sie dann unter **zugewiesen an** in das Profil, das Sie zuweisen möchten, klicken Sie auf den Link.</span><span class="sxs-lookup"><span data-stu-id="6cb38-150">Select **Configuration profile**, and then under **Assigned to** in the profile you want to assign, click the link.</span></span>  
3. <span data-ttu-id="6cb38-151">Suchen Sie und wählen Sie die Geräte, die Sie zuweisen möchten, klicken Sie im Bereich **Geräte zu einem Konfigurationsprofil zuweisen** .</span><span class="sxs-lookup"><span data-stu-id="6cb38-151">In the **Assign devices to a configuration profile** pane, search for and select the devices you want to assign.</span></span>
4. <span data-ttu-id="6cb38-152">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="6cb38-152">Click **Save**.</span></span>
