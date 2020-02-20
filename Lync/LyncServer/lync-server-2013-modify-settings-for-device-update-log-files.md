---
title: 'Lync Server 2013: Ändern von Einstellungen für Geräte Aktualisierungsprotokolldateien'
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
ms.openlocfilehash: 0734050b050c00a8f7a0a262e69451a223dfb6fd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149464"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="modify-settings-for-device-update-log-files-in-lync-server-2013"></a><span data-ttu-id="05fdc-102">Ändern der Einstellungen für Geräte Aktualisierungsprotokolldateien in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05fdc-102">Modify settings for Device Update log files in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05fdc-103">_**Letztes Änderungsstand des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="05fdc-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="05fdc-104">Sie können mithilfe von lync Server-Systemsteuerung oder lync Server-Verwaltungsshell Einstellungen für die Protokollierung von Geräte Aktualisierungsinformationen in Ihrer Organisation ändern.</span><span class="sxs-lookup"><span data-stu-id="05fdc-104">You can change settings for how device update information is logged in your organization by using Lync Server Control Panel or Lync Server Management Shell.</span></span> <span data-ttu-id="05fdc-105">Die folgende Tabelle zeigt, welche Einstellungen geändert werden können und welche Tools Sie zum Ändern der Einstellungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="05fdc-105">The following table shows which settings are modifiable, and which tool(s) you use to modify the settings.</span></span>

<span data-ttu-id="05fdc-106">Protokolleinstellungen können global oder pro Standort geändert und angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="05fdc-106">Log settings can be changed and applied globally, or per site.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="05fdc-107">Ändern</span><span class="sxs-lookup"><span data-stu-id="05fdc-107">To change</span></span></th>
<th><span data-ttu-id="05fdc-108">Verwendung</span><span class="sxs-lookup"><span data-stu-id="05fdc-108">Use</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="05fdc-109">Die maximale Größe (in Byte) für eine Protokolldatei</span><span class="sxs-lookup"><span data-stu-id="05fdc-109">The maximum size (in bytes) for a log file</span></span></p></td>
<td><p><span data-ttu-id="05fdc-110">Lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="05fdc-110">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="05fdc-111">- oder -</span><span class="sxs-lookup"><span data-stu-id="05fdc-111">-or-</span></span></p>
<p><span data-ttu-id="05fdc-112">Lync Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="05fdc-112">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05fdc-113">Die maximale Menge an Informationen (in Bytes), die im Cache gespeichert werden können.</span><span class="sxs-lookup"><span data-stu-id="05fdc-113">The maximum amount of information (in bytes) that can be held in the cache</span></span></p></td>
<td><p><span data-ttu-id="05fdc-114">Lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="05fdc-114">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="05fdc-115">- oder -</span><span class="sxs-lookup"><span data-stu-id="05fdc-115">-or-</span></span></p>
<p><span data-ttu-id="05fdc-116">Lync Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="05fdc-116">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05fdc-117">Wie oft (in Minuten) zwischengespeicherte Informationen in die Protokolldatei geschrieben werden sollen</span><span class="sxs-lookup"><span data-stu-id="05fdc-117">How often (in minutes) to write cached information to the log file</span></span></p></td>
<td><p><span data-ttu-id="05fdc-118">Lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="05fdc-118">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="05fdc-119">- oder -</span><span class="sxs-lookup"><span data-stu-id="05fdc-119">-or-</span></span></p>
<p><span data-ttu-id="05fdc-120">Lync Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="05fdc-120">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05fdc-121">Wie lange (in Tagen), um Protokolldateien beizubehalten</span><span class="sxs-lookup"><span data-stu-id="05fdc-121">How long (in days) to keep log files</span></span></p></td>
<td><p><span data-ttu-id="05fdc-122">Lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="05fdc-122">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="05fdc-123">- oder -</span><span class="sxs-lookup"><span data-stu-id="05fdc-123">-or-</span></span></p>
<p><span data-ttu-id="05fdc-124">Lync Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="05fdc-124">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05fdc-125">Wann (Tageszeit) zum Überprüfen auf abgelaufene Dateien, die gelöscht werden sollten</span><span class="sxs-lookup"><span data-stu-id="05fdc-125">When (time of day) to check for expired files that should be deleted</span></span></p></td>
<td><p><span data-ttu-id="05fdc-126">Lync Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="05fdc-126">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05fdc-127">Welche Protokolldatei Erweiterungen zugelassen werden sollen</span><span class="sxs-lookup"><span data-stu-id="05fdc-127">What log file extensions to permit</span></span></p></td>
<td><p><span data-ttu-id="05fdc-128">Lync Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="05fdc-128">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05fdc-129">Welche Protokolldatei Typen aufbewahrt werden sollen</span><span class="sxs-lookup"><span data-stu-id="05fdc-129">Which log file types to retain</span></span></p></td>
<td><p><span data-ttu-id="05fdc-130">Lync Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="05fdc-130">Lync Server Management Shell</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-change-logging-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="05fdc-131">So ändern Sie die Protokollierungseinstellungen mithilfe von lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="05fdc-131">To change logging settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="05fdc-132">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="05fdc-132">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="05fdc-133">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="05fdc-133">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="05fdc-134">Klicken Sie in der linken Navigationsleiste auf **Clients** und dann auf **Geräteprotokollkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="05fdc-134">In the left navigation bar, click **Clients**, and then click **Device Log Configuration**.</span></span>

3.  <span data-ttu-id="05fdc-135">Doppelklicken Sie auf der Seite **Geräteprotokollkonfiguration** auf die Konfiguration, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="05fdc-135">On the **Device Log Configuration** page, double-click the configuration that you want to change.</span></span>

4.  <span data-ttu-id="05fdc-136">Ändern Sie im Dialogfeld **Protokolleinstellung bearbeiten** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="05fdc-136">In the **Edit Log Setting** dialog box, change any of the following settings:</span></span>
    
      - <span data-ttu-id="05fdc-137">**Maximale Dateigröße (Bytes)**   gibt die maximale Größe an, mit der eine Protokolldatei gelöscht werden kann, bevor Sie bereinigt wird.</span><span class="sxs-lookup"><span data-stu-id="05fdc-137">**Maximum file size (bytes)**   Specifies the maximum size a log file can become before it is purged.</span></span> <span data-ttu-id="05fdc-138">Der Standardwert beträgt 1.024.000 (1 MB).</span><span class="sxs-lookup"><span data-stu-id="05fdc-138">The default is 1,024,000 bytes (1 MB).</span></span>
    
      - <span data-ttu-id="05fdc-139">**Maximale Cachegröße (Bytes)**   gibt die maximale Menge an Informationen (in Byte) an, die im Protokolldatei Cache aufbewahrt werden können, bevor dieser Cache gelöscht werden muss und die Daten in eine Protokolldatei geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="05fdc-139">**Maximum cache size (bytes)**   Specifies the maximum amount of information (in bytes) that can be held in the log file cache before that cache must be cleared and the data is written to a log file.</span></span> <span data-ttu-id="05fdc-140">Der Standardwert beträgt 512.000 (0,5 MB).</span><span class="sxs-lookup"><span data-stu-id="05fdc-140">The default is 512,000 bytes (0.5 MB).</span></span>
    
      - <span data-ttu-id="05fdc-141">**Anzahl der Minuten für das Leeren des Caches (1-60)**   gibt an, wie oft im Protokolldatei Cache gespeicherte Informationen in die tatsächliche Protokolldatei geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="05fdc-141">**Number of minutes to flush cache (1-60)**   Indicates how often information stored in the log file cache is written to the actual log file.</span></span> <span data-ttu-id="05fdc-142">Nachdem die Daten protokolliert wurden, wird der Cache geleert.</span><span class="sxs-lookup"><span data-stu-id="05fdc-142">After the data is logged, the cache is cleared.</span></span> <span data-ttu-id="05fdc-143">Der Standardwert beträgt fünf Minuten.</span><span class="sxs-lookup"><span data-stu-id="05fdc-143">The default is five minutes.</span></span>
    
      - <span data-ttu-id="05fdc-144">**Anzahl der Tage für die Aufbewahrung von Protokolldateien (1-365)**   gibt an, wie viele Tage die Protokolldateien aufbewahrt werden, bevor Sie gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="05fdc-144">**Number of days to keep log files (1-365)**   Specifies the number of days the log files are kept before they are purged.</span></span> <span data-ttu-id="05fdc-145">Der Standardwert beträgt 10 Tage.</span><span class="sxs-lookup"><span data-stu-id="05fdc-145">The default is 10 days.</span></span>

5.  <span data-ttu-id="05fdc-146">Klicken Sie auf **Commit**.</span><span class="sxs-lookup"><span data-stu-id="05fdc-146">Click **Commit**.</span></span>

</div>

<div>

## <a name="changing-logging-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="05fdc-147">Ändern der Protokollierungseinstellungen mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="05fdc-147">Changing Logging Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="05fdc-148">Einstellungen für die Geräteupdate Protokolldatei können mithilfe von Windows PowerShell und dem Cmdlet "Cmdlet **festlegen** " geändert werden.</span><span class="sxs-lookup"><span data-stu-id="05fdc-148">Device update log file settings can be modified by using Windows PowerShell and the **Set-CsDeviceUpdateConfiguration** cmdlet.</span></span> <span data-ttu-id="05fdc-149">Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="05fdc-149">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="05fdc-150">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>mithilfe von Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="05fdc-150">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<span data-ttu-id="05fdc-151">Die folgenden Beispiele zeigen eine Reihe von Möglichkeiten, mit denen Sie die Einstellungen mithilfe von " **CsDeviceUpdateConfiguration** " ändern können.</span><span class="sxs-lookup"><span data-stu-id="05fdc-151">The following examples show a couple of the ways that you can use **Set-CsDeviceUpdateConfiguration** to modify settings.</span></span>

<div>

## <a name="to-modify-the-maximum-log-file-size-and-the-log-cleanup-interval"></a><span data-ttu-id="05fdc-152">So ändern Sie die maximale Protokolldateigröße und das Protokoll Bereinigungsintervall</span><span class="sxs-lookup"><span data-stu-id="05fdc-152">To modify the maximum log file size and the log cleanup interval</span></span>

  - <span data-ttu-id="05fdc-153">Mit dem folgenden Befehl werden die Einstellungen für das Geräteupdate Protokoll geändert, die auf den Standort "Redmond" angewendet wurden.</span><span class="sxs-lookup"><span data-stu-id="05fdc-153">The following command modifies the device update log settings applied to the Redmond site.</span></span> <span data-ttu-id="05fdc-154">In diesem Beispiel wird die maximale Größe der Protokolldatei auf 204800 Byte festgelegt, und das Intervall für die Protokoll Bereinigung wird auf 14 Tage festgelegt.</span><span class="sxs-lookup"><span data-stu-id="05fdc-154">In this example, the maximum log file size is set to 204800 bytes and the log cleanup interval is set to 14 days.</span></span>
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -MaxLogFileSize 204800 -LogCleanUpInterval 14.00:00:00

</div>

<div>

## <a name="to-modify-the-log-cleanup-time-of-day"></a><span data-ttu-id="05fdc-155">So ändern Sie die Zeit des Protokoll Bereinigungs Tags</span><span class="sxs-lookup"><span data-stu-id="05fdc-155">To modify the log cleanup time of day</span></span>

  - <span data-ttu-id="05fdc-156">Mit diesem Befehl wird die Zeit für die Protokoll Bereinigung für den Standort "Redmond" auf 3:00 Uhr festgelegt.</span><span class="sxs-lookup"><span data-stu-id="05fdc-156">This command sets the log cleanup time for the Redmond site to 3:00 AM.</span></span>
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupTimeOfDay 03:00

</div>

<span data-ttu-id="05fdc-157">Ausführliche Informationen finden Sie im Hilfethema zum Cmdlet " [CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsDeviceUpdateConfiguration) ".</span><span class="sxs-lookup"><span data-stu-id="05fdc-157">For details, see the Help topic for the [Set-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsDeviceUpdateConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

