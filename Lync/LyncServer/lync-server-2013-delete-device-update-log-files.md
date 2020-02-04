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

# <a name="delete-device-update-log-files-in-lync-server-2013"></a>Löschen von Geräte Aktualisierungsprotokolldateien in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Der Geräte Update-Webdienst speichert eine umfangreiche Sammlung von Protokolldateien. Diese Sammlung umfasst sowohl Überwachungsprotokolle, die vom Dienst selbst durchgeführt werden, als auch Protokolldateien, die von Clientgeräten hochgeladen wurden. Um zu verhindern, dass der Server mit den Device Update-Webdienstprotokollen gefüllt wird, möchten Sie ihn wahrscheinlich von Protokolldateien löschen, die für eine bestimmte Anzahl von Tagen in Umlauf sind. Sie können diese Anzahl von Tagen basierend auf den Aktualisierungsaktivitäten und der Anzahl der Clientgeräte in Ihrer Organisation und mithilfe der lync Server-Systemsteuerung oder der lync Server-Verwaltungsshell festlegen.

<div>

## <a name="to-clear-the-device-update-log-by-using-lync-server-control-panel"></a>So löschen Sie das Geräte Aktualisierungsprotokoll mithilfe der lync Server-Systemsteuerung

1.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Klicken Sie in der linken Navigationsleiste auf **Clients**, und klicken Sie dann auf **geräteprotokoll Konfiguration**.

3.  Doppelklicken Sie auf der Seite **Device Log-Konfiguration** auf die Konfiguration, die Sie ändern möchten.

4.  Legen Sie im Dialogfeld **Protokolleinstellung bearbeiten** in **Anzahl von Tagen, um Protokolldateien zu speichern (1-365)** eine Anzahl von Tagen fest.

5.  Klicken Sie auf **Commit ausführen**. Alle Dateien, die mehr als die angegebene Anzahl von Tagen auf dem Server vorhanden sind, werden gelöscht. Diese Einstellung wird auf diese Konfiguration angewendet, bis Sie Sie ändern.

</div>

<div>

## <a name="clearing-the-device-update-log-by-using-the-windows-powershell-cmdlets"></a>Löschen des Geräte Aktualisierungsprotokolls mithilfe der Windows PowerShell-Cmdlets

Sie können Geräte Aktualisierungsprotokolle mithilfe von Windows PowerShell und dem Cmdlet " **Clear-CsDeviceUpdateLog** " löschen. Dieses Cmdlet kann entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden.

<div>


> [!NOTE]  
> Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Remote-PowerShell" unter.



</div>

<div>

## <a name="to-clear-device-update-logs-on-one-server"></a>So löschen Sie Geräte Aktualisierungsprotokolle auf einem Server

  - Mit dem folgenden Befehl wird das Geräte Aktualisierungsprotokoll auf dem Webserver ATL-CS-001.litwareinc.com gelöscht. Alle Protokolleinträge, die mehr als 10 Tage alt sind (der durch den DaysBack-Parameter angegebene Wert), werden aus dem Protokoll entfernt.
    
        Clear-CsDeviceUpdateLog -Identity "service:WebServer:atl-cs-001.litwareinc.com" -DaysBack 10

</div>

<div>

## <a name="to-clear-all-device-update-logs"></a>So löschen Sie alle Geräte Aktualisierungsprotokolle

  - Dieser Befehl entfernt veraltete Einträge (in diesem Beispieleinträge, die mehr als 10 Tage alt sind) aus allen Geräte Aktualisierungs Protokollen, die derzeit in Ihrer Organisation verwendet werden.
    
        Get-CsService -WebServer | Foreach-Object {Clear-CsDeviceUpdateLog -Identity $_.Identity -DaysBack 10}

</div>

Ausführliche Informationen finden Sie im Hilfethema zum Cmdlet " [Clear-CsDeviceUpdateLog](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateLog) ".

</div>

</div>

<span> </span>

</div>

</div>

</div>

