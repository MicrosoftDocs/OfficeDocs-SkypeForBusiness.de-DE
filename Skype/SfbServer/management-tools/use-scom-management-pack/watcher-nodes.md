---
title: Installieren und Konfigurieren von Monitorknoten
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 11/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 7392e4f8-6e2d-447b-aaa3-878f73995f9d
description: So installieren und konfigurieren Sie Watcher-Knoten für Skype for Business Server synthetische Transaktionen.
ms.openlocfilehash: aca051b005c3ec9a901c5366a7788af5e95d06f0
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60766213"
---
# <a name="how-to-install-and-configure-watcher-nodes"></a>Installieren und Konfigurieren von Monitorknoten
 
**Zusammenfassung:** Installieren und konfigurieren Sie Monitorknoten für Skype for Business Server synthetische Transaktionen.
  
Monitorknoten sind Computer, die regelmäßig Skype for Business Server synthetische Transaktionen ausführen. Synthetische Transaktionen sind Windows PowerShell Cmdlets, die überprüfen, ob wichtige Benutzerszenarien wie die Möglichkeit, sich anzumelden oder Chatnachrichten auszutauschen, erwartungsgemäß funktionieren. For Skype for Business Server 2015, System Center Operations Manager can run the synthetic transactions shown in the following table, which includes three synthetic transaction types:
  
- **Standardeinstellung** Synthetische Transaktionen, die standardmäßig von einem Watcher-Knoten ausgeführt werden. Wenn Sie einen neuen Watcher-Knoten erstellen, können Sie angeben, welche synthetischen Transaktionen dieser Knoten ausführen wird. (Dies ist der Zweck des Tests-Parameters, der vom Cmdlet New-CsWatcherNodeConfiguration verwendet wird.) Wenn Sie beim Erstellen des Watcher-Knotens nicht den Parameter "Tests" verwenden, werden automatisch alle synthetischen Standardtransaktionen und keine der nicht standardmäßigen synthetischen Transaktionen ausgeführt. Dies bedeutet beispielsweise, dass der Monitorknoten für die Ausführung des Test-CsAddressBookService Tests konfiguriert ist, aber nicht für die Ausführung des Test-CsExumConnectivity Tests konfiguriert ist.
    
- **Nicht standardmäßig** Tests, bei denen Monitorknoten nicht standardmäßig ausgeführt werden. (Ausführliche Informationen finden Sie in der Beschreibung des Standardtyps.) Der Monitorknoten kann jedoch aktiviert werden, um alle nicht standardmäßigen synthetischen Transaktionen auszuführen. Sie können dies tun, wenn Sie den Watcher-Knoten (mithilfe des Cmdlets New-CsWatcherNodeConfiguration) oder jederzeit nach dem Erstellen des Watcher-Knotens erstellen. Beachten Sie, dass viele der nicht standardmäßigen synthetischen Transaktionen zusätzliche Einrichtungsschritte erfordern. Weitere Informationen zu diesen Schritten finden Sie in [den speziellen Setupanweisungen für synthetische Transaktionen.](test-users-and-settings.md#special_synthetictrans)
    
- **Erweitert** Ein spezieller Typ einer nicht standardmäßigen synthetischen Transaktion. Im Unterschied zu anderen synthetischen Transaktionen können sie bei jedem Durchgang mehrere Male ausgeführt werden. Dies ist beim Überprüfen des Verhaltens hilfreich, z. B. bei mehreren PSTN-VoIP-Routen (Public Switched Telephone Network) für einen Pool. Sie können dies einfach konfigurieren, indem Sie einem Monitorknoten mehrere Instanzen eines erweiterten Tests hinzufügen.
    
Ausführliche Informationen zum Verfahren zum Hinzufügen anderer synthetischer Transaktionen zu einem Watcher-Knoten finden Sie unter [Konfigurieren eines Watcher-Knotens zum Ausführen synthetischer Transaktionen.](watcher-nodes.md#enable_synthetic_trans) Sie können auch Skype for Business Server Verwaltungsshell verwenden, um synthetische Transaktionen aus einem Watcher-Knoten zu entfernen.
  
Zu den für Watcher-Knoten verfügbaren synthetischen Transaktionen gehören:
  
|**Cmdlet-Name (Test-Name)**|**Beschreibung**|
|:-----|:-----|
|Test-CsAddressBookService (ABS)  <br/> |Bestätigt, dass Benutzer in der Lage sind, Benutzer nachzuschlagen, die sich nicht in ihrer Kontaktliste befinden.  <br/> |
|Test-CsAddressBookWebQuery (ABWQ)  <br/> |Bestätigt, dass Benutzer Benutzer, die sich nicht in ihrer Kontaktliste befinden, über HTTP nachschlagen können.  <br/> |
|Test-CsAVConference (AvConference)  <br/> |Überprüft, ob Benutzer in der Lage sind, eine Audio-/Videokonferenz zu erstellen und daran teilzunehmen.  <br/> |
|Test-CsGroupIM (Chatkonferenzen)  <br/> |Überprüft, ob Benutzer in der Lage sind, in Konferenzen Sofortnachrichten zu senden und an Sofortnachrichtengesprächen mit drei oder mehr Personen teilzunehmen.  <br/> |
|Test-CsIM (P2P-Chat)  <br/> |Überprüft, ob Benutzer in der Lage sind, Peer-zu-Peer-Sofortnachrichten zu senden.  <br/> |
|Test-CsP2PAV (P2PAV)  <br/> |Überprüft, ob Benutzer in der Lage sind, Peer-zu-Peer-Audioanrufe zu tätigen (nur Signal).  <br/> |
|Test-CsPresence (Anwesenheit)  <br/> |Bestätigt, dass Benutzer in der Lage sind, die Anwesenheit anderer Benutzer anzuzeigen.  <br/> |
|Test-CsRegistration (Registrierung)  <br/> |Bestätigt, dass sich Benutzer bei Skype for Business anmelden können.  <br/> |
|Test-CsPstnPeerToPeerCall (PSTN)  <br/> |Überprüft, ob Benutzer in der Lage sind, Anrufe von Personen außerhalb des Unternehmens (PSTN-Nummern) entgegenzunehmen oder diese anzurufen.  <br/> |
|Test-CsASConference (ASConference)  <br/> |Bestätigt, dass Benutzer in der Lage sind, eine Konferenz zur Anwendungsfreigabe zu erstellen und daran teilzunehmen.  <br/> |
|Test-CsAVEdgeConnectivity (AVEdgeConnectivity)  <br/> |Bestätigt, dass die Audiovideo-Edgeserver Verbindungen für Peer-to-Peer-Anrufe und Konferenzanrufe annehmen können.  <br/> |
|Test-CsDataConference (DataConference)  <br/> |Bestätigt, dass Benutzer an einer Konferenz zur Datenzusammenarbeit teilnehmen können (einer Onlinebesprechung, die Aktivitäten wie Whiteboards und Umfragen umfasst).  <br/> |
|Test-CsDialinConferencing (DialinConferencing)  <br/> |Bestätigt, dass Benutzer Telefonnummern wählen können, um an Konferenzen teilzunehmen.  <br/> |
|Test-CsDialinConferencing (DialinConferencing)  <br/> |Bestätigt, dass Benutzer Telefonnummern wählen können, um an Konferenzen teilzunehmen.  <br/> |
|Test-CsExumConnectivity (ExumConnectivity)  <br/> |Bestätigt, dass ein Benutzer eine Verbindung mit Exchange Unified Messaging (UM) herstellen kann.  <br/> |
|Test-CsGroupIM -TestJoinLauncher (JoinLauncher)  <br/> |Bestätigt, dass Benutzer geplante Besprechungen (über einen Webadressenlink) erstellen und daran teilnehmen können.  <br/> |
|Test-CsMCXP2PIM (MCXP2PIM)  <br/> |Überprüft, ob Benutzer mit Mobilgeräten in der Lage sind, sich zu registrieren und Sofortnachrichten zu senden.  <br/> |
|Test-CsP2PVideoInteropServerSipTrunkAV (P2PVideoInteropServerSipTrunkAV)  <br/> |Bestätigt, dass der Video-Interoperabilitätsserver aktiviert ist und eingehende Verbindungen über einen Video-SIP-Trunk verarbeiten kann.  <br/> **Hinweis:** MCX-Unterstützung für mobile Legacyclients ist in Skype for Business Server 2019 nicht mehr verfügbar. |
|Test-CsPersistentChatMessage (PersistentChatMessage)  <br/> |Bestätigt, dass Benutzer Nachrichten mithilfe des Diensts für beständigen Chat austauschen können.  <br/> |
|Test-CsUcwaConference (UcwaConference)  <br/> |Bestätigt, dass Benutzer über das Web an Konferenzen teilnehmen können.  <br/> |
|Test-CsUnifiedContactStore (UnifiedContactStore)  <br/> |Überprüft, ob die Kontakte eines Benutzers über den einheitlichen Kontaktspeicher zugänglich sind. Der einheitliche Kontaktspeicher bietet Benutzern die Möglichkeit, eine einzelne Gruppe von Kontakten zu verwalten, auf die mithilfe von Skype for Business Server 2015, Outlook Messaging- und Zusammenarbeitsclient und/oder Outlook Web Access zugegriffen werden kann.  <br/> |
|Test-CsXmppIM (XmppIM)  <br/> |Bestätigt, dass eine Chatnachricht über das XMPP-Gateway (Extensible Messaging and Presence Protocol) gesendet werden kann.  <br/> XMPP-Gateways und Proxys sind in Skype for Business Server 2015 verfügbar, werden jedoch in Skype for Business Server 2019 nicht mehr unterstützt.  |

Sie müssen keine Monitorknoten installieren, um System Center Operations Manager zu verwenden. Wenn Sie diese Knoten nicht installieren, können Sie immer noch Echtzeitwarnungen von Skype for Business Server 2015-Komponenten erhalten, wenn ein Problem auftritt. (Das Component and User Management Pack verwendet keine Monitorknoten.) Watcher-Knoten sind jedoch erforderlich, wenn Sie End-to-End-Szenarien mithilfe des Active Monitoring Management Packs überwachen möchten.
  
> [!NOTE]
> Administratoren können synthetische Transaktionen auch manuell ausführen, ohne Operations Manager zu verwenden oder zu installieren. Abhängig von der Größe Ihrer Skype for Business Server Bereitstellung können synthetische Transaktionen einen großen Teil des Computerspeichers und der Prozessorzeit belegen. Aus diesem Grund wird empfohlen, einen dedizierten Computer als Monitorknoten zu verwenden. Sie sollten beispielsweise keinen Skype for Business Server Front-End-Server so konfigurieren, dass er als Monitorknoten fungiert. Monitorknoten sollten die gleichen grundlegenden Hardwareanforderungen erfüllen wie jeder andere Computer in Ihrer Skype for Business Server Topologie. 
  
> [!NOTE]
> Ein legacy Lync Server 2013 Watcher-Knoten kann nicht auf demselben Computer wie ein Skype for Business Server 2015 Watcher-Knoten verbunden werden, da die Kernsystemdateien für Lync Server 2013 und Skype for Business Server 2015 nicht auf demselben Computer installiert werden können. Skype for Business Server 2015 Watcher-Knoten können jedoch Skype for Business Server 2015 und Lync Server 2013 gleichzeitig überwachen. Synthetische Standardtransaktionen werden für beide Produktversionen unterstützt. 
  
Lync Server 2013 Watcher-Knoten können innerhalb oder außerhalb eines Unternehmens bereitgestellt werden, um Folgendes zu überprüfen:
  
- Konnektivität zu Pools für Benutzer innerhalb des Unternehmens
    
- Konnektivität über Umkreisnetzwerke für Remotebenutzer, die außerhalb des Unternehmens arbeiten.
    
- Konnektivität zu Branch Office Appliances
    
- Konnektivität zu Lync Server 2013 innerhalb des Unternehmens und über Umkreisnetzwerke.
    
Um die Verwaltung zu vereinfachen, stehen innerhalb und außerhalb des Unternehmens unterschiedliche Authentifizierungsoptionen zur Verfügung. Ausführliche Informationen finden Sie unter [Konfigurieren eines Watcher-Knotens zum Ausführen synthetischer Transaktionen.](watcher-nodes.md#enable_synthetic_trans)
  
Um einen Computer so zu konfigurieren, dass er als Monitorknoten fungiert, müssen Sie zunächst die folgenden Voraussetzungen erfüllen: 
  
- Installieren Sie System Center Operations Manager, und importieren Sie die Skype for Business Server 2015 Management Packs. Außerdem müssen Sie zunächst überprüfen, ob der Monitorknotencomputer alle Voraussetzungen für die Installation von Skype for Business Server 2015 erfüllt.
    
- Installieren Sie die folgenden Elemente auf dem Monitorknotencomputer:
    
  - Die Vollversion von .NET Framework 4.5
    
  - Windows Identity Foundation
    
  - Windows PowerShell 3.0
    
Nachdem die Voraussetzungen erfüllt sind, können Sie den Watcher-Knoten konfigurieren, indem Sie die folgenden Schritte ausführen:
  
1. Installieren Sie die Skype for Business Server 2015-Kerndateien auf dem Monitorknotencomputer.
    
2. Installieren Sie System Center Operations Manager-Agent auf dem Monitorknotencomputer.
    
3. Führen Sie die Watchernode.msi ausführbare Datei aus.
    
4. Verwenden Sie das Cmdlet **"New-CsWatcherNodeConfiguration",** um Testbenutzerkonten zu konfigurieren, die vom Monitorknoten verwendet werden sollen.
    
## <a name="install-the-skype-for-business-server-2015-core-files-and-the-rtclocal-database"></a>Installieren der Skype for Business Server 2015 Core-Dateien und der RTCLocal-Datenbank

Führen Sie das folgende Verfahren aus, um die Skype for Business Server 2015-Kerndateien auf einem Computer zu installieren. Die RTCLocal-Datenbank wird automatisch installiert, wenn Sie die Kerndateien installieren. Beachten Sie, dass Sie SQL Server auf den Monitorknoten nicht installieren müssen. SQL Server Express wird automatisch installiert.
  
So installieren Sie die Skype for Business Server 2015-Kerndateien und die RTCLocal-Datenbank:
  
1. Klicken Sie auf dem Watcher-Knoten-Computer auf Start, Alle Programme und Zubehör, klicken Sie mit der rechten Maustaste auf Eingabeaufforderung, und klicken Sie dann auf Als Administrator ausführen.
    
2. Geben Sie im Konsolenfenster den folgenden Befehl ein, und drücken Sie die EINGABETASTE. Geben Sie unbedingt den entsprechenden Pfad zu Den Skype for Business Server Setupdateien ein: D:\Setup.exe /BootstrapLocalMgmtTo verify that the core Skype for Business Server components are successfully installed, click **Start**, click **All Programs**, click **Skype for Business Server 2015**, und klicken Sie dann auf **Skype for Business Server Verwaltungsshell**. Geben Sie in der Skype for Business Server Verwaltungsshell den folgenden befehl Windows PowerShell ein, und drücken Sie die EINGABETASTE:
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

> [!NOTE]
> Wenn Sie diesen Befehl zum ersten Mal ausführen, werden keine Daten zurückgegeben, da Sie noch keine Monitorknotencomputer konfiguriert haben. Wenn der Befehl ohne Fehler ausgeführt wird, können Sie davon ausgehen, dass die Skype for Business Server Setup erfolgreich abgeschlossen wurde. 
  
Wenn sich ihr Monitorknotencomputer in Ihrem Umkreisnetzwerk befindet, können Sie den folgenden Befehl ausführen, um die Installation von Skype for Business Server 2015 zu überprüfen:
  
Get-CsPinPolicyYou erhalten informationen wie diese, abhängig von der Anzahl der PIN-Richtlinien, die für die Verwendung in Ihrer Organisation konfiguriert sind:
  
Identität : Global
  
Beschreibung:
  
MinPasswordLength : 5
  
PINHistoryCount : 0
  
AllowCommonPatterns : False
  
PINLifetime : 0
  
MaximumLogonAttempts:
  
Wenn Informationen zu Ihren PIN-Richtlinien angezeigt werden, wurden die Hauptkomponenten erfolgreich installiert.
  
## <a name="install-the-operation-manager-agent-files-on-a-watcher-node"></a>Installieren der Operation Manager-Agent-Dateien auf einem Watcher-Knoten

Ähnlich wie bei Skype for Business Server Einrichtung für das Melden von Komponentenwarnungen muss für einen Skype for Business Server 2015 Watcher-Knoten System Center Operations Manager-Agent-Dateien installiert werden. Dadurch können synthetische Transaktionen ausgeführt und Warnungen an den System Center Operations Manager-Stammverwaltungsserver gemeldet werden.
  
Führen Sie zum Installieren der Agentdateien die unter [Konfigurieren der Skype for Business Server Computer, die überwacht werden, aufgeführten](configure-computers-to-monitor.md)Verfahren aus.
  
## <a name="configure-a-watcher-node-to-run-synthetic-transactions"></a>Konfigurieren eines Watcher-Knotens zum Ausführen synthetischer Transaktionen
<a name="enable_synthetic_trans"> </a>

Nachdem die System Center Operations Manager-Agent-Dateien installiert wurden, müssen Sie den Monitorknoten selbst konfigurieren. Welche Schritte Sie dazu ausführen, hängt davon ab, ob sich ihr Monitorknotencomputer innerhalb ihres Umkreisnetzwerks oder außerhalb Ihres Umkreisnetzwerks befindet. 
  
Beim Konfigurieren eines Watcher-Knotens müssen Sie außerdem die Authentifizierungsmethode auswählen, die von diesem Knoten verwendet werden soll. Skype for Business Server 2015 können Sie eine von zwei Authentifizierungsmethoden auswählen: Vertrauenswürdiger Server oder Anmeldeinformationsauthentifizierung. Die folgende Tabelle zeigt die Unterschiede zwischen diesen beiden Methoden:
  
|&nbsp;|**Beschreibung**|**Unterstützte Speicherorte**|
|:-----|:-----|:-----|
|TrustedServer  <br/> |Ein Zertifikat wird verwendet, um die Identität eines internen Servers anzunehmen und die Authentifizierungsaufforderungen zu umgehen.  <br/> Nützlich für Administratoren, die ein einzelnes Zertifikat anstelle vieler Benutzer-Kennwörter auf jedem Monitorknoten verwalten möchten.  <br/> |Innerhalb des Unternehmens.  <br/> Bei dieser Methode muss sich der Monitorknoten in derselben Domäne wie die überwachten Pools befinden. Wenn sich der Monitorknoten und die Pools in verschiedenen Domänen befinden, verwenden Sie stattdessen die Anmeldeinformationsauthentifizierung.  <br/> |
|Verhandeln  <br/> |Benutzernamen und Kennwörter werden auf sichere Weise in der Windows-Anmeldeinformationsverwaltung auf jedem Watcher-Knoten gespeichert.  <br/> Dieser Modus erfordert mehr Kennwortverwaltung, ist aber die einzige Option für Monitorknoten außerhalb des Unternehmens. Diese Watcher-Knoten können nicht als Endpunkt, der bezüglich der Authentifizierung vertrauenswürdig ist, betrachtet werden.  <br/> |Außerhalb des Unternehmens.  <br/> Innerhalb des Unternehmens.  <br/> |
   
## <a name="configure-a-watcher-node-to-use-trusted-server-authentication"></a>Konfigurieren eines Watcher-Knotens für die Verwendung der Authentifizierung mit vertrauenswürdigen Servern
<a name="enable_synthetic_trans"> </a>

Wenn sich ihr Monitorknotencomputer im Umkreisnetzwerk befindet, kann die Verwendung der Trusted Server-Authentifizierung verwaltungsvorgänge erheblich reduzieren, indem ein einzelnes Zertifikat verwaltet wird, anstatt zahlreiche Benutzerkonten-Kennwörter zu verwenden.
  
Um die Authentifizierung mit vertrauenswürdigen Servern zu konfigurieren, müssen Sie zuerst einen vertrauenswürdigen Anwendungspool erstellen, um den Monitorknotencomputer zu hosten. Nachdem Sie den vertrauenswürdigen Anwendungspool erstellt haben, müssen Sie synthetische Transaktionen auf diesem Watcher-Knoten so konfigurieren, dass sie als vertrauenswürdige Anwendungen ausgeführt werden.
  
> [!NOTE]
> Eine vertrauenswürdige Anwendung ist eine Anwendung, der der vertrauenswürdige Status für die Ausführung als Teil von Skype for Business Server 2015 zugewiesen wird, die jedoch kein integrierter Bestandteil des Produkts ist. Vertrauensstatus bedeutet, dass nicht bei jeder Ausführung der Anwendung eine Authentifizierung angefordert wird.
  
Um einen vertrauenswürdigen Anwendungspool zu erstellen, öffnen Sie die Skype for Business Server-Verwaltungsshell, und führen Sie einen Befehl wie den folgenden aus:
  
```PowerShell
New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond
```

> [!NOTE]
> Geben Sie an der Eingabeaufforderung der Skype for Business Server Verwaltungsshell Folgendes ein, um Details zu den Parametern im vorherigen Befehl zu erhalten: 
  
```PowerShell
Get-Help New-CsTrustedApplicationPool -Full | more
```

Nach dem Erstellen des vertrauenswürdigen Anwendungspools können Sie den Monitorknotencomputer so konfigurieren, dass synthetische Transaktionen als vertrauenswürdige Anwendung ausgeführt werden, indem Sie das Cmdlet **"New-CsTrustedApplication"** und einen Befehl wie den folgenden verwenden:
  
```PowerShell
New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061
```

Wenn dieser Befehl abgeschlossen ist und die vertrauenswürdige Anwendung erstellt wird, müssen Sie das Cmdlet **"Enable-CsTopology"** ausführen, um sicherzustellen, dass die Änderungen wirksam werden:
  
```PowerShell
Enable-CsTopology
```

Das Computerkonto des Watcher-Knotens erfordert die Möglichkeit, cms für einige synthetische Transaktionen abfragt. Um diese Möglichkeit zuzulassen, fügen Sie das Computerkonto des Watcher-Knotens zur Sicherheitsgruppe "RTCUniversalReadOnlyAdmins" hinzu. Starten Sie den Computer neu, nachdem die AD-Replikation erfolgt ist.
  
Um zu überprüfen, ob die neue vertrauenswürdige Anwendung erstellt wurde, geben Sie Folgendes an der Eingabeaufforderung der Skype for Business Server Verwaltungsshell ein:
  
```PowerShell
Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"
```

## <a name="configure-a-default-certificate-on-the-watcher-node"></a>Konfigurieren eines Standardzertifikats auf dem Monitorknoten
<a name="enable_synthetic_trans"> </a>

Jedem Watcher-Knoten, der die TrustedServer-Authentifizierung verwendet, muss mithilfe des Skype for Business Server Bereitstellungs-Assistenten ein Standardzertifikat zugewiesen sein. 
  
So weisen Sie ein Standardzertifikat zu:
  
1. Klicken Sie auf "Start", auf "Alle Programme", auf Skype for Business Server 2015 und dann auf Skype for Business Server Bereitstellungs-Assistenten. 
    
2. Klicken Sie im Bereitstellungs-Assistenten Skype for Business Server auf Skype for Business Server System installieren oder aktualisieren, und klicken Sie dann unter der Überschrift "Zertifikat anfordern", "Installieren" oder "Zuweisen" auf "Ausführen". 
    
> [!NOTE]
> Wenn die Schaltfläche Ausführen deaktiviert ist, müssen Sie möglicherweise zunächst unter Lokalen Konfigurationsspeicher installieren auf Ausführen klicken. 
  
Führen Sie einen der folgenden Schritte aus:
  
- Wenn Sie bereits über ein Zertifikat verfügen, das als Standardzertifikat verwendet werden kann, klicken Sie im Zertifikat-Assistenten auf "Standard", und klicken Sie dann auf "Zuweisen". Befolgen Sie die Anweisungen des Zertifikat-Assistenten, um das Zertifikat zuzuweisen.
    
- Wenn Sie ein Zertifikat für die Verwendung des Standardzertifikats anfordern müssen, klicken Sie auf "Anfordern", und führen Sie dann die Schritte im Zertifikatanforderungs-Assistenten aus, um dieses Zertifikat anzufordern. Wenn Sie die Standardwerte für das Webserver-Zertifikat verwenden, erhalten Sie ein Zertifikat, das Sie als Standardzertifikat zuweisen können.
    
## <a name="install-and-configure-a-watcher-node"></a>Installieren und Konfigurieren eines Watcher-Knotens
<a name="enable_synthetic_trans"> </a>

Nachdem Sie den Monitorknotencomputer neu gestartet und ein Zertifikat konfiguriert haben, müssen Sie die Datei Watchernode.msi ausführen. (Sie müssen Watchernode.msi auf jedem Computer ausführen, auf dem sowohl die Operations Manager-Agentdateien als auch die Skype for Business Server 2015-Kernkomponenten installiert sind.) 
  
So installieren und konfigurieren Sie einen Watcher-Knoten:
  
1. Öffnen Sie die Skype for Business Server Verwaltungsshell, indem Sie auf "Start", "Alle Programme", "Skype for Business Server 2015" und dann auf Skype for Business Server Verwaltungsshell klicken. 
    
2. Geben Sie in der Verwaltungsshell den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE (achten Sie darauf, und geben Sie den tatsächlichen Pfad zu Ihrer Kopie von Watchernode.msi an):
    
```PowerShell
C:\Tools\Watchernode.msi Authentication=TrustedServer
```

> [!NOTE]
> Sie können auch Watchernode.msi n in einem Befehlsfenster ausführen. Klicken Sie zum Öffnen eines Befehlsfensters auf Start, klicken Sie mit der rechten Maustaste auf Eingabeaufforderung, und klicken Sie dann auf Als Administrator ausführen. Wenn das Befehlsfenster geöffnet wird, geben Sie denselben Befehl wie in Schritt 2 oben ein. 
  
> [!IMPORTANT]
> Im vorherigen Befehl wird beim Namen-Wert-Paar "Authentication=TrustedServer" die Groß-/Kleinschreibung beachtet. Sie muss genau wie dargestellt eingegeben werden. Dieser Befehl schlägt beispielsweise fehl, da er nicht die richtige Groß-/Kleinschreibung verwendet: 
  
```PowerShell
C:\Tools\Watchernode.msi authentication=trustedserver
```

Der TrustedServer-Modus kann nur für Computer verwendet werden, die sich innerhalb des Umkreisnetzwerks befinden. Wenn ein Monitorknoten im TrustedServer-Modus ausgeführt wird, müssen Administratoren keine Testbenutzer-Kennwörter auf dem Computer verwalten.
  
## <a name="configure-a-watcher-node-to-use-negotiate"></a>Konfigurieren eines Watcher-Knotens für die Verwendung von Negotiate
<a name="enable_synthetic_trans"> </a>

Wenn sich ihr Monitorknotencomputer außerhalb des Umkreisnetzwerks befindet, müssen Sie ein etwas anderes Verfahren ausführen, um diesen Watcher-Knoten so zu konfigurieren, dass synthetische Transaktionen ausgeführt werden: Insbesondere sollten Sie keinen vertrauenswürdigen Anwendungspool oder eine vertrauenswürdige Anwendung erstellen. Das bedeutet, dass Sie die nächsten beiden Aufgaben ausführen müssen.
  
### <a name="update-membership-in-the-rtc-local-read-only-administrators-group"></a>Aktualisieren der Mitgliedschaft in der Gruppe "RTC Local Read-Only Administrators"

Wenn der Monitorknoten außerhalb des Umkreisnetzwerks liegt, müssen Sie das Netzwerkdienstkonto der Gruppe "RTC Local Read-only Administrators" auf dem Monitorknotencomputer hinzufügen, indem Sie das folgende Verfahren auf dem Monitorknoten ausführen:
  
1. Klicken Sie auf Start, klicken Sie mit der rechten Maustaste auf Arbeitsplatz, und klicken Sie dann auf Verwalten.
    
2. Erweitern Sie im Server-Manager die Optionen Konfiguration und Lokale Benutzer und Gruppen, und klicken Sie dann auf Gruppen.
    
3. Doppelklicken Sie im Bereich "Gruppen" mit der rechten Maustaste auf RTC Local Read-only Administrators.
    
4. Klicken Sie im Dialogfeld mit den Eigenschaften von RTC Local Read-only Administrators auf Hinzufügen.
    
5. Klicken Sie im Dialogfeld für die Auswahl von Benutzern, Computern, Dienstkonten oder Gruppen auf Standorte.
    
6. Wählen Sie im Dialogfeld Standorte den Namen des Monitorknotencomputers aus, und klicken Sie dann auf OK.
    
7. Geben Sie im Feld Geben Sie die zu verwendenden Objektnamen ein den Text Netzwerkdienst ein, und klicken Sie auf OK.
    
8. Klicken Sie im Dialogfeld mit den Eigenschaften von RTC Local Read-only Administrators auf OK, und schließen Sie den Server-Manager.
    
9. Starten Sie den Monitorknotencomputer neu.
    
### <a name="install-the-watcher-node-configuration-files"></a>Installieren der Konfigurationsdateien des Watcher-Knotens

Der nächste Schritt besteht darin, die Datei Watchernode.msi auszuführen: 
  
1. Öffnen Sie die Microsoft Skype for Business Server 2015-Verwaltungsshell. Klicken Sie auf "Start", "Alle Programme", auf "Microsoft Skype for Business Server 2015" und dann auf Skype for Business Server Verwaltungsshell. 
    
2. Geben Sie in Skype for Business Server Verwaltungsshell den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE (geben Sie unbedingt den tatsächlichen Pfad zu Ihrer Kopie von Watchernode.msi an):
    
   ```PowerShell
   c:\Tools\Watchernode.msi Authentication=Negotiate
   ```

> [!NOTE]
> Wie bereits erwähnt, können Watchernode.msi auch über ein Befehlsfenster ausgeführt werden. Klicken Sie zum Öffnen eines Befehlsfensters auf **Start**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und klicken Sie dann auf **Als Administrator ausführen**. Wenn das Befehlsfenster geöffnet wird, geben Sie denselben Befehl wie in Schritt 2 oben ein. 
  
Der Aushandlungsmodus wird verwendet, wenn der Monitorknoten nicht als Pool mit vertrauenswürdigen Anwendungen eingerichtet werden kann. In diesem Modus müssen Administratoren Testbenutzerkennwörter für den Monitorknoten verwalten.
  

