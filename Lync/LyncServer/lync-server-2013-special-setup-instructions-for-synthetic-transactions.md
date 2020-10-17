---
title: 'Lync Server 2013: spezielle Einrichtungsanweisungen für synthetische Transaktionen'
description: 'Lync Server 2013: spezielle Einrichtungsanweisungen für synthetische Transaktionen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Special setup instructions for synthetic transactions
ms:assetid: 694cbe05-5dba-4035-a01c-c87ebfb0478b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688080(v=OCS.15)
ms:contentKeyID: 49733676
ms.date: 11/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e288a9d7f15f4b84df591d152a912509c77129a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551321"
---
# <a name="special-setup-instructions-for-synthetic-transactions-in-lync-server-2013"></a>Spezielle Einrichtungsanweisungen für synthetische Transaktionen in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2015-11-16_

Die meisten synthetischen Transaktionen können auf einem Watcher-Knoten ohne größere Umstände ausgeführt werden. Das bedeutet, sobald eine synthetische Transaktion den Konfigurationseinstellungen des Watcher-Knotens hinzugefügt wurde, kann sie vom Watcher-Knoten bei seinen Testdurchläufen eingesetzt werden. Allerdings gilt dies nicht für alle synthetischen Transaktionen. Für welche synthetischen Transaktionen spezielle Einrichtungsschritte erforderlich sind, wird in den nächsten Abschnitten erklärt.

<div>

## <a name="dealing-with-server-timeout-errors"></a>Umgang mit Server Timeout Fehlern

In einigen Fällen können Sie feststellen, dass Ihre synthetischen Transaktionen mit Servertimeout Fehlern fehlschlagen (Fehlercode 504). Diese Fehler sind in der Regel auf Firewall-Probleme zurückzuführen. Wenn eine synthetische Transaktion ausgeführt wird, wird diese Transaktion im MonitoringHost.exe Prozess ausgeführt. MonitoringHost.exe startet wiederum eine Instanz des PowerShell.exe-Prozesses. Wenn entweder MonitoringHost.exe oder PowerShell.exe von Ihrer Firewall blockiert wird, tritt bei der synthetischen Transaktion ein Fehler auf, und es wird ein 504-Fehler generiert.

Um dieses Problem zu beheben, sollten Sie manuell eingehende Firewallregeln für MonitoringHost.exe und PowerShell.exe auf dem lokalen Computer erstellen. Dies kann in Abhängigkeit von der bereits vorhandenen Konfiguration des Servers über die Windows-Firewall oder eine lokale Firewallsoftware eines Drittanbieters erfolgen.

Wenn Sie ein Netzwerkfirewall-Gerät zwischen dem Hostcomputer der synthetischen Transaktion und den lync-Servern verwenden, die Sie überwachen möchten, sollten Sie den Host als Clientcomputer behandeln und alle Firewall-Portanforderungen von [Ports und Protokollen für interne Server in lync Server 2013](lync-server-2013-ports-and-protocols-for-internal-servers.md)beobachten.

</div>

<div>

## <a name="data-conferencing-synthetic-transactions"></a>Synthetische Transaktion für Datenkonferenzen

Wenn sich der Monitor Knoten Computer außerhalb des Umkreisnetzwerks befindet, können Sie die synthetische Datenkonferenz-Transaktion möglicherweise nur ausführen, wenn Sie zuerst die Internet Explorer Proxyeinstellungen für das Netzwerkdienstkonto deaktiviert haben. Gehen Sie dazu wie folgt vor:

1.  Klicken Sie auf dem Computer mit den Watcher-Knoten auf **Start**, **Alle Programme**, **Zubehör**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und klicken Sie dann auf **Als Administrator ausführen**.

2.  Geben Sie in dem Konsolenfenster den folgenden Befehl ein, und drücken Sie anschließend die EINGABETASTE:
    
        bitsadmin /util /SetIEProxy NetworkService NO_PROXY

Die folgende Meldung wird im Befehlsfenster angezeigt:

    BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.
    
    Internet proxy settings for account NetworkService set to NO_PROXY. 
    (connection = default)

Diese Meldung bedeutet, dass Sie die Internet Explorer Proxyeinstellungen für das Netzwerkdienstkonto deaktiviert haben.

</div>

<div>

## <a name="exchange-unified-messaging-synthetic-transactions"></a>Synthetische Transaktionen für Exchange Unified Messaging

Die Exchange Unified Messaging (um) synthetische Transaktion überprüft, ob Testbenutzer eine Verbindung mit Voicemail-Konten herstellen können, die in Exchange verwaltet werden. Diese Testbenutzer müssen mit Voicemail-Konten vorkonfiguriert werden, bevor sie die Exchange-UM-Tests verwenden können.

</div>

<div>

## <a name="persistent-chat-synthetic-transactions"></a>Synthetische Transaktionen für beständigen Chat

Um die synthetische persistent Chat-Transaktion zu verwenden, müssen Administratoren zunächst einen Kanal erstellen und den Testbenutzern Berechtigungen zur Verwendung geben. Das Cmdlet [Test-cspersistentchatmessage "](https://docs.microsoft.com/powershell/module/skype/Test-CsPersistentChatMessage) kann verwendet werden, um diese Testbenutzer ordnungsgemäß zu konfigurieren:

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress sip:kenmyer@litwareinc.com -SenderCredential $cred1 -ReceiverSipAddress sip:pilar@litwareinc.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:kenmyer@litwareinc.com -TestUser2SipAddress sip:pilar@litwareinc.com -Setup $True

Diese Einrichtungsaufgabe muss auf einem Computer innerhalb des Unternehmens durchgeführt werden:

  - Wenn das Cmdlet auf einem Computer ausgeführt wird, der kein Server ist, muss der entsprechende Benutzer bei rollenbasierter Zugriffssteuerung (RBAC) Mitglied der Rolle "PersistentChatAdministrators" sein.

  - Wenn das Cmdlet auf dem Server selbst ausgeführt wird, sollte der entsprechende Benutzer Mitglied der Gruppe "RTCUniversalServerAdmins" sein.

In dem oben gezeigten Befehl wurde der Parameter "Setup" eingefügt und auf "True" ($True) festgelegt. Wenn Sie den Parameter Setup einschließen, erstellt Test-CsPersistentChatMessage einen speziellen beständigen Chatroom und füllt diesen Raum mit den Testbenutzern auf. Dadurch soll sichergestellt werden, dass tatsächlich ein Chatroom für Testzwecke verfügbar ist. Beachten Sie, dass der Setup-Parameter nur von einem Front-End-Server ausgeführt werden sollte.

Der per Test-CsPersistentChatMessage erstellte Chatroom kann nur von einem Administrator gelöscht werden.

</div>

<div>

## <a name="pstn-peer-to-peer-call-synthetic-transactions"></a>Synthetische Transaktionen für Peer-zu-Peer-Festnetzanrufe

Die synthetische [Test-CsPstnPeerToPeerCall-](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) Transaktion überprüft die Möglichkeit, Anrufe über das Telefon Festnetz (Public Switched Telephone Network, PSTN) zu tätigen und zu empfangen.

Zum Ausführen dieser synthetischen Transaktion müssen Administratoren Folgendes konfigurieren:

  - Zwei Testbenutzer (ein Anrufer und ein Empfänger), die für Enterprise-VoIP aktiviert sind.

  - DID-Nummern (Direct Inward Dialing) für jedes Benutzerkonto

  - VoIP-Richtlinien und -Routen, über die Anrufer mit der Nummer des Empfängers das PSTN-Gateway erreichen

  - Ein PSTN-Gateway, das Anrufe entgegennimmt, und Medien, die Anrufe anhand der gewählten Nummer zurück zum Homepool des Empfängers leiten

</div>

<div>

## <a name="unified-contact-store-synthetic-transactions"></a>Synthetische Transaktionen für den einheitlichen Kontaktspeicher

Die synthetische Transaktion des einheitlichen Kontaktspeichers überprüft, ob lync Server 2013 Kontakte im Namen eines Benutzers aus Microsoft Exchange Server 2013 abrufen kann.

Für die Verwendung dieser synthetischen Transaktionen müssen die folgenden Bedingungen erfüllt sein:

  - Die [Verwaltung der Server-zu-Server-Authentifizierung (OAuth) und der Partneranwendungen in lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) muss zwischen lync Server 2013 und Exchange 2013 konfiguriert werden.

  - Test Benutzer müssen über ein gültiges Exchange 2013 Postfach verfügen.

Wenn diese Bedingungen erfüllt sind, können Administratoren mit dem folgenden Befehl überprüfen, ob der Benutzer mit der SIP-Adresse "kenmyer@litwareinc.com" seine Kontakte aus dem einheitlichen Kontaktspeicher abrufen kann:

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer -Setup

Beachten Sie die Verwendung des Setup-Parameters im oben gezeigten Befehl. Bei Ausführung des Test-CsUnifiedContactStore mit diesem Parameter werden die Kontakte des angegebenen Benutzers (in diesem Fall: sip:kenmyer@litwareinc.com) in den einheitlichen Kontaktspeicher verschoben (falls sie sich nicht bereits dort befinden). (Selbstverständlich, wenn sich die Kontakte des Benutzers bereits im einheitlichen Kontaktspeicher befinden, müssen Sie nicht verschoben werden.) Der Setup-Parameter wird in der Regel nur einmal verwendet (das erste Mal Test-CsUnifiedContactStore ausgeführt wird) und sollte nur mit Testbenutzern verwendet werden; Das heißt, mit Benutzerkonten, die nie tatsächlich bei lync Server angemeldet werden. Nachdem Ihre Testbenutzer zum einheitlichen Kontaktspeicher migriert wurden, können Sie durch Aufruf von Test-CsUnifiedContactStore ohne Setup-Parameter überprüfen, ob die Kontakte des Benutzers abgerufen werden können:

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer

</div>

<div>

## <a name="xmpp-synthetic-transactions"></a>Synthetische XMPP-Transaktionen

Für die synthetischen XMPP-IM-Transaktionen (Extensible Messaging and Presence Protocol) ist es erforderlich, dass die XMPP-Funktion mit einer oder mehreren Verbunddomänen konfiguriert ist.

Zum Aktivieren der synthetischen XMPP-Transaktion muss der Parameter "XmppTestReceiverMailAddress" mit einem Benutzerkonto bei einer routingfähigen XMPP-Domäne angegeben werden. Beispiel:

    Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com

In diesem Beispiel muss eine lync Server 2013-Regel vorhanden sein, um Nachrichten für litwareinc.com an ein XMPP-Gateway weiterzuleiten.

</div>

</div>

<span> </span>

</div>

</div>

</div>

