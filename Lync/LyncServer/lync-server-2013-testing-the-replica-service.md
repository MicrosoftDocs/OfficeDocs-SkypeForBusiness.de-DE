---
title: 'Lync Server 2013: Testen des Replikat Diensts'
description: 'Lync Server 2013: Testen des Replikat Diensts.'
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
ms.openlocfilehash: a61751b95115da3d6519f20f52262b7159ffcbfe
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556161"
---
# <a name="testing-the-replica-service-in-lync-server-2013"></a>Testen des Replikat Diensts in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-11-03_


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
<td><p>Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</p>
<p>Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets <strong>Test-csreplica "</strong> verfügt. Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsReplica&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Das Cmdlet **Test-csreplica "** überprüft, ob der lync Server 2013 Replikat Dienst auf dem lokalen Computer aktiv ist. Das Cmdlet **Test-csreplica "** erfüllt folgende Aufgaben:

  - Überprüfen des Status des Replikations-Agents und der zentralisierten Protokollierungs-Agent-Dienste

  - Überprüfen, ob die erforderlichen Ports in der Windows-Firewall geöffnet wurden

  - sicherstellen, dass die erforderlichen Sicherheitsgruppen für Active Directory und lokale Computer vorhanden sind.

Beachten Sie, dass dieses Cmdlet lokal ausgeführt werden muss. Das heißt, Sie muss auf demselben Computer ausgeführt werden, auf dem der Replikat Dienst ausgeführt wird. Es gibt keine Optionen zum Ausführen des **Test-csreplica "-** Cmdlets für einen Remoteserver.

</div>

<div>

## <a name="running-the-test"></a>Durchführen des Tests

Der in Beispiel 1 gezeigte Befehl testet den lync Server 2013 Replikat Dienst auf dem lokalen Computer. In diesem Beispiel wird der Verbose-Parameter verwendet, um sicherzustellen, dass Informationen zum Test – einschließlich des eventuellen Fehlers oder des Erfolgs des Tests und des Standorts des Berichts, der durch den Test generiert wird – auf dem Bildschirm angezeigt werden.

    Test-CsReplica -Verbose

Beispiel 2 ist eine Variante des Befehls in Beispiel 1. In diesem Fall ist der Parameter Report enthalten, um einen Ordnerpfad und-Namen für den vom Test generierten Bericht anzugeben. Wenn Sie keinen Berichtspfad angeben, erhält der Bericht einen automatisch generierten Namen, der dem folgenden ähnelt:

C: \\ Benutzer \\ Administrator. litwareinc \\ AppData \\ lokale \\ Temp \\ 1 \\Test-Cs-Replica-3db40ee0-4b5d-4f58-8d3d-b1e61253129e.html

    Test-CsReplica -Verbose -Report C:\Logs\ReplicaTest.html

</div>

<div>

## <a name="determining-success-or-failure"></a>Bestimmen des Erfolgs oder Fehlers

Abschnittstext hier einfügen.

Ausführlich: Erstellen einer neuen Protokolldatei "C: \\ Benutzer \\ Testen \\ AppData \\ local \\ Temp \\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".

Ausführlich: Erstellen einer neuen Protokolldatei "C: \\ Benutzer \\ Testen \\ AppData \\ local \\ Temp \\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".

Verbose: die Verarbeitung von "Test-csreplica" "wurde erfolgreich abgeschlossen.

Ausführlich: detaillierte Ergebnisse finden Sie unter "C: \\ Users \\ testing \\ AppData \\ local \\ Temp \\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".

Ausführlich: Erstellen einer neuen Protokolldatei

"C: \\ Benutzer \\ Testen \\ AppData \\ local \\ Temp \\ 2 \\ Test-csreplica"-29fddb35-f56e-4e3c-8f4c-e

d3bd0e4a083.xml ".

Ausführlich: Erstellen einer neuen Protokolldatei

"C: \\ Benutzer \\ Testen \\ AppData \\ local \\ Temp \\ 2 \\ Test-csreplica"-29fddb35-f56e-4e3c-8f4c-e

d3bd0e4a083.html ".

Warnung: Test-CsReplica fehlgeschlagen.

Warnung: detaillierte Ergebnisse finden Sie unter

"C: \\ Benutzer \\ Testen \\ AppData \\ local \\ Temp \\ 2 \\ Test-csreplica"-29fddb35-f56e-4e3c-8f4c-e

d3bd0e4a083.html ".

Test-CsReplica: Fehler bei Befehlsausführung: der angeforderte Registrierungszugriff ist nicht

erlaubt.

In der Reihe: 1 Char: 1

\+ Test-CsReplica-ausführlich

\+ ~~~~~~~~~~~~~~~~~~~~~~~

\+ CategoryInfo: InvalidOperation: (:) \[ Test-csreplica " \] , Sicherheit

Ausnahme

\+ FullyQualifiedErrorId: ProcessingFailed, Microsoft. RTC. Management. deploy

ment. TestReplicaCmdlet

PS C: \\ Testen von Benutzern \\\>

PS C: \\ Benutzer \\ Testen \> Test-CsUcwaConference-TargetFqdn "LyncTest. SelfHost. Corp. M

icrosoft.com "

Warnung: Fehler beim Lesen der Registrierungs Portnummer für die angegebene vollqualifizierte

Domänenname (FQDN). Verwenden der standardmäßigen Registrierungsstellen-Portnummer. Ausnahme

System. InvalidOperationException: kein übereinstimmender Cluster in der Topologie gefunden.

auf

Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri

eveRegistrarPortFromTopology (Int32& registrarPortNumber)

Test-CsUcwaConference: kein Testbenutzer zugewiesen

\[LyncTest.SelfHost.Corp.Microsoft.com \] . Überprüfen Sie die Konfiguration des Testbenutzers.

In der Reihe: 1 Char: 1

\+ Test-CsUcwaConference-TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"

\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

\+ CategoryInfo: ResourceUnavailable: (:) \[ Test-CsUcwaConference\]

, InvalidOperationException

\+ FullyQualifiedErrorId: NotFoundTestUsers, Microsoft. RTC. Management. Synth

eticTransactions.TestUcwaConferenceCmdlet

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Im folgenden werden einige häufige Gründe aufgeführt, warum das **Testen von csreplica "** möglicherweise fehlschlägt:

  - Möglicherweise liegt ein größeres Problem mit dem Replikations-Agent und den zentralisierten Protokollierungs-Agent-Diensten vor.

  - Die erforderlichen Ports sind möglicherweise nicht in der Windows-Firewall geöffnet.

  - Die erforderlichen Active Directory und lokale Computersicherheitsgruppen sind möglicherweise nicht vorhanden.

</div>

</div>

<span> </span>

</div>

</div>

</div>

