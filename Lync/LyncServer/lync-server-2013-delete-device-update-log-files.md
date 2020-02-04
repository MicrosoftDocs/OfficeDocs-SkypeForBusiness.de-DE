---
title: 'Lync Server 2013: Löschen von Geräte Update Protokolldateien'
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
ms.openlocfilehash: c684978445f727dc155fade59654ff6e2866f084
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734205"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-device-update-log-files-in-lync-server-2013"></a><span data-ttu-id="0000d-102">Löschen von Geräte Aktualisierungsprotokolldateien in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0000d-102">Delete Device Update log files in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0000d-103">_**Letztes Änderungsdatum des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="0000d-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="0000d-104">Der Geräte Update-Webdienst speichert eine umfangreiche Sammlung von Protokolldateien.</span><span class="sxs-lookup"><span data-stu-id="0000d-104">The Device Update Web service keeps an extensive collection of log files.</span></span> <span data-ttu-id="0000d-105">Diese Sammlung umfasst sowohl Überwachungsprotokolle, die vom Dienst selbst durchgeführt werden, als auch Protokolldateien, die von Clientgeräten hochgeladen wurden.</span><span class="sxs-lookup"><span data-stu-id="0000d-105">This collection includes both audit logs conducted by the service itself and log files uploaded from client devices.</span></span> <span data-ttu-id="0000d-106">Um zu verhindern, dass der Server mit den Device Update-Webdienstprotokollen gefüllt wird, möchten Sie ihn wahrscheinlich von Protokolldateien löschen, die für eine bestimmte Anzahl von Tagen in Umlauf sind.</span><span class="sxs-lookup"><span data-stu-id="0000d-106">To prevent the server from filling up with Device Update Web service logs, you’ll probably want to clear it of log files that have been around for a certain number of days.</span></span> <span data-ttu-id="0000d-107">Sie können diese Anzahl von Tagen basierend auf den Aktualisierungsaktivitäten und der Anzahl der Clientgeräte in Ihrer Organisation und mithilfe der lync Server-Systemsteuerung oder der lync Server-Verwaltungsshell festlegen.</span><span class="sxs-lookup"><span data-stu-id="0000d-107">Set this number of days based on update activity and the number of client devices in your organization, and by using Lync Server Control Panel or Lync Server Management Shell.</span></span>

<div>

## <a name="to-clear-the-device-update-log-by-using-lync-server-control-panel"></a><span data-ttu-id="0000d-108">So löschen Sie das Geräte Aktualisierungsprotokoll mithilfe der lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="0000d-108">To clear the device update log by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="0000d-109">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="0000d-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0000d-110">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0000d-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="0000d-111">Klicken Sie in der linken Navigationsleiste auf **Clients**, und klicken Sie dann auf **geräteprotokoll Konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="0000d-111">In the left navigation bar, click **Clients**, and then click **Device Log Configuration**.</span></span>

3.  <span data-ttu-id="0000d-112">Doppelklicken Sie auf der Seite **Device Log-Konfiguration** auf die Konfiguration, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="0000d-112">On the **Device Log Configuration** page, double-click the configuration that you want to change.</span></span>

4.  <span data-ttu-id="0000d-113">Legen Sie im Dialogfeld **Protokolleinstellung bearbeiten** in **Anzahl von Tagen, um Protokolldateien zu speichern (1-365)** eine Anzahl von Tagen fest.</span><span class="sxs-lookup"><span data-stu-id="0000d-113">In the **Edit Log Setting** dialog box, in **Number of days to keep log files (1-365)**, specifiy a number of days.</span></span>

5.  <span data-ttu-id="0000d-114">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="0000d-114">Click **Commit**.</span></span> <span data-ttu-id="0000d-115">Alle Dateien, die mehr als die angegebene Anzahl von Tagen auf dem Server vorhanden sind, werden gelöscht.</span><span class="sxs-lookup"><span data-stu-id="0000d-115">All files that have been on the server for more than the specified number of day are deleted.</span></span> <span data-ttu-id="0000d-116">Diese Einstellung wird auf diese Konfiguration angewendet, bis Sie Sie ändern.</span><span class="sxs-lookup"><span data-stu-id="0000d-116">This setting will apply to this configuration until you change it.</span></span>

</div>

<div>

## <a name="clearing-the-device-update-log-by-using-the-windows-powershell-cmdlets"></a><span data-ttu-id="0000d-117">Löschen des Geräte Aktualisierungsprotokolls mithilfe der Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="0000d-117">Clearing the Device Update Log by Using the Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="0000d-118">Sie können Geräte Aktualisierungsprotokolle mithilfe von Windows PowerShell und dem Cmdlet " **Clear-CsDeviceUpdateLog** " löschen.</span><span class="sxs-lookup"><span data-stu-id="0000d-118">You can clear device update logs by using Windows PowerShell and the **Clear-CsDeviceUpdateLog** cmdlet.</span></span> <span data-ttu-id="0000d-119">Dieses Cmdlet kann entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="0000d-119">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0000d-120">Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="0000d-120">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-clear-device-update-logs-on-one-server"></a><span data-ttu-id="0000d-121">So löschen Sie Geräte Aktualisierungsprotokolle auf einem Server</span><span class="sxs-lookup"><span data-stu-id="0000d-121">To clear device update logs on one server</span></span>

  - <span data-ttu-id="0000d-122">Mit dem folgenden Befehl wird das Geräte Aktualisierungsprotokoll auf dem Webserver ATL-CS-001.litwareinc.com gelöscht.</span><span class="sxs-lookup"><span data-stu-id="0000d-122">The following command clears the device update log on the Web server atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="0000d-123">Alle Protokolleinträge, die mehr als 10 Tage alt sind (der durch den DaysBack-Parameter angegebene Wert), werden aus dem Protokoll entfernt.</span><span class="sxs-lookup"><span data-stu-id="0000d-123">All log entries more than 10 days old (the value specified by the DaysBack parameter) will be removed from the log.</span></span>
    
        Clear-CsDeviceUpdateLog -Identity "service:WebServer:atl-cs-001.litwareinc.com" -DaysBack 10

</div>

<div>

## <a name="to-clear-all-device-update-logs"></a><span data-ttu-id="0000d-124">So löschen Sie alle Geräte Aktualisierungsprotokolle</span><span class="sxs-lookup"><span data-stu-id="0000d-124">To clear all device update logs</span></span>

  - <span data-ttu-id="0000d-125">Dieser Befehl entfernt veraltete Einträge (in diesem Beispieleinträge, die mehr als 10 Tage alt sind) aus allen Geräte Aktualisierungs Protokollen, die derzeit in Ihrer Organisation verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0000d-125">This command removes outdated entries (in this example, entries more than 10 days old) from all the device update logs currently in use in your organization.</span></span>
    
        Get-CsService -WebServer | Foreach-Object {Clear-CsDeviceUpdateLog -Identity $_.Identity -DaysBack 10}

</div>

<span data-ttu-id="0000d-126">Ausführliche Informationen finden Sie im Hilfethema zum Cmdlet " [Clear-CsDeviceUpdateLog](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateLog) ".</span><span class="sxs-lookup"><span data-stu-id="0000d-126">For details, see the Help topic for the [Clear-CsDeviceUpdateLog](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateLog) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

