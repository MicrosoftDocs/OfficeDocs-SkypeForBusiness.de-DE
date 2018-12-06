---
title: Konfigurieren von Portbereichen für Microsoft Lync-Clients
TOCTitle: Konfigurieren von Portbereichen für Microsoft Lync-Clients
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204760(v=OCS.15)
ms:contentKeyID: 49293493
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von Portbereichen für Microsoft Lync-Clients

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Standardmäßig können Lync-Clientanwendungen einen beliebigen Port zwischen 1024 und 65535 verwenden, wenn sie an einer Kommunikationssitzung beteiligt sind. Dies ist darauf zurückzuführen, dass bestimmte Portbereiche nicht automatisch für Clients aktiviert sind. Um Quality of Service (QoS) zu verwenden, müssen Sie jedoch die verschiedenen Datenverkehrstypen (Audio, Video, Medien, Anwendungsfreigabe und Dateiübertragung) einer Reihe von eindeutigen Portbereichen neu zuweisen. Diese Neuzuweisung kann mit dem Cmdlet **Set-CsConferencingConfiguration** durchgeführt werden.

Sie können die derzeit für Kommunikationssitzungen verwendeten Portbereiche ermitteln, indem Sie in der Verwaltungsshell für Microsoft Lync Server 2013 den folgenden Befehl ausführen:

    Get-CsConferencingConfiguration

Sofern Sie seit der Installation von Lync Server 2013 noch keine Änderungen an den Konferenzeinstellungen vorgenommen haben, sollten Informationen zurückgegeben werden, die diese Eigenschaftswerte enthalten:

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

Wenn Sie sich die vorherige Ausgabe genauer ansehen, werden Sie zwei wichtige Aspekte feststellen. Zunächst ist die Eigenschaft **ClientMediaPortRangeEnabled** auf **False** gesetzt:

    ClientMediaPortRangeEnabled : False

Das ist wichtig, denn wenn diese Eigenschaft auf False gesetzt ist, verwenden Lync-Clients, die an einer Kommunikationssitzung beteiligt sind, einen beliebigen verfügbaren Port zwischen Port 1024 und 65535. Dies erfolgt unabhängig von anderen Porteinstellungen (z. B. ClientMediaPort oder ClientVideoPort). Wenn Sie die Verwendung auf einen bestimmten Satz von Ports beschränken möchten (was beispielsweise bei der Implementierung von Quality of Service erforderlich ist), müssen Sie zunächst die Client-Medienportbereiche aktivieren. Hierzu können Sie den folgenden Windows PowerShell-Befehl verwenden:

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

Mit dem obigen Befehl werden die Client-Medienportbereiche für die globale Auflistung der Konferenzkonfigurationseinstellungen aktiviert. Diese Einstellungen können jedoch auch auf Standortebene und/oder Dienstebene (nur für den Konferenzserverdienst) angewendet werden. Um die Client-Medienportbereiche für einen bestimmten Standort oder Server zu aktivieren, geben Sie beim Aufruf von **Set-CsConferencingConfiguration** die Identität des Standorts oder Servers an:

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

Alternativ können Sie diesen Befehl verwenden, um Portbereiche für die gesamten Konferenzkonfigurationseinstellungen gleichzeitig zu aktivieren:

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

Der zweite wichtige Aspekt ist, dass für jeden Typ von Netzwerkdatenverkehr standardmäßig dieselben Medienportbereiche festgelegt werden, wie Sie in der Beispielausgabe sehen können:

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

Zur Implementierung des Quality of Service (QoS) muss jeder dieser Portbereiche identisch sein. Sie können diese Portbereiche z. B. wie folgt konfigurieren:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Client-Datenverkehrstyp</th>
<th>Anfang des Portbereichs</th>
<th>Portbereich</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Audio</p></td>
<td><p>50020</p></td>
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>Video</p></td>
<td><p>58000</p></td>
<td><p>20</p></td>
</tr>
<tr class="odd">
<td><p>Anwendungsfreigabe</p></td>
<td><p>42000</p></td>
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>Dateiübertragung</p></td>
<td><p>42020</p></td>
<td><p>20</p></td>
</tr>
</tbody>
</table>


In der obigen Tabelle stellen Clientportbereiche eine Teilmenge der für die Server konfigurierten Portbereiche dar. Beispielsweise ist auf den Servern konfiguriert, dass die Ports 40803 bis 49151 für die Anwendungsfreigabe verwendet werden. Auf den Clientcomputern ist konfiguriert, dass die Ports 42000 bis 42019 für die Anwendungsfreigabe verwendet werden. Dies dient hauptsächlich dem Zweck, die QoS-Verwaltung zu vereinfachen: Die Clientports müssen keine Teilmenge der auf dem Server verwendeten Ports darstellen. (Sie können auf Clientcomputern auch konfigurieren, dass die Ports 10000 bis 10019 für die Anwendungsfreigabe verwendet werden.) Es wird jedoch empfohlen, für Clients eine Teilmenge der Serverportbereiche zu verwenden.

Zudem haben Sie vielleicht festgestellt, dass auf den Servern 8348 Ports für die Anwendungsfreigabe reserviert wurden, auf den Clients jedoch lediglich 20 Ports. Dies ist auch nur eine Empfehlung und keine verbindliche Regel. Im Allgemeinen können Sie einplanen, dass jeder verfügbare Port eine einzelne Kommunikationssitzung darstellt: Wenn in einem Portbereich 100 Ports verfügbar sind, bedeutet dies, dass der fragliche Computer zu einem bestimmten Zeitpunkt an maximal 100 Kommunikationssitzungen teilnehmen kann. Da Server wahrscheinlich an weitaus mehr Unterhaltungen als Clients beteiligt sind, ist es sinnvoll, auf den Servern viel mehr Ports als auf den Clients zu öffnen. Wenn Sie auf einem Client 20 Ports für die Anwendungsfreigabe reservieren, bedeutet dies, dass ein Benutzer auf dem angegebenen Gerät an 20 Anwendungssitzungen gleichzeitig teilnehmen kann. Dies sollte für die allermeisten Benutzer ausreichend sein.

Sie können den folgenden Lync Server-Verwaltungsshell-Befehl verwenden, um die obigen Portbereiche Ihrer globalen Auflistung der Konferenzkonfigurationseinstellungen zuzuweisen:

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

Oder verwenden Sie diesen Befehl, um dieselben Portbereiche für alle Konferenzkonfigurationseinstellungen zuzuweisen:

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

Einzelne Benutzer müssen sich bei Lync abmelden und dann wieder anmelden, bevor diese Änderungen tatsächlich in Kraft treten.


> [!NOTE]
> Sie können auch Client-Medienportbereiche aktivieren und diese Portbereiche dann mit einem einzelnen Befehl zuweisen. Beispiel:<BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>


