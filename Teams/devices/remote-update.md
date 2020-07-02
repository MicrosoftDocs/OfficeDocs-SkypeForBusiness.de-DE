---
title: Remote-Update von Microsoft Teams-Geräten
ms.author: dstrome
author: dstrome
ms.reviewer: rahulmi
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: Aktualisieren von Microsoft Teams-Smartphones und-Zusammenarbeits leisten über das Team Admin Center
ms.openlocfilehash: 7e47c9394eddfa73b8b55279b68ae59ff7b6de3d
ms.sourcegitcommit: 9b1c138b39fd87e239a7b1c5051f30c633e7d813
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "44944105"
---
# <a name="update-microsoft-teams-devices-remotely"></a><span data-ttu-id="8935b-103">Remote-Update von Microsoft Teams-Geräten</span><span class="sxs-lookup"><span data-stu-id="8935b-103">Update Microsoft Teams devices remotely</span></span>

<span data-ttu-id="8935b-104">Mit dem Microsoft Teams Admin Center können Sie Ihre Teams-Geräte wie Telefone und Kollaborations leisten Remote aktualisieren, und Sie können das automatische Updateverhalten der Gerätefirmware auswählen.</span><span class="sxs-lookup"><span data-stu-id="8935b-104">Using the Microsoft Teams admin center, you can update your Teams devices, such as phones and collaboration bars, remotely, and you can choose device firmware automatic-update behavior.</span></span> <span data-ttu-id="8935b-105">Mit dem Team Admin Center können Sie Folgendes auf Ihren Geräten aktualisieren:</span><span class="sxs-lookup"><span data-stu-id="8935b-105">You can update the following on your devices using the Teams admin center:</span></span>

- <span data-ttu-id="8935b-106">Teams-APP und Team-Administrator-Agent</span><span class="sxs-lookup"><span data-stu-id="8935b-106">Teams app and teams admin agent</span></span>
- <span data-ttu-id="8935b-107">Unternehmensportal-App</span><span class="sxs-lookup"><span data-stu-id="8935b-107">Company portal app</span></span>
- <span data-ttu-id="8935b-108">OEM-Agent-App</span><span class="sxs-lookup"><span data-stu-id="8935b-108">OEM agent app</span></span>
- <span data-ttu-id="8935b-109">Geräte-Firmware</span><span class="sxs-lookup"><span data-stu-id="8935b-109">Device firmware</span></span>

<span data-ttu-id="8935b-110">Geräte-Firmware-Updates können entweder automatisch oder für ein zukünftiges Datum und eine Uhrzeit geplant werden.</span><span class="sxs-lookup"><span data-stu-id="8935b-110">Device firmware updates can either be applied automatically or scheduled for a future date and time.</span></span> <span data-ttu-id="8935b-111">Andere verfügbare Geräte Updates werden nicht automatisch angewendet, können aber manuell angewendet oder für ein zukünftiges Datum und eine Uhrzeit geplant werden.</span><span class="sxs-lookup"><span data-stu-id="8935b-111">Other available device updates aren't applied automatically, but can be applied manually or scheduled for a future date and time.</span></span>

> [!NOTE]
> <span data-ttu-id="8935b-112">Wenn die Gerätefirmware-Updates geplant werden können, wenn das geplante Datum und die Uhrzeit nach der konfigurierten maximalen Verzögerung von 30 oder 90 Tage fallen, wird die Firmware-Aktualisierung angewendet, wenn die maximale Verzögerung erreicht ist.</span><span class="sxs-lookup"><span data-stu-id="8935b-112">While device firmware updates can be scheduled, if the scheduled date and time falls after the configured maximum 30 or 90 day delay, the firmware update is applied when the maximum delay is reached.</span></span> <span data-ttu-id="8935b-113">Geplantes Datum und Uhrzeit werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="8935b-113">The scheduled date and time are ignored.</span></span>

## <a name="choose-automatic-device-firmware-update-behavior"></a><span data-ttu-id="8935b-114">Auswählen des automatischen Gerätefirmware-Update Verhaltens</span><span class="sxs-lookup"><span data-stu-id="8935b-114">Choose automatic device firmware update behavior</span></span>

<span data-ttu-id="8935b-115">Geräte-Firmware-Updates werden automatisch angewendet.</span><span class="sxs-lookup"><span data-stu-id="8935b-115">Device firmware updates are applied automatically.</span></span> <span data-ttu-id="8935b-116">Sie können entscheiden, ob Sie Updates anwenden möchten, sobald eine Veröffentlichung erfolgt, oder 30 oder 90 Tage nach Veröffentlichung eines Updates.</span><span class="sxs-lookup"><span data-stu-id="8935b-116">You can decide whether to apply updates as soon as one is released, or 30 or 90 days after an update is released.</span></span> <span data-ttu-id="8935b-117">Standardmäßig werden Geräte-Firmware-Updates 30 Tage lang veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="8935b-117">By default, device firmware updates are applied 30 days one released.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8935b-118">Die aktuelle Version der Firmware-Aktualisierung wird auf Ihrem Team-Gerät nicht angewendet.</span><span class="sxs-lookup"><span data-stu-id="8935b-118">The latest firmware update release isn't applied on your Teams device.</span></span> <span data-ttu-id="8935b-119">Stattdessen wird das Update, das auf Ihrem Gerät automatisch angewendet wird, um eine Version verzögert.</span><span class="sxs-lookup"><span data-stu-id="8935b-119">Instead, the update that's automatically applied on your device is delayed by one version.</span></span> <span data-ttu-id="8935b-120">Nehmen Sie beispielsweise an, dass auf Ihrem Gerät die Version "10" angewendet wurde und Version "11" freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="8935b-120">For example, assume your device has version "10" applied, and version "11" is released.</span></span> <span data-ttu-id="8935b-121">Die Version "11" wird noch nicht angewendet.</span><span class="sxs-lookup"><span data-stu-id="8935b-121">Version "11" won't be applied yet.</span></span> <span data-ttu-id="8935b-122">Ihr Gerät wird stattdessen nur auf Version "11" aktualisiert, nachdem die Version "12" veröffentlicht wurde.</span><span class="sxs-lookup"><span data-stu-id="8935b-122">Instead your device will only be updated to version "11" after version "12" is released.</span></span>

<span data-ttu-id="8935b-123">Gehen Sie wie folgt vor, um das automatische Updateverhalten für Ihre Geräte zu wählen:</span><span class="sxs-lookup"><span data-stu-id="8935b-123">To choose the automatic update behavior for your devices, do the following:</span></span>

1. <span data-ttu-id="8935b-124">Wenn Sie sich beim Microsoft Teams Admin Center anmelden, besuchen Siehttps://admin.teams.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="8935b-124">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com</span></span>
2. <span data-ttu-id="8935b-125">Navigieren in **Geräten**für  >  **Telefone** oder **Kollaborations leisten**</span><span class="sxs-lookup"><span data-stu-id="8935b-125">Navigate **Devices** > **Phones** or **Collaboration bars**</span></span>
3. <span data-ttu-id="8935b-126">Wählen Sie ein oder mehrere Geräte aus, und wählen Sie dann **Aktualisieren** aus.</span><span class="sxs-lookup"><span data-stu-id="8935b-126">Select one or more devices and then select **Update**</span></span>
4. <span data-ttu-id="8935b-127">Wählen Sie unter **automatische Firmware-Aktualisierung**eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="8935b-127">Under **Firmware auto-update**, select one of the following:</span></span>
    - <span data-ttu-id="8935b-128">Sobald **verfügbar** Das neueste Update der Gerätefirmware wird so schnell wie möglich angewendet, nachdem das neueste Update veröffentlicht wurde.</span><span class="sxs-lookup"><span data-stu-id="8935b-128">**As soon as available** Second-newest device firmware update is applied as soon as possible after the latest update is released.</span></span>
    - <span data-ttu-id="8935b-129">**30 Tage verschieben** Das neueste Update der Geräte-Firmware wird 30 Tage nach der Veröffentlichung des neuesten Updates angewendet.</span><span class="sxs-lookup"><span data-stu-id="8935b-129">**Defer 30 days** Second-newest device firmware update is applied 30 days after the latest update is released.</span></span>
    - <span data-ttu-id="8935b-130">**Verschieben von 90 Tagen** Das neueste Update der Gerätefirmware wird 90 Tage nach der Veröffentlichung des neuesten Updates angewendet.</span><span class="sxs-lookup"><span data-stu-id="8935b-130">**Defer 90 days** Second-newest device firmware update is applied 90 days after the latest update is released.</span></span>
5. <span data-ttu-id="8935b-131">**Update** auswählen</span><span class="sxs-lookup"><span data-stu-id="8935b-131">Select **Update**</span></span>

<span data-ttu-id="8935b-132">Wenn Sie aus irgendeinem Grund eine Gerätefirmware-Aktualisierung wiederherstellen müssen, müssen Sie Ihr Gerät auf die Werkseinstellungen zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="8935b-132">If, for whatever reason, you need to revert a device firmware update, you need to reset your device to its factory settings.</span></span> <span data-ttu-id="8935b-133">Setzen Sie Ihr Gerät mit den Anweisungen seines Herstellers zurück.</span><span class="sxs-lookup"><span data-stu-id="8935b-133">Reset your device using the instructions from its manufacturer.</span></span>  

## <a name="manually-update-remote-devices"></a><span data-ttu-id="8935b-134">Manuelles Aktualisieren von Remotegeräten</span><span class="sxs-lookup"><span data-stu-id="8935b-134">Manually update remote devices</span></span>

<span data-ttu-id="8935b-135">Wenn Sie ein oder mehrere Geräte mithilfe des Admin Centers aktualisieren, können Sie entscheiden, ob Sie die Geräte sofort aktualisieren oder ein Update für ein zukünftiges Datum und eine Uhrzeit planen.</span><span class="sxs-lookup"><span data-stu-id="8935b-135">When you update one or more devices using the admin center, you can decide whether to update the devices immediately or schedule an update for a future date and time.</span></span>

<span data-ttu-id="8935b-136">Gehen Sie wie folgt vor, um Remotegeräte manuell zu aktualisieren:</span><span class="sxs-lookup"><span data-stu-id="8935b-136">To manually update remote devices, do the following:</span></span>

1. <span data-ttu-id="8935b-137">Wenn Sie sich beim Microsoft Teams Admin Center anmelden, besuchen Siehttps://admin.teams.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="8935b-137">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com</span></span>
2. <span data-ttu-id="8935b-138">Navigieren in **Geräten**für  >  **Telefone** oder **Kollaborations leisten**</span><span class="sxs-lookup"><span data-stu-id="8935b-138">Navigate  **Devices** > **Phones** or **Collaboration bars**</span></span>
3. <span data-ttu-id="8935b-139">Wählen Sie ein oder mehrere Geräte aus, und wählen Sie dann **Aktualisieren** aus.</span><span class="sxs-lookup"><span data-stu-id="8935b-139">Select one or more devices and then select **Update**</span></span>
4. <span data-ttu-id="8935b-140">Wählen Sie unter **Manuelle Updates**die Option **Zeitplan** aus, wenn Sie das Update für ein zukünftiges Datum und eine Uhrzeit planen möchten.</span><span class="sxs-lookup"><span data-stu-id="8935b-140">Under **Manual updates**, select **Schedule** if you want to schedule the update for a future date and time.</span></span> <span data-ttu-id="8935b-141">Die Updates werden zu dem Datum und der Uhrzeit in der Zeitzone angewendet, die in **TimeZone**ausgewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="8935b-141">The updates are applied at the date and time in the timezone selected in **Timezone**.</span></span>

<span data-ttu-id="8935b-142">Was Sie sehen, hängt davon ab, ob Sie ein oder mehrere Geräte ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="8935b-142">What you'll see depends on whether you have one, or multiple, devices selected.</span></span> <span data-ttu-id="8935b-143">In der linken Abbildung unten sind mehrere Geräte ausgewählt, während das Bild auf der rechten Seite ein einzelnes Gerät ausgewählt zeigt.</span><span class="sxs-lookup"><span data-stu-id="8935b-143">The left image below shows multiple devices selected while the image on the right shows a single device selected.</span></span>

:::image type="content" source="../media/device-update-status.png" alt-text="Einzel-und mehrere Geräte Ansichten im Bereich "Geräte Aktualisierungsstatus"":::

<span data-ttu-id="8935b-145">Wenn Sie mehrere Geräte auswählen, können Sie auswählen, welche Updatetypen für jedes ausgewählte Gerät gelten sollen.</span><span class="sxs-lookup"><span data-stu-id="8935b-145">When you select multiple devices, you can choose which update types to apply to each selected device.</span></span> <span data-ttu-id="8935b-146">Wählen Sie die Updatetypen aus, die Sie anwenden möchten, und wählen Sie **Aktualisieren**aus.</span><span class="sxs-lookup"><span data-stu-id="8935b-146">Select the update types you want to apply and select **Update**.</span></span>

<span data-ttu-id="8935b-147">Wenn Sie ein einzelnes Gerät auswählen, werden Updates angezeigt, die für das Gerät verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="8935b-147">When you select a single device, updates that are available for the device are shown.</span></span> <span data-ttu-id="8935b-148">Wenn mehrere Updatetypen für das Gerät verfügbar sind, wählen Sie die einzelnen Updatetypen aus, die Sie anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="8935b-148">If multiple update types are available for the device, select each update type to apply.</span></span> <span data-ttu-id="8935b-149">Sie können die **aktuelle Version** anzeigen, die auf dem Gerät angewendet wurde, und die **neue Version** , die angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="8935b-149">You can view the **Current version** applied on the device and the **New version** that will be applied.</span></span> <span data-ttu-id="8935b-150">Wählen Sie die Updates aus, die Sie anwenden möchten, und wählen Sie **Aktualisieren**aus.</span><span class="sxs-lookup"><span data-stu-id="8935b-150">Select the update(s) you want to apply and select **Update**.</span></span>

<span data-ttu-id="8935b-151">Nachdem Sie **Update**ausgewählt haben, werden Updates auf Ihre Geräte zu dem Datum und der Uhrzeit angewendet, die Sie bei der Planung eines Updates ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="8935b-151">After you select **Update**, updates are applied to your devices at the date and time you selected if you scheduled an update.</span></span> <span data-ttu-id="8935b-152">Wenn Sie kein zukünftiges Datum und keine Uhrzeit ausgewählt haben, werden Updates auf Ihre Geräte innerhalb weniger Minuten angewendet.</span><span class="sxs-lookup"><span data-stu-id="8935b-152">If you didn't select a future date and time, updates are applied to your devices within a few minutes.</span></span>
