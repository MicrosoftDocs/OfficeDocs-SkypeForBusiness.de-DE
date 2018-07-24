---
title: Gerät Protokoll Konfiguration bearbeiten
ms.author: SerdarS
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceUpdateEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e534e6a5-fb3e-40b1-a189-fce64c42f512
description: Sie können auf der Seite Protokolleinstellungen bearbeiten eine geräteprotokollkonfiguration hinzufügen, die bestimmt, die maximale Cachegröße, die maximale Größe der Protokolldatei oder die Zeitdauer, die eine Protokolldatei gespeichert wird, bevor es gelöscht wird. Sie können diese Einstellungen entsprechend den Anforderungen der Organisation ändern.
ms.openlocfilehash: fac6dd8aae7c1081c268d35ea0336b41eb7c6f55
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20969994"
---
# <a name="device-log-configuration-edit"></a><span data-ttu-id="ffb50-104">Geräteprotokollkonfiguration: Bearbeiten</span><span class="sxs-lookup"><span data-stu-id="ffb50-104">Device Log Configuration: Edit</span></span>
 
<span data-ttu-id="ffb50-105">Sie können auf der Seite **Protokolleinstellungen bearbeiten** eine geräteprotokollkonfiguration hinzufügen, die bestimmt, die maximale Cachegröße, die maximale Größe der Protokolldatei oder die Zeitdauer, die eine Protokolldatei gespeichert wird, bevor es gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="ffb50-105">You can add a device log configuration to the **Edit Log Setting** page that determines the maximum log cache size, maximum log file size, or length of time a log file is kept before it is purged.</span></span> <span data-ttu-id="ffb50-106">Sie können diese Einstellungen entsprechend den Anforderungen der Organisation ändern.</span><span class="sxs-lookup"><span data-stu-id="ffb50-106">You can change these settings according to your organization's requirements.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="ffb50-p103">Durch das dauerhafte Löschen von Dateien werden diese aus dem Dateisystem entfernt. Nach dem Löschen einer Datei kann diese nicht mehr wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="ffb50-p103">Purging files permanently removes them from the file system. After you purge a file, it cannot be recovered.</span></span> 
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="ffb50-109">Mögliche Aufgaben</span><span class="sxs-lookup"><span data-stu-id="ffb50-109">Tasks you can perform</span></span>

<span data-ttu-id="ffb50-110">Klicken Sie auf der Seite **Protokolleinstellungen bearbeiten** können Sie die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="ffb50-110">You can perform the following tasks on the **Edit Log Setting** page:</span></span>
  
- <span data-ttu-id="ffb50-111">Hinzufügen einer geräteprotokollkonfiguration global oder für einen bestimmten Standort.</span><span class="sxs-lookup"><span data-stu-id="ffb50-111">Add a device log configuration globally or for a particular site.</span></span>
    
- <span data-ttu-id="ffb50-112">Ändern der Optionen für eine vorhandene Geräteprotokollkonfiguration</span><span class="sxs-lookup"><span data-stu-id="ffb50-112">Modify the options for an existing device log configuration.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="ffb50-113">Referenz zur Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="ffb50-113">UI Reference</span></span>

<span data-ttu-id="ffb50-114">In den folgenden Listen werden die Menüs, Befehle, Felder und Eigenschaften der Seite beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ffb50-114">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="ffb50-115">**Bereich** Gibt den Bereich (Global oder Standort) der geräteprotokollkonfiguration an.</span><span class="sxs-lookup"><span data-stu-id="ffb50-115">**Scope** Identifies the scope (Global or Site) of the device log configuration.</span></span>
    
- <span data-ttu-id="ffb50-116">**Name** Sie können hinzufügen oder ändern den Namen der geräteprotokollkonfiguration an.</span><span class="sxs-lookup"><span data-stu-id="ffb50-116">**Name** You can add or modify the name of the device log configuration.</span></span>
    
- <span data-ttu-id="ffb50-117">**Maximale Dateigröße (Byte)** Sie können die maximale Größe angeben, die eine Protokolldatei werden kann, bevor es gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="ffb50-117">**Maximum file size (bytes)** You can specify the maximum size a log file can become before it is purged.</span></span> <span data-ttu-id="ffb50-118">Der Standardwert ist 1,024,000 Bytes (1 MB).</span><span class="sxs-lookup"><span data-stu-id="ffb50-118">The default is 1,024,000 bytes (1 MB).</span></span>
    
- <span data-ttu-id="ffb50-119">**Maximale Cachegröße (Bytes)** Sie können die maximale Datenmenge (in Bytes) angeben, die im Dateicache melden Sie sich vor dem aufbewahrt werden können, dass der Cache gelöscht werden muss und die Daten werden in einer Protokolldatei geschrieben.</span><span class="sxs-lookup"><span data-stu-id="ffb50-119">**Maximum cache size (bytes)** You can specify the maximum amount of information (in bytes) that can be held in the log file cache before that cache must be cleared and the data is written to a log file.</span></span> <span data-ttu-id="ffb50-120">Der Standardwert ist 512,000 Byte (0,5 MB).</span><span class="sxs-lookup"><span data-stu-id="ffb50-120">The default is 512,000 bytes (0.5 MB).</span></span>
    
- <span data-ttu-id="ffb50-121">**Minuten (1 bis 60) Cache zu leeren.** Sie können angeben, wie oft wird im Protokoll Dateicache gespeicherten Informationen in die aktuelle Protokolldatei geschrieben.</span><span class="sxs-lookup"><span data-stu-id="ffb50-121">**Minutes to flush cache (1-60)** You can specify how often information stored in the log file cache is written to the actual log file.</span></span> <span data-ttu-id="ffb50-122">Nachdem die Daten angemeldet ist, wird der Cache gelöscht.</span><span class="sxs-lookup"><span data-stu-id="ffb50-122">After the data is logged, the cache is cleared.</span></span> <span data-ttu-id="ffb50-123">Der Standardwert beträgt fünf Minuten.</span><span class="sxs-lookup"><span data-stu-id="ffb50-123">The default is five minutes.</span></span>
    
- <span data-ttu-id="ffb50-124">**Tage (1-365)-Protokolldateien aufbewahrt werden sollen** Sie können die Anzahl der Tage angeben, die die Protokolldateien aufbewahrt werden, bevor sie gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="ffb50-124">**Days to keep log files (1-365)** You can specify the number of days the log files are kept before they are purged.</span></span> <span data-ttu-id="ffb50-125">Der Standardwert ist 10 Tage.</span><span class="sxs-lookup"><span data-stu-id="ffb50-125">The default is 10 days.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ffb50-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ffb50-126">See also</span></span>

[<span data-ttu-id="ffb50-127">Geräteprotokollkonfiguration</span><span class="sxs-lookup"><span data-stu-id="ffb50-127">Device Log Configuration</span></span>](device-log-configuration.md)