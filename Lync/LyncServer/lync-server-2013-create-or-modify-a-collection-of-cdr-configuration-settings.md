---
title: Erstellen oder Ändern einer Auflistung von Konfigurationseinstellungen für die Aufzeichnung von Kommunikationsdatensätzen
TOCTitle: Erstellen oder Ändern einer Auflistung von Konfigurationseinstellungen für die Aufzeichnung von Kommunikationsdatensätzen
ms:assetid: c830be5a-2a82-468d-9c46-d3fec0f79fd0
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ721878(v=OCS.15)
ms:contentKeyID: 49890937
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen oder Ändern einer Auflistung von Konfigurationseinstellungen für die Aufzeichnung von Kommunikationsdatensätzen

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Die Aufzeichnung von Kommunikationsdatensätzen (KDS) ermöglicht das Nachverfolgen von Peer-zu-Peer-, VoIP- und Konferenzanrufen. Diese Nutzungsdaten umfassen Informationen wie z. B. Anrufer, Angerufener, Anrufzeitpunkt und Anrufdauer.

Bei der Installation von Microsoft Lync Server 2013 wird eine einzelne, globale Auflistung von KDS-Konfigurationseinstellungen erstellt. Administratoren haben auch die Möglichkeit, benutzerdefinierte Einstellungen für die Standortebene zu erstellen. Wenn diese Einstellungen auf Standortebene verwendet werden, haben sie Vorrang vor den globalen Einstellungen. Wenn Sie beispielsweise Einstellungen auf Standortebene für den Standort "Redmond" erstellen, werden diese Einstellung (anstelle der globalen Einstellungen) für die KDS-Verwaltung in Redmond verwendet.

KDS-Konfigurationseinstellungen können Sie mit der Lync Server-Systemsteuerung oder dem [New-CsCdrConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsCdrConfiguration)-Cmdlet erstellen. Mit der Lync Server-Systemsteuerung oder dem [Set-CsCdrConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCdrConfiguration)-Cmdlet können Sie vorhandene Einstellungen ändern. Falls Sie die Lync Server-Systemsteuerung zum Erstellen oder Ändern von Einstellungen verwenden, sind die folgenden Optionen verfügbar:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Benutzeroberflächeneinstellung</th>
<th>PowerShell-Parameter</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Name</p></td>
<td><p>Identity</p></td>
<td><p>Eindeutiger Bezeichner für die KDS-Konfigurationseinstellungen, die erstellt werden. Diese Einstellungen können nur auf der Standortebene erstellt werden.</p></td>
</tr>
<tr class="even">
<td><p>Überwachung von KDS-Aufzeichnungen aktivieren</p></td>
<td><p>EnableCDR</p></td>
<td><p>Gibt an, ob KDS aktiviert ist.</p></td>
</tr>
<tr class="odd">
<td><p>Bereinigung von KDS-Aufzeichnungen aktivieren</p></td>
<td><p>EnablePurging</p></td>
<td><p>Gibt an, ob Kommunikationsdatensätze (KDS) regelmäßig aus der KDS-Datenbank gelöscht werden.</p></td>
</tr>
<tr class="even">
<td><p>Maximale Aufbewahrungsdauer für KDS-Aufzeichnungen (in Tagen)</p></td>
<td><p>KeepCallDetailForDays</p></td>
<td><p>Gibt die Anzahl von Tagen an, die KDS-Datensätze in der KDS-Datenbank gespeichert werden. Datensätze, die älter sind als angegeben, werden automatisch gelöscht. (Beachten Sie, dass der Löschvorgang nur stattfindet, wenn die Bereinigung aktiviert wurde.)</p></td>
</tr>
<tr class="odd">
<td><p>Maximale Aufbewahrungsdauer von Fehlerberichtsdaten (in Tagen)</p></td>
<td><p>KeepErrorReportForDays</p></td>
<td><p>Gibt die Anzahl von Tagen an, die KDS-Fehlerberichte aufbewahrt werden. Berichte, die älter sind als angegeben, werden automatisch gelöscht. Fehlerberichte zu Kommunikationsdatensätzen sind Diagnoseberichte, die von Clientanwendungen hochgeladen werden.</p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> Die neuen Cmdlets New-CsCdrConfiguration und Set-CsCdrConfiguration enthalten zusätzliche Optionen, die in der Lync Server-Systemsteuerung nicht verfügbar sind. Weitere Informationen finden Sie in den Hilfethemen <A href="https://docs.microsoft.com/en-us/powershell/module/skype/New-CsCdrConfiguration">New-CsCdrConfiguration</A> und <A href="https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCdrConfiguration">Set-CsCdrConfiguration</A>.



## So erstellen Sie KDS-Konfigurationseinstellungen mithilfe der Lync Server-Systemsteuerung

1.  Klicken Sie in der Lync Server-Systemsteuerung auf **Überwachen und Archivieren**.

2.  Klicken Sie auf der Registerkarte **Aufzeichnung von Kommunikationsdatensätzen** auf **Neu**.

3.  Wählen Sie im Dialogfeld **Standort auswählen** den Standort aus, in dem die neuen Konfigurationseinstellungen erstellt werden sollen. Falls das Dialogfeld leer ist, bedeutet dies, dass allen Ihren Standorten bereits eine Auflistung von KDS-Konfigurationseinstellungen zugewiesen wurde. Für jeden Standort ist nur eine einzige derartige Auflistung zulässig. In diesem Fall können Sie entweder die Einstellungen löschen und anschließend neu erstellen oder aber einfach die vorhandenen Einstellungen ändern.

4.  Wählen Sie im Dialogfeld **Neue Einstellung für die Aufzeichnung von Kommunikationsdatensätzen (KDS)** die gewünschten Optionen aus, und klicken Sie dann auf **Commit ausführen**.

## So ändern Sie vorhandene KDS-Konfigurationseinstellungen mithilfe der Lync Server-Systemsteuerung

1.  Klicken Sie in der Lync Server-Systemsteuerung auf **Überwachen und Archivieren**.

2.  Doppelklicken Sie auf die zu ändernde Auflistung von Einstellungen, oder wählen Sie die Auflistung aus, klicken Sie auf **Bearbeiten**, und klicken Sie anschließend auf **Details einblenden**. Beachten Sie, dass Sie jeweils immer nur eine Auflistung ändern können. Verwenden Sie die Lync Server-Verwaltungsshell, um dieselben Änderungen an mehreren Auflistungen vorzunehmen.

3.  Wählen Sie im Dialogfeld **Einstellung für die Aufzeichnung von Kommunikationsdatensätzen (KDS) bearbeiten** die gewünschten Optionen aus, und klicken Sie dann auf **Commit ausführen**.

## So erstellen Sie KDS-Konfigurationseinstellungen mithilfe der Lync Server-Verwaltungsshell-Cmdlets

KDS-Konfigurationseinstellungen können auch mit der Windows PowerShell und mit dem **New-CsCdrConfiguration**-Cmdlet erstellt werden. Dieses Cmdlet können Sie entweder über die Verwaltungsshell für Lync Server 2013 oder in einer Remotesitzung von Windows PowerShell ausführen. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## So erstellen Sie eine neue Auflistung von KDS-Konfigurationseinstellungen

  - Mit dem folgenden Befehl wird eine neue Auflistung von KDS-Konfigurationseinstellungen für den Standort "Redmond" erstellt:
    
        New-CsCdrConfiguration -Identity "site:Redmond"

## So erstellen Sie eine Auflistung von KDS-Konfigurationseinstellungen, mit denen die Aufzeichnung von Kommunikationsdatensätzen deaktiviert wird

  - Da im vorherigen Befehl keine weiteren Parameter (außer dem obligatorischen Identity-Parameter) angegeben wurden, werden in der neuen Auflistung von Konfigurationseinstellungen für alle Eigenschaften die Standardwerte verwendet. Um Einstellungen zu erstellen, die andere Eigenschaftswerte verwenden, geben Sie einfach den entsprechenden Parameter und Parameterwert ein. Wenn Sie beispielsweise eine Auflistung von KDS-Konfigurationseinstellungen erstellen möchten, die standardmäßig das Deaktivieren der Aufzeichnung von Kommunikationsdatensätzen erlauben, verwenden Sie den folgenden Befehl:
    
        New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

## So geben Sie beim Erstellen einer neuen Auflistung von KDS-Konfigurationseinstellungen mehrere Eigenschaftswerte an

  - Durch die Angabe mehrerer Parameter können Sie mehrere Eigenschaftswerte ändern. Beispielsweise werden mit dem folgenden Befehl die neuen Einstellungen so konfiguriert, dass Kommunikationsdatensätze 30 Tage und Fehlerberichte 90 Tage lang aufbewahrt werden:
    
        New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90

Weitere Informationen finden Sie im Hilfethema für das [New-CsCdrConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsCdrConfiguration)-Cmdlet.

