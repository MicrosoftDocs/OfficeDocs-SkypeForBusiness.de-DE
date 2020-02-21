---
title: 'Lync Server 2013: Löschen von Protokolldateien für Geräte Updates'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete Device Update log files
ms:assetid: 58d4097f-5bbf-4824-a04d-2a6555cd93c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994039(v=OCS.15)
ms:contentKeyID: 51803949
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 685b3e34c0f2bd5392f71899564d0738e814b616
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202591"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-device-update-log-files-in-lync-server-2013"></a><span data-ttu-id="e84ad-102">Löschen von Protokolldateien für Geräte Updates in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e84ad-102">Delete Device Update log files in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e84ad-103">_**Letztes Änderungsstand des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="e84ad-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="e84ad-104">Der Geräte Update-Webdienst behält eine umfangreiche Sammlung von Protokolldateien bei.</span><span class="sxs-lookup"><span data-stu-id="e84ad-104">The Device Update Web service keeps an extensive collection of log files.</span></span> <span data-ttu-id="e84ad-105">Diese Auflistung umfasst sowohl vom Dienst selbst durchgeführte Überwachungsprotokolle als auch von Clientgeräten hochgeladene Protokolldateien.</span><span class="sxs-lookup"><span data-stu-id="e84ad-105">This collection includes both audit logs conducted by the service itself and log files uploaded from client devices.</span></span> <span data-ttu-id="e84ad-106">Um zu verhindern, dass sich der Server mit den Protokollen des Geräte Update-Webdiensts füllt, sollten Sie ihn wahrscheinlich von Protokolldateien löschen, die für eine bestimmte Anzahl von Tagen vorhanden waren.</span><span class="sxs-lookup"><span data-stu-id="e84ad-106">To prevent the server from filling up with Device Update Web service logs, you’ll probably want to clear it of log files that have been around for a certain number of days.</span></span> <span data-ttu-id="e84ad-107">Legen Sie diese Anzahl von Tagen basierend auf der Aktualisierungsaktivität und der Anzahl der Clientgeräte in Ihrer Organisation sowie mithilfe von lync Server-Systemsteuerung oder lync Server-Verwaltungsshell fest.</span><span class="sxs-lookup"><span data-stu-id="e84ad-107">Set this number of days based on update activity and the number of client devices in your organization, and by using Lync Server Control Panel or Lync Server Management Shell.</span></span>

<div>

## <a name="to-clear-the-device-update-log-by-using-lync-server-control-panel"></a><span data-ttu-id="e84ad-108">So löschen Sie das Geräte Aktualisierungsprotokoll mithilfe von lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="e84ad-108">To clear the device update log by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="e84ad-109">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="e84ad-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e84ad-110">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e84ad-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="e84ad-111">Klicken Sie in der linken Navigationsleiste auf **Clients** und dann auf **Geräteprotokollkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="e84ad-111">In the left navigation bar, click **Clients**, and then click **Device Log Configuration**.</span></span>

3.  <span data-ttu-id="e84ad-112">Doppelklicken Sie auf der Seite **Geräteprotokollkonfiguration** auf die Konfiguration, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="e84ad-112">On the **Device Log Configuration** page, double-click the configuration that you want to change.</span></span>

4.  <span data-ttu-id="e84ad-113">Stellen Sie im Dialogfeld **Protokolleinstellung bearbeiten** in der **Anzahl der Tage, die Protokolldateien aufbewahrt werden sollen (1-365)** eine Anzahl von Tagen ein.</span><span class="sxs-lookup"><span data-stu-id="e84ad-113">In the **Edit Log Setting** dialog box, in **Number of days to keep log files (1-365)**, specifiy a number of days.</span></span>

5.  <span data-ttu-id="e84ad-114">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="e84ad-114">Click **Commit**.</span></span> <span data-ttu-id="e84ad-115">Alle Dateien, die sich auf dem Server für mehr als die angegebene Anzahl von Tagen befinden, werden gelöscht.</span><span class="sxs-lookup"><span data-stu-id="e84ad-115">All files that have been on the server for more than the specified number of day are deleted.</span></span> <span data-ttu-id="e84ad-116">Diese Einstellung wird auf diese Konfiguration angewendet, bis Sie Sie ändern.</span><span class="sxs-lookup"><span data-stu-id="e84ad-116">This setting will apply to this configuration until you change it.</span></span>

</div>

<div>

## <a name="clearing-the-device-update-log-by-using-the-windows-powershell-cmdlets"></a><span data-ttu-id="e84ad-117">Löschen des Geräte Aktualisierungsprotokolls mithilfe der Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="e84ad-117">Clearing the Device Update Log by Using the Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="e84ad-118">Sie können Geräte Aktualisierungsprotokolle mit Windows PowerShell und dem Cmdlet **Clear-CsDeviceUpdateLog** löschen.</span><span class="sxs-lookup"><span data-stu-id="e84ad-118">You can clear device update logs by using Windows PowerShell and the **Clear-CsDeviceUpdateLog** cmdlet.</span></span> <span data-ttu-id="e84ad-119">Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e84ad-119">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e84ad-120">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>mithilfe von Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="e84ad-120">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-clear-device-update-logs-on-one-server"></a><span data-ttu-id="e84ad-121">So löschen Sie Geräte Aktualisierungsprotokolle auf einem Server</span><span class="sxs-lookup"><span data-stu-id="e84ad-121">To clear device update logs on one server</span></span>

  - <span data-ttu-id="e84ad-122">Mit dem folgenden Befehl wird das Geräte Aktualisierungsprotokoll auf dem Webserver ATL-CS-001.litwareinc.com gelöscht.</span><span class="sxs-lookup"><span data-stu-id="e84ad-122">The following command clears the device update log on the Web server atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="e84ad-123">Alle Protokolleinträge, die älter als 10 Tage sind (der durch den DaysBack-Parameter angegebene Wert), werden aus dem Protokoll entfernt.</span><span class="sxs-lookup"><span data-stu-id="e84ad-123">All log entries more than 10 days old (the value specified by the DaysBack parameter) will be removed from the log.</span></span>
    
        Clear-CsDeviceUpdateLog -Identity "service:WebServer:atl-cs-001.litwareinc.com" -DaysBack 10

</div>

<div>

## <a name="to-clear-all-device-update-logs"></a><span data-ttu-id="e84ad-124">So löschen Sie alle Geräte Aktualisierungsprotokolle</span><span class="sxs-lookup"><span data-stu-id="e84ad-124">To clear all device update logs</span></span>

  - <span data-ttu-id="e84ad-125">Mit diesem Befehl werden veraltete Einträge aus allen derzeit in Ihrer Organisation verwendeten Geräte Aktualisierungs Protokollen entfernt (in diesem Beispieleinträge, die älter als 10 Tage sind).</span><span class="sxs-lookup"><span data-stu-id="e84ad-125">This command removes outdated entries (in this example, entries more than 10 days old) from all the device update logs currently in use in your organization.</span></span>
    
        Get-CsService -WebServer | Foreach-Object {Clear-CsDeviceUpdateLog -Identity $_.Identity -DaysBack 10}

</div>

<span data-ttu-id="e84ad-126">Ausführliche Informationen finden Sie im Hilfethema zum Cmdlet [Clear-CsDeviceUpdateLog](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateLog) .</span><span class="sxs-lookup"><span data-stu-id="e84ad-126">For details, see the Help topic for the [Clear-CsDeviceUpdateLog](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateLog) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

