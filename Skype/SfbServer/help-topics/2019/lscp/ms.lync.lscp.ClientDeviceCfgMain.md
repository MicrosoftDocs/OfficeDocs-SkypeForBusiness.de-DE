---
title: Geräteprotokollkonfiguration
ms.reviewer: ''
ms.author: SerdarS
author: SerdarSoysal
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceCfgMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c9b81f20-ce8c-40f1-8bed-50775cc35e58
ROBOTS: NOINDEX, NOFOLLOW
description: Der Geräteaktualisierungs-Webdienst erstellt automatisch Protokolldateien, mit denen die Aktivität bei der Geräteaktualisierung aufgezeichnet wird. Im Rahmen Ihres Unternehmens Data Management-Strategie sollten Sie die Grenzwerte zu Protokollgröße Daten-Cache, Größe der Protokolldatei oder die Zeitdauer, die eine Protokolldatei gespeichert wird, bevor es gelöscht wird. Sie können diese Einstellungen entsprechend den Anforderungen der Organisation ändern. Falls Sie nicht möchten, dass der Geräteaktualisierungs-Webdienst die Protokolldateien automatisch löscht, können Sie diese je nach Bedarf manuell löschen. Protokolleinstellungen können global oder auf Standortebene geändert werden.
ms.openlocfilehash: 68e5e7d569f3a0436f80bb081b0785e5278bcb0d
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30892392"
---
# <a name="device-log-configuration"></a><span data-ttu-id="cffb2-107">Geräteprotokollkonfiguration</span><span class="sxs-lookup"><span data-stu-id="cffb2-107">Device Log Configuration</span></span>

<span data-ttu-id="cffb2-108">Der Geräteaktualisierungs-Webdienst erstellt automatisch Protokolldateien, mit denen die Aktivität bei der Geräteaktualisierung aufgezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="cffb2-108">Device Update Web service automatically creates log files that record device update activity.</span></span> <span data-ttu-id="cffb2-109">Im Rahmen Ihres Unternehmens Data Management-Strategie sollten Sie die Grenzwerte zu Protokollgröße Daten-Cache, Größe der Protokolldatei oder die Zeitdauer, die eine Protokolldatei gespeichert wird, bevor es gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="cffb2-109">As part of your organization's data management strategy, you may want to set thresholds on log data cache size, log file size, or the length of time a log file is kept before it is purged.</span></span> <span data-ttu-id="cffb2-110">Sie können diese Einstellungen entsprechend den Anforderungen der Organisation ändern.</span><span class="sxs-lookup"><span data-stu-id="cffb2-110">You can change these settings according to your organization's requirements.</span></span> <span data-ttu-id="cffb2-111">Falls Sie nicht möchten, dass der Geräteaktualisierungs-Webdienst die Protokolldateien automatisch löscht, können Sie diese je nach Bedarf manuell löschen.</span><span class="sxs-lookup"><span data-stu-id="cffb2-111">If you do not want Device Update Web service to purge log files automatically, you can purge them manually, as needed.</span></span> <span data-ttu-id="cffb2-112">Protokolleinstellungen können global oder auf Standortebene geändert werden.</span><span class="sxs-lookup"><span data-stu-id="cffb2-112">Log settings can be changed globally or per site.</span></span>

> [!NOTE]
> <span data-ttu-id="cffb2-113">Sie können auch eine Uhrzeit konfigurieren, zu der der Geräteaktualisierungs-Webdienst automatisch Protokolldateien löscht, die älter sind als die angegebene Anzahl von Tagen für die Speicherung der Protokolldateien durch den Dienst (in der Standardeinstellung sind dies Protokolldateien, die älter als 10 Tage sind).</span><span class="sxs-lookup"><span data-stu-id="cffb2-113">You can also configure a time of day when you want Device Update Web service to automatically delete log files that are older than the number of days you configured the service to keep log files (by default, that is log files that are more than 10 days old).</span></span> <span data-ttu-id="cffb2-114">Diese Einstellung kann nicht mit Skype Business Server-Systemsteuerung geändert werden.</span><span class="sxs-lookup"><span data-stu-id="cffb2-114">This setting cannot be modified using Skype for Business Server Control Panel.</span></span> <span data-ttu-id="cffb2-115">Stattdessen müssen Sie Skype für Business Server-Verwaltungsshell verwenden.</span><span class="sxs-lookup"><span data-stu-id="cffb2-115">Instead, you must use Skype for Business Server Management Shell.</span></span> <span data-ttu-id="cffb2-116">Um die Uhrzeit für das Löschen von abgelaufenen Protokolldateien anzugeben, verwenden Sie das Cmdlet " **New-CsDeviceUpdateConfiguration** " mit dem LogCleanUpTimeOfDay - Parameter.</span><span class="sxs-lookup"><span data-stu-id="cffb2-116">To specify the time of day to delete expired log files, use the **New-CsDeviceUpdateConfiguration** cmdlet with the -LogCleanUpTimeOfDay parameter.</span></span> <span data-ttu-id="cffb2-117">Weitere Informationen hierzu finden Sie unter [New-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="cffb2-117">For details, see [New-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps).</span></span>

> [!CAUTION]
> <span data-ttu-id="cffb2-p104">Durch das dauerhafte Löschen von Dateien werden diese aus dem Dateisystem entfernt. Nach dem Löschen einer Datei kann diese nicht mehr wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="cffb2-p104">Purging files permanently removes them from the file system. After you purge a file, it cannot be recovered.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="cffb2-120">Mögliche Aufgaben</span><span class="sxs-lookup"><span data-stu-id="cffb2-120">Tasks you can perform</span></span>

<span data-ttu-id="cffb2-121">Auf der Seite **Geräteprotokollkonfiguration** können Sie die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="cffb2-121">You can perform the following tasks on the **Device Log Configuration** page:</span></span>

- <span data-ttu-id="cffb2-122">Hinzufügen einer Geräteprotokollkonfiguration auf globaler Ebene oder für einen bestimmten Standort oder Pool</span><span class="sxs-lookup"><span data-stu-id="cffb2-122">Add a device log configuration globally or for a particular site or pool.</span></span>

- <span data-ttu-id="cffb2-123">Ändern der Optionen für eine vorhandene Geräteprotokollkonfiguration</span><span class="sxs-lookup"><span data-stu-id="cffb2-123">Modify the options for an existing device log configuration.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="cffb2-124">Referenz zur Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="cffb2-124">UI Reference</span></span>

<span data-ttu-id="cffb2-125">In den folgenden Listen werden die Menüs, Befehle, Felder und Eigenschaften der Seite beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cffb2-125">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="cffb2-126">**Neue** Sie können eine neue geräteprotokollkonfiguration mit dem folgenden Bereich hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="cffb2-126">**New** You can add a new device log configuration with the following scope:</span></span>

  - <span data-ttu-id="cffb2-127">Global</span><span class="sxs-lookup"><span data-stu-id="cffb2-127">Global</span></span>

  - <span data-ttu-id="cffb2-128">Standort</span><span class="sxs-lookup"><span data-stu-id="cffb2-128">Site</span></span>

- <span data-ttu-id="cffb2-129">**Bearbeiten** Sie können die Optionen in der Liste eine geräteprotokollkonfiguration ändern.</span><span class="sxs-lookup"><span data-stu-id="cffb2-129">**Edit** You can change the options of a device log configuration in the list.</span></span> <span data-ttu-id="cffb2-130">Mit dieser Option haben Sie folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="cffb2-130">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="cffb2-131">**Details anzeigen** Diese Option öffnet ein Dialogfeld, in dem Sie die Optionen für eine geräteprotokollkonfiguration ändern können.</span><span class="sxs-lookup"><span data-stu-id="cffb2-131">**Show details** This option opens a dialog box in which you can change the options for a device log configuration.</span></span>

  - <span data-ttu-id="cffb2-132">**Wählen Sie alle** Diese Option werden alle geräteprotokollkonfigurationen der Liste ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="cffb2-132">**Select All** This option selects all device log configuration in the list.</span></span>

  - <span data-ttu-id="cffb2-133">**Löschen** Diese Option werden alle ausgewählten geräteprotokollkonfigurationen gelöscht.</span><span class="sxs-lookup"><span data-stu-id="cffb2-133">**Delete** This option deletes all selected device log configuration.</span></span>

- <span data-ttu-id="cffb2-134">**Aktualisieren** Sie können Log Liste mit den Gerätekonfigurationen zum Überprüfen des Status der Optionen aller geräteprotokollkonfigurationen aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="cffb2-134">**Refresh** You can refresh the device log configuration list to verify the status of the options of all device log configuration.</span></span>

## <a name="see-also"></a><span data-ttu-id="cffb2-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cffb2-135">See also</span></span>

[<span data-ttu-id="cffb2-136">Modify Settings for Log Files of Device Update Activity</span><span class="sxs-lookup"><span data-stu-id="cffb2-136">Modify Settings for Log Files of Device Update Activity</span></span>](https://technet.microsoft.com/library/9b57f126-1853-43b3-bbd4-06401e6498bd.aspx)
