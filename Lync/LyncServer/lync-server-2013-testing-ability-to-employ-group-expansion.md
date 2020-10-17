---
title: 'Lync Server 2013: Testen der Fähigkeit zur Verwendung der Gruppenerweiterung'
description: 'Lync Server 2013: Testen der Fähigkeit zur Verwendung der Gruppenerweiterung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to employ group expansion
ms:assetid: 9b0fc954-6f9c-411a-ab32-94ebabc42de2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743836(v=OCS.15)
ms:contentKeyID: 63969634
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6267bc2099fc420c5c57e1ef80f4bf4491334938
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560791"
---
# <a name="testing-ability-to-employ-group-expansion-in-lync-server-2013"></a>Testen der Möglichkeit zur Verwendung der Gruppenerweiterung in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-06-05_


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
<p>Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsGroupExpansion-Cmdlets verfügt. Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupExpansion&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Mit dem Test-CsGroupExpansion-Cmdlet können Sie bestimmen, ob die Gruppenerweiterung in Ihrer Organisation funktioniert. Wenn die Gruppenerweiterung aktiviert ist, konfigurieren Benutzer Verteilergruppen als Kontakt. Das bedeutet, dass diese Benutzer dann dieselbe Sofortnachricht an alle Gruppenmitglieder senden können, indem Sie die Nachricht an die Gruppe anstatt an einzelne Mitglieder dieser Gruppe adressieren. Mit Gruppenerweiterung können Sie mühelos alle Gruppenmitglieder und ihren aktuellen Status anzeigen.

Mit dem Test-CsGroupExpansion-Cmdlet geben Sie eine Active Directory Verteilergruppe mithilfe der e-Mail-Adresse der Gruppe an. Test-CsGroupExpansion verwendet dann die Gruppenerweiterung, um die Gruppenmitgliedschaft abzurufen und die abgerufene Liste mit der Mitgliedschaft der von Ihnen angegebenen Gruppen-e-Mail-Adresse zu vergleichen. Stimmen die beiden Listen überein, funktioniert die Gruppenerweiterung ordnungsgemäß. Beachten Sie, dass Sie die Gruppenerweiterung auf zwei Arten testen können: durch Testen des Diensts selbst oder durch Testen des zugeordneten Webdiensts.

Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) .

</div>

<div>

## <a name="running-the-test"></a>Durchführen des Tests

Das Test-CsGroupExpansion-Cmdlet kann entweder mit einem vorkonfigurierten Test Konto ausgeführt werden (siehe Einrichten von Testkonten zum Ausführen lync Server Tests) oder nach dem Konto eines beliebigen Benutzers, der für lync Server aktiviert wurde. Um diese Prüfung mit einem Test Konto auszuführen, müssen Sie lediglich den FQDN des getesteten lync Server Pools und die e-Mail-Adresse für eine gültige Verteilergruppe angeben. Zum Beispiel:

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com"

Um diese Prüfung mit einem tatsächlichen Benutzerkonto auszuführen, müssen Sie zuerst ein lync Server Credentials-Objekt erstellen, das den Kontonamen und das Kennwort enthält. Anschließend müssen Sie das Credentials-Objekt und die dem Konto zugewiesene SIP-Adresse hinzufügen, wenn das System Test-CsGroupExpansion aufruft:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Bestimmen des Erfolgs oder Fehlers

Wenn der angegebene Benutzer die Gruppenerweiterung verwenden kann, erhalten Sie eine ähnliche Ausgabe, wobei die Result-Eigenschaft als **Success** markiert ist:

TargetUri https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

TargetFqdn: ATL-CS-001.litwareinc.com

Ergebnis: Success

Wartezeit: 00:00:01.1234976

Fehler

Diagnose

Wenn der angegebene Benutzer keine Gruppenerweiterung verwenden kann, wird das Ergebnis als Fehler angezeigt, und zusätzliche Informationen werden in den Eigenschaften Error und Diagnostic aufgezeichnet:

TargetUri https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

TargetFqdn: ATL-CS-001.litwareinc.com

Ergebnis: Fehler

Wartezeit: 00:00:00

Fehler

Diagnose

Test-CsGroupExpansion: der Endpunkt konnte sich nicht registrieren. Lesen Sie den ErrorCode aus einem bestimmten Grund.

In der vorherigen Ausgabe wird angegeben, dass der Test fehlgeschlagen ist, da sich der angegebene Benutzer nicht bei lync Server registrieren konnte. Dies tritt normalerweise auf, wenn das Testkonto nicht vorhanden ist oder für lync Server nicht aktiviert ist. Sie können sicherstellen, dass das Konto vorhanden ist, und bestimmen, ob das Konto für nm-OCS-14-3rd aktiviert wurde, indem Sie einen Befehl wie den folgenden ausführen:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

Wenn Test-CsGroupExpansion fehlschlägt, möchten Sie möglicherweise den Test erneut ausführen, dieses Mal einschließlich des Parameters verbose:

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -Verbose

Wenn der Verbose-Parameter enthalten ist Test-CsGroupExpansion gibt eine Schritt-für-Schritt-Konto für jede Aktion zurück, die versucht wurde, als die Möglichkeit des angegebenen Benutzers geprüft wurde, sich bei lync Server anzumelden. Diese Ausgabe gibt beispielsweise an, dass die angegebene Verteilergruppe nicht gefunden werden konnte:

Das Abrufen von webtickets wird versucht.

Webdienst-URL: https://atl-cs-001.litwareinc.com:443/WebTicket/WebTicketService.svc

Verwenden von NTLM/Kerb-Authentifizierung.

GetWebTicketActivity abgeschlossen.

"VerifyDistributionList"-Aktivität wurde gestartet.

Der Antwort Status des dlx-Webdiensts lautet: NotFound.

"VerifyDistributionList"-Aktivität wurde in "0,2597923" Sek. abgeschlossen.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Im folgenden werden einige häufige Gründe aufgeführt, aus denen Test-CsGroupExpansion Fehler auftreten können:

  - Sie haben ein ungültiges Benutzerkonto angegeben. Sie können überprüfen, ob ein Benutzerkonto vorhanden ist, indem Sie einen Befehl wie den folgenden ausführen:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - Das Benutzerkonto ist gültig, aber das Konto ist derzeit nicht für lync Server aktiviert. Um zu überprüfen, ob ein Benutzerkonto für lync Server aktiviert wurde, führen Sie einen Befehl wie den folgenden aus:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Wenn die Enabled-Eigenschaft auf false festgelegt ist, bedeutet dies, dass der Benutzer derzeit nicht für lync Server aktiviert ist.

  - Die Gruppenerweiterung ist möglicherweise deaktiviert. Die Gruppenerweiterung kann deaktiviert werden. Wenn die Gruppenerweiterung deaktiviert wurde, tritt beim Test-CsGroupExpansion-Cmdlet ein Fehler auf. Verwenden Sie einen Befehl wie den folgenden, um festzustellen, ob die Gruppenerweiterung aktiviert ist:
    
        Get-CsWebServiceConfiguration | Select-Object Identity, EnableGroupExpansion

</div>

</div>

<span> </span>

</div>

</div>

</div>

