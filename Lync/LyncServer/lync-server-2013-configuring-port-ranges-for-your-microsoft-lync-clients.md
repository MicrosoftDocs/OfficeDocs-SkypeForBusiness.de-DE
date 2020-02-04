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
ms.openlocfilehash: f6405ff6738315476efb7ee65f6d5e020a7cf28a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730675"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-for-your-microsoft-lync-clients-in-lync-server-2013"></a>Konfigurieren von Portbereichen für Ihre Microsoft lync-Clients in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-04-22_

Standardmäßig können lync-Clientanwendungen einen beliebigen Port zwischen den Anschlüssen 1024 und 65535 verwenden, wenn Sie an einer Kommunikationssitzung beteiligt sind. Dies liegt daran, dass bestimmte Portbereiche für Clients nicht automatisch aktiviert werden. Um die Dienstqualität zu nutzen, müssen Sie jedoch die verschiedenen Datenverkehrstypen (Audio, Video, Medien, Anwendungsfreigabe und Dateiübertragung) einer Reihe von eindeutigen Portbereichen neu zuweisen. Dies kann mithilfe des Cmdlets "CsConferencingConfiguration" erfolgen.

<div>


> [!NOTE]  
> Endbenutzer können diese Änderungen nicht selbst vornehmen. Port Änderungen können nur von Administratoren mit dem Cmdlet "Satz-CsConferencingConfiguration" vorgenommen werden.



</div>

Sie können ermitteln, welche Portbereiche derzeit für Kommunikationssitzungen verwendet werden, indem Sie den folgenden Befehl in der Microsoft lync Server 2013-Verwaltungsshell ausführen:

    Get-CsConferencingConfiguration

Vorausgesetzt, dass Sie seit der Installation von lync Server 2013 keine Änderungen an Ihren Konferenzeinstellungen vorgenommen haben, sollten Sie Informationen zurück erhalten, die diese Eigenschaftswerte enthalten:

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

Wenn Sie die vorhergehende Ausgabe genau betrachten, sehen Sie zwei wichtige Dinge. Zuerst ist die ClientMediaPortRangeEnabled-Eigenschaft auf false festgelegt:

    ClientMediaPortRangeEnabled : False

Das ist wichtig, da lync-Clients, wenn diese Eigenschaft auf "false" festgelegt ist, einen beliebigen verfügbaren Port zwischen den Anschlüssen 1024 und 65535 verwenden, wenn Sie an einer Kommunikationssitzung beteiligt sind. Dies gilt unabhängig von anderen Porteinstellungen (beispielsweise ClientMediaPort oder ClientVideoPort). Wenn Sie die Verwendung auf eine bestimmte Anzahl von Ports einschränken möchten (und dies ist etwas, was Sie tun möchten, wenn Sie die Implementierung von Quality of Service planen), müssen Sie zuerst die Client Medien-Portbereiche aktivieren. Dies kann mithilfe des folgenden Windows PowerShell-Befehls erfolgen:

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

Der obige Befehl aktiviert Client Medien-Portbereiche für die globale Sammlung von Konferenz Konfigurationseinstellungen; Diese Einstellungen können jedoch auch auf den Website Bereich und/oder den Dienstbereich angewendet werden (nur für den Conferencing Server-Dienst). Wenn Sie die Client Medien-Portbereiche für eine bestimmte Website oder einen bestimmten Server aktivieren möchten, geben Sie die Identität dieser Website oder des Servers beim Aufrufen von CsConferencingConfiguration an:

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

Sie können diesen Befehl auch verwenden, um Portbereiche für alle Ihre Konferenz Konfigurationseinstellungen gleichzeitig zu aktivieren:

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

Wichtig ist, dass die Beispielausgabe zeigt, dass standardmäßig die für die einzelnen Netzwerkdatenverkehr-Typen festgelegten Medien Portbereiche identisch sind:

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

Um QoS zu implementieren, müssen alle diese Portbereiche eindeutig sein. So können Sie beispielsweise die Portbereiche wie folgt konfigurieren:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Client Datenverkehrstyp</th>
<th>Port Start</th>
<th>Port Bereich</th>
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


In der obigen Tabelle stellen Client-Portbereiche eine Teilmenge der Portbereiche dar, die für Ihre Server konfiguriert sind. Auf den Servern wurde die Anwendungsfreigabe beispielsweise so konfiguriert, dass die Ports 40803 bis 49151 verwendet werden. auf den Clientcomputern ist die Anwendungsfreigabe so konfiguriert, dass die Ports 42000 bis 42019 verwendet werden. Dies erfolgt in erster Linie, um die Verwaltung von QoS zu vereinfachen: Clientports müssen keine Teilmenge der auf dem Server verwendeten Ports darstellen. (Beispielsweise können Sie auf den Clientcomputern die Anwendungsfreigabe so konfigurieren, dass die Verwendung von Ports 10000 bis 10019 verwendet wird.) Es wird jedoch empfohlen, dass Sie die Client Portbereiche zu einer Teilmenge der Server Portbereiche machen.

Darüber hinaus haben Sie möglicherweise festgestellt, dass 8348-Ports für die Anwendungsfreigabe auf den Servern reserviert wurden, aber nur 20 Ports für die Anwendungsfreigabe auf den Clients reserviert wurden. Auch dies wird empfohlen, ist aber keine harte und schnelle Regel. Im Allgemeinen können Sie jeden verfügbaren Port in Betracht ziehen, um eine einzelne Kommunikationssitzung darzustellen: Wenn Sie 100-Ports in einem Portbereich zur Verfügung haben, bedeutet dies, dass der fragliche Computer zu einem bestimmten Zeitpunkt an maximal 100 Kommunikationssitzungen teilnehmen kann. Da Server wahrscheinlich an vielen weiteren Unterhaltungen als Clients teilnehmen, ist es sinnvoll, viel mehr Ports auf Servern als auf Clients zu öffnen. Wenn Sie 20 Ports für die Anwendungsfreigabe auf einem Client beiseite legen, bedeutet dies, dass ein Benutzer an 20 Anwendungsfreigabesitzungen auf dem angegebenen Gerät und alle zur gleichen Zeit teilnehmen kann. Dies sollte für die meisten Benutzer ausreichend sein.

Wenn Sie der globalen Sammlung von Konferenz Konfigurationseinstellungen die vorherigen Portbereiche zuweisen möchten, können Sie den folgenden Befehl der lync Server-Verwaltungsshell verwenden:

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

Oder verwenden Sie diesen Befehl, um dieselben Portbereiche für alle Konferenz Konfigurationseinstellungen zuzuweisen:

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

Einzelne Benutzer müssen sich von lync abmelden und dann wieder anmelden, bevor diese Änderungen tatsächlich wirksam werden.

<div>


> [!NOTE]  
> Sie können auch Client Medien-Portbereiche aktivieren und dann mithilfe eines einzigen Befehls Diese Portbereiche zuweisen. Beispiel:<BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>



</div>

</div>

<span> </span>

</div>

</div>

</div>

