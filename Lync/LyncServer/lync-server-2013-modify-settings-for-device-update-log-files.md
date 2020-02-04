---
title: 'Lync Server 2013: Ändern der Einstellungen für Geräte Aktualisierungsprotokolldateien'
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
ms.openlocfilehash: 88d75086f0532205c2897f7e86d49f50072aaa89
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756929"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-settings-for-device-update-log-files-in-lync-server-2013"></a>Ändern der Einstellungen für Geräte Aktualisierungsprotokolldateien in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Mithilfe der lync Server-Systemsteuerung oder der lync Server-Verwaltungsshell können Sie die Einstellungen für die Protokollierung von Geräte Aktualisierungsinformationen in Ihrer Organisation ändern. In der folgenden Tabelle wird aufgezeigt, welche Einstellungen änderbar sind und welches Tool (e) Sie verwenden, um die Einstellungen zu ändern.

Protokolleinstellungen können global oder pro Website geändert und angewendet werden.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Zu ändern</th>
<th>Verwendung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Die maximale Größe (in Bytes) für eine Protokolldatei</p></td>
<td><p>Lync Server-Systemsteuerung</p>
<p>oder</p>
<p>Lync Server-Verwaltungsshell</p></td>
</tr>
<tr class="even">
<td><p>Die maximale Menge an Informationen (in Bytes), die im Cache gespeichert werden können</p></td>
<td><p>Lync Server-Systemsteuerung</p>
<p>oder</p>
<p>Lync Server-Verwaltungsshell</p></td>
</tr>
<tr class="odd">
<td><p>Wie oft (in Minuten), um zwischengespeicherte Informationen in die Protokolldatei zu schreiben</p></td>
<td><p>Lync Server-Systemsteuerung</p>
<p>oder</p>
<p>Lync Server-Verwaltungsshell</p></td>
</tr>
<tr class="even">
<td><p>Wie lange (in Tagen) Protokolldateien aufbewahrt werden</p></td>
<td><p>Lync Server-Systemsteuerung</p>
<p>oder</p>
<p>Lync Server-Verwaltungsshell</p></td>
</tr>
<tr class="odd">
<td><p>Zeitpunkt (Tageszeit) zum Überprüfen auf abgelaufene Dateien, die gelöscht werden sollen</p></td>
<td><p>Lync Server-Verwaltungsshell</p></td>
</tr>
<tr class="even">
<td><p>Welche Protokolldatei Erweiterungen zugelassen werden sollen</p></td>
<td><p>Lync Server-Verwaltungsshell</p></td>
</tr>
<tr class="odd">
<td><p>Welche Protokolldatei Typen beibehalten werden sollen</p></td>
<td><p>Lync Server-Verwaltungsshell</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-change-logging-settings-by-using-lync-server-control-panel"></a>So ändern Sie die Protokollierungseinstellungen mithilfe der lync Server-Systemsteuerung

1.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Klicken Sie in der linken Navigationsleiste auf **Clients**, und klicken Sie dann auf **geräteprotokoll Konfiguration**.

3.  Doppelklicken Sie auf der Seite **Device Log-Konfiguration** auf die Konfiguration, die Sie ändern möchten.

4.  Ändern Sie im Dialogfeld **Protokolleinstellung bearbeiten** eine der folgenden Einstellungen:
    
      - **Maximale Dateigröße (Bytes)**   gibt die maximale Größe an, die eine Protokolldatei erhalten kann, bevor Sie bereinigt wird. Der Standardwert ist 1.024.000 Bytes (1 MB).
    
      - **Maximale Cachegröße (Bytes)**   gibt die maximale Informationsmenge (in Byte) an, die im Protokolldatei Cache gespeichert werden kann, bevor dieser Cache gelöscht werden muss und die Daten in eine Protokolldatei geschrieben werden. Der Standardwert ist 512.000 Bytes (0,5 MB).
    
      - **Die Anzahl der Minuten zum Leeren des Caches (1-60)**   gibt an, wie häufig im Protokolldatei Cache gespeicherte Informationen in die eigentliche Protokolldatei geschrieben werden. Nachdem die Daten protokolliert wurden, wird der Cache gelöscht. Der Standardwert ist fünf Minuten.
    
      - **Anzahl der Tage für die Beibehaltung von Protokolldateien (1-365)**   gibt an, wie viele Tage die Protokolldateien aufbewahrt werden, bevor Sie gelöscht werden. Der Standardwert ist 10 Tage.

5.  Klicken Sie auf **Commit ausführen**.

</div>

<div>

## <a name="changing-logging-settings-by-using-windows-powershell-cmdlets"></a>Ändern der Protokollierungseinstellungen mithilfe von Windows PowerShell-Cmdlets

Einstellungen für die Geräteupdate Protokolldatei können mithilfe von Windows PowerShell und dem Cmdlet " **Satz-CsDeviceUpdateConfiguration** " geändert werden. Dieses Cmdlet kann entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden.

<div>


> [!NOTE]  
> Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Remote-PowerShell" unter.



</div>

Die folgenden Beispiele zeigen eine Reihe von Möglichkeiten, wie Sie mit " **CsDeviceUpdateConfiguration** " Einstellungen ändern können.

<div>

## <a name="to-modify-the-maximum-log-file-size-and-the-log-cleanup-interval"></a>So ändern Sie die maximale Protokolldateigröße und das Protokoll Bereinigungsintervall

  - Mit dem folgenden Befehl werden die Einstellungen für das Geräteupdate Protokoll geändert, die auf die Redmond-Website angewendet wurden. In diesem Beispiel ist die maximale Protokolldateigröße auf 204800 Bytes und das Protokoll Bereinigungsintervall auf 14 Tage eingestellt.
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -MaxLogFileSize 204800 -LogCleanUpInterval 14.00:00:00

</div>

<div>

## <a name="to-modify-the-log-cleanup-time-of-day"></a>So ändern Sie die Zeit für die Protokoll Bereinigung

  - Mit diesem Befehl wird die Protokoll Bereinigungszeit für die Website "Redmond" auf 3:00 Uhr festgelegt.
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupTimeOfDay 03:00

</div>

Ausführliche Informationen finden Sie im Hilfethema zum Cmdlet " [Satz-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsDeviceUpdateConfiguration) ".

</div>

</div>

<span> </span>

</div>

</div>

</div>

