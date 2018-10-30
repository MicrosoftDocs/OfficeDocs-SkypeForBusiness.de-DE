---
title: Grundlegendes zu Konfigurationseinstellungen für den zentralisierten Protokollierungsdienst
TOCTitle: Grundlegendes zu Konfigurationseinstellungen für den zentralisierten Protokollierungsdienst
ms:assetid: 3c34e600-0b91-43dc-b4cc-90b6a70ee12e
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688029(v=OCS.15)
ms:contentKeyID: 49890710
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Grundlegendes zu Konfigurationseinstellungen für den zentralisierten Protokollierungsdienst

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Der Zentraler Protokollierungsdienst ist dazu konfiguriert zu definieren, was der Protokollierungsdienst sammeln soll, wie und von wo er sammelt und welche Protokolleinstellungen verwendet werden. Sie definieren diese Einstellungen für eine globale (also die gesamte) oder eine standortbezogene Bereitstellung (also einen benannten Standort in Ihrer Bereitstellung). Für jede Protokollierung, die Sie definieren, werden die Einstellungen verwendet, die jeweils für die von Ihnen für Befehle zum Starten, Beenden, Leeren und Durchsuchen von Protokollen verwendete Identität geeignet sind.

## So zeigen Sie die aktuelle Zentraler Protokollierungsdienst-Konfiguration an

Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

Geben Sie den folgenden Befehl an der Eingabeaufforderung ein:

    Get-CsClsConfiguration


> [!TIP]
> Sie können den Bereich der zurückgegebenen Konfigurationseinstellungen beschränken oder erweitern, indem Sie <CODE>-Identity</CODE> und einen Bereich, z.&nbsp;B. "Site:Redmond", so definieren, dass nur die CsClsConfiguration für den Standort Redmond zurückgegeben wird. Wenn Sie Details über einen bestimmten Teil der Konfiguration erhalten möchten, können Sie die Ausgabe an ein anderes Windows PowerShell-Cmdlet weiterleiten. Um beispielsweise Details über die Szenarien zu erhalten, die in der Konfiguration für den Standort "Redmond" definiert sind, geben Sie Folgendes ein: <CODE>Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandPropery Scenarios</CODE>



![Beispielausgabe von Get-CsClsConfiguration](images/JJ688138.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Beispielausgabe von Get-CsClsConfiguration")

Das vom Cmdlet empfangene Ergebnis zeigt die aktuelle Konfiguration des Zentraler Protokollierungsdienst an.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Konfigurationseinstellung</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Identity</strong></p></td>
<td><p>Identifiziert den Bereich und den Namen dieser Konfiguration. Es gibt nur eine globale Konfiguration sowie eine Konfiguration pro Standort.</p></td>
</tr>
<tr class="even">
<td><p><strong>Szenarien</strong></p></td>
<td><p>Auflistung aller Szenarien, die für diese Konfiguration definiert sind.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SearchTerms</strong></p></td>
<td><p>Definierte Suchbegriffe für die Konfiguration. Office 365, keine lokalen Bereitstellungen.</p></td>
</tr>
<tr class="even">
<td><p><strong>SecurityGroups</strong></p></td>
<td><p>Definierte Sicherheitsgruppen, die steuern, wer (welche Mitglieder der Sicherheitsgruppen) Computer basierend auf dem Standort, an dem sie sich befinden, anzeigen können. &quot;Standort&quot; ist in diesem Kontext der Standort, wie er im Topologie-Generator definiert ist.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Regions</strong></p></td>
<td><p>Definierte Regionen werden verwendet, um Sicherheitsgruppen zu einer Region zusammenzufassen, beispielsweise EMEA.</p></td>
</tr>
<tr class="even">
<td><p><strong>EtlFileFolder</strong></p></td>
<td><p>Definierter Pfad zu dem Speicherort, an dem Protokolldateien auf Computer geschrieben werden. CLSAgent schreibt die Protokolldatei und wird im Kontext des Netzwerkdiensts ausgeführt. In diesem Fall wird %TEMP% zu %WINDIR%\ServiceProfiles\NetworkService\AppData\Local erweitert.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EtlFileRolloverSizeMB</strong></p></td>
<td><p>Der Parameter gibt die maximale Größe der Protokolldatei vor der Erstellung einer neuen ETL-Datei (Event Trace Log, Ereignis-Ablaufverfolgungsprotokoll) an. Wenn die definierte Größe erreicht ist, wird eine neue Protokolldatei erstellt, auch wenn die in EtlFileRolloverMinutes festgelegte maximale Zeit noch nicht erreicht wurde.</p></td>
</tr>
<tr class="even">
<td><p><strong>EtlFileRolloverMinutes</strong></p></td>
<td><p>Die definierte maximale Zeitspanne in Minuten, die für ein Protokoll verstreichen kann, bevor eine neue ETL-Datei erstellt wird. Wenn der Timer abläuft, wird eine neue Protokolldatei erstellt, auch wenn die in EtlFileRolloverSizeMB festgelegte maximale Größe noch nicht erreicht wurde.</p></td>
</tr>
<tr class="odd">
<td><p><strong>TmfFileSearchPath</strong></p></td>
<td><p>Speicherort, an dem nach den Formatdateien für Ablaufverfolgungsmeldungen gesucht wird. Die Formatdateien für Ablaufverfolgungsmeldungen werden verwendet, um die binären Dateien in ein von Menschen lesbares Format zu konvertieren.</p></td>
</tr>
<tr class="even">
<td><p><strong>CacheFileLocalFolders</strong></p></td>
<td><p>Definierter Pfad zu dem Speicherort, an dem Cachedateien auf Computer geschrieben werden. CLSAgent schreibt die Cachedatei und wird im Kontext des Netzwerkdiensts ausgeführt. In diesem Fall wird %TEMP% zu %WINDIR%\ServiceProfiles\NetworkService\AppData\Local erweitert. Standardmäßig werden Cache- und Protokolldateien in dasselbe Verzeichnis geschrieben.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CacheFileNetworkFolder</strong></p></td>
<td><p>Sie können einen UNC-Pfad (Universal Naming Convention) definieren, um die Cachedateien während Protokollierungsvorgängen zu empfangen.</p></td>
</tr>
<tr class="even">
<td><p><strong>CacheFileLocalRetentionPeriod</strong></p></td>
<td><p>Definiert als die Höchstdauer in Tagen, für die Cachedateien beibehalten werden.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CacheFileMaxDiskUsage</strong></p></td>
<td><p>Definiert als der prozentuale Anteil des Speicherplatzes, der von den Cachedateien verwendet werden kann.</p></td>
</tr>
<tr class="even">
<td><p><strong>ComponentThrottleLimit</strong></p></td>
<td><p>Definiert als die Höchstzahl an Ablaufverfolgungen pro Sekunde, die eine Komponente erzeugen kann, bevor der automatische Drosselbegrenzer ausgelöst wird.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ComponentThrottleSample</strong></p></td>
<td><p>Anzahl der möglichen Überschreitungen von ComponentThrottleLimit in 60 Sekunden.</p></td>
</tr>
<tr class="even">
<td><p><strong>MinimumClsAgentServiceVersion</strong></p></td>
<td><p>Die mindestens erforderliche Version des CLSAgent, die ausgeführt werden kann. Dieses Element ist für Office 365 gedacht.</p></td>
</tr>
</tbody>
</table>


## Siehe auch

#### Konzepte

[Übersicht über den zentralisierten Protokollierungsdienst](lync-server-2013-overview-of-the-centralized-logging-service.md)  

#### Weitere Ressourcen

[Set-CsClsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClsConfiguration)  
[Remove-CsClsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsClsConfiguration)  
[New-CsClsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClsConfiguration)  
[Get-CsClsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClsConfiguration)

