---
title: Konfigurieren von Benutzern und Einstellungen für den Watcher-Knotentest
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Zusammenfassung: Konfigurieren von Testbenutzerkonten und Watcher-Knoten Einstellungen für Skype for Business Server synthetischen Transaktionen.'
ms.openlocfilehash: 8b586cf4c1d003bb54afa050469a10eee8d113e3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42005950"
---
# <a name="configure-watcher-node-test-users-and-settings"></a>Konfigurieren von Benutzern und Einstellungen für den Watcher-Knotentest
 
**Zusammenfassung:** Konfigurieren Sie Testbenutzerkonten und Watcher-Knoten Einstellungen für Skype for Business Server synthetischen Transaktionen.
  
Nachdem Sie den Computer konfiguriert haben, der als Watcher-Knoten agieren wird, müssen Sie die folgenden Schritte ausführen:
  
1. [Konfigurieren Sie Test Benutzerkonten](test-users-and-settings.md#testuser) , die von diesen Watcher-Knoten verwendet werden sollen. Wenn Sie die Aushandlungsauthentifizierungsmethode verwenden, müssen Sie auch das Cmdlet **Set-CsTestUserCredential** verwenden, um die Verwendung dieser Testkonten auf dem Watcher-Knoten zu aktivieren.
    
2. Aktualisieren Sie die Konfigurationseinstellungen für den Watcher-Knoten.
    
## <a name="configure-test-user-accounts"></a>Konfigurieren von Test Benutzerkonten
<a name="testuser"> </a>

Test Konten müssen keine tatsächlichen Personen darstellen, Sie müssen jedoch Active Directory Konten gültig sein. Darüber hinaus müssen diese Konten für Skype for Business Server aktiviert sein, Sie müssen über gültige SIP-Adressen verfügen und für Enterprise-VoIP aktiviert sein (für die Verwendung der synthetischen Test-CsPstnPeerToPeerCall-Transaktion). 
  
Wenn Sie die TrustedServer-Authentifizierungsmethode verwenden, müssen Sie lediglich sicherstellen, dass diese Konten vorhanden sind, und Sie wie angegeben konfigurieren. Sie sollten mindestens zwei Testbenutzer für jeden Pool zuweisen, den Sie testen möchten. Wenn Sie die Negotiate-Authentifizierungsmethode verwenden, müssen Sie auch das Cmdlet "CsTestUserCredential" und die Skype for Business Server-Verwaltungsshell verwenden, damit diese Testkonten mit den synthetischen Transaktionen verwendet werden können. Führen Sie dazu einen Befehl wie den folgenden aus (bei diesen Befehlen wird davon ausgegangen, dass die beiden Active Directory Benutzerkonten erstellt wurden und diese Konten für Skype for Business Server aktiviert sind):
  
```PowerShell
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
```

Sie müssen nicht nur die SIP-Adresse, sondern auch den Benutzernamen und das Kennwort einbeziehen. Wenn Sie das Kennwort nicht einschließen, werden Sie vom Cmdlet "CsTestUserCredential" aufgefordert, diese Informationen einzugeben. Der Benutzername kann mithilfe des im vorherigen Codeblock angezeigten Namensformats für Domänenname \ Benutzer angegeben werden.
  
Um sicherzustellen, dass die Testbenutzer Anmeldeinformationen erstellt wurden, führen Sie diese Befehle in der Skype for Business Server-Verwaltungsshell aus:
  
```PowerShell
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
```

Informationen wie diese werden für jeden Benutzer zurückgegeben:
  
|**UserName**|**Password**|
|:-----|:-----|
|Litwareinc\watcher1  <br/> |System. Security. SecureString  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a>Konfigurieren eines Basis Monitor Knotens mit den synthetischen Standardtransaktionen

Nachdem die Testbenutzer erstellt wurden, können Sie einen Watcher-Knoten erstellen, indem Sie einen Befehl wie den folgenden verwenden:
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

Mithilfe dieses Befehls wird ein neuer Watcher-Knoten erstellt, für den die Standardeinstellungen verwendet werden und der die Standardgruppe synthetischer Transaktionen ausführt. Der neue Watcher-Knoten verwendet auch die Testbenutzer watcher1@litwareinc.com und watcher2@litwareinc.com. Wenn der Watcher-Knoten die TrustedServer-Authentifizierung verwendet, können die beiden Testkonten alle gültigen Benutzerkonten sein, die für Active Directory und Skype for Business Server aktiviert sind. Wenn der Watcher-Knoten die Negotiate-Authentifizierungsmethode verwendet, müssen diese Benutzerkonten auch für den Watcher-Knoten mithilfe des Cmdlets "CsTestUserCredential" aktiviert werden.
  
Um zu überprüfen, ob die automatische Ermittlung des Ziel Pools zur Anmeldung ordnungsgemäß konfiguriert ist, statt einen Pool direkt zu verwenden, führen Sie stattdessen die folgenden Schritte aus:
  
```PowerShell
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a>Konfigurieren erweiterter Tests

Wenn Sie den PSTN-Test aktivieren möchten, der die Verbindung mit dem öffentlichen Telefonnetz überprüft, müssen Sie beim Einrichten des Watcher-Knotens eine zusätzliche Konfiguration durchführen. Zunächst müssen Sie die Testbenutzer dem PSTN-Testtyp zuordnen, indem Sie einen Befehl wie den folgenden in der Skype for Business Server Verwaltungsshell ausführen:
  
```PowerShell
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com" -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> Die Ergebnisse dieses Befehls müssen in einer Variablen gespeichert werden. In diesem Beispiel wird die Variable $pstnTest benannt. 
  
Im nächsten Schritt können Sie das Cmdlet **New-CsWatcherNodeConfiguration** verwenden, um den in der Variablen $pstnTest gespeicherten Testtyp einem Skype for Business Server-Pool zuzuordnen. Mit dem folgenden Befehl wird beispielsweise eine neue Watcher-Knoten Konfiguration für den Pool ATL-CS-001.litwareinc.com erstellt, wobei die beiden zuvor erstellten Testbenutzer hinzugefügt und der PSTN-Testtyp hinzugefügt wurde:
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

Der obige Befehl schlägt fehl, wenn Sie die Skype for Business Server Kerndateien und die RTCLocal-Datenbank nicht auf dem Watcher-Knoten Computer installiert haben. 
  
Um mehrere VoIP-Richtlinien zu testen, können Sie mithilfe des Cmdlets **New-csextendedtest "** einen erweiterten Test für jede Richtlinie erstellen. Die bereitgestellten Benutzer sollten mit den gewünschten VoIP-Richtlinien konfiguriert werden. Die erweiterten Tests werden mithilfe von Kommatrennzeichen an das Cmdlet **New-CsWatcherNodeConfiguration** übergeben, beispielsweise:
  
-ExtendedTests @ {Add = $pstnTest 1, $pstnTest 2, $pstnTest 3}
  
Da das **New-CsWatcherNodeConfiguration-** Cmdlet ohne Verwendung des Parameters Tests aufgerufen wurde, werden nur die synthetischen Standardtransaktionen (und die angegebene erweiterte synthetische Transaktion) für den neuen Watcher-Knoten aktiviert. Daher testet der Watcher-Knoten die folgenden Komponenten:
  
- Registrierung
    
- Chat
    
- GroupIM
    
- P2PAV (Peer-zu-Peer-Audio/Videositzungen)
    
- AvConference (Audio/Konferenzen)
    
- Anwesenheit
    
- ABS (Adressbuchdienst)
    
- ABWQ (Adressbuchwebdienst)
    
Die folgenden Komponenten werden standardmäßig nicht getestet:
  
- Konferenz
    
- AVEdgeConnectivity
    
- Dataconference
    
- DialinConferencing
    
- ExumConnectivity (Exchange Unified Messaging)
    
- JoinLauncher
    
- MCXP2PIM (Instant Messaging für ältere Mobile Geräte)
    
- P2PVideoInteropServerSipTrunkAV
    
- PersistentChatMessage
    
- PSTN (PSTN-Gateway-Anrufe, angegeben als erweiterter Test)
    
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

Wenn mindestens ein solcher Test (beispielsweise dataconference) auf dem Watcher-Knoten bereits aktiviert wurde, tritt ein Fehler auf. In diesem Fall erhalten Sie eine Fehlermeldung, die der Folgenden ähnelt:
  
CsWatcherNodeConfiguration: Es gibt eine doppelte Schlüsselsequenz "dataconference" für die Key-oder Unique Identity-Einschränkung "urn: Schema: Microsoft. RTC. Management. Settings. WatcherNode. 2010: Testname".
  
Wenn dieser Fehler auftritt, werden keine Änderungen wirksam. Der Befehl sollte erneut ausgeführt werden, wenn der doppelte Test entfernt wurde.
  
Verwenden Sie die Remove-Methode, um eine synthetische Transaktion aus einem Watcher-Knoten zu entfernen. Mithilfe des folgenden Befehls wird beispielsweise der ABWQ-Test aus einem Watcher-Knoten entfernt:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

Sie können die Replace-Methode verwenden, um alle derzeit aktivierten Tests durch einen oder mehrere neue Tests zu ersetzen. Wenn Sie beispielsweise einen Watcher-Knoten nur zum Ausführen des Sofortnachrichten Tests verwenden möchten, können Sie diesen mithilfe dieses Befehls konfigurieren:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

Wenn Sie diesen Befehl ausführen, werden alle synthetischen Transaktionen auf dem angegebenen Watcher-Knoten mit Ausnahme von Chatnachrichten deaktiviert.
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a>Anzeigen und Testen der Konfiguration des Watcher-Knotens

Wenn Sie die Tests anzeigen möchten, die einem Watcher-Knoten zugewiesen wurden, verwenden Sie einen Befehl, der dem Folgenden ähnelt:
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

Dieser Befehl gibt abhängig von den synthetischen Transaktionen, die dem Knoten zugewiesen wurden, ähnliche Informationen zurück:
  
Registrierung im GroupIM P2PAV AvConference Presence PersistentChatMessage dataconference
> [!TIP]
> Wenn Sie die synthetischen Transaktionen in alphabetischer Reihenfolge anzeigen möchten, verwenden Sie stattdessen den folgenden Befehl: 
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

Um zu überprüfen, ob ein Watcher-Knoten erstellt wurde, geben Sie den folgenden Befehl in der Skype for Business Server-Verwaltungsshell ein:
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

Sie erhalten wieder Informationen wie die folgende:
  
Identity: ATL-CS-001.litwareinc.com <br/>
TestUsers: {SIP:watcher1@litwareinc.com, SIP:watcher2@litwareinc.com...}<br/>
ExtendedTests: {TestUsers = IList<System. String>; Name = PSTN-Test; Te...}<br/>
TargetFqdn: ATL-CS-001.litwareinc.com<br/>
PortNumber: 5061<br/>

Um zu überprüfen, ob der Watcher-Knoten ordnungsgemäß konfiguriert wurde, geben Sie den folgenden Befehl in der Skype for Business Server-Verwaltungsshell ein:
  
```PowerShell
Test-CsWatcherNodeConfiguration
```

Mit diesem Befehl wird jeder Watcher-Knoten in Ihrer Bereitstellung getestet, und es wird überprüft, ob die folgenden Aktionen ausgeführt werden:
  
- Die erforderliche Registrierungsstellen Rolle ist installiert.
    
- Der erforderliche Registrierungsschlüssel wird erstellt (abgeschlossen, als Sie das Cmdlet "CsWatcherNodeConfiguration" ausgeführt haben).
    
- Auf Ihren Servern wird die richtige Version von Skype for Business Server.
    
- Ihre Ports sind ordnungsgemäß konfiguriert.
    
- Ob die zugewiesenen Testbenutzer über die erforderlichen Anmeldeinformationen verfügen.
    
## <a name="managing-watcher-nodes"></a>Verwalten von Watcher-Knoten
<a name="testuser"> </a>

Zusätzlich zum Ändern der synthetischen Transaktionen, die auf einem Watcher-Knoten ausgeführt werden, können Sie auch das Cmdlet " **CsWatcherNodeConfiguration** " verwenden, um zwei andere wichtige Aufgaben auszuführen: Aktivieren und Deaktivieren des Watcher-Knotens und Konfigurieren des Watcher-Knotens zur Verwendung interner oder externer weburls beim Ausführen der Tests.
  
In der Standardeinstellung führen Watcher-Knoten in regelmäßigen Abständen alle für sie aktivierten synthetischen Transaktionen aus. Gelegentlich möchten Sie jedoch diese Transaktionen anhalten. Wenn der Watcher-Knoten zum Beispiel vorübergehend vom Netzwerk getrennt ist, liegt kein Grund vor, dass die synthetischen Transaktionen ausgeführt werden. Ohne Netzwerkkonnektivität treten bei diesen Transaktionen Fehler auf. Wenn Sie einen Watcher-Knoten vorübergehend deaktivieren möchten, führen Sie einen Befehl wie den folgenden aus der Skype for Business Server-Verwaltungsshell aus:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

Mit diesem Befehl wird die Ausführung synthetischer Transaktionen auf dem Watcher-Knoten ATL Watcher 001.litwareinc.com deaktiviert. Wenn die synthetischen Transaktionen wieder aufgenommen werden sollen, setzen Sie die Eigenschaft "Enabled" wieder zurück auf "True" ($True):
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> Mithilfe der Eigenschaft "Enabled" können Watcher-Knoten ein- und ausgeschaltet werden. Wenn Sie einen Watcher-Knoten dauerhaft löschen möchten, verwenden Sie das **Remove-CsWatcherNodeConfiguration**-Cmdlet:
  
```PowerShell
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

Mit diesem Befehl werden alle Konfigurationseinstellungen des Watcher-Knotens aus dem angegebenen Computer entfernt, wodurch verhindert wird, dass der Computer synthetische Transaktionen automatisch ausführt. Mit dem Befehl werden die System Center-Agent-Dateien oder die Skype for Business Server Systemdateien jedoch nicht deinstalliert.
  
Standardmäßig verwenden Watcher-Knoten beim Durchführen von Tests die externen weburls einer Organisation. Watcher-Knoten können jedoch auch für die Verwendung der internen weburls der Organisation konfiguriert werden. Dies ermöglicht es Administratoren, den URL-Zugriff für innerhalb des Umkreisnetzwerks befindliche Benutzer zu überprüfen. Wenn Sie einen Watcher-Knoten so konfigurieren möchten, dass er interne URLs anstelle externer URLs verwendet, legen Sie die UseInternalWebURls-Eigenschaft auf true ($true) fest:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

Wenn Sie diese Eigenschaft auf den Standardwert false ($false) zurücksetzen, wird die externe URL vom Watcher erneut verwendet:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a>Besondere Anweisungen zum Einrichten von synthetischen Transaktionen
<a name="special_synthetictrans"> </a>

Die meisten synthetischen Transaktionen können auf einem Watcher-Knoten ausgeführt werden. In den meisten Fällen kann der Watcher-Knoten, sobald die synthetische Transaktion den Konfigurationseinstellungen des Watcher-Knotens hinzugefügt wird, diese synthetische Transaktion während der Testdurchläufe verwenden. Es gibt jedoch einige synthetische Transaktionen, die spezielle Setupanweisungen erfordern, wie in den folgenden Abschnitten erläutert.
  
### <a name="data-conferencing-synthetic-transaction"></a>Synthetische Datenkonferenz Transaktion

Wenn sich der Monitor Knoten Computer außerhalb des Umkreisnetzwerks befindet, können Sie die synthetische Datenkonferenz-Transaktion möglicherweise nicht ausführen, es sei denn, Sie deaktivieren zunächst die Windows Internet Explorer® Internet Browser-Proxyeinstellungen für das Netzwerk Dienstkonto, indem Sie die folgenden Schritte ausführen:
  
1. Klicken Sie auf dem Monitor Knoten Computer auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Zubehör**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und klicken Sie dann auf **als Administrator ausführen**.
    
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
      
    Diese Meldung weist darauf hin, dass Sie die Internet Explorer Proxyeinstellungen für das Netzwerkdienstkonto deaktiviert haben.
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a>Synthetische Exchange Unified Messaging-Transaktion

Die Exchange Unified Messaging (um) synthetische Transaktion überprüft, ob Testbenutzer eine Verbindung mit Voicemail-Konten herstellen können, die in Exchange verwaltet werden.
  
Die Testbenutzer müssen mit Voicemail-Konten vorkonfiguriert sein. 
  
### <a name="persistent-chat-synthetic-transaction"></a>Synthetische Transaktion für beständigen Chat

Um die synthetische persistent Chat-Transaktion zu verwenden, müssen Sie zunächst einen Kanal erstellen und den Testbenutzern Berechtigungen zur Verwendung geben.
  
Sie können die synthetische persistent Chat-Transaktion zum Konfigurieren dieses Kanals verwenden: 
  
```powershell
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true
```

Sie müssen diesen Setup-Task ausführen innerhalb des Unternehmens ausführen:
  
- Wenn von einem Computer ohne Server ausgeführt wird, muss der Benutzer, der das Cmdlet ausführt, ein Mitglied der CsPersistentChatAdministrators-Rolle für die rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC) sein.
    
- Wenn Sie vom Server selbst ausgeführt wird, muss der Benutzer, der das Cmdlet ausführt, Mitglied der RTCUniversalServerAdmins-Gruppe sein.
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a>PSTN-Peer-to-Peer-Anruf synthetische Transaktion

Die synthetische Test-CsPstnPeerToPeerCall-Transaktion überprüft, ob Anrufe über ein öffentliches Telefonnetz (PSTN) getätigt und empfangen werden können.
  
Um diese synthetische Transaktion auszuführen, müssen Sie Folgendes konfigurieren:
  
- Zwei UC-fähige Testbenutzer (Anrufer und Empfänger).
    
- DID-Nummern (Direct Inward Dialing) für jedes Benutzerkonto
    
- VoIP-Richtlinien und VoIP-Routen, bei denen Anrufe an die Nummer des Empfängers das PSTN-Gateway erreichen können.
    
- Ein PSTN-Gateway, das Anrufe und Medien annimmt, die Anrufe basierend auf der gewählten Nummer zurück an den Home-Pool eines Empfängers weiterleiten werden.
    
### <a name="unified-contact-store-synthetic-transaction"></a>Synthetische Transaktion des einheitlichen Kontaktspeichers

Die synthetische Transaktion des einheitlichen Kontaktspeichers überprüft, ob Skype for Business Server Kontakte im Auftrag eines Benutzers aus Exchange abrufen können.
  
Für die Verwendung dieser synthetischen Transaktionen müssen die folgenden Bedingungen erfüllt sein:
  
- Lyss-Exchange Server-zu-Server-Authentifizierung muss konfiguriert sein.
    
- Test Benutzer benötigen ein gültiges Exchange-Postfach.
    
Nachdem diese Bedingungen erfüllt sind, können Sie das folgende Windows PowerShell-Cmdlet ausführen, um die Kontaktlisten der Testbenutzer zu Exchange zu migrieren:
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

Es kann einige Zeit dauern, bis die Testbenutzer Kontaktlisten zu Exchange migriert wurden. Um den Migrations Fortschritt zu überwachen, kann dieselbe Befehlszeile ohne das Flag-Setup ausgeführt werden:
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

Diese Befehlszeile ist nach Abschluss der Migration erfolgreich.
  
### <a name="xmpp-synthetic-transaction"></a>Synthetische XMPP-Transaktion

Für die synthetische XMPP-Sofortnachrichten Transaktion (Extensible Messaging and Presence Protocol) ist es erforderlich, dass Sie das XMPP-Feature mit einer oder mehreren Verbunddomänen konfigurieren.
  
Um die synthetische XMPP-Transaktion zu aktivieren, müssen Sie einen XmppTestReceiverMailAddress-Parameter mit einem Benutzerkonto in einer routingfähigen XMPP-Domäne bereitstellen. Beispiel:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

In diesem Beispiel muss eine Skype for Business Server-Regel vorhanden sein, um Nachrichten für litwareinc.com an ein XMPP-Gateway weiterzuleiten.

> [!NOTE]
> XMPP-Gateways und-Proxys stehen in Skype for Business Server 2015 zur Verfügung, werden in Skype for Business Server 2019 jedoch nicht mehr unterstützt. Weitere Informationen finden Sie unter [Migrating XMPP Federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) . 
  
### <a name="video-interop-server-vis-synthetic-transaction"></a>Synthetische Transaktion für Video-Interop-Server (VIS)

Für die synthetische Video Interop Server-Transaktion ist es erforderlich, dass Sie die synthetischen Transaktions Unterstützungsdateien ([VISSTSupportPackage. msi](https://www.microsoft.com/download/details.aspx?id=46921)) herunterladen und installieren. 
  
Zum Installieren von VISSTSupportPackage. msi stellen Sie sicher, dass die Abhängigkeiten (unter System Anforderungen) für die MSI-Datei bereits installiert sind. Führen Sie VISSTSupportPackage. msi aus, um eine einfache Installation durchzuführen. Die MSI-Datei installiert alle Dateien im folgenden Pfad: "%ProgramFiles%\VIS synthetische Transaktions Unterstützungspaket".
  
Weitere Informationen zum Ausführen der VIS-synthetischen Transaktion finden Sie in der Dokumentation zum Cmdlet [Test-CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/library/dn985894.aspx) .
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a>Ändern der Lauf Häufigkeit für synthetische Transaktionen
<a name="special_synthetictrans"> </a>

Standardmäßig werden synthetische Transaktionen alle 15 Minuten mit den konfigurierten Benutzern ausgeführt. Synthetische Transaktionen werden nacheinander in einer Gruppe von Benutzern ausgeführt, um zu vermeiden, dass zwei synthetische Transaktionen miteinander in Konflikt stehen. Es ist ein längeres Intervall erforderlich, um Zeit für die Ausführung aller synthetischen Transaktionen bereitzustellen.
  
Wenn es wünschenswert ist, synthetische Transaktionen häufiger auszuführen, sollte die Anzahl der synthetischen Transaktionen, die mit einer bestimmten Gruppe von Benutzern ausgeführt werden, verringert werden, damit die Tests im gewünschten Zeitbereich mit einem Puffer für gelegentliche Netzwerkverzögerungen abgeschlossen werden können. Wenn das Ausführen von mehr synthetischen Transaktionen wünschenswert ist, erstellen Sie weitere Benutzergruppen, um zusätzliche synthetische Transaktionen auszuführen.
  
Führen Sie die folgenden Schritte aus, um die Häufigkeit zu ändern, mit der synthetische Transaktionen ausgeführt werden:
  
1. Öffnen Sie System Center Operations Manager. Klicken Sie auf Erstellungs Abschnitt. Klicken Sie auf Rules section (unter Authoring).
    
2. Suchen Sie im Abschnitt Regeln nach der Regel mit dem Namen "primäre synthetische Transaktions Runner-Leistungssammlungsregel".
    
3. Klicken Sie mit der rechten Maustaste auf die Regel, und wählen Sie Außerkraftsetzungen, die Regel außer Kraft setzen aus, und wählen Sie dann "für alle Objekte der Klasse: Pool Watcher" aus.
    
4. Wählen Sie im Fenster Außerkraftsetzungseigenschaften die Option Parameter Name "Frequency" aus, und legen Sie den Außerkraftsetzungswert auf den gewünschten Wert fest.
    
5. Wählen Sie im gleichen Fenster das Management Pack aus, auf das diese Außerkraftsetzung angewendet werden muss.
    
## <a name="using-rich-logging-for-synthetic-transactions"></a>Verwenden von erweiterter Protokollierung für synthetische Transaktionen
<a name="special_synthetictrans"> </a>

Synthetische Transaktionen sind äußerst hilfreich, um Probleme mit dem System zu identifizieren. Beispielsweise könnte das Test-CsRegistration-Cmdlet Administratoren darauf hinweisen, dass die Benutzer bei der Registrierung bei Skype for Business Server Schwierigkeiten hatten. Es sind jedoch möglicherweise zusätzliche Details erforderlich, um die tatsächliche Ursache eines Fehlers zu ermitteln.
  
Aus diesem Grund bieten synthetische Transaktionen umfangreiche Protokollierung. Bei der umfangreichen Protokollierung werden für jede Aktivität, die eine synthetische Transaktion unternimmt, die folgenden Informationen aufgezeichnet:
  
- Die Zeit, zu der die Aktivität gestartet wurde.
    
- Die Zeit, zu der die Aktivität abgeschlossen wurde.
    
- Die Aktion, die ausgeführt wurde (beispielsweise zum Erstellen, hinzufügen oder verlassen einer Konferenz; Anmelden bei Skype for Business Server; senden einer Sofortnachricht).
    
- Informations-, ausführliche, Warn-oder Fehlermeldungen, die beim Ausführen der Aktivität generiert wurden.
    
- SIP-Registrierungsnachrichten.
    
- Ausnahmedaten Sätze oder Diagnosecodes, die beim Ausführen der Aktivität generiert wurden.
    
- Das Ergebnis der Ausführung der Aktivität.
    
Diese Informationen werden automatisch jedes Mal generiert, wenn eine synthetische Transaktion ausgeführt wird, aber nicht automatisch angezeigt oder in einer Protokolldatei gespeichert wird. Wenn Sie eine synthetische Transaktion manuell durchführen, können Sie den OutLoggerVariable-Parameter verwenden, um eine Windows PowerShell Variable anzugeben, in der die Informationen gespeichert werden. Von dort haben Sie die Möglichkeit, eine der beiden folgenden Methoden zum Speichern und/oder Anzeigen von Fehlermeldungen im Rich-Protokoll im XML-oder HTML-Format zu verwenden. 
  
Um die Informationen zur Problembehandlung abzurufen, geben Sie den OutLoggerVariable-Parameter an, gefolgt von einem Variablennamen, den Sie auswählen:
  
```PowerShell
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> Stellen Sie dem Variablennamen kein $-Zeichen voran. Verwenden Sie einen Variablennamen wie RegistrationTest (nicht $RegistrationTest). 
  
Wenn Sie diesen Befehl ausführen, wird die Ausgabe ähnlich der folgenden angezeigt:
  
Ziel-FQDN: ATL-CS-001.litwareinc.com Ergebnis: Fehlerwartezeit: 00:00:00 Fehlermeldung: dieser Computer verfügt über keine zugewiesenen Zertifikate. Diagnose: Sie können auf ausführlichere Informationen für diesen Fehler zugreifen, als nur die hier gezeigte Fehlermeldung.

Um auf diese Informationen im HTML-Format zuzugreifen, verwenden Sie einen Befehl wie den folgenden, um die in der Variablen RegistrationTest gespeicherten Informationen in einer HTML-Datei zu speichern:
  
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
> Standardmäßig speichert Skype for Business Server Protokolldateien in einem Ordner, der nicht freigegeben ist. Damit diese Protokolle leicht zugänglich sind, sollten Sie diesen Ordner freigeben. Beispiel: \\ATL-Watcher-001. litwareinc. com\WatcherNode. 
