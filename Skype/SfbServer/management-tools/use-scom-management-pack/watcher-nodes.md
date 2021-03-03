---
title: Installieren und Konfigurieren von Watcher-Knoten
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7392e4f8-6e2d-447b-aaa3-878f73995f9d
description: 'Zusammenfassung: Installieren und Konfigurieren von Watcher-Knoten für synthetische Skype for Business Server-Transaktionen.'
ms.openlocfilehash: f6d3db973291b8a41647a3c4a4d3c3530c7af019
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812754"
---
# <a name="install-and-configure-watcher-nodes"></a>Installieren und Konfigurieren von Watcher-Knoten
 
**Zusammenfassung:** Installieren und Konfigurieren von Watcher-Knoten für synthetische Skype for Business Server-Transaktionen.
  
Watcherknoten sind Computer, auf denen regelmäßig synthetische Skype for Business Server-Transaktionen ausgeführt werden. Synthetische Transaktionen werden Windows PowerShell cmdlets verwendet, die überprüfen, ob wichtige Benutzerszenarien, z. B. die Möglichkeit der Anmeldung oder des Austauschs von Chatnachrichten, wie erwartet funktionieren. Für Skype for Business Server 2015 kann System Center Operations Manager die in der folgenden Tabelle aufgeführten synthetischen Transaktionen ausführen, die drei synthetische Transaktionstypen enthalten:
  
- **Standard** Synthetische Transaktionen, die von einem Watcherknoten standardmäßig ausgeführt werden. Wenn Sie einen neuen Watcher-Knoten erstellen, können Sie angeben, welche synthetischen Transaktionen dieser Knoten ausführen soll. (Dies ist der Zweck des vom cmdlet New-CsWatcherNodeConfiguration verwendeten Parameters "Tests".) Wenn Sie beim Erstellen des Watcher-Knotens nicht den Parameter "Tests" verwenden, werden automatisch alle synthetischen Standardtransaktionen und keine der nicht standardmäßigen synthetischen Transaktionen ausgeführt. Dies bedeutet beispielsweise, dass der Watcherknoten für die Ausführung des Test-CsAddressBookService-Tests, aber nicht für die Ausführung des Test-CsExumConnectivity konfiguriert wird.
    
- **Nicht standardmäßig** Testet, ob Watcherknoten nicht standardmäßig ausgeführt werden. (Ausführliche Informationen finden Sie in der Beschreibung des Standardtyps.) Der Watcherknoten kann jedoch aktiviert werden, um alle nicht standardmäßigen synthetischen Transaktionen ausführen zu können. Sie können dies tun, wenn Sie den Watcherknoten (mithilfe des cmdlets New-CsWatcherNodeConfiguration) oder zu einem beliebigen Zeitpunkt nach dem Erstellen des Watcher-Knotens erstellen. Beachten Sie, dass viele der nicht standardmäßigen synthetischen Transaktionen zusätzliche Einrichtungsschritte erfordern. Weitere Informationen zu diesen Schritten finden Sie unter ["Spezielle Setupanweisungen für synthetische Transaktionen".](test-users-and-settings.md#special_synthetictrans)
    
- **Erweitert** Ein spezieller Typ von synthetischer Nicht-Standardtransaktion. Im Unterschied zu anderen synthetischen Transaktionen können sie bei jedem Durchgang mehrere Male ausgeführt werden. Dies ist bei der Überprüfung des Verhaltens hilfreich, z. B. bei mehreren PSTN-Sprachrouten für einen Pool. Sie können dies einfach konfigurieren, indem Sie einem Watcherknoten mehrere Instanzen eines erweiterten Tests hinzufügen.
    
Weitere Informationen zum Hinzufügen weiterer synthetischer Transaktionen zu einem Watcherknoten finden Sie unter "Konfigurieren eines [Watcher-Knotens](watcher-nodes.md#enable_synthetic_trans)zum Ausführen synthetischer Transaktionen". Sie können auch die Skype for Business Server-Verwaltungsshell verwenden, um synthetische Transaktionen aus einem Watcher-Knoten zu entfernen.
  
Zu den für Watcher-Knoten verfügbaren synthetischen Transaktionen gehören:
  
|**Cmdlet-Name (Test-Name)**|**Beschreibung**|
|:-----|:-----|
|Test-CsAddressBookService (ABS)  <br/> |Überprüft, ob Benutzer nach Benutzern suchen können, die nicht in ihrer Kontaktliste enthalten sind.  <br/> |
|Test-CsAddressBookWebQuery (ABWQ)  <br/> |Überprüft, ob Benutzer in der Lage sind, Benutzer nach oben zu suchen, die nicht über HTTP in ihrer Kontaktliste enthalten sind.  <br/> |
|Test-CsAVConference (AvConference)  <br/> |Überprüft, ob Benutzer in der Lage sind, eine Audio-/Videokonferenz zu erstellen und daran teilzunehmen.  <br/> |
|Test-CsGroupIM (Im-Konferenzen)  <br/> |Überprüft, ob Benutzer in der Lage sind, in Konferenzen Sofortnachrichten zu senden und an Sofortnachrichtengesprächen mit drei oder mehr Personen teilzunehmen.  <br/> |
|Test-CsIM (P2P-IM)  <br/> |Überprüft, ob Benutzer in der Lage sind, Peer-zu-Peer-Sofortnachrichten zu senden.  <br/> |
|Test-CsP2PAV (P2PAV)  <br/> |Überprüft, ob Benutzer in der Lage sind, Peer-zu-Peer-Audioanrufe zu tätigen (nur Signal).  <br/> |
|Test-CsPresence (Anwesenheit)  <br/> |Überprüft, ob Benutzer die Anwesenheit anderer Benutzer anzeigen können.  <br/> |
|Test-CsRegistration (Registrierung)  <br/> |Überprüft, ob sich Benutzer bei Skype for Business anmelden können.  <br/> |
|Test-CsPstnPeerToPeerCall (PSTN)  <br/> |Überprüft, ob Benutzer in der Lage sind, Anrufe von Personen außerhalb des Unternehmens (PSTN-Nummern) entgegenzunehmen oder diese anzurufen.  <br/> |
|Test-CsASConference (ASConference)  <br/> |Überprüft, ob Benutzer in der Lage sind, eine Konferenz zur Anwendungsfreigabe zu erstellen und daran teilzunehmen.  <br/> |
|Test-CsAVEdgeConnectivity (AVEdgeConnectivity)  <br/> |Überprüft, ob die Audiovideo-Edgeserver Verbindungen für Peer-zu-Peer-Anrufe und Konferenzanrufe annehmen können.  <br/> |
|Test-CsDataConference (DataConference)  <br/> |Überprüft, ob Benutzer an einer Konferenz zur Datenzusammenarbeit teilnehmen können (eine Online-Besprechung, die Aktivitäten wie Whiteboards und Umfragen umfasst).  <br/> |
|Test-CsDialinConferencing (DialinConferencing)  <br/> |Überprüft, ob Benutzer Telefonnummern wählen können, um an Konferenzen teilzunehmen.  <br/> |
|Test-CsDialinConferencing (DialinConferencing)  <br/> |Überprüft, ob Benutzer Telefonnummern wählen können, um an Konferenzen teilzunehmen.  <br/> |
|Test-CsExumConnectivity (ExumConnectivity)  <br/> |Überprüft, ob ein Benutzer eine Verbindung mit Exchange Unified Messaging (UM) herstellen kann.  <br/> |
|Test-CsGroupIM -TestJoinLauncher (JoinLauncher)  <br/> |Überprüft, ob Benutzer in der Lage sind, geplante Besprechungen zu erstellen und daran teilzunehmen (über einen Webadressenlink).  <br/> |
|Test-CsMCXP2PIM (MCXP2PIM)  <br/> |Überprüft, ob Benutzer mit Mobilgeräten in der Lage sind, sich zu registrieren und Sofortnachrichten zu senden.  <br/> |
|Test-CsP2PVideoInteropServerSipTrunkAV (P2PVideoInteropServerSipTrunkAV)  <br/> |Überprüft, ob der Video-Interop-Server verfügbar ist und eingehende Verbindungen über einen Video-SIP-Trunk verarbeiten kann.  <br/> **Hinweis:** Die McX-Unterstützung für ältere mobile Clients ist in Skype for Business Server 2019 nicht mehr verfügbar. |
|Test-CsPersistentChatMessage (PersistentChatMessage)  <br/> |Überprüft, ob Benutzer Nachrichten mithilfe des Diensts für beständigen Chat austauschen können.  <br/> |
|Test-CsUcwaConference (UcwaConference)  <br/> |Überprüft, ob Benutzer über das Web an Konferenzen teilnehmen können.  <br/> |
|Test-CsUnifiedContactStore (UnifiedContactStore)  <br/> |Überprüft, ob die Kontakte eines Benutzers über den einheitlichen Kontaktspeicher zugänglich sind. Der einheitliche Kontaktspeicher bietet Benutzern die Möglichkeit, einen einzelnen Satz von Kontakten zu verwalten, auf den über Skype for Business Server 2015, den Outlook-Client für Messaging und Zusammenarbeit und/oder Outlook Web Access zugegriffen werden kann.  <br/> |
|Test-CsXmppIM (XmppIM)  <br/> |Überprüft, ob eine Chatnachricht über das Extensible Messaging and Presence Protocol (XMPP)-Gateway gesendet werden kann.  <br/> XMPP-Gateways und -Proxys sind in Skype for Business Server 2015 verfügbar, werden jedoch in Skype for Business Server 2019 nicht mehr unterstützt.  |

Sie müssen keine Watcherknoten installieren, um System Center Operations Manager verwenden zu können. Wenn Sie diese Knoten nicht installieren, können Sie immer noch Echtzeitbenachrichtigungen von Skype for Business Server 2015-Komponenten erhalten, wenn ein Problem auftritt. (Das Component and User Management Pack verwendet keine Watcher-Knoten.) Monitorknoten sind jedoch erforderlich, wenn Sie End-to-End-Szenarien mithilfe des Active Monitoring Management Packs überwachen möchten.
  
> [!NOTE]
> Administratoren können synthetische Transaktionen auch manuell ausführen, ohne Operations Manager zu verwenden oder zu installieren. Abhängig von der Größe Ihrer Skype for Business Server-Bereitstellung können synthetische Transaktionen sehr viel Arbeitsspeicher und Prozessorzeit auf dem Computer verwenden. Aus diesem Grund wird empfohlen, einen dedizierten Computer als Watcher-Knoten zu verwenden. Beispielsweise sollten Sie einen Skype for Business Server-Front-End-Server nicht als Watcher-Knoten konfigurieren. Watcherknoten sollten dieselben grundlegenden Hardwareanforderungen erfüllen wie alle anderen Computer in Ihrer Skype for Business Server-Topologie. 
  
> [!NOTE]
> Ein Lync Server 2013-Watcher-Legacyknoten kann nicht auf demselben Computer wie ein Skype for Business Server 2015-Watcher-Knoten ausgeführt werden, da die Hauptsystemdateien für Lync Server 2013 und Skype for Business Server 2015 nicht auf demselben Computer installiert werden können. Skype for Business Server 2015-Monitorknoten können jedoch skype for Business Server 2015 und Lync Server 2013 gleichzeitig überwachen. Synthetische Standardtransaktionen werden für beide Produktversionen unterstützt. 
  
Lync Server 2013-Watcher-Knoten können innerhalb oder außerhalb eines Unternehmens bereitgestellt werden, um dies zu überprüfen:
  
- Konnektivität zu Pools für Benutzer innerhalb des Unternehmens
    
- Konnektivität über Umkreisnetzwerke für Remotebenutzer, die außerhalb des Unternehmens arbeiten.
    
- Konnektivität zu Branch Office Appliances
    
- Verbindung mit Lync Server 2013 innerhalb des Unternehmens und über Umkreisnetzwerke.
    
Zur Vereinfachung der Verwaltung stehen innerhalb und außerhalb des Unternehmens unterschiedliche Authentifizierungsoptionen zur Verfügung. Weitere Informationen finden Sie unter ["Konfigurieren eines Watcher-Knotens zum Ausführen synthetischer Transaktionen".](watcher-nodes.md#enable_synthetic_trans)
  
Um einen Computer als Watcherknoten zu konfigurieren, müssen Sie zunächst die folgenden Voraussetzungen erfüllen: 
  
- Installieren Sie System Center Operations Manager, und importieren Sie die Skype for Business Server 2015 Management Packs. Außerdem müssen Sie zunächst überprüfen, ob der Watcher-Knoten-Computer alle Voraussetzungen für die Installation von Skype for Business Server 2015 erfüllt.
    
- Installieren Sie die folgenden Elemente auf dem Watcher-Knoten-Computer:
    
  - Die Vollversion von .NET Framework 4.5
    
  - Windows Identity Foundation
    
  - Windows PowerShell 3.0
    
Nachdem die Voraussetzungen erfüllt sind, können Sie den Watcher-Knoten konfigurieren, indem Sie die folgenden Schritte ausführen:
  
1. Installieren Sie die Skype for Business Server 2015-Kerndateien auf dem Watcher-Knoten-Computer.
    
2. Installieren Sie den System Center Operations Manager-Agent auf dem Watcher-Knoten-Computer.
    
3. Führen Sie die Watchernode.msi ausführbare Datei aus.
    
4. Verwenden Sie **das Cmdlet "New-CsWatcherNodeConfiguration",** um Testbenutzerkonten für den Watcher-Knoten zu konfigurieren.
    
## <a name="install-the-skype-for-business-server-2015-core-files-and-the-rtclocal-database"></a>Installieren der Skype for Business Server 2015-Kerndateien und der RTCLocal-Datenbank

Führen Sie die folgenden Schritte aus, um die Skype for Business Server 2015-Kerndateien auf einem Computer zu installieren. Die DATENBANK "RTCLocal" wird automatisch installiert, wenn Sie die Kerndateien installieren. Beachten Sie, dass Sie keine SQL Server auf den Watcher-Knoten installieren müssen. SQL Server Express wird automatisch installiert.
  
So installieren Sie die Skype for Business Server 2015-Kerndateien und die RTCLocal-Datenbank:
  
1. Klicken Sie auf dem Watcher-Knoten-Computer auf Start, Alle Programme und Zubehör, klicken Sie mit der rechten Maustaste auf Eingabeaufforderung, und klicken Sie dann auf Als Administrator ausführen.
    
2. Geben Sie im Konsolenfenster den folgenden Befehl ein, und drücken Sie die EINGABETASTE. Geben Sie den entsprechenden Pfad zu Ihren Skype for Business Server-Setupdateien ein: D:\Setup.exe /BootstrapLocalMgmtTo verify that the core Skype for Business Server components are successfully installed, click **Start**, click **All Programs**, click Skype for Business **Server 2015,** and then click **Skype for Business Server Management Shell**. Geben Sie in der Skype for Business Server-Verwaltungsshell den folgenden Befehl Windows PowerShell und drücken Sie die EINGABETASTE:
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

> [!NOTE]
> Wenn Sie diesen Befehl zum ersten Mal ausführen, werden keine Daten zurückgegeben, da Sie noch keine Watcher-Knoten-Computer konfiguriert haben. Wenn der Befehl ohne Fehler ausgeführt wird, können Sie davon ausgehen, dass das Skype for Business Server-Setup erfolgreich abgeschlossen wurde. 
  
Wenn sich Ihr Watcher-Knoten-Computer in Ihrem Umkreisnetzwerk befindet, können Sie den folgenden Befehl ausführen, um die Installation von Skype for Business Server 2015 zu überprüfen:
  
Get-CsPinPolicyYou erhalten abhängig von der Anzahl der für die Verwendung in Ihrer Organisation konfigurierten PIN-Richtlinien Informationen wie dies:
  
Identität: Global
  
Beschreibung:
  
MinPasswordLength : 5
  
PINHistoryCount : 0
  
AllowCommonPatterns : False
  
PINLifetime : 0
  
MaximumLogonAttempts :
  
Wenn Sie Informationen zu Ihren PIN-Richtlinien sehen, wurden die Hauptkomponenten erfolgreich installiert.
  
## <a name="install-the-operation-manager-agent-files-on-a-watcher-node"></a>Installieren der Operation Manager-Agent-Dateien auf einem Watcher-Knoten

Ähnlich wie das Skype for Business Server-Setup zum Melden von Komponentenwarnungen erfordert ein Skype for Business Server 2015-Watcher-Knoten die Installation von System Center Operations Manager-Agent-Dateien. Dadurch können die synthetischen Transaktionen ausgeführt und Warnungen an den System Center Operations Manager Root Management Server gemeldet werden.
  
Führen Sie zum Installieren der Agentdateien die unter "Konfigurieren der Skype for Business Server-Computer, die überwacht werden" [aufgeführten Verfahren aus.](configure-computers-to-monitor.md)
  
## <a name="configure-a-watcher-node-to-run-synthetic-transactions"></a>Konfigurieren eines Watcher-Knotens zum Ausführen synthetischer Transaktionen
<a name="enable_synthetic_trans"> </a>

Nachdem die System Center Operations Manager-Agent-Dateien installiert wurden, müssen Sie den Watcherknoten selbst konfigurieren. Die schritte dazu variieren, je nachdem, ob sich der Watcher-Knoten-Computer innerhalb oder außerhalb des Umkreisnetzwerks befindet. 
  
Beim Konfigurieren eines Watcher-Knotens müssen Sie außerdem die Authentifizierungsmethode auswählen, die von diesem Knoten verwendet werden soll. Mit Skype for Business Server 2015 können Sie eine von zwei Authentifizierungsmethoden auswählen: Vertrauenswürdige Server- oder Anmeldeinformationsauthentifizierung. In der folgenden Tabelle sind die Unterschiede zwischen diesen beiden Methoden aufgeführt:
  
||**Beschreibung**|**Unterstützte Speicherorte**|
|:-----|:-----|:-----|
|TrustedServer  <br/> |Ein Zertifikat wird verwendet, um die Identität eines internen Servers anzunehmen und die Authentifizierungsaufforderungen zu umgehen.  <br/> Hilfreich für Administratoren, die ein einzelnes Zertifikat anstelle vieler Benutzerkennwörter auf jedem Watcher-Knoten verwalten möchten.  <br/> |Innerhalb des Unternehmens.  <br/> Bei dieser Methode muss sich der Watcherknoten in derselben Domäne wie die überwachten Pools befinden. Wenn sich der Watcherknoten und die Pools in unterschiedlichen Domänen befinden, verwenden Sie stattdessen die Anmeldeinformationsauthentifizierung.  <br/> |
|Aushandeln  <br/> |Benutzernamen und Kennwörter werden auf sichere Weise in der Windows-Anmeldeinformationsverwaltung auf jedem Watcher-Knoten gespeichert.  <br/> Dieser Modus erfordert mehr Kennwortverwaltung, ist aber die einzige Option für Watcher-Knoten außerhalb des Unternehmens. Diese Watcher-Knoten können nicht als Endpunkt, der bezüglich der Authentifizierung vertrauenswürdig ist, betrachtet werden.  <br/> |Außerhalb des Unternehmens.  <br/> Innerhalb des Unternehmens.  <br/> |
   
## <a name="configure-a-watcher-node-to-use-trusted-server-authentication"></a>Konfigurieren eines Watcher-Knotens für die Verwendung der vertrauenswürdigen Serverauthentifizierung
<a name="enable_synthetic_trans"> </a>

Wenn sich der Watcher-Knoten-Computer innerhalb des Umkreisnetzwerks befindet, kann die Verwendung der vertrauenswürdigen Serverauthentifizierung Verwaltungsaufgaben erheblich reduzieren, indem ein einzelnes Zertifikat beibehalten wird, anstatt zahlreiche Benutzerkontenkennwörter zu verwenden.
  
Zum Konfigurieren der vertrauenswürdigen Serverauthentifizierung müssen Sie zunächst einen vertrauenswürdigen Anwendungspool zum Hosten des Watcher-Knoten-Computers erstellen. Nachdem Sie den vertrauenswürdigen Anwendungspool erstellt haben, müssen Sie synthetische Transaktionen auf diesem Watcherknoten für die Ausführung als vertrauenswürdige Anwendungen konfigurieren.
  
> [!NOTE]
> Eine vertrauenswürdige Anwendung ist eine Anwendung, die als Teil von Skype for Business Server 2015 als vertrauenswürdiger Status ausgeführt werden kann, aber kein integrierter Bestandteil des Produkts ist. Vertrauensstatus bedeutet, dass nicht bei jeder Ausführung der Anwendung eine Authentifizierung angefordert wird.
  
Öffnen Sie zum Erstellen eines vertrauenswürdigen Anwendungspools die Skype for Business Server-Verwaltungsshell, und führen Sie einen Befehl wie den folgenden aus:
  
```PowerShell
New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond
```

> [!NOTE]
> Details zu den Parametern im vorherigen Befehl erhalten Sie, wenn Sie an der Eingabeaufforderung der Skype for Business Server-Verwaltungsshell Folgendes eingeben: 
  
```PowerShell
Get-Help New-CsTrustedApplicationPool -Full | more
```

Nach dem Erstellen des Pools vertrauenswürdiger Anwendungen können Sie den Watcher-Knoten-Computer so konfigurieren, dass synthetische Transaktionen als vertrauenswürdige Anwendung ausgeführt werden, indem Sie das **Cmdlet "New-CsTrustedApplication"** und einen Befehl wie den folgenden verwenden:
  
```PowerShell
New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061
```

Wenn dieser Befehl abgeschlossen ist und die vertrauenswürdige Anwendung erstellt wird, müssen Sie das Cmdlet **"Enable-CsTopology"** ausführen, um sicherzustellen, dass die Änderungen wirksam werden:
  
```PowerShell
Enable-CsTopology
```

Das Computerkonto des Watcherknotens erfordert die Möglichkeit, CMS nach einigen synthetischen Transaktionen zu fragen. Um diese Möglichkeit zu ermöglichen, fügen Sie das Computerkonto des Watcher-Knotens der Sicherheitsgruppe "RTCUniversalReadOnlyAdmins" hinzu. Nachdem die Replikation von AD erfolgt ist, starten Sie den Computer neu.
  
Geben Sie an der Eingabeaufforderung der Skype for Business Server-Verwaltungsshell Folgendes ein, um zu überprüfen, ob die neue vertrauenswürdige Anwendung erstellt wurde:
  
```PowerShell
Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"
```

## <a name="configure-a-default-certificate-on-the-watcher-node"></a>Konfigurieren eines Standardzertifikats auf dem Watcher-Knoten
<a name="enable_synthetic_trans"> </a>

Jedem Watcherknoten, der die TrustedServer-Authentifizierung verwendet, muss mithilfe des Skype for Business Server-Bereitstellungs-Assistenten ein Standardzertifikat zugewiesen sein. 
  
So weisen Sie ein Standardzertifikat zu:
  
1. Klicken Sie auf "Start", "Alle Programme", "Skype for Business Server 2015" und dann auf "Skype for Business Server-Bereitstellungs-Assistent". 
    
2. Klicken Sie im Skype for Business Server-Bereitstellungs-Assistenten auf "Skype for Business Server System installieren oder aktualisieren", und klicken Sie dann unter der Überschrift "Zertifikat anfordern, installieren oder zuweisen" auf "Ausführen". 
    
> [!NOTE]
> Wenn die Schaltfläche Ausführen deaktiviert ist, müssen Sie möglicherweise zunächst unter Lokalen Konfigurationsspeicher installieren auf Ausführen klicken. 
  
Führen Sie einen der folgenden Schritte aus:
  
- Wenn Sie bereits über ein Zertifikat verfügen, das als Standardzertifikat verwendet werden kann, klicken Sie im Assistenten für Zertifikate auf "Standard" und dann auf "Zuweisen". Befolgen Sie die Anweisungen des Zertifikat-Assistenten, um das Zertifikat zuzuweisen.
    
- Wenn Sie ein Zertifikat für die Verwendung des Standardzertifikats anfordern müssen, klicken Sie auf "Anfordern", und führen Sie dann die Schritte im Assistenten für Zertifikatsanforderung aus, um dieses Zertifikat an fordern. Wenn Sie die Standardwerte für das Webserver-Zertifikat verwenden, erhalten Sie ein Zertifikat, das Sie als Standardzertifikat zuweisen können.
    
## <a name="install-and-configure-a-watcher-node"></a>Installieren und Konfigurieren eines Watcher-Knotens
<a name="enable_synthetic_trans"> </a>

Nachdem Sie den Watcher-Knoten-Computer neu gestartet und ein Zertifikat konfiguriert haben, müssen Sie die Datei Watchernode.msi. (Sie müssen Watchernode.msi auf jedem Computer ausführen, auf dem sowohl die Operations Manager-Agent-Dateien als auch die Skype for Business Server 2015-Hauptkomponenten installiert sind.) 
  
So installieren und konfigurieren Sie einen Watcher-Knoten:
  
1. Öffnen Sie die Skype for Business Server-Verwaltungsshell, indem Sie auf "Start", "Alle Programme", "Skype for Business Server 2015" und dann auf "Skype for Business Server-Verwaltungsshell" klicken. 
    
2. Geben Sie in der Verwaltungsshell den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE (achten Sie darauf, und geben Sie den tatsächlichen Pfad zu Ihrer Kopie des Watchernode.msi):
    
```PowerShell
C:\Tools\Watchernode.msi Authentication=TrustedServer
```

> [!NOTE]
> Sie können auch Watchernode.msi n in einem Befehlsfenster ausführen. Klicken Sie zum Öffnen eines Befehlsfensters auf Start, klicken Sie mit der rechten Maustaste auf Eingabeaufforderung, und klicken Sie dann auf Als Administrator ausführen. Wenn das Befehlsfenster geöffnet wird, geben Sie denselben Befehl wie in Schritt 2 oben gezeigt ein. 
  
> [!IMPORTANT]
> Im vorstehenden Befehl wird beim Namen-Wert-Paar "Authentication=TrustedServer" die Kleinschreibung beachtet. Sie muss genau wie dargestellt typiert werden. Bei diesem Befehl wird beispielsweise ein Fehler ausgeführt, da nicht die richtige Buchstabenschrift verwendet wird: 
  
```PowerShell
C:\Tools\Watchernode.msi authentication=trustedserver
```

Der Modus "TrustedServer" kann nur für Computer verwendet werden, die sich innerhalb des Umkreisnetzwerks befinden. Wenn ein Watcherknoten im vertrauenswürdigenServermodus ausgeführt wird, müssen Administratoren keine Testbenutzerkennwörter auf dem Computer verwalten.
  
## <a name="configure-a-watcher-node-to-use-negotiate"></a>Konfigurieren eines Watcher-Knotens für die Verwendung von Aushandeln
<a name="enable_synthetic_trans"> </a>

Wenn sich ihr Watcher-Knoten-Computer außerhalb des Umkreisnetzwerks befindet, müssen Sie ein etwas anderes Verfahren ausführen, um diesen Watcherknoten für die Ausführung synthetischer Transaktionen zu konfigurieren: Insbesondere sollten Sie keinen Pool mit vertrauenswürdigen Anwendungen oder keine vertrauenswürdige Anwendung erstellen. Das bedeutet, dass Sie die nächsten beiden Aufgaben ausführen müssen.
  
### <a name="update-membership-in-the-rtc-local-read-only-administrators-group"></a>Aktualisieren der Mitgliedschaft in der Gruppe "RTC Local Read-Only Administrators"

Wenn sich der Watcherknoten außerhalb des Umkreisnetzwerks befindet, müssen Sie das Netzwerkdienstkonto der Gruppe "RTC Local Read-only Administrators" auf dem Computer mit dem Watcherknoten hinzufügen, indem Sie das folgende Verfahren auf dem Watcher-Knoten abschließen:
  
1. Klicken Sie auf Start, klicken Sie mit der rechten Maustaste auf Arbeitsplatz, und klicken Sie dann auf Verwalten.
    
2. Erweitern Sie im Server-Manager die Optionen Konfiguration und Lokale Benutzer und Gruppen, und klicken Sie dann auf Gruppen.
    
3. Doppelklicken Sie im Bereich "Gruppen" mit der rechten Maustaste auf RTC Local Read-only Administrators.
    
4. Klicken Sie im Dialogfeld mit den Eigenschaften von RTC Local Read-only Administrators auf Hinzufügen.
    
5. Klicken Sie im Dialogfeld für die Auswahl von Benutzern, Computern, Dienstkonten oder Gruppen auf Standorte.
    
6. Wählen Sie im Dialogfeld Standorte den Namen des Monitorknotencomputers aus, und klicken Sie dann auf OK.
    
7. Geben Sie im Feld Geben Sie die zu verwendenden Objektnamen ein den Text Netzwerkdienst ein, und klicken Sie auf OK.
    
8. Klicken Sie im Dialogfeld mit den Eigenschaften von RTC Local Read-only Administrators auf OK, und schließen Sie den Server-Manager.
    
9. Starten Sie den Monitorknotencomputer neu.
    
### <a name="install-the-watcher-node-configuration-files"></a>Installieren der Konfigurationsdateien für den Watcher-Knoten

Im nächsten Schritt führen Sie die Datei Watchernode.msi: 
  
1. Öffnen Sie die Microsoft Skype for Business Server 2015-Verwaltungsshell. Klicken Sie auf "Start", "Alle Programme", "Microsoft Skype for Business Server 2015" und dann auf "Skype for Business Server-Verwaltungsshell". 
    
2. Geben Sie in der Skype for Business Server-Verwaltungsshell den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE (achten Sie darauf, den tatsächlichen Pfad zu Ihrer Kopie des Watchernode.msi):
    
   ```PowerShell
   c:\Tools\Watchernode.msi Authentication=Negotiate
   ```

> [!NOTE]
> Wie bereits erwähnt, Watchernode.msi auch über ein Befehlsfenster ausgeführt werden. Klicken Sie zum Öffnen eines Befehlsfensters auf **Start**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und klicken Sie dann auf **Als Administrator ausführen**. Wenn das Befehlsfenster geöffnet wird, geben Sie denselben Befehl wie in Schritt 2 oben gezeigt ein. 
  
Der Aushandlungsmodus wird verwendet, wenn der Monitorknoten nicht als Pool mit vertrauenswürdigen Anwendungen eingerichtet werden kann. In diesem Modus müssen Administratoren Testbenutzerkennwörter für den Monitorknoten verwalten.
  

