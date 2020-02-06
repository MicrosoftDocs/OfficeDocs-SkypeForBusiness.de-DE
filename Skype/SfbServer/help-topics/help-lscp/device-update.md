---
title: Geräteaktualisierung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientDeviceUpdateMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6f6b7f73-f8f5-41dc-9e2a-727baaaa828b
description: Microsoft veröffentlicht in regelmäßigen Abständen einen neuen Satz von Gerätefirmware-Updates für Skype for Business Phone Edition, die Sie auf Ihre Server importieren und an Benutzer verteilen können. Sie können die neuesten Regeln für Geräte Updates abrufen, indem Sie auf der Microsoft-Website auf der Seite Hilfe und Support auf der Microsoft-Website nach forPhone Edition suchen. Laden Sie das neueste Update-Paket herunter, und extrahieren Sie die Dateien in einen Ordner auf dem Computer, auf dem die Updates hochgeladen werden sollen. Nachdem Sie die Dateien extrahiert haben, können Sie das Cmdlet Import-CsDeviceUpdate verwenden, um die Geräteaktualisierungsregeln aus der extrahierten CAB-Datei (die „UCUpdates.cab“ oder ähnlich heißt) zu importieren. Ausführliche Informationen finden Sie unter Importieren-CsDeviceUpdate.
ms.openlocfilehash: ad296ebc3b8ade977884a925180dbb3639855f76
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822888"
---
# <a name="device-update"></a><span data-ttu-id="77694-106">Geräteupdate</span><span class="sxs-lookup"><span data-stu-id="77694-106">Device Update</span></span>

<span data-ttu-id="77694-107">Microsoft veröffentlicht in regelmäßigen Abständen einen neuen Satz von Gerätefirmware-Updates für Skype for Business Phone Edition, die Sie auf Ihre Server importieren und an Benutzer verteilen können.</span><span class="sxs-lookup"><span data-stu-id="77694-107">Microsoft periodically releases a new set of device firmware updates for Skype for Business Phone Edition, which you can import to your servers and distribute to users.</span></span> <span data-ttu-id="77694-108">Sie erhalten den neuesten Satz von Geräteaktualisierungsregeln, indem Sie auf der Microsoft-Website die Seite „Hilfe und Support“ aufrufen und nach „Phone Edition“ suchen.</span><span class="sxs-lookup"><span data-stu-id="77694-108">You can obtain the latest set of device update rules by going to the Help and Support page on the Microsoft website and searching for "Phone Edition."</span></span> <span data-ttu-id="77694-109">Laden Sie das aktuelle Updatepaket herunter und extrahieren Sie die Dateien in einen Ordner auf dem Computer, auf den die Updates geladen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="77694-109">Download the latest update package and extract the files to a folder on the computer where the updates are to be uploaded.</span></span> <span data-ttu-id="77694-110">Nachdem Sie die Dateien extrahiert haben, können Sie das Cmdlet **Import-CsDeviceUpdate** verwenden, um die Geräteaktualisierungsregeln aus der extrahierten CAB-Datei (die „UCUpdates.cab“ oder ähnlich heißt) zu importieren.</span><span class="sxs-lookup"><span data-stu-id="77694-110">After the files have been extracted, you can then use the **Import-CsDeviceUpdate** cmdlet to import the device update rules found in the extracted .CAB file (which will have the name UCUpdates.cab).</span></span> <span data-ttu-id="77694-111">Ausführliche Informationen finden Sie unter [importieren-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="77694-111">For details, see [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps).</span></span>

<span data-ttu-id="77694-112">Nachdem die geräteaktualisierungsregeln importiert wurden, können Sie auf der Seite **Device Update** diese Regeln für die Geräte Ihrer Organisation anzeigen und verwalten.</span><span class="sxs-lookup"><span data-stu-id="77694-112">After the device update rules have been imported, you can use the **Device Update** page to view and manage these rules for your organization's devices.</span></span>

> [!TIP]
> <span data-ttu-id="77694-113">Sie können die Firmwareupdates testen und dann, sofern die Tests erfolgreich waren, allen relevanten Geräten in der Organisation zur Verfügung stellen.</span><span class="sxs-lookup"><span data-stu-id="77694-113">You can test the firmware updates and then, assuming the tests succeed, make the updates available to all the relevant devices used in the organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="77694-114">Mögliche Aufgaben</span><span class="sxs-lookup"><span data-stu-id="77694-114">Tasks you can perform</span></span>

<span data-ttu-id="77694-115">Auf der Seite **Geräteupdate** können Sie die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="77694-115">You can perform the following tasks on the **Device Update** page:</span></span>

- <span data-ttu-id="77694-116">Genehmigen von Geräteupdates der Liste</span><span class="sxs-lookup"><span data-stu-id="77694-116">Approve device updates in the list.</span></span>

- <span data-ttu-id="77694-117">Abbrechen oder Wiederherstellen ausstehender Geräteupdates</span><span class="sxs-lookup"><span data-stu-id="77694-117">Cancel or restore pending device updates.</span></span>

- <span data-ttu-id="77694-118">Löschen von Geräteupdates aus der Liste</span><span class="sxs-lookup"><span data-stu-id="77694-118">Delete device updates from the list.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="77694-119">Referenz zur Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="77694-119">UI Reference</span></span>

<span data-ttu-id="77694-120">In den folgenden Listen werden die Menüs, Befehle, Felder und Eigenschaften der Seite beschrieben.</span><span class="sxs-lookup"><span data-stu-id="77694-120">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="77694-121">**Bearbeiten** von Sie können diese Option verwenden, um folgende Aktionen auszuführen:</span><span class="sxs-lookup"><span data-stu-id="77694-121">**Edit** You can use this option to do the following:</span></span>

  - <span data-ttu-id="77694-122">**Alle auswählen** Mit dieser Option werden alle Geräte Updates in der Liste ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="77694-122">**Select All** This option selects all device updates in the list.</span></span>

  - <span data-ttu-id="77694-123">**Löschen** Mit dieser Option werden alle ausgewählten Geräte Updates gelöscht.</span><span class="sxs-lookup"><span data-stu-id="77694-123">**Delete** This option deletes all selected device updates.</span></span>

- <span data-ttu-id="77694-124">**Aktion** Sie können ein oder mehrere Updates in der Liste auswählen und die folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="77694-124">**Action** You can select one or more updates in the list and take the following actions:</span></span>

  - <span data-ttu-id="77694-125">**Ausstehende Updates Abbrechen** Mit dieser Option wird verhindert, dass das ausgewählte Update auf den Geräten Ihrer Organisation bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="77694-125">**Cancel pending updates** This option prevents the selected update from being deployed to your organization's devices.</span></span>

  - <span data-ttu-id="77694-126">**Genehmigen** Mit dieser Option kann das ausgewählte Update auf den Geräten Ihrer Organisation bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="77694-126">**Approve** This option allows the selected update to be deployed to your organization's devices.</span></span>

  - <span data-ttu-id="77694-127">**Wiederherstellen** Mit dieser Option kann ein zuvor genehmigtes Update auf den Geräten Ihrer Organisation bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="77694-127">**Restore** This option allows a previously approved update to be deployed to your organization's devices</span></span>

- <span data-ttu-id="77694-128">**Aktualisieren** Sie können die Liste aktualisieren, um den Status aller Geräte Updates zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="77694-128">**Refresh** You can refresh the list to verify the status of all device updates.</span></span>

<span data-ttu-id="77694-129">Ausführliche Informationen zum Geräteaktualisierungs-Webdienst finden Sie in der Planungsdokumentation unter [View Software Updates for Devices in Your Organization](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx) .</span><span class="sxs-lookup"><span data-stu-id="77694-129">For details about Device Update Web service, see [View Software Updates for Devices in Your Organization](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx) in the Planning documentation.</span></span>
## <a name="see-also"></a><span data-ttu-id="77694-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="77694-130">See also</span></span>

[<span data-ttu-id="77694-131">Importieren-CsDeviceUpdate</span><span class="sxs-lookup"><span data-stu-id="77694-131">Import-CsDeviceUpdate</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps)
