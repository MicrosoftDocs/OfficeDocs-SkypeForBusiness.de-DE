---
title: Konfigurieren von Testbenutzern und Konfigurationseinstellungen für Watcher-Knoten
description: Konfigurieren von Testbenutzern und Konfigurationseinstellungen für Watcher-Knoten
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring watcher node test users and configuration settings
ms:assetid: ab00e9cb-f539-4aa6-bcb4-5533fbe7bc44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205152(v=OCS.15)
ms:contentKeyID: 48185048
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e39a35d3db6ed80c715c706f4b5766e4b684e39e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542181"
---
# <a name="configuring-watcher-node-test-users-and-configuration-settings-in-lync-server-2013"></a>Konfigurieren von Testbenutzern und Konfigurationseinstellungen für Watcher-Knoten in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-07-29_

Nachdem Sie den Computer konfiguriert haben, der als Watcher-Knoten agieren wird, müssen Sie die folgenden Schritte ausführen:

1.  Erstellen Sie die von diesen Watcher-Knoten zu verwendenden Testkonten. Wenn Sie die Aushandlungsauthentifizierungsmethode verwenden, müssen Sie auch das Cmdlet [Set-CsTestUserCredential](https://technet.microsoft.com/library/JJ205341(v=OCS.15)) verwenden, um die Verwendung dieser Testkonten auf dem Watcher-Knoten zu aktivieren.

2.  Aktualisieren Sie die Konfigurationseinstellungen für den Watcher-Knoten.

In diesem Abschnitt werden folgende Themen behandelt:

  - Konfigurieren von Testbenutzerkonten

  - Konfigurieren eines einfachen Watcher-Knotens mit den synthetischen Standardtransaktionen

  - Konfigurieren erweiterter Tests

  - Hinzufügen und Entfernen synthetischer Transaktionen

  - Anzeigen und Testen der Konfiguration des Watcher-Knotens

<div>

## <a name="configuring-test-user-accounts"></a>Konfigurieren von Testbenutzerkonten

Test Benutzer müssen keine tatsächlichen Personen darstellen, Sie müssen jedoch Active Directory-Domänendienste Konten gültig sein; Darüber hinaus müssen diese Konten für lync Server 2013 aktiviert sein, Sie müssen über gültige SIP-Adressen verfügen und für Enterprise-VoIP aktiviert sein (für die Verwendung der Test-CsPstnPeerToPeerCall synthetischen Transaktion). Wenn Sie die TrustedServer-Authentifizierungsmethode verwenden, müssen Sie lediglich sicherstellen, dass diese Konten vorhanden sind und gemäß den Angaben in diesem  Dokument konfiguriert wurden. Sie sollten für jeden zu testenden Pool mindestens drei Testbenutzer zuweisen.

Wenn Sie die Negotiate-Authentifizierungsmethode verwenden, müssen Sie auch das Cmdlet " **CsTestUserCredential** " und die lync Server-Verwaltungsshell verwenden, damit diese Testkonten mit den synthetischen Transaktionen arbeiten können. Dazu können Sie einen Befehl ausführen, der dem Folgenden ähnelt. (Bei diesen Befehlen wird davon ausgegangen, dass die drei Active Directory Benutzerkonten bereits erstellt wurden und diese Konten für lync Server 2013 aktiviert wurden.):

    Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"

Beachten Sie, dass Sie nicht nur die SIP-Adresse, sondern auch den Benutzernamen und das Kennwort einbeziehen müssen. Wenn Sie das Kennwort nicht einschließen Set-CsTestUserCredential werden Sie zur Eingabe dieser Informationen aufgefordert. Der Benutzername kann mit dem oben aufgeführten Domänennamen \\ -Benutzernamenformat oder mit dem Format User Name@Domain Name angegeben werden; Beispiel:

    -UserName "watcher3@litwareinc.com"

Um sicherzustellen, dass die Testbenutzer Anmeldeinformationen erstellt wurden, führen Sie diese Befehle in der lync Server-Verwaltungsshell aus:

    Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"

Daraufhin sollten für jeden Benutzer Informationen zurückgegeben werden, die den Folgenden ähneln:

    UserName                        Password
    --------                        --------
    Litwareinc\watcher1              System.Security.SecureString

</div>

<div>

## <a name="configuring-a-basic-watcher-node-with-the-default-synthetic-transactions"></a>Konfigurieren eines einfachen Watcher-Knotens mit den synthetischen Standardtransaktionen

Nachdem die Testbenutzer erstellt wurden, können Sie mithilfe eines Befehls, der dem Folgenden ähnelt, einen Watcher-Knoten erstellen:

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}

Mithilfe dieses Befehls wird ein neuer Watcher-Knoten erstellt, für den die Standardeinstellungen verwendet werden und der die Standardgruppe synthetischer Transaktionen ausführt. Für den neuen Watcher-Knoten werden zudem die Testbenutzer "watcher1@litwareinc.com", "watcher2@litwareinc.com" und "watcher3@litwareinc.com" verwendet. Wenn der Watcher-Knoten die TrustedServer-Authentifizierung verwendet, können die drei Testkonten alle gültigen Benutzerkonten sein, die für Active Directory und lync Server aktiviert sind. Wenn der Watcher-Knoten die Aushandlungsauthentifizierungsmethode verwendet, müssen Sie diese Benutzerkonten auch für den Watcher-Knoten aktivieren, indem Sie das Cmdlet **Set-CsTestUserCredential** verwenden.

</div>

<div>

## <a name="configuring-extended-tests"></a>Konfigurieren erweiterter Tests

Wen Sie den PSTN-Test (Public Switched Telephone Network, Telefonfestnetz) aktivieren möchten, mit dessen Hilfe die Verbindung mit dem Telefonfestnetz überprüft wird, müssen Sie beim Einrichten des Watcher-Knotens einige zusätzliche Konfigurationsschritte ausführen. Zuerst müssen Sie die Testbenutzer dem PSTN-Testtyp zuweisen. Führen Sie dazu einen Befehl wie den folgenden aus dem lync Server-Verwaltungsshell aus:

    $pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN

Beachten Sie, dass die Ergebnisse dieses Befehls in einer Variable gespeichert werden müssen. In diesem Beispiel handelt es sich dabei um die Variable "$pstnTest".

Zu diesem Zeitpunkt können Sie das Cmdlet **New-CsWatcherNodeConfiguration** verwenden, um den in der Variablen $pstnTest gespeicherten Testtyp einem lync Server 2013-Pool zuzuordnen. Mithilfe des folgenden Befehls wird beispielsweise eine neue Watcher-Knotenkonfiguration für den Pool "atl-cs-001.litwareinc.com" erstellt, wobei die drei zuvor erstellten Testbenutzer und der PSTN-Testtyp hinzugefügt werden:

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}

Beachten Sie, dass der obige Befehl fehlschlägt, wenn Sie die lync Server Kerndateien und die RTCLocal-Datenbank nicht auf dem Watcher-Knoten Computer installiert haben.

Wenn Sie mehrere VoIP-Richtlinien testen möchten, müssen Sie für alle Richtlinien mithilfe des Cmdlets **New-CsExtendedTest** einen erweiterten Test erstellen. Die diesem Test zugewiesenen Benutzer müssen mit den gewünschten VoIP-Richtlinien konfiguriert werden. Anschließend werden die erweiterten Tests mithilfe eines Befehls, der dem Folgenden ähnelt, an das Cmdlet **New-CsWatcherNodeConfiguration** übergeben:

    -ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}

Wenn "New-CsWatcherNodeConfiguration" ohne den Parameter "Tests" aufgerufen wird, bedeutet dies, dass für den neuen Watcher-Knoten nur die synthetischen Standardtransaktionen (und die angegebene erweiterte synthetische Transaktion) aktiviert werden. Demnach testet der Watcher-Knoten die folgenden Komponenten:

  - Registrierung

  - Chat

  - GroupIM

  - P2PAV (Peer-zu-Peer-Audio/Videositzungen)

  - AvConference (Audio/Konferenzen)

  - Anwesenheit

  - ABS (Adressbuchdienst)

  - ABWQ (Adressbuchwebdienst)

  - PSTN (PSTN-Gatewayanrufe, angegeben als erweiterter Test. PSTN ist standardmäßig deaktiviert. Der Test wird in diesem Fall nur aktiviert, weil der Befehl PSTN mithilfe des Parameters "ExtendedTests" aktiviert hat.)

Dies bedeutet auch, dass die folgenden Komponenten standardmäßig nicht getestet werden:

  - AVEdgeConnectivity

  - MCXP2PIM (Instant Messaging für mobile Geräte)

  - ExumConnectivity (Exchange Unified Messaging)

  - JoinLauncher

  - PersistentChatMessage

  - Dataconference

  - XmppIM

  - UnifiedContactStore

</div>

<div>

## <a name="adding-and-removing-synthetic-transactions"></a>Hinzufügen und Entfernen synthetischer Transaktionen

Nachdem ein Watcher-Knoten konfiguriert wurde, können Sie dem Knoten mithilfe des Cmdlets **Set-CsWatcherNodeConfiguration** synthetische Transaktionen hinzufügen oder Knoten daraus entfernen. Wenn Sie beispielsweise dem Watcher-Knoten den Test "PersistentChatMessage" hinzufügen möchten, verwenden Sie die Add-Methode und einen Befehl, der dem Folgenden ähnelt:

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}

Sie können mehrere Tests hinzufügen, indem Sie die Testnamen durch Kommas voneinander trennen. Beispiel:

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}

Beachten Sie, dass ein Fehler auftritt, wenn einer oder mehrere dieser Tests (z. B. "DataConference") bereits für den Watcher-Knoten aktiviert wurden. In diesem Fall erhalten Sie eine Fehlermeldung, die der Folgenden ähnelt:

    Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.

Wenn dieser Fehler auftritt, werden keine Änderungen wirksam. Führen Sie den Befehl erneut aus, nachdem Sie den doppelten Test entfernt haben.

Wenn Sie eine synthetische Transaktion aus einem Watcher-Knoten entfernen möchten, verwenden Sie anstelle der Add-Methode die Remove-Methode. Mithilfe des folgenden Befehls wird beispielsweise der ABWQ-Test aus einem Watcher-Knoten entfernt:

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}

Sie können auch die Replace-Methode verwenden, um alle momentan aktivierten Tests durch einen oder mehrere neue Tests zu ersetzen. Wenn Sie beispielsweise möchten, dass ein Watcher-Knoten nur den IM-Test ausführt, können Sie dieses Verhalten mithilfe des folgenden Befehls konfigurieren:

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}

Wenn Sie den zuvor aufgeführten Befehl ausführen, werden mit Ausnahme von IM alle synthetischen Transaktionen für den angegebenen Watcher-Knoten deaktiviert.

</div>

<div>

## <a name="viewing-and-testing-the-watcher-node-configuration"></a>Anzeigen und Testen der Konfiguration des Watcher-Knotens

Wenn Sie die Tests anzeigen möchten, die einem Watcher-Knoten zugewiesen wurden, verwenden Sie einen Befehl, der dem Folgenden ähnelt:

    Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests

Mithilfe des zuvor genannten Befehls werden je nach den synthetischen Transaktionen, die dem Knoten zugewiesen wurden, Informationen zurückgegeben, die den Folgenden ähneln:

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
> Wenn Sie die synthetischen Transaktionen in alphabetischer Reihenfolge anzeigen möchten, verwenden Sie stattdessen den folgenden Befehl:<BR>Get-CsWatcherNodeConfiguration –Identity "atl-cs-001.litwareinc.com" | Select-Object –ExpandProperty Tests | Sort-Object



</div>

Um zu überprüfen, ob ein Watcher-Knoten erstellt wurde, geben Sie den folgenden Befehl in der lync Server-Verwaltungsshell ein:

    Get-CsWatcherNodeConfiguration

Daraufhin werden Informationen zurückgegeben, die den Folgenden ähneln:

    Identity      : atl-cs-001.litwareinc.com
    TestUsers     : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}
    ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}
    TargetFqdn    : atl-cs-001.litwareinc.com
    PortNumber    : 5061

Um zu überprüfen, ob der Watcher-Knoten ordnungsgemäß konfiguriert wurde, geben Sie den folgenden Befehl in der lync Server-Verwaltungsshell ein:

    Test-CsWatcherNodeConfiguration

Mithilfe des vorherigen Befehls werden alle Watcher-Knoten in Ihrer Bereitstellung getestet, und Sie erhalten Informationen zu Folgendem:

  - Ob die erforderliche Registrar-Rolle installiert wurde.

  - Ob der erforderliche Registrierungsschlüssel für Sie erstellt wurde, als Sie "Set-CsWatcherNodeConfiguration" ausgeführt haben.

  - Auf Ihren Servern wird die richtige Version von lync Server.

  - Ob Ihre Ports ordnungsgemäß konfiguriert wurden.

  - Ob die zugewiesenen Testbenutzer über die erforderlichen Anmeldeinformationen verfügen.

</div>

</div>

<span> </span>

</div>

</div>

</div>

