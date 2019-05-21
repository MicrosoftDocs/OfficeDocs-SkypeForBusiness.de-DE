---
title: Geräteprotokoll-Konfigurations Bearbeitung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceUpdateEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e534e6a5-fb3e-40b1-a189-fce64c42f512
description: Sie können der Seite Protokolleinstellungen bearbeiten eine geräteprotokoll Konfiguration hinzufügen, die die maximale Größe des Protokollcaches, die maximale Protokolldateigröße oder die Zeitdauer festlegt, die eine Protokolldatei aufbewahrt wird, bevor Sie bereinigt wird. Sie können diese Einstellungen entsprechend den Anforderungen Ihrer Organisation ändern.
ms.openlocfilehash: 51804fb420c940494017cde86f3f8c62bd335424
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34285960"
---
# <a name="device-log-configuration-edit"></a><span data-ttu-id="87cfc-104">Geräteprotokollkonfiguration: Bearbeiten</span><span class="sxs-lookup"><span data-stu-id="87cfc-104">Device Log Configuration: Edit</span></span>
 
<span data-ttu-id="87cfc-105">Sie können der Seite **Protokolleinstellungen bearbeiten** eine geräteprotokoll Konfiguration hinzufügen, die die maximale Größe des Protokollcaches, die maximale Protokolldateigröße oder die Zeitdauer festlegt, die eine Protokolldatei aufbewahrt wird, bevor Sie bereinigt wird.</span><span class="sxs-lookup"><span data-stu-id="87cfc-105">You can add a device log configuration to the **Edit Log Setting** page that determines the maximum log cache size, maximum log file size, or length of time a log file is kept before it is purged.</span></span> <span data-ttu-id="87cfc-106">Sie können diese Einstellungen entsprechend den Anforderungen Ihrer Organisation ändern.</span><span class="sxs-lookup"><span data-stu-id="87cfc-106">You can change these settings according to your organization's requirements.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="87cfc-p103">Durch das dauerhafte Löschen von Dateien werden diese aus dem Dateisystem entfernt. Nach dem Löschen einer Datei kann diese nicht mehr wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="87cfc-p103">Purging files permanently removes them from the file system. After you purge a file, it cannot be recovered.</span></span> 
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="87cfc-109">Mögliche Aufgaben</span><span class="sxs-lookup"><span data-stu-id="87cfc-109">Tasks you can perform</span></span>

<span data-ttu-id="87cfc-110">Auf der Seite **Protokolleinstellungen bearbeiten** können Sie die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="87cfc-110">You can perform the following tasks on the **Edit Log Setting** page:</span></span>
  
- <span data-ttu-id="87cfc-111">Fügen Sie eine geräteprotokoll Konfiguration Global oder für eine bestimmte Website hinzu.</span><span class="sxs-lookup"><span data-stu-id="87cfc-111">Add a device log configuration globally or for a particular site.</span></span>
    
- <span data-ttu-id="87cfc-112">Ändern der Optionen für eine vorhandene Geräteprotokollkonfiguration</span><span class="sxs-lookup"><span data-stu-id="87cfc-112">Modify the options for an existing device log configuration.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="87cfc-113">Referenz zur Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="87cfc-113">UI Reference</span></span>

<span data-ttu-id="87cfc-114">In den folgenden Listen werden die Menüs, Befehle, Felder und Eigenschaften der Seite beschrieben.</span><span class="sxs-lookup"><span data-stu-id="87cfc-114">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="87cfc-115">**Bereich** Identifiziert den Bereich (Global oder Website) der geräteprotokoll Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="87cfc-115">**Scope** Identifies the scope (Global or Site) of the device log configuration.</span></span>
    
- <span data-ttu-id="87cfc-116">**Name** Sie können den Namen der geräteprotokoll Konfiguration hinzufügen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="87cfc-116">**Name** You can add or modify the name of the device log configuration.</span></span>
    
- <span data-ttu-id="87cfc-117">**Maximale Dateigröße (Bytes)** Sie können die maximale Größe angeben, die eine Protokolldatei erhalten kann, bevor Sie bereinigt wird.</span><span class="sxs-lookup"><span data-stu-id="87cfc-117">**Maximum file size (bytes)** You can specify the maximum size a log file can become before it is purged.</span></span> <span data-ttu-id="87cfc-118">Der Standardwert ist 1.024.000 Bytes (1 MB).</span><span class="sxs-lookup"><span data-stu-id="87cfc-118">The default is 1,024,000 bytes (1 MB).</span></span>
    
- <span data-ttu-id="87cfc-119">**Maximale Cachegröße (Bytes)** Sie können die maximale Menge an Informationen (in Byte) angeben, die im Protokolldatei Cache gespeichert werden können, bevor dieser Cache gelöscht werden muss und die Daten in eine Protokolldatei geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="87cfc-119">**Maximum cache size (bytes)** You can specify the maximum amount of information (in bytes) that can be held in the log file cache before that cache must be cleared and the data is written to a log file.</span></span> <span data-ttu-id="87cfc-120">Der Standardwert ist 512.000 Bytes (0,5 MB).</span><span class="sxs-lookup"><span data-stu-id="87cfc-120">The default is 512,000 bytes (0.5 MB).</span></span>
    
- <span data-ttu-id="87cfc-121">**Minuten zum Leeren des Caches (1-60)** Sie können angeben, wie oft im Protokolldatei Cache gespeicherte Informationen in die eigentliche Protokolldatei geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="87cfc-121">**Minutes to flush cache (1-60)** You can specify how often information stored in the log file cache is written to the actual log file.</span></span> <span data-ttu-id="87cfc-122">Nachdem die Daten protokolliert wurden, wird der Cache gelöscht.</span><span class="sxs-lookup"><span data-stu-id="87cfc-122">After the data is logged, the cache is cleared.</span></span> <span data-ttu-id="87cfc-123">Der Standardwert ist fünf Minuten.</span><span class="sxs-lookup"><span data-stu-id="87cfc-123">The default is five minutes.</span></span>
    
- <span data-ttu-id="87cfc-124">**Tage, um Protokolldateien zu speichern (1-365)** Sie können angeben, wie viele Tage die Protokolldateien aufbewahrt werden, bevor Sie gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="87cfc-124">**Days to keep log files (1-365)** You can specify the number of days the log files are kept before they are purged.</span></span> <span data-ttu-id="87cfc-125">Der Standardwert ist 10 Tage.</span><span class="sxs-lookup"><span data-stu-id="87cfc-125">The default is 10 days.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="87cfc-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="87cfc-126">See also</span></span>

[<span data-ttu-id="87cfc-127">Geräteprotokollkonfiguration</span><span class="sxs-lookup"><span data-stu-id="87cfc-127">Device Log Configuration</span></span>](device-log-configuration.md)
