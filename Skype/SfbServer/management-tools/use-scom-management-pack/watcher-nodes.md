---
title: Installieren und Konfigurieren von Monitorknoten
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 11/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7392e4f8-6e2d-447b-aaa3-878f73995f9d
description: 'Zusammenfassung: Installieren und Konfigurieren von Watcher-Knoten für Skype für synthetische Transaktionen Business Server.'
ms.openlocfilehash: 6719826515954290f30eac272f638b846f45142a
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375986"
---
# <a name="install-and-configure-watcher-nodes"></a>Installieren und Konfigurieren von Monitorknoten
 
**Zusammenfassung:** Installieren und Konfigurieren von Watcher-Knoten für Skype für synthetische Transaktionen Business Server.
  
Watcher-Knoten sind Computer, die in regelmäßigen Abständen Skype für synthetische Transaktionen Business Server ausgeführt. Synthetische Transaktionen sind Windows PowerShell-Cmdlets, die überprüfen, ob wichtige Endbenutzerszenarien (wie die Fähigkeit zur Anmeldung beim System oder zum Austausch von Chatnachrichten) ordnungsgemäß funktionieren. System Center Operations Manager können für Skype für Business Server 2015 die synthetischen Transaktionen dargestellt in der folgenden Tabelle, die drei Typen von synthetischen Transaktionen enthält ausführen:
  
- **Standard** Synthetische Transaktionen, die ein Watcher-Knoten in der Standardeinstellung ausgeführt wird. Wenn Sie einen neuen Watcher-Knoten erstellen, können Sie angeben, welche synthetische Transaktionen, Knoten wird ausgeführt. (Das ist der Zweck des Parameters Tests, die vom Cmdlet "New-cswatchernodeconfiguration" verwendet.) Wenn Sie den Tests-Parameter nicht verwenden, wenn der Watcher-Knoten erstellt wird, wird automatisch alle synthetischen standardtransaktionen ausgeführt und kann nicht standardmäßige synthetischen Transaktionen nicht ausgeführt. Dies bedeutet z. B., dass der Watcher-Knoten wird zum Ausführen des Tests mit Test-CsAddressBookService konfiguriert werden, jedoch wird zum Ausführen des Test-CsExumConnectivity Tests nicht konfiguriert werden.
    
- **Nicht standardmäßige** Tests, die Watcher-Knoten standardmäßig nicht ausgeführt werden. (Weitere Informationen hierzu finden Sie unter der Beschreibung des Typs des standardmäßigen.) Allerdings kann der Watcher-Knoten zum Ausführen von synthetischen Transaktionen nicht standardmäßige aktiviert werden. Dies ist möglich, wenn Sie den Watcher-Knoten (mithilfe des Cmdlets "New-cswatchernodeconfiguration") erstellen, oder jederzeit danach den Watcher-Knoten erstellt wurde. Beachten Sie, dass viele synthetischen Transaktionen nicht standardmäßige zusätzliche Schritte erforderlich ist. Weitere Informationen zu diesen Schritten finden Sie unter spezielle Setupanweisungen für synthetische Transaktionen. Weitere Informationen zu diesen Schritten finden Sie unter [Spezielle Anweisungen zum Einrichten von synthetischen Transaktionen ](test-users-and-settings.md#special_synthetictrans).
    
- **Erweiterte** Eine spezielle Art von synthetischen Transaktionen nicht standardmäßige. Im Gegensatz zu anderen synthetischen Transaktionen können Extended Tests mehrmals bei jedem Durchlauf ausgeführt werden. Dies ist nützlich, wenn Verhalten, beispielsweise mehrere public switched Telephone Network, (PSTN) VoIP-Routen für einen Pool zu überprüfen. Sie können dies konfigurieren, indem Sie einfach mehrere Instanzen eines erweiterten Tests auf einem Watcher-Knoten hinzufügen.
    
Nähere Informationen über die Vorgehensweise zum Hinzufügen anderer synthetischer Transaktionen zu einem Monitorknoten finden Sie unter [Configure a Watcher Node to Run Synthetic Transactions](watcher-nodes.md#enable_synthetic_trans). Skype für Business Server-Verwaltungsshell können auch die um synthetische Transaktionen aus einem Watcher-Knoten zu entfernen.
  
Folgende synthetische Transaktionen sind für Monitorknoten verfügbar:
  
|**Name des Cmdlets (Name des Tests)**|**Beschreibung**|
|:-----|:-----|
|Test-CsAddressBookService (ABS)  <br/> |Bestätigt, dass Benutzer können Benutzer nachzuschlagen, die nicht in ihrer Kontaktliste stehen.  <br/> |
|Test-CsAddressBookWebQuery (ABWQ)  <br/> |Bestätigt, dass Benutzer können Benutzer nachzuschlagen, die nicht in ihrer Kontaktliste über HTTP sind.  <br/> |
|Test-CsAVConference (AvConference)  <br/> |Überprüft, ob Benutzer in der Lage sind, eine Audio-/Videokonferenz zu erstellen und daran teilzunehmen.  <br/> |
|Test-CsGroupIM (Chatkonferenz)  <br/> |Überprüft, ob Benutzer in der Lage sind, in Konferenzen Chatnachrichten zu senden und an Chatnachrichtenunterhaltungen mit drei oder mehr Personen teilzunehmen.  <br/> |
|Test-CsIM (P2P IM)  <br/> |Überprüft, ob Benutzer in der Lage sind, Peer-zu-Peer-Chatnachrichten zu senden.  <br/> |
|Test-CsP2PAV (P2PAV)  <br/> |Überprüft, ob Benutzer in der Lage sind, Peer-zu-Peer-Audioanrufe zu tätigen (nur Signal).  <br/> |
|Test-CsPresence (Anwesenheit)  <br/> |Bestätigt, dass Benutzer Anwesenheit anderer Benutzer anzeigen können.  <br/> |
|Test-CsRegistration (Registrierung)  <br/> |Bestätigt, dass Benutzer in der Lage, melden Sie sich bei Skype für Unternehmen sind.  <br/> |
|Test-CsPstnPeerToPeerCall (PSTN)  <br/> |Überprüft, ob Benutzer in der Lage sind, Anrufe von Personen außerhalb des Unternehmens (PSTN-Nummern) entgegenzunehmen oder diese anzurufen.  <br/> |
|Test-CsASConference (ASConference)  <br/> |Überprüft, ob Benutzer in der Lage sind, eine Anwendungsfreigabekonferenz zu erstellen und daran teilzunehmen.  <br/> |
|Test-CsAVEdgeConnectivity (AVEdgeConnectivity)  <br/> |Überprüft, ob die Audio-/Video-Edgeserver in der Lage sind, Verbindungen für Peer-zu-Peer-Anrufe und Konferenzanrufe entgegenzunehmen.  <br/> |
|Test-CsDataConference (DataConference)  <br/> |Überprüft, ob Benutzer an einer Datenzusammenarbeitskonferenz (eine Onlinebesprechung, zu der Aktivitäten wie Whiteboards und Umfragen gehören) teilnehmen können.  <br/> |
|Test-CsDialinConferencing (DialinConferencing)  <br/> |Überprüft, ob Benutzer Telefonnummern anrufen können, um an Konferenzen teilzunehmen.  <br/> |
|Test-CsDialinConferencing (DialinConferencing)  <br/> |Überprüft, ob Benutzer Telefonnummern anrufen können, um an Konferenzen teilzunehmen.  <br/> |
|Test-CsExumConnectivity (ExumConnectivity)  <br/> |Bestätigt, dass ein Benutzer eine Verbindung zu Exchange Unified Messaging (UM) herstellen kann.  <br/> |
|Mit Test-CsGroupIM - TestJoinLauncher (JoinLauncher)  <br/> |Überprüft, ob Benutzer geplante Besprechungen erstellen und an geplanten Besprechungen teilnehmen können (über einen Weblink).  <br/> |
|Test-CsMCXP2PIM (MCXP2PIM)  <br/> |Überprüft, ob Benutzer mit Mobilgeräten in der Lage sind, sich zu registrieren und Chatnachrichten zu senden.  <br/> |
|Test-CsP2PVideoInteropServerSipTrunkAV (P2PVideoInteropServerSipTrunkAV)  <br/> |Überprüft, ob Interop-Video-Server ist nicht gedrückt und eingehende Verbindungen über einen SIP-Trunk video behandeln können.  <br/> **Hinweis:** MCX-Unterstützung für mobile Clients von Vorversionen ist nicht mehr in Skype für Business Server 2019 verfügbar. |
|Test-CsPersistentChatMessage (PersistentChatMessage)  <br/> |Überprüft, ob Benutzer über den Dienst für beständigen Chat Sprachnachrichten austauschen können.  <br/> |
|Test-CsUcwaConference (UcwaConference)  <br/> |Überprüft, ob Benutzer über das Internet an Konferenzen teilnehmen können.  <br/> |
|Test-CsUnifiedContactStore (UnifiedContactStore)  <br/> |Überprüft, ob die Kontakte eines Benutzers über den einheitlichen Kontaktspeicher zugänglich sind. Dem einheitlichen Kontaktspeicher bietet eine Möglichkeit für Benutzer, die einen einzelnen Satz von Kontakten vorhalten, die mithilfe von Skype für Business Server 2015, Outlook messaging und Collaboration-Client und/oder Outlook Web Access zugegriffen werden kann.  <br/> |
|Test-CsXmppIM (XmppIM)  <br/> |Überprüft, ob eine Chatnachricht über das XMPP-Gateway (Extensible Messaging and Presence Protocol) gesendet werden kann.  <br/> XMPP-Gateways und -Proxys werden stehen in Skype für Business Server 2015 jedoch nicht mehr unterstützt in Skype für Business Server 2019.  |

Sie müssen nicht Watcher-Knoten, um mithilfe von System Center Operations Manager installieren. Wenn Sie diese Knoten nicht installieren, können Sie weiterhin abrufen in Echtzeit Benachrichtigungen von Skype für Business Server 2015 Komponenten Wenn ein Problem auftritt. (Der Komponente und User Management Pack verwendet keine Watcher-Knoten.) Watcher-Knoten sind jedoch erforderlich, wenn Sie die End-to-End-Szenarien mithilfe des aktiven Monitoring Management Packs überwachen möchten.
  
> [!NOTE]
> Administratoren können synthetische Transaktionen auch manuell ohne Verwendung oder Installation von Operations Manager ausführen. Je nach Größe Ihrer Skype für Business Server-Bereitstellung können synthetische Transaktionen eine große Menge an Arbeitsspeicher und Uhrzeit. Aus diesem Grund wird empfohlen, als Monitorknoten einen dedizierten Computer zu verwenden. Beispielsweise sollten Sie einen Skype für Business Server-Front-End-Server, die als Watcher-Knoten fungiert nicht konfigurieren. Watcher-Knoten sollten die gleichen grundlegenden hardwareanforderungen wie alle anderen Computer in Ihrer Skype für Business Server-Topologie erfüllen. 
  
> [!NOTE]
> Älterer Lync Server 2013 Watcher-Knoten kann nicht auf demselben Computer wie eine Skype für Business Server 2015 Watcher-Knoten kombiniert werden, da die System-Hauptdateien für Lync Server 2013 und Skype für Business Server 2015 auf demselben Computer installiert werden können. Skype für Business Server 2015 Watcher-Knoten kann jedoch gleichzeitig Skype für Business Server 2015 und Lync Server 2013 überwachen. Die synthetischen Transaktionen vom Typ „Standard“ werden in beiden Produktversionen unterstützt. 
  
Lync Server 2013 Watcher-Knoten können innerhalb oder außerhalb eines Unternehmens zu überprüfen bereitgestellt werden:
  
- Konnektivität zu Pools für Benutzer innerhalb des Unternehmens
    
- Konnektivität über Umkreisnetzwerke für Remotebenutzer, die außerhalb des Unternehmens arbeiten
    
- Konnektivität zu Branch Office Appliances
    
- Verbindung zu Lync Server 2013 innerhalb des Unternehmens und über Umkreisnetzwerke.
    
Zur leichteren Verwaltung stehen unterschiedliche Authentifizierungsoptionen für innerhalb oder außerhalb des Unternehmens bereitgestellte Monitorknoten zur Verfügung. Weitere Informationen finden Sie unter [Configure a Watcher Node to Run Synthetic Transactions](watcher-nodes.md#enable_synthetic_trans).
  
Wenn Sie einen Computer so konfigurieren möchten, dass er als Monitorknoten fungiert, müssen die folgenden Voraussetzungen erfüllt sein: 
  
- Installieren von System Center Operations Manager und die Skype für Business Server 2015 Management Packs importieren. Sie müssen auch zunächst sicherstellen, dass der Watcher-Knoten-Computer alle für die Installation von Skype für Business Server 2015 erfüllt.
    
- Installieren Sie die folgenden Elemente auf dem als Monitorknoten fungierenden Computer:
    
  - Die Vollversion von .NET Framework 4.5
    
  - Windows Identity Foundation
    
  - Windows PowerShell 3.0
    
Wenn alle Anforderungen erfüllt sind, können Sie den Monitorknoten mit den folgenden Schritten installieren:
  
1. Installieren Sie die Skype für Business Server 2015 Hauptdateien auf dem Watcher-Knoten-Computer.
    
2. Installieren von System Center Operations Manager-Agent auf dem Watcher-Knoten-Computer.
    
3. Ausführen der Datei „Watchernode.msi“
    
4. Konfigurieren von Testbenutzerkonten auf dem Monitorknoten mithilfe des Cmdlets **New-CsWatcherNodeConfiguration**
    
## <a name="install-the-skype-for-business-server-2015-core-files-and-the-rtclocal-database"></a>Installieren der Hauptdateien von Skype for Business Server 2015 und der RTCLocal-Datenbank

Gehen Sie folgendermaßen vor, um die Skype für Business Server 2015 Hauptdateien auf einem Computer zu installieren. Die RTCLocal-Datenbank wird zusammen mit den Hauptdateien automatisch installiert. Beachten Sie, dass Sie nicht auf den Watcher-Knoten SQL Server installieren müssen. SQL Server Express wird automatisch installiert.
  
So installieren Sie die Skype für Business Server 2015-Hauptdateien und die RTCLocal-Datenbank:
  
1. Klicken Sie auf dem Monitorknotencomputer auf „Start“, auf „Alle Programme“ und auf „Zubehör“. Klicken Sie mit der rechten Maustaste auf „Eingabeaufforderung“ und klicken Sie dann auf „Als Administrator ausführen“.
    
2. Geben Sie im Konsolenfenster den folgenden Befehl ein und drücken Sie die EINGABETASTE. Achten Sie darauf, den entsprechenden Pfad zu Ihrer Skype für Business Server-Setupdateien einzugeben: D:\Setup.exe /BootstrapLocalMgmtTo stellen Sie sicher, dass die Core Skype für Business Server-Komponenten erfolgreich installiert sind, klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, Klicken Sie auf **Skype für Business Server 2015**, und klicken Sie dann auf **Skype für Business Server-Verwaltungsshell**. Geben Sie in der Skype für Business Server-Verwaltungsshell den folgenden Windows PowerShell-Befehl ein, und drücken Sie die EINGABETASTE:
  
```
Get-CsWatcherNodeConfiguration
```

> [!NOTE]
> Bei der ersten Ausführung dieses Befehls werden keine Daten zurückgegeben, da noch keine Computer als Monitorknoten konfiguriert wurden. Wenn der Befehl ausgeführt wird, ohne dass einen Fehler zurückgegeben, können Sie davon ausgehen, dass die Skype für Business Server-Setup erfolgreich abgeschlossen. 
  
Befindet sich der Monitorknotencomputer in Ihrem Umkreisnetzwerk, können Sie den folgenden Befehl ausführen, um die Installation von Skype for Business Server 2015 zu überprüfen:
  
Get-CsPinPolicyYou erhalten Informationen wie die folgende, abhängig von der Anzahl der PIN-Richtlinien für die Verwendung in Ihrer Organisation konfiguriert sind:
  
Identität: globale
  
Beschreibung:
  
MinPasswordLength: 5
  
"Pinhistorycount": 0
  
AllowCommonPatterns: False
  
PINLifetime: 0
  
MaximumLogonAttempts :
  
Werden Informationen zu Ihren PIN-Richtlinien angezeigt, wurden die Hauptkomponenten erfolgreich installiert.
  
## <a name="install-the-operation-manager-agent-files-on-a-watcher-node"></a>Installieren der Operations Manager-Agent-Dateien auf einem Monitorknoten

Ähnlich wie bei Skype für Business Server-Setup für reporting Komponente Benachrichtigungen, erfordert einen Skype für Business Server 2015 Watcher-Knoten System Center Operations Manager-Agentdateien installiert werden soll. Auf diese Weise können die synthetische Transaktionen ausgeführt werden und Benachrichtigungen an der System Center Operations Manager-Stammverwaltungsserver gemeldet werden.
  
Um der Agent-Dateien zu installieren, führen Sie die Verfahren unter [Konfigurieren der Skype für Business Server-Computern, die überwacht werden,](configure-computers-to-monitor.md)aufgeführt.
  
## <a name="configure-a-watcher-node-to-run-synthetic-transactions"></a>Konfigurieren eines Monitorknotens für die Ausführung von synthetischen Transaktionen
<a name="enable_synthetic_trans"> </a>

Nachdem die System Center Operations Manager-Agentdateien installiert wurden, müssen Sie den Watcher-Knoten selbst konfigurieren. Welche Schritte Sie hierfür durchführen hängt davon ab, ob sich der Monitorknotencomputer innerhalb oder außerhalb Ihres Umkreisnetzwerks befindet. 
  
Beim Konfigurieren eines Monitorknotens müssen Sie außerdem die Authentifizierungsmethode auswählen, die von diesem Knoten verwendet werden soll. Skype für Business Server 2015 können Sie eine der beiden Authentifizierungsmethoden auswählen: vertrauenswürdige Server oder Authentifizierung mit Anmeldeinformationen. In der folgenden Tabelle sind die Unterschiede zwischen diesen beiden Methoden aufgeführt:
  
||**Beschreibung**|**Unterstützte Standorte**|
|:-----|:-----|:-----|
|TrustedServer  <br/> |Ein Zertifikat wird verwendet, um die Identität eines internen Servers anzunehmen und die Authentifizierungsaufforderungen zu umgehen.  <br/> Eignet sich für Administratoren, die es vorziehen, ein einzelnes Zertifikat anstelle vieler Benutzerkennwörter auf jedem Monitorknoten zu verwalten.  <br/> |Innerhalb des Unternehmens.  <br/> Bei dieser Methode muss sich der Monitorknoten in derselben Domäne wie die überwachten Pools befinden. Falls sich der Monitorknoten und die Pools in unterschiedlichen Domänen befinden, verwenden Sie stattdessen die Authentifizierung mit Anmeldeinformationen.  <br/> |
|Negotiate  <br/> |Benutzernamen und Kennwörter werden auf sichere Weise in der Windows-Anmeldeinformationsverwaltung auf jedem Monitorknoten gespeichert.  <br/> Dieser Modus erfordert einen höheren Kennwortverwaltungsaufwand, ist aber die einzige Option für Monitorknoten außerhalb des Unternehmens. Diese Monitorknoten können nicht als vertrauenswürdiger Endpunkt für die Authentifizierung betrachtet werden.  <br/> |Außerhalb des Unternehmens.  <br/> Innerhalb des Unternehmens.  <br/> |
   
## <a name="configure-a-watcher-node-to-use-trusted-server-authentication"></a>Konfigurieren eines Monitorknotens für die Verwendung der Authentifizierung über vertrauenswürdige Server
<a name="enable_synthetic_trans"> </a>

Wenn sich Ihr Monitorknotencomputer innerhalb des Umkreisnetzwerks befindet, können die Administrationsaufgaben durch die Verwendung der Authentifizierung über vertrauenswürdige Server deutlich verringert werden, indem ein einziges Zertifikat verwaltet wird, statt zahlreiche Benutzerkontokennwörter verwenden zu müssen.
  
Zum Konfigurieren der Authentifizierung über vertrauenswürdige Server müssen Sie zuerst einen vertrauenswürdigen Anwendungspool zum Hosten des Monitorknotencomputers erstellen. Nachdem Sie den vertrauenswürdigen Anwendungspool erstellt haben, müssen Sie synthetische Transaktionen klicken Sie dann auf diese Watcher-Knoten zum Ausführen als vertrauenswürdige Anwendungen konfigurieren.
  
> [!NOTE]
> Eine vertrauenswürdige Anwendung ist eine Anwendung, die als vertrauenswürdig eingestuft zum Ausführen als Teil des Skype für Business Server 2015 erhält, aber nicht integrierter Bestandteil des Produkts ist. Vertrauensstatus bedeutet, dass nicht bei jeder Ausführung der Anwendung eine Authentifizierung angefordert wird.
  
Um einen vertrauenswürdigen Anwendungspool zu erstellen, öffnen Sie die Skype für Business Server-Verwaltungsshell, und führen Sie einen Befehl wie den folgenden:
  
```
New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond
```

> [!NOTE]
> Ausführliche Informationen zu den Parametern im vorstehenden Befehl geben Sie den folgenden von der Skype für Aufforderung zur Business Server-Verwaltungsshell: 
  
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
  
Um sicherzustellen, dass die neue vertrauenswürdige Anwendung erstellt wurde, geben Sie an der Skype für Business Server-Verwaltungsshell Aufforderung Folgendes ein:
  
```
Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"
```

## <a name="configure-a-default-certificate-on-the-watcher-node"></a>Konfigurieren eines Standardzertifikats auf dem Monitorknoten
<a name="enable_synthetic_trans"> </a>

Jedem Watcher-Knoten, die TrustedServer-Authentifizierung verwendet, benötigen ein Standardzertifikat mithilfe der Skype für Business Server-Bereitstellungsassistenten zugewiesen. 
  
So weisen Sie ein Standardzertifikat zu
  
1. Klicken Sie auf Start, klicken Sie auf alle Programme, klicken Sie auf Skype für Business Server 2015, und klicken Sie dann auf Skype für Business Server-Bereitstellungs-Assistenten. 
    
2. In der Skype für Business Server-Bereitstellungs-Assistenten installieren oder aktualisieren Skype für Business Server-System auf und klicken Sie dann auf Ausführen unter der Überschrift anfordern, installieren oder Zertifikat zuweisen. 
    
> [!NOTE]
> Wenn die Schaltfläche „Ausführen“ deaktiviert ist, müssen Sie möglicherweise zunächst unter „Lokalen Konfigurationsspeicher installieren“ auf „Ausführen“ klicken. 
  
Führen Sie einen der folgenden Schritte aus:
  
- Wenn Sie bereits ein Zertifikat besitzen, das als Standardzertifikat verwendet werden kann, klicken Sie im Zertifikat-Assistenten auf „Standard“ und anschließend auf „Zuweisen“. Befolgen Sie die Anweisungen des Zertifikat-Assistenten, um das Zertifikat zuzuweisen.
    
- Wenn Sie ein Zertifikat für die Verwendung als Standardzertifikat anfordern müssen, klicken Sie auf „Anfordern“ und folgen Sie den Schritten im Zertifikatanforderungs-Assistenten, um das Zertifikat anzufordern. Wenn Sie die Standardwerte für das Webserverzertifikat verwenden, erhalten Sie ein Zertifikat, das Sie als Standardzertifikat zuweisen können.
    
## <a name="install-and-configure-a-watcher-node"></a>Installieren und Konfigurieren eines Monitorknotens
<a name="enable_synthetic_trans"> </a>

Nachdem Sie den Monitorknotencomputer neu gestartet und ein Zertifikat konfiguriert haben, müssen Sie die Datei „Watchernode.msi“ ausführen. (Sie müssen ausgeführt Watchernode.msi auf jedem Computer, auf dem die Operations Manager-Agent-Dateien und die Skype für Business Server 2015 Hauptkomponenten installiert.) 
  
So installieren und konfigurieren Sie einen Monitorknoten
  
1. Öffnen Sie die Skype für Business Server-Verwaltungsshell, indem Sie auf Start, alle Programme, auf Skype für Business Server 2015, und klicken Sie dann auf Skype für Business Server-Verwaltungsshell. 
    
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
  

