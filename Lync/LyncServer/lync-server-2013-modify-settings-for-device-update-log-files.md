---
title: Ändern von Protokolldateieinstellungen für die Geräteaktualisierung
TOCTitle: Ändern von Protokolldateieinstellungen für die Geräteaktualisierung
ms:assetid: 9b57f126-1853-43b3-bbd4-06401e6498bd
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg182554(v=OCS.15)
ms:contentKeyID: 49294878
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ändern von Protokolldateieinstellungen für die Geräteaktualisierung

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Sie können die Einstellungen für die Protokollierung von Geräteaktualisierungsinformationen in Ihrer Organisation mithilfe der Lync Server-Systemsteuerung oder der Lync Server-Verwaltungsshell ändern. In der folgenden Tabelle sind die Einstellungen, die geändert werden können und das bzw. die dafür zu verwendenden Tool(s) aufgeführt.

Protokolleinstellungen können global oder auf Standortebene geändert und angewendet werden.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Zu ändernde Einstellung</th>
<th>Verwendung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Die maximale Größe (in Bytes) einer Protokolldatei</p></td>
<td><p>Lync Server-Systemsteuerung</p>
<p>- oder -</p>
<p>Lync Server-Verwaltungsshell</p></td>
</tr>
<tr class="even">
<td><p>Maximale Informationsmenge (in Byte), die im Cache gespeichert werden kann</p></td>
<td><p>Lync Server-Systemsteuerung</p>
<p>- oder -</p>
<p>Lync Server-Verwaltungsshell</p></td>
</tr>
<tr class="odd">
<td><p>Häufigkeit (in Minuten), mit der zwischengspeicherte Informationen in die Protokolldatei geschrieben werden</p></td>
<td><p>Lync Server-Systemsteuerung</p>
<p>- oder -</p>
<p>Lync Server-Verwaltungsshell</p></td>
</tr>
<tr class="even">
<td><p>Zeitraum (in Tagen), für den Protokolldateien gespeichert werden</p></td>
<td><p>Lync Server-Systemsteuerung</p>
<p>- oder -</p>
<p>Lync Server-Verwaltungsshell</p></td>
</tr>
<tr class="odd">
<td><p>Wann (Uhrzeit) eine Überprüfung auf zu löschende Dateien stattfindet</p></td>
<td><p>Lync Server-Verwaltungsshell</p></td>
</tr>
<tr class="even">
<td><p>Zulässige Protokolldateierweiterungen</p></td>
<td><p>Lync Server-Verwaltungsshell</p></td>
</tr>
<tr class="odd">
<td><p>Aufzubewahrende Protokolldateitypen</p></td>
<td><p>Lync Server-Verwaltungsshell</p></td>
</tr>
</tbody>
</table>


## So ändern Sie die Einstellungen für die Protokollierung mithilfe der Lync Server-Systemsteuerung

1.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Klicken Sie in der linken Navigationsleiste auf **Clients** und dann auf **Geräteprotokollkonfiguration**.

3.  Doppelklicken Sie auf der Seite **Geräteprotokollkonfiguration** auf die Konfiguration, die Sie ändern möchten.

4.  Ändern Sie im Dialogfeld **Protokolleinstellungen bearbeiten** eine der folgenden Einstellungen:
    
      - **Maximale Dateigröße (Byte)**   Legt die maximale Größe einer Protokolldatei fest, bevor sie gelöscht wird. Der Standardwert beträgt 1.024.000 (1 MB).
    
      - **Maximale Cachegröße (Byte)**   Gibt die maximale Informationsmenge (in Byte) an, die im Protokolldateicache gespeichert werden kann, bevor der Cache geleert und die Daten in eine Protokolldatei geschrieben werden müssen. Der Standardwert beträgt 512.000 (0,5 MB).
    
      - **Minuten bis zur Cacheleerung (1-60)**   Gibt an, wie häufig die im Protokolldateicache gespeicherten Informationen in die eigentliche Protokolldatei geschrieben werden. Nachdem die Daten protokolliert wurden, wird der Cache geleert. Der Standardwert beträgt fünf Minuten.
    
      - **Speicherung von Protokolldateien in Tagen (1-365)**   Gibt die Anzahl an Tagen an, für die Protokolldateien gespeichert werden, bevor sie gelöscht werden. Der Standardwert beträgt 10 Tage.

5.  Klicken Sie auf **Commit**.

## Ändern der Einstellungen für die Protokollierung mithilfe von Windows PowerShell-Cmdlets

Einstellungen für Protokolldateien der Geräteaktualisierung können Sie mithilfe von Windows PowerShell und dem Cmdlet **Set-CsDeviceUpdateConfiguration** löschen. Dieses Cmdlet kann entweder über die Verwaltungsshell für Lync Server 2013 oder in einer Remotesitzung von Windows PowerShell ausgeführt werden.


> [!NOTE]
> Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server&nbsp;Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.



Die folgenden Beispiele zeigen einige Methoden der Verwendung von **Set-CsDeviceUpdateConfiguration** zum Ändern von Einstellungen.

## So ändern Sie die maximale Größe der Protokolldatei und das Protokollleerungsintervall

  - Mit dem folgenden Befehl werden die Einstellungen für die Geräteaktualisierungsprotokollierung für den Standort Redmond geändert. In diesem Beispiel wird die maximale Größe der Protokolldatei auf 2.048.000 Byte und das Protokollleerungsintervall auf 14 Tage festgelegt.
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -MaxLogFileSize 204800 -LogCleanUpInterval 14.00:00:00

## So ändern Sie die Uhrzeit für die Protokollleerung

  - Mit diesem Befehl wird die Uhrzeit der Protokollleerung für den Standort Redmond auf 3.00 Uhr festgelegt.
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupTimeOfDay 03:00

Einzelheiten dazu finden Sie im Hilfethema zum Cmdlet [Set-CsDeviceUpdateConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsDeviceUpdateConfiguration).

