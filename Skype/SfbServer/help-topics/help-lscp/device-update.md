---
title: Geräteaktualisierung
ms.author: laurawi
author: LauraWi
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceUpdateMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6f6b7f73-f8f5-41dc-9e2a-727baaaa828b
description: Microsoft stellt in regelmäßigen Abständen einen neuen Satz von Geräteupdates Firmware für Skype für Business Phone Edition, die Sie importieren auf den Servern und an Benutzer verteilen können. Sie können erhalten der aktuellen Gruppe von geräteaktualisierungsregeln durch Aufrufen der Hilfe und Support-Seite auf der Microsoft-Website und Suche ForPhone Edition.Download das neueste Updatepaket und extrahieren Sie die Dateien in einen Ordner auf dem Computer, auf dem die Updates sind hochgeladen werden. Nachdem die Dateien extrahiert wurden, können Sie das Cmdlet Import-CsDeviceUpdate klicken Sie dann zum Importieren der geräteaktualisierungsregeln gefunden in die extrahierten verwenden. CAB-Datei (die den Namen UCUpdates.cab verfügen). Weitere Informationen hierzu finden Sie unter Import-CsDeviceUpdate.
ms.openlocfilehash: 584c04e8169eec4621c91c469127b99388f4820a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="device-update"></a><span data-ttu-id="28b3c-106">Geräteupdate</span><span class="sxs-lookup"><span data-stu-id="28b3c-106">Device Update</span></span>
 
<span data-ttu-id="28b3c-107">Microsoft stellt in regelmäßigen Abständen einen neuen Satz von Geräteupdates Firmware für Skype für Business Phone Edition, die Sie importieren auf den Servern und an Benutzer verteilen können.</span><span class="sxs-lookup"><span data-stu-id="28b3c-107">Microsoft periodically releases a new set of device firmware updates for Skype for Business Phone Edition, which you can import to your servers and distribute to users.</span></span> <span data-ttu-id="28b3c-108">Sie erhalten den neuesten Satz von Geräteaktualisierungsregeln, indem Sie auf der Microsoft-Website die Seite „Hilfe und Support“ aufrufen und nach „Phone Edition“ suchen.</span><span class="sxs-lookup"><span data-stu-id="28b3c-108">You can obtain the latest set of device update rules by going to the Help and Support page on the Microsoft website and searching for "Phone Edition."</span></span> <span data-ttu-id="28b3c-109">Laden Sie das aktuelle Updatepaket herunter und extrahieren Sie die Dateien in einen Ordner auf dem Computer, auf den die Updates geladen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="28b3c-109">Download the latest update package and extract the files to a folder on the computer where the updates are to be uploaded.</span></span> <span data-ttu-id="28b3c-110">Nachdem Sie die Dateien extrahiert haben, können Sie das Cmdlet **Import-CsDeviceUpdate** verwenden, um die Geräteaktualisierungsregeln aus der extrahierten CAB-Datei (die „UCUpdates.cab“ oder ähnlich heißt) zu importieren.</span><span class="sxs-lookup"><span data-stu-id="28b3c-110">After the files have been extracted, you can then use the **Import-CsDeviceUpdate** cmdlet to import the device update rules found in the extracted .CAB file (which will have the name UCUpdates.cab).</span></span> <span data-ttu-id="28b3c-111">Weitere Informationen hierzu finden Sie unter [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="28b3c-111">For details, see [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps).</span></span>
  
<span data-ttu-id="28b3c-112">Nach dem Import der geräteaktualisierungsregeln können Sie die Seite **Geräteupdate** verwenden, anzeigen und verwalten diese Regeln für die Geräte Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="28b3c-112">After the device update rules have been imported, you can use the **Device Update** page to view and manage these rules for your organization's devices.</span></span>
  
> [!TIP]
> <span data-ttu-id="28b3c-113">Sie können die Firmwareupdates testen und dann, sofern die Tests erfolgreich waren, allen relevanten Geräten in der Organisation zur Verfügung stellen.</span><span class="sxs-lookup"><span data-stu-id="28b3c-113">You can test the firmware updates and then, assuming the tests succeed, make the updates available to all the relevant devices used in the organization.</span></span> 
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="28b3c-114">Mögliche Aufgaben</span><span class="sxs-lookup"><span data-stu-id="28b3c-114">Tasks you can perform</span></span>

<span data-ttu-id="28b3c-115">Auf der Seite **Geräteupdate** können Sie die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="28b3c-115">You can perform the following tasks on the **Device Update** page:</span></span>
  
- <span data-ttu-id="28b3c-116">Genehmigen von Geräteupdates der Liste</span><span class="sxs-lookup"><span data-stu-id="28b3c-116">Approve device updates in the list.</span></span>
    
- <span data-ttu-id="28b3c-117">Abbrechen oder Wiederherstellen ausstehender Geräteupdates</span><span class="sxs-lookup"><span data-stu-id="28b3c-117">Cancel or restore pending device updates.</span></span>
    
- <span data-ttu-id="28b3c-118">Löschen von Geräteupdates aus der Liste</span><span class="sxs-lookup"><span data-stu-id="28b3c-118">Delete device updates from the list.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="28b3c-119">Referenz zur Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="28b3c-119">UI Reference</span></span>

<span data-ttu-id="28b3c-120">In den folgenden Listen werden die Menüs, Befehle, Felder und Eigenschaften der Seite beschrieben.</span><span class="sxs-lookup"><span data-stu-id="28b3c-120">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="28b3c-121">**Bearbeiten** Diese Option können Sie folgende Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="28b3c-121">**Edit** You can use this option to do the following:</span></span>
    
  - <span data-ttu-id="28b3c-122">**Wählen Sie alle** Diese Option werden alle Geräteupdates der Liste ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="28b3c-122">**Select All** This option selects all device updates in the list.</span></span>
    
  - <span data-ttu-id="28b3c-123">**Löschen** Diese Option werden alle ausgewählten Geräteupdates gelöscht.</span><span class="sxs-lookup"><span data-stu-id="28b3c-123">**Delete** This option deletes all selected device updates.</span></span>
    
- <span data-ttu-id="28b3c-124">**Aktion** Sie können ein oder mehrere Updates in der Liste wählen und führen die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="28b3c-124">**Action** You can select one or more updates in the list and take the following actions:</span></span>
    
  - <span data-ttu-id="28b3c-125">**Ausstehende Updates Abbrechen** Diese Option wird verhindert, dass das ausgewählte Update Geräte der Organisation bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="28b3c-125">**Cancel pending updates** This option prevents the selected update from being deployed to your organization's devices.</span></span>
    
  - <span data-ttu-id="28b3c-126">**Genehmigen** Mit dieser Option können das ausgewählte Update für die Geräte Ihrer Organisation bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="28b3c-126">**Approve** This option allows the selected update to be deployed to your organization's devices.</span></span>
    
  - <span data-ttu-id="28b3c-127">**Stellen Sie wieder her** Mit dieser Option können ein bereits genehmigtes Update auf Geräten in Ihrer Organisation bereitgestellt werden</span><span class="sxs-lookup"><span data-stu-id="28b3c-127">**Restore** This option allows a previously approved update to be deployed to your organization's devices</span></span>
    
- <span data-ttu-id="28b3c-128">**Aktualisieren** Aktualisieren Sie die Liste, um den Status aller Geräteupdates zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="28b3c-128">**Refresh** You can refresh the list to verify the status of all device updates.</span></span>
    
<span data-ttu-id="28b3c-129">Ausführliche Informationen zu den Geräteupdate-Webdienst finden Sie unter [View Software Updates for Devices in Your Organization](http://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="28b3c-129">For details about Device Update Web service, see [View Software Updates for Devices in Your Organization](http://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx) in the Planning documentation.</span></span>
## <a name="see-also"></a><span data-ttu-id="28b3c-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="28b3c-130">See also</span></span>

#### 

[<span data-ttu-id="28b3c-131">Import-CsDeviceUpdate</span><span class="sxs-lookup"><span data-stu-id="28b3c-131">Import-CsDeviceUpdate</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps)

