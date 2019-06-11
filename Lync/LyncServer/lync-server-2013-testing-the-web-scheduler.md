---
title: 'Lync Server 2013: Testen des Web Scheduler'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing the Web scheduler
ms:assetid: 58e34058-1afa-42e3-9096-c4ea1954c237
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727304(v=OCS.15)
ms:contentKeyID: 63969603
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: beb4030a87302c8abaaba9418eaba06b831ed8d6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847465"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-web-scheduler-in-lync-server-2013"></a>Testen des Web Scheduler in lync Server 2013

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
<p>Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des <strong>Test-CsWebScheduler-</strong> Cmdlets verfügt. Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebScheduler&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Mit dem Cmdlet **Test-CsWebScheduler** können Sie ermitteln, ob ein bestimmter Benutzer eine Besprechung mit dem Web Scheduler planen kann. Der Web Scheduler ermöglicht es Benutzern, die Outlook nicht ausführen, Onlinebesprechungen zu planen. Diese neue Funktion (mit der Funktionalität des Web Scheduler-Tools, die im Microsoft lync Server 2010 Resource Kit enthalten war) bietet Benutzern unter anderem die folgenden Möglichkeiten:

  - Planen einer neuen Onlinebesprechung

  - Listen Sie alle Besprechungen auf, die er geplant hat.

  - Anzeigen/Ändern einer vorhandenen Besprechung

  - Löschen einer vorhandenen Besprechung

  - Senden einer e-Mail-Einladung an Besprechungsteilnehmer mithilfe eines vorkonfigurierten SMTP-e-Mail-Servers.

  - Teilnehmen an einer vorhandenen Konferenz

</div>

<div>

## <a name="running-the-test"></a>Ausführen des Tests

Im folgenden Beispiel wird der Web Scheduler für den Pool ATL-CS-001.litwareinc.com überprüft. Dieser Befehl funktioniert nur, wenn Testbenutzer für den Pool ATL-CS-001.litwareinc.com definiert sind. Wenn ja, bestimmt der Befehl, ob der erste Testbenutzer eine Onlinebesprechung mit dem Web Scheduler planen kann.

Wenn Testbenutzer nicht definiert sind, schlägt der Befehl fehl, da er nicht weiß, zu welchem Benutzer Sie sich anmelden müssen. Wenn Sie für einen Pool keine Testbenutzer definiert haben, müssen Sie den "usersipaddress"-Parameter und die Anmeldeinformationen des Benutzers einbeziehen, den der Befehl bei der Anmeldung verwenden soll.

    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com"

Die im nächsten Beispiel gezeigten Befehle testen die Fähigkeit eines bestimmten Benutzers ("litwareinc\\kenmeyer), eine Onlinebesprechung mit dem Web Scheduler zu planen. Dazu verwendet der erste Befehl im Beispiel das Cmdlet " **Get-Credential** ", um ein Windows PowerShell-Anmeldeinformationsobjekt für die Befehlszeilenschnittstelle zu erstellen, das den Namen und das Kennwort des Benutzers Ken Meyer enthält. (Da der Anmeldename "litwareinc\\kenmeyer als Parameter enthalten ist, erfordert das Windows PowerShell-Dialogfeld Anmeldeinformationen nur den Administrator, das Kennwort für das Ken Meyer-Konto einzugeben.) Das resultierende Anmeldeinformationsobjekt wird dann in einer Variablen mit dem Namen $cred 1 gespeichert.

Der zweite Befehl überprüft dann, ob dieser Benutzer sich beim Pool ATL-CS-001.litwareinc.com anmelden und eine Onlinebesprechung planen kann. Zum Ausführen dieser Aufgabe wird das Cmdlet **Test-CsWebScheduler** zusammen mit drei Parametern aufgerufen: TargetFqdn (dem FQDN des registrierungspools); UserCredential (das Windows PowerShell-Objekt, das die Benutzeranmeldeinformationen von Pilar Ackerman enthält); und "usersipaddress" (die SIP-Adresse, die den angegebenen Benutzeranmeldeinformationen entspricht).

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>Ermitteln von Erfolg oder Misserfolg

Wenn der Web Scheduler richtig konfiguriert ist, erhalten Sie eine ähnliche Ausgabe, wobei die Eigenschaft Ergebnis als **erfolgreich**markiert ist:

Ziel-FQDN: ATL-CS-001.litwareinc.com

Ziel-URI: https://-ATL-CS-001.litwareinc.com.

litwareinc.com:443/Scheduler

Ergebnis: Erfolg

Latenz: 00:00:00

Fehlermeldung:

Diagnose

Wenn der Web Scheduler nicht richtig konfiguriert ist, wird das Ergebnis als **Fehler**angezeigt, und zusätzliche Informationen werden in den Eigenschaften Fehler und Diagnose aufgezeichnet:

Warnung: Fehler beim Lesen der Registrierungsstellen-Portnummer für die angegebene vollqualifizierte

Domänenname (FQDN). Verwenden der standardmäßigen Registrierungs Portnummer Ausnahme

System. InvalidOperationException: kein übereinstimmender Cluster in der Topologie gefunden.

am

Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri

eveRegistrarPortFromTopology (Int32& registrarPortNumber)

Ziel-FQDN: ATL-CS-001.litwareinc.com

Ziel-URI:

Ergebnis: Fehler

Latenz: 00:00:00

Fehlermeldung: Es wurde kein übereinstimmender Cluster in der Topologie gefunden.

Diagnose

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Nachfolgend finden Sie einige häufige Gründe, warum **Test-CsWebScheduler** möglicherweise fehlschlägt:

  - Es wurde ein falscher Parameterwert angegeben. Wenn die optionalen Parameter verwendet werden, müssen Sie ordnungsgemäß konfiguriert sein, oder der Test schlägt fehl. Führen Sie den Befehl ohne die optionalen Parameter erneut aus, und überprüfen Sie, ob dies erfolgreich war.

  - Dieser Befehl schlägt fehl, wenn der Web Scheduler falsch konfiguriert oder noch nicht bereitgestellt wurde.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Set-CsWebServer](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServer)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

