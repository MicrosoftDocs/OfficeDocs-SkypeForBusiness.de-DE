---
title: 'Lync Server 2013: Ändern von Einstellungen für Geräte Aktualisierungsprotokolldateien'
description: 'Lync Server 2013: Ändern Sie die Einstellungen für Geräte Aktualisierungsprotokolldateien.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify settings for Device Update log files
ms:assetid: 9b57f126-1853-43b3-bbd4-06401e6498bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182554(v=OCS.15)
ms:contentKeyID: 48184975
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c2086e11a67207a00ca99773cc818106b16d05c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566971"
---
# <a name="modify-settings-for-device-update-log-files-in-lync-server-2013"></a><span data-ttu-id="81b72-103">Ändern der Einstellungen für Geräte Aktualisierungsprotokolldateien in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81b72-103">Modify settings for Device Update log files in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81b72-104">_**Letztes Änderungsstand des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="81b72-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="81b72-105">Sie können mithilfe von lync Server-Systemsteuerung oder lync Server-Verwaltungsshell Einstellungen für die Protokollierung von Geräte Aktualisierungsinformationen in Ihrer Organisation ändern.</span><span class="sxs-lookup"><span data-stu-id="81b72-105">You can change settings for how device update information is logged in your organization by using Lync Server Control Panel or Lync Server Management Shell.</span></span> <span data-ttu-id="81b72-106">Die folgende Tabelle zeigt, welche Einstellungen geändert werden können und welche Tools Sie zum Ändern der Einstellungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="81b72-106">The following table shows which settings are modifiable, and which tool(s) you use to modify the settings.</span></span>

<span data-ttu-id="81b72-107">Protokolleinstellungen können global oder pro Standort geändert und angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="81b72-107">Log settings can be changed and applied globally, or per site.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="81b72-108">Ändern</span><span class="sxs-lookup"><span data-stu-id="81b72-108">To change</span></span></th>
<th><span data-ttu-id="81b72-109">Verwendung</span><span class="sxs-lookup"><span data-stu-id="81b72-109">Use</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="81b72-110">Die maximale Größe (in Byte) für eine Protokolldatei</span><span class="sxs-lookup"><span data-stu-id="81b72-110">The maximum size (in bytes) for a log file</span></span></p></td>
<td><p><span data-ttu-id="81b72-111">Lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="81b72-111">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="81b72-112">oder</span><span class="sxs-lookup"><span data-stu-id="81b72-112">-or-</span></span></p>
<p><span data-ttu-id="81b72-113">Lync Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="81b72-113">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81b72-114">Die maximale Menge an Informationen (in Bytes), die im Cache gespeichert werden können.</span><span class="sxs-lookup"><span data-stu-id="81b72-114">The maximum amount of information (in bytes) that can be held in the cache</span></span></p></td>
<td><p><span data-ttu-id="81b72-115">Lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="81b72-115">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="81b72-116">oder</span><span class="sxs-lookup"><span data-stu-id="81b72-116">-or-</span></span></p>
<p><span data-ttu-id="81b72-117">Lync Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="81b72-117">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81b72-118">Wie oft (in Minuten) zwischengespeicherte Informationen in die Protokolldatei geschrieben werden sollen</span><span class="sxs-lookup"><span data-stu-id="81b72-118">How often (in minutes) to write cached information to the log file</span></span></p></td>
<td><p><span data-ttu-id="81b72-119">Lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="81b72-119">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="81b72-120">oder</span><span class="sxs-lookup"><span data-stu-id="81b72-120">-or-</span></span></p>
<p><span data-ttu-id="81b72-121">Lync Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="81b72-121">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81b72-122">Wie lange (in Tagen), um Protokolldateien beizubehalten</span><span class="sxs-lookup"><span data-stu-id="81b72-122">How long (in days) to keep log files</span></span></p></td>
<td><p><span data-ttu-id="81b72-123">Lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="81b72-123">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="81b72-124">oder</span><span class="sxs-lookup"><span data-stu-id="81b72-124">-or-</span></span></p>
<p><span data-ttu-id="81b72-125">Lync Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="81b72-125">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81b72-126">Wann (Tageszeit) zum Überprüfen auf abgelaufene Dateien, die gelöscht werden sollten</span><span class="sxs-lookup"><span data-stu-id="81b72-126">When (time of day) to check for expired files that should be deleted</span></span></p></td>
<td><p><span data-ttu-id="81b72-127">Lync Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="81b72-127">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81b72-128">Welche Protokolldatei Erweiterungen zugelassen werden sollen</span><span class="sxs-lookup"><span data-stu-id="81b72-128">What log file extensions to permit</span></span></p></td>
<td><p><span data-ttu-id="81b72-129">Lync Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="81b72-129">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81b72-130">Welche Protokolldatei Typen aufbewahrt werden sollen</span><span class="sxs-lookup"><span data-stu-id="81b72-130">Which log file types to retain</span></span></p></td>
<td><p><span data-ttu-id="81b72-131">Lync Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="81b72-131">Lync Server Management Shell</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-change-logging-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="81b72-132">So ändern Sie die Protokollierungseinstellungen mithilfe von lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="81b72-132">To change logging settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="81b72-133">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="81b72-133">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="81b72-134">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="81b72-134">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="81b72-135">Klicken Sie in der linken Navigationsleiste auf **Clients** und dann auf **Geräteprotokollkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="81b72-135">In the left navigation bar, click **Clients**, and then click **Device Log Configuration**.</span></span>

3.  <span data-ttu-id="81b72-136">Doppelklicken Sie auf der Seite **Geräteprotokollkonfiguration** auf die Konfiguration, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="81b72-136">On the **Device Log Configuration** page, double-click the configuration that you want to change.</span></span>

4.  <span data-ttu-id="81b72-137">Ändern Sie im Dialogfeld **Protokolleinstellung bearbeiten** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="81b72-137">In the **Edit Log Setting** dialog box, change any of the following settings:</span></span>
    
      - <span data-ttu-id="81b72-138">**Maximale Dateigröße (Bytes)**     Gibt die maximale Größe an, die eine Protokolldatei erhalten werden kann, bevor Sie gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="81b72-138">**Maximum file size (bytes)**   Specifies the maximum size a log file can become before it is purged.</span></span> <span data-ttu-id="81b72-139">Der Standardwert beträgt 1.024.000 (1 MB).</span><span class="sxs-lookup"><span data-stu-id="81b72-139">The default is 1,024,000 bytes (1 MB).</span></span>
    
      - <span data-ttu-id="81b72-140">**Maximale Cachegröße (Bytes)**     Gibt die maximale Menge an Informationen (in Byte) an, die im Protokolldatei Cache aufbewahrt werden können, bevor dieser Cache gelöscht werden muss und die Daten in eine Protokolldatei geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="81b72-140">**Maximum cache size (bytes)**   Specifies the maximum amount of information (in bytes) that can be held in the log file cache before that cache must be cleared and the data is written to a log file.</span></span> <span data-ttu-id="81b72-141">Der Standardwert beträgt 512.000 (0,5 MB).</span><span class="sxs-lookup"><span data-stu-id="81b72-141">The default is 512,000 bytes (0.5 MB).</span></span>
    
      - <span data-ttu-id="81b72-142">**Anzahl der Minuten für leeren Zwischenspeicher (1-60)**     Gibt an, wie oft im Protokolldatei Cache gespeicherte Informationen in die tatsächliche Protokolldatei geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="81b72-142">**Number of minutes to flush cache (1-60)**   Indicates how often information stored in the log file cache is written to the actual log file.</span></span> <span data-ttu-id="81b72-143">Nachdem die Daten protokolliert wurden, wird der Cache geleert.</span><span class="sxs-lookup"><span data-stu-id="81b72-143">After the data is logged, the cache is cleared.</span></span> <span data-ttu-id="81b72-144">Der Standardwert beträgt fünf Minuten.</span><span class="sxs-lookup"><span data-stu-id="81b72-144">The default is five minutes.</span></span>
    
      - <span data-ttu-id="81b72-145">**Anzahl der Tage, die Protokolldateien aufbewahrt werden sollen (1-365)**     Gibt an, wie viele Tage die Protokolldateien aufbewahrt werden, bevor Sie gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="81b72-145">**Number of days to keep log files (1-365)**   Specifies the number of days the log files are kept before they are purged.</span></span> <span data-ttu-id="81b72-146">Der Standardwert beträgt 10 Tage.</span><span class="sxs-lookup"><span data-stu-id="81b72-146">The default is 10 days.</span></span>

5.  <span data-ttu-id="81b72-147">Klicken Sie auf **Commit**.</span><span class="sxs-lookup"><span data-stu-id="81b72-147">Click **Commit**.</span></span>

</div>

<div>

## <a name="changing-logging-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="81b72-148">Ändern der Protokollierungseinstellungen mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="81b72-148">Changing Logging Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="81b72-149">Einstellungen für die Geräteupdate Protokolldatei können mithilfe von Windows PowerShell und dem Cmdlet "Cmdlet **festlegen** " geändert werden.</span><span class="sxs-lookup"><span data-stu-id="81b72-149">Device update log file settings can be modified by using Windows PowerShell and the **Set-CsDeviceUpdateConfiguration** cmdlet.</span></span> <span data-ttu-id="81b72-150">Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="81b72-150">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="81b72-151">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> .</span><span class="sxs-lookup"><span data-stu-id="81b72-151">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<span data-ttu-id="81b72-152">Die folgenden Beispiele zeigen eine Reihe von Möglichkeiten, mit denen Sie die Einstellungen mithilfe von " **CsDeviceUpdateConfiguration** " ändern können.</span><span class="sxs-lookup"><span data-stu-id="81b72-152">The following examples show a couple of the ways that you can use **Set-CsDeviceUpdateConfiguration** to modify settings.</span></span>

<div>

## <a name="to-modify-the-maximum-log-file-size-and-the-log-cleanup-interval"></a><span data-ttu-id="81b72-153">So ändern Sie die maximale Protokolldateigröße und das Protokoll Bereinigungsintervall</span><span class="sxs-lookup"><span data-stu-id="81b72-153">To modify the maximum log file size and the log cleanup interval</span></span>

  - <span data-ttu-id="81b72-154">Mit dem folgenden Befehl werden die Einstellungen für das Geräteupdate Protokoll geändert, die auf den Standort "Redmond" angewendet wurden.</span><span class="sxs-lookup"><span data-stu-id="81b72-154">The following command modifies the device update log settings applied to the Redmond site.</span></span> <span data-ttu-id="81b72-155">In diesem Beispiel wird die maximale Größe der Protokolldatei auf 204800 Byte festgelegt, und das Intervall für die Protokoll Bereinigung wird auf 14 Tage festgelegt.</span><span class="sxs-lookup"><span data-stu-id="81b72-155">In this example, the maximum log file size is set to 204800 bytes and the log cleanup interval is set to 14 days.</span></span>
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -MaxLogFileSize 204800 -LogCleanUpInterval 14.00:00:00

</div>

<div>

## <a name="to-modify-the-log-cleanup-time-of-day"></a><span data-ttu-id="81b72-156">So ändern Sie die Zeit des Protokoll Bereinigungs Tags</span><span class="sxs-lookup"><span data-stu-id="81b72-156">To modify the log cleanup time of day</span></span>

  - <span data-ttu-id="81b72-157">Mit diesem Befehl wird die Zeit für die Protokoll Bereinigung für den Standort "Redmond" auf 3:00 Uhr festgelegt.</span><span class="sxs-lookup"><span data-stu-id="81b72-157">This command sets the log cleanup time for the Redmond site to 3:00 AM.</span></span>
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupTimeOfDay 03:00

</div>

<span data-ttu-id="81b72-158">Ausführliche Informationen finden Sie im Hilfethema zum Cmdlet " [CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsDeviceUpdateConfiguration) ".</span><span class="sxs-lookup"><span data-stu-id="81b72-158">For details, see the Help topic for the [Set-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsDeviceUpdateConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

