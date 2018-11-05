---
title: Erstellen von Konfigurationseinstellungen für QoE (Quality of Experience)
TOCTitle: Erstellen von Konfigurationseinstellungen für QoE (Quality of Experience)
ms:assetid: 64f05569-07c7-4f76-a96b-ea4125a510d5
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg521006(v=OCS.15)
ms:contentKeyID: 49294218
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen von Konfigurationseinstellungen für QoE (Quality of Experience)

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

QoE-Metriken (Quality of Experience) verfolgen die Qualität von in Ihrer Organisation getätigten Audio- und Videoanrufen nach. Dazu gehören Aspekte wie die Anzahl der verloren gegangenen Netzwerkpakete, Hintergrundgeräusche und die Unterschiede bei Paketverzögerungen ("Jitter"). Diese Metriken werden in einer Datenbank getrennt von anderen Daten (z. B. den Kommunikationsdatensätzen) gespeichert, sodass QoE unabhängig von anderen Datenaufzeichnungen aktiviert und deaktiviert werden kann.

Bei der Installation von Microsoft Lync Server 2013 wird eine einzelne, globale Auflistung von QoE-Konfigurationseinstellungen erstellt. Administratoren haben auch die Möglichkeit, benutzerdefinierte Einstellungen auf Standortebene zu erstellen. Wenn diese standortspezifischen Einstellungen verwendet werden, haben Sie Vorrang vor den globalen Einstellungen. Beispiel: Wenn Sie für den Standort "Redmond" standortspezifische Einstellungen erstellen, wird QoE in Redmond gemäß diesen Einstellungen (anstelle der globalen) verwaltet.

QoE-Konfigurationseinstellungen können entweder mithilfe der Lync Server-Systemsteuerung oder mit dem [New-CsQoEConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsQoEConfiguration)-Cmdlet erstellt werden. Bei Verwendung der Lync Server-Systemsteuerung stehen Ihnen die folgenden Optionen zur Verfügung:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Einstellung in der Benutzeroberfläche</th>
<th>PowerShell-Parameter</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Name</p></td>
<td><p>Identity</p></td>
<td><p>Eindeutiger Bezeichner für die zu erstellenden Einstellungen. QoE-Konfigurationseinstellungen können nur auf der Standortebene erstellt werden.</p></td>
</tr>
<tr class="even">
<td><p>Überwachung der QoE-Daten aktivieren</p></td>
<td><p>EnableQoE</p></td>
<td><p>Gibt an, ob QoE-Datensätze erfasst und in der Überwachungsdatenbank gespeichert werden sollen.</p></td>
</tr>
<tr class="odd">
<td><p>Bereinigungsfunktion für QoE-Daten aktivieren</p></td>
<td><p>EnablePurging</p></td>
<td><p>Gibt an, ob Datensätze nach Ablauf des in der Eigenschaft <strong>QoE-Daten für maximal (Tage) aufbewahren</strong> festgelegten Zeitraums bereinigt werden sollen.</p></td>
</tr>
<tr class="even">
<td><p>QoE-Daten für maximal (Tage) aufbewahren</p></td>
<td><p>KeepQoEDataForDays</p></td>
<td><p>Zeitdauer in Tagen, die QoE-Daten gespeichert bleiben sollen, bevor sie aus der Datenbank bereinigt werden. Bei deaktivierter Bereinigung wird dieser Wert ignoriert.</p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> Das New-CsQoEConfiguration-Cmdlet verfügt über weitere Optionen, die in der Lync Server-Systemsteuerung nicht zur Verfügung stehen. Weitere Informationen dazu finden Sie im Hilfethema <A href="https://docs.microsoft.com/en-us/powershell/module/skype/New-CsQoEConfiguration">New-CsQoEConfiguration</A>.



## So erstellen Sie QoE-Konfigurationseinstellungen in der Lync Server-Systemsteuerung

1.  Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter [Delegieren von Setupberechtigungen in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **QoE-Daten**.

4.  Klicken Sie auf der Seite **QoE-Daten** auf **Neu**.

5.  Klicken Sie in **Standort auswählen** auf den Standort, auf den die Richtlinie angewendet werden soll, und klicken Sie dann auf **OK**.

6.  Führen Sie in **Neue QoE-Einstellung** die folgenden Aktionen aus:
    
      - Wählen Sie **Überwachung der QoE-Daten aktivieren** aus, um die Überwachung einzuschalten.
    
      - Wählen Sie **Bereinigungsfunktion für QoE-Daten aktivieren** aus, um die Bereinigung zu aktivieren.
    
      - Wählen Sie in **QoE-Daten für maximal (Tage) aufbewahren** aus, wie viele Tage QoE-Datensätze maximal aufbewahrt werden sollen.

7.  Klicken Sie auf **Commit**.

## So erstellen Sie QoE-Konfigurationseinstellungen mit den Windows PowerShell-Cmdlets

Sie können QoE-Konfigurationseinstellungen auch in der Windows PowerShell mit dem New-CsQoEConfiguration-Cmdlet erstellen. Dieses Cmdlet können Sie entweder von der Verwaltungsshell für Lync Server 2013 aus oder in einer Remotesitzung der Windows PowerShell ausführen. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## So erstellen Sie eine neue Auflistung von QoE-Konfigurationseinstellungen

  - Dieser Befehl erstellt eine neue Auflistung von QoE-Konfigurationseinstellungen, die für den Standort "Redmond" gelten sollen:
    
        New-CsQoEConfiguration -Identity "site:Redmond"

## So erstellen Sie eine neue Auflistung von QoE-Konfigurationseinstellungen mit deaktivierter QoE-Überwachung

  - Da in dem oben aufgeführten Befehl keine Parameter (außer dem obligatorischen Identity-Parameter) angegeben sind, werden in den neuen Konfigurationseinstellungen bei allen Eigenschaften die Standardwerte verwendet. Wenn Sie Einstellungen erstellen möchten, deren Eigenschaften andere Werte haben, fügen Sie in den Befehl einfach den entsprechenden Parameter mit dem gewünschten Wert ein. Beispiel: Zum Erstellen von QoE-Konfigurationseinstellungen, die es standardmäßig erlauben, die QoE-Aufzeichnung zu deaktivieren, verwenden Sie einen Befehl der folgenden Art:
    
        New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False

## So geben Sie beim Erstellen einer neuen Auflistung von QoE-Konfigurationseinstellungen mehrere Eigenschaftswerte an:

  - Sie können mehrere Eigenschaftswerte angeben, indem Sie mehrere Parameter in den Befehl einfügen. So konfiguriert zum Beispiel dieser Befehl die neuen Einstellungen so, dass QoE-Daten 30 Tage aufbewahrt und alte Daten um 03:00 Uhr bereinigt werden:
    
        New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3

Weitere Informationen finden Sie in dem Hilfethema zum [New-CsQoEConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsQoEConfiguration)-Cmdlet.

