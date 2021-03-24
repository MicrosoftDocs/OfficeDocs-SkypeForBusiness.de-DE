---
title: Konfigurieren von Testbenutzern und Einstellungen des Watcherknotens
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
ms.assetid: ab2e0d93-cf52-4a4e-b5a4-fd545df7a1a9
description: 'Zusammenfassung: Konfigurieren von Testbenutzerkonten und Watcherknoteneinstellungen für synthetische Skype for Business Server-Transaktionen.'
ms.openlocfilehash: 4069b1b51dc826beb631306e941eb40146188f42
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111601"
---
# <a name="configure-watcher-node-test-users-and-settings"></a>Konfigurieren von Testbenutzern und Einstellungen des Watcherknotens
 
**Zusammenfassung:** Konfigurieren Von Testbenutzerkonten und Watcherknoteneinstellungen für synthetische Skype for Business Server-Transaktionen.
  
Nachdem Sie den Computer konfiguriert haben, der als Watcher-Knoten agieren wird, müssen Sie die folgenden Schritte ausführen:
  
1. [Konfigurieren Sie Testbenutzerkonten,](test-users-and-settings.md#testuser) die von diesen Watcherknoten verwendet werden sollen. Wenn Sie die Aushandlungsauthentifizierungsmethode verwenden, müssen Sie auch das Cmdlet **Set-CsTestUserCredential** verwenden, um die Verwendung dieser Testkonten auf dem Watcher-Knoten zu aktivieren.
    
2. Aktualisieren Sie die Konfigurationseinstellungen für den Watcher-Knoten.
    
## <a name="configure-test-user-accounts"></a>Konfigurieren von Testbenutzerkonten
<a name="testuser"> </a>

Testkonten müssen keine tatsächlichen Personen darstellen, aber sie müssen gültige Active Directory-Konten sein. Darüber hinaus müssen diese Konten für Skype for Business Server aktiviert sein, sie müssen über gültige SIP-Adressen verfügen, und sie sollten für Enterprise-VoIP aktiviert sein (um die synthetische Transaktion Test-CsPstnPeerToPeerCall verwenden). 
  
Wenn Sie die TrustedServer-Authentifizierungsmethode verwenden, müssen Sie nur sicherstellen, dass diese Konten vorhanden sind, und sie wie erwähnt konfigurieren. Sie sollten für jeden Pool, den Sie testen möchten, mindestens zwei Testbenutzer zuweisen. Wenn Sie die Negotiate-Authentifizierungsmethode verwenden, müssen Sie auch das cmdlet Set-CsTestUserCredential und die Skype for Business Server-Verwaltungsshell verwenden, damit diese Testkonten mit den synthetischen Transaktionen arbeiten können. Führen Sie hierzu einen Befehl wie den folgenden aus (bei diesen Befehlen wird davon ausgegangen, dass die beiden Active Directory-Benutzerkonten erstellt wurden und diese Konten für Skype for Business Server aktiviert sind):
  
```PowerShell
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
```

Sie müssen nicht nur die SIP-Adresse, sondern auch den Benutzernamen und das Kennwort angeben. Wenn Sie das Kennwort nicht angeben, fordert Set-CsTestUserCredential cmdlet Sie auf, diese Informationen einzugeben. Der Benutzername kann mithilfe des im vorherigen Codeblock angezeigten Domänennamen-/Benutzernamenformats angegeben werden.
  
Führen Sie die folgenden Befehle in der Skype for Business Server-Verwaltungsshell aus, um zu überprüfen, ob die Anmeldeinformationen des Testbenutzers erstellt wurden:
  
```PowerShell
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
```

Informationen wie diese werden für jeden Benutzer zurückgegeben:
  
|**UserName**|**Password**|
|:-----|:-----|
|Litwareinc\watcher1  <br/> |System.Security.SecureString  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a>Konfigurieren eines Einfachen Watcher-Knotens mit den synthetischen Standardtransaktionen

Nachdem die Testbenutzer erstellt wurden, können Sie einen Watcherknoten mit einem Befehl wie dem folgenden erstellen:
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

Mithilfe dieses Befehls wird ein neuer Watcher-Knoten erstellt, für den die Standardeinstellungen verwendet werden und der die Standardgruppe synthetischer Transaktionen ausführt. Der neue Watcherknoten verwendet auch die Testbenutzer, watcher1@litwareinc.com und watcher2@litwareinc.com. Wenn der Watcherknoten die TrustedServer-Authentifizierung verwendet, können die beiden Testkonten alle gültigen Benutzerkonten sein, die für Active Directory und Skype for Business Server aktiviert sind. Wenn der Watcherknoten die Negotiate-Authentifizierungsmethode verwendet, müssen diese Benutzerkonten auch für den Watcherknoten mithilfe des cmdlets Set-CsTestUserCredential aktiviert werden.
  
Verwenden Sie stattdessen die folgenden Schritte, um zu überprüfen, ob die automatische Ermittlung des Zielpools für die Anmeldung ordnungsgemäß konfiguriert ist, anstatt direkt auf einen Pool zu zielen:
  
```PowerShell
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a>Konfigurieren erweiterter Tests

Wenn Sie den PSTN-Test aktivieren möchten, der die Konnektivität mit dem öffentlichen Telefonnetz überprüft, müssen Sie beim Einrichten des Watcher-Knotens eine zusätzliche Konfiguration erstellen. Zunächst müssen Sie Ihre Testbenutzer dem PSTN-Testtyp zuordnen, indem Sie einen Befehl wie den folgenden in der Skype for Business Server Management Shell ausführen:
  
```PowerShell
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com" -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> Die Ergebnisse dieses Befehls müssen in einer Variablen gespeichert werden. In diesem Beispiel heißt die Variable $pstnTest. 
  
Als Nächstes können Sie das **Cmdlet New-CsWatcherNodeConfiguration** verwenden, um den Testtyp (gespeichert in der Variablen $pstnTest) einem Skype for Business Server-Pool zuzuordnen. Mit dem folgenden Befehl wird beispielsweise eine neue Konfiguration des Watcherknotens für den Pool atl-cs-001.litwareinc.com erstellt, die beiden zuvor erstellten Testbenutzer hinzugefügt und der PSTN-Testtyp hinzugefügt:
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

Wenn Sie die Skype for Business Server-Kerndateien und die RTCLocal-Datenbank auf dem Computer des Watcherknotens nicht installiert haben, wird beim vorherigen Befehl ein Fehler ausgeführt. 
  
Zum Testen mehrerer Sprachrichtlinien können Sie mit dem **Cmdlet New-CsExtendedTest** einen erweiterten Test für jede Richtlinie erstellen. Die bereitgestellten Benutzer sollten mit den gewünschten Sprachrichtlinien konfiguriert werden. Die erweiterten Tests werden mithilfe von Kommatrennzeichen an das **Cmdlet New-CsWatcherNodeConfiguration** übergeben, z. B.:
  
-ExtendedTests @{Add=$pstnTest 1,$pstnTest 2,$pstnTest 3}
  
Da das **Cmdlet New-CsWatcherNodeConfiguration** ohne Verwendung des Parameters Tests aufgerufen wurde, werden nur die synthetischen Standardtransaktionen (und die angegebene erweiterte synthetische Transaktion) für den neuen Watcherknoten aktiviert. Daher testt der Watcher-Knoten die folgenden Komponenten:
  
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

Ein Fehler tritt auf, wenn mindestens einer dieser Tests (z. B. DataConference) bereits auf dem Watcher-Knoten aktiviert wurde. In diesem Fall erhalten Sie eine Fehlermeldung, die der Folgenden ähnelt:
  
Set-CsWatcherNodeConfiguration : Es gibt eine doppelte Schlüsselsequenz "DataConference" für den Schlüssel "urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName" oder eine eindeutige Identitätseinschränkung.
  
Wenn dieser Fehler auftritt, werden keine Änderungen wirksam. Der Befehl sollte erneut ausgeführt werden, wenn der doppelte Test entfernt wurde.
  
Verwenden Sie die Remove-Methode, um eine synthetische Transaktion aus einem Watcherknoten zu entfernen. Mithilfe des folgenden Befehls wird beispielsweise der ABWQ-Test aus einem Watcher-Knoten entfernt:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

Sie können die Replace-Methode verwenden, um alle derzeit aktivierten Tests durch einen oder mehrere neue Tests zu ersetzen. Wenn Sie z. B. möchten, dass ein Watcherknoten nur den Automatischen Test ausführen soll, können Sie dies mithilfe des folgenden Befehls konfigurieren:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

Wenn Sie diesen Befehl ausführen, werden alle synthetischen Transaktionen auf dem angegebenen Watcher-Knoten deaktiviert, mit Ausnahme von Im-In-Vorgängen.
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a>Anzeigen und Testen der Konfiguration des Watcher-Knotens

Wenn Sie die Tests anzeigen möchten, die einem Watcher-Knoten zugewiesen wurden, verwenden Sie einen Befehl, der dem Folgenden ähnelt:
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

Dieser Befehl gibt Informationen wie die folgenden zurück, abhängig von den synthetischen Transaktionen, die dem Knoten zugewiesen wurden:
  
Registrierungs-CHAT GroupIM P2PAV AvConference Presence PersistentChatMessage DataConference
> [!TIP]
> Wenn Sie die synthetischen Transaktionen in alphabetischer Reihenfolge anzeigen möchten, verwenden Sie stattdessen den folgenden Befehl: 
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

Geben Sie den folgenden Befehl aus der Skype for Business Server-Verwaltungsshell ein, um zu überprüfen, ob ein Watcherknoten erstellt wurde:
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

Sie erhalten Informationen wie dies:
  
Identität : atl-cs-001.litwareinc.com <br/>
TestUsers : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}<br/>
ExtendedTests : {TestUsers=IList<System.String>; Name=PSTN Test; Te...}<br/>
TargetFqdn : atl-cs-001.litwareinc.com<br/>
PortNumber : 5061<br/>

Geben Sie den folgenden Befehl aus der Skype for Business Server-Verwaltungsshell ein, um zu überprüfen, ob der Watcherknoten ordnungsgemäß konfiguriert wurde:
  
```PowerShell
Test-CsWatcherNodeConfiguration
```

Mit diesem Befehl werden die einzelnen Watcherknoten in Ihrer Bereitstellung testen und bestätigt, ob die folgenden Aktionen abgeschlossen sind:
  
- Die erforderliche Registrierungsrolle ist installiert.
    
- Der erforderliche Registrierungsschlüssel wird erstellt (abgeschlossen, wenn Sie das cmdlet Set-CsWatcherNodeConfiguration haben).
    
- Auf Ihren Servern wird die richtige Version von Skype for Business Server ausgeführt.
    
- Ihre Ports sind ordnungsgemäß konfiguriert.
    
- Ob die zugewiesenen Testbenutzer über die erforderlichen Anmeldeinformationen verfügen.
    
## <a name="managing-watcher-nodes"></a>Verwalten von Watcher-Knoten
<a name="testuser"> </a>

Zusätzlich zum Ändern der synthetischen Transaktionen, die auf einem Watcherknoten ausgeführt werden, können Sie auch das **Cmdlet Set-CsWatcherNodeConfiguration** verwenden, um zwei weitere wichtige Aufgaben auszuführen: Aktivieren und Deaktivieren des Watcherknotens und Konfigurieren des Watcherknotens für die Verwendung interner Web-URLs oder externer Web-URLs beim Ausführen der Tests.
  
In der Standardeinstellung führen Watcher-Knoten in regelmäßigen Abständen alle für sie aktivierten synthetischen Transaktionen aus. Manchmal möchten Sie diese Transaktionen jedoch möglicherweise anhalten. Wenn der Watcher-Knoten zum Beispiel vorübergehend vom Netzwerk getrennt ist, liegt kein Grund vor, dass die synthetischen Transaktionen ausgeführt werden. Ohne Netzwerkkonnektivität werden diese Transaktionen fehlschlagen. Führen Sie einen Befehl wie den folgenden in der Skype for Business Server-Verwaltungsshell aus, um einen Watcherknoten vorübergehend zu deaktivieren:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

Mit diesem Befehl wird die Ausführung synthetischer Transaktionen auf dem Watcherknoten atl watcher 001.litwareinc.com. Wenn die synthetischen Transaktionen wieder aufgenommen werden sollen, setzen Sie die Eigenschaft "Enabled" wieder zurück auf "True" ($True):
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> Mithilfe der Eigenschaft "Enabled" können Watcher-Knoten ein- und ausgeschaltet werden. Wenn Sie einen Watcher-Knoten dauerhaft löschen möchten, verwenden Sie das **Remove-CsWatcherNodeConfiguration**-Cmdlet:
  
```PowerShell
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

Mit diesem Befehl werden alle Konfigurationseinstellungen für den Watcherknoten vom angegebenen Computer entfernt, wodurch verhindert wird, dass auf diesem Computer automatisch synthetische Transaktionen ausgeführt werden. Der Befehl deinstalliert jedoch weder die System Center-Agent-Dateien noch die Skype for Business Server-Systemdateien.
  
Standardmäßig verwenden Watcherknoten die externen Web-URLs einer Organisation beim Ausführen von Tests. Watcherknoten können jedoch auch für die Verwendung der internen Web-URLs der Organisation konfiguriert werden. Dies ermöglicht es Administratoren, den URL-Zugriff für innerhalb des Umkreisnetzwerks befindliche Benutzer zu überprüfen. Um einen Watcherknoten für die Verwendung interner URLs anstelle externer URLs zu konfigurieren, legen Sie die UseInternalWebURls-Eigenschaft auf True ($True):
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

Wenn Sie diese Eigenschaft auf den Standardwert False ($False) zurücksetzen, verwendet der Watcher erneut die externen URLs:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a>Besondere Anweisungen zum Einrichten von synthetischen Transaktionen
<a name="special_synthetictrans"> </a>

Die meisten synthetischen Transaktionen können wie folgt auf einem Watcherknoten ausgeführt werden. In den meisten Fällen kann der Watcherknoten diese synthetische Transaktion während der Testläufe verwenden, sobald die synthetische Transaktion den Konfigurationseinstellungen des Watcherknotens hinzugefügt wird. Es gibt jedoch einige synthetische Transaktionen, für die spezielle Setupanweisungen erforderlich sind, wie in den folgenden Abschnitten erläutert.
  
### <a name="data-conferencing-synthetic-transaction"></a>Synthetische Datenkonferenztransaktion

Wenn sich der Computer des Watcherknotens außerhalb Ihres Umkreisnetzwerks befindet, können Sie wahrscheinlich die synthetische Transaktion für Datenkonferenzen nur ausführen, wenn Sie zuerst die Windows Internet Explorer® Internetbrowserproxyeinstellungen für das Netzwerkdienstkonto deaktivieren, indem Sie die folgenden Schritte ausführen:
  
1. Klicken Sie auf dem Computer des Watcher-Knotens auf **Start,** klicken Sie auf **Alle** **Programme,** klicken Sie auf **Zubehör,** klicken Sie mit der rechten Maustaste auf Eingabeaufforderung, und klicken Sie dann auf Als Administrator ausführen .
    
2. Geben Sie im Konsolenfenster den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE. 
    
    ```console
    bitsadmin /util /SetIEProxy NetworkService NO_PROXY
    ```

    Im Befehlsfenster wird die folgende Meldung angezeigt:

    ```console
    BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.
  
    Internet proxy settings for account NetworkService set to NO_PROXY. 
      
    (connection = default)
    ```
      
    Diese Meldung gibt an, dass Sie die Internet Explorer-Proxyeinstellungen für das Netzwerkdienstkonto deaktiviert haben.
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a>Synthetische Exchange Unified Messaging-Transaktion

Die synthetische Exchange Unified Messaging (UM)-Transaktion überprüft, ob Testbenutzer eine Verbindung mit Voicemailkonten herstellen können, die in Exchange heimisch sind.
  
Die Testbenutzer müssen mit Voicemailkonten vorkonfiguriert sein. 
  
### <a name="persistent-chat-synthetic-transaction"></a>Synthetische Transaktion für beständigen Chat

Zum Verwenden der synthetischen Transaktion für beständigen Chat müssen Sie zunächst einen Kanal erstellen und den Testbenutzern die Berechtigung zur Verwendung erteilen.
  
Sie können die synthetische Transaktion für beständigen Chat verwenden, um diesen Kanal zu konfigurieren: 
  
```powershell
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true
```

Sie müssen diese Setupaufgabe von innerhalb des Unternehmens ausführen:
  
- Wenn das Cmdlet von einem Nicht-Servercomputer ausgeführt wird, muss der Benutzer, der das Cmdlet ausgeführt hat, Mitglied der Rolle CsPersistentChatAdministrators für Role-Based Zugriffssteuerung (RBAC) sein.
    
- Wenn er vom Server selbst ausgeführt wird, muss der Benutzer, der das Cmdlet ausgeführt hat, Mitglied der Gruppe "RTCUniversalServerAdmins" sein.
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a>Synthetische PstN-Peer-zu-Peer-Anruftransaktion

Die Test-CsPstnPeerToPeerCall synthetische Transaktion überprüft die Möglichkeit, Anrufe über ein Festnetz (Public Switched Telephone Network, PSTN) zu platzieren und zu empfangen.
  
Zum Ausführen dieser synthetischen Transaktion müssen Sie konfigurieren:
  
- Zwei UC-aktivierte Testbenutzer (ein Anrufer und ein Empfänger).
    
- DID-Nummern (Direct Inward Dialing) für jedes Benutzerkonto
    
- VoIP-Richtlinien und Voicerouten, mit denen Anrufe an die Empfängernummer das PSTN-Gateway erreichen können.
    
- Ein PSTN-Gateway, das Anrufe und Medien akzeptiert, die Anrufe basierend auf der gewählten Nummer an den Homepool eines Empfängers zurückrouten.
    
### <a name="unified-contact-store-synthetic-transaction"></a>Synthetische Transaktion im einheitlichen Kontaktspeicher

Die synthetische Transaktion Unified Contact Store überprüft, ob Skype for Business Server Kontakte im Auftrag eines Benutzers aus Exchange abrufen kann.
  
Für die Verwendung dieser synthetischen Transaktionen müssen die folgenden Bedingungen erfüllt sein:
  
- Lyss-Exchange Server-zu-Server-Authentifizierung muss konfiguriert werden.
    
- Testbenutzer müssen über ein gültiges Exchange-Postfach verfügen.
    
Nachdem diese Bedingungen erfüllt sind, können Sie das folgende Windows PowerShell ausführen, um die Kontaktlisten der Testbenutzer zu Exchange zu migrieren:
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

Es kann einige Zeit dauern, bis die Testbenutzerkontaktlisten zu Exchange migriert werden. Zum Überwachen des Migrationsfortschritts kann dieselbe Befehlszeile ohne das -Setup-Flag ausgeführt werden:
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

Diese Befehlszeile ist erfolgreich, nachdem die Migration abgeschlossen wurde.
  
### <a name="xmpp-synthetic-transaction"></a>Synthetische XMPP-Transaktion

Die synthetische Transaktion extensible Messaging and Presence Protocol (XMPP) erfordert, dass Sie das XMPP-Feature mit einer oder mehreren Verbunddomänen konfigurieren.
  
Zum Aktivieren der synthetischen XMPP-Transaktion müssen Sie einen XmppTestReceiverMailAddress-Parameter mit einem Benutzerkonto in einer routingbaren XMPP-Domäne angeben. Zum Beispiel:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

In diesem Beispiel muss eine Skype for Business Server-Regel vorhanden sein, um Nachrichten für litwareinc.com an ein XMPP-Gateway weiter zu routen.

> [!NOTE]
> XMPP-Gateways und Proxys sind in Skype for Business Server 2015 verfügbar, werden jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Weitere Informationen finden Sie unter Migrieren des [XMPP-Verbunds.](../../../SfBServer2019/migration/migrating-xmpp-federation.md) 
  
### <a name="video-interop-server-vis-synthetic-transaction"></a>Synthetische Transaktion mit Video Interop Server (VIS)

Die synthetische Transaktion Video Interop Server (VIS) erfordert, dass Sie die synthetischen Transaktionsunterstützungsdateien herunterladen und installieren ([VISSTSupportPackage.msi](https://www.microsoft.com/download/details.aspx?id=46921)). 
  
Zum Installieren VISSTSupportPackage.msi sicherstellen, dass die Abhängigkeiten (unter Systemanforderungen) für den msi bereits installiert sind. Führen VISSTSupportPackage.msi für eine einfache Installation aus. Die MSI installiert alle Dateien im folgenden Pfad: "%ProgramFiles%\VIS Synthetic Transaction Support Package".
  
Weitere Informationen zum Ausführen der synthetischen VIS-Transaktion finden Sie in der Dokumentation zum [Cmdlet Test-CsP2PVideoInteropServerSipTrunkAV.](/powershell/module/skype/Test-CsP2PVideoInteropServerSipTrunkAV)
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a>Ändern der Ausführungshäufigkeit für synthetische Transaktionen
<a name="special_synthetictrans"> </a>

Synthetische Transaktionen werden standardmäßig alle 15 Minuten mit den konfigurierten Benutzern ausgeführt. Synthetische Transaktionen werden sequenziell innerhalb einer Gruppe von Benutzern ausgeführt, um zu vermeiden, dass zwei synthetische Transaktionen miteinander in Konflikt stehen. Es ist ein längeres Intervall erforderlich, damit alle synthetischen Transaktionen abgeschlossen werden können.
  
Wenn synthetische Transaktionen häufiger ausgeführt werden sollen, sollte die Anzahl synthetischer Transaktionen, die mit einer bestimmten Gruppe von Benutzern ausgeführt werden, verringert werden, damit die Tests im gewünschten Zeitraum mit einem Puffer für gelegentliche Netzwerkverzögerungen abgeschlossen werden können. Wenn das Ausführen weiterer synthetischer Transaktionen wünschenswert ist, erstellen Sie mehr Benutzersätze, um zusätzliche synthetische Transaktionen ausführen zu können.
  
Führen Sie die folgenden Schritte aus, um die Häufigkeit der Ausführung synthetischer Transaktionen zu ändern:
  
1. Öffnen Sie System Center Operations Manager. Klicken Sie auf Erstellen. Klicken Sie auf Den Abschnitt Regeln (unter Erstellen).
    
2. Suchen Sie im Abschnitt Regeln nach der Regel mit dem Namen "Main Synthetic Transaction Runner Performance Collection Rule".
    
3. Klicken Sie mit der rechten Maustaste auf die Regel, und wählen Sie Außerkraftsetzungen aus, wählen Sie Regel außer Kraft setzen und dann "Für alle Objekte der Klasse: Pool-Watcher" aus.
    
4. Wählen Sie im Fenster Eigenschaften überschreiben den Parameternamen "Häufigkeit" aus, und legen Sie den Überschreibungswert auf den gewünschten Wert fest.
    
5. Wählen Sie im gleichen Fenster das Management Pack aus, auf das diese Außerkraftsetzung angewendet werden muss.
    
## <a name="using-rich-logging-for-synthetic-transactions"></a>Verwenden von erweiterter Protokollierung für synthetische Transaktionen
<a name="special_synthetictrans"> </a>

Synthetische Transaktionen sind äußerst nützlich, um Probleme mit dem System zu identifizieren. Das cmdlet Test-CsRegistration administratoren beispielsweise darauf aufmerksam machen, dass Benutzer Schwierigkeiten hatten, sich bei Skype for Business Server zu registrieren. Es können jedoch zusätzliche Details erforderlich sein, um die tatsächliche Ursache eines Fehlers zu ermitteln.
  
Aus diesem Grund bieten synthetische Transaktionen eine umfassende Protokollierung. Bei der rich-Protokollierung werden für jede Aktivität, die eine synthetische Transaktion übernimmt, die folgenden Informationen aufgezeichnet:
  
- Der Zeitpunkt, zu dem die Aktivität gestartet wurde.
    
- Der Zeitpunkt, zu dem die Aktivität abgeschlossen wurde.
    
- Die ausgeführte Aktion (z. B. Erstellen, Beitreten oder Verlassen einer Konferenz, Anmelden bei Skype for Business Server, Senden einer Sofortnachricht).
    
- Informations-, Ausführliche, Warnungs- oder Fehlermeldungen, die beim Betrieb der Aktivität generiert wurden.
    
- SIP-Registrierungsmeldungen.
    
- Ausnahmedatensätze oder Diagnosecodes, die beim Ausführen der Aktivität generiert wurden.
    
- Das Nettoergebnis der Ausführung der Aktivität.
    
Diese Informationen werden bei jeder Ausführung einer synthetischen Transaktion automatisch generiert, aber nicht automatisch angezeigt oder in einer Protokolldatei gespeichert. Wenn Sie eine synthetische Transaktion manuell ausführen, können Sie den Parameter OutLoggerVariable verwenden, um eine Windows PowerShell anzugeben, in der die Informationen gespeichert werden. Von dort haben Sie die Möglichkeit, eine von zwei Methoden zum Speichern und/oder Anzeigen von Fehlermeldungen im Rich Log im XML- oder HTML-Format zu verwenden. 
  
Geben Sie zum Abrufen der Problembehandlungsinformationen den Parameter OutLoggerVariable an, gefolgt von einem Variablennamen, den Sie auswählen:
  
```PowerShell
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> Stellen Sie dem Variablennamen kein $-Zeichen voran. Verwenden Sie einen Variablennamen wie RegistrationTest (nicht $RegistrationTest). 
  
Wenn Sie diesen Befehl ausführen, wird eine Ausgabe wie die folgenden angezeigt:
  
Ziel-Fqdn : atl-cs-001.litwareinc.com Result : Failure Latency : 00:00:00 Error Message : This machine does not have any assigned certificates. Diagnose :Sie können auf viel detailliertere Informationen für diesen Fehler zugreifen als nur auf die hier gezeigte Fehlermeldung.

Verwenden Sie einen Befehl wie diesen, um auf diese Informationen im HTML-Format zu zugreifen, um die in der Variablen RegistrationTest gespeicherten Informationen in einer HTML-Datei zu speichern:
  
```PowerShell
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

Alternativ können Sie die XML()-Methode verwenden, um Dateien in einer XML-Datei zu speichern:
  
```PowerShell
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

Sie können diese Dateien mithilfe von Windows Internet Explorer, Microsoft Visual Studio oder einer anderen Anwendung anzeigen, die HTML/XML-Dateien öffnen kann.
  
Synthetische Transaktionen, die von innerhalb von System Center Operations Manager ausgeführt werden, generieren diese Protokolldateien automatisch für Fehler. Diese Protokolle werden nicht generiert, wenn die Ausführung fehlschlägt, bevor Skype for Business Server PowerShell die synthetische Transaktion laden und ausführen kann. 
  
> [!IMPORTANT]
> Standardmäßig speichert Skype for Business Server Protokolldateien in einem Ordner, der nicht freigegeben ist. Damit auf diese Protokolle leicht zugegriffen werden kann, sollten Sie diesen Ordner freigeben. Beispiel: \\ atl-watcher-001.litwareinc.com\WatcherNode.