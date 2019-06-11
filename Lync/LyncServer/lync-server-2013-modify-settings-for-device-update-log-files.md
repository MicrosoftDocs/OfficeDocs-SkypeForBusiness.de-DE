---
title: 'Lync Server 2013: Ändern der Einstellungen für Geräte Aktualisierungsprotokolldateien'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify settings for Device Update log files
ms:assetid: 9b57f126-1853-43b3-bbd4-06401e6498bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182554(v=OCS.15)
ms:contentKeyID: 48184975
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37002e1043f990ae1e726301b9c720af35556201
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826885"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-settings-for-device-update-log-files-in-lync-server-2013"></a><span data-ttu-id="ce80d-102">Ändern der Einstellungen für Geräte Aktualisierungsprotokolldateien in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce80d-102">Modify settings for Device Update log files in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce80d-103">_**Letztes Änderungsdatum des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="ce80d-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="ce80d-104">Mithilfe der lync Server-Systemsteuerung oder der lync Server-Verwaltungsshell können Sie die Einstellungen für die Protokollierung von Geräte Aktualisierungsinformationen in Ihrer Organisation ändern.</span><span class="sxs-lookup"><span data-stu-id="ce80d-104">You can change settings for how device update information is logged in your organization by using Lync Server Control Panel or Lync Server Management Shell.</span></span> <span data-ttu-id="ce80d-105">In der folgenden Tabelle wird aufgezeigt, welche Einstellungen änderbar sind und welches Tool (e) Sie verwenden, um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="ce80d-105">The following table shows which settings are modifiable, and which tool(s) you use to modify the settings.</span></span>

<span data-ttu-id="ce80d-106">Protokolleinstellungen können global oder pro Website geändert und angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="ce80d-106">Log settings can be changed and applied globally, or per site.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ce80d-107">Zu ändern</span><span class="sxs-lookup"><span data-stu-id="ce80d-107">To change</span></span></th>
<th><span data-ttu-id="ce80d-108">Verwendung</span><span class="sxs-lookup"><span data-stu-id="ce80d-108">Use</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ce80d-109">Die maximale Größe (in Bytes) für eine Protokolldatei</span><span class="sxs-lookup"><span data-stu-id="ce80d-109">The maximum size (in bytes) for a log file</span></span></p></td>
<td><p><span data-ttu-id="ce80d-110">Lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="ce80d-110">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="ce80d-111">oder</span><span class="sxs-lookup"><span data-stu-id="ce80d-111">-or-</span></span></p>
<p><span data-ttu-id="ce80d-112">Lync Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="ce80d-112">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce80d-113">Die maximale Menge an Informationen (in Bytes), die im Cache gespeichert werden können</span><span class="sxs-lookup"><span data-stu-id="ce80d-113">The maximum amount of information (in bytes) that can be held in the cache</span></span></p></td>
<td><p><span data-ttu-id="ce80d-114">Lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="ce80d-114">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="ce80d-115">oder</span><span class="sxs-lookup"><span data-stu-id="ce80d-115">-or-</span></span></p>
<p><span data-ttu-id="ce80d-116">Lync Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="ce80d-116">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce80d-117">Wie oft (in Minuten), um zwischengespeicherte Informationen in die Protokolldatei zu schreiben</span><span class="sxs-lookup"><span data-stu-id="ce80d-117">How often (in minutes) to write cached information to the log file</span></span></p></td>
<td><p><span data-ttu-id="ce80d-118">Lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="ce80d-118">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="ce80d-119">oder</span><span class="sxs-lookup"><span data-stu-id="ce80d-119">-or-</span></span></p>
<p><span data-ttu-id="ce80d-120">Lync Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="ce80d-120">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce80d-121">Wie lange (in Tagen) Protokolldateien aufbewahrt werden</span><span class="sxs-lookup"><span data-stu-id="ce80d-121">How long (in days) to keep log files</span></span></p></td>
<td><p><span data-ttu-id="ce80d-122">Lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="ce80d-122">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="ce80d-123">oder</span><span class="sxs-lookup"><span data-stu-id="ce80d-123">-or-</span></span></p>
<p><span data-ttu-id="ce80d-124">Lync Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="ce80d-124">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce80d-125">Zeitpunkt (Tageszeit) zum Überprüfen auf abgelaufene Dateien, die gelöscht werden sollen</span><span class="sxs-lookup"><span data-stu-id="ce80d-125">When (time of day) to check for expired files that should be deleted</span></span></p></td>
<td><p><span data-ttu-id="ce80d-126">Lync Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="ce80d-126">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce80d-127">Welche Protokolldatei Erweiterungen zugelassen werden sollen</span><span class="sxs-lookup"><span data-stu-id="ce80d-127">What log file extensions to permit</span></span></p></td>
<td><p><span data-ttu-id="ce80d-128">Lync Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="ce80d-128">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce80d-129">Welche Protokolldatei Typen beibehalten werden sollen</span><span class="sxs-lookup"><span data-stu-id="ce80d-129">Which log file types to retain</span></span></p></td>
<td><p><span data-ttu-id="ce80d-130">Lync Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="ce80d-130">Lync Server Management Shell</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-change-logging-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="ce80d-131">So ändern Sie die Protokollierungseinstellungen mithilfe der lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="ce80d-131">To change logging settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="ce80d-132">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="ce80d-132">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ce80d-133">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ce80d-133">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="ce80d-134">Klicken Sie in der linken Navigationsleiste auf **Clients**, und klicken Sie dann auf **geräteprotokoll Konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="ce80d-134">In the left navigation bar, click **Clients**, and then click **Device Log Configuration**.</span></span>

3.  <span data-ttu-id="ce80d-135">Doppelklicken Sie auf der Seite **Device Log-Konfiguration** auf die Konfiguration, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="ce80d-135">On the **Device Log Configuration** page, double-click the configuration that you want to change.</span></span>

4.  <span data-ttu-id="ce80d-136">Ändern Sie im Dialogfeld **Protokolleinstellung bearbeiten** eine der folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="ce80d-136">In the **Edit Log Setting** dialog box, change any of the following settings:</span></span>
    
      - <span data-ttu-id="ce80d-137">**Maximale Dateigröße (Bytes)**   gibt die maximale Größe an, die eine Protokolldatei erhalten kann, bevor Sie bereinigt wird.</span><span class="sxs-lookup"><span data-stu-id="ce80d-137">**Maximum file size (bytes)**   Specifies the maximum size a log file can become before it is purged.</span></span> <span data-ttu-id="ce80d-138">Der Standardwert ist 1.024.000 Bytes (1 MB).</span><span class="sxs-lookup"><span data-stu-id="ce80d-138">The default is 1,024,000 bytes (1 MB).</span></span>
    
      - <span data-ttu-id="ce80d-139">**Maximale Cachegröße (Bytes)**   gibt die maximale Informationsmenge (in Byte) an, die im Protokolldatei Cache gespeichert werden kann, bevor dieser Cache gelöscht werden muss und die Daten in eine Protokolldatei geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="ce80d-139">**Maximum cache size (bytes)**   Specifies the maximum amount of information (in bytes) that can be held in the log file cache before that cache must be cleared and the data is written to a log file.</span></span> <span data-ttu-id="ce80d-140">Der Standardwert ist 512.000 Bytes (0,5 MB).</span><span class="sxs-lookup"><span data-stu-id="ce80d-140">The default is 512,000 bytes (0.5 MB).</span></span>
    
      - <span data-ttu-id="ce80d-141">**Die Anzahl der Minuten zum Leeren des Caches (1-60)**   gibt an, wie häufig im Protokolldatei Cache gespeicherte Informationen in die eigentliche Protokolldatei geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="ce80d-141">**Number of minutes to flush cache (1-60)**   Indicates how often information stored in the log file cache is written to the actual log file.</span></span> <span data-ttu-id="ce80d-142">Nachdem die Daten protokolliert wurden, wird der Cache gelöscht.</span><span class="sxs-lookup"><span data-stu-id="ce80d-142">After the data is logged, the cache is cleared.</span></span> <span data-ttu-id="ce80d-143">Der Standardwert ist fünf Minuten.</span><span class="sxs-lookup"><span data-stu-id="ce80d-143">The default is five minutes.</span></span>
    
      - <span data-ttu-id="ce80d-144">**Anzahl der Tage für die Beibehaltung von Protokolldateien (1-365)**   gibt an, wie viele Tage die Protokolldateien aufbewahrt werden, bevor Sie gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="ce80d-144">**Number of days to keep log files (1-365)**   Specifies the number of days the log files are kept before they are purged.</span></span> <span data-ttu-id="ce80d-145">Der Standardwert ist 10 Tage.</span><span class="sxs-lookup"><span data-stu-id="ce80d-145">The default is 10 days.</span></span>

5.  <span data-ttu-id="ce80d-146">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="ce80d-146">Click **Commit**.</span></span>

</div>

<div>

## <a name="changing-logging-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="ce80d-147">Ändern der Protokollierungseinstellungen mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="ce80d-147">Changing Logging Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="ce80d-148">Einstellungen für die Geräteupdate Protokolldatei können mithilfe von Windows PowerShell und dem Cmdlet " **Satz-CsDeviceUpdateConfiguration** " geändert werden.</span><span class="sxs-lookup"><span data-stu-id="ce80d-148">Device update log file settings can be modified by using Windows PowerShell and the **Set-CsDeviceUpdateConfiguration** cmdlet.</span></span> <span data-ttu-id="ce80d-149">Dieses Cmdlet kann entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ce80d-149">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ce80d-150">Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="ce80d-150">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<span data-ttu-id="ce80d-151">Die folgenden Beispiele zeigen eine Reihe von Möglichkeiten, wie Sie mit " **CsDeviceUpdateConfiguration** " Einstellungen ändern können.</span><span class="sxs-lookup"><span data-stu-id="ce80d-151">The following examples show a couple of the ways that you can use **Set-CsDeviceUpdateConfiguration** to modify settings.</span></span>

<div>

## <a name="to-modify-the-maximum-log-file-size-and-the-log-cleanup-interval"></a><span data-ttu-id="ce80d-152">So ändern Sie die maximale Protokolldateigröße und das Protokoll Bereinigungsintervall</span><span class="sxs-lookup"><span data-stu-id="ce80d-152">To modify the maximum log file size and the log cleanup interval</span></span>

  - <span data-ttu-id="ce80d-153">Mit dem folgenden Befehl werden die Einstellungen für das Geräteupdate Protokoll geändert, die auf die Redmond-Website angewendet wurden.</span><span class="sxs-lookup"><span data-stu-id="ce80d-153">The following command modifies the device update log settings applied to the Redmond site.</span></span> <span data-ttu-id="ce80d-154">In diesem Beispiel ist die maximale Protokolldateigröße auf 204800 Bytes und das Protokoll Bereinigungsintervall auf 14 Tage eingestellt.</span><span class="sxs-lookup"><span data-stu-id="ce80d-154">In this example, the maximum log file size is set to 204800 bytes and the log cleanup interval is set to 14 days.</span></span>
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -MaxLogFileSize 204800 -LogCleanUpInterval 14.00:00:00

</div>

<div>

## <a name="to-modify-the-log-cleanup-time-of-day"></a><span data-ttu-id="ce80d-155">So ändern Sie die Zeit für die Protokoll Bereinigung</span><span class="sxs-lookup"><span data-stu-id="ce80d-155">To modify the log cleanup time of day</span></span>

  - <span data-ttu-id="ce80d-156">Mit diesem Befehl wird die Protokoll Bereinigungszeit für die Website "Redmond" auf 3:00 Uhr festgelegt.</span><span class="sxs-lookup"><span data-stu-id="ce80d-156">This command sets the log cleanup time for the Redmond site to 3:00 AM.</span></span>
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupTimeOfDay 03:00

</div>

<span data-ttu-id="ce80d-157">Ausführliche Informationen finden Sie im Hilfethema zum Cmdlet " [Satz-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsDeviceUpdateConfiguration) ".</span><span class="sxs-lookup"><span data-stu-id="ce80d-157">For details, see the Help topic for the [Set-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsDeviceUpdateConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

