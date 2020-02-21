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

# <a name="delete-device-update-log-files-in-lync-server-2013"></a>Löschen von Protokolldateien für Geräte Updates in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-23_

Der Geräte Update-Webdienst behält eine umfangreiche Sammlung von Protokolldateien bei. Diese Auflistung umfasst sowohl vom Dienst selbst durchgeführte Überwachungsprotokolle als auch von Clientgeräten hochgeladene Protokolldateien. Um zu verhindern, dass sich der Server mit den Protokollen des Geräte Update-Webdiensts füllt, sollten Sie ihn wahrscheinlich von Protokolldateien löschen, die für eine bestimmte Anzahl von Tagen vorhanden waren. Legen Sie diese Anzahl von Tagen basierend auf der Aktualisierungsaktivität und der Anzahl der Clientgeräte in Ihrer Organisation sowie mithilfe von lync Server-Systemsteuerung oder lync Server-Verwaltungsshell fest.

<div>

## <a name="to-clear-the-device-update-log-by-using-lync-server-control-panel"></a>So löschen Sie das Geräte Aktualisierungsprotokoll mithilfe von lync Server-Systemsteuerung

1.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Klicken Sie in der linken Navigationsleiste auf **Clients** und dann auf **Geräteprotokollkonfiguration**.

3.  Doppelklicken Sie auf der Seite **Geräteprotokollkonfiguration** auf die Konfiguration, die Sie ändern möchten.

4.  Stellen Sie im Dialogfeld **Protokolleinstellung bearbeiten** in der **Anzahl der Tage, die Protokolldateien aufbewahrt werden sollen (1-365)** eine Anzahl von Tagen ein.

5.  Klicken Sie auf **Commit ausführen**. Alle Dateien, die sich auf dem Server für mehr als die angegebene Anzahl von Tagen befinden, werden gelöscht. Diese Einstellung wird auf diese Konfiguration angewendet, bis Sie Sie ändern.

</div>

<div>

## <a name="clearing-the-device-update-log-by-using-the-windows-powershell-cmdlets"></a>Löschen des Geräte Aktualisierungsprotokolls mithilfe der Windows PowerShell-Cmdlets

Sie können Geräte Aktualisierungsprotokolle mit Windows PowerShell und dem Cmdlet **Clear-CsDeviceUpdateLog** löschen. Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.

<div>


> [!NOTE]  
> Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>mithilfe von Remote-PowerShell" unter.



</div>

<div>

## <a name="to-clear-device-update-logs-on-one-server"></a>So löschen Sie Geräte Aktualisierungsprotokolle auf einem Server

  - Mit dem folgenden Befehl wird das Geräte Aktualisierungsprotokoll auf dem Webserver ATL-CS-001.litwareinc.com gelöscht. Alle Protokolleinträge, die älter als 10 Tage sind (der durch den DaysBack-Parameter angegebene Wert), werden aus dem Protokoll entfernt.
    
        Clear-CsDeviceUpdateLog -Identity "service:WebServer:atl-cs-001.litwareinc.com" -DaysBack 10

</div>

<div>

## <a name="to-clear-all-device-update-logs"></a>So löschen Sie alle Geräte Aktualisierungsprotokolle

  - Mit diesem Befehl werden veraltete Einträge aus allen derzeit in Ihrer Organisation verwendeten Geräte Aktualisierungs Protokollen entfernt (in diesem Beispieleinträge, die älter als 10 Tage sind).
    
        Get-CsService -WebServer | Foreach-Object {Clear-CsDeviceUpdateLog -Identity $_.Identity -DaysBack 10}

</div>

Ausführliche Informationen finden Sie im Hilfethema zum Cmdlet [Clear-CsDeviceUpdateLog](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateLog) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

