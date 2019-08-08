---
title: Verwalten Ihrer Geräte in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 11/12/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: kelsawi
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1keywords:
- ms.teamsadmincenter.devicemanagement.overview
- ms.teamsadmincenter.managedevices.overview
description: Hier erfahren Sie, wie Sie Geräte verwalten, die mit Teams in Ihrer Organisation verwendet werden.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3b259b893f443a068b8156f2298613b0feb6d028
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237503"
---
# <a name="manage-your-devices-in-microsoft-teams"></a><span data-ttu-id="401c2-103">Verwalten Ihrer Geräte in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="401c2-103">Manage your devices in Microsoft Teams</span></span>

::: zone target="docs"
<span data-ttu-id="401c2-104">Als Administrator verwalten Sie alle Geräte, die mit Teams in Ihrer Organisation verwendet werden, im Microsoft Teams #a0 Skype for Business Admin Center.</span><span class="sxs-lookup"><span data-stu-id="401c2-104">As an admin, you manage all devices used with Teams in your organization from the Microsoft Teams & Skype for Business admin center.</span></span> <span data-ttu-id="401c2-105">Sie können die Geräte Inventur für Ihre Organisation anzeigen und verwalten sowie Aufgaben wie aktualisieren, Neustarten und Überwachen der Diagnose für Geräte ausführen.</span><span class="sxs-lookup"><span data-stu-id="401c2-105">You can view and manage the device inventory for your organization and do tasks such as update, restart, and monitor diagnostics for devices.</span></span> <span data-ttu-id="401c2-106">Sie können auch einem Gerät oder einer Gruppe von Geräten Konfigurationsprofile erstellen und zuweisen.</span><span class="sxs-lookup"><span data-stu-id="401c2-106">You can also create and assign configuration profiles to a device or groups of devices.</span></span> 

## <a name="what-devices-can-you-manage"></a><span data-ttu-id="401c2-107">Welche Geräte können verwaltet werden?</span><span class="sxs-lookup"><span data-stu-id="401c2-107">What devices can you manage?</span></span>
<span data-ttu-id="401c2-108">Geräte müssen für Teams zertifiziert und in Teams registriert sein.</span><span class="sxs-lookup"><span data-stu-id="401c2-108">Devices must be certified for Teams and enrolled in Teams.</span></span> <span data-ttu-id="401c2-109">Ein Gerät wird automatisch registriert, wenn sich ein Benutzer zum ersten Mal bei Teams auf dem Gerät anmeldet.</span><span class="sxs-lookup"><span data-stu-id="401c2-109">A device is automatically enrolled the first time a user signs in to Teams on the device.</span></span> <span data-ttu-id="401c2-110">Eine Liste der zertifizierten Geräte, die verwaltet werden können, finden Sie unter [Konferenztelefone](https://products.office.com/en-us/microsoft-teams/across-devices/devices/category?devicetype=16) und [Tischtelefone](https://products.office.com/en-us/microsoft-teams/across-devices/devices/category?devicetype=34).</span><span class="sxs-lookup"><span data-stu-id="401c2-110">For a list of certified devices that can be managed, see [Conference phones](https://products.office.com/en-us/microsoft-teams/across-devices/devices/category?devicetype=16) and [Desk phones](https://products.office.com/en-us/microsoft-teams/across-devices/devices/category?devicetype=34).</span></span>

> [!NOTE]
> <span data-ttu-id="401c2-111">Wenn Sie über Microsoft InTune verfügen, werden Geräte automatisch in InTune registriert.</span><span class="sxs-lookup"><span data-stu-id="401c2-111">If you have Microsoft Intune, devices are automatically enrolled in Intune.</span></span> <span data-ttu-id="401c2-112">Nachdem ein Gerät registriert wurde, wird die Gerätekompatibilität bestätigt, und auf das Gerät werden Richtlinien für den bedingten Zugriff angewendet.</span><span class="sxs-lookup"><span data-stu-id="401c2-112">After a device is enrolled, device compliance is confirmed and conditional access policies are applied to the device.</span></span> 

## <a name="manage-devices-in-teams"></a><span data-ttu-id="401c2-113">Verwalten von Geräten in Teams</span><span class="sxs-lookup"><span data-stu-id="401c2-113">Manage devices in Teams</span></span>

<span data-ttu-id="401c2-114">![Ein Symbol, das das Microsoft Teams](media/teams-logo-30x30.png) -Logo **mit dem Microsoft Teams Admin Center** zeigt</span><span class="sxs-lookup"><span data-stu-id="401c2-114">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="401c2-115">Navigieren Sie in der linken Navigationsleiste zu **Devices** > **Manage Devices**.</span><span class="sxs-lookup"><span data-stu-id="401c2-115">In the left navigation, go to **Devices** > **Manage Devices**.</span></span>
2. <span data-ttu-id="401c2-116">Wählen Sie **alle Geräte**aus.</span><span class="sxs-lookup"><span data-stu-id="401c2-116">Select **All devices**.</span></span>  

::: zone-end

 <span data-ttu-id="401c2-117">Hier können Sie alle Geräte anzeigen und verwalten, die für Teams in Ihrer Organisation registriert sind.</span><span class="sxs-lookup"><span data-stu-id="401c2-117">From here, you can view and manage all devices enrolled in Teams in your organization.</span></span> <span data-ttu-id="401c2-118">Zu den Informationen, die Sie für jedes Gerät sehen, gehören Gerätename, Hersteller, Modell, Benutzer, Status, Aktion, zuletzt gesehen und Verlauf.</span><span class="sxs-lookup"><span data-stu-id="401c2-118">Information that you'll see for each device includes device name, manufacturer, model, user, status, action, last seen, and history.</span></span> <span data-ttu-id="401c2-119">Sie können die Ansicht anpassen, um die Informationen anzuzeigen, die Ihren Anforderungen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="401c2-119">You can customize the view to show the information that fits your needs.</span></span>

 <span data-ttu-id="401c2-120">Nachfolgend finden Sie einige Beispiele für die Verwaltung von Teams-Geräten in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="401c2-120">Here's some examples of how you can manage Teams devices in your organization.</span></span>  
    
|<span data-ttu-id="401c2-121">Zu diesem Zweck...</span><span class="sxs-lookup"><span data-stu-id="401c2-121">To do this...</span></span>  |<span data-ttu-id="401c2-122">Tun Sie dies</span><span class="sxs-lookup"><span data-stu-id="401c2-122">Do this</span></span> |
|---------|---------|
|<span data-ttu-id="401c2-123">Ändern von Geräteinformationen</span><span class="sxs-lookup"><span data-stu-id="401c2-123">Change device information</span></span>   | <span data-ttu-id="401c2-124">Wählen Sie ein Gerät #a0 **Bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="401c2-124">Select a device > **Edit**.</span></span> <span data-ttu-id="401c2-125">Sie können Details wie Gerätename, Benutzerinformationen, Inventar Kategorien und Notizen bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="401c2-125">You can edit details such as device name, user information, asset tag, and add notes.</span></span>     |
|<span data-ttu-id="401c2-126">Verwalten von Softwareupdates</span><span class="sxs-lookup"><span data-stu-id="401c2-126">Manage software updates</span></span>   |<span data-ttu-id="401c2-127">Wählen Sie ein Gerät #a0 **Update**aus.</span><span class="sxs-lookup"><span data-stu-id="401c2-127">Select a device > **Update**.</span></span> <span data-ttu-id="401c2-128">Sie können die Liste der für das Gerät verfügbaren Software-und Firmware-Updates anzeigen und die zu installierenden Updates auswählen.</span><span class="sxs-lookup"><span data-stu-id="401c2-128">You can view the list of software and firmware updates available for the device and choose the updates to install.</span></span>    |
|<span data-ttu-id="401c2-129">Starten eines Geräts</span><span class="sxs-lookup"><span data-stu-id="401c2-129">Restart a device</span></span>   |<span data-ttu-id="401c2-130">Wählen Sie ein Gerät #a0 **Neustart**aus.</span><span class="sxs-lookup"><span data-stu-id="401c2-130">Select a device > **Restart**.</span></span>          |
|<span data-ttu-id="401c2-131">Geräte Verlauf anzeigen</span><span class="sxs-lookup"><span data-stu-id="401c2-131">View device history</span></span>  | <span data-ttu-id="401c2-132">Wählen Sie ein Gerät #a0 **Verlauf**aus.</span><span class="sxs-lookup"><span data-stu-id="401c2-132">Select a device > **History**.</span></span> <span data-ttu-id="401c2-133">Sie können den Updateverlauf für das Gerät anzeigen.</span><span class="sxs-lookup"><span data-stu-id="401c2-133">You can view the update history for the device.</span></span>     |
|<span data-ttu-id="401c2-134">Anzeigen von Diagnosen</span><span class="sxs-lookup"><span data-stu-id="401c2-134">View diagnostics</span></span>  | <span data-ttu-id="401c2-135">Wählen Sie ein Gerät #a0 **Diagnose**aus.</span><span class="sxs-lookup"><span data-stu-id="401c2-135">Select a device > **Diagnostics**.</span></span>        |

## <a name="use-configuration-profiles-in-teams"></a><span data-ttu-id="401c2-136">Verwenden von Konfigurationsprofilen in Teams</span><span class="sxs-lookup"><span data-stu-id="401c2-136">Use configuration profiles in Teams</span></span>

<span data-ttu-id="401c2-137">Verwenden Sie Konfigurationsprofile, um Einstellungen und Features für Teams-Geräte in Ihrer Organisation zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="401c2-137">Use configuration profiles to manage settings and features for Teams devices in your organization.</span></span> <span data-ttu-id="401c2-138">Sie können Konfigurationsprofile erstellen oder hochladen, um Einstellungen und Features einzubeziehen, die Sie aktivieren oder deaktivieren möchten, und dann einem Gerät oder einer Gruppe von Geräten ein Profil zuweisen.</span><span class="sxs-lookup"><span data-stu-id="401c2-138">You can create or upload configuration profiles to include settings and features you want to enable or disable and then assign a profile to a device or groups of devices.</span></span> 

### <a name="create-a-configuration-profile"></a><span data-ttu-id="401c2-139">Erstellen eines Konfigurationsprofils</span><span class="sxs-lookup"><span data-stu-id="401c2-139">Create a configuration profile</span></span>

::: zone target="docs"

![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) <span data-ttu-id="401c2-141">Verwenden des Microsoft Teams #a0 Skype for Business Admin Center</span><span class="sxs-lookup"><span data-stu-id="401c2-141">Using the Microsoft Teams & Skype for Business admin center</span></span>

1. <span data-ttu-id="401c2-142">Navigieren Sie in der linken Navigationsleiste zu **Devices** > **Manage Devices**.</span><span class="sxs-lookup"><span data-stu-id="401c2-142">In the left navigation, go to **Devices** > **Manage Devices**.</span></span>

::: zone-end

2. <span data-ttu-id="401c2-143">Wählen Sie **Konfigurationsprofile**aus, und wählen Sie dann **Neues Konfigurationsprofil**aus.</span><span class="sxs-lookup"><span data-stu-id="401c2-143">Select **Configuration profiles**, and then select **New configuration profile**.</span></span>
3. <span data-ttu-id="401c2-144">Geben Sie einen Namen für das Profil ein, und fügen Sie bei Bedarf eine Beschreibung hinzu.</span><span class="sxs-lookup"><span data-stu-id="401c2-144">Enter a name for the profile and if you want, add a friendly description.</span></span>
4. <span data-ttu-id="401c2-145">Geben Sie die gewünschten Einstellungen für das Profil ein, und klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="401c2-145">Specify the settings you want for the profile, and then click **Save**.</span></span>

### <a name="assign-a-configuration-profile"></a><span data-ttu-id="401c2-146">Zuweisen eines Konfigurationsprofils</span><span class="sxs-lookup"><span data-stu-id="401c2-146">Assign a configuration profile</span></span>

::: zone target="docs"

![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) <span data-ttu-id="401c2-148">Verwenden des Microsoft Teams #a0 Skype for Business Admin Center</span><span class="sxs-lookup"><span data-stu-id="401c2-148">Using the Microsoft Teams & Skype for Business admin center</span></span>

1. <span data-ttu-id="401c2-149">Navigieren Sie in der linken Navigationsleiste zu **Devices** > **Manage Devices**.</span><span class="sxs-lookup"><span data-stu-id="401c2-149">In the left navigation, go to **Devices** > **Manage Devices**.</span></span>

::: zone-end

2. <span data-ttu-id="401c2-150">Wählen Sie **Konfigurationsprofil**aus, und klicken Sie dann unter **zugewiesen an** in dem Profil, das Sie zuweisen möchten, auf den Link.</span><span class="sxs-lookup"><span data-stu-id="401c2-150">Select **Configuration profile**, and then under **Assigned to** in the profile you want to assign, click the link.</span></span>  
3. <span data-ttu-id="401c2-151">Suchen Sie im Bereich **Geräte zu einem Konfigurationsprofil zuweisen** nach den Geräten, die Sie zuweisen möchten, und wählen Sie Sie aus.</span><span class="sxs-lookup"><span data-stu-id="401c2-151">In the **Assign devices to a configuration profile** pane, search for and select the devices you want to assign.</span></span>
4. <span data-ttu-id="401c2-152">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="401c2-152">Click **Save**.</span></span>
