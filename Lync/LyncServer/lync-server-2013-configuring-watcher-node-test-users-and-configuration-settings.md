---
title: Konfigurieren von Watcher-Knotentest Benutzern und Konfigurationseinstellungen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring watcher node test users and configuration settings
ms:assetid: ab00e9cb-f539-4aa6-bcb4-5533fbe7bc44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205152(v=OCS.15)
ms:contentKeyID: 48185048
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d446934e8d84a12a6eecd84fbc94a956d8ae95e8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839158"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-watcher-node-test-users-and-configuration-settings-in-lync-server-2013"></a>Konfigurieren von Watcher-Knotentest Benutzern und Konfigurationseinstellungen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-07-29_

Nachdem Sie den Computer konfiguriert haben, der als Watcher-Knoten agieren wird, müssen Sie die folgenden Schritte ausführen:

1.  Erstellen Sie die Testkonten, die von diesen Watcher-Knoten verwendet werden sollen. Wenn Sie die Aushandlungsauthentifizierungsmethode verwenden, müssen Sie auch das Cmdlet [Set-CsTestUserCredential](https://technet.microsoft.com/en-us/library/JJ205341(v=OCS.15)) verwenden, um die Verwendung dieser Testkonten auf dem Watcher-Knoten zu aktivieren.

2.  Aktualisieren Sie die Konfigurationseinstellungen für den Watcher-Knoten.

In diesem Abschnitt werden folgende Themen behandelt:

  - Konfigurieren von Test Benutzerkonten

  - Konfigurieren eines Basis Überwachungs Knotens mit den standardmäßigen synthetischen Transaktionen

  - Konfigurieren erweiterter Tests

  - Hinzufügen und Entfernen synthetischer Transaktionen

  - Anzeigen und Testen der Konfiguration des Watcher-Knotens

<div>

## <a name="configuring-test-user-accounts"></a>Konfigurieren von Test Benutzerkonten

Test Benutzer müssen keine tatsächlichen Personen darstellen, Sie müssen jedoch gültige Active Directory-Domänendienstkonten sein. Darüber hinaus müssen diese Konten für lync Server 2013 aktiviert sein, Sie müssen über gültige SIP-Adressen verfügen und für Enterprise-VoIP aktiviert sein (um die synthetische Test-CsPstnPeerToPeerCall-Transaktion zu verwenden). Wenn Sie die TrustedServer-Authentifizierungsmethode verwenden, müssen Sie lediglich sicherstellen, dass diese Konten vorhanden sind und wie hier angegeben konfiguriert wurden. Sie sollten für jeden zu testenden Pool mindestens drei Testbenutzer zuweisen.

Wenn Sie die Negotiate-Authentifizierungsmethode verwenden, müssen Sie auch das Cmdlet " **festlegen-CsTestUserCredential** " und die lync Server-Verwaltungsshell verwenden, damit diese Testkonten mit den synthetischen Transaktionen funktionieren. Sie können dies tun, indem Sie einen Befehl wie den folgenden ausführen. (Bei diesen Befehlen wird davon ausgegangen, dass die drei Active Directory-Benutzerkonten bereits erstellt wurden und diese Konten für lync Server 2013 aktiviert wurden.):

    Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"

Beachten Sie, dass Sie nicht nur die SIP-Adresse, sondern auch den Benutzernamen und das Kennwort angeben müssen. Wenn Sie das Kennwort nicht angeben, werden Sie von CsTestUserCredential zur Eingabe dieser Informationen aufgefordert. Der Benutzername kann mit dem oben gezeigten\\Domänennamen-Benutzernamenformat oder mithilfe des Formats User Name @ Domain Name angegeben werden. Zum Beispiel:

    -UserName "watcher3@litwareinc.com"

Um zu überprüfen, ob die Anmeldeinformationen des Testbenutzers erstellt wurden, führen Sie diese Befehle in der lync Server-Verwaltungsshell aus:

    Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"

Ähnliche Informationen sollten für jeden Nutzer zurückgegeben werden:

    UserName                        Password
    --------                        --------
    Litwareinc\watcher1              System.Security.SecureString

</div>

<div>

## <a name="configuring-a-basic-watcher-node-with-the-default-synthetic-transactions"></a>Konfigurieren eines Basis Überwachungs Knotens mit den standardmäßigen synthetischen Transaktionen

Nachdem die Testbenutzer erstellt wurden, können Sie einen Watcher-Knoten erstellen, indem Sie einen ähnlichen Befehl wie den folgenden verwenden:

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}

Mithilfe dieses Befehls wird ein neuer Watcher-Knoten erstellt, für den die Standardeinstellungen verwendet werden und der die Standardgruppe synthetischer Transaktionen ausführt. Für den neuen Watcher-Knoten werden zudem die Testbenutzer watcher1@litwareinc.com, watcher2@litwareinc.com und watcher3@litwareinc.com verwendet. Wenn der Watcher-Knoten die TrustedServer-Authentifizierung verwendet, können die drei Testkonten alle gültigen Benutzerkonten sein, die für Active Directory und lync Server aktiviert sind. Wenn der Watcher-Knoten die Negotiate-Authentifizierungsmethode verwendet, müssen Sie diese Benutzerkonten für Watcher-Knoten auch mithilfe des Cmdlets " **festlegen-CsTestUserCredential** " aktivieren.

</div>

<div>

## <a name="configuring-extended-tests"></a>Konfigurieren erweiterter Tests

Wenn Sie das öffentlich geschaltete Telefonnetz (PSTN-Test) aktivieren möchten, das die Konnektivität mit dem öffentlich geschalteten Telefonnetz überprüft, müssen Sie beim Einrichten des Watcher-Knotens einige zusätzliche Einstellungen vornehmen. Zunächst müssen Sie die Testbenutzer dem PSTN-Testtyps zuordnen. Führen Sie dazu in der lync Server-Verwaltungsshell einen ähnlichen Befehl wie den folgenden aus:

    $pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN

Beachten Sie, dass die Ergebnisse dieses Befehls in einer Variablen gespeichert werden müssen. In diesem Beispiel handelt es sich um eine Variable mit dem Namen $pstnTest.

An diesem Punkt können Sie das Cmdlet **New-CsWatcherNodeConfiguration** verwenden, um den in der Variablen $pstnTest gespeicherten Testtyp einem lync Server 2013-Pool zuzuordnen. Mit dem folgenden Befehl wird beispielsweise eine neue Watcher-Knoten Konfiguration für den Pool ATL-CS-001.litwareinc.com erstellt, wobei die drei zuvor erstellten Testbenutzer hinzugefügt und auch der PSTN-Testtyp hinzugefügt wurde:

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}

Beachten Sie, dass der vorhergehende Befehl fehlschlägt, wenn Sie die lync Server Core-Dateien und die RTCLocal-Datenbank auf dem Watcher-Knoten Computer nicht installiert haben.

Um mehrere VoIP-Richtlinien zu testen, müssen Sie mit dem Cmdlet **New-CsExtendedTest** einen erweiterten Test für jede Richtlinie erstellen. Die diesem Test zugewiesenen Benutzer sollten mit den gewünschten VoIP-Richtlinien konfiguriert sein. Die erweiterten Tests werden dann mithilfe eines Befehls, der der folgenden ähnelt, an das Cmdlet **New-CsWatcherNodeConfiguration** übergeben:

    -ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}

Wenn New-CsWatcherNodeConfiguration ohne Verwendung des Parameters Tests aufgerufen wird, bedeutet dies, dass nur die synthetischen Standardtransaktionen (und die angegebene erweiterte synthetische Transaktion) für den neuen Watcher-Knoten aktiviert werden. Dies bedeutet, dass der Watcher-Knoten die folgenden Komponenten testet:

  - Registrierung

  - IM

  - GroupIM

  - P2PAV (Peer-zu-Peer-Audio/Videositzungen)

  - AvConference (Audio/Konferenzen)

  - Anwesenheit

  - ABS (Adressbuchdienst)

  - ABWQ (Adressbuchwebdienst)

  - PSTN (PSTN-Gateway-Aufrufe, als erweiterter Test angegeben. Standardmäßig ist PSTN deaktiviert. Der Test ist in diesem Fall nur aktiviert, weil der Befehl PSTN mithilfe des ExtendedTests-Parameters aktiviert hat.)

Das bedeutet auch, dass die folgenden Komponenten nicht standardmäßig getestet werden:

  - AVEdgeConnectivity

  - MCXP2PIM (Instant Messaging für mobile Geräte)

  - ExumConnectivity (Exchange Unified Messaging)

  - JoinLauncher

  - PersistentChatMessage

  - DataConference

  - XmppIM

  - UnifiedContactStore

</div>

<div>

## <a name="adding-and-removing-synthetic-transactions"></a>Hinzufügen und Entfernen synthetischer Transaktionen

Nachdem ein Watcher-Knoten konfiguriert wurde, können Sie das Cmdlet " **CsWatcherNodeConfiguration** " verwenden, um synthetische Transaktionen vom Knoten hinzuzufügen oder daraus zu entfernen. Wenn Sie beispielsweise dem Watcher-Knoten den Test PersistentChatMessage hinzufügen möchten, verwenden Sie die Add-Methode und einen Befehl, der dem Folgenden ähnelt:

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}

Sie können mehrere Tests hinzufügen, indem Sie die Testnamen durch Kommas voneinander trennen. Beispiel:

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}

Beachten Sie, dass ein Fehler auftritt, wenn ein oder mehrere dieser Tests (beispielsweise dataconference) bereits auf dem Watcher-Knoten aktiviert sind. In diesem Fall erhalten Sie eine Fehlermeldung, die der Folgenden ähnelt:

    Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.

Wenn dieser Fehler auftritt, werden keine Änderungen wirksam. Der Befehl sollte erneut ausgeführt werden, wenn der doppelte Test entfernt wurde.

Wenn Sie eine synthetische Transaktion von einem Watcher-Knoten entfernen möchten, verwenden Sie die Remove-Methode anstelle der Add-Methode. Mithilfe des folgenden Befehls wird beispielsweise der ABWQ-Test aus einem Watcher-Knoten entfernt:

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}

Sie können auch die Replace-Methode verwenden, um alle derzeit aktivierten Tests durch einen oder mehrere neue Tests zu ersetzen. Wenn Sie beispielsweise nur einen Watcher-Knoten zum Ausführen des im-Tests verwenden möchten, können Sie diesen mithilfe dieses Befehls konfigurieren:

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}

Wenn Sie den vorhergehenden Befehl ausführen, werden alle synthetischen Transaktionen auf dem angegebenen Watcher-Knoten mit Ausnahme von Chat deaktiviert.

</div>

<div>

## <a name="viewing-and-testing-the-watcher-node-configuration"></a>Anzeigen und Testen der Konfiguration des Watcher-Knotens

Wenn Sie die Tests anzeigen möchten, die einem Watcher-Knoten zugewiesen wurden, verwenden Sie einen Befehl, der dem Folgenden ähnelt:

    Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests

Der vorhergehende Befehl gibt je nach den synthetischen Transaktionen, die dem Knoten zugewiesen wurden, ähnliche Informationen zurück:

    Registration
    IM
    GroupIM
    P2PAV
    AvConference
    Presence
    PersistentChatMessage
    DataConference

<div>


> [!TIP]
> Wenn Sie die synthetischen Transaktionen in alphabetischer Reihenfolge anzeigen möchten, verwenden Sie stattdessen den folgenden Befehl:<BR>Get-CsWatcherNodeConfiguration – Identity "ATL-CS-001.litwareinc.com" | Select-Object – expando-Tests | Sortieren-Objekt



</div>

Um zu überprüfen, ob ein Watcher-Knoten erstellt wurde, geben Sie in der lync Server-Verwaltungsshell den folgenden Befehl ein:

    Get-CsWatcherNodeConfiguration

Sie erhalten ähnliche Informationen:

    Identity      : atl-cs-001.litwareinc.com
    TestUsers     : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}
    ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}
    TargetFqdn    : atl-cs-001.litwareinc.com
    PortNumber    : 5061

Um zu überprüfen, ob der Watcher-Knoten ordnungsgemäß konfiguriert wurde, geben Sie in der lync Server-Verwaltungsshell den folgenden Befehl ein:

    Test-CsWatcherNodeConfiguration

Mit dem vorhergehenden Befehl wird jeder Watcher-Knoten in Ihrer Bereitstellung getestet und Ihnen Informationen mitgeteilt, beispielsweise ob:

  - Die erforderliche Registrierungsstelle-Rolle wurde installiert.

  - Der erforderliche Registrierungsschlüssel wurde für Sie erstellt, als Sie "Satz-CsWatcherNodeConfiguration" ausgeführt haben.

  - Auf Ihren Servern wird die richtige Version von lync Server ausgeführt.

  - Ihre Ports sind ordnungsgemäß konfiguriert.

  - Ihre zugewiesenen Testbenutzer verfügen über die erforderlichen Anmeldeinformationen.

</div>

</div>

<span> </span>

</div>

</div>

</div>

