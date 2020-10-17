---
title: 'Lync Server 2013: Testen des Zugriffs auf den einheitlichen Kontaktspeicher'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Unified Contact Store access
ms:assetid: 761f46bd-2e14-4f40-82b9-afa1eaa816b0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727309(v=OCS.15)
ms:contentKeyID: 63969621
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5552c03ac18ddd373385674da03d872ce89eb585
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503902"
---
# <a name="testing-unified-contact-store-access-in-lync-server-2013"></a>Testen des Zugriffs auf den einheitlichen Kontaktspeicher in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2015-05-15_


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
<p>Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets <strong>Test-CsUnifiedContactStore</strong> verfügt. Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUnifiedContactStore&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Der in lync Server 2013 eingeführte einheitliche Kontaktspeicher bietet Administratoren die Möglichkeit, die Kontakte eines Benutzers in Microsoft Exchange Server 2013 anstatt in lync Server zu speichern. Dadurch kann der Benutzer neben lync 2013 auf denselben Satz Kontakte in Outlook Web Access zugreifen. (Oder Sie können Kontakte weiterhin in lync Server speichern. In diesem Fall müssen die Benutzer zwei getrennte Kontaktsätze verwalten: eine für die Verwendung mit Outlook und Outlook Web Access und eine für die Verwendung mit lync 2013.)

Sie können ermitteln, ob die Kontakte eines Benutzers in den einheitlichen Kontaktspeicher verschoben wurden, indem Sie das Cmdlet **Test-CsUnifiedContactStore** ausführen. Das Cmdlet **Test-CsUnifiedContactStore** übernimmt das angegebene Benutzerkonto, stellt eine Verbindung mit dem einheitlichen Kontaktspeicher her und versucht, einen Kontakt für den Benutzer abzurufen. Wenn keine Kontakte abgerufen werden können, wird der Befehl zusammen mit der Meldung "keine Kontakte für den Benutzer empfangen" fehl. Stellen Sie sicher, dass Kontakte für den Benutzer vorhanden sind.".

Beachten Sie, dass das **Test-CsUnifiedContactStore-** Cmdlet einen Fehler aufweist, wenn der Benutzer erfolgreich zum einheitlichen Kontaktspeicher migriert wurde, aber keine Kontakte in seiner Kontaktliste hat. Der angegebene Benutzer muss mindestens über einen Kontakt verfügen, damit das Cmdlet **Test-CsUnifiedContactStore** erfolgreich abgeschlossen werden konnte.

</div>

<div>

## <a name="running-the-test"></a>Durchführen des Tests

Die im folgenden Beispiel gezeigten Befehle bestimmen, ob Kontakte für den Benutzer litwareinc \\ kenmyer im einheitlichen Kontaktspeicher gefunden werden können. Dazu wird im ersten Befehl des Beispiels das Cmdlet **Get-Credential** verwendet, um ein Windows PowerShell-Objekt der Befehlszeilen-Schnittstellen Anmeldeinformationen für den Benutzer litwareinc \\ kenmyer zu erstellen. Beachten Sie, dass Sie das Kennwort für dieses Konto angeben müssen, um ein gültiges Credentials-Objekt zu erstellen und sicherzustellen, dass das **Test-CsUnifiedContactStore-** Cmdlet seine Überprüfung ausführen kann.

Der zweite Befehl in diesem Beispiel verwendet das angegebene Credentials-Objekt ($x) und die SIP-Adresse des Benutzers litwareinc \\ kenmyer, um zu ermitteln, ob seine Kontakte im einheitlichen Kontaktspeicher gefunden werden können.

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsUnifiedContactStore -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>Bestimmen des Erfolgs oder Fehlers

Wenn der Zugriff auf den Kontaktspeicher ordnungsgemäß konfiguriert ist, erhalten Sie eine ähnliche Ausgabe, wobei die Result-Eigenschaft als Success markiert ist **:**

Ziel-FQDN: ATL-CS-001.litwareinc.com

Ergebnis: Success

Wartezeit: 00:00:14.9862716

Fehlermeldung:

Diagnose

Wenn der Zugriff auf den Kontaktspeicher nicht ordnungsgemäß konfiguriert ist, wird das Ergebnis als **Fehler**angezeigt, und in den Eigenschaften Error und Diagnostic werden zusätzliche Informationen aufgezeichnet:

Warnung: Fehler beim Lesen der Registrierungs Portnummer für die angegebene vollqualifizierte

Domänenname (FQDN). Verwenden der standardmäßigen Registrierungsstellen-Portnummer. Ausnahme

System. InvalidOperationException: kein übereinstimmender Cluster in der Topologie gefunden.

auf

Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri

eveRegistrarPortFromTopology (Int32& registrarPortNumber)

Ziel-FQDN: ATL-CS-001.litwareinc.com

Ergebnis: Fehler

Wartezeit: 00:00:00

Fehlermeldung: 10060, ein Verbindungsversuch ist fehlgeschlagen, da die verbundene Partei

nach einem bestimmten Zeitraum nicht ordnungsgemäß reagiert oder

Fehler bei hergestellter Verbindung, da der verbundene Host

Fehler beim Antworten auf 10.188.116.96:5061

Innere Ausnahme: ein Verbindungsversuch ist fehlgeschlagen, da die

die verbundene Partei hat nach einer bestimmten Zeit nicht ordnungsgemäß reagiert.

Zeit oder Fehler bei hergestellter Verbindung, weil verbundener Host

Fehler beim Antworten auf 10.188.116.96:5061

Diagnose

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Im folgenden werden einige häufige Gründe aufgeführt, warum das **Testen von CsUnifiedContactStore** möglicherweise fehlschlägt:

  - Ein falscher Parameterwert wurde angegeben. Wenn die optionalen Parameter verwendet werden, müssen Sie ordnungsgemäß konfiguriert sein, oder der Test kann nicht ausgeführt werden. Führen Sie den Befehl ohne die optionalen Parameter erneut aus, und überprüfen Sie, ob dies erfolgreich ist.

  - Die Verbindung mit dem einheitlichen Kontaktspeicher ist fehlgeschlagen, und der Versuch, einen Kontakt für den Benutzer abzurufen, war nicht möglich. Möglicherweise treten Netzwerkverbindungsprobleme auf.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[New-csuserservicespolicy "](https://docs.microsoft.com/powershell/module/skype/New-CsUserServicesPolicy)  
[Gruppe-csuserservicespolicy "](https://docs.microsoft.com/powershell/module/skype/Set-CsUserServicesPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

