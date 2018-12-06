---
title: Besondere Anweisungen zum Einrichten von synthetischen Transaktionen
TOCTitle: Besondere Anweisungen zum Einrichten von synthetischen Transaktionen
ms:assetid: 694cbe05-5dba-4035-a01c-c87ebfb0478b
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688080(v=OCS.15)
ms:contentKeyID: 49890778
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Besondere Anweisungen zum Einrichten von synthetischen Transaktionen

 

_**Letztes Änderungsdatum des Themas:** 2015-11-16_

Die meisten synthetischen Transaktionen können auf einem Watcher-Knoten ohne größere Umstände ausgeführt werden. Das bedeutet, sobald eine synthetische Transaktion den Konfigurationseinstellungen des Watcher-Knotens hinzugefügt wurde, kann sie vom Watcher-Knoten bei seinen Testdurchläufen eingesetzt werden. Allerdings gilt dies nicht für alle synthetischen Transaktionen. Für welche synthetischen Transaktionen spezielle Einrichtungsschritte erforderlich sind, wird in den nächsten Abschnitten erklärt.

## Synthetische Transaktion für Datenkonferenzen

Wenn sich Ihr Watcher-Knoten-Computer außerhalb Ihres Umkreisnetzwerks befindet, werden Sie die synthetische Transaktion für Datenkonferenzen wahrscheinlich erst dann ausführen können, nachdem Sie die Internet Explorer-Proxyeinstellungen für das Konto "Netzwerkdienst" deaktiviert haben. Gehen Sie dazu wie folgt vor:

1.  Klicken Sie auf dem Watcher-Knoten-Computer auf **Start**, **Alle Programme** und **Zubehör**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und klicken Sie dann auf **Als Administrator ausführen**.

2.  Geben Sie in dem Konsolenfenster den folgenden Befehl ein, und drücken Sie anschließend die EINGABETASTE:
    
        bitsadmin /util /SetIEProxy NetworkService NO_PROXY

Die folgende Meldung wird im Befehlsfenster angezeigt:

    BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.
    
    Internet proxy settings for account NetworkService set to NO_PROXY. 
    (connection = default)

Diese Meldung bedeutet, dass Sie die Internet Explorer-Proxyeinstellungen für das Konto "Netzwerkdienst" deaktiviert haben.

## Synthetische Transaktionen für Exchange Unified Messaging

Die synthetischen Exchange Unified Messaging (UM)-Transaktionen überprüfen, ob Testbenutzer eine Verbindung zu in Exchange geführten Voicemail-Konten herstellen können. Diese Testbenutzer müssen mit Voicemail-Konten vorkonfiguriert werden, bevor sie die Exchange-UM-Tests verwenden können.

## Synthetische Beständiger Chat-Transaktionen

Für die Verwendung der synthetischen Beständiger Chat-Transaktion müssen Administratoren zuerst einen Kanal erstellen und den Testbenutzern die Berechtigung für dessen Verwendung erteilen. Die korrekte Konfiguration dieser Testbenutzer kann mithilfe des [Test-CsPersistentChatMessage](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsPersistentChatMessage)-Cmdlets erfolgen:

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress sip:kenmyer@litwareinc.com -SenderCredential $cred1 -ReceiverSipAddress sip:pilar@litwareinc.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:kenmyer@litwareinc.com -TestUser2SipAddress sip:pilar@litwareinc.com -Setup $True

Diese Einrichtungsaufgabe muss auf einem Computer innerhalb des Unternehmens durchgeführt werden:

  - Wenn das Cmdlet auf einem Computer ausgeführt wird, der kein Server ist, muss der entsprechende Benutzer bei rollenbasierter Zugriffssteuerung (RBAC) Mitglied der Rolle "PersistentChatAdministrators" sein.

  - Wenn das Cmdlet auf dem Server selbst ausgeführt wird, sollte der entsprechende Benutzer Mitglied der Gruppe "RTCUniversalServerAdmins" sein.

In dem oben gezeigten Befehl wurde der Parameter "Setup" eingefügt und auf "True" ($True) festgelegt. Bei Verwendung des Setup-Parameters erstellt Test-CsPersistentChatMessage einen speziellen Beständiger Chat-Room und füllt ihn mit den Testbenutzern auf. Dadurch soll sichergestellt werden, dass tatsächlich ein Chatroom für Testzwecke verfügbar ist. Beachten Sie, dass der Setup-Parameter nur auf einem Front-End-Server ausgeführt werden sollte.

Der per Test-CsPersistentChatMessage erstellte Chatroom kann nur von einem Administrator gelöscht werden.

## Synthetische Transaktionen für Peer-zu-Peer-Festnetzanrufe

Die synthetische [Test-CsPstnPeerToPeerCall](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsPstnPeerToPeerCall)-Transaktion überprüft, ob es möglich ist, Anrufe über das Festnetz zu tätigen und entgegenzunehmen.

Zum Ausführen dieser synthetischen Transaktion müssen Administratoren Folgendes konfigurieren:

  - Zwei für Enterprise-VoIP aktivierte Testbenutzer (einen Anrufer und einen Empfänger)

  - DID-Nummern (Direct Inward Dialing) für jedes Benutzerkonto

  - VoIP-Richtlinien und -Routen, über die Anrufer mit der Nummer des Empfängers das PSTN-Gateway erreichen

  - Ein PSTN-Gateway, das Anrufe entgegennimmt, und Medien, die Anrufe anhand der gewählten Nummer zurück zum Homepool des Empfängers leiten

## Synthetische Transaktionen für den einheitlichen Kontaktspeicher

Die synthetischen Transaktionen für den einheitlichen Kontaktspeicher überprüfen, ob Lync Server 2013 in der Lage ist, im Namen eines Benutzers Kontakte aus Microsoft Exchange Server 2013 abzurufen.

Für die Verwendung dieser synthetischen Transaktionen müssen die folgenden Bedingungen erfüllt sein:

  - [Verwalten von Server-zu-Server-Authentifizierung (OAuth) und Partneranwendungen](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) muss zwischen Lync Server 2013 und Exchange 2013 konfiguriert sein.

  - Testbenutzer müssen ein gültiges Exchange 2013-Postfach besitzen.

Wenn diese Bedingungen erfüllt sind, können Administratoren mit dem folgenden Befehl überprüfen, ob der Benutzer mit der SIP-Adresse "kenmyer@litwareinc.com" seine Kontakte aus dem einheitlichen Kontaktspeicher abrufen kann:

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer -Setup

Beachten Sie die Verwendung des Setup-Parameters im oben gezeigten Befehl. Bei Ausführung des Test-CsUnifiedContactStore mit diesem Parameter werden die Kontakte des angegebenen Benutzers (in diesem Fall: sip:kenmyer@litwareinc.com) in den einheitlichen Kontaktspeicher verschoben (falls sie sich nicht bereits dort befinden). Der Setup-Parameter wird meist nur ein einziges Mal eingesetzt (beim ersten Ausführen von Test-CsUnifiedContactStore) und sollte nur mit Testbenutzern verwendet werden, d. h. mit Benutzerkonten, die nie wirklich bei Lync Server angemeldet sein werden. Nachdem Ihre Testbenutzer zum einheitlichen Kontaktspeicher migriert wurden, können Sie durch Aufruf von Test-CsUnifiedContactStore ohne Setup-Parameter überprüfen, ob die Kontakte des Benutzers abgerufen werden können:

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer

## Synthetische XMPP-Transaktionen

Für die synthetischen XMPP-IM-Transaktionen (Extensible Messaging and Presence Protocol) ist es erforderlich, dass die XMPP-Funktion mit einer oder mehreren Verbunddomänen konfiguriert ist.

Zum Aktivieren der synthetischen XMPP-Transaktion muss der Parameter "XmppTestReceiverMailAddress" mit einem Benutzerkonto bei einer routingfähigen XMPP-Domäne angegeben werden. Beispiel:

    Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com

In diesem Beispiel muss eine Lync Server 2013-Regel vorhanden sein, die Nachrichten für "litwareinc.com" zu einem XMPP-Gateway routet.

