---
title: 'Lync Server 2013: spezielle Setupanweisungen für synthetische Transaktionen'
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
ms.openlocfilehash: a15177a3c4548b235bf01a10274168e4a830fad3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731905"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="special-setup-instructions-for-synthetic-transactions-in-lync-server-2013"></a>Spezielle Einrichtungsanweisungen für synthetische Transaktionen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2015-11-16_

Die meisten synthetischen Transaktionen können auf einem Watcher-Knoten ausgeführt werden. Das heißt, sobald die synthetische Transaktion den Konfigurationseinstellungen des Watcher-Knotens hinzugefügt wurde, kann der Watcher-Knoten die synthetische Transaktion während der Testdurchläufe verwenden. Dies gilt allerdings nicht für alle synthetischen Transaktionen. Die Ausnahmen – synthetische Transaktionen, die spezielle Einrichtungsanweisungen erfordern – werden in den folgenden Abschnitten erläutert.

<div>

## <a name="dealing-with-server-timeout-errors"></a>Umgang mit Server Timeout Fehlern

In einigen Fällen stellen Sie möglicherweise fest, dass Ihre synthetischen Transaktionen mit Servertimeout Fehlern fehlschlagen (Fehlercode 504). Diese Fehler sind in der Regel auf Firewall-Probleme zurückzuführen. Wenn eine synthetische Transaktion ausgeführt wird, wird diese Transaktion unter dem Prozess "MonitoringHost. exe" ausgeführt. im Gegenzug startet MonitoringHost. exe eine Instanz des Prozesses "PowerShell. exe". Wenn entweder "MonitoringHost. exe" oder "PowerShell. exe" von Ihrer Firewall blockiert wird, schlägt die synthetische Transaktion fehl, und es wird ein 504-Fehler generiert.

Um dieses Problem zu beheben, sollten Sie die eingehenden Firewallregeln sowohl für MonitoringHost. exe als auch für PowerShell. exe auf dem lokalen Computer manuell erstellen. Dies kann abhängig von der bereits vorhandenen Konfiguration des Servers über die Windows-Firewall oder eine lokale Firewall-Software eines Drittanbieters erfolgen.

Wenn Sie ein Netzwerkfirewall-Gerät zwischen dem synthetischen Transaktions Hostcomputer und den lync-Servern verwenden, die Sie überwachen möchten, sollten Sie den Host als Clientcomputer behandeln und alle Firewall-Portanforderungen aus [Ports und Protokollen für interne Server in lync Server 2013](lync-server-2013-ports-and-protocols-for-internal-servers.md).

</div>

<div>

## <a name="data-conferencing-synthetic-transactions"></a>Synthetische Datenkonferenz Transaktionen

Wenn sich Ihr Watcher-Knoten Computer außerhalb des Umkreisnetzwerks befindet, können Sie die synthetische Datenkonferenz-Transaktion wahrscheinlich nur ausführen, wenn Sie zuerst die Internet Explorer-Proxyeinstellungen für das Netzwerkdienstkonto deaktivieren. Führen Sie die folgenden Schritte aus, um die Proxyeinstellungen für diesen Dienst zu deaktivieren:

1.  Klicken Sie auf dem Watcher-Knoten Computer auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Zubehör**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und klicken Sie dann auf **als Administrator ausführen**.

2.  Geben Sie im Konsolenfenster den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE:
    
        bitsadmin /util /SetIEProxy NetworkService NO_PROXY

Im Befehlsfenster wird die folgende Meldung angezeigt:

    BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.
    
    Internet proxy settings for account NetworkService set to NO_PROXY. 
    (connection = default)

Diese Meldung bedeutet, dass Sie die Internet Explorer-Proxyeinstellungen für das Netzwerkdienstkonto deaktiviert haben.

</div>

<div>

## <a name="exchange-unified-messaging-synthetic-transactions"></a>Synthetische Exchange Unified Messaging-Transaktionen

Die synthetischen Transaktion „Exchange Unified Messaging“ (UM) überprüft, ob Testbenutzer eine Verbindung zu in Exchange geführten Voicemail-Konten herstellen können. Diese Testbenutzer müssen mit Voicemail-Konten vorkonfiguriert sein, bevor Sie die Exchange um-Tests verwenden können.

</div>

<div>

## <a name="persistent-chat-synthetic-transactions"></a>Synthetische Transaktionen für beständigen Chat

Um die synthetische persistent-Chat-Transaktion zu verwenden, müssen Administratoren zunächst einen Kanal erstellen und den Testbenutzern die Berechtigung erteilen, diese zu verwenden. Das Cmdlet [Test-CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Test-CsPersistentChatMessage) kann verwendet werden, um diese Testbenutzer ordnungsgemäß zu konfigurieren:

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress sip:kenmyer@litwareinc.com -SenderCredential $cred1 -ReceiverSipAddress sip:pilar@litwareinc.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:kenmyer@litwareinc.com -TestUser2SipAddress sip:pilar@litwareinc.com -Setup $True

Dieser Einrichtungs Task muss innerhalb des Unternehmens ausgeführt werden:

  - Wenn der Benutzer, der das Cmdlet ausführt, von einem nicht Server basierten Computer ausgeführt wird, muss er Mitglied der Rolle PersistentChatAdministrators für rollenbasierte Zugriffssteuerung sein.

  - Wenn vom Server selbst ausgeführt wird, sollte der Benutzer, der das Cmdlet ausführt, ein Mitglied der RTCUniversalServerAdmins-Gruppe sein.

Im vorhergehenden Befehl wurde der Setup-Parameter aufgenommen und auf true ($true) festgelegt. Wenn Sie den Setup-Parameter einbeziehen, erstellt Test-CsPersistentChatMessage einen speziellen beständigen Chatroom und füllt diesen Raum mit den Testbenutzern auf. Dadurch wird sichergestellt, dass tatsächlich ein Chatroom für Testzwecke zur Verfügung steht. Beachten Sie, dass der Setup-Parameter nur von einem Front-End-Server ausgeführt werden sollte.

Der von Test-CsPersistentChatMessage erstellte Chatroom kann nur von einem Administrator gelöscht werden.

</div>

<div>

## <a name="pstn-peer-to-peer-call-synthetic-transactions"></a>PSTN-Peer-to-Peer-Anruf synthetische Transaktionen

Die synthetische [Test-CsPstnPeerToPeerCall-](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) Transaktion überprüft die Möglichkeit, Anrufe über das öffentlich geschaltete Telefonnetz (PSTN) zu tätigen und zu empfangen.

Zum Ausführen dieser synthetischen Transaktion müssen Administratoren Folgendes konfigurieren:

  - Zwei Testbenutzer (ein Anrufer und ein Empfänger) sind für Enterprise-VoIP aktiviert.

  - DID-Nummern (Direct Inward Dialing) für jedes Benutzerkonto

  - VoIP-Richtlinien und VoIP-Routen, die Anrufe an die Rufnummer des Empfängers ermöglichen, um das PSTN-Gateway zu erreichen.

  - Ein PSTN-Gateway, das Anrufe annimmt, und Medien, die auf der Grundlage der gewählten Nummer Anrufe zurück an den Home-Pool eines Empfängers weiterleiten.

</div>

<div>

## <a name="unified-contact-store-synthetic-transactions"></a>Synthetische Transaktionen im Unified Contact Store

Durch die synthetische Unified Contact Store-Transaktion wird überprüft, ob lync Server 2013 Kontakte für einen Benutzer aus Microsoft Exchange Server 2013 abrufen kann.

Für die Verwendung dieser synthetischen Transaktion müssen die folgenden Bedingungen erfüllt sein:

  - [Das Verwalten der Server-zu-Server-Authentifizierung (OAuth) und der Partneranwendungen in lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) muss zwischen lync Server 2013 und Exchange 2013 konfiguriert sein.

  - Test Benutzer müssen über ein gültiges Exchange 2013-Postfach verfügen.

Nachdem diese Bedingungen erfüllt sind, können Administratoren den folgenden Befehl ausführen, um zu überprüfen, ob der Benutzer mit der SIP-Adresse kenmyer@litwareinc.com seine Kontakte aus dem Unified Contact Store abrufen kann:

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer -Setup

Beachten Sie die Verwendung des im vorhergehenden Befehl verwendeten Setup-Parameters. Wenn der Setup-Parameter beim Ausführen von Test-CsUnifiedContactStore enthalten ist, werden die Kontakte des angegebenen Benutzers (in diesem Fall SIP:kenmyer@litwareinc.com) in den einheitlichen Kontaktspeicher verschoben. (Wenn sich die Kontakte des Benutzers bereits im Unified Contact Store befinden, müssen Sie natürlich nicht verschoben werden.) Der Setup-Parameter wird in der Regel nur einmal verwendet (das erste Mal, wenn Test-CsUnifiedContactStore ausgeführt wird), und sollte nur für Testbenutzer verwendet werden. Das heißt, mit Benutzerkonten, die nie tatsächlich bei lync Server angemeldet sind. Nachdem der Testbenutzer in den einheitlichen Kontaktspeicher migriert wurde, können Sie überprüfen, ob die Kontakte des Benutzers durch Aufrufen von Test-CsUnifiedContactStore ohne den Setup-Parameter abgerufen werden können:

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer

</div>

<div>

## <a name="xmpp-synthetic-transactions"></a>Synthetische XMPP-Transaktionen

Die synthetische Transaktion xmpp (Extensible Messaging and Presence Protocol) erfordert, dass das XMPP-Feature mit mindestens einer Föderationsdomäne konfiguriert wird.

Zum Aktivieren der synthetischen XMPP-Transaktion muss ein XmppTestReceiverMailAddress-Parameter mit einem Benutzerkonto in einer routingfähigen XMPP-Domäne bereitgestellt werden. Beispiel:

    Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com

In diesem Beispiel muss eine lync Server 2013-Regel vorhanden sein, damit Nachrichten für litwareinc.com an ein XMPP-Gateway weitergeleitet werden.

</div>

</div>

<span> </span>

</div>

</div>

</div>

