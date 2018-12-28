---
title: Verwalten Ihrer Geräte in Microsoft Teams
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
ms.openlocfilehash: dff307b1bd4ede3e8999a78a5e6a8df36b8a1411
ms.sourcegitcommit: a378848c5aeb8e2b25300024318de792454d905b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/28/2018
ms.locfileid: "27458550"
---
# <a name="manage-your-devices-in-microsoft-teams"></a><span data-ttu-id="d3203-103">Verwalten Ihrer Geräte in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d3203-103">Manage your devices in Microsoft Teams</span></span>

 <span data-ttu-id="d3203-104">Als Administrator verwalten Sie alle Geräte mit Teams in Ihrer Organisation aus dem Microsoft-Teams & Skype für Business-Verwaltungskonsole verwendet.</span><span class="sxs-lookup"><span data-stu-id="d3203-104">As an admin, you manage all devices used with Teams in your organization from the Microsoft Teams & Skype for Business admin center.</span></span> <span data-ttu-id="d3203-105">Anzeigen und Verwalten der Geräteübersicht für Ihre Organisation, und führen Aufgaben wie das Update, neu und Monitordiagnose für Geräte.</span><span class="sxs-lookup"><span data-stu-id="d3203-105">You can view and manage the device inventory for your organization and do tasks such as update, restart, and monitor diagnostics for devices.</span></span> <span data-ttu-id="d3203-106">Sie können auch ein Gerät oder Gerätegruppen Konfigurationsprofile zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="d3203-106">You can also create and assign configuration profiles to a device or groups of devices.</span></span> 

## <a name="what-devices-can-you-manage"></a><span data-ttu-id="d3203-107">Welche Geräte können Sie verwalten?</span><span class="sxs-lookup"><span data-stu-id="d3203-107">What devices can you manage?</span></span>
<span data-ttu-id="d3203-108">Geräte müssen für Teams zertifiziert und Teams registriert werden.</span><span class="sxs-lookup"><span data-stu-id="d3203-108">Devices must be certified for Teams and enrolled in Teams.</span></span> <span data-ttu-id="d3203-109">Ein Gerät wird automatisch beim ersten registriert, die ein Benutzer bei Teams auf dem Gerät anmeldet.</span><span class="sxs-lookup"><span data-stu-id="d3203-109">A device is automatically enrolled the first time a user signs in to Teams on the device.</span></span> <span data-ttu-id="d3203-110">Eine Liste mit zertifizierten Geräte, die verwaltet werden können, finden Sie unter [Konferenz Mobiltelefone](https://products.office.com/en-us/microsoft-teams/across-devices/devices/category?categoryid=ddb1bc66-7499-4823-8d2b-a2c6dbe4f716) und [herkömmliche Telefone](https://products.office.com/en-us/microsoft-teams/across-devices/devices/category?categoryid=c6536b33-f554-4b55-bd3d-c98733ebc017&page=1&filters=).</span><span class="sxs-lookup"><span data-stu-id="d3203-110">For a list of certified devices that can be managed, see [Conference phones](https://products.office.com/en-us/microsoft-teams/across-devices/devices/category?categoryid=ddb1bc66-7499-4823-8d2b-a2c6dbe4f716) and [Desk phones](https://products.office.com/en-us/microsoft-teams/across-devices/devices/category?categoryid=c6536b33-f554-4b55-bd3d-c98733ebc017&page=1&filters=).</span></span>

> [!NOTE]
> <span data-ttu-id="d3203-111">Wenn Sie Microsoft Intune verfügen, werden automatisch Geräte Intune registriert.</span><span class="sxs-lookup"><span data-stu-id="d3203-111">If you have Microsoft Intune, devices are automatically enrolled in Intune.</span></span> <span data-ttu-id="d3203-112">Nachdem ein Gerät registriert, Gerät Compliance bestätigt wurde, und bedingte Zugriffsrichtlinien auf das Gerät angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="d3203-112">After a device is enrolled, device compliance is confirmed and conditional access policies are applied to the device.</span></span> 

## <a name="manage-devices-in-teams"></a><span data-ttu-id="d3203-113">Verwalten von Geräten in Teams</span><span class="sxs-lookup"><span data-stu-id="d3203-113">Manage devices in Teams</span></span>

![Teams-Logo-30x30.png](media/teams-logo-30x30.png) <span data-ttu-id="d3203-115">Verwenden die Microsoft-Teams & Skype für Business Administrationscenter</span><span class="sxs-lookup"><span data-stu-id="d3203-115">Using the Microsoft Teams & Skype for Business admin center</span></span>

1. <span data-ttu-id="d3203-116">Wechseln Sie im linken Navigationsbereich auf **Geräte** > **Geräte verwalten**.</span><span class="sxs-lookup"><span data-stu-id="d3203-116">In the left navigation, go to **Devices** > **Manage Devices**.</span></span>
2. <span data-ttu-id="d3203-117">Wählen Sie **alle Geräte**aus.</span><span class="sxs-lookup"><span data-stu-id="d3203-117">Select **All devices**.</span></span>  

 <span data-ttu-id="d3203-118">Von hier aus können Sie anzeigen und verwalten alle Geräte in Ihrer Organisation in Teams registriert.</span><span class="sxs-lookup"><span data-stu-id="d3203-118">From here, you can view and manage all devices enrolled in Teams in your organization.</span></span> <span data-ttu-id="d3203-119">Informationen, die Sie für jedes Gerät sehen enthält Gerätename, Hersteller, Modell, Benutzer, Status, Aktion, letzten angezeigt und Verlauf.</span><span class="sxs-lookup"><span data-stu-id="d3203-119">Information that you'll see for each device includes device name, manufacturer, model, user, status, action, last seen, and history.</span></span> <span data-ttu-id="d3203-120">Sie können die Ansicht, um die Informationen anzeigen, die Ihren Anforderungen entspricht anpassen.</span><span class="sxs-lookup"><span data-stu-id="d3203-120">You can customize the view to show the information that fits your needs.</span></span>

 <span data-ttu-id="d3203-121">Nachfolgend finden Sie einige Beispiele, wie Sie Teams Geräte in Ihrer Organisation verwalten können.</span><span class="sxs-lookup"><span data-stu-id="d3203-121">Here's some examples of how you can manage Teams devices in your organization.</span></span>  
    
|<span data-ttu-id="d3203-122">Hierzu...</span><span class="sxs-lookup"><span data-stu-id="d3203-122">To do this...</span></span>  |<span data-ttu-id="d3203-123">Aktion...</span><span class="sxs-lookup"><span data-stu-id="d3203-123">Do this</span></span> |
|---------|---------|
|<span data-ttu-id="d3203-124">Geräteinformationen ändern</span><span class="sxs-lookup"><span data-stu-id="d3203-124">Change device information</span></span>   | <span data-ttu-id="d3203-125">Wählen Sie ein Gerät > **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="d3203-125">Select a device > **Edit**.</span></span> <span data-ttu-id="d3203-126">Sie können Bearbeiten der Details wie Gerätename, Benutzerinformationen, Asset-Tags und Notizen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="d3203-126">You can edit details such as device name, user information, asset tag, and add notes.</span></span>     |
|<span data-ttu-id="d3203-127">Verwalten von Softwareupdates</span><span class="sxs-lookup"><span data-stu-id="d3203-127">Manage software updates</span></span>   |<span data-ttu-id="d3203-128">Wählen Sie ein Gerät > **Update**.</span><span class="sxs-lookup"><span data-stu-id="d3203-128">Select a device > **Update**.</span></span> <span data-ttu-id="d3203-129">Sie können die Liste der Software- und Firmwareupdates Updates für das Gerät anzeigen, und wählen Sie zur Installation der Updates.</span><span class="sxs-lookup"><span data-stu-id="d3203-129">You can view the list of software and firmware updates available for the device and choose the updates to install.</span></span>    |
|<span data-ttu-id="d3203-130">Neustart eines Geräts</span><span class="sxs-lookup"><span data-stu-id="d3203-130">Restart a device</span></span>   |<span data-ttu-id="d3203-131">Wählen Sie ein Gerät > **neu zu starten**.</span><span class="sxs-lookup"><span data-stu-id="d3203-131">Select a device > **Restart**.</span></span>          |
|<span data-ttu-id="d3203-132">Gerät-Historie anzeigen</span><span class="sxs-lookup"><span data-stu-id="d3203-132">View device history</span></span>  | <span data-ttu-id="d3203-133">Wählen Sie ein Gerät > **Verlauf**.</span><span class="sxs-lookup"><span data-stu-id="d3203-133">Select a device > **History**.</span></span> <span data-ttu-id="d3203-134">Sie können den Updateverlauf für das Gerät anzeigen.</span><span class="sxs-lookup"><span data-stu-id="d3203-134">You can view the update history for the device.</span></span>     |
|<span data-ttu-id="d3203-135">Ansicht Diagnose</span><span class="sxs-lookup"><span data-stu-id="d3203-135">View diagnostics</span></span>  | <span data-ttu-id="d3203-136">Wählen Sie ein Gerät > **Diagnose**.</span><span class="sxs-lookup"><span data-stu-id="d3203-136">Select a device > **Diagnostics**.</span></span>        |

## <a name="use-configuration-profiles-in-teams"></a><span data-ttu-id="d3203-137">Verwenden Sie Konfigurationsprofile in Teams</span><span class="sxs-lookup"><span data-stu-id="d3203-137">Use configuration profiles in Teams</span></span>

<span data-ttu-id="d3203-138">Verwenden Sie Konfigurationsprofile, um Einstellungen und Features für Teams Geräte in Ihrer Organisation zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="d3203-138">Use configuration profiles to manage settings and features for Teams devices in your organization.</span></span> <span data-ttu-id="d3203-139">Sie können erstellen oder Hochladen Konfigurationsprofile zum Einschließen von Einstellungen und Features zu aktivieren oder deaktivieren, und weisen Sie einem Profil ein Gerät oder Gruppen von Geräten.</span><span class="sxs-lookup"><span data-stu-id="d3203-139">You can create or upload configuration profiles to include settings and features you want to enable or disable and then assign a profile to a device or groups of devices.</span></span> 

### <a name="create-a-configuration-profile"></a><span data-ttu-id="d3203-140">Erstellen Sie ein Konfigurationsprofil</span><span class="sxs-lookup"><span data-stu-id="d3203-140">Create a configuration profile</span></span>

![Teams-Logo-30x30.png](media/teams-logo-30x30.png) <span data-ttu-id="d3203-142">Verwenden die Microsoft-Teams & Skype für Business Administrationscenter</span><span class="sxs-lookup"><span data-stu-id="d3203-142">Using the Microsoft Teams & Skype for Business admin center</span></span>

1. <span data-ttu-id="d3203-143">Wechseln Sie im linken Navigationsbereich auf **Geräte** > **Geräte verwalten**.</span><span class="sxs-lookup"><span data-stu-id="d3203-143">In the left navigation, go to **Devices** > **Manage Devices**.</span></span>
2. <span data-ttu-id="d3203-144">Wählen Sie **Konfigurationsprofile**aus, und wählen Sie dann auf **neues Konfigurationsprofil**.</span><span class="sxs-lookup"><span data-stu-id="d3203-144">Select **Configuration profiles**, and then select **New configuration profile**.</span></span>
3. <span data-ttu-id="d3203-145">Geben Sie einen Namen für das Profil, und wenn Sie möchten, fügen Sie eine benutzerfreundliche Beschreibung.</span><span class="sxs-lookup"><span data-stu-id="d3203-145">Enter a name for the profile and if you want, add a friendly description.</span></span>
4. <span data-ttu-id="d3203-146">Geben Sie die Einstellungen, die Sie für das Profil verwenden möchten, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="d3203-146">Specify the settings you want for the profile, and then click **Save**.</span></span>

### <a name="assign-a-configuration-profile"></a><span data-ttu-id="d3203-147">Zuweisen eines Konfigurationsprofils</span><span class="sxs-lookup"><span data-stu-id="d3203-147">Assign a configuration profile</span></span>

![Teams-Logo-30x30.png](media/teams-logo-30x30.png) <span data-ttu-id="d3203-149">Verwenden die Microsoft-Teams & Skype für Business Administrationscenter</span><span class="sxs-lookup"><span data-stu-id="d3203-149">Using the Microsoft Teams & Skype for Business admin center</span></span>

1. <span data-ttu-id="d3203-150">Wechseln Sie im linken Navigationsbereich auf **Geräte** > **Geräte verwalten**.</span><span class="sxs-lookup"><span data-stu-id="d3203-150">In the left navigation, go to **Devices** > **Manage Devices**.</span></span>
2. <span data-ttu-id="d3203-151">Wählen Sie **Konfigurationsprofil**aus, und klicken Sie dann unter **zugewiesen an** in das Profil, das Sie zuweisen möchten, klicken Sie auf den Link.</span><span class="sxs-lookup"><span data-stu-id="d3203-151">Select **Configuration profile**, and then under **Assigned to** in the profile you want to assign, click the link.</span></span>  
3. <span data-ttu-id="d3203-152">Suchen Sie und wählen Sie die Geräte, die Sie zuweisen möchten, klicken Sie im Bereich **Geräte zu einem Konfigurationsprofil zuweisen** .</span><span class="sxs-lookup"><span data-stu-id="d3203-152">In the **Assign devices to a configuration profile** pane, search for and select the devices you want to assign.</span></span>
4. <span data-ttu-id="d3203-153">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="d3203-153">Click **Save**.</span></span>
