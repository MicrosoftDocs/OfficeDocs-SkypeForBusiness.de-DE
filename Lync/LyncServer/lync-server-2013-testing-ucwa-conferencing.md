---
title: 'Lync Server 2013: Testen von UCWA-Konferenzen'
description: 'Lync Server 2013: Testen von UCWA-Konferenzen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing UCWA conferencing
ms:assetid: 62b3866a-0759-4b1f-99ec-5a68d6a74f00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727306(v=OCS.15)
ms:contentKeyID: 63969610
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37f88a683abb67d55211422fc4dcf45fc1d5c966
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556091"
---
# <a name="testing-ucwa-conferencing-in-lync-server-2013"></a>Testen von UCWA-Konferenzen in lync Server 2013

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
<p>Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets <strong>Test-CsUcwaConference</strong> verfügt. Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUcwaConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Das Cmdlet **Test-CsUcwaConference** überprüft, ob ein paar von Testbenutzern die Planung, Teilnahme und anschließende Durchführung einer Onlinekonferenz mithilfe der Unified Communications Web API (UCWA) durchführen kann. Zu diesem Zwecke verwendet das Cmdlet den lync Server-webticketdienst, um die beiden Testbenutzer zu authentifizieren und Sie mit lync Server zu registrieren. Das Cmdlet startet dann mit den Anmeldeinformationen des Organisators eine Besprechung und lädt den Teilnehmer ein, der Besprechung beizutreten. Nachdem die Besprechung verbunden wurde, überprüft das Cmdlet **Test-CsUcwaConference** , dass die Benutzer solche Dinge wie Exchange-Sofortnachrichten und Durchführen von Pools ausführen können, trennt dann die Konferenz und hebt die Registrierung der beiden Test Benutzer auf. Die geplante Konferenz wird auch gelöscht, wenn der Test abgeschlossen ist.

Das Cmdlet **Test-CsUcwaConference** kann auch verwendet werden, um zu bestimmen, ob anonyme Benutzer Online Konferenzen beitreten können.

Beachten Sie, dass das Cmdlet **Test-CsUcwaConference** nicht für einen Microsoft lync Server 2010 Pool ausgeführt werden sollte, es sei denn, UCWA wurde in diesem Pool installiert. Wenn UCWA nicht installiert wurde, tritt beim Aufruf des **Test-CsUcwaConference-** Cmdlets ein Fehler auf.

</div>

<div>

## <a name="running-the-test"></a>Durchführen des Tests

Der Befehl in Beispiel 1 überprüft, ob zwei Testbenutzer im Pool "atl-cs-001.litwareinc.com" an einer UCWA-Konferenz teilnehmen können. Beachten Sie, dass beim Ausführen des Befehls ein Fehler auftritt, wenn zuvor nicht zwei Testbenutzer für die Zustandsüberwachungskonfiguration für "atl-cs-001.litwareinc.com" festgelegt wurden.

    Test-CsUcwaConference -TargetFqdn "atl-cs-001.litwareinc.com"

Die in Beispiel 2 gezeigten Befehle testen die Fähigkeit eines Benutzer Paares (litwareinc \\ Pilar und litwareinc \\ kenmyer), an einer UCWA Konferenz teilzunehmen. Dazu wird im ersten Befehl des Beispiels das Get-Credential-Cmdlet verwendet, um ein Windows PowerShell-Befehlszeilen-Schnittstellen Anmeldeinformationsobjekt zu erstellen, das den Namen und das Kennwort des Benutzers Pilar Ackerman enthält. (Da der Anmeldename litwareinc \\ Pilar als Parameter angegeben wurde, erfordert das Dialogfeld Windows PowerShell Anmeldeinformationen nur den Administrator, das Kennwort für das Pilar Ackerman-Konto einzugeben.) Das resultierende Credentials-Objekt wird dann in einer Variablen mit dem Namen "$cred 1" gespeichert. Der zweite Befehl hat die gleiche Aufgabe, nur gibt dieser ein Objekt mit Anmeldeinformationen für das Konto "Ken Myer" zurück.

Mit den beiden Anmeldeinformationen-Objekten in der Hand, der dritte Befehl im Beispiel bestimmt, ob die beiden Benutzer an einer UCWA-Konferenz teilnehmen können. Zum Ausführen dieser Aufgabe wird das Cmdlet **Test-CsUcwaConference** zusammen mit den folgenden Parametern aufgerufen: TargetFqdn (FQDN des Registrierungsstellen Pools); OrganizerSipAddress (die SIP-Adresse für den Besprechungsorganisator); OrganizerCredential (das Windows PowerShell-Objekt, das die Anmeldeinformationen für diesen Benutzer enthält); ParticipantSipAddress (die SIP-Adresse für den anderen Testbenutzer); und ParticipantCredential (das Windows PowerShell Befehlszeilen-Schnittstellenobjekt, das die Anmeldeinformationen für den anderen Benutzer enthält).

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    Test-CsUcwaConference -TargetFqdn atl-cs-001.litwareinc.com -OrganizerSipAddress "sip:pilar@litwareinc.com" -OrganizerCredential $cred1 -ParticipantSipAddress "sip:kenmyer@litwareinc.com" -ParticipantCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a>Bestimmen des Erfolgs oder Fehlers

Wenn die Konferenz ordnungsgemäß konfiguriert ist, erhalten Sie eine ähnliche Ausgabe, wobei die Result-Eigenschaft als Success markiert wurde **:**

Ziel-FQDN: ATL-CS-001.litwareinc.com

Ziel-URI: https://LyncTest-SE. LyncTest. SelfHost. Corp.

Microsoft.com:443/CertProv/CertProvisiongService.svc

Ergebnis: Success

Wartezeit: 00:00:14.9862716

Fehlermeldung:

Diagnose

Wenn die angegebenen Benutzer keine Konferenzen verwenden können, wird das Ergebnis als **Fehler**angezeigt, und in den Eigenschaften Error und Diagnostic werden zusätzliche Informationen aufgezeichnet:

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

Im folgenden werden einige häufige Gründe aufgeführt, warum das **Testen von CsUcwaConference** möglicherweise fehlschlägt:

  - Ein falscher Parameterwert wurde angegeben. Wenn die optionalen Parameter verwendet werden, müssen Sie ordnungsgemäß konfiguriert sein, oder der Test kann nicht ausgeführt werden. Führen Sie den Befehl ohne die optionalen Parameter erneut aus, und überprüfen Sie, ob dies erfolgreich ist.

  - Die Möglichkeit zum Durchführen einer Konferenz hängt von der konferenzrichtlinie ab, die dem Benutzer zugewiesen wurde, der die Konferenz organisiert hat (im Fall des **Test-CsUcwaConference-** Cmdlets, also des "Absenders"). Wenn der Organisator keine kollaborativen Aktivitäten in seine Besprechung einschließen darf (Wenn beispielsweise die EnableDataCollaboration-Eigenschaft für die konferenzrichtlinie auf false festgelegt ist), tritt das **Test-CsUcwaConference-** Cmdlet nicht mehr auf.

  - Dieser Befehl schlägt fehl, wenn der Edgeserver falsch konfiguriert oder noch nicht bereitgestellt wurde.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Test-csasconference "](https://docs.microsoft.com/powershell/module/skype/Test-CsASConference)  
[Test-csdataconference "](https://docs.microsoft.com/powershell/module/skype/Test-CsDataConference)  
[Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

