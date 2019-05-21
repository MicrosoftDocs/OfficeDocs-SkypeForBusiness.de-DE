---
title: Installieren und Konfigurieren von Monitorknoten
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7392e4f8-6e2d-447b-aaa3-878f73995f9d
description: 'Zusammenfassung: Installieren und Konfigurieren von Watcher-Knoten für synthetische Skype for Business Server-Transaktionen.'
ms.openlocfilehash: 11d99ac51ab3b6c3d2cffbe2061a2e0527bfc633
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277622"
---
# <a name="install-and-configure-watcher-nodes"></a>Installieren und Konfigurieren von Monitorknoten
 
**Zusammenfassung:** Installieren und konfigurieren Sie Watcher-Knoten für synthetische Skype for Business Server-Transaktionen.
  
Watcher-Knoten sind Computer, die in regelmäßigen Abständen die synthetischen Skype for Business Server-Transaktionen ausführen. Synthetische Transaktionen sind Windows PowerShell-Cmdlets, die überprüfen, ob wichtige Endbenutzerszenarien (wie die Fähigkeit zur Anmeldung beim System oder zum Austausch von Chatnachrichten) ordnungsgemäß funktionieren. Für Skype for Business Server 2015 kann System Center Operations Manager die synthetischen Transaktionen ausführen, die in der folgenden Tabelle aufgeführt sind, die drei synthetische Transaktionstypen umfasst:
  
- **Standardwert** Synthetische Transaktionen, die ein Watcher-Knoten standardmäßig ausführt. Wenn Sie einen neuen Watcher-Knoten erstellen, können Sie angeben, welche synthetischen Transaktionen dieser Knoten ausführen soll. (Dies ist der Zweck des Parameters Tests, der vom Cmdlet New-CsWatcherNodeConfiguration verwendet wird.) Wenn Sie den Parameter Tests nicht verwenden, wenn der Watcher-Knoten erstellt wird, werden automatisch alle synthetischen Standardtransaktionen ausgeführt, und es werden keine der nicht standardmäßigen synthetischen Transaktionen ausgeführt. Dies bedeutet beispielsweise, dass der Watcher-Knoten so konfiguriert ist, dass er den Test-CsAddressBookService-Test ausführt, aber nicht für die Ausführung des Test-CsExumConnectivity-Tests konfiguriert ist.
    
- **Nicht Standard** Testet, ob Watcher-Knoten standardmäßig nicht ausgeführt werden. (Ausführliche Informationen finden Sie in der Beschreibung des Standardtyps.) Allerdings kann der Watcher-Knoten aktiviert werden, um eine der nicht standardmäßigen synthetischen Transaktionen auszuführen. Sie können dies tun, wenn Sie den Watcher-Knoten erstellen (mithilfe des Cmdlets New-CsWatcherNodeConfiguration) oder zu einem beliebigen Zeitpunkt nach der Erstellung des Watcher-Knotens. Beachten Sie, dass für viele der nicht standardmäßigen synthetischen Transaktionen zusätzliche Setupschritte erforderlich sind. Details zu diesen Schritten finden Sie unter spezielle Setup Anweisungen für synthetische Transaktionen. Weitere Informationen zu diesen Schritten finden Sie unter [spezielle Setup Anweisungen für synthetische Transaktionen ](test-users-and-settings.md#special_synthetictrans).
    
- **Erweitert** Eine spezielle Art von nicht standardmäßigen synthetischen Transaktionen. Im Gegensatz zu anderen synthetischen Transaktionen können erweiterte Tests während der einzelnen Durchlaufzeiten mehrmals ausgeführt werden. Dies ist hilfreich, wenn Sie das Verhalten überprüfen, beispielsweise mehrere PSTN-VoIP-Routen (Public Switched Telephone Network) für einen Pool. Sie können dies einfach konfigurieren, indem Sie einem Watcher-Knoten mehrere Instanzen eines erweiterten Tests hinzufügen.
    
Nähere Informationen über die Vorgehensweise zum Hinzufügen anderer synthetischer Transaktionen zu einem Monitorknoten finden Sie unter [Configure a Watcher Node to Run Synthetic Transactions](watcher-nodes.md#enable_synthetic_trans). Sie können auch die Skype for Business Server-Verwaltungsshell verwenden, um synthetische Transaktionen von einem Watcher-Knoten zu entfernen.
  
Folgende synthetische Transaktionen sind für Monitorknoten verfügbar:
  
|**Name des Cmdlets (Name des Tests)**|**Beschreibung**|
|:-----|:-----|
|Test-CsAddressBookService (ABS)  <br/> |Bestätigt, dass Benutzer nach Benutzern suchen können, die nicht in Ihrer Kontaktliste enthalten sind.  <br/> |
|Test-CsAddressBookWebQuery (ABWQ)  <br/> |Bestätigt, dass Benutzer nach Benutzern suchen können, die nicht in Ihrer Kontaktliste über HTTP sind.  <br/> |
|Test-CsAVConference (AvConference)  <br/> |Überprüft, ob Benutzer in der Lage sind, eine Audio-/Videokonferenz zu erstellen und daran teilzunehmen.  <br/> |
|Test-CsGroupIM (Chatkonferenz)  <br/> |Überprüft, ob Benutzer in der Lage sind, in Konferenzen Chatnachrichten zu senden und an Chatnachrichtenunterhaltungen mit drei oder mehr Personen teilzunehmen.  <br/> |
|Test-CsIM (P2P IM)  <br/> |Überprüft, ob Benutzer in der Lage sind, Peer-zu-Peer-Chatnachrichten zu senden.  <br/> |
|Test-CsP2PAV (P2PAV)  <br/> |Überprüft, ob Benutzer in der Lage sind, Peer-zu-Peer-Audioanrufe zu tätigen (nur Signal).  <br/> |
|Test-CsPresence (Anwesenheit)  <br/> |Bestätigt, dass Benutzer die Anwesenheit anderer Benutzer anzeigen können.  <br/> |
|Test-CsRegistration (Registrierung)  <br/> |Bestätigt, dass Benutzer sich bei Skype for Business anmelden können.  <br/> |
|Test-CsPstnPeerToPeerCall (PSTN)  <br/> |Überprüft, ob Benutzer in der Lage sind, Anrufe von Personen außerhalb des Unternehmens (PSTN-Nummern) entgegenzunehmen oder diese anzurufen.  <br/> |
|Test-CsASConference (ASConference)  <br/> |Überprüft, ob Benutzer in der Lage sind, eine Anwendungsfreigabekonferenz zu erstellen und daran teilzunehmen.  <br/> |
|Test-CsAVEdgeConnectivity (AVEdgeConnectivity)  <br/> |Überprüft, ob die Audio-/Video-Edgeserver in der Lage sind, Verbindungen für Peer-zu-Peer-Anrufe und Konferenzanrufe entgegenzunehmen.  <br/> |
|Test-CsDataConference (DataConference)  <br/> |Überprüft, ob Benutzer an einer Datenzusammenarbeitskonferenz (eine Onlinebesprechung, zu der Aktivitäten wie Whiteboards und Umfragen gehören) teilnehmen können.  <br/> |
|Test-CsDialinConferencing (DialinConferencing)  <br/> |Überprüft, ob Benutzer Telefonnummern anrufen können, um an Konferenzen teilzunehmen.  <br/> |
|Test-CsDialinConferencing (DialinConferencing)  <br/> |Überprüft, ob Benutzer Telefonnummern anrufen können, um an Konferenzen teilzunehmen.  <br/> |
|Test-CsExumConnectivity (ExumConnectivity)  <br/> |Bestätigt, dass ein Benutzer eine Verbindung mit Exchange Unified Messaging (um) herstellen kann.  <br/> |
|Test-CsGroupIM-TestJoinLauncher (JoinLauncher)  <br/> |Überprüft, ob Benutzer geplante Besprechungen erstellen und an geplanten Besprechungen teilnehmen können (über einen Weblink).  <br/> |
|Test-CsMCXP2PIM (MCXP2PIM)  <br/> |Überprüft, ob Benutzer mit Mobilgeräten in der Lage sind, sich zu registrieren und Chatnachrichten zu senden.  <br/> |
|Test-CsP2PVideoInteropServerSipTrunkAV (P2PVideoInteropServerSipTrunkAV)  <br/> |Bestätigt, dass der Video-Interop-Server eingerichtet ist und eingehende Verbindungen über einen Video-SIP-Trunk verarbeiten kann.  <br/> **Hinweis:** MCX-Unterstützung für ältere Mobile Clients steht in Skype for Business Server 2019 nicht mehr zur Verfügung. |
|Test-CsPersistentChatMessage (PersistentChatMessage)  <br/> |Überprüft, ob Benutzer über den Dienst für beständigen Chat Sprachnachrichten austauschen können.  <br/> |
|Test-CsUcwaConference (UcwaConference)  <br/> |Überprüft, ob Benutzer über das Internet an Konferenzen teilnehmen können.  <br/> |
|Test-CsUnifiedContactStore (UnifiedContactStore)  <br/> |Überprüft, ob die Kontakte eines Benutzers über den einheitlichen Kontaktspeicher zugänglich sind. Der Unified Contact Store bietet Benutzern eine Möglichkeit zum Verwalten einer einzelnen Gruppe von Kontakten, auf die mithilfe von Skype for Business Server 2015, Outlook-Messaging-und Zusammenarbeitsclient und/oder Outlook Web Access zugegriffen werden kann.  <br/> |
|Test-CsXmppIM (XmppIM)  <br/> |Überprüft, ob eine Chatnachricht über das XMPP-Gateway (Extensible Messaging and Presence Protocol) gesendet werden kann.  <br/> XMPP-Gateways und-Proxies sind in Skype for Business Server 2015 verfügbar, werden aber in Skype for Business Server 2019 nicht mehr unterstützt.  |

Sie müssen Watcher-Knoten nicht installieren, um System Center Operations Manager verwenden zu können. Wenn Sie diese Knoten nicht installieren, können Sie immer noch in Echtzeit über Skype for Business Server 2015-Komponenten benachrichtigt werden, wenn ein Problem auftritt. (Das Komponenten-und Benutzer Verwaltungspaket verwendet keine Watcher-Knoten.) Watcher-Knoten sind jedoch erforderlich, wenn Sie End-to-End-Szenarien überwachen möchten, indem Sie das aktive Überwachungs Management Pack verwenden.
  
> [!NOTE]
> Administratoren können synthetische Transaktionen auch manuell ohne Verwendung oder Installation von Operations Manager ausführen. Je nach Größe Ihrer Skype for Business Server-Bereitstellung können synthetische Transaktionen eine große Menge an Computerspeicher und Prozessorzeit nutzen. Aus diesem Grund wird empfohlen, als Monitorknoten einen dedizierten Computer zu verwenden. Beispielsweise sollten Sie einen Skype for Business Server-Front-End-Server nicht so konfigurieren, dass er als Watcher-Knoten fungiert. Watcher-Knoten sollten die gleichen grundlegenden Hardwareanforderungen erfüllen wie alle anderen Computer in Ihrer Skype for Business Server-Topologie. 
  
> [!NOTE]
> Ein Legacy lync Server 2013 Watcher-Knoten kann nicht auf dem gleichen Computer wie ein Skype for Business Server 2015 Watcher-Knoten aufgestellt werden, da die Hauptsystem Dateien für lync Server 2013 und Skype for Business Server 2015 nicht auf demselben Computer installiert werden können. Skype for Business Server 2015 Watcher-Knoten können jedoch Skype for Business Server 2015 und lync Server 2013 gleichzeitig überwachen. Die synthetischen Transaktionen vom Typ „Standard“ werden in beiden Produktversionen unterstützt. 
  
Lync Server 2013 Watcher-Knoten können innerhalb oder außerhalb eines Unternehmens bereitgestellt werden, um Folgendes zu überprüfen:
  
- Konnektivität zu Pools für Benutzer innerhalb des Unternehmens
    
- Konnektivität über Umkreisnetzwerke für Remotebenutzer, die außerhalb des Unternehmens arbeiten
    
- Konnektivität zu Branch Office Appliances
    
- Konnektivität mit lync Server 2013 innerhalb des Unternehmens und über Umkreisnetzwerke.
    
Zur leichteren Verwaltung stehen unterschiedliche Authentifizierungsoptionen für innerhalb oder außerhalb des Unternehmens bereitgestellte Monitorknoten zur Verfügung. Weitere Informationen finden Sie unter [Configure a Watcher Node to Run Synthetic Transactions](watcher-nodes.md#enable_synthetic_trans).
  
Wenn Sie einen Computer so konfigurieren möchten, dass er als Monitorknoten fungiert, müssen die folgenden Voraussetzungen erfüllt sein: 
  
- Installieren Sie System Center Operations Manager, und importieren Sie die Skype for Business Server 2015-Management Packs. Sie müssen auch zuerst überprüfen, ob der Watcher-Knoten Computer alle Voraussetzungen für die Installation von Skype for Business Server 2015 erfüllt.
    
- Installieren Sie die folgenden Elemente auf dem als Monitorknoten fungierenden Computer:
    
  - Die Vollversion von .NET Framework 4,5
    
  - Windows Identity Foundation
    
  - Windows PowerShell 3.0
    
Wenn alle Anforderungen erfüllt sind, können Sie den Monitorknoten mit den folgenden Schritten installieren:
  
1. Installieren Sie die Core-Dateien von Skype for Business Server 2015 auf dem Watcher-Knoten Computer.
    
2. Installieren Sie den System Center Operations Manager-Agent auf dem Watcher-Knoten Computer.
    
3. Ausführen der Datei „Watchernode.msi“
    
4. Konfigurieren von Testbenutzerkonten auf dem Monitorknoten mithilfe des Cmdlets **New-CsWatcherNodeConfiguration**
    
## <a name="install-the-skype-for-business-server-2015-core-files-and-the-rtclocal-database"></a>Installieren der Hauptdateien von Skype for Business Server 2015 und der RTCLocal-Datenbank

Führen Sie die folgenden Schritte aus, um die Core-Dateien von Skype for Business Server 2015 auf einem Computer zu installieren. Die RTCLocal-Datenbank wird zusammen mit den Hauptdateien automatisch installiert. Beachten Sie, dass Sie SQL Server nicht auf den Watcher-Knoten installieren müssen. SQL Server Express wird automatisch installiert.
  
So installieren Sie die Core-Dateien von Skype for Business Server 2015 und die RTCLocal-Datenbank:
  
1. Klicken Sie auf dem Monitorknotencomputer auf „Start“, auf „Alle Programme“ und auf „Zubehör“. Klicken Sie mit der rechten Maustaste auf „Eingabeaufforderung“ und klicken Sie dann auf „Als Administrator ausführen“.
    
2. Geben Sie im Konsolenfenster den folgenden Befehl ein und drücken Sie die EINGABETASTE. Stellen Sie sicher, dass Sie den richtigen Pfad zu Ihren Skype for Business Server-Setupdateien eingeben: D:\setup.exe/BootstrapLocalMgmtTo stellen Sie sicher, dass die Kernkomponenten von Skype for Business Server erfolgreich installiert wurden, klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, Klicken Sie auf **Skype for Business Server 2015**, und klicken Sie dann auf **Skype for Business Server-Verwaltungsshell**. Geben Sie in der Skype for Business Server-Verwaltungsshell den folgenden Windows PowerShell-Befehl ein, und drücken Sie die EINGABETASTE:
  
```
Get-CsWatcherNodeConfiguration
```

> [!NOTE]
> Bei der ersten Ausführung dieses Befehls werden keine Daten zurückgegeben, da noch keine Computer als Monitorknoten konfiguriert wurden. Wenn der Befehl ausgeführt wird, ohne einen Fehler zurückzugeben, können Sie davon ausgehen, dass das Setup von Skype for Business Server erfolgreich abgeschlossen wurde. 
  
Befindet sich der Monitorknotencomputer in Ihrem Umkreisnetzwerk, können Sie den folgenden Befehl ausführen, um die Installation von Skype for Business Server 2015 zu überprüfen:
  
Get-CsPinPolicyYou erhält ähnliche Informationen, abhängig von der Anzahl der PIN-Richtlinien, die für die Verwendung in Ihrer Organisation konfiguriert sind:
  
Identität: Global
  
Beschreibung
  
MinPasswordLength: 5
  
PINHistoryCount: 0
  
AllowCommonPatterns: falsch
  
PINLifetime: 0
  
MaximumLogonAttempts :
  
Werden Informationen zu Ihren PIN-Richtlinien angezeigt, wurden die Hauptkomponenten erfolgreich installiert.
  
## <a name="install-the-operation-manager-agent-files-on-a-watcher-node"></a>Installieren der Operations Manager-Agent-Dateien auf einem Monitorknoten

Ähnlich wie bei Skype for Business Server-Setup für Berichte über Komponenten Benachrichtigungen erfordert ein Skype for Business Server 2015 Watcher-Knoten die Installation von System Center Operations Manager-Agentendateien. Auf diese Weise können die synthetischen Transaktionen ausgeführt und Benachrichtigungen an den System Center Operations Manager-Stamm Verwaltungs Server gemeldet werden.
  
Wenn Sie die Agentendateien installieren möchten, folgen Sie den Verfahren unter [Konfigurieren der Skype for Business Server-Computer, die überwacht werden](configure-computers-to-monitor.md)sollen.
  
## <a name="configure-a-watcher-node-to-run-synthetic-transactions"></a>Konfigurieren eines Monitorknotens für die Ausführung von synthetischen Transaktionen
<a name="enable_synthetic_trans"> </a>

Nachdem die System Center Operations Manager-Agentendateien installiert wurden, müssen Sie den Watcher-Knoten selbst konfigurieren. Welche Schritte Sie hierfür durchführen hängt davon ab, ob sich der Monitorknotencomputer innerhalb oder außerhalb Ihres Umkreisnetzwerks befindet. 
  
Beim Konfigurieren eines Monitorknotens müssen Sie außerdem die Authentifizierungsmethode auswählen, die von diesem Knoten verwendet werden soll. Mit Skype for Business Server 2015 können Sie eine von zwei Authentifizierungsmethoden auswählen: Trusted Server-oder Anmelde Informations Authentifizierung. In der folgenden Tabelle sind die Unterschiede zwischen diesen beiden Methoden aufgeführt:
  
||**Beschreibung**|**Unterstützte Standorte**|
|:-----|:-----|:-----|
|TrustedServer  <br/> |Ein Zertifikat wird verwendet, um die Identität eines internen Servers anzunehmen und die Authentifizierungsaufforderungen zu umgehen.  <br/> Eignet sich für Administratoren, die es vorziehen, ein einzelnes Zertifikat anstelle vieler Benutzerkennwörter auf jedem Monitorknoten zu verwalten.  <br/> |Innerhalb des Unternehmens.  <br/> Bei dieser Methode muss sich der Monitorknoten in derselben Domäne wie die überwachten Pools befinden. Falls sich der Monitorknoten und die Pools in unterschiedlichen Domänen befinden, verwenden Sie stattdessen die Authentifizierung mit Anmeldeinformationen.  <br/> |
|Negotiate  <br/> |Benutzernamen und Kennwörter werden auf sichere Weise in der Windows-Anmeldeinformationsverwaltung auf jedem Monitorknoten gespeichert.  <br/> Dieser Modus erfordert einen höheren Kennwortverwaltungsaufwand, ist aber die einzige Option für Monitorknoten außerhalb des Unternehmens. Diese Monitorknoten können nicht als vertrauenswürdiger Endpunkt für die Authentifizierung betrachtet werden.  <br/> |Außerhalb des Unternehmens.  <br/> Innerhalb des Unternehmens.  <br/> |
   
## <a name="configure-a-watcher-node-to-use-trusted-server-authentication"></a>Konfigurieren eines Monitorknotens für die Verwendung der Authentifizierung über vertrauenswürdige Server
<a name="enable_synthetic_trans"> </a>

Wenn sich Ihr Monitorknotencomputer innerhalb des Umkreisnetzwerks befindet, können die Administrationsaufgaben durch die Verwendung der Authentifizierung über vertrauenswürdige Server deutlich verringert werden, indem ein einziges Zertifikat verwaltet wird, statt zahlreiche Benutzerkontokennwörter verwenden zu müssen.
  
Zum Konfigurieren der Authentifizierung über vertrauenswürdige Server müssen Sie zuerst einen vertrauenswürdigen Anwendungspool zum Hosten des Monitorknotencomputers erstellen. Nachdem Sie den vertrauenswürdigen Anwendungspool erstellt haben, müssen Sie die synthetischen Transaktionen auf diesem Watcher-Knoten so konfigurieren, dass Sie als vertrauenswürdige Anwendungen ausgeführt werden.
  
> [!NOTE]
> Bei einer vertrauenswürdigen Anwendung handelt es sich um eine Anwendung, die für die Ausführung als Teil von Skype for Business Server 2015 einen vertrauenswürdigen Status erhält, aber kein integrierter Teil des Produkts ist. Vertrauensstatus bedeutet, dass nicht bei jeder Ausführung der Anwendung eine Authentifizierung angefordert wird.
  
Wenn Sie einen vertrauenswürdigen Anwendungspool erstellen möchten, öffnen Sie die Skype for Business Server-Verwaltungsshell, und führen Sie einen Befehl wie den folgenden aus:
  
```
New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond
```

> [!NOTE]
> Einzelheiten zu den Parametern im vorhergehenden Befehl geben Sie in der Eingabeaufforderung der Skype for Business Server-Verwaltungsshell Folgendes ein: 
  
```
Get-Help New-CsTrustedApplicationPool -Full | more
```

Konfigurieren Sie nach der Erstellung des Pools vertrauenswürdiger Anwendungen den Monitorknotencomputer für die Ausführung synthetischer Transaktionen als vertrauenswürdige Anwendung. Verwenden Sie dazu das Cmdlet **New-CsTrustedApplication** und einen Befehl wie den folgenden:
  
```
New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061
```

Nachdem dieser Befehl ausgeführt wurde und die vertrauenswürdige Anwendung erstellt ist, müssen Sie das Cmdlet **Enable-CsTopology** ausführen, um sicherzustellen, dass die Änderungen übernommen werden:
  
```
Enable-CsTopology
```

Führen Sie nach der Ausführung von „Enable-CsTopology“ einen Neustart des Computers durch.
  
Um zu überprüfen, ob die neue vertrauenswürdige Anwendung erstellt wurde, geben Sie Folgendes an der Eingabeaufforderung der Skype for Business Server-Verwaltungsshell ein:
  
```
Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"
```

## <a name="configure-a-default-certificate-on-the-watcher-node"></a>Konfigurieren eines Standardzertifikats auf dem Monitorknoten
<a name="enable_synthetic_trans"> </a>

Für jeden Watcher-Knoten, der die TrustedServer-Authentifizierung verwendet, muss ein Standardzertifikat mit dem Skype for Business Server-Bereitstellungs-Assistenten zugewiesen sein. 
  
So weisen Sie ein Standardzertifikat zu
  
1. Klicken Sie auf Start, klicken Sie auf alle Programme, klicken Sie auf Skype for Business Server 2015, und klicken Sie dann auf Skype for Business Server-Bereitstellungs-Assistent. 
    
2. Klicken Sie im Skype for Business Server-Bereitstellungs-Assistenten auf Skype for Business Server System installieren oder aktualisieren, und klicken Sie dann unter der Überschrift anfordern, installieren oder Zertifikat zuweisen auf ausführen. 
    
> [!NOTE]
> Wenn die Schaltfläche „Ausführen“ deaktiviert ist, müssen Sie möglicherweise zunächst unter „Lokalen Konfigurationsspeicher installieren“ auf „Ausführen“ klicken. 
  
Führen Sie einen der folgenden Schritte aus:
  
- Wenn Sie bereits ein Zertifikat besitzen, das als Standardzertifikat verwendet werden kann, klicken Sie im Zertifikat-Assistenten auf „Standard“ und anschließend auf „Zuweisen“. Befolgen Sie die Anweisungen des Zertifikat-Assistenten, um das Zertifikat zuzuweisen.
    
- Wenn Sie ein Zertifikat für die Verwendung als Standardzertifikat anfordern müssen, klicken Sie auf „Anfordern“ und folgen Sie den Schritten im Zertifikatanforderungs-Assistenten, um das Zertifikat anzufordern. Wenn Sie die Standardwerte für das Webserverzertifikat verwenden, erhalten Sie ein Zertifikat, das Sie als Standardzertifikat zuweisen können.
    
## <a name="install-and-configure-a-watcher-node"></a>Installieren und Konfigurieren eines Monitorknotens
<a name="enable_synthetic_trans"> </a>

Nachdem Sie den Monitorknotencomputer neu gestartet und ein Zertifikat konfiguriert haben, müssen Sie die Datei „Watchernode.msi“ ausführen. (Sie müssen Watchernode. msi auf jedem Computer ausführen, auf dem sowohl die Operations Manager-Agentendateien als auch die Core-Komponenten von Skype for Business Server 2015 installiert sind.) 
  
So installieren und konfigurieren Sie einen Monitorknoten
  
1. Öffnen Sie die Skype for Business Server-Verwaltungsshell, indem Sie auf Start klicken, auf alle Programme klicken, auf Skype for Business Server 2015 und dann auf Skype for Business Server-Verwaltungsshell klicken. 
    
2. Geben Sie in der Verwaltungsshell den folgenden Befehl ein und drücken Sie die EINGABETASTE (geben Sie den tatsächlichen Pfad Ihrer Kopie von „Watchernode.msi“ ein):
    
```
C:\Tools\Watchernode.msi Authentication=TrustedServer
```

> [!NOTE]
> Sie können „Watchernode.msi“ auch aus einem Befehlsfenster ausführen. Klicken Sie zum Öffnen eines Befehlsfensters auf „Start“, klicken Sie mit der rechten Maustaste auf „Eingabeaufforderung“ und klicken Sie dann auf „Als Administrator ausführen“. Wenn das Befehlsfenster geöffnet wird, geben Sie den Befehl aus Schritt 2 ein. 
  
> [!IMPORTANT]
> Im vorstehenden Befehl unterliegt das Namen-/Wertepaar „Authentication=TrustedServer“ der Groß-/Kleinschreibung. Es muss genau wie angezeigt eingegeben werden. Bei der Ausführung dieses Befehls tritt ein Fehler auf, wenn nicht die richtige Abfolge von Groß- und Kleinbuchstaben verwendet wird: 
  
```
C:\Tools\Watchernode.msi authentication=trustedserver
```

Der TrustedServer-Modus kann nur auf Computern verwendet werden, die sich im Umkreisnetzwerk befinden. Wenn ein Monitorknoten im TrustedServer-Modus ausgeführt wird, müssen Administratoren keine Kennwörter für Testbenutzer auf dem Computer beibehalten.
  
## <a name="configure-a-watcher-node-to-use-negotiate"></a>Konfigurieren eines Monitorknotens für die Verwendung von „Negotiate“
<a name="enable_synthetic_trans"> </a>

Wenn Ihr Monitorknotencomputer außerhalb des Umkreisnetzwerks positioniert ist, müssen Sie ein etwas anderes Verfahren anwenden, um diesen Monitorknoten für die Ausführung synthetischer Transaktionen zu konfigurieren. Insbesondere sollten Sie keinen vertrauenswürdigen Anwendungspool und keine vertrauenswürdige Anwendung erstellen. Sie müssen daher die folgenden beiden Aufgaben ausführen.
  
### <a name="update-membership-in-the-rtc-local-read-only-administrators-group"></a>Aktualisieren der Mitgliedschaft in der Gruppe „RTC Local Read-only Administrators“

Wenn der Monitorknoten außerhalb des Umkreisnetzwerks positioniert ist, müssen Sie das Netzwerkdienstkonto auf dem Computer mit dem Monitorknoten der Gruppe „RTC Local Read-only Administrators“ hinzufügen, indem Sie auf dem Monitorknoten die folgenden Schritte ausführen:
  
1. Klicken Sie auf „Start“, klicken Sie mit der rechten Maustaste auf „Arbeitsplatz“ und klicken Sie dann auf „Verwalten“.
    
2. Erweitern Sie im Server-Manager „Konfiguration“ und „Lokale Benutzer und Gruppen“ und klicken Sie dann auf „Gruppen“.
    
3. Doppelklicken Sie im Bereich „Gruppen“ auf „RTC Local Read-only Administrators“.
    
4. Klicken Sie im Dialogfeld mit den Eigenschaften von „RTC Local Read-only Administrators“ auf „Hinzufügen“.
    
5. Klicken Sie im Dialogfeld für die Auswahl von Benutzern, Computern, Dienstkonten oder Gruppen auf „Standorte“.
    
6. Wählen Sie im Dialogfeld „Standorte“ den Namen des Monitorknotencomputers aus und klicken Sie dann auf „OK“.
    
7. Geben Sie im Feld „Geben Sie die zu verwendenden Objektnamen ein“ den Text „Netzwerkdienst“ ein und klicken Sie auf „OK“.
    
8. Klicken Sie im Dialogfeld mit den Eigenschaften von „RTC Local Read-only Administrators“ auf „OK“ und schließen Sie den Server-Manager.
    
9. Starten Sie den Monitorknotencomputer neu.
    
### <a name="install-the-watcher-node-configuration-files"></a>Installieren der Konfigurationsdateien des Monitorknotens

Führen Sie im nächsten Schritt die Datei „Watchernode.msi“ aus: 
  
1. Öffnen Sie die Microsoft Skype for Business Server 2015-Verwaltungsshell. Klicken Sie auf „Start“, zeigen Sie auf „Alle Programme“ und dann auf „Microsoft Skype for Business Server 2015“ und klicken Sie anschließend auf „Skype for Business Server-Verwaltungsshell“. 
    
2. Geben Sie in der Skype for Business Server-Verwaltungsshell den folgenden Befehl ein und drücken Sie dann die EINGABETASTE (achten Sie darauf, den tatsächlichen Pfad zu Ihrer Kopie der Datei „Watchernode.msi“ anzugeben):
    
   ```
   c:\Tools\Watchernode.msi Authentication=Negotiate
   ```

> [!NOTE]
> Wie bereits erwähnt, kann die Datei „Watchernode.msi“ auch über ein Befehlsfenster ausgeführt werden. Klicken Sie zum Öffnen eines Befehlsfensters auf **Start**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung** und klicken Sie dann auf **Als Administrator ausführen**. Geben Sie den in Schritt 2 gezeigten Befehl ein, nachdem das Befehlsfenster geöffnet wurde. 
  
Der Aushandlungsmodus wird verwendet, wenn der Monitorknoten nicht als Pool mit vertrauenswürdigen Anwendungen eingerichtet werden kann. In diesem Modus müssen Administratoren Testbenutzerkennwörter für den Monitorknoten verwalten.
  

