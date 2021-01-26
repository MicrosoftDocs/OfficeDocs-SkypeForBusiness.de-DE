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
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Zusammenfassung: Konfigurieren von Testbenutzerkonten und Watcher-Knoten-Einstellungen für synthetische Skype for Business Server-Transaktionen.'
ms.openlocfilehash: 6edce666345e4691d8850e5806eedbebc98e3743
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812765"
---
# <a name="configure-watcher-node-test-users-and-settings"></a>Konfigurieren von Testbenutzern und Einstellungen für Watcher-Knoten
 
**Zusammenfassung:** Konfigurieren Sie Testbenutzerkonten und Watcher-Knoten-Einstellungen für synthetische Skype for Business Server-Transaktionen.
  
Nachdem Sie den Computer konfiguriert haben, der als Watcher-Knoten agieren wird, müssen Sie die folgenden Schritte ausführen:
  
1. [Konfigurieren Sie Testbenutzerkonten](test-users-and-settings-2019.md#testuser) für die Verwendung durch diese Watcher-Knoten. Wenn Sie die Aushandlungsauthentifizierungsmethode verwenden, müssen Sie auch das Cmdlet **Set-CsTestUserCredential** verwenden, um die Verwendung dieser Testkonten auf dem Watcher-Knoten zu aktivieren.
    
2. Aktualisieren Sie die Konfigurationseinstellungen für den Watcher-Knoten.
    
## <a name="configure-test-user-accounts"></a>Konfigurieren von Testbenutzerkonten
<a name="testuser"> </a>

Testkonten müssen keine tatsächlichen Personen darstellen, sie müssen jedoch gültige Active Directory-Konten sein. Darüber hinaus müssen diese Konten für Skype for Business Server aktiviert sein, sie müssen über gültige ENTERPRISE-VOIP verfügen und für die Verwendung der synthetischen Transaktion Test-CsPstnPeerToPeerCall aktiviert sein. 
  
Wenn Sie die TrustedServer-Authentifizierungsmethode verwenden, müssen Sie nur sicherstellen, dass diese Konten vorhanden sind, und sie wie erwähnt konfigurieren. Sie sollten für jeden zu testenden Pool mindestens drei Testbenutzer zuweisen. Wenn Sie die Authentifizierungsmethode "Aushandeln" verwenden, müssen Sie auch das Cmdlet Set-CsTestUserCredential und die Skype for Business Server-Verwaltungsshell verwenden, damit diese Testkonten mit synthetischen Transaktionen verwendet werden können. Führen Sie dazu einen Befehl ähnlich dem folgenden aus (bei diesen Befehlen wird davon ausgegangen, dass die drei Active Directory-Benutzerkonten erstellt wurden und diese Konten für Skype for Business Server aktiviert sind):
  
```PowerShell
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"
```

Sie müssen nicht nur die SIP-Adresse, sondern auch den Benutzernamen und das Kennwort angeben. Wenn Sie das Kennwort nicht angeben, werden Sie vom Set-CsTestUserCredential aufgefordert, diese Informationen einzugeben. Der Benutzername kann im Format "Domänenname\Benutzername" im vorherigen Codeblock angegeben werden.
  
Führen Sie die folgenden Befehle in der Skype for Business Server-Verwaltungsshell aus, um zu überprüfen, ob die Anmeldeinformationen des Testbenutzers erstellt wurden:
  
```PowerShell
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"
```

Informationen wie diese werden für jeden Benutzer zurückgegeben:
  
|**UserName**|**Password**|
|:-----|:-----|
|Litwareinc\watcher1  <br/> |System.Security.SecureString  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a>Konfigurieren eines einfachen Watcher-Knotens mit den synthetischen Standardtransaktionen

Nachdem die Testbenutzer erstellt wurden, können Sie einen Watcher-Knoten mit einem Befehl wie dem folgenden erstellen:
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

Mithilfe dieses Befehls wird ein neuer Watcher-Knoten erstellt, für den die Standardeinstellungen verwendet werden und der die Standardgruppe synthetischer Transaktionen ausführt. Für den neuen Watcher-Knoten werden zudem die Testbenutzer "watcher1@litwareinc.com", "watcher2@litwareinc.com" und "watcher3@litwareinc.com" verwendet. Wenn der Watcherknoten die TrustedServer-Authentifizierung verwendet, können die drei Testkonten beliebige gültige Benutzerkonten sein, die für Active Directory und Skype for Business Server aktiviert sind. Wenn der Watcherknoten die Aushandlungsauthentifizierungsmethode verwendet, müssen diese Benutzerkonten auch für den Watcherknoten mithilfe des cmdlets Set-CsTestUserCredential aktiviert werden.
  
Gehen Sie stattdessen wie unten dargestellt vor, um zu überprüfen, ob die automatische Ermittlung des Zielpools für die Anmeldung ordnungsgemäß konfiguriert ist, anstatt direkt auf einen Pool zu zielen:
  
```PowerShell
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a>Konfigurieren erweiterter Tests

Wenn Sie den PSTN-Test aktivieren möchten, der die Konnektivität mit dem Telefonnetz des öffentlichen Telefons überprüft, müssen Sie beim Einrichten des Watcher-Knotens eine zusätzliche Konfiguration erstellen. Zunächst müssen Sie Ihre Testbenutzer dem Testtyp PSTN zuordnen, indem Sie einen Befehl wie den folgenden in der Skype for Business Server-Verwaltungsshell ausführen:
  
```PowerShell
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> Die Ergebnisse dieses Befehls müssen in einer Variablen gespeichert werden. In diesem Beispiel heißt die Variable $pstnTest. 
  
Als Nächstes können Sie das Cmdlet **"New-CsWatcherNodeConfiguration"** verwenden, um den Testtyp (in der Variablen $pstnTest gespeichert) einem Skype for Business Server-Pool zuzuordnen. Mit dem folgenden Befehl wird beispielsweise eine neue Watcher-Knoten-Konfiguration für den Pool atl-cs-001.litwareinc.com erstellt, die drei zuvor erstellten Testbenutzer hinzugefügt und der Testtyp PSTN hinzugefügt:
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

Wenn Sie die Skype for Business Server-Kerndateien und die DATENBANK "RTCLocal" auf dem Computer mit den Watcher-Knoten nicht installiert haben, kann der vorstehende Befehl nicht ausgeführt werden. 
  
Zum Testen mehrerer Sprachrichtlinien können Sie mit dem Cmdlet **"New-CsExtendedTest"** einen erweiterten Test für jede Richtlinie erstellen. Die bereitgestellten Benutzer sollten mit den gewünschten Sprachrichtlinien konfiguriert werden. Die erweiterten Tests werden mithilfe von Kommatrennzeichen an das Cmdlet **"New-CsWatcherNodeConfiguration"** übergeben, z. B.:
  
-ExtendedTests @{Add=$pstnTest 1,$pstnTest 2,$pstnTest 3}
  
Da das **Cmdlet New-CsWatcherNodeConfiguration** ohne Verwendung des Parameters "Tests" aufgerufen wurde, werden nur die synthetischen Standardtransaktionen (und die angegebene erweiterte synthetische Transaktion) für den neuen Watcher-Knoten aktiviert. Daher teste der Watcher-Knoten die folgenden Komponenten:
  
- Registrierung
    
- Chat
    
- GroupIM
    
- P2PAV (Peer-zu-Peer-Audio/Videositzungen)
    
- AvConference (Audio/Konferenzen)
    
- Anwesenheit
    
- ABS (Adressbuchdienst)
    
- ABWQ (Adressbuchwebdienst)
    
Die folgenden Komponenten werden standardmäßig nicht getestet:
  
- ASConference
    
- AVEdgeConnectivity
    
- DataConference
    
- DialinConferencing
    
- ExumConnectivity (Exchange Unified Messaging)
    
- JoinLauncher
    
- MCXP2PIM (Legacy-Instant Messaging für mobile Geräte)
    
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

Wenn mindestens einer dieser Tests (z. B. DataConference) bereits auf dem Watcher-Knoten aktiviert wurde, tritt ein Fehler auf. In diesem Fall erhalten Sie eine Fehlermeldung, die der Folgenden ähnelt:
  
Set-CsWatcherNodeConfiguration : Es gibt eine doppelte Schlüsselsequenz "DataConference" für den Schlüssel "urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName" oder eine eindeutige Identitätseinschränkung.
  
Wenn dieser Fehler auftritt, werden keine Änderungen wirksam. Der Befehl sollte erneut ausgeführt werden, und der duplizierte Test sollte entfernt werden.
  
Verwenden Sie die Remove-Methode, um eine synthetische Transaktion aus einem Watcherknoten zu entfernen. Mithilfe des folgenden Befehls wird beispielsweise der ABWQ-Test aus einem Watcher-Knoten entfernt:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

Sie können die Replace -Methode verwenden, um alle derzeit aktivierten Tests durch einen oder mehrere neue Tests zu ersetzen. Wenn sie z. B. möchten, dass ein Watcherknoten nur den Im-Im-Test ausführen kann, können Sie dies mithilfe des folgenden Befehls konfigurieren:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

Wenn Sie diesen Befehl ausführen, werden alle synthetischen Transaktionen auf dem angegebenen Watcherknoten mit Ausnahme von Imiten deaktiviert.
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a>Anzeigen und Testen der Konfiguration des Watcher-Knotens

Wenn Sie die Tests anzeigen möchten, die einem Watcher-Knoten zugewiesen wurden, verwenden Sie einen Befehl, der dem Folgenden ähnelt:
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

Dieser Befehl gibt Informationen wie die folgenden zurück, abhängig von den synthetischen Transaktionen, die dem Knoten zugewiesen wurden:
  
Registrierung im Chat GroupIM P2PAV AvConference Presence PersistentChatMessage DataConference
> [!TIP]
> Wenn Sie die synthetischen Transaktionen in alphabetischer Reihenfolge anzeigen möchten, verwenden Sie stattdessen den folgenden Befehl: 
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

Um zu überprüfen, ob ein Watcherknoten erstellt wurde, geben Sie den folgenden Befehl in der Skype for Business Server-Verwaltungsshell ein:
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

Sie erhalten Informationen wie dies:
  
Identität : atl-cs-001.litwareinc.com TestUsers : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...} ExtendedTests : {TestUsers=IList<System.String>; Name=PSTN-Test; Te...} TargetFqdn : atl-cs-001.litwareinc.com PortNumber : 5061To verify that the watcher node has been configured correctly, type the following command from the Skype for Business Server Management Shell:
  
```PowerShell
Test-CsWatcherNodeConfiguration
```

Mit diesem Befehl werden die einzelnen Watcherknoten in Ihrer Bereitstellung testen und bestätigt, ob die folgenden Aktionen abgeschlossen sind:
  
- Die erforderliche Registrierungsrolle ist installiert
    
- Der erforderliche Registrierungsschlüssel wird erstellt (abgeschlossen, wenn Sie das cmdlet Set-CsWatcherNodeConfiguration haben)
    
- Auf Ihren Servern wird die richtige Version von Skype for Business Server ausgeführt
    
- Ihre Ports sind ordnungsgemäß konfiguriert
    
- Die zugewiesenen Testbenutzer verfügen über die erforderlichen Anmeldeinformationen
    
## <a name="managing-watcher-nodes"></a>Verwalten von Watcher-Knoten
<a name="testuser"> </a>

Sie können nicht nur die synthetischen Transaktionen ändern, die auf einem Watcherknoten ausgeführt werden, sondern auch das Cmdlet **"Set-CsWatcherNodeConfiguration"** verwenden, um zwei weitere wichtige Aufgaben auszuführen: Aktivieren und Deaktivieren des Watcher-Knotens und Konfigurieren des Watcherknotens für die Verwendung interner oder externer Web-URLs beim Ausführen der Tests.
  
In der Standardeinstellung führen Watcher-Knoten in regelmäßigen Abständen alle für sie aktivierten synthetischen Transaktionen aus. Manchmal möchten Sie diese Transaktionen jedoch aussetzen. Wenn der Watcher-Knoten zum Beispiel vorübergehend vom Netzwerk getrennt ist, liegt kein Grund vor, dass die synthetischen Transaktionen ausgeführt werden. Ohne Netzwerkkonnektivität können diese Transaktionen nicht verwendet werden. Führen Sie einen Befehl wie den folgenden in der Skype for Business Server-Verwaltungsshell aus, um einen Watcher-Knoten vorübergehend zu deaktivieren:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

Dieser Befehl deaktiviert die Ausführung synthetischer Transaktionen auf dem watcher node atl watcher 001.litwareinc.com. Wenn die synthetischen Transaktionen wieder aufgenommen werden sollen, setzen Sie die Eigenschaft "Enabled" wieder zurück auf "True" ($True):
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> Mithilfe der Eigenschaft "Enabled" können Watcher-Knoten ein- und ausgeschaltet werden. Wenn Sie einen Watcher-Knoten dauerhaft löschen möchten, verwenden Sie das **Remove-CsWatcherNodeConfiguration**-Cmdlet:
  
```PowerShell
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

Mit diesem Befehl werden alle Konfigurationseinstellungen für Watcherknoten vom angegebenen Computer entfernt, wodurch verhindert wird, dass auf diesem Computer automatisch synthetische Transaktionen ausgeführt werden. Der Befehl deinstalliert jedoch nicht die System Center-Agent-Dateien oder die Skype for Business Server-Systemdateien.
  
Standardmäßig verwenden Watcherknoten beim Durchführen von Tests die externen Web-URLs einer Organisation. Watcherknoten können jedoch auch für die Verwendung der internen Web-URLs der Organisation konfiguriert werden. Dies ermöglicht es Administratoren, den URL-Zugriff für innerhalb des Umkreisnetzwerks befindliche Benutzer zu überprüfen. Um einen Watcherknoten für die Verwendung interner URLs anstelle externer URLs zu konfigurieren, legen Sie die Eigenschaft "UseInternalWebURls" auf "True" ($True) $True:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

Wenn Sie diese Eigenschaft auf den Standardwert "False" ($False) zurücksetzen, verwendet das Watcher erneut die externen URLs:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a>Besondere Anweisungen zum Einrichten von synthetischen Transaktionen
<a name="special_synthetictrans"> </a>

Die meisten synthetischen Transaktionen können auf einem Watcherknoten ausgeführt werden. In den meisten Fällen kann der Watcherknoten, sobald die synthetische Transaktion den Konfigurationseinstellungen des Watcher-Knotens hinzugefügt wird, diese synthetische Transaktion während seiner Testläufe verwenden. Es gibt jedoch einige synthetische Transaktionen, für die spezielle Setupanweisungen erforderlich sind, wie in den folgenden Abschnitten erläutert.
  
### <a name="data-conferencing-synthetic-transaction"></a>Synthetische Transaktion für Datenkonferenzen

Wenn sich ihr Watcher-Knoten-Computer außerhalb Ihres Umkreisnetzwerks befindet, können Sie wahrscheinlich die synthetische Transaktion für Datenkonferenzen erst ausführen, wenn Sie zuerst die Proxyeinstellungen des Windows Internet Explorer® Internetbrowsers für das Netzwerkdienstkonto deaktivieren, indem Sie die folgenden Schritte ausführen:
  
1. Klicken Sie auf dem Computer mit dem Watcher-Knoten auf **"Start",** klicken Sie auf "Alle Programme", klicken Sie auf "Zubehör", klicken Sie mit der rechten Maustaste auf "Eingabeaufforderung", und klicken Sie dann auf "Als Administrator **ausführen".**
    
2. Geben Sie im Konsolenfenster den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE. 
    
```PowerShell
bitsadmin /util /SetIEProxy NetworkService NO_PROXY
```

Im Befehlsfenster wird die folgende Meldung angezeigt:
  
BITSAdmin ist veraltet und ist nicht garantiert in zukünftigen Versionen von Windows verfügbar. Verwaltungstools für den BITS-Dienst werden jetzt von BITS -PowerShell-Cmdlets bereitgestellt.
  
Internetproxyeinstellungen für Das Konto "NetworkService" ist auf NO_PROXY. 
  
(Verbindung = Standard)
  
Diese Meldung gibt an, dass Sie die Internet Explorer-Proxyeinstellungen für das Netzwerkdienstkonto deaktiviert haben.
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a>Synthetische Transaktion in Exchange Unified Messaging

Mit der synthetischen Transaktion von Exchange Unified Messaging (UM) wird überprüft, ob Testbenutzer eine Verbindung mit In Exchange-einheitlichen Voicemailkonten herstellen können.
  
Die Testbenutzer müssen mit Voicemailkonten vorkonfiguriert werden. 
  
### <a name="persistent-chat-synthetic-transaction"></a>Synthetische Transaktion für beständigen Chat

Um die synthetische Transaktion für den beständigen Chat zu verwenden, müssen Sie zuerst einen Kanal erstellen und den Testbenutzern die Berechtigung zur Verwendung erteilen.
  
Sie können die synthetische Transaktion für beständigen Chat verwenden, um diesen Kanal zu konfigurieren: 
  
```PowerShell
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true
```

Sie müssen diese Setupaufgabe innerhalb des Unternehmens ausführen:
  
- Wenn er von einem Computer ausgeführt wird, der kein Server ist, muss der Benutzer, der das Cmdlet ausgeführt, Mitglied der Rolle "CsPersistentChatAdministrators" für Role-Based Access Control (RBAC) sein.
    
- Wenn er vom Server selbst ausgeführt wird, muss der Benutzer, der das Cmdlet ausgeführt, Mitglied der Gruppe "RTCUniversalServerAdmins" sein.
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a>Synthetische Transaktion für PSTN-Peer-zu-Peer-Anrufe

Die Test-CsPstnPeerToPeerCall synthetische Transaktion überprüft die Möglichkeit, Anrufe über ein Festnetz (Public Switched Telephone Network, PSTN) zu platzieren und zu empfangen.
  
Zum Ausführen dieser synthetischen Transaktion müssen Sie Dies konfigurieren:
  
- Zwei UC-aktivierte Testbenutzer (ein Anrufer und ein Empfänger).
    
- DID-Nummern (Direct Inward Dialing) für jedes Benutzerkonto
    
- VoIP-Richtlinien und VoIP-Routen, die das Erreichen des PSTN-Gateways durch Anrufe an die Nummer des Empfängers ermöglichen.
    
- Ein PSTN-Gateway, das Anrufe und Medien akzeptiert, die Anrufe basierend auf der gewählten Nummer an den Homepool eines Empfängers zurückrouten.
    
### <a name="unified-contact-store-synthetic-transaction"></a>Synthetische Transaktion des einheitlichen Kontaktspeichers

Die synthetische Transaktion des einheitlichen Kontaktspeichers überprüft, ob Skype for Business Server Kontakte im Auftrag eines Benutzers aus Exchange abrufen kann.
  
Für die Verwendung dieser synthetischen Transaktionen müssen die folgenden Bedingungen erfüllt sein:
  
- Lyss-Exchange Server-zu-Server-Authentifizierung muss konfiguriert sein.
    
- Testbenutzer müssen über ein gültiges Exchange-Postfach verfügen.
    
Wenn diese Bedingungen erfüllt sind, können Sie das folgende Windows PowerShell ausführen, um die Kontaktlisten der Testbenutzer zu Exchange zu migrieren:
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

Es kann einige Zeit dauern, bis die Testbenutzerkontaktlisten zu Exchange migriert wurden. Zum Überwachen des Migrationsfortschritts kann dieselbe Befehlszeile ohne das Flag "-Setup" ausgeführt werden:
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

Diese Befehlszeile ist nach Abschluss der Migration erfolgreich.
  
### <a name="xmpp-synthetic-transaction"></a>Synthetische XMPP-Transaktion

Für die synthetische Transaktion des Extensible Messaging and Presence Protocol (XMPP) für Chatnachrichten müssen Sie das Feature XMPP mit einer oder mehreren Verbunddomänen konfigurieren.
  
Zum Aktivieren der synthetischen XMPP-Transaktion müssen Sie einen Parameter "XmppTestReceiverMailAddress" mit einem Benutzerkonto in einer routingbaren XMPP-Domäne angeben. Beispiel:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

In diesem Beispiel muss eine Skype for Business Server-Regel vorhanden sein, um Nachrichten litwareinc.com an ein XMPP-Gateway weiter zu routen.

> [!NOTE]
> XMPP-Gateways und -Proxys waren in Skype for Business Server 2015 verfügbar, werden jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Weitere Informationen finden Sie unter ["Migrieren des XMPP-Verbunds".](../migration/migrating-xmpp-federation.md)
  
### <a name="video-interop-server-vis-synthetic-transaction"></a>Synthetische Transaktion des Video-Inop-Servers (VIS)

Die synthetische Transaktion des Video Interop Servers (VIS) erfordert, dass Sie die Unterstützungsdateien für synthetische Transaktionen herunterladen und installieren ([VISSTSupportPackage.msi](https://www.microsoft.com/download/details.aspx?id=46921)). 
  
Um die VISSTSupportPackage.msi stellen Sie sicher, dass die Abhängigkeiten (unter Systemanforderungen) für die msi bereits installiert sind. Führen VISSTSupportPackage.msi für eine einfache Installation aus. Die MSI installiert alle Dateien im folgenden Pfad: "%ProgramFiles%\VIS Synthetic Transaction Support Package".
  
Weitere Informationen zum Ausführen der synthetischen VIS-Transaktion finden Sie in der Dokumentation für das Cmdlet ["Test-CsP2PVideoInteropServerSipTrunkAV".](https://technet.microsoft.com/library/dn985894.aspx)
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a>Ändern der Ausführungshäufigkeit für synthetische Transaktionen
<a name="special_synthetictrans"> </a>

Standardmäßig werden synthetische Transaktionen mit den konfigurierten Benutzern alle 15 Minuten ausgeführt. Synthetische Transaktionen werden sequenziell innerhalb einer Gruppe von Benutzern ausgeführt, um zu vermeiden, dass zwei synthetische Transaktionen miteinander in Konflikt stehen. Es ist ein längeres Intervall erforderlich, um Zeit für den Abschluss aller synthetischen Transaktionen zu bieten.
  
Wenn synthetische Transaktionen häufiger ausgeführt werden sollen, sollte die Anzahl synthetischer Transaktionen, die mit einer bestimmten Gruppe von Benutzern ausgeführt werden, verringert werden, damit die Tests im gewünschten Zeitraum mit einem Puffer für gelegentliche Netzwerkverzögerungen abgeschlossen werden können. Wenn mehr synthetische Transaktionen ausgeführt werden sollen, erstellen Sie weitere Benutzergruppen, um zusätzliche synthetische Transaktionen ausführen zu können.
  
Führen Sie die folgenden Schritte aus, um die Häufigkeit der Ausführung synthetischer Transaktionen zu ändern:
  
1. Öffnen Sie System Center Operations Manager. Klicken Sie auf den Abschnitt "Erstellen". Klicken Sie auf den Abschnitt "Regeln" (unter "Erstellen")
    
2. Suchen Sie im Abschnitt "Regeln" die Regel mit dem Namen "Main Synthetic Transaction Runner Performance Collection Rule".
    
3. Klicken Sie mit der rechten Maustaste auf die Regel, und wählen Sie Außerkraftsetzungen aus, wählen Sie "Regel außer Kraft setzen" und dann "Für alle Objekte der Klasse: Pool-Watcher" aus.
    
4. Wählen Sie im Fenster Eigenschaften außer Kraft setzen den Parameternamen "Häufigkeit" aus, und legen Sie den Überschreibungswert auf den gewünschten Wert fest.
    
5. Wählen Sie im selben Fenster das Management Pack aus, auf das diese Außerkraftsetzung angewendet werden muss.
    
## <a name="using-rich-logging-for-synthetic-transactions"></a>Verwenden von erweiterter Protokollierung für synthetische Transaktionen
<a name="special_synthetictrans"> </a>

Synthetische Transaktionen sind äußerst nützlich, um Probleme mit dem System zu identifizieren. Beispielsweise könnte das cmdlet Test-CsRegistration Administratoren darauf aufmerksam machen, dass Benutzer Schwierigkeiten hatten, sich bei Skype for Business Server zu registrieren. Es können jedoch zusätzliche Details erforderlich sein, um die tatsächliche Ursache eines Fehlers zu ermitteln.
  
Aus diesem Grund bieten synthetische Transaktionen umfassende Protokollierung. Bei der rich-Protokollierung werden für jede Aktivität, die eine synthetische Transaktion vornimmt, die folgenden Informationen aufgezeichnet:
  
- Der Zeitpunkt, zu dem die Aktivität gestartet wurde.
    
- Der Zeitpunkt, zu dem die Aktivität beendet wurde.
    
- Die Aktion, die ausgeführt wurde (z. B. Erstellen, Beitreten oder Verlassen einer Konferenz, Anmelden bei Skype for Business Server; Senden einer Chatnachricht).
    
- Informative oder ausführliche Meldungen bzw. Warn- oder Fehlermeldungen, die beim Ausführen der Aktivität generiert wurden
    
- SIP-Registrierungsnachrichten.
    
- Ausnahmedatensätze oder Diagnosecodes, die beim Ausführen der Aktivität generiert wurden.
    
- Das Ergebnis der Ausführung der Aktivität.
    
Diese Informationen werden bei jeder Ausführung einer synthetischen Transaktion automatisch generiert, aber nicht automatisch angezeigt oder in einer Protokolldatei gespeichert. Wenn Sie eine synthetische Transaktion manuell ausführen, können Sie den Parameter "OutLoggerVariable" verwenden, um eine Windows PowerShell anzugeben, in der die Informationen gespeichert werden. Von dort aus haben Sie die Möglichkeit, eine von zwei Methoden zum Speichern und/oder Anzeigen von Fehlermeldungen im Rich Log im XML- oder HTML-Format zu verwenden. 
  
Geben Sie zum Abrufen der Problembehandlungsinformationen den Parameter "OutLoggerVariable" an, gefolgt von einem Variablennamen, den Sie auswählen:
  
```PowerShell
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> : Geben Sie dem Variablennamen nicht das Zeichen $vor. Verwenden Sie einen Variablennamen wie "RegistrationTest" (nicht $RegistrationTest). 
  
Wenn Sie diesen Befehl ausführen, wird eine Ausgabe wie die folgenden angezeigt:
  
Ziel-FQDN : atl-cs-001.litwareinc.com Ergebnis : Fehlerwartezeit : 00:00:00 Fehlermeldung: Diesem Computer sind keine Zertifikate zugewiesen. Diagnose:Sie können auf viel detailliertere Informationen zu diesem Fehler zugreifen als nur auf die hier gezeigte Fehlermeldung. Verwenden Sie einen Befehl wie diesen, um auf diese Informationen im HTML-Format zu zugreifen, um die in der Variablen RegistrationTest gespeicherten Informationen in einer HTML-Datei zu speichern:
  
```PowerShell
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

Alternativ können Sie die XML()-Methode verwenden, um Dateien in einer XML-Datei zu speichern:
  
```PowerShell
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

Sie können diese Dateien mithilfe von Windows Internet Explorer, Microsoft Visual Studio oder einer anderen Anwendung anzeigen, die HTML/XML-Dateien öffnen kann.
  
Synthetische Transaktionen, die innerhalb von System Center Operations Manager ausgeführt werden, generieren diese Protokolldateien automatisch für Fehler. Diese Protokolle werden nicht generiert, wenn die Ausführung fehlschlägt, bevor Skype for Business Server PowerShell die synthetische Transaktion laden und ausführen kann. 
  
> [!IMPORTANT]
> Standardmäßig speichert Skype for Business Server Protokolldateien in einem Ordner, der nicht freigegeben ist. Damit auf diese Protokolle problemlos zugegriffen werden kann, sollten Sie diesen Ordner freigeben. Beispiel: \\ atl-watcher-001.litwareinc.com\WatcherNode. 
