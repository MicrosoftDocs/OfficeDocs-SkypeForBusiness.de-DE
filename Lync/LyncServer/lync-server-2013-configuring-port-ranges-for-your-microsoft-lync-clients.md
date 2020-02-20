---
title: 'Lync Server 2013: Konfigurieren von Portbereichen für Ihre Microsoft lync-Clients'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring port ranges for your Microsoft Lync clients
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f16fa3b16a992ce15f16e7413a59525e55ddba75
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147288"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-for-your-microsoft-lync-clients-in-lync-server-2013"></a>Konfigurieren von Portbereichen für Ihre Microsoft lync-Clients in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-04-22_

Lync-Clientanwendungen können standardmäßig einen beliebigen Port zwischen den Ports 1024 und 65535 verwenden, wenn Sie an einer Kommunikationssitzung beteiligt sind. Dies liegt daran, dass bestimmte Portbereiche für Clients nicht automatisch aktiviert werden. Um die Dienstqualität zu verwenden, müssen Sie jedoch die verschiedenen Datenverkehrstypen (Audio, Video, Medien, Anwendungsfreigabe und Dateiübertragung) einer Reihe eindeutiger Portbereiche neu zuweisen. Dies kann mithilfe des Cmdlets "CsConferencingConfiguration" geschehen.

<div>


> [!NOTE]  
> Endbenutzer können diese Änderungen nicht selbst vornehmen. Port Änderungen können nur von Administratoren mithilfe des Cmdlets "CsConferencingConfiguration" vorgenommen werden.



</div>

Sie können bestimmen, welche Portbereiche derzeit für Kommunikationssitzungen verwendet werden, indem Sie den folgenden Befehl in der Microsoft lync Server 2013 Verwaltungsshell ausführen:

    Get-CsConferencingConfiguration

Unter der Annahme, dass Sie seit der Installation von lync Server 2013 keine Änderungen an Ihren Konferenzeinstellungen vorgenommen haben, sollten Sie Informationen zurück erhalten, die diese Eigenschaftswerte enthalten:

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

Wenn Sie sich die vorherige Ausgabe genauer ansehen, werden Sie zwei wichtige Aspekte feststellen. Zunächst ist die Eigenschaft ClientMediaPortRangeEnabled auf False gesetzt:

    ClientMediaPortRangeEnabled : False

Dies ist wichtig, da lync-Clients, wenn diese Eigenschaft auf "false" festgelegt ist, einen beliebigen verfügbaren Port zwischen den Ports 1024 und 65535 verwenden, wenn Sie an einer Kommunikationssitzung beteiligt sind. Dies gilt unabhängig von anderen Porteinstellungen (beispielsweise ClientMediaPort oder ClientVideoPort). Wenn Sie die Verwendung auf eine bestimmte Anzahl von Ports einschränken möchten (und dies möchten Sie tun, wenn Sie die Implementierung von Quality of Service planen), müssen Sie zuerst die Client-Medien Portbereiche aktivieren. Dies kann mithilfe des folgenden Windows PowerShell Befehls erfolgen:

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

Mit dem obigen Befehl werden die Client-Medienportbereiche für die globale Auflistung der Konferenzkonfigurationseinstellungen aktiviert. Diese Einstellungen können jedoch auch auf Standortebene und/oder Dienstebene (nur für den Konferenzserverdienst) angewendet werden. Um die Client-Medienportbereiche für einen bestimmten Standort oder Server zu aktivieren, geben Sie beim Aufruf von Set-CsConferencingConfiguration die Identität des Standorts oder Servers an:

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

Sie können den folgenden lync Server-Verwaltungsshell Befehl verwenden, um die vorhergehenden Portbereiche ihrer globalen Sammlung von Konferenz Konfigurationseinstellungen zuzuweisen:

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

Oder verwenden Sie diesen Befehl, um dieselben Portbereiche für alle Konferenzkonfigurationseinstellungen zuzuweisen:

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

Einzelne Benutzer müssen sich von lync abmelden und dann wieder anmelden, bevor diese Änderungen tatsächlich wirksam werden.

<div>


> [!NOTE]  
> Sie können auch Client-Medienportbereiche aktivieren und diese Portbereiche dann mit einem einzelnen Befehl zuweisen. Beispiel:<BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>



</div>

</div>

<span> </span>

</div>

</div>

</div>

