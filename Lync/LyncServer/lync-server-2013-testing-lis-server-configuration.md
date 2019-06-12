---
title: 'Lync Server 2013: Testen der LIS-Serverkonfiguration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing LIS server configuration
ms:assetid: 6b06e7ab-522f-41a2-878b-e89cd4e3c6da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690129(v=OCS.15)
ms:contentKeyID: 63969614
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e5baed37e4c72da8b8348dab9702b5d22fbbc5e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847494"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-lis-server-configuration-in-lync-server-2013"></a>Testen der LIS-Serverkonfiguration in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-06-05_


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
<p>Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsLisConfiguration-Cmdlets verfügt. Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLisConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Das Cmdlet Test-CsLisConfiguration überprüft Ihre Fähigkeit, den LIS-Webdienst zu kontaktieren. Wenn der Webdienst kontaktiert werden kann, wird der Test als Erfolg betrachtet, unabhängig davon, ob bestimmte Speicherorte gefunden werden können.

</div>

<div>

## <a name="running-the-test"></a>Ausführen des Tests

Das Cmdlet "Test-CsLisConfguration" kann entweder mit einem vorkonfigurierten Test Konto ausgeführt werden (siehe Einrichten von Testkonten zum Ausführen von lync Server-Tests) oder dem Konto eines beliebigen Benutzers, der für lync Server aktiviert ist. Um diese Überprüfung mit einem Testkonto auszuführen, müssen Sie lediglich den FQDN des zu testenden lync-Server Pools angeben. Beispiel:

    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com"

Damit diese Überprüfung mit einem tatsächlichen Benutzerkonto ausgeführt werden kann, müssen Sie zuerst ein Windows PowerShell-Anmeldeinformationsobjekt erstellen, das den Kontonamen und das Kennwort enthält. Sie müssen das Anmeldeinformationen-Objekt und die SIP-Adresse, die dem Konto zugewiesen ist, beim Aufrufen von Test-CsLisConfiguration einfügen:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsLisConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsLisConfiguration) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Ermitteln von Erfolg oder Misserfolg

Wenn der LIS ordnungsgemäß konfiguriert ist, erhalten Sie eine ähnliche Ausgabe, wobei die Eigenschaft Ergebnis als erfolgreich markiert ist **:**

TargetUrihttps://atl-cs-001.litwareinc.com:443/locationinformation/

liservice. svc

TargetFqdn: ATL-CS-001.litwareinc.com

Ergebnis: Erfolg

Latenz: 00:00:06.1616913

Fehler

Diagnose

Wenn sich der angegebene Benutzer nicht anmelden oder sich abmelden kann, wird das Ergebnis als Fehler angezeigt, und weitere Informationen werden in den Eigenschaften Fehler und Diagnose aufgezeichnet:

TargetUri

TargetFqdn: ATL-CS-001.litwareinc.com

Ergebnis: Fehler

Latenz: 00:00:00

Fehler: 11004, der angeforderte Name ist gültig, aber keine Daten der angeforderten

Typ wurde gefunden

Diagnose

Test-CsLisConfiguration: kein übereinstimmender Cluster in der Topologie gefunden.

Die vorherige Ausgabe enthält beispielsweise die Notiz "kein übereinstimmender Cluster in Topologie gefunden". Dies weist in der Regel auf ein Problem mit dem Edgeserver hin: der LIS, der den Edgeserver verwendet, um eine Verbindung mit dem Dienstanbieter herzustellen und Adressen zu überprüfen.

Wenn Test-CsLisConfiguration fehlschlägt, möchten Sie möglicherweise den Test erneut ausführen, wobei dieser Zeitpunkt einschließlich des Verbose-Parameters lautet:

    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Wenn der Verbose-Parameter enthalten ist, gibt Test-CsLisConfiguration eine Schritt-für-Schritt-Konto für jede Aktion zurück, die versucht wurde, als die Möglichkeit des angegebenen Benutzers zur Anmeldung bei lync Server überprüft wurde. Beispiel:

Standortinformationsdienst für Anrufe.

Dienstpfad =https://atl-cs-001.litwareinc.com:443/locationinformation/liservice.svc

Subnet =

BssId = 5

Fahrgestell-Nr =

Port-Nr =

PortIdSubType = undefined Type

Mac

Eine Ausnahme "Standortinformationen-Webdienstanforderung ist mit einem Antwortcode-Item400 fehlgeschlagen." während des Workflows Microsoft. RTC. SyntheticTrsnactions. Workflows. STLisConfigurationWorkflow-Ausführung aufgetreten.

Wenn Sie die vorherige Ausgabe genau untersuchen, sehen Sie, dass das Cmdlet nach dem Versuch, den standortinformationsdienst aufzurufen, fehlgeschlagen ist. Einer der Parameter, die in diesem Aufruf verwendet wurden, war:

BssId = 5

Dies ist kein gültiger Wert für die grundlegende Dienst Satz-ID (BssID). Stattdessen sollte eine BssID wie folgt aussehen:

12-34-56-78-90-ab

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Nachfolgend finden Sie einige häufige Gründe, warum Test-CsLisConfiguration möglicherweise fehlschlägt:

  - Es wurde ein falscher Parameterwert angegeben. Wie im vorherigen Beispiel gezeigt, müssen die optionalen Parameter richtig konfiguriert sein, oder der Test schlägt fehl. Führen Sie den Befehl ohne die optionalen Parameter erneut aus, und überprüfen Sie, ob dies erfolgreich war.

</div>

</div>

<span> </span>

</div>

</div>

</div>

