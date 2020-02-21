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
ms.openlocfilehash: 112f9e5a90e0b7b73acc40c6c7ec9d68b256d45d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184908"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="modify-settings-for-device-update-log-files-in-lync-server-2013"></a>Ändern der Einstellungen für Geräte Aktualisierungsprotokolldateien in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-23_

Sie können mithilfe von lync Server-Systemsteuerung oder lync Server-Verwaltungsshell Einstellungen für die Protokollierung von Geräte Aktualisierungsinformationen in Ihrer Organisation ändern. Die folgende Tabelle zeigt, welche Einstellungen geändert werden können und welche Tools Sie zum Ändern der Einstellungen verwenden.

Protokolleinstellungen können global oder pro Standort geändert und angewendet werden.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Ändern</th>
<th>Verwendung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Die maximale Größe (in Byte) für eine Protokolldatei</p></td>
<td><p>Lync Server-Systemsteuerung</p>
<p>- oder -</p>
<p>Lync Server-Verwaltungsshell</p></td>
</tr>
<tr class="even">
<td><p>Die maximale Menge an Informationen (in Bytes), die im Cache gespeichert werden können.</p></td>
<td><p>Lync Server-Systemsteuerung</p>
<p>- oder -</p>
<p>Lync Server-Verwaltungsshell</p></td>
</tr>
<tr class="odd">
<td><p>Wie oft (in Minuten) zwischengespeicherte Informationen in die Protokolldatei geschrieben werden sollen</p></td>
<td><p>Lync Server-Systemsteuerung</p>
<p>- oder -</p>
<p>Lync Server-Verwaltungsshell</p></td>
</tr>
<tr class="even">
<td><p>Wie lange (in Tagen), um Protokolldateien beizubehalten</p></td>
<td><p>Lync Server-Systemsteuerung</p>
<p>- oder -</p>
<p>Lync Server-Verwaltungsshell</p></td>
</tr>
<tr class="odd">
<td><p>Wann (Tageszeit) zum Überprüfen auf abgelaufene Dateien, die gelöscht werden sollten</p></td>
<td><p>Lync Server-Verwaltungsshell</p></td>
</tr>
<tr class="even">
<td><p>Welche Protokolldatei Erweiterungen zugelassen werden sollen</p></td>
<td><p>Lync Server-Verwaltungsshell</p></td>
</tr>
<tr class="odd">
<td><p>Welche Protokolldatei Typen aufbewahrt werden sollen</p></td>
<td><p>Lync Server-Verwaltungsshell</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-change-logging-settings-by-using-lync-server-control-panel"></a>So ändern Sie die Protokollierungseinstellungen mithilfe von lync Server-Systemsteuerung

1.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Klicken Sie in der linken Navigationsleiste auf **Clients** und dann auf **Geräteprotokollkonfiguration**.

3.  Doppelklicken Sie auf der Seite **Geräteprotokollkonfiguration** auf die Konfiguration, die Sie ändern möchten.

4.  Ändern Sie im Dialogfeld **Protokolleinstellung bearbeiten** die folgenden Einstellungen:
    
      - **Maximale Dateigröße (Bytes)**   gibt die maximale Größe an, mit der eine Protokolldatei gelöscht werden kann, bevor Sie bereinigt wird. Der Standardwert beträgt 1.024.000 (1 MB).
    
      - **Maximale Cachegröße (Bytes)**   gibt die maximale Menge an Informationen (in Byte) an, die im Protokolldatei Cache aufbewahrt werden können, bevor dieser Cache gelöscht werden muss und die Daten in eine Protokolldatei geschrieben werden. Der Standardwert beträgt 512.000 (0,5 MB).
    
      - **Anzahl der Minuten für das Leeren des Caches (1-60)**   gibt an, wie oft im Protokolldatei Cache gespeicherte Informationen in die tatsächliche Protokolldatei geschrieben werden. Nachdem die Daten protokolliert wurden, wird der Cache geleert. Der Standardwert beträgt fünf Minuten.
    
      - **Anzahl der Tage für die Aufbewahrung von Protokolldateien (1-365)**   gibt an, wie viele Tage die Protokolldateien aufbewahrt werden, bevor Sie gelöscht werden. Der Standardwert beträgt 10 Tage.

5.  Klicken Sie auf **Commit**.

</div>

<div>

## <a name="changing-logging-settings-by-using-windows-powershell-cmdlets"></a>Ändern der Protokollierungseinstellungen mithilfe von Windows PowerShell-Cmdlets

Einstellungen für die Geräteupdate Protokolldatei können mithilfe von Windows PowerShell und dem Cmdlet "Cmdlet **festlegen** " geändert werden. Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.

<div>


> [!NOTE]  
> Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>mithilfe von Remote-PowerShell" unter.



</div>

Die folgenden Beispiele zeigen eine Reihe von Möglichkeiten, mit denen Sie die Einstellungen mithilfe von " **CsDeviceUpdateConfiguration** " ändern können.

<div>

## <a name="to-modify-the-maximum-log-file-size-and-the-log-cleanup-interval"></a>So ändern Sie die maximale Protokolldateigröße und das Protokoll Bereinigungsintervall

  - Mit dem folgenden Befehl werden die Einstellungen für das Geräteupdate Protokoll geändert, die auf den Standort "Redmond" angewendet wurden. In diesem Beispiel wird die maximale Größe der Protokolldatei auf 204800 Byte festgelegt, und das Intervall für die Protokoll Bereinigung wird auf 14 Tage festgelegt.
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -MaxLogFileSize 204800 -LogCleanUpInterval 14.00:00:00

</div>

<div>

## <a name="to-modify-the-log-cleanup-time-of-day"></a>So ändern Sie die Zeit des Protokoll Bereinigungs Tags

  - Mit diesem Befehl wird die Zeit für die Protokoll Bereinigung für den Standort "Redmond" auf 3:00 Uhr festgelegt.
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupTimeOfDay 03:00

</div>

Ausführliche Informationen finden Sie im Hilfethema zum Cmdlet " [CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsDeviceUpdateConfiguration) ".

</div>

</div>

<span> </span>

</div>

</div>

</div>

