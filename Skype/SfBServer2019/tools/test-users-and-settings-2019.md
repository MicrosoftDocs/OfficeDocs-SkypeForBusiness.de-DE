---
title: Konfigurieren von Testbenutzern und Einstellungen für Monitorknoten
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/13/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Zusammenfassung: Konfigurieren von Testbenutzerkonten und Watcher-Knoten-Einstellungen für Skype für synthetische Transaktionen Business Server.'
ms.openlocfilehash: 3348d0407321ca53a771e2783b0f27c6463143f4
ms.sourcegitcommit: 139b3d3b7fcc1dd7fba7fd14ff34e4ffdfcc7eeb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2018
ms.locfileid: "26216121"
---
# <a name="configure-watcher-node-test-users-and-settings"></a>Konfigurieren von Testbenutzern und Einstellungen für Monitorknoten
 
**Zusammenfassung:** Konfigurieren von Testbenutzerkonten und Watcher-Knoten-Einstellungen für Skype für synthetische Transaktionen Business Server.
  
Nachdem Sie den Computer konfiguriert haben, der als Watcher-Knoten agieren wird, müssen Sie die folgenden Schritte ausführen:
  
1. [Konfigurieren von Testbenutzerkonten](test-users-and-settings-2019.md#testuser) von diese Watcher-Knoten verwendet werden. Wenn Sie die Aushandlungsauthentifizierungsmethode verwenden, müssen Sie auch das Cmdlet **Set-CsTestUserCredential** verwenden, um die Verwendung dieser Testkonten auf dem Watcher-Knoten zu aktivieren.
    
2. Aktualisieren Sie die Konfigurationseinstellungen für den Watcher-Knoten.
    
## <a name="configure-test-user-accounts"></a>Konfigurieren von Testbenutzerkonten
<a name="testuser"> </a>

Testkonten müssen keine tatsächliche Personen darstellen, jedoch muss es sich um gültige Active Directory-Konten. Darüber hinaus dieser Konten müssen für Skype für Business Server aktiviert werden, über eine gültige SIP-Adressen verfügen, und sie für Enterprise-VoIP (zur Verwendung von der synthetischen Transaktionsprotokolls Test-CsPstnPeerToPeerCall) aktiviert werden soll. 
  
Wenn Sie die TrustedServer-Authentifizierungsmethode verwenden, müssen Sie lediglich sicherstellen, dass diese Konten vorhanden sind und wie bereits erwähnt konfiguriert werden. Sie sollten für jeden zu testenden Pool mindestens drei Testbenutzer zuweisen. Wenn Sie die Authentifizierungsmethode verhandeln verwenden, müssen Sie auch die Cmdlets "Set-cstestusercredential" verwenden, und die Skype für Business Server-Verwaltungsshell, um diese zu aktivieren Testkonten synthetischen Transaktionen entwickelt. Dazu führen einen Befehl ähnlich dem folgenden (diese Befehle wird davon ausgegangen, dass die folgenden drei Active Directory-Benutzerkonten erstellt wurden und dass diese Konten für Skype für Business Server aktiviert sind):
  
```
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"
```

Sie müssen zusätzlich zur SIP-Adresse auch den Benutzernamen und das Kennwort einfügen. Wenn Sie das Kennwort nicht einfügen, werden Sie vom Set-CsTestUserCredential-Cmdlet zur Eingabe dieser Informationen aufgefordert. Der Benutzername kann im Format „Domänenname\Benutzername“, das im vorangehenden Codeblock gezeigt wurde, verwendet werden.
  
Um sicherzustellen, dass die testbenutzeranmeldeinformationen erstellt wurden, führen Sie diese Befehle an der Skype für Business Server-Verwaltungsshell:
  
```
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"
```

Daraufhin werden für jeden Benutzer Informationen zurückgegeben werden, die den Folgenden ähneln:
  
|**Benutzername**|**Kennwort**|
|:-----|:-----|
|Litwareinc\watcher1  <br/> |System.Security.SecureString  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a>Konfigurieren eines einfachen Watcher-Knotens mit den synthetischen Standardtransaktionen

Nachdem die Testbenutzer erstellt wurden, können Sie mithilfe eines Befehls, der dem Folgenden ähnelt, einen Watcher-Knoten erstellen:
  
```
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

Mithilfe dieses Befehls wird ein neuer Watcher-Knoten erstellt, für den die Standardeinstellungen verwendet werden und der die Standardgruppe synthetischer Transaktionen ausführt. Für den neuen Watcher-Knoten werden zudem die Testbenutzer watcher1@litwareinc.com, watcher2@litwareinc.com und watcher3@litwareinc.com verwendet. Wenn der Watcher-Knoten die TrustedServer-Authentifizierung verwendet, kann es sich bei den drei Testkonten um beliebige gültige Benutzerkonten handeln, die für Active Directory und Skype for Business Server aktiviert sind. Wenn der Watcher-Knoten die Negotiate-Authentifizierungsmethode verwendet, müssen Sie diese Benutzerkonten auch für den Watcher-Knoten aktivieren, indem Sie das Cmdlet Set-CsTestUserCredential verwenden.
  
Um zu überprüfen, ob die automatische Ermittlung des Zielpools zur Anmeldung ordnungsgemäß konfiguriert ist, führen Sie diese Schritte aus, statt einen Pool direkt vorzugeben:
  
```
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a>Konfigurieren erweiterter Tests

Wenn Sie den PSTN-Test aktivieren möchten, mit dessen Hilfe die Verbindung mit dem Telefonfestnetz überprüft wird, müssen Sie beim Einrichten des Watcher-Knotens einige zusätzliche Konfigurationsschritte ausführen. Zuerst müssen Sie die Testbenutzer dem PSTN-Testtyp zuweisen. Führen Sie dazu in der Skype for Business Server-Verwaltungsshell einen Befehl aus, der dem Folgenden ähnelt:
  
```
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> Die Ergebnisse dieses Befehls müssen in einer Variablen gespeichert werden. In diesem Beispiel handelt es sich dabei um die Variable $pstnTest. 
  
Das Cmdlet **"New-cswatchernodeconfiguration"** können Sie im nächsten Schritt Testtyp (in der Variablen $pstnTest gespeichert), um einen Skype für Business Server-Pool zuordnen. Mithilfe des folgenden Befehls wird beispielsweise eine neue Watcher-Knotenkonfiguration für den Pool atl-cs-001.litwareinc.com erstellt, wobei die drei zuvor erstellten Testbenutzer und der PSTN-Testtyp hinzugefügt werden:
  
```
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

Der zuvor angeführte Befehl gibt einen Fehler zurück, wenn Sie die Skype for Business Server-Hauptdateien und die RTCLocal-Datenbank nicht auf dem Computer des Watcher-Knotens installiert haben. 
  
Wenn Sie mehrere VoIP-Richtlinien testen möchten, können Sie für alle Richtlinien mithilfe des Cmdlets **New-CsExtendedTest** einen erweiterten Test erstellen. Die diesem Test zugewiesenen Benutzer müssen mit den gewünschten VoIP-Richtlinien konfiguriert werden. Die erweiterten Tests werden mit Komma-Trennzeichen an das Cmdlet **New-CsWatcherNodeConfiguration** übergeben, zum Beispiel:
  
-ExtendedTests @{Add = pstnTest1$, pstnTest2$, $pstnTest3}
  
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
    
- MCXP2PIM (instant messaging-legacy Mobilgerät)
    
- P2PVideoInteropServerSipTrunkAV
    
- PersistentChatMessage
    
- PSTN (PSTN-Gatewayanrufe, angegeben als erweiterter Test)
    
- UcwaConference
    
- UnifiedContactStore
    
- XmppIM
    
### <a name="adding-and-removing-synthetic-transactions"></a>Hinzufügen und Entfernen synthetischer Transaktionen

Nachdem ein Watcher-Knoten konfiguriert wurde, können Sie dem Knoten mithilfe des Cmdlets Set-CsWatcherNodeConfiguration synthetische Transaktionen hinzufügen oder Knoten daraus entfernen. Wenn Sie beispielsweise dem Watcher-Knoten den Test PersistentChatMessage hinzufügen möchten, verwenden Sie die Add-Methode und einen Befehl, der dem Folgenden ähnelt:
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}
```

Sie können mehrere Tests hinzufügen, indem Sie die Testnamen durch Kommas voneinander trennen. Beispiel:
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}
```

Ein Fehler tritt auf, wenn einer oder mehrere dieser Tests (z. B. DataConference) bereits für den Watcher-Knoten aktiviert wurden. In diesem Fall erhalten Sie eine Fehlermeldung, die der Folgenden ähnelt:
  
Set-CsWatcherNodeConfiguration: There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.
  
Wenn dieser Fehler auftritt, werden keine Änderungen wirksam. Führen Sie den Befehl erneut aus, nachdem Sie den doppelten Test entfernt haben.
  
Wenn Sie eine synthetische Transaktion aus einem Watcher-Knoten entfernen möchten, verwenden Sie die Remove-Methode. Mithilfe des folgenden Befehls wird beispielsweise der ABWQ-Test aus einem Watcher-Knoten entfernt:
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

Sie können die Replace-Methode verwenden, um alle momentan aktivierten Tests durch einen oder mehrere neue Tests zu ersetzen. Wenn Sie beispielsweise möchten, dass ein Watcher-Knoten nur den IM-Test ausführt, können Sie dieses Verhalten mithilfe des folgenden Befehls konfigurieren:
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

Wenn Sie diesen Befehl ausführen, werden mit Ausnahme von IM alle synthetischen Transaktionen für den angegebenen Watcher-Knoten deaktiviert.
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a>Anzeigen und Testen der Konfiguration des Watcher-Knotens

Wenn Sie die Tests anzeigen möchten, die einem Watcher-Knoten zugewiesen wurden, verwenden Sie einen Befehl, der dem Folgenden ähnelt:
  
```
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

Mithilfe dieses Befehls werden je nach den synthetischen Transaktionen, die dem Knoten zugewiesen wurden, Informationen zurückgegeben, die den Folgenden ähneln:
  
Registrierung Sofortnachrichten GroupIM P2PAV AvConference Anwesenheit PersistentChatMessage DataConference
> [!TIP]
> Wenn Sie die synthetischen Transaktionen in alphabetischer Reihenfolge anzeigen möchten, verwenden Sie stattdessen den folgenden Befehl: 
  
```
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

Wenn Sie überprüfen möchten, ob ein Watcher-Knoten erstellt wurde, geben Sie den folgenden Befehl über die Skype for Business Server-Verwaltungsshell ein:
  
```
Get-CsWatcherNodeConfiguration
```

Sie erhalten Informationen, die den Folgenden ähneln:
  
Identität: "Atl-Cs-001.litwareinc.com" TestUsers: {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com...} ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...} "Targetfqdn": "Atl-Cs-001.litwareinc.com" Portnummer: 5061To stellen Sie sicher, dass der Watcher-Knoten konfiguriert wurde ordnungsgemäß funktioniert, geben Sie den folgenden Befehl aus der Skype für Business Server-Verwaltungsshell:
  
```
Test-CsWatcherNodeConfiguration
```

Mit diesem Befehl werden alle Watcher-Knoten in Ihrer Bereitstellung getestet und überprüft, ob die folgenden Aktionen durchgeführt wurden:
  
- Ob die erforderliche Registrar-Rolle installiert wurde
    
- Ob der erforderliche Registrierungsschlüssel erstellt wurde (abgeschlossen, als Sie das Cmdlet Set-CsWatcherNodeConfiguration ausgeführt haben)
    
- Ob auf Ihren Servern die richtige Version von Skype for Business Server ausgeführt wird
    
- Ob Ihre Ports ordnungsgemäß konfiguriert wurden
    
- Ob die zugewiesenen Testbenutzer über die erforderlichen Anmeldeinformationen verfügen
    
## <a name="managing-watcher-nodes"></a>Verwalten von Watcher-Knoten
<a name="testuser"> </a>

Mit dem **Set-CsWatcherNodeConfiguration**-Cmdlet können Sie nicht nur die auf einem Watcher-Knoten ausgeführten synthetischen Transaktionen ändern, sondern auch noch zwei andere wichtige Aufgaben durchführen: das Aktivieren und Deaktivieren des Watcher-Knotens sowie das Konfigurieren des Watcher-Knotens zur Verwendung interner oder externer Web-URLs beim Durchführen seiner Tests.
  
In der Standardeinstellung führen Watcher-Knoten in regelmäßigen Abständen alle für sie aktivierten synthetischen Transaktionen aus. Manchmal müssen solche Transaktionen jedoch angehalten werden. Wenn der Watcher-Knoten zum Beispiel vorübergehend vom Netzwerk getrennt ist, liegt kein Grund vor, dass die synthetischen Transaktionen ausgeführt werden. Ohne Verbindung mit dem Netzwerk würden solche Transaktionen fehlschlagen. Wenn Sie einen Watcher-Knoten vorübergehend deaktivieren, führen Sie in der Skype for Business Server-Verwaltungsshell einen Befehl aus, der in etwa so aussieht:
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

Dieser Befehl deaktiviert die Ausführung synthetischer Transaktionen auf dem Watcher-Knoten „atl-watcher- 001.litwareinc.com“. Wenn die synthetischen Transaktionen wieder aufgenommen werden sollen, setzen Sie die Eigenschaft „Enabled“ wieder zurück auf „True“ ($True):
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> Mithilfe der Eigenschaft „Enabled“ können Watcher-Knoten ein- und ausgeschaltet werden. Wenn Sie einen Watcher-Knoten dauerhaft löschen möchten, verwenden Sie das **Remove-CsWatcherNodeConfiguration**-Cmdlet:
  
```
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

Dieser Befehl entfernt auf dem angegebenen Computer alle Konfigurationseinstellungen für Watcher-Knoten, sodass auf diesem Computer keine synthetischen Transaktionen mehr automatisch ausgeführt werden. Der Befehl wird jedoch nicht der System Center-Agent-Dateien oder das Skype für Systemdateien Business Server deinstalliert.
  
In der Standardeinstellung verwenden Watcher-Knoten bei der Durchführung ihrer Tests externe Web-URLs des Unternehmens. Es ist jedoch auch möglich, die Verwendung interner Web-URLs zu konfigurieren. Dies ermöglicht es Administratoren, den URL-Zugriff für innerhalb des Umkreisnetzwerks befindliche Benutzer zu überprüfen. Wenn Sie einen Watcher-Knoten so konfigurieren möchten, dass er interne anstatt externe URLs verwendet, legen Sie die Eigenschaft UseInternalWebURls auf „True“ ($True) fest:
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

Zurücksetzen dieser Eigenschaft auf den Standardwert „False“ ($False) führt dazu, dass der Watcher-Knoten wieder externe URLs verwendet:
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a>Besondere Anweisungen zum Einrichten von synthetischen Transaktionen
<a name="special_synthetictrans"> </a>

Die meisten synthetischen Transaktionen können auf einem Watcher-Knoten ohne größere Umstände ausgeführt werden. Sobald eine synthetische Transaktion den Konfigurationseinstellungen des Watcher-Knotens hinzugefügt wurde, kann sie in den meisten Fällen vom Watcher-Knoten bei seinen Testdurchläufen eingesetzt werden. Allerdings gibt es einige synthetische Transaktionen, für die spezielle Einrichtungsschritte erforderlich sind, wie in den nächsten Abschnitten erklärt.
  
### <a name="data-conferencing-synthetic-transaction"></a>Synthetische Transaktion für Datenkonferenzen

Wenn sich Ihr Watcher-Knoten-Computer außerhalb Ihres Umkreisnetzwerks befindet, werden Sie die synthetische Transaktion für Datenkonferenzen wahrscheinlich erst dann ausführen können, nachdem Sie zuerst die Proxyeinstellungen für den Windows Internet Explorer®-Internetbrowser für das Konto „Netzwerkdienst“ mithilfe der folgenden Schritte deaktiviert haben:
  
1. Klicken Sie auf dem Watcher-Knoten-Computer auf **Start**, **Alle Programme** und **Zubehör**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung** und klicken Sie dann auf **Als Administrator ausführen**.
    
2. Geben Sie im Konsolenfenster den folgenden Befehl ein und drücken Sie dann die EINGABETASTE. 
    
```
bitsadmin /util /SetIEProxy NetworkService NO_PROXY
```

Die folgende Meldung wird im Befehlsfenster angezeigt:
  
BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.
  
Internet proxy settings for account NetworkService set to NO_PROXY. 
  
(connection = default)
  
Diese Meldung weist darauf hin, dass Sie die Internet Explorer-Proxyeinstellungen für das Konto „Netzwerkdienst“ deaktiviert haben.
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a>Synthetische Transaktionen „Exchange Unified Messaging“

Die synthetischen Transaktion „Exchange Unified Messaging“ (UM) überprüft, ob Testbenutzer eine Verbindung zu in Exchange geführten Voicemail-Konten herstellen können.
  
Die Testbenutzer müssen mit Voicemail-Konten vorkonfiguriert werden. 
  
### <a name="persistent-chat-synthetic-transaction"></a>Synthetische Transaktion „Beständiger Chat“

Für die Verwendung der synthetischen Transaktion „Beständiger Chat“ müssen Sie zuerst einen Kanal erstellen und den Testbenutzern die Berechtigung für dessen Verwendung erteilen.
  
Sie können die synthetische Transaktion „Beständiger Chat“ zum Konfigurieren dieses Kanals verwenden: 
  
```
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
    
- VoIP-Richtlinien und VoIP-Routen, mit denen Sie Anrufe an die der Nummer des Empfängers das PSTN-Gateway erreichen können.
    
- Ein PSTN-Gateway, das akzeptiert Anruf und Medien, die Routen der Anrufe zurück zum Homepool des Empfängers, basierend auf der Anzahl gewählt.
    
### <a name="unified-contact-store-synthetic-transaction"></a>Synthetische Transaktion für den einheitlichen Kontaktspeicher

Die synthetische Transaktion Unified Contact Store überprüft die Fähigkeit von Skype für Business Server Kontakte im Auftrag eines Benutzers von Exchange abrufen.
  
Für die Verwendung dieser synthetischen Transaktion müssen die folgenden Bedingungen erfüllt sein:
  
- Lyss-Exchange-Server-Server-Authentifizierung muss konfiguriert sein.
    
- Testbenutzer müssen ein gültiges Exchange-Postfach besitzen.
    
Wenn diese Bedingungen erfüllt sind, können Sie das folgenden Windows PowerShell-Cmdlet zum Migrieren der Testbenutzer Kontaktlisten in Exchange ausführen:
  
```
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

Es kann einige Zeit dauern, bis die Migration der Testbenutzer-Kontaktlisten Migration nach Exchange abgeschlossen ist. Um den Migrationsstatus zu überwachen, kann die gleiche Command-Line ohne das - Setup-Flag ausgeführt werden:
  
```
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

Diese Befehlszeile hat nach Abschluss der Migration Erfolg.
  
### <a name="xmpp-synthetic-transaction"></a>Synthetische XMPP-Transaktion

Für die synthetische XMPP-IM-Transaktion (Extensible Messaging and Presence Protocol) ist es erforderlich, dass Sie die XMPP-Funktion mit einer oder mehreren Verbunddomänen konfigurieren.
  
Zum Aktivieren der synthetischen XMPP-Transaktion müssen Sie den Parameter XmppTestReceiverMailAddress mit einem Benutzerkonto bei einer routingfähigen XMPP-Domäne angeben. Beispiel:
  
```
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

In diesem Beispiel wird eine Skype für Business Server Regel muss zum Weiterleiten von Nachrichten für "litwareinc.com" zu einem XMPP-Gateway vorhanden sein.

> [!NOTE]
> XMPP-Gateways und -Proxys wurden in Skype für Business Server 2015 verfügbar, jedoch werden in Skype für Business Server 2019 nicht mehr unterstützt. Weitere Informationen finden Sie unter [Migrieren von XMPP-Verbund](../migration/migrating-xmpp-federation.md) .
  
### <a name="video-interop-server-vis-synthetic-transaction"></a>Synthetische VIS-Transaktion (Video Interop Server)

Die synthetische VIS-Transaktion (Video Interop Server) erfordert, dass Sie die Supportdateien für die synthetische Transaktion herunterladen und installieren ([VISSTSupportPackage.msi](https://www.microsoft.com/en-us/download/details.aspx?id=46921)). 
  
Für die Installation der Datei VISSTSupportPackage.msi stellen Sie sicher, dass die Abhängigkeiten (unter Systemanforderungen) für die MSI-Datei bereits installiert sind. Führen Sie VISSTSupportPackage.msi aus, um eine einfache Installation durchzuführen. MSI-Datei installiert alle Dateien in den folgenden Pfad: "%ProgramFiles%\VIS synthetische Transaktion Support-Paket".
  
Weitere Informationen zum Ausführen von die synthetische Transaktion gegenüber finden Sie in der Dokumentation für das Cmdlet [Test-CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/en-us/library/dn985894.aspx) .
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a>Ändern der Häufigkeit für die Ausführung synthetischer Transaktionen
<a name="special_synthetictrans"> </a>

Standardmäßig werden synthetische Transaktionen mit den konfigurierten Benutzern alle 15 Minuten ausgeführt. Synthetische Transaktionen werden nacheinander innerhalb einer Gruppe von Benutzern ausgeführt, um zu vermeiden, dass zwei synthetische Transaktionen miteinander in Konflikt stehen. Ein längeres Intervall ist erforderlich, damit genügend Zeit für den Abschluss aller synthetischen Transaktionen zur Verfügung steht.
  
Wenn es wünschenswert ist, synthetische Transaktionen häufiger auszuführen, sollte die Anzahl synthetischer Transaktionen, die mit einer vorgegebenen Gruppe von Benutzern ausgeführt wird, verringert werden, damit die Tests im gewünschten Zeitraum mit einem Puffer für gelegentliche Netzwerkverzögerungen abgeschlossen werden können. Wenn es wünschenswert ist, mehr synthetische Transaktionen auszuführen, erstellen Sie weitere Benutzergruppen, um zusätzliche synthetische Transaktionen auszuführen.
  
So ändern Sie die Häufigkeit, mit der synthetischen Transaktionen ausgeführt werden:
  
1. Öffnen Sie System Center Operations Manager. Klicken Sie auf den Abschnitt „Konfiguration. Klicken Sie auf den Abschnitt „Regeln“ (unter „Konfiguration“).
    
2. Suchen Sie im Abschnitt Regeln die Regel mit dem Namen "Main synthetische Transaktion Testprogramm Leistung Collection Rule"
    
3. Klicken Sie mit der rechten Maustaste auf die Regel, und wählen Sie Außerkraftsetzungen, wählen Sie die Regel Außerkraftsetzung und wählen Sie dann "für alle Objekte der Klasse: Pool Watcher"
    
4. Wählen Sie im Fenster Eigenschaften außer Kraft setzen Name des Parameters "Häufigkeit" aus, und legen Sie den Wert außer Kraft setzen, zu dem gewünschten.
    
5. Im selben Fenster wählen Sie das Management Pack aus, auf das die Überschreibung angewendet werden muss
    
## <a name="using-rich-logging-for-synthetic-transactions"></a>Verwenden von erweiterter Protokollierung für synthetische Transaktionen
<a name="special_synthetictrans"> </a>

Synthetische Transaktionen sind äußerst nützlich, um Probleme mit dem System zu identifizieren. Beispiel: Das Cmdlet Test-CsRegistration kann Administratoren darauf aufmerksam machen, dass Benutzer Schwierigkeiten haben, sich bei Skype for Business Server zu registrieren. Es können jedoch zusätzliche Details erforderlich sein, um die tatsächliche Fehlerursache festzustellen.
  
Aus diesem Grund stellen synthetische Transaktionen umfassende Protokollierung bereit. Dabei werden für jede Aktivität, die eine synthetische Transaktion unternimmt, die folgenden Informationen aufgezeichnet:
  
- Die Uhrzeit, zu der die Aktivität begann.
    
- Die Uhrzeit, zu der die Aktivität endete.
    
- Die Aktion, die durchgeführt wurde (z. B. Erstellen, Beitreten zu oder Verlassen einer Konferenz, Anmelden bei Skype for Business Server, Senden einer Chatnachricht).
    
- Informative oder ausführliche Meldungen bzw. Warn- oder Fehlermeldungen, die beim Ausführen der Aktivität generiert wurden
    
- Meldungen zur SIP-Registrierung.
    
- Ausnahmedatensätze oder Diagnosecodes, die beim Ausführen der Aktivität generiert wurden.
    
- Das Resultat der Aktivitätsausführung.
    
Diese Informationen werden bei jeder Ausführung einer synthetischen Transaktion automatisch generiert. Sie werden jedoch nicht automatisch angezeigt oder in einer Protokolldatei gespeichert. Wenn Sie eine synthetische Transaktion manuell durchführen, können Sie den Parameter OutLoggerVariable verwenden, um eine Windows PowerShell-Variable anzugeben, in der diese Informationen gespeichert werden. Sie können dann das umfassende Protokoll mithilfe von Methoden entweder im XML- oder HTML-Format anzeigen und/oder speichern. 
  
Zum Abrufen der Informationen zur Problembehandlung geben Sie den Parameter OutLoggerVariable an, gefolgt von einem Variablennamen, den Sie auswählen:
  
```
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> : Der Name der Variablen mit dem Zeichen $ führen Sie nicht vorangestellt werden. Verwenden Sie einen Variablennamen wie RegistrationTest (nicht $RegistrationTest). 
  
Wenn Sie diesen Befehl ausführen, sehen Sie eine Ausgabe wie die folgende:
  
Ziel-Fqdn: "Atl-Cs-001.litwareinc.com" Ergebnis: Fehler bei Wartezeit: 00:00:00 Fehlermeldung: diesen Computer verfügt nicht über alle zugewiesenen Zertifikate. Diagnose: Sie ausführlichere Informationen für diesen Fehler als nur die hier angezeigten Fehlermeldung zugreifen können. Sie können einen ähnlichen Befehl wie den folgenden verwenden, um auf diese Informationen im HTML-Format zuzugreifen und die in der Variablen RegistrationTest gespeicherten Informationen in einer HTML-Datei zu speichern:
  
```
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

Alternativ können Sie die ToXML()-Methode verwenden, um Dateien in einer XML-Datei zu speichern:
  
```
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

Sie können diese Dateien mithilfe von Windows Internet Explorer, Microsoft Visual Studio oder einer beliebigen anderen Anwendung anzeigen, die HTML-/XML-Dateien öffnen kann.
  
Führen Sie in System Center Operations Manager von synthetische Transaktionen werden diese Protokolldateien für Fehler automatisch generiert. Diese Protokolle werden jedoch nicht generiert, wenn die Ausführung scheitert, bevor die synthetische Transaktion in Skype for Business Server PowerShell geladen und ausgeführt werden kann. 
  
> [!IMPORTANT]
> Skype für Business Server speichert standardmäßig Protokolldateien in einen Ordner, der nicht freigegeben ist. Um den Zugriff auf diese Protokolle zu ermöglichen, sollten Sie diesen Ordner freigeben. Beispiel: \\atl-watcher-001.litwareinc.com\WatcherNode. 