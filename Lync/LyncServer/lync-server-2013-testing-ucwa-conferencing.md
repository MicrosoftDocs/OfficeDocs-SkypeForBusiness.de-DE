---
title: 'Lync Server 2013: Testen von UCWA-Konferenzen'
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
ms.openlocfilehash: 9496b2a860f0a8272d6eb98df6a2c897aa245ec9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745395"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ucwa-conferencing-in-lync-server-2013"></a>Testen von UCWA-Konferenzen in lync Server 2013

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
<p>Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des <strong>Test-CsUcwaConference-</strong> Cmdlets verfügt. Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUcwaConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Das Cmdlet **Test-CsUcwaConference** überprüft, ob ein paar Testbenutzer mithilfe der Unified Communications Web-API (UCWA) eine Onlinekonferenz planen, daran teilnehmen und dann eine Onlinekonferenz durchführen können. Dazu verwendet das Cmdlet den lync Server Web Ticket-Dienst, um die beiden Testbenutzer zu authentifizieren und bei lync Server zu registrieren. Das Cmdlet startet dann eine Konferenz mit den Anmeldeinformationen des Organisators und fordert den Teilnehmer auf, an der Besprechung teilzunehmen. Nachdem die Besprechung beigetreten ist, überprüft das Cmdlet " **Test-CsUcwaConference** ", ob die Benutzer die folgenden Aktionen ausführen können: Exchange-Sofortnachrichten und leiten von Pools, trennt die Konferenz und hebt die Registrierung der beiden Testbenutzer auf. Die geplante Konferenz wird auch nach Abschluss des Tests gelöscht.

Das Cmdlet **Test-CsUcwaConference** kann auch verwendet werden, um zu ermitteln, ob anonyme Benutzer an Online Konferenzen teilnehmen können.

Beachten Sie, dass das Cmdlet **Test-CsUcwaConference** nicht für einen Microsoft lync Server 2010-Pool ausgeführt werden sollte, es sei denn, UCWA wurde in diesem Pool installiert. Wenn UCWA nicht installiert wurde, tritt beim Aufruf des **Test-CsUcwaConference-** Cmdlets ein Fehler auf.

</div>

<div>

## <a name="running-the-test"></a>Ausführen des Tests

Der in Beispiel 1 gezeigte Befehl überprüft, ob ein paar Testbenutzer an einer UCWA-Konferenz im Pool-ATL-CS-001.litwareinc.com teilnehmen können. Beachten Sie, dass dieser Befehl fehlschlägt, wenn Sie für ATL-CS-001.litwareinc.com keine Konfigurationstest Benutzer für die Integritätsüberwachung vordefiniert haben.

    Test-CsUcwaConference -TargetFqdn "atl-cs-001.litwareinc.com"

Die in Beispiel 2 gezeigten Befehle testen die Möglichkeit eines Paars von Benutzern\\("litwareinc Pilar\\und" litwareinc kenmyer), an einer UCWA Konferenz teilzunehmen. Dazu verwendet der erste Befehl im Beispiel das Cmdlet "Get-Credential", um ein Windows PowerShell-Anmeldeinformationsobjekt für die Befehlszeilenschnittstelle zu erstellen, das den Namen und das Kennwort des Benutzers Pilar Ackerman enthält. (Da der Anmeldename, "litwareinc\\Pilar, als Parameter enthalten war, erfordert das Dialogfeld Windows PowerShell-Anmeldeinformationen nur, dass der Administrator das Kennwort für das Pilar Ackerman-Konto eingegeben hat.) Das resultierende Credentials-Objekt wird dann in einer Variablen mit dem Namen $cred 1 gespeichert. Der zweite Befehl führt dieselbe Aufgabe aus, wobei dieses Mal ein Anmeldeinformationsobjekt für das Ken Myers-Konto zurückgegeben wird.

Wenn die beiden Anmeldeinformationsobjekte in der Hand sind, bestimmt der dritte Befehl im Beispiel, ob die beiden Benutzer an einer UCWA-Konferenz teilnehmen können. Zum Ausführen dieser Aufgabe wird das Cmdlet **Test-CsUcwaConference** zusammen mit den folgenden Parametern aufgerufen: TargetFqdn (der FQDN des registrierungspools); OrganizerSipAddress (die SIP-Adresse für den Besprechungsorganisator); OrganizerCredential (das Windows PowerShell-Objekt, das die Anmeldeinformationen für denselben Benutzer enthält); ParticipantSipAddress (die SIP-Adresse des anderen Testbenutzers); und ParticipantCredential (das Windows PowerShell-Befehlszeilen-Schnittstellenobjekt, das die Anmeldeinformationen für den anderen Benutzer enthält).

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    Test-CsUcwaConference -TargetFqdn atl-cs-001.litwareinc.com -OrganizerSipAddress "sip:pilar@litwareinc.com" -OrganizerCredential $cred1 -ParticipantSipAddress "sip:kenmyer@litwareinc.com" -ParticipantCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a>Ermitteln von Erfolg oder Misserfolg

Wenn Conferencing richtig konfiguriert ist, erhalten Sie eine ähnliche Ausgabe, wobei die Eigenschaft Ergebnis als erfolgreich markiert ist **:**

Ziel-FQDN: ATL-CS-001.litwareinc.com

Ziel-URI: https://LyncTest-SE. LyncTest. SelfHost. Corp.

Microsoft.com:443/CertProv/CertProvisiongService.svc

Ergebnis: Erfolg

Latenz: 00:00:14.9862716

Fehlermeldung:

Diagnose

Wenn die angegebenen Benutzer keine Konferenz verwenden können, wird das Ergebnis als **Fehler**angezeigt, und weitere Informationen werden in den Eigenschaften Fehler und Diagnose aufgezeichnet:

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

Nachfolgend finden Sie einige häufige Gründe, warum **Test-CsUcwaConference** möglicherweise fehlschlägt:

  - Es wurde ein falscher Parameterwert angegeben. Wenn die optionalen Parameter verwendet werden, müssen Sie ordnungsgemäß konfiguriert sein, oder der Test schlägt fehl. Führen Sie den Befehl ohne die optionalen Parameter erneut aus, und überprüfen Sie, ob dies erfolgreich war.

  - Die Möglichkeit zum Durchführen einer Konferenz hängt von der konferenzrichtlinie ab, die dem Benutzer zugewiesen wurde, der die Konferenz organisiert hat (im Fall des **Test-CsUcwaConference-** Cmdlets, bei dem es sich um den Absender handelt). Wenn es dem Organisator nicht gestattet ist, in seiner Besprechung kollaborative Aktivitäten einzubeziehen (Wenn beispielsweise die EnableDataCollaboration-Eigenschaft der konferenzrichtlinie auf "false" festgelegt ist), schlägt das **Test-CsUcwaConference-** Cmdlet fehl.

  - Dieser Befehl schlägt fehl, wenn der Edgeserver falsch konfiguriert oder noch nicht bereitgestellt wurde.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Test-CsASConference](https://docs.microsoft.com/powershell/module/skype/Test-CsASConference)  
[Test-CsDataConference](https://docs.microsoft.com/powershell/module/skype/Test-CsDataConference)  
[Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

