---
title: Konfigurieren von Testbenutzern und Einstellungen für Watcher-Knoten
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
description: 'Zusammenfassung: Konfigurieren von Testbenutzerkonten und Watcher-Knoteneinstellungen für Skype for Business Server synthetische Transaktionen.'
ms.openlocfilehash: 77e742940b75845e67a48bddb2c19a4450b289e2
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58580069"
---
# <a name="skype-for-business-server-configure-watcher-node-test-users-and-settings"></a>Skype for Business Server: Konfigurieren von Testbenutzern und Einstellungen für Watcher-Knoten
 
**Zusammenfassung:** Konfigurieren Sie Testbenutzerkonten und Watcher-Knoteneinstellungen für Skype for Business Server synthetische Transaktionen.
  
Nachdem Sie den Computer konfiguriert haben, der als Watcher-Knoten agieren wird, müssen Sie die folgenden Schritte ausführen:
  
1. [Konfigurieren Sie Testbenutzerkonten,](test-users-and-settings-2019.md#testuser) die von diesen Monitorknoten verwendet werden sollen. Wenn Sie die Aushandlungsauthentifizierungsmethode verwenden, müssen Sie auch das Cmdlet **Set-CsTestUserCredential** verwenden, um die Verwendung dieser Testkonten auf dem Watcher-Knoten zu aktivieren.
    
2. Aktualisieren Sie die Konfigurationseinstellungen für den Watcher-Knoten.
    
## <a name="configure-test-user-accounts"></a>Konfigurieren von Testbenutzerkonten
<a name="testuser"> </a>

Testkonten müssen keine tatsächlichen Personen darstellen, aber sie müssen gültige Active Directory-Konten sein. Darüber hinaus müssen diese Konten für Skype for Business Server aktiviert sein, sie müssen über gültige SIP-Adressen verfügen, und sie sollten für Enterprise-VoIP aktiviert sein (um die Test-CsPstnPeerToPeerCall synthetische Transaktion zu verwenden). 
  
Wenn Sie die TrustedServer-Authentifizierungsmethode verwenden, müssen Sie lediglich sicherstellen, dass diese Konten vorhanden sind, und sie wie angegeben konfigurieren. Weisen Sie mindestens drei Testbenutzer für jeden Pool zu, den Sie testen möchten. Wenn Sie die Negotiate-Authentifizierungsmethode verwenden, müssen Sie auch das Cmdlet Set-CsTestUserCredential und die Skype for Business Server-Verwaltungsshell verwenden, damit diese Testkonten mit den synthetischen Transaktionen arbeiten können. Führen Sie dazu einen Befehl aus, der dem folgenden ähnelt (bei diesen Befehlen wird davon ausgegangen, dass die drei Active Directory-Benutzerkonten erstellt wurden und dass diese Konten für Skype for Business Server aktiviert sind):
  
```PowerShell
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"
```

Geben Sie nicht nur die SIP-Adresse an, sondern auch den Benutzernamen und das Kennwort. Wenn Sie das Kennwort nicht angeben, werden Sie vom Cmdlet Set-CsTestUserCredential aufgefordert, diese Informationen einzugeben. Der Benutzername kann mithilfe des Im vorherigen Codeblocks angezeigten Domänennamen-/Benutzernamenformats angegeben werden.
  
Führen Sie die folgenden Befehle aus der Skype for Business Server Verwaltungsshell aus, um zu überprüfen, ob die Anmeldeinformationen des Testbenutzers erstellt wurden:
  
```PowerShell
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"
```

Ähnliche Informationen werden für jeden Benutzer zurückgegeben:
  
|**UserName**|**Password**|
|:-----|:-----|
|Litwareinc\watcher1  <br/> |System.Security.SecureString  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a>Konfigurieren eines einfachen Watcher-Knotens mit den synthetischen Standardtransaktionen

Nachdem die Testbenutzer erstellt wurden, können Sie einen Watcher-Knoten erstellen, indem Sie einen Befehl wie den folgenden verwenden:
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

Mithilfe dieses Befehls wird ein neuer Watcher-Knoten erstellt, für den die Standardeinstellungen verwendet werden und der die Standardgruppe synthetischer Transaktionen ausführt. Für den neuen Watcher-Knoten werden zudem die Testbenutzer "watcher1@litwareinc.com", "watcher2@litwareinc.com" und "watcher3@litwareinc.com" verwendet. Wenn der Watcher-Knoten die TrustedServer-Authentifizierung verwendet, können die drei Testkonten alle gültigen Benutzerkonten sein, die für Active Directory und Skype for Business Server aktiviert sind. Wenn der Watcher-Knoten die Negotiate-Authentifizierungsmethode verwendet, müssen diese Benutzerkonten auch mithilfe des Cmdlets Set-CsTestUserCredential für den Watcher-Knoten aktiviert werden.
  
Führen Sie stattdessen die folgenden Schritte aus, um zu überprüfen, ob die automatische Ermittlung des Zielpools für die Anmeldung korrekt konfiguriert ist, anstatt direkt auf einen Pool zu abzielen:
  
```PowerShell
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a>Konfigurieren erweiterter Tests

Wenn Sie den PSTN-Test aktivieren möchten, der die Konnektivität mit dem Telefonfestnetz überprüft, müssen Sie beim Einrichten des Monitorknotens eine weitere Konfiguration durchführen. Zunächst müssen Sie die Testbenutzer dem PSTN-Testtyp zuordnen, indem Sie einen Befehl wie den folgenden in der Skype for Business Server Verwaltungsshell ausführen:
  
```PowerShell
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> Die Ergebnisse dieses Befehls müssen in einer Variablen gespeichert werden. In diesem Beispiel heißt die Variable $pstnTest. 
  
Als Nächstes können Sie das Cmdlet **"New-CsWatcherNodeConfiguration"** verwenden, um den Testtyp (in der Variablen $pstnTest gespeichert) einem Skype for Business Server Pool zuzuordnen. Mit dem folgenden Befehl wird beispielsweise eine neue Watcher-Knotenkonfiguration für den Pool atl-cs-001.litwareinc.com erstellt, die drei zuvor erstellten Testbenutzer hinzugefügt und der PSTN-Testtyp hinzugefügt:
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

Der vorstehende Befehl schlägt fehl, wenn Sie die Skype for Business Server Kerndateien und die RTCLocal-Datenbank nicht auf dem Monitorknotencomputer installiert haben. 
  
Um mehrere VoIP-Richtlinien zu testen, können Sie mit dem Cmdlet **"New-CsExtendedTest"** einen erweiterten Test für jede Richtlinie erstellen. Die bereitgestellten Benutzer sollten mit den gewünschten VoIP-Richtlinien konfiguriert werden. Die erweiterten Tests werden mithilfe von Kommatrennzeichen an das Cmdlet **New-CsWatcherNodeConfiguration** übergeben, z. B.:
  
-ExtendedTests @{Add=$pstnTest 1,$pstnTest 2,$pstnTest 3}
  
Da das Cmdlet **"New-CsWatcherNodeConfiguration"** aufgerufen wurde, ohne den Parameter "Tests" zu verwenden, werden nur die synthetischen Standardtransaktionen (und die angegebene erweiterte synthetische Transaktion) für den neuen Watcher-Knoten aktiviert. Daher teste der Watcher-Knoten die folgenden Komponenten:
  
- Registrierung
    
- Chat
    
- GroupIM
    
- P2PAV (Peer-zu-Peer-Audio/Videositzungen)
    
- AvConference (Audio/Konferenzen)
    
- Anwesenheit
    
- ABS (Adressbuchdienst)
    
- ABWQ (Adressbuchwebdienst)
    
Die folgenden Komponenten werden nicht standardmäßig getestet:
  
- ASConference
    
- AVEdgeConnectivity
    
- DataConference
    
- DialinConferencing
    
- ExumConnectivity (Exchange Unified Messaging)
    
- JoinLauncher
    
- MCXP2PIM (Instant Messaging für ältere mobile Geräte)
    
- P2PVideoInteropServerSipTrunkAV
    
- PersistentChatMessage
    
- PSTN (PSTN-Gatewayanrufe, angegeben als erweiterter Test)
    
- UcwaConference
    
- UnifiedContactStore
    
- XmppIM
    
### <a name="adding-and-removing-synthetic-transactions"></a>Hinzufügen und Entfernen synthetischer Transaktionen

Nachdem ein Watcher-Knoten konfiguriert wurde, können Sie dem Knoten mithilfe des Cmdlets Set-CsWatcherNodeConfiguration synthetische Transaktionen hinzufügen oder Knoten daraus entfernen. Wenn Sie beispielsweise dem Watcher-Knoten den Test "PersistentChatMessage" hinzufügen möchten, verwenden Sie die Add-Methode und einen Befehl, der dem Folgenden ähnelt:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}
```

Sie können mehrere Tests hinzufügen, indem Sie die Testnamen durch Kommas voneinander trennen. Beispiel:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}
```

Wenn einer oder mehrere dieser Tests (z. B. DataConference) bereits auf dem Monitorknoten aktiviert wurden, tritt ein Fehler auf. In diesem Fall erhalten Sie eine Fehlermeldung, die der folgenden Meldung ähnelt:
  
Set-CsWatcherNodeConfiguration: Es gibt eine doppelte Tastenfolge "DataConference" für "urn:schema:Microsoft.Rtc.Management". Einstellungen. WatcherNode.2010:TestName's key or unique identity constraint.
  
Wenn dieser Fehler auftritt, werden keine Änderungen wirksam. Führen Sie den Befehl erneut aus, nachdem Sie den doppelten Test entfernt haben.
  
Verwenden Sie die Remove -Methode, um eine synthetische Transaktion aus einem Watcher-Knoten zu entfernen. Mithilfe des folgenden Befehls wird beispielsweise der ABWQ-Test aus einem Watcher-Knoten entfernt:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

Sie können die Replace-Methode verwenden, um alle derzeit aktivierten Tests durch einen oder mehrere neue Tests zu ersetzen. Wenn Sie beispielsweise möchten, dass ein Monitorknoten nur den Chattest ausführt, können Sie dies mithilfe des folgenden Befehls konfigurieren:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

Wenn Sie diesen Befehl ausführen, werden alle synthetischen Transaktionen auf dem angegebenen Watcher-Knoten mit Ausnahme von Chatnachrichten deaktiviert.
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a>Anzeigen und Testen der Konfiguration des Watcher-Knotens

Wenn Sie die Tests anzeigen möchten, die einem Monitorknoten zugewiesen wurden, verwenden Sie einen Befehl wie den folgenden:
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

Dieser Befehl gibt Abhängig von den synthetischen Transaktionen, die dem Knoten zugewiesen wurden, Informationen wie die folgenden zurück:
  
Registrierung IM GroupIM P2PAV AvConference Presence PersistentChatMessage DataConference
> [!TIP]
> Wenn Sie die synthetischen Transaktionen in alphabetischer Reihenfolge anzeigen möchten, verwenden Sie stattdessen den folgenden Befehl: 
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

Um zu überprüfen, ob ein Watcher-Knoten erstellt wurde, geben Sie den folgenden Befehl aus der Skype for Business Server Verwaltungsshell ein:
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

Sie erhalten Informationen wie die folgende:
  
Identity : atl-cs-001.litwareinc.com TestUsers : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...} ExtendedTests : {TestUsers=IList<System.String>; Name=PSTN-Test; Te...} TargetFqdn : atl-cs-001.litwareinc.com PortNumber : 5061Zu überprüfen, ob der Watcher-Knoten ordnungsgemäß konfiguriert wurde, geben Sie den folgenden Befehl aus der Skype for Business Server-Verwaltungsshell ein:
  
```PowerShell
Test-CsWatcherNodeConfiguration
```

Mit diesem Befehl werden die einzelnen Watcher-Knoten in Ihrer Bereitstellung getestet und überprüft, ob die folgenden Aktionen abgeschlossen sind:
  
- Die erforderliche Registrierungsstellenrolle ist installiert.
    
- Der erforderliche Registrierungsschlüssel wird erstellt (abgeschlossen, wenn Sie das Cmdlet Set-CsWatcherNodeConfiguration ausgeführt haben)
    
- Auf Ihren Servern wird die richtige Version von Skype for Business Server
    
- Ihre Ports sind ordnungsgemäß konfiguriert
    
- Ihre zugewiesenen Testbenutzer verfügen über die erforderlichen Anmeldeinformationen.
    
## <a name="managing-watcher-nodes"></a>Verwalten von Watcher-Knoten
<a name="testuser"> </a>

Zusätzlich zum Ändern der synthetischen Transaktionen, die auf einem Watcher-Knoten ausgeführt werden, können Sie auch das Cmdlet **"Set-CsWatcherNodeConfiguration"** verwenden, um zwei weitere wichtige Aufgaben auszuführen: Aktivieren und Deaktivieren des Watcher-Knotens und Konfigurieren des Watcher-Knotens, um interne Web-URLs oder externe Web-URLs beim Ausführen der Tests zu verwenden.
  
In der Standardeinstellung führen Watcher-Knoten in regelmäßigen Abständen alle für sie aktivierten synthetischen Transaktionen aus. Manchmal möchten Sie diese Transaktionen jedoch möglicherweise aussetzen. Wenn der Watcher-Knoten zum Beispiel vorübergehend vom Netzwerk getrennt ist, liegt kein Grund vor, dass die synthetischen Transaktionen ausgeführt werden. Ohne Netzwerkkonnektivität schlagen diese Transaktionen fehl. Um einen Watcher-Knoten vorübergehend zu deaktivieren, führen Sie in der Skype for Business Server Verwaltungsshell einen Befehl aus, der dem folgenden ähnelt:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

Mit diesem Befehl wird die Ausführung synthetischer Transaktionen auf dem Watcher-Knoten atl watcher 001.litwareinc.com deaktiviert. Wenn die synthetischen Transaktionen wieder aufgenommen werden sollen, setzen Sie die Eigenschaft "Enabled" wieder zurück auf "True" ($True):
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> Mithilfe der Eigenschaft "Enabled" können Watcher-Knoten ein- und ausgeschaltet werden. Wenn Sie einen Watcher-Knoten dauerhaft löschen möchten, verwenden Sie das **Remove-CsWatcherNodeConfiguration**-Cmdlet:
  
```PowerShell
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

Dieser Befehl entfernt alle Konfigurationseinstellungen des Watcher-Knotens vom angegebenen Computer, wodurch verhindert wird, dass auf dem Computer automatisch synthetische Transaktionen ausgeführt werden. Der Befehl deinstalliert jedoch nicht die System Center Agent-Dateien oder die Skype for Business Server Systemdateien.
  
Standardmäßig verwenden Watcher-Knoten bei der Durchführung von Tests die externen Web-URLs einer Organisation. Watcher-Knoten können jedoch auch für die Verwendung der internen Web-URLs der Organisation konfiguriert werden. Dies ermöglicht es Administratoren, den URL-Zugriff für innerhalb des Umkreisnetzwerks befindliche Benutzer zu überprüfen. Um einen Watcher-Knoten so zu konfigurieren, dass interne URLs anstelle externer URLs verwendet werden, legen Sie die UseInternalWebURls-Eigenschaft auf "True" ($True) fest:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

Wenn Sie diese Eigenschaft auf den Standardwert False ($False) zurücksetzen, verwendet der Watcher erneut die externen URLs:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a>Besondere Anweisungen zum Einrichten von synthetischen Transaktionen
<a name="special_synthetictrans"> </a>

Die meisten synthetischen Transaktionen können auf einem Monitorknoten wie besehen ausgeführt werden. In den meisten Fällen kann der Watcher-Knoten mit der Verwendung dieser synthetischen Transaktion während seiner Testdurchläufe beginnen, sobald die synthetische Transaktion den Konfigurationseinstellungen des Watcher-Knotens hinzugefügt wird. Es gibt jedoch einige synthetische Transaktionen, die spezielle Einrichtungsanweisungen erfordern, wie in den folgenden Abschnitten erläutert.
  
### <a name="data-conferencing-synthetic-transaction"></a>Synthetische Transaktion für Datenkonferenzen

Wenn sich ihr Monitorknotencomputer außerhalb Ihres Umkreisnetzwerks befindet, können Sie die synthetische Transaktion für Datenkonferenzen wahrscheinlich erst ausführen, wenn Sie zuerst die Windows Internet Explorer deaktivieren® Proxyeinstellungen für den Internetbrowser für das Netzwerkdienstkonto, indem Sie die folgenden Schritte ausführen:
  
1. Klicken Sie auf dem Monitorknotencomputer auf **"Start",** klicken Sie auf **"Alle Programme",** klicken Sie auf **"Zubehör",** klicken Sie mit der rechten Maustaste auf **"Eingabeaufforderung"** und dann auf **"Als Administrator ausführen".**
    
2. Geben Sie im Konsolenfenster den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE. 
    
```PowerShell
bitsadmin /util /SetIEProxy NetworkService NO_PROXY
```

Im Befehlsfenster wird die folgende Meldung angezeigt:
  
BITSAdmin ist veraltet und ist nicht garantiert in zukünftigen Versionen von Windows verfügbar. Verwaltungstools für den BITS-Dienst werden jetzt von BITS PowerShell-Cmdlets bereitgestellt.
  
Internetproxyeinstellungen für Konto NetworkService auf NO_PROXY festgelegt. 
  
(Connection = Standard)
  
Diese Meldung gibt an, dass Sie die Internet Explorer-Proxyeinstellungen für das Netzwerkdienstkonto deaktiviert haben.
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a>Exchange Synthetische Unified Messaging-Transaktion

Die synthetische Transaktion Exchange Unified Messaging (UM) überprüft, ob Testbenutzer eine Verbindung mit Voicemailkonten herstellen können, die in Exchange verwaltet werden.
  
Die Testbenutzer müssen mit Voicemailkonten vorkonfiguriert sein. 
  
### <a name="persistent-chat-synthetic-transaction"></a>Synthetische Transaktion für beständigen Chat

Um die synthetische Transaktion für den beständigen Chat zu verwenden, müssen Sie zuerst einen Kanal erstellen und den Testbenutzern Berechtigungen für die Verwendung erteilen.
  
Sie können die synthetische Transaktion für beständigen Chat verwenden, um diesen Kanal zu konfigurieren: 
  
```PowerShell
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true
```

Führen Sie diese Setupaufgabe innerhalb des Unternehmens aus:
  
- Wenn er von einem Computer ausgeführt wird, der kein Server ist, muss der Benutzer, der das Cmdlet ausführt, Mitglied der Rolle "CsPersistentChatAdministrators" für Role-Based Zugriffssteuerung (Access Control, RBAC) sein.
    
- Wenn er vom Server selbst ausgeführt wird, muss der Benutzer, der das Cmdlet ausführt, Mitglied der Gruppe "RTCUniversalServerAdmins" sein.
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a>Synthetische Transaktion für PSTN-Peer-to-Peer-Anrufe

Die Test-CsPstnPeerToPeerCall synthetische Transaktion überprüft die Möglichkeit, Anrufe über ein Telefonfestnetz (Public Switched Telephone Network, PSTN) zu tätigen und zu empfangen.
  
Zum Ausführen dieser synthetischen Transaktion müssen Sie Folgendes konfigurieren:
  
- Zwei UC-fähige Testbenutzer (ein Anrufer und ein Empfänger).
    
- DID-Nummern (Direct Inward Dialing) für jedes Benutzerkonto
    
- VoIP-Richtlinien und VoIP-Routen, mit denen Anrufe an die Nummer des Empfängers das PSTN-Gateway erreichen können.
    
- Ein PSTN-Gateway, das Anrufe und Medien akzeptiert, die Anrufe basierend auf der gewählten Nummer zurück an den Heimpool eines Empfängers weiterleiten.
    
### <a name="unified-contact-store-synthetic-transaction"></a>Synthetische Transaktion für einheitliche Kontakte Store

Der einheitliche Kontakt Store synthetische Transaktion überprüft die Fähigkeit von Skype for Business Server, Kontakte im Namen eines Benutzers aus Exchange abzurufen.
  
Für die Verwendung dieser synthetischen Transaktionen müssen die folgenden Bedingungen erfüllt sein:
  
- Lyss-Exchange Server-zu-Server-Authentifizierung muss konfiguriert werden.
    
- Testbenutzer müssen über ein gültiges Exchange Postfach verfügen.
    
Nachdem diese Bedingungen erfüllt sind, können Sie das folgende cmdlet Windows PowerShell ausführen, um die Kontaktlisten der Testbenutzer zu Exchange zu migrieren:
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

Es kann einige Zeit dauern, bis die Testbenutzerkontaktlisten zu Exchange migriert wurden. Um den Migrationsfortschritt zu überwachen, kann dieselbe Befehlszeile ohne das Flag "-Setup" ausgeführt werden:
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

Diese Befehlszeile ist nach Abschluss der Migration erfolgreich.
  
### <a name="xmpp-synthetic-transaction"></a>Synthetische XMPP-Transaktion

Für die synthetische Transaktion im Extensible Messaging and Presence Protocol (XMPP) müssen Sie das XMPP-Feature mit einer oder mehreren Verbunddomänen konfigurieren.
  
Um die synthetische XMPP-Transaktion zu aktivieren, müssen Sie einen XmppTestReceiverMailAddress-Parameter mit einem Benutzerkonto in einer routingfähigen XMPP-Domäne bereitstellen. Zum Beispiel:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

In diesem Beispiel muss eine Skype for Business Server Regel vorhanden sein, um Nachrichten für litwareinc.com an ein XMPP-Gateway weiterzuleiten.

> [!NOTE]
> XMPP-Gateways und Proxys waren in Skype for Business Server 2015 verfügbar, werden jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Weitere Informationen finden Sie unter [Migrieren des XMPP-Partnerverbunds.](../migration/migrating-xmpp-federation.md)
  
### <a name="video-interop-server-vis-synthetic-transaction"></a>Synthetische Transaktion des Video-Interoperabilität-Servers (VIS)

Für die synthetische Transaktion des Video-Interoperabilität-Servers (VIS) müssen Sie die Unterstützungsdateien für synthetische Transaktionen herunterladen und installieren ([VISSTSupportPackage.msi](https://www.microsoft.com/download/details.aspx?id=46921)). 
  
Um VISSTSupportPackage.msi zu installieren, stellen Sie sicher, dass die Abhängigkeiten (unter Systemanforderungen) für die MSI-Datei bereits installiert sind. Führen Sie VISSTSupportPackage.msi aus, um eine einfache Installation durchzuführen. Das .msi installiert alle Dateien im folgenden Pfad: "%ProgramFiles%\VIS Synthetic Transaction Support Package".
  
Weitere Informationen zum Ausführen der synthetischen VIS-Transaktion finden Sie in der Dokumentation für das Cmdlet ["Test-CsP2PVideoInteropServerSipTrunkAV".](/powershell/module/skype/Test-CsP2PVideoInteropServerSipTrunkAV)
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a>Ändern der Ausführungshäufigkeit für synthetische Transaktionen
<a name="special_synthetictrans"> </a>

Standardmäßig werden synthetische Transaktionen alle 15 Minuten mit den konfigurierten Benutzern ausgeführt. Synthetische Transaktionen werden sequenziell innerhalb einer Gruppe von Benutzern ausgeführt, um zu vermeiden, dass zwei synthetische Transaktionen miteinander in Konflikt stehen. Ein längeres Intervall ist erforderlich, damit alle synthetischen Transaktionen abgeschlossen werden können.
  
Wenn es wünschenswert ist, synthetische Transaktionen häufiger auszuführen, sollte die Anzahl synthetischer Transaktionen, die mit einer bestimmten Gruppe von Benutzern ausgeführt werden, verringert werden, damit die Tests im gewünschten Zeitraum mit einem Puffer für gelegentliche Netzwerkverzögerungen abgeschlossen werden können. Wenn es wünschenswert ist, mehr synthetische Transaktionen auszuführen, erstellen Sie mehr Benutzersätze, um mehr synthetische Transaktionen auszuführen.
  
Führen Sie die folgenden Schritte aus, um die Häufigkeit der Ausführung synthetischer Transaktionen zu ändern:
  
1. Öffnen Sie System Center Operations Manager. Klicken Sie auf "Erstellen". Klicken Sie auf "Regeln" (unter "Erstellen")
    
2. Suchen Sie im Abschnitt "Regeln" die Regel mit dem Namen "Main Synthetic Transaction Runner Performance Collection Rule".
    
3. Klicken Sie mit der rechten Maustaste auf die Regel, und wählen Sie "Außerkraftsetzungen" aus, wählen Sie "Regel überschreiben" und dann "Für alle Objekte der Klasse: Pool-Watcher" aus.
    
4. Wählen Sie im Fenster "Eigenschaften überschreiben" den Parameternamen "Frequency" aus, und legen Sie den Überschreibungswert auf den gewünschten Wert fest.
    
5. Wählen Sie im selben Fenster das Management Pack aus, auf das diese Außerkraftsetzung angewendet werden muss.
    
## <a name="using-rich-logging-for-synthetic-transactions"></a>Verwenden von erweiterter Protokollierung für synthetische Transaktionen
<a name="special_synthetictrans"> </a>

Synthetische Transaktionen sind hilfreich, um Probleme mit dem System zu erkennen. Beispielsweise könnte das Cmdlet Test-CsRegistration Administratoren darauf hinweisen, dass Benutzer Schwierigkeiten hatten, sich bei Skype for Business Server zu registrieren. Möglicherweise sind jedoch weitere Details erforderlich, um die tatsächliche Ursache eines Fehlers zu ermitteln.
  
Aus diesem Grund bieten synthetische Transaktionen umfassende Protokollierung. Mit umfassender Protokollierung werden für jede Aktivität, die eine synthetische Transaktion durchführt, die folgenden Informationen aufgezeichnet:
  
- Die Zeit, zu der die Aktivität gestartet wurde.
    
- Der Zeitpunkt, zu dem die Aktivität abgeschlossen wurde.
    
- Die ausgeführte Aktion (z. B. Erstellen, Beitreten zu einer Konferenz oder Verlassen einer Konferenz, Anmelden bei Skype for Business Server; Senden einer Chatnachricht).
    
- Informative oder ausführliche Meldungen bzw. Warn- oder Fehlermeldungen, die beim Ausführen der Aktivität generiert wurden
    
- SIP-Registrierungsnachrichten.
    
- Ausnahmedatensätze oder Diagnosecodes, die beim Ausführen der Aktivität generiert wurden.
    
- Das Nettoergebnis der Ausführung der Aktivität.
    
Diese Informationen werden bei jeder Ausführung einer synthetischen Transaktion automatisch generiert, aber nicht automatisch angezeigt oder in einer Protokolldatei gespeichert. Wenn Sie eine synthetische Transaktion manuell ausführen, können Sie den Parameter OutLoggerVariable verwenden, um eine Windows PowerShell Variable anzugeben, in der die Informationen gespeichert werden. Von dort aus haben Sie die Möglichkeit, eine von zwei Methoden zum Speichern und/oder Anzeigen von Fehlermeldungen im umfangreichen Protokoll im XML- oder HTML-Format zu verwenden. 
  
Um die Informationen zur Problembehandlung abzurufen, geben Sie den Parameter OutLoggerVariable gefolgt von einem Variablennamen an, den Sie auswählen:
  
```PowerShell
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> : Stellen Sie dem Variablennamen nicht das Zeichen $voran. Verwenden Sie einen Variablennamen wie RegistrationTest (nicht $RegistrationTest). 
  
Wenn Sie diesen Befehl ausführen, wird eine Ausgabe wie die folgende angezeigt:
  
Ziel-Fqdn : atl-cs-001.litwareinc.com Ergebnis: Fehlerlatenz: 00:00:00 Fehlermeldung: Diesem Computer sind keine Zertifikate zugewiesen. Diagnose: Sie können auf viel detailliertere Informationen für diesen Fehler zugreifen als nur auf die hier gezeigte Fehlermeldung. Um auf diese Informationen im HTML-Format zuzugreifen, verwenden Sie einen Befehl ähnlich dem folgenden, um die in der Variablen RegistrationTest gespeicherten Informationen in einer HTML-Datei zu speichern:
  
```PowerShell
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

Alternativ können Sie die XML()-Methode verwenden, um Dateien in einer XML-Datei zu speichern:
  
```PowerShell
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

Sie können diese Dateien mit Windows Internet Explorer, Microsoft Visual Studio oder einer anderen Anwendung anzeigen, die HTML-/XML-Dateien öffnen kann.
  
Synthetische Transaktionen, die innerhalb von System Center Operations Manager ausgeführt werden, generieren diese Protokolldateien automatisch für Fehler. Diese Protokolle werden nicht generiert, wenn die Ausführung fehlschlägt, bevor Skype for Business Server PowerShell die synthetische Transaktion laden und ausführen kann. 
  
> [!IMPORTANT]
> Standardmäßig speichert Skype for Business Server Protokolldateien in einem Ordner, der nicht freigegeben ist. Damit auf diese Protokolle schnell zugegriffen werden kann, sollten Sie diesen Ordner freigeben. Beispiel: \\ atl-watcher-001.litwareinc.com\WatcherNode.
