---
title: Konfigurieren von Einstellungen für Medienportbereiche
TOCTitle: Konfigurieren von Einstellungen für Medienportbereiche
ms:assetid: 2c4b7c0b-0dce-48f4-a489-336d6e526f7c
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204770(v=OCS.15)
ms:contentKeyID: 49293552
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von Einstellungen für Medienportbereiche

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Die Einstellungen für Medienportbereiche können sich erheblich auf die Clientleistung auswirken und sollten konfiguriert werden. Sie können die Lync Server-Verwaltungsshell zum Konfigurieren dieser Einstellungen verwenden.

### Einstellungen für den Medienportbereich

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Einstellung</th>
<th>Beschreibung</th>
<th>Lync Server-Verwaltungsshell-Cmdlet</th>
<th>Cmdlet-Parameter</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Portrange\Enabled</p></td>
<td><p>Gibt an, ob die vom Server gesendeten Portbereiche vom Client für Medien- und Signaldatenverkehr verwendet werden sollen. Wird gemeinsam mit den Unterwerten &quot;MinMediaPort&quot; und &quot;MaxMediaPort&quot; verwendet.</p></td>
<td><p><strong>CsConferencingConfiguration</strong></p></td>
<td><p>ClientMediaPortRangeEnabled</p></td>
</tr>
<tr class="even">
<td><p>Portrange\MinMediaPort</p></td>
<td><p>Gibt die erste Portnummer an, die für Mediendaten verwendet wird. Gibt in Kombination mit &quot;MaxMediaPort&quot; den Portbereich an. Der empfohlene Mindestbereich umfasst 40 Ports.</p></td>
<td><p><strong>CsConferencingConfiguration</strong></p></td>
<td><p>ClientMediaPort (repräsentiert die erste Portnummer, die für Clientmediendaten verwendet wird)</p></td>
</tr>
<tr class="odd">
<td><p>Portrange\MaxMediaPort</p></td>
<td><p>Gibt die höchste Portnummer an, die für Mediendaten verwendet wird. Gibt in Kombination mit &quot;MinMediaPort&quot; den Portbereich an. Der empfohlene Mindestbereich umfasst 40 Ports.</p></td>
<td><p><strong>CsConferencingConfiguration</strong></p></td>
<td><p>ClientMediaPortRange (gibt die Gesamtanzahl von Ports an, die für Clientmediendaten verfügbar sind; der Standardwert lautet 40)</p></td>
</tr>
</tbody>
</table>


## So konfigurieren Sie die Einstellungen für den Medienportbereich

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Führen Sie das folgende Cmdlet aus:
    
        Get-CsConferencingConfiguration
    
    Dieses Cmdlet gibt die Konfigurationseinstellungen für Konferenzen zurück.

3.  Führen Sie das folgende Cmdlet mit den Parametern und Werten aus, die Sie ändern möchten (detaillierte Informationen zu den Parametern für dieses Cmdlet finden Sie in der Dokumentation zur Lync Server-Verwaltungsshell):
    
        Set-CsConferencingConfiguration
    

    > [!NOTE]
    > Sie können zusätzliche Sätze mit Konfigurationseinstellungen für Konferenzen für bestimmte Standorte erstellen. Verwenden Sie das Cmdlet <STRONG>New- CsConferencingConfiguration</STRONG> mit einer Standortidentität. Beim Erstellen neuer Konfigurationseinstellungen für Konferenzen für einen Standort haben die Standorteinstellungen Vorrang vor den globalen Einstellungen. Ausführliche Informationen finden Sie in der Dokumentation zur Lync Server-Verwaltungsshell.


