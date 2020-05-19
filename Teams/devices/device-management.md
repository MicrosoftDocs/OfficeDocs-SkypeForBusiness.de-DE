---
title: Verwalten Ihrer Geräte in Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: kelsawi
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.managedevices.overview
- ms.teamsadmincenter.devicemanagement.overview
description: Hier erfahren Sie, wie Sie Geräte verwalten, die mit Teams in Ihrer Organisation verwendet werden.
localization_priority: Normal
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 366a24706a80f6fe96cc8a3733022cc64f78ba7e
ms.sourcegitcommit: 3ed779277540589eabef745685ab6c67d8a8ff90
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "44281725"
---
# <a name="manage-your-devices-in-microsoft-teams"></a><span data-ttu-id="a3e1b-103">Verwalten Ihrer Geräte in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a3e1b-103">Manage your devices in Microsoft Teams</span></span>

<span data-ttu-id="a3e1b-104">Als Administrator können Sie Geräte, die mit Teams in Ihrer Organisation verwendet werden, über das Microsoft Teams Admin Center verwalten.</span><span class="sxs-lookup"><span data-stu-id="a3e1b-104">As an admin, you can manage devices used with Teams in your organization from the Microsoft Teams admin center.</span></span> <span data-ttu-id="a3e1b-105">Sie können die Geräte Inventur für Ihre Organisation anzeigen und verwalten sowie Aufgaben wie aktualisieren, Neustarten und Überwachen der Diagnose für Geräte ausführen.</span><span class="sxs-lookup"><span data-stu-id="a3e1b-105">You can view and manage the device inventory for your organization and do tasks such as update, restart, and monitor diagnostics for devices.</span></span> <span data-ttu-id="a3e1b-106">Sie können auch einem Gerät oder einer Gruppe von Geräten Konfigurationsprofile erstellen und zuweisen.</span><span class="sxs-lookup"><span data-stu-id="a3e1b-106">You can also create and assign configuration profiles to a device or groups of devices.</span></span> 

## <a name="what-devices-can-you-manage"></a><span data-ttu-id="a3e1b-107">Welche Geräte können verwaltet werden?</span><span class="sxs-lookup"><span data-stu-id="a3e1b-107">What devices can you manage?</span></span>
<span data-ttu-id="a3e1b-108">Sie können jedes Gerät verwalten, das für Teams zertifiziert und registriert ist.</span><span class="sxs-lookup"><span data-stu-id="a3e1b-108">You can manage any device that's certified for, and enrolled in, Teams.</span></span> <span data-ttu-id="a3e1b-109">Ein Gerät wird automatisch registriert, wenn sich ein Benutzer zum ersten Mal bei Teams auf dem Gerät anmeldet.</span><span class="sxs-lookup"><span data-stu-id="a3e1b-109">A device is automatically enrolled the first time a user signs in to Teams on the device.</span></span> <span data-ttu-id="a3e1b-110">Eine Liste der zertifizierten Geräte, die verwaltet werden können, finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="a3e1b-110">For a list of certified devices that can be managed, see:</span></span>

- [<span data-ttu-id="a3e1b-111">Konferenztelefone</span><span class="sxs-lookup"><span data-stu-id="a3e1b-111">Conference phones</span></span>](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=16)
- [<span data-ttu-id="a3e1b-112">Tischtelefone</span><span class="sxs-lookup"><span data-stu-id="a3e1b-112">Desk phones</span></span>](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=34)
- <span data-ttu-id="a3e1b-113">Zusammenarbeits leisten</span><span class="sxs-lookup"><span data-stu-id="a3e1b-113">Collaboration bars</span></span>

<span data-ttu-id="a3e1b-114">Geräte werden im [Microsoft Teams Admin Center](https://admin.teams.microsoft.com) unter " **Geräte** " im linken Navigationsbereich verwaltet.</span><span class="sxs-lookup"><span data-stu-id="a3e1b-114">Devices are managed in the [Microsoft Teams admin center](https://admin.teams.microsoft.com) under **Devices** in the left navigation.</span></span>

> [!NOTE]
> <span data-ttu-id="a3e1b-115">Wenn Sie über Microsoft InTune verfügen, werden Geräte automatisch in InTune registriert.</span><span class="sxs-lookup"><span data-stu-id="a3e1b-115">If you have Microsoft Intune, devices are automatically enrolled in Intune.</span></span> <span data-ttu-id="a3e1b-116">Nachdem ein Gerät registriert wurde, wird die Gerätekompatibilität bestätigt, und auf das Gerät werden Richtlinien für den bedingten Zugriff angewendet.</span><span class="sxs-lookup"><span data-stu-id="a3e1b-116">After a device is enrolled, device compliance is confirmed and conditional access policies are applied to the device.</span></span>

## <a name="manage-phones-and-collaboration-bars-in-teams"></a><span data-ttu-id="a3e1b-117">Verwalten von Telefonen und Teamarbeits leisten in Teams</span><span class="sxs-lookup"><span data-stu-id="a3e1b-117">Manage phones and collaboration bars in Teams</span></span>

<span data-ttu-id="a3e1b-118">Auch wenn Telefone und Kollaborations leisten im Microsoft Teams Admin Center gleich verwaltet werden, verfügen Sie über eigene Abschnitte im linken Navigationsbereich unter " **Geräte**".</span><span class="sxs-lookup"><span data-stu-id="a3e1b-118">Even though phones and collaboration bars are managed the same in the Microsoft Teams admin center, they have their own respective sections in the left navigation under **Devices**.</span></span> <span data-ttu-id="a3e1b-119">Auf diese Weise können Sie die einzelnen Gerätetypen separat verwalten.</span><span class="sxs-lookup"><span data-stu-id="a3e1b-119">This lets you manage each type of device separately.</span></span>

<span data-ttu-id="a3e1b-120">Von hier aus können Sie Telefone und Zusammenarbeit leisten anzeigen und verwalten, die für Teams in Ihrer Organisation registriert sind.</span><span class="sxs-lookup"><span data-stu-id="a3e1b-120">From here, you can view and manage phones and collaboration bars enrolled in Teams in your organization.</span></span> <span data-ttu-id="a3e1b-121">Zu den Informationen, die Sie für jedes Gerät sehen, gehören Gerätename, Hersteller, Modell, Benutzer, Status, Aktion, zuletzt gesehen und Verlauf.</span><span class="sxs-lookup"><span data-stu-id="a3e1b-121">Information that you'll see for each device includes device name, manufacturer, model, user, status, action, last seen, and history.</span></span> <span data-ttu-id="a3e1b-122">Sie können die Ansicht anpassen, um die Informationen anzuzeigen, die Ihren Anforderungen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="a3e1b-122">You can customize the view to show the information that fits your needs.</span></span>

<span data-ttu-id="a3e1b-123">Nachfolgend finden Sie einige Beispiele für die Verwaltung von Teams-Geräten in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="a3e1b-123">Here's some examples of how you can manage Teams devices in your organization.</span></span>  
    
|<span data-ttu-id="a3e1b-124">Zu diesem Zweck...</span><span class="sxs-lookup"><span data-stu-id="a3e1b-124">To do this...</span></span>  |<span data-ttu-id="a3e1b-125">Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="a3e1b-125">Do this</span></span> |
|---------|---------|
|<span data-ttu-id="a3e1b-126">Ändern von Geräteinformationen</span><span class="sxs-lookup"><span data-stu-id="a3e1b-126">Change device information</span></span>   | <span data-ttu-id="a3e1b-127">Wählen Sie ein Gerät > **Bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="a3e1b-127">Select a device > **Edit**.</span></span> <span data-ttu-id="a3e1b-128">Sie können Details wie Gerätename, Inventar Kategorie und Notizen bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="a3e1b-128">You can edit details such as device name, asset tag, and add notes.</span></span>     |
|<span data-ttu-id="a3e1b-129">Verwalten von Softwareupdates</span><span class="sxs-lookup"><span data-stu-id="a3e1b-129">Manage software updates</span></span>   |<span data-ttu-id="a3e1b-130">Wählen Sie ein Gerät > **Update**aus.</span><span class="sxs-lookup"><span data-stu-id="a3e1b-130">Select a device > **Update**.</span></span> <span data-ttu-id="a3e1b-131">Sie können die Liste der für das Gerät verfügbaren Software-und Firmware-Updates anzeigen und die zu installierenden Updates auswählen.</span><span class="sxs-lookup"><span data-stu-id="a3e1b-131">You can view the list of software and firmware updates available for the device and choose the updates to install.</span></span>    |
|<span data-ttu-id="a3e1b-132">Starten eines Geräts</span><span class="sxs-lookup"><span data-stu-id="a3e1b-132">Restart a device</span></span>   |<span data-ttu-id="a3e1b-133">Wählen Sie ein Gerät > **Neustart**aus.</span><span class="sxs-lookup"><span data-stu-id="a3e1b-133">Select a device > **Restart**.</span></span>          |
|<span data-ttu-id="a3e1b-134">Geräte Verlauf anzeigen</span><span class="sxs-lookup"><span data-stu-id="a3e1b-134">View device history</span></span>  | <span data-ttu-id="a3e1b-135">Wählen Sie ein Gerät > **Verlauf**aus.</span><span class="sxs-lookup"><span data-stu-id="a3e1b-135">Select a device > **History**.</span></span> <span data-ttu-id="a3e1b-136">Sie können den Updateverlauf für das Gerät anzeigen.</span><span class="sxs-lookup"><span data-stu-id="a3e1b-136">You can view the update history for the device.</span></span>     |
|<span data-ttu-id="a3e1b-137">Anzeigen von Diagnosen</span><span class="sxs-lookup"><span data-stu-id="a3e1b-137">View diagnostics</span></span>  | <span data-ttu-id="a3e1b-138">Wählen Sie ein Gerät > **Diagnose**aus.</span><span class="sxs-lookup"><span data-stu-id="a3e1b-138">Select a device > **Diagnostics**.</span></span>        |

## <a name="use-configuration-profiles-in-teams"></a><span data-ttu-id="a3e1b-139">Verwenden von Konfigurationsprofilen in Teams</span><span class="sxs-lookup"><span data-stu-id="a3e1b-139">Use configuration profiles in Teams</span></span>

<span data-ttu-id="a3e1b-140">Verwenden Sie Konfigurationsprofile, um Einstellungen und Features für Teams-Geräte in Ihrer Organisation zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="a3e1b-140">Use configuration profiles to manage settings and features for Teams devices in your organization.</span></span> <span data-ttu-id="a3e1b-141">Sie können Konfigurationsprofile erstellen oder hochladen, um Einstellungen und Features einzubeziehen, die Sie aktivieren oder deaktivieren möchten, und dann einem Gerät oder einer Gruppe von Geräten ein Profil zuweisen.</span><span class="sxs-lookup"><span data-stu-id="a3e1b-141">You can create or upload configuration profiles to include settings and features you want to enable or disable and then assign a profile to a device or groups of devices.</span></span> 

### <a name="create-a-configuration-profile"></a><span data-ttu-id="a3e1b-142">Erstellen eines Konfigurationsprofils</span><span class="sxs-lookup"><span data-stu-id="a3e1b-142">Create a configuration profile</span></span>

1. <span data-ttu-id="a3e1b-143">Navigieren Sie in der linken Navigationsleiste zu **Devices**-  >  **Konfigurationsprofilen**.</span><span class="sxs-lookup"><span data-stu-id="a3e1b-143">In the left navigation, go to **Devices** > **Configuration profiles**.</span></span>
2. <span data-ttu-id="a3e1b-144">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="a3e1b-144">Click **Add**.</span></span>
3. <span data-ttu-id="a3e1b-145">Geben Sie einen Namen für das Profil ein, und fügen Sie bei Bedarf eine Beschreibung hinzu.</span><span class="sxs-lookup"><span data-stu-id="a3e1b-145">Enter a name for the profile and if you want, add a friendly description.</span></span>
4. <span data-ttu-id="a3e1b-146">Geben Sie die gewünschten Einstellungen für das Profil ein, und klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="a3e1b-146">Specify the settings you want for the profile, and then click **Save**.</span></span>

### <a name="assign-a-configuration-profile"></a><span data-ttu-id="a3e1b-147">Zuweisen eines Konfigurationsprofils</span><span class="sxs-lookup"><span data-stu-id="a3e1b-147">Assign a configuration profile</span></span>

1. <span data-ttu-id="a3e1b-148">Navigieren Sie in der linken Navigationsleiste zu **Devices**-  >  **Konfigurationsprofilen**.</span><span class="sxs-lookup"><span data-stu-id="a3e1b-148">In the left navigation, go to **Devices** > **Configuration profiles**.</span></span>
2. <span data-ttu-id="a3e1b-149">Wählen Sie das **Konfigurationsprofil** aus, das Sie zuweisen möchten, und klicken Sie dann auf **auf Gerät zuweisen**.</span><span class="sxs-lookup"><span data-stu-id="a3e1b-149">Select the **Configuration profile** you want to assign, and then click **Assign to device**.</span></span>  
3. <span data-ttu-id="a3e1b-150">Suchen Sie im Bereich **Geräte zu einem Konfigurationsprofil zuweisen** nach den Geräten, die Sie zuweisen möchten, und wählen Sie Sie aus.</span><span class="sxs-lookup"><span data-stu-id="a3e1b-150">In the **Assign devices to a configuration profile** pane, search for and select the devices you want to assign.</span></span>
4. <span data-ttu-id="a3e1b-151">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="a3e1b-151">Click **Save**.</span></span>
