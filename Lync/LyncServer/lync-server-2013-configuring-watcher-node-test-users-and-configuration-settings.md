---
title: Konfigurieren von Testbenutzern und Einstellungen für Watcher-Knoten
TOCTitle: Konfigurieren von Testbenutzern und Einstellungen für Watcher-Knoten
ms:assetid: ab00e9cb-f539-4aa6-bcb4-5533fbe7bc44
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205152(v=OCS.15)
ms:contentKeyID: 49295051
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von Testbenutzern und Einstellungen für Watcher-Knoten

 

_**Letztes Änderungsdatum des Themas:** 2013-07-29_

Nachdem Sie den Computer konfiguriert haben, der als Watcher-Knoten agieren wird, müssen Sie die folgenden Schritte ausführen:

1.  Erstellen Sie die von diesen Watcher-Knoten zu verwendenden Testkonten. Wenn Sie die Aushandlungsauthentifizierungsmethode verwenden, müssen Sie auch das Cmdlet [Set-CsTestUserCredential](https://docs.microsoft.com/en-us/powershell/module/skype/) verwenden, um die Verwendung dieser Testkonten auf dem Watcher-Knoten zu aktivieren.

2.  Aktualisieren Sie die Konfigurationseinstellungen für den Watcher-Knoten.

In diesem Abschnitt werden folgende Themen behandelt:

  - Konfigurieren von Testbenutzerkonten

  - Konfigurieren eines einfachen Watcher-Knotens mit den synthetischen Standardtransaktionen

  - Konfigurieren erweiterter Tests

  - Hinzufügen und Entfernen synthetischer Transaktionen

  - Anzeigen und Testen der Konfiguration des Watcher-Knotens

## Konfigurieren von Testbenutzerkonten

Testbenutzer müssen keinen echten Personen entsprechen, es muss sich dabei jedoch um gültige Konten für die Active Directory-Domänendienste handeln; zudem müssen diese Konten für Lync Server 2013 aktiviert sein, sie müssen gültige SIP-Adressen haben, und sie sollten für Enterprise-VoIP aktiviert sein (für die Verwendung der synthetischen Transaktion "Test-CsPstnPeerToPeerCall"). Wenn Sie die TrustedServer-Authentifizierungsmethode verwenden, müssen Sie lediglich sicherstellen, dass diese Konten vorhanden sind und gemäß den Angaben in diesem Dokument konfiguriert wurden. Sie sollten für jeden zu testenden Pool mindestens drei Testbenutzer zuweisen.

Wenn Sie die Aushandlungsauthentifizierungsmethode verwenden, müssen Sie auch das Cmdlet **Set-CsTestUserCredential** und die Lync Server-Verwaltungsshell verwenden, damit diese Testkonten ordnungsgemäß mit den synthetischen Transaktionen verwendet werden können. Dazu können Sie einen Befehl ausführen, der dem Folgenden ähnelt. (Bei diesen Befehlen wird davon ausgegangen, dass die drei Active Directory-Benutzerkonten bereits erstellt wurden und dass diese Konten für Lync Server 2013 aktiviert sind.):

    Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"

Beachten Sie, dass Sie zusätzlich zur SIP-Adresse auch den Benutzernamen und das Kennwort einfügen müssen. Wenn Sie das Kennwort nicht einfügen, werden Sie von "Set-CsTestUserCredential" zur Eingabe dieser Informationen aufgefordert. Der Benutzername kann im oben gezeigten Format "Domänenname\\Benutzername" oder mithilfe des Formats "Benutzername@Domänenname" angegeben werden, z. B.:

    -UserName "watcher3@litwareinc.com"

Wenn Sie sicherstellen möchten, dass die Testbenutzeranmeldeinformationen erstellt wurden, führen Sie in der Lync Server-Verwaltungsshell die folgenden Befehle aus:

    Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"

Daraufhin sollten für jeden Benutzer Informationen zurückgegeben werden, die den Folgenden ähneln:

    UserName                        Password
    --------                        --------
    Litwareinc\watcher1              System.Security.SecureString

## Konfigurieren eines einfachen Watcher-Knotens mit den synthetischen Standardtransaktionen

Nachdem die Testbenutzer erstellt wurden, können Sie mithilfe eines Befehls, der dem Folgenden ähnelt, einen Watcher-Knoten erstellen:

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}

Mithilfe dieses Befehls wird ein neuer Watcher-Knoten erstellt, für den die Standardeinstellungen verwendet werden und der die Standardgruppe synthetischer Transaktionen ausführt. Für den neuen Watcher-Knoten werden zudem die Testbenutzer "watcher1@litwareinc.com", "watcher2@litwareinc.com" und "watcher3@litwareinc.com" verwendet. Wenn der Watcher-Knoten die TrustedServer-Authentifizierung verwendet, kann es sich bei den drei Testkonten um beliebige gültige Benutzerkonten handeln, die für Active Directory und Lync Server aktiviert sind. Wenn der Watcher-Knoten die Aushandlungsauthentifizierungsmethode verwendet, müssen Sie diese Benutzerkonten auch für den Watcher-Knoten aktivieren, indem Sie das Cmdlet **Set-CsTestUserCredential** verwenden.

## Konfigurieren erweiterter Tests

Wen Sie den PSTN-Test (Public Switched Telephone Network, Telefonfestnetz) aktivieren möchten, mit dessen Hilfe die Verbindung mit dem Telefonfestnetz überprüft wird, müssen Sie beim Einrichten des Watcher-Knotens einige zusätzliche Konfigurationsschritte ausführen. Zuerst müssen Sie die Testbenutzer dem PSTN-Testtyp zuweisen. Führen Sie dazu in der Lync Server-Verwaltungsshell einen Befehl aus, der dem Folgenden ähnelt:

    $pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN

Beachten Sie, dass die Ergebnisse dieses Befehls in einer Variable gespeichert werden müssen. In diesem Beispiel handelt es sich dabei um die Variable "$pstnTest".

An dieser Stelle können Sie das Cmdlet **New-CsWatcherNodeConfiguration** verwenden, um den Testtyp (in der Variable "$pstnTest" gespeichert) einem Lync Server 2013-Pool zuzuweisen. Mithilfe des folgenden Befehls wird beispielsweise eine neue Watcher-Knotenkonfiguration für den Pool "atl-cs-001.litwareinc.com" erstellt, wobei die drei zuvor erstellten Testbenutzer und der PSTN-Testtyp hinzugefügt werden:

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}

Beachten Sie, dass der zuvor angeführte Befehl einen Fehler zurückgibt, wenn Sie die Lync Server-Hauptdateien und die RTCLocal-Datenbank nicht auf dem Computer des Watcher-Knotens installiert haben.

Wenn Sie mehrere VoIP-Richtlinien testen möchten, müssen Sie für alle Richtlinien mithilfe des Cmdlets **New-CsExtendedTest** einen erweiterten Test erstellen. Die diesem Test zugewiesenen Benutzer müssen mit den gewünschten VoIP-Richtlinien konfiguriert werden. Anschließend werden die erweiterten Tests mithilfe eines Befehls, der dem Folgenden ähnelt, an das Cmdlet **New-CsWatcherNodeConfiguration** übergeben:

    -ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}

Wenn "New-CsWatcherNodeConfiguration" ohne den Parameter "Tests" aufgerufen wird, bedeutet dies, dass für den neuen Watcher-Knoten nur die synthetischen Standardtransaktionen (und die angegebene erweiterte synthetische Transaktion) aktiviert werden. Demnach testet der Watcher-Knoten die folgenden Komponenten:

  - Registrierung

  - Instant Messaging

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

  - DataConference

  - XmppIM

  - UnifiedContactStore

## Hinzufügen und Entfernen synthetischer Transaktionen

Nachdem ein Watcher-Knoten konfiguriert wurde, können Sie dem Knoten mithilfe des Cmdlets **Set-CsWatcherNodeConfiguration** synthetische Transaktionen hinzufügen oder Knoten daraus entfernen. Wenn Sie beispielsweise dem Watcher-Knoten den Test "PersistentChatMessage" hinzufügen möchten, verwenden Sie die Add-Methode und einen Befehl, der dem Folgenden ähnelt:

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}

Sie können mehrere Tests hinzufügen, indem Sie die Testnamen durch Kommas voneinander trennen. Beispiel:

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}

Beachten Sie, dass ein Fehler auftritt, wenn einer oder mehrere dieser Tests (z. B. "DataConference") bereits für den Watcher-Knoten aktiviert wurden. In diesem Fall erhalten Sie eine Fehlermeldung, die der Folgenden ähnelt:

    Set-CsWatcherNodeConfiguration: Für den Schlüssel "urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName" oder eine eindeutige Identitätseinschränkung ist die doppelte Schlüsselsequenz "DataConference" vorhanden.

Wenn dieser Fehler auftritt, werden keine Änderungen wirksam. Führen Sie den Befehl erneut aus, nachdem Sie den doppelten Test entfernt haben.

Wenn Sie eine synthetische Transaktion aus einem Watcher-Knoten entfernen möchten, verwenden Sie anstelle der Add-Methode die Remove-Methode. Mithilfe des folgenden Befehls wird beispielsweise der ABWQ-Test aus einem Watcher-Knoten entfernt:

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}

Sie können auch die Replace-Methode verwenden, um alle momentan aktivierten Tests durch einen oder mehrere neue Tests zu ersetzen. Wenn Sie beispielsweise möchten, dass ein Watcher-Knoten nur den IM-Test ausführt, können Sie dieses Verhalten mithilfe des folgenden Befehls konfigurieren:

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}

Wenn Sie den zuvor aufgeführten Befehl ausführen, werden mit Ausnahme von IM alle synthetischen Transaktionen für den angegebenen Watcher-Knoten deaktiviert.

## Anzeigen und Testen der Konfiguration des Watcher-Knotens

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


> [!TIP]
> Wenn Sie die synthetischen Transaktionen in alphabetischer Reihenfolge anzeigen möchten, verwenden Sie stattdessen den folgenden Befehl:<BR>Get-CsWatcherNodeConfiguration –Identity "atl-cs-001.litwareinc.com" | Select-Object –ExpandProperty Tests | Sort-Object



Wenn Sie überprüfen möchten, ob ein Watcher-Knoten erstellt wurde, geben Sie in der Lync Server-Verwaltungsshell den folgenden Befehl ein:

    Get-CsWatcherNodeConfiguration

Daraufhin werden Informationen zurückgegeben, die den Folgenden ähneln:

    Identity      : atl-cs-001.litwareinc.com
    TestUsers     : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}
    ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}
    TargetFqdn    : atl-cs-001.litwareinc.com
    PortNumber    : 5061

Wenn Sie überprüfen möchten, ob der Watcher-Knoten ordnungsgemäß konfiguriert wurde, geben Sie in der Lync Server-Verwaltungsshell den folgenden Befehl ein:

    Test-CsWatcherNodeConfiguration

Mithilfe des vorherigen Befehls werden alle Watcher-Knoten in Ihrer Bereitstellung getestet, und Sie erhalten Informationen zu Folgendem:

  - Ob die erforderliche Registrar-Rolle installiert wurde.

  - Ob der erforderliche Registrierungsschlüssel für Sie erstellt wurde, als Sie "Set-CsWatcherNodeConfiguration" ausgeführt haben.

  - Ob auf Ihren Servern die richtige Version von Lync Server ausgeführt wird.

  - Ob Ihre Ports ordnungsgemäß konfiguriert wurden.

  - Ob die zugewiesenen Testbenutzer über die erforderlichen Anmeldeinformationen verfügen.

