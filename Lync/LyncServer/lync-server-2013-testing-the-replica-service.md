---
title: 'Lync Server 2013: Testen des Replikat Diensts'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the replica service
ms:assetid: 4ff2cc91-0036-4c5a-9792-7bf43d8ce18d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727303(v=OCS.15)
ms:contentKeyID: 63969600
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c955da727a4213098a5b6af4f6fbb348bb60dd21
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745435"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-replica-service-in-lync-server-2013"></a>Testen des Replikat Diensts in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-11-03_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Überprüfungszeitplan</p></td>
<td><p>Täglich</p></td>
</tr>
<tr class="even">
<td><p>Test Tool</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Erforderliche Berechtigungen</p></td>
<td><p>Wenn Benutzer lokal mit der lync Server-Verwaltungsshell ausgeführt werden, müssen Sie Mitglied der RTCUniversalServerAdmins-Sicherheitsgruppe sein.</p>
<p>Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des <strong>Test-CsReplica-</strong> Cmdlets verfügt. Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsReplica&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Das Cmdlet **Test-CsReplica** überprüft, ob der lync Server 2013-Replikat Dienst auf dem lokalen Computer ausgeführt wird. Das Cmdlet " **Test-CsReplica** " führt Aufgaben wie die folgenden aus:

  - Überprüfen des Status des Replicator-Agents und der Dienste für zentralisierte Protokollierungs-Agents

  - Überprüfen, ob die erforderlichen Ports in der Windows-Firewall geöffnet wurden

  - sicherstellen, dass die erforderlichen Active Directory-und lokalen Computersicherheitsgruppen vorhanden sind.

Beachten Sie, dass dieses Cmdlet lokal ausgeführt werden muss. Das bedeutet, dass es auf dem Computer ausgeführt werden muss, auf dem der Replikat Dienst ausgeführt wird. Es gibt keine Optionen für das Ausführen des **Test-CsReplica-** Cmdlets für einen Remoteserver.

</div>

<div>

## <a name="running-the-test"></a>Ausführen des Tests

Der in Beispiel 1 gezeigte Befehl testet den lync Server 2013-Replikat Dienst auf dem lokalen Computer. In diesem Beispiel wird der Verbose-Parameter verwendet, um sicherzustellen, dass Informationen über den Test – einschließlich des eventuellen Fehlers oder des Erfolgs des Tests und der Position des vom Test generierten Berichts – auf dem Bildschirm angezeigt werden.

    Test-CsReplica -Verbose

Beispiel 2 ist eine Variation des Befehls, die in Beispiel 1 gezeigt wird. In diesem Fall ist der Berichtsparameter enthalten, um einen Ordnerpfad und einen Namen für den vom Test generierten Bericht anzugeben. Wenn Sie keinen Berichtspfad angeben, erhält der Bericht einen automatisch generierten Namen, der wie folgt lautet:

C:\\Benutzer\\Administrator. "litwareinc\\APPDATA\\local\\Temp\\1\\Test-CS-Replica-3db40ee0-4b5d-4f58-8d3d-b1e61253129e. html

    Test-CsReplica -Verbose -Report C:\Logs\ReplicaTest.html

</div>

<div>

## <a name="determining-success-or-failure"></a>Ermitteln von Erfolg oder Misserfolg

Abschnittstext hier einfügen.

Ausführlich: Erstellen einer neuen Protokolldatei "C:\\Benutzer\\testen\\APPDATA\\local\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c. xml".

Ausführlich: Erstellen einer neuen Protokolldatei "C:\\Benutzer\\testen\\APPDATA\\local\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c. xml".

Ausführlich: die Verarbeitung von "Test-CsReplica" wurde erfolgreich abgeschlossen.

Ausführlich: detaillierte Ergebnisse finden Sie unter "C\\: Benutzer\\testen\\APPDATA\\local\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c. xml".

Ausführlich: Erstellen einer neuen Protokolldatei

"C:\\Benutzer\\testen\\APPDATA\\local\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e

d3bd0e4a083. xml ".

Ausführlich: Erstellen einer neuen Protokolldatei

"C:\\Benutzer\\testen\\APPDATA\\local\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e

d3bd0e4a083. html ".

Warnung: Test-CsReplica ist fehlgeschlagen.

Warnung: detaillierte Ergebnisse finden Sie unter

"C:\\Benutzer\\testen\\APPDATA\\local\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e

d3bd0e4a083. html ".

Test-CsReplica: Fehler bei der Befehlsausführung: der angeforderte Registrierungszugriff ist nicht

zulässig.

Zeile: 1 Zeichen: 1

\+Test-CsReplica-Verbose

\+ ~~~~~~~~~~~~~~~~~~~~~~~

\+CategoryInfo: InvalidOperation: (:) \[Test-CsReplica\], Sicherheit

Ausnahme

\+FullyQualifiedErrorId: ProcessingFailed, Microsoft. RTC. Management. deploy

ment. TestReplicaCmdlet

PS C:\\testen\\der Benutzer\>

PS C:\\Benutzer\\testen\> Test-CsUcwaConference-TargetFqdn "LyncTest. SelfHost. Corp. M

icrosoft.com "

Warnung: Fehler beim Lesen der Registrierungsstellen-Portnummer für die angegebene vollqualifizierte

Domänenname (FQDN). Verwenden der standardmäßigen Registrierungs Portnummer Ausnahme

System. InvalidOperationException: kein übereinstimmender Cluster in der Topologie gefunden.

am

Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri

eveRegistrarPortFromTopology (Int32& registrarPortNumber)

Test-CsUcwaConference: Es wurde kein Testbenutzer zugewiesen

\[LyncTest.SelfHost.Corp.Microsoft.com\]. Überprüfen Sie die Benutzerkonfiguration testen.

Zeile: 1 Zeichen: 1

\+Test-CsUcwaConference-TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"

\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

\+CategoryInfo: ResourceUnavailable: (:) \[Test-CsUcwaConference\]

, InvalidOperationException

\+FullyQualifiedErrorId: NotFoundTestUsers, Microsoft. RTC. Management. Synth

eticTransactions.TestUcwaConferenceCmdlet

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Nachfolgend finden Sie einige häufige Gründe, warum **Test-CsReplica** möglicherweise fehlschlägt:

  - Möglicherweise liegt ein größeres Problem mit dem Replicator-Agent und den zentralen Protokollierungs-Agent-Diensten vor.

  - Die erforderlichen Ports sind möglicherweise nicht in der Windows-Firewall geöffnet.

  - Die erforderlichen Active Directory-und lokalen Computersicherheitsgruppen sind möglicherweise nicht vorhanden

</div>

</div>

<span> </span>

</div>

</div>

</div>

