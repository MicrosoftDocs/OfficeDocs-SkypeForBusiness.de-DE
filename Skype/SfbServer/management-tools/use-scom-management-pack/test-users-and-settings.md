---
title: Konfigurieren von Testbenutzern und Einstellungen für Monitorknoten
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
description: 'Zusammenfassung: Konfigurieren von Testbenutzerkonten und Watcher-Knoten Einstellungen für synthetische Skype for Business Server-Transaktionen.'
ms.openlocfilehash: 877e7256c31bf5bf66f25e80c9625078cfc15b02
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888854"
---
# <a name="configure-watcher-node-test-users-and-settings"></a>Konfigurieren von Testbenutzern und Einstellungen für Monitorknoten
 
**Zusammenfassung:** Konfigurieren Sie Testbenutzerkonten und Watcher-Knoten Einstellungen für synthetische Skype for Business Server-Transaktionen.
  
Nachdem Sie den Computer konfiguriert haben, der als Watcher-Knoten agieren wird, müssen Sie die folgenden Schritte ausführen:
  
1. [Konfigurieren Sie Test Benutzerkonten](test-users-and-settings.md#testuser) , die von diesen Watcher-Knoten verwendet werden sollen. Wenn Sie die Aushandlungsauthentifizierungsmethode verwenden, müssen Sie auch das Cmdlet **Set-CsTestUserCredential** verwenden, um die Verwendung dieser Testkonten auf dem Watcher-Knoten zu aktivieren.
    
2. Aktualisieren Sie die Konfigurationseinstellungen für den Watcher-Knoten.
    
## <a name="configure-test-user-accounts"></a>Konfigurieren von Testbenutzerkonten
<a name="testuser"> </a>

Test Konten müssen keine tatsächlichen Personen darstellen, Sie müssen jedoch gültige Active Directory-Konten sein. Darüber hinaus müssen diese Konten für Skype for Business Server aktiviert sein, Sie müssen über gültige SIP-Adressen verfügen und für Enterprise-VoIP aktiviert sein (um die synthetische Test-CsPstnPeerToPeerCall-Transaktion zu verwenden). 
  
Wenn Sie die TrustedServer-Authentifizierungsmethode verwenden, müssen Sie lediglich sicherstellen, dass diese Konten vorhanden sind und wie bereits erwähnt konfiguriert werden. Sie sollten mindestens zwei Testbenutzer für jeden Pool zuweisen, den Sie testen möchten. Wenn Sie die Negotiate-Authentifizierungsmethode verwenden, müssen Sie auch das Cmdlet "Satz-CsTestUserCredential" und die Skype for Business Server-Verwaltungsshell verwenden, damit diese Testkonten mit den synthetischen Transaktionen funktionieren. Führen Sie dazu einen Befehl ähnlich wie den folgenden aus (bei diesen Befehlen wird davon ausgegangen, dass die beiden Active Directory-Benutzerkonten erstellt wurden und diese Konten für Skype for Business Server aktiviert sind):
  
```PowerShell
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
```

Sie müssen zusätzlich zur SIP-Adresse auch den Benutzernamen und das Kennwort einfügen. Wenn Sie das Kennwort nicht einfügen, werden Sie vom Set-CsTestUserCredential-Cmdlet zur Eingabe dieser Informationen aufgefordert. Der Benutzername kann im Format „Domänenname\Benutzername“, das im vorangehenden Codeblock gezeigt wurde, verwendet werden.
  
Führen Sie die folgenden Befehle aus der Skype for Business Server-Verwaltungsshell aus, um zu überprüfen, ob die Anmeldeinformationen des Testbenutzers erstellt wurden:
  
```PowerShell
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
```

Daraufhin werden für jeden Benutzer Informationen zurückgegeben werden, die den Folgenden ähneln:
  
|**UserName**|**Kennwort**|
|:-----|:-----|
|Litwareinc\watcher1  <br/> |System. Security. SecureString  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a>Konfigurieren eines einfachen Watcher-Knotens mit den synthetischen Standardtransaktionen

Nachdem die Testbenutzer erstellt wurden, können Sie mithilfe eines Befehls, der dem Folgenden ähnelt, einen Watcher-Knoten erstellen:
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

Mithilfe dieses Befehls wird ein neuer Watcher-Knoten erstellt, für den die Standardeinstellungen verwendet werden und der die Standardgruppe synthetischer Transaktionen ausführt. Der neue Watcher-Knoten verwendet auch die Testbenutzer watcher1@litwareinc.com und watcher2@litwareinc.com. Wenn der Watcher-Knoten die TrustedServer-Authentifizierung verwendet, können die beiden Testkonten alle gültigen Benutzerkonten sein, die für Active Directory und Skype for Business Server aktiviert sind. Wenn der Watcher-Knoten die Negotiate-Authentifizierungsmethode verwendet, müssen Sie diese Benutzerkonten auch für den Watcher-Knoten aktivieren, indem Sie das Cmdlet Set-CsTestUserCredential verwenden.
  
Um zu überprüfen, ob die automatische Ermittlung des Zielpools zur Anmeldung ordnungsgemäß konfiguriert ist, führen Sie diese Schritte aus, statt einen Pool direkt vorzugeben:
  
```PowerShell
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a>Konfigurieren erweiterter Tests

Wenn Sie den PSTN-Test aktivieren möchten, mit dessen Hilfe die Verbindung mit dem Telefonfestnetz überprüft wird, müssen Sie beim Einrichten des Watcher-Knotens einige zusätzliche Konfigurationsschritte ausführen. Zuerst müssen Sie die Testbenutzer dem PSTN-Testtyp zuweisen. Führen Sie dazu in der Skype for Business Server-Verwaltungsshell einen Befehl aus, der dem Folgenden ähnelt:
  
```PowerShell
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com" -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> Die Ergebnisse dieses Befehls müssen in einer Variablen gespeichert werden. In diesem Beispiel handelt es sich dabei um die Variable $pstnTest. 
  
Als nächstes können Sie das Cmdlet **New-CsWatcherNodeConfiguration** verwenden, um den in der Variablen $pstnTest gespeicherten Testtyp einem Skype for Business-Server Pool zuzuordnen. Mit dem folgenden Befehl wird beispielsweise eine neue Watcher-Knoten Konfiguration für den Pool ATL-CS-001.litwareinc.com erstellt, wobei die beiden zuvor erstellten Testbenutzer hinzugefügt und der PSTN-Testtyp hinzugefügt wurde:
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

Der zuvor angeführte Befehl gibt einen Fehler zurück, wenn Sie die Skype for Business Server-Hauptdateien und die RTCLocal-Datenbank nicht auf dem Computer des Watcher-Knotens installiert haben. 
  
Wenn Sie mehrere VoIP-Richtlinien testen möchten, können Sie für alle Richtlinien mithilfe des Cmdlets **New-CsExtendedTest** einen erweiterten Test erstellen. Die diesem Test zugewiesenen Benutzer müssen mit den gewünschten VoIP-Richtlinien konfiguriert werden. Die erweiterten Tests werden mit Komma-Trennzeichen an das Cmdlet **New-CsWatcherNodeConfiguration** übergeben, zum Beispiel:
  
-ExtendedTests @ {Add = $pstnTest 1, $pstnTest 2, $pstnTest 3}
  
Da das **New-CsWatcherNodeConfiguration**-Cmdlet ohne den Parameter „Tests“ aufgerufen wird, bedeutet dies, dass für den neuen Watcher-Knoten nur die synthetischen Standardtransaktionen (und die angegebene erweiterte synthetische Transaktion) aktiviert werden. Daher testet der Watcher-Knoten die folgenden Komponenten:
  
- Registrierung
    
- IM
    
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
    
- MCXP2PIM (Instant Messaging für Legacy-Mobile Geräte)
    
- P2PVideoInteropServerSipTrunkAV
    
- PersistentChatMessage
    
- PSTN (PSTN-Gatewayanrufe, angegeben als erweiterter Test)
    
- UcwaConference
    
- UnifiedContactStore
    
- XmppIM
    
### <a name="adding-and-removing-synthetic-transactions"></a>Hinzufügen und Entfernen synthetischer Transaktionen

Nachdem ein Watcher-Knoten konfiguriert wurde, können Sie dem Knoten mithilfe des Cmdlets Set-CsWatcherNodeConfiguration synthetische Transaktionen hinzufügen oder Knoten daraus entfernen. Wenn Sie beispielsweise dem Watcher-Knoten den Test PersistentChatMessage hinzufügen möchten, verwenden Sie die Add-Methode und einen Befehl, der dem Folgenden ähnelt:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}
```

Sie können mehrere Tests hinzufügen, indem Sie die Testnamen durch Kommas voneinander trennen. Beispiel:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}
```

Ein Fehler tritt auf, wenn einer oder mehrere dieser Tests (z. B. DataConference) bereits für den Watcher-Knoten aktiviert wurden. In diesem Fall erhalten Sie eine Fehlermeldung, die der Folgenden ähnelt:
  
Set-CsWatcherNodeConfiguration: There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.
  
Wenn dieser Fehler auftritt, werden keine Änderungen wirksam. Führen Sie den Befehl erneut aus, nachdem Sie den doppelten Test entfernt haben.
  
Wenn Sie eine synthetische Transaktion aus einem Watcher-Knoten entfernen möchten, verwenden Sie die Remove-Methode. Mithilfe des folgenden Befehls wird beispielsweise der ABWQ-Test aus einem Watcher-Knoten entfernt:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

Sie können die Replace-Methode verwenden, um alle momentan aktivierten Tests durch einen oder mehrere neue Tests zu ersetzen. Wenn Sie beispielsweise möchten, dass ein Watcher-Knoten nur den IM-Test ausführt, können Sie dieses Verhalten mithilfe des folgenden Befehls konfigurieren:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

Wenn Sie diesen Befehl ausführen, werden mit Ausnahme von IM alle synthetischen Transaktionen für den angegebenen Watcher-Knoten deaktiviert.
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a>Anzeigen und Testen der Konfiguration des Watcher-Knotens

Wenn Sie die Tests anzeigen möchten, die einem Watcher-Knoten zugewiesen wurden, verwenden Sie einen Befehl, der dem Folgenden ähnelt:
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

Mithilfe dieses Befehls werden je nach den synthetischen Transaktionen, die dem Knoten zugewiesen wurden, Informationen zurückgegeben, die den Folgenden ähneln:
  
Registrierung im GroupIM P2PAV AvConference Anwesenheits PersistentChatMessage dataconference
> [!TIP]
> Wenn Sie die synthetischen Transaktionen in alphabetischer Reihenfolge anzeigen möchten, verwenden Sie stattdessen den folgenden Befehl: 
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

Wenn Sie überprüfen möchten, ob ein Watcher-Knoten erstellt wurde, geben Sie den folgenden Befehl über die Skype for Business Server-Verwaltungsshell ein:
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

Sie erhalten Informationen, die den Folgenden ähneln:
  
Identität: ATL-CS-001.litwareinc.com <br/>
TestUsers: {SIP:watcher1@litwareinc.com, SIP:watcher2@litwareinc.com...}<br/>
ExtendedTests: {TestUsers = IList<System. String>; Name = PSTN-Test; Te...}<br/>
TargetFqdn: ATL-CS-001.litwareinc.com<br/>
PortNumber: 5061<br/>

Wenn Sie überprüfen möchten, ob der Watcher-Knoten ordnungsgemäß konfiguriert wurde, geben Sie den folgenden Befehl über die Skype for Business Server-Verwaltungsshell ein:
  
```PowerShell
Test-CsWatcherNodeConfiguration
```

Mit diesem Befehl werden alle Watcher-Knoten in Ihrer Bereitstellung getestet und überprüft, ob die folgenden Aktionen durchgeführt wurden:
  
- Die erforderliche Registrierungsstelle-Rolle ist installiert.
    
- Der erforderliche Registrierungsschlüssel wird erstellt (abgeschlossen, wenn Sie das Cmdlet "Satz-CsWatcherNodeConfiguration" ausgeführt haben).
    
- Auf Ihren Servern wird die richtige Version von Skype for Business Server ausgeführt.
    
- Ihre Ports sind ordnungsgemäß konfiguriert.
    
- Ihre zugewiesenen Testbenutzer verfügen über die erforderlichen Anmeldeinformationen.
    
## <a name="managing-watcher-nodes"></a>Verwalten von Watcher-Knoten
<a name="testuser"> </a>

Mit dem **Set-CsWatcherNodeConfiguration**-Cmdlet können Sie nicht nur die auf einem Watcher-Knoten ausgeführten synthetischen Transaktionen ändern, sondern auch noch zwei andere wichtige Aufgaben durchführen: das Aktivieren und Deaktivieren des Watcher-Knotens sowie das Konfigurieren des Watcher-Knotens zur Verwendung interner oder externer Web-URLs beim Durchführen seiner Tests.
  
In der Standardeinstellung führen Watcher-Knoten in regelmäßigen Abständen alle für sie aktivierten synthetischen Transaktionen aus. Manchmal müssen solche Transaktionen jedoch angehalten werden. Wenn der Watcher-Knoten zum Beispiel vorübergehend vom Netzwerk getrennt ist, liegt kein Grund vor, dass die synthetischen Transaktionen ausgeführt werden. Ohne Verbindung mit dem Netzwerk würden solche Transaktionen fehlschlagen. Wenn Sie einen Watcher-Knoten vorübergehend deaktivieren, führen Sie in der Skype for Business Server-Verwaltungsshell einen Befehl aus, der in etwa so aussieht:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

Dieser Befehl deaktiviert die Ausführung synthetischer Transaktionen auf dem Watcher-Knoten „atl-watcher- 001.litwareinc.com“. Wenn die synthetischen Transaktionen wieder aufgenommen werden sollen, setzen Sie die Eigenschaft „Enabled“ wieder zurück auf „True“ ($True):
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> Mithilfe der Eigenschaft „Enabled“ können Watcher-Knoten ein- und ausgeschaltet werden. Wenn Sie einen Watcher-Knoten dauerhaft löschen möchten, verwenden Sie das **Remove-CsWatcherNodeConfiguration**-Cmdlet:
  
```PowerShell
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

Dieser Befehl entfernt auf dem angegebenen Computer alle Konfigurationseinstellungen für Watcher-Knoten, sodass auf diesem Computer keine synthetischen Transaktionen mehr automatisch ausgeführt werden. Der Befehl deinstalliert jedoch nicht die System Center-Agentendateien oder die Skype for Business Server-Systemdateien.
  
In der Standardeinstellung verwenden Watcher-Knoten bei der Durchführung ihrer Tests externe Web-URLs des Unternehmens. Es ist jedoch auch möglich, die Verwendung interner Web-URLs zu konfigurieren. Dies ermöglicht es Administratoren, den URL-Zugriff für innerhalb des Umkreisnetzwerks befindliche Benutzer zu überprüfen. Wenn Sie einen Watcher-Knoten so konfigurieren möchten, dass er interne anstatt externe URLs verwendet, legen Sie die Eigenschaft UseInternalWebURls auf „True“ ($True) fest:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

Zurücksetzen dieser Eigenschaft auf den Standardwert „False“ ($False) führt dazu, dass der Watcher-Knoten wieder externe URLs verwendet:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a>Besondere Anweisungen zum Einrichten von synthetischen Transaktionen
<a name="special_synthetictrans"> </a>

Die meisten synthetischen Transaktionen können auf einem Watcher-Knoten ohne größere Umstände ausgeführt werden. Sobald eine synthetische Transaktion den Konfigurationseinstellungen des Watcher-Knotens hinzugefügt wurde, kann sie in den meisten Fällen vom Watcher-Knoten bei seinen Testdurchläufen eingesetzt werden. Allerdings gibt es einige synthetische Transaktionen, für die spezielle Einrichtungsschritte erforderlich sind, wie in den nächsten Abschnitten erklärt.
  
### <a name="data-conferencing-synthetic-transaction"></a>Synthetische Transaktion für Datenkonferenzen

Wenn sich Ihr Watcher-Knoten-Computer außerhalb Ihres Umkreisnetzwerks befindet, werden Sie die synthetische Transaktion für Datenkonferenzen wahrscheinlich erst dann ausführen können, nachdem Sie zuerst die Proxyeinstellungen für den Windows Internet Explorer®-Internetbrowser für das Konto „Netzwerkdienst“ mithilfe der folgenden Schritte deaktiviert haben:
  
1. Klicken Sie auf dem Watcher-Knoten-Computer auf **Start**, **Alle Programme** und **Zubehör**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung** und klicken Sie dann auf **Als Administrator ausführen**.
    
2. Geben Sie im Konsolenfenster den folgenden Befehl ein und drücken Sie dann die EINGABETASTE. 
    
    ```console
    bitsadmin /util /SetIEProxy NetworkService NO_PROXY
    ```

    Die folgende Meldung wird im Befehlsfenster angezeigt:

    ```console
    BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.
  
    Internet proxy settings for account NetworkService set to NO_PROXY. 
      
    (connection = default)
    ```
      
    Diese Meldung weist darauf hin, dass Sie die Internet Explorer-Proxyeinstellungen für das Konto „Netzwerkdienst“ deaktiviert haben.
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a>Synthetische Transaktionen „Exchange Unified Messaging“

Die synthetischen Transaktion „Exchange Unified Messaging“ (UM) überprüft, ob Testbenutzer eine Verbindung zu in Exchange geführten Voicemail-Konten herstellen können.
  
Die Testbenutzer müssen mit Voicemail-Konten vorkonfiguriert werden. 
  
### <a name="persistent-chat-synthetic-transaction"></a>Synthetische Transaktion „Beständiger Chat“

Für die Verwendung der synthetischen Transaktion „Beständiger Chat“ müssen Sie zuerst einen Kanal erstellen und den Testbenutzern die Berechtigung für dessen Verwendung erteilen.
  
Sie können die synthetische Transaktion „Beständiger Chat“ zum Konfigurieren dieses Kanals verwenden: 
  
```powershell
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true
```

Sie müssen diese Einrichtungsaufgabe auf einem Computer innerhalb des Unternehmens durchführen:
  
- Wenn das Cmdlet auf einem Computer ausgeführt wird, der kein Server ist, muss der entsprechende Benutzer bei rollenbasierter Zugriffssteuerung (RBAC) Mitglied der Rolle CsPersistentChatAdministrators sein.
    
- Wenn das Cmdlet auf dem Server selbst ausgeführt wird, muss der entsprechende Benutzer Mitglied der Gruppe RTCUniversalServerAdmins sein.
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a>Synthetische Transaktionen für Peer-zu-Peer-Festnetzanrufe

Die synthetische Test-CsPstnPeerToPeerCall-Transaktion überprüft, ob es möglich ist, Anrufe über das Festnetz zu tätigen und entgegenzunehmen.
  
Zum Ausführen dieser synthetischen Transaktion müssen Sie Folgendes konfigurieren:
  
- Zwei UC-fähige Testbenutzer (einen Anrufer und einen Empfänger)
    
- DID-Nummern (Direct Inward Dialing) für jedes Benutzerkonto
    
- VoIP-Richtlinien und VoIP-Routen, die Anrufe an die Rufnummer des Empfängers ermöglichen, um das PSTN-Gateway zu erreichen.
    
- Ein PSTN-Gateway, das Anrufe und Medien akzeptiert, die Anrufe zurück an den privaten Pool eines Empfängers weiterleiten, basierend auf der gewählten Nummer.
    
### <a name="unified-contact-store-synthetic-transaction"></a>Synthetische Transaktion für den einheitlichen Kontaktspeicher

Die synthetische Transaktion für den Unified Contact Store überprüft, ob Skype for Business Server Kontakte im Auftrag eines Benutzers aus Exchange abrufen kann.
  
Für die Verwendung dieser synthetischen Transaktion müssen die folgenden Bedingungen erfüllt sein:
  
- Lyss-Exchange-Server-Server-Authentifizierung muss konfiguriert sein.
    
- Testbenutzer müssen ein gültiges Exchange-Postfach besitzen.
    
Nachdem diese Bedingungen erfüllt sind, können Sie das folgende Windows PowerShell-Cmdlet ausführen, um die Kontaktlisten der Testbenutzer in Exchange zu migrieren:
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

Es kann einige Zeit dauern, bis die Migration der Testbenutzer-Kontaktlisten Migration nach Exchange abgeschlossen ist. Um den Migrationsstatus zu überwachen, kann dieselbe Befehlszeile ohne das-Setup-Flag ausgeführt werden:
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

Diese Befehlszeile hat nach Abschluss der Migration Erfolg.
  
### <a name="xmpp-synthetic-transaction"></a>Synthetische XMPP-Transaktion

Für die synthetische XMPP-IM-Transaktion (Extensible Messaging and Presence Protocol) ist es erforderlich, dass Sie die XMPP-Funktion mit einer oder mehreren Verbunddomänen konfigurieren.
  
Zum Aktivieren der synthetischen XMPP-Transaktion müssen Sie den Parameter XmppTestReceiverMailAddress mit einem Benutzerkonto bei einer routingfähigen XMPP-Domäne angeben. Beispiel:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

In diesem Beispiel muss eine Skype for Business-Server Regel vorhanden sein, damit Nachrichten für litwareinc.com an ein XMPP-Gateway weitergeleitet werden.

> [!NOTE]
> XMPP-Gateways und-Proxies sind in Skype for Business Server 2015 verfügbar, werden aber in Skype for Business Server 2019 nicht mehr unterstützt. Weitere Informationen finden Sie unter [Migrieren der XMPP-Föderation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) . 
  
### <a name="video-interop-server-vis-synthetic-transaction"></a>Synthetische VIS-Transaktion (Video Interop Server)

Für die synthetische Transaktion des Video Interop-Servers (VIS) müssen Sie die synthetischen Transaktions Unterstützungsdateien ([VISSTSupportPackage. msi](https://www.microsoft.com/en-us/download/details.aspx?id=46921)) herunterladen und installieren. 
  
Für die Installation der Datei VISSTSupportPackage.msi stellen Sie sicher, dass die Abhängigkeiten (unter Systemanforderungen) für die MSI-Datei bereits installiert sind. Führen Sie VISSTSupportPackage.msi aus, um eine einfache Installation durchzuführen. Mit der MSI-Datei werden alle Dateien im folgenden Pfad installiert: "%ProgramFiles%\VIS-synthetisches Transaktions Unterstützungspaket".
  
Weitere Informationen zum Ausführen der synthetischen VIS-Transaktion finden Sie in der Dokumentation für das Cmdlet [Test-CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/library/dn985894.aspx) .
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a>Ändern der Häufigkeit für die Ausführung synthetischer Transaktionen
<a name="special_synthetictrans"> </a>

Standardmäßig werden synthetische Transaktionen mit den konfigurierten Benutzern alle 15 Minuten ausgeführt. Synthetische Transaktionen werden nacheinander innerhalb einer Gruppe von Benutzern ausgeführt, um zu vermeiden, dass zwei synthetische Transaktionen miteinander in Konflikt stehen. Ein längeres Intervall ist erforderlich, damit genügend Zeit für den Abschluss aller synthetischen Transaktionen zur Verfügung steht.
  
Wenn es wünschenswert ist, synthetische Transaktionen häufiger auszuführen, sollte die Anzahl synthetischer Transaktionen, die mit einer vorgegebenen Gruppe von Benutzern ausgeführt wird, verringert werden, damit die Tests im gewünschten Zeitraum mit einem Puffer für gelegentliche Netzwerkverzögerungen abgeschlossen werden können. Wenn es wünschenswert ist, mehr synthetische Transaktionen auszuführen, erstellen Sie weitere Benutzergruppen, um zusätzliche synthetische Transaktionen auszuführen.
  
So ändern Sie die Häufigkeit, mit der synthetischen Transaktionen ausgeführt werden:
  
1. Öffnen Sie System Center Operations Manager. Klicken Sie auf den Abschnitt „Konfiguration. Klicken Sie auf Regelabschnitt (unter Dokumenterstellung).
    
2. Suchen Sie im Abschnitt Rules die Regel mit dem Namen "wichtigste synthetische Transaktions Runner-Leistungssammlungsregel".
    
3. Klicken Sie mit der rechten Maustaste auf die Regel, wählen Sie Außerkraftsetzungen, wählen Sie die Regel außer Kraft, und wählen Sie dann "für alle Objekte der Klasse: Pool Watcher" aus.
    
4. Wählen Sie im Fenster Außerkraftsetzungseigenschaften die Option Parameter Name "Frequency" aus, und legen Sie den Wert für override auf den gewünschten Wert ein.
    
5. Wählen Sie im gleichen Fenster das Management Pack aus, auf das diese Außerkraftsetzung angewendet werden muss.
    
## <a name="using-rich-logging-for-synthetic-transactions"></a>Verwenden von erweiterter Protokollierung für synthetische Transaktionen
<a name="special_synthetictrans"> </a>

Synthetische Transaktionen sind äußerst nützlich, um Probleme mit dem System zu identifizieren. Beispiel: Das Cmdlet Test-CsRegistration kann Administratoren darauf aufmerksam machen, dass Benutzer Schwierigkeiten haben, sich bei Skype for Business Server zu registrieren. Es können jedoch zusätzliche Details erforderlich sein, um die tatsächliche Fehlerursache festzustellen.
  
Aus diesem Grund stellen synthetische Transaktionen umfassende Protokollierung bereit. Dabei werden für jede Aktivität, die eine synthetische Transaktion unternimmt, die folgenden Informationen aufgezeichnet:
  
- Die Uhrzeit, zu der die Aktivität begann.
    
- Die Uhrzeit, zu der die Aktivität endete.
    
- Die Aktion, die durchgeführt wurde (z. B. Erstellen, Beitreten zu oder Verlassen einer Konferenz, Anmelden bei Skype for Business Server, Senden einer Chatnachricht).
    
- Informations-, Verbose-, Warnungs-oder Fehlermeldungen, die beim Ausführen der Aktivität generiert wurden.
    
- Meldungen zur SIP-Registrierung.
    
- Ausnahmedatensätze oder Diagnosecodes, die beim Ausführen der Aktivität generiert wurden.
    
- Das Resultat der Aktivitätsausführung.
    
Diese Informationen werden bei jeder Ausführung einer synthetischen Transaktion automatisch generiert. Sie werden jedoch nicht automatisch angezeigt oder in einer Protokolldatei gespeichert. Wenn Sie eine synthetische Transaktion manuell durchführen, können Sie den Parameter OutLoggerVariable verwenden, um eine Windows PowerShell-Variable anzugeben, in der diese Informationen gespeichert werden. Sie können dann das umfassende Protokoll mithilfe von Methoden entweder im XML- oder HTML-Format anzeigen und/oder speichern. 
  
Zum Abrufen der Informationen zur Problembehandlung geben Sie den Parameter OutLoggerVariable an, gefolgt von einem Variablennamen, den Sie auswählen:
  
```PowerShell
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> Führen Sie den Variablennamen nicht mit dem $-Zeichen vor. Verwenden Sie einen Variablennamen wie RegistrationTest (nicht $RegistrationTest). 
  
Wenn Sie diesen Befehl ausführen, sehen Sie eine Ausgabe wie die folgende:
  
Ziel-FQDN: ATL-CS-001.litwareinc.com-Ergebnis: Fehler Latenz: 00:00:00-Fehlermeldung: auf diesem Computer gibt es keine zugewiesenen Zertifikate. Diagnose: Sie können auf ausführlichere Informationen für diesen Fehler zugreifen, als nur die hier gezeigte Fehlermeldung.

Sie können einen ähnlichen Befehl wie den folgenden verwenden, um auf diese Informationen im HTML-Format zuzugreifen und die in der Variablen RegistrationTest gespeicherten Informationen in einer HTML-Datei zu speichern:
  
```PowerShell
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

Alternativ können Sie die ToXML()-Methode verwenden, um Dateien in einer XML-Datei zu speichern:
  
```PowerShell
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

Sie können diese Dateien mithilfe von Windows Internet Explorer, Microsoft Visual Studio oder einer beliebigen anderen Anwendung anzeigen, die HTML-/XML-Dateien öffnen kann.
  
Synthetische Transaktionen, die innerhalb von System Center Operations Manager ausgeführt werden, generieren diese Protokolldateien automatisch für Fehler. Diese Protokolle werden jedoch nicht generiert, wenn die Ausführung scheitert, bevor die synthetische Transaktion in Skype for Business Server PowerShell geladen und ausgeführt werden kann. 
  
> [!IMPORTANT]
> Skype for Business Server speichert standardmäßig Protokolldateien in einem nicht freigegebenen Ordner. Um den Zugriff auf diese Protokolle zu ermöglichen, sollten Sie diesen Ordner freigeben. Beispiel: \\ATL-Watcher-001. "litwareinc. com\WatcherNode. 
