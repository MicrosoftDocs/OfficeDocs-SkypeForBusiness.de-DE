---
title: Installieren und Konfigurieren von Watcher-Knoten
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Zusammenfassung: Installieren und Konfigurieren von Watcher-Knoten für Skype for Business Server synthetischen Transaktionen.'
ms.openlocfilehash: 8efe291f72312b7634ae644d0e910cf58951b7a6
ms.sourcegitcommit: b72bf3827e7145b9b6a95c84e88a7879c6e8c337
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/12/2020
ms.locfileid: "46640945"
---
# <a name="install-and-configure-watcher-nodes"></a>Installieren und Konfigurieren von Watcher-Knoten
 
**Zusammenfassung:** Installieren und konfigurieren Sie Watcher-Knoten für Skype for Business Server synthetischen Transaktionen.
  
Watcher-Knoten sind Computer, die regelmäßig Skype for Business Server synthetischen Transaktionen ausgeführt werden. Synthetische Transaktionen sind Windows PowerShell Cmdlets, mit denen sichergestellt wird, dass wichtige Benutzerszenarien wie die Möglichkeit zum Anmelden oder zum Austauschen von Chatnachrichten wie erwartet funktionieren. Für Skype for Business Server 2015 kann System Center Operations Manager die synthetischen Transaktionen ausführen, die in der folgenden Tabelle gezeigt werden, die drei synthetische Transaktionstypen umfasst:
  
- **Standardwert** Synthetische Transaktionen, die ein Watcher-Knoten standardmäßig ausführt. Wenn Sie einen neuen Watcher-Knoten erstellen, können Sie angeben, welche synthetischen Transaktionen dieser Knoten ausführen soll. (Dies ist der Zweck des Parameters "Tests", der vom Cmdlet "New-CsWatcherNodeConfiguration" verwendet wird.) Wenn Sie den Parameter Tests nicht verwenden, wenn der Watcher-Knoten erstellt wird, werden alle synthetischen Standardtransaktionen automatisch ausgeführt, und es werden keine synthetischen, nicht standardmäßigen Transaktionen ausgeführt. Dies bedeutet beispielsweise, dass der Watcher-Knoten so konfiguriert wird, dass der Test-CsAddressBookService-Test ausgeführt wird, aber nicht für die Ausführung des Test-csexumconnectivity "-Tests konfiguriert ist.
    
- **Nicht Standard** Testet, ob Watcher-Knoten standardmäßig nicht ausgeführt werden. (Ausführliche Informationen finden Sie in der Beschreibung des Standardtyps.) Allerdings kann der Watcher-Knoten aktiviert werden, um alle nicht standardmäßigen synthetischen Transaktionen auszuführen. Sie können dies tun, wenn Sie den Watcher-Knoten (mithilfe des New-CsWatcherNodeConfiguration-Cmdlets) oder nach der Erstellung des Watcher-Knotens erstellen. Beachten Sie, dass für viele der nicht standardmäßigen synthetischen Transaktionen zusätzliche Einrichtungsschritte erforderlich sind. Ausführliche Informationen zu diesen Schritten finden Sie unter [spezielle Einrichtungsanweisungen für synthetische Transaktionen](test-users-and-settings.md#special_synthetictrans).
    
- **Erweitert** Ein spezieller Typ einer nicht standardmäßigen synthetischen Transaktion. Im Unterschied zu anderen synthetischen Transaktionen können sie bei jedem Durchgang mehrere Male ausgeführt werden. Dies ist hilfreich, wenn Sie das Verhalten überprüfen möchten, beispielsweise mehrere PSTN-VoIP-Routen (Public Switched Telephone Network) für einen Pool. Sie können dies einfach durch Hinzufügen mehrerer Instanzen eines erweiterten Tests zu einem Watcher-Knoten konfigurieren.
    
Ausführliche Informationen zum Prozess zum Hinzufügen weiterer synthetischer Transaktionen zu einem Watcher-Knoten finden Sie unter [Configure a Watcher Node to Run Synthetic Transactions](watcher-nodes.md#enable_synthetic_trans). Sie können auch Skype for Business Server-Verwaltungsshell verwenden, um synthetische Transaktionen aus einem Watcher-Knoten zu entfernen.
  
Zu den für Watcher-Knoten verfügbaren synthetischen Transaktionen gehören:
  
|**Cmdlet-Name (Test-Name)**|**Beschreibung**|
|:-----|:-----|
|Test-CsAddressBookService (ABS)  <br/> |Bestätigt, dass Benutzer in der Lage sind, Benutzer nachzuschlagen, die nicht in Ihrer Kontaktliste aufgeführt sind.  <br/> |
|Test-CsAddressBookWebQuery (ABWQ)  <br/> |Bestätigt, dass Benutzer in der Lage sind, Benutzer nachzuschlagen, die nicht in Ihrer Kontaktliste über HTTP stehen.  <br/> |
|Test-CsAVConference (AvConference)  <br/> |Überprüft, ob Benutzer in der Lage sind, eine Audio-/Videokonferenz zu erstellen und daran teilzunehmen.  <br/> |
|Test-CsGroupIM (Chat Konferenzen)  <br/> |Überprüft, ob Benutzer in der Lage sind, in Konferenzen Sofortnachrichten zu senden und an Sofortnachrichtengesprächen mit drei oder mehr Personen teilzunehmen.  <br/> |
|Test-CsIM (P2P im)  <br/> |Überprüft, ob Benutzer in der Lage sind, Peer-zu-Peer-Sofortnachrichten zu senden.  <br/> |
|Test-CsP2PAV (P2PAV)  <br/> |Überprüft, ob Benutzer in der Lage sind, Peer-zu-Peer-Audioanrufe zu tätigen (nur Signal).  <br/> |
|Test-CsPresence (Anwesenheit)  <br/> |Bestätigt, dass Benutzer in der Lage sind, die Anwesenheit anderer Benutzer anzuzeigen.  <br/> |
|Test-CsRegistration (Registrierung)  <br/> |Bestätigt, dass sich Benutzer bei Skype for Business anmelden können.  <br/> |
|Test-CsPstnPeerToPeerCall (PSTN)  <br/> |Überprüft, ob Benutzer in der Lage sind, Anrufe von Personen außerhalb des Unternehmens (PSTN-Nummern) entgegenzunehmen oder diese anzurufen.  <br/> |
|Test-csasconference "(Konferenz)  <br/> |Bestätigt, dass Benutzer in der Lage sind, eine Anwendungsfreigabe Konferenz zu erstellen und daran teilzunehmen.  <br/> |
|Test-csavedgeconnectivity "(AVEdgeConnectivity)  <br/> |Bestätigt, dass die Audio-Video-Edgeserver Verbindungen für Peer-zu-Peer-Anrufe und Telefonkonferenzen annehmen können.  <br/> |
|Test-csdataconference "(dataconference)  <br/> |Bestätigt, dass Benutzer an einer Daten Zusammenarbeits Konferenz teilnehmen können (eine Onlinebesprechung, die Aktivitäten wie Whiteboards und Umfragen umfasst).  <br/> |
|Test-CsDialinConferencing (DialinConferencing)  <br/> |Bestätigt, dass Benutzer in der Lage sind, Telefonnummern für die Teilnahme an Konferenzen zu wählen.  <br/> |
|Test-CsDialinConferencing (DialinConferencing)  <br/> |Bestätigt, dass Benutzer in der Lage sind, Telefonnummern für die Teilnahme an Konferenzen zu wählen.  <br/> |
|Test-csexumconnectivity "(ExumConnectivity)  <br/> |Bestätigt, dass ein Benutzer eine Verbindung mit Exchange Unified Messaging (um) herstellen kann.  <br/> |
|Test-CsGroupIM-TestJoinLauncher (JoinLauncher)  <br/> |Bestätigt, dass Benutzer in der Lage sind, geplante Besprechungen (über einen Webadressen Link) zu erstellen und daran teilzunehmen.  <br/> |
|Test-CsMCXP2PIM (MCXP2PIM)  <br/> |Überprüft, ob Benutzer mit Mobilgeräten in der Lage sind, sich zu registrieren und Sofortnachrichten zu senden.  <br/> |
|Test-CsP2PVideoInteropServerSipTrunkAV (P2PVideoInteropServerSipTrunkAV)  <br/> |Bestätigt, dass der Video-Interop-Server installiert ist und eingehende Verbindungen über einen Video-SIP-Trunk verarbeiten kann.  <br/> **Hinweis:** Die MCX-Unterstützung für ältere Mobile Clients steht in Skype for Business Server 2019 nicht mehr zur Verfügung. |
|Test-cspersistentchatmessage "(PersistentChatMessage)  <br/> |Bestätigt, dass Benutzer Nachrichten mithilfe des Diensts für beständigen Chat austauschen können.  <br/> |
|Test-CsUcwaConference (UcwaConference)  <br/> |Bestätigt, dass Benutzer über das Internet an Konferenzen teilnehmen können.  <br/> |
|Test-CsUnifiedContactStore (UnifiedContactStore)  <br/> |Überprüft, ob die Kontakte eines Benutzers über den einheitlichen Kontaktspeicher zugänglich sind. Der einheitliche Kontaktspeicher bietet Benutzern eine Möglichkeit, eine einzelne Gruppe von Kontakten zu verwalten, auf die mithilfe von Skype for Business Server 2015, dem Outlook-Messaging-und Zusammenarbeitsclient und/oder Outlook Web Access zugegriffen werden kann.  <br/> |
|Test-csxmppim "(XmppIM)  <br/> |Bestätigt, dass eine Sofortnachricht über das XMPP-Gateway (Extensible Messaging and Presence Protocol) gesendet werden kann.  <br/> XMPP-Gateways und-Proxys stehen in Skype for Business Server 2015 zur Verfügung, werden in Skype for Business Server 2019 jedoch nicht mehr unterstützt.  |

Sie müssen keine Watcher-Knoten installieren, um System Center Operations Manager verwenden zu können. Wenn Sie diese Knoten nicht installieren, können Sie immer noch Echtzeitwarnungen von Skype for Business Server 2015 Komponenten erhalten, wenn ein Problem auftritt. (Die Komponente und das Benutzer Management Pack verwenden keine Watcher-Knoten.) Watcher-Knoten sind jedoch erforderlich, wenn Sie End-to-End-Szenarien mithilfe des Active Monitoring Management Packs überwachen möchten.
  
> [!NOTE]
> Administratoren können synthetische Transaktionen auch manuell ausführen, ohne Operations Manager zu verwenden oder zu installieren. Je nach Größe Ihrer Skype for Business Server-Bereitstellung können synthetische Transaktionen eine große Menge an Computerspeicher und Prozessorzeit verwenden. Aus diesem Grund wird empfohlen, einen dedizierten Computer als Watcher-Knoten zu verwenden. Beispielsweise sollten Sie keine Skype for Business Server Front-End-Server konfigurieren, die als Watcher-Knoten fungieren soll. Watcher-Knoten sollten die gleichen grundlegenden Hardwareanforderungen erfüllen wie alle anderen Computer in Ihrer Skype for Business Server Topologie. 
  
> [!NOTE]
> Ein Legacy lync Server 2013 Watcher-Knoten kann nicht auf demselben Computer wie ein Skype for Business Server 2015 Watcher-Knoten zusammengefasst werden, da die Hauptsystem Dateien für lync Server 2013 und Skype for Business Server 2015 nicht auf demselben Computer installiert werden können. Skype for Business Server 2015 Watcher-Knoten können jedoch gleichzeitig Skype for Business Server 2015 und lync Server 2013 überwachen. Synthetische Standardtransaktionen werden für beide Produktversionen unterstützt. 
  
Lync Server 2013 Watcher-Knoten können innerhalb oder außerhalb eines Unternehmens bereitgestellt werden, um Folgendes zu überprüfen:
  
- Konnektivität zu Pools für Benutzer innerhalb des Unternehmens
    
- Konnektivität über Umkreisnetzwerke für Remotebenutzer, die außerhalb des Unternehmens arbeiten.
    
- Konnektivität zu Branch Office Appliances
    
- Konnektivität mit lync Server 2013 innerhalb des Unternehmens und über Umkreisnetzwerke.
    
Zur Vereinfachung der Verwaltung stehen unterschiedliche Authentifizierungsoptionen für innerhalb und außerhalb des Unternehmens zur Verfügung. Ausführliche Informationen finden Sie unter [Konfigurieren eines Watcher-Knotens zum Ausführen synthetischer Transaktionen](watcher-nodes.md#enable_synthetic_trans).
  
Wenn Sie einen Computer als Watcher-Knoten konfigurieren möchten, müssen Sie zunächst die folgenden Voraussetzungen erfüllen: 
  
- Installieren Sie System Center Operations Manager, und importieren Sie die Skype for Business Server 2015 Management Packs. Außerdem müssen Sie zunächst sicherstellen, dass der Watcher-Knoten Computer alle Voraussetzungen für die Installation von Skype for Business Server 2015 erfüllt.
    
- Installieren Sie die folgenden Elemente auf dem Watcher-Knoten Computer:
    
  - Die Vollversion von .NET Framework 4.5
    
  - Windows Identity Foundation
    
  - Windows PowerShell 3.0
    
Nachdem die Voraussetzungen erfüllt sind, können Sie den Watcher-Knoten konfigurieren, indem Sie die folgenden Schritte ausführen:
  
1. Installieren Sie die Skype for Business Server 2015 Kerndateien auf dem Watcher-Knoten Computer.
    
2. Installieren Sie den System Center Operations Manager-Agent auf dem Monitor Knoten Computer.
    
3. Führen Sie die ausführbare Datei Watchernode.msi aus.
    
4. Verwenden Sie das Cmdlet **New-CsWatcherNodeConfiguration** , um Testbenutzerkonten zu konfigurieren, die vom Watcher-Knoten verwendet werden sollen.
    
## <a name="install-the-skype-for-business-server-2015-core-files-and-the-rtclocal-database"></a>Installieren der Skype for Business Server 2015-Hauptdateien und der RTCLocal-Datenbank

Um die Skype for Business Server 2015 Kerndateien auf einem Computer zu installieren, führen Sie das folgende Verfahren aus. Die RTCLocal-Datenbank wird automatisch installiert, wenn Sie die Kerndateien installieren. Beachten Sie, dass Sie SQL Server nicht auf den Watcher-Knoten installieren müssen. SQL Server Express werden automatisch installiert.
  
So installieren Sie die Skype for Business Server 2015 Kerndateien und die RTCLocal-Datenbank:
  
1. Klicken Sie auf dem Watcher-Knoten-Computer auf Start, Alle Programme und Zubehör, klicken Sie mit der rechten Maustaste auf Eingabeaufforderung, und klicken Sie dann auf Als Administrator ausführen.
    
2. Geben Sie im Konsolenfenster den folgenden Befehl ein, und drücken Sie die EINGABETASTE. Achten Sie darauf, dass Sie den geeigneten Pfad zu Ihren Skype for Business Server-Setupdateien eingeben: D:\Setup.exe/BootstrapLocalMgmtTo Vergewissern Sie sich, dass die Kern Skype for Business Server Komponenten erfolgreich installiert wurden, klicken Sie auf **Start**, **Alle Programme**, **Skype for Business Server 2015**und dann auf **Skype for Business Server Verwaltungsshell**. Geben Sie in der Skype for Business Server Verwaltungsshell den folgenden Windows PowerShell Befehl ein, und drücken Sie die EINGABETASTE:
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

> [!NOTE]
> Wenn Sie diesen Befehl zum ersten Mal ausführen, werden keine Daten zurückgegeben, da Sie noch keine Monitor Knoten Computer konfiguriert haben. Wenn der Befehl ausgeführt wird, ohne einen Fehler zurückzugeben, können Sie davon ausgehen, dass das Skype for Business Server Setup erfolgreich abgeschlossen wurde. 
  
Wenn sich der Monitor Knoten Computer in Ihrem Umkreisnetzwerk befindet, können Sie den folgenden Befehl ausführen, um die Installation von Skype for Business Server 2015 zu überprüfen:
  
Abhängig von der Anzahl der für die Verwendung in Ihrer Organisation konfigurierten PIN-Richtlinien erhält Get-CsPinPolicyYou Informationen wie diese.
  
Identity: Global
  
Beschreibung
  
"Minpasswordlength": 5
  
"PINHistoryCount": 0
  
AllowCommonPatterns: false
  
"PINLifetime": 0
  
MaximumLogonAttempts :
  
Wenn Sie Informationen zu Ihren PIN-Richtlinien sehen, wurden die Kernkomponenten erfolgreich installiert.
  
## <a name="install-the-operation-manager-agent-files-on-a-watcher-node"></a>Installieren der Operations Manager-Agent-Dateien auf einem Watcher-Knoten

Ähnlich wie Skype for Business Server-Setup für Warnungen bei der Komponente "Reporting Component" erfordert ein Skype for Business Server 2015 Watcher-Knoten die Installation von System Center Operations Manager-Agentendateien. Dadurch können synthetische Transaktionen ausgeführt und Warnungen an den System Center Operations Manager-Stamm Verwaltungs Server gemeldet werden.
  
Um die Agentdateien zu installieren, befolgen Sie die unter [Konfigurieren der Skype for Business Server Computer, die überwacht](configure-computers-to-monitor.md)werden, aufgeführten Verfahren.
  
## <a name="configure-a-watcher-node-to-run-synthetic-transactions"></a>Konfigurieren eines Watcher-Knotens zum Ausführen synthetischer Transaktionen
<a name="enable_synthetic_trans"> </a>

Nachdem die System Center Operations Manager-Agent-Dateien installiert wurden, müssen Sie den Watcher-Knoten selbst konfigurieren. Die erforderlichen Schritte sind unterschiedlich, je nachdem, ob sich der Monitor Knoten Computer in Ihrem Umkreisnetzwerk oder außerhalb Ihres Umkreisnetzwerks befindet. 
  
Beim Konfigurieren eines Watcher-Knotens müssen Sie außerdem die Authentifizierungsmethode auswählen, die von diesem Knoten verwendet werden soll. Skype for Business Server 2015 können Sie eine von zwei Authentifizierungsmethoden auswählen: vertrauenswürdige Server-oder Anmelde Informations Authentifizierung. In der folgenden Tabelle sind die Unterschiede zwischen diesen beiden Methoden dargestellt:
  
||**Beschreibung**|**Unterstützte Speicherorte**|
|:-----|:-----|:-----|
|TrustedServer  <br/> |Ein Zertifikat wird verwendet, um die Identität eines internen Servers anzunehmen und die Authentifizierungsaufforderungen zu umgehen.  <br/> Nützlich für Administratoren, die es vorziehen, ein einzelnes Zertifikat anstelle vieler Benutzerkennwörter auf jedem Watcher-Knoten zu verwalten.  <br/> |Innerhalb des Unternehmens.  <br/> Bei dieser Methode muss sich der Watcher-Knoten in derselben Domäne befinden wie die Pools, die überwacht werden. Wenn sich der Watcher-Knoten und die Pools in unterschiedlichen Domänen befinden, verwenden Sie stattdessen die Anmelde Informations Authentifizierung.  <br/> |
|Aushandeln  <br/> |Benutzernamen und Kennwörter werden auf sichere Weise in der Windows-Anmeldeinformationsverwaltung auf jedem Watcher-Knoten gespeichert.  <br/> Dieser Modus erfordert mehr Kennwortverwaltung, ist aber die einzige Option für Watcher-Knoten außerhalb des Unternehmens. Diese Watcher-Knoten können nicht als Endpunkt, der bezüglich der Authentifizierung vertrauenswürdig ist, betrachtet werden.  <br/> |Außerhalb des Unternehmens.  <br/> Innerhalb des Unternehmens.  <br/> |
   
## <a name="configure-a-watcher-node-to-use-trusted-server-authentication"></a>Konfigurieren eines Watcher-Knotens für die Verwendung der vertrauenswürdigen Server Authentifizierung
<a name="enable_synthetic_trans"> </a>

Wenn sich der Monitor Knoten Computer innerhalb des Umkreisnetzwerks befindet, kann die Verwendung der vertrauenswürdigen Server Authentifizierung die Verwaltungsaufgaben erheblich reduzieren, indem ein einzelnes Zertifikat verwaltet wird, anstatt zahlreiche Kennwörter für Benutzerkonten zu verwenden.
  
Zum Konfigurieren der vertrauenswürdigen Server Authentifizierung müssen Sie zunächst einen vertrauenswürdigen Anwendungspool erstellen, um den Watcher-Knoten Computer zu hosten. Nachdem Sie den vertrauenswürdigen Anwendungspool erstellt haben, müssen Sie synthetische Transaktionen auf dem Watcher-Knoten konfigurieren, um als vertrauenswürdige Anwendungen auszuführen.
  
> [!NOTE]
> Bei einer vertrauenswürdigen Anwendung handelt es sich um eine Anwendung, die als Teil der Skype for Business Server 2015 als vertrauenswürdiger Status ausgeführt wird, aber kein integrierter Bestandteil des Produkts ist. Vertrauensstatus bedeutet, dass nicht bei jeder Ausführung der Anwendung eine Authentifizierung angefordert wird.
  
Öffnen Sie zum Erstellen eines vertrauenswürdigen Anwendungspools die Skype for Business Server-Verwaltungsshell, und führen Sie einen Befehl wie den folgenden aus:
  
```PowerShell
New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond
```

> [!NOTE]
> Ausführliche Informationen zu den Parametern im obigen Befehl geben Sie in der Eingabeaufforderung der Skype for Business Server Verwaltungsshell Folgendes ein: 
  
```PowerShell
Get-Help New-CsTrustedApplicationPool -Full | more
```

Nachdem Sie den vertrauenswürdigen Anwendungspool erstellt haben, können Sie den Watcher-Knoten Computer so konfigurieren, dass synthetische Transaktionen als vertrauenswürdige Anwendung mithilfe des **New-CsTrustedApplication-** Cmdlets und eines Befehls wie dem folgenden ausgeführt werden:
  
```PowerShell
New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061
```

Wenn dieser Befehl abgeschlossen ist und die vertrauenswürdige Anwendung erstellt wird, müssen Sie das Cmdlet **enable-CsTopology** ausführen, um sicherzustellen, dass die Änderungen wirksam werden:
  
```PowerShell
Enable-CsTopology
```

Das Computerkonto des Watcher-Knotens erfordert die Möglichkeit, CMS für einige synthetische Transaktionen abzufragen. Um diese Möglichkeit zu ermöglichen, fügen Sie das Computerkonto des Watcher-Knotens zur Sicherheitsgruppe RTCUniversalReadOnlyAdmins hinzu. Nachdem die AD-Replikation eingetreten ist, starten Sie den Computer neu.
  
Um zu überprüfen, ob die neue vertrauenswürdige Anwendung erstellt wurde, geben Sie an der Eingabeaufforderung der Skype for Business Server Verwaltungsshell Folgendes ein:
  
```PowerShell
Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"
```

## <a name="configure-a-default-certificate-on-the-watcher-node"></a>Konfigurieren eines Standardzertifikats auf dem Watcher-Knoten
<a name="enable_synthetic_trans"> </a>

Jeder Watcher-Knoten, der die TrustedServer-Authentifizierung verwendet, muss über ein Standardzertifikat verfügen, das mit dem Skype for Business Server-Bereitstellungs-Assistenten zugewiesen ist. 
  
So weisen Sie ein Standardzertifikat zu:
  
1. Klicken Sie im Startmenü auf alle Programme, klicken Sie auf Skype for Business Server 2015, und klicken Sie dann auf Skype for Business Server Bereitstellungs-Assistent. 
    
2. Klicken Sie im Skype for Business Server-Bereitstellungs-Assistenten auf Skype for Business Server System installieren oder aktualisieren, und klicken Sie dann unter der Überschrift Anforderung, installieren oder Zuweisen eines Zertifikats auf ausführen. 
    
> [!NOTE]
> Wenn die Schaltfläche Ausführen deaktiviert ist, müssen Sie möglicherweise zunächst unter Lokalen Konfigurationsspeicher installieren auf Ausführen klicken. 
  
Führen Sie eine der folgenden Aktionen aus:
  
- Wenn Sie bereits über ein Zertifikat verfügen, das als Standardzertifikat verwendet werden kann, klicken Sie im Zertifikat-Assistenten auf Standard, und klicken Sie dann auf zuweisen. Befolgen Sie die Anweisungen des Zertifikat-Assistenten, um das Zertifikat zuzuweisen.
    
- Wenn Sie ein Zertifikat anfordern müssen, um das Standardzertifikat zu verwenden, klicken Sie auf anfordern, und befolgen Sie dann die Schritte im Zertifikat Anforderungs-Assistenten, um das Zertifikat anzufordern. Wenn Sie die Standardwerte für das Webserver-Zertifikat verwenden, erhalten Sie ein Zertifikat, das Sie als Standardzertifikat zuweisen können.
    
## <a name="install-and-configure-a-watcher-node"></a>Installieren und Konfigurieren eines Watcher-Knotens
<a name="enable_synthetic_trans"> </a>

Nachdem Sie den Watcher-Knoten Computer neu gestartet und ein Zertifikat konfiguriert haben, müssen Sie die Datei Watchernode.msi ausführen. (Sie müssen Watchernode.msi auf jedem Computer ausführen, auf dem sowohl die Operations Manager-Agent-Dateien als auch die Skype for Business Server 2015-Kernkomponenten installiert sind.) 
  
So installieren und konfigurieren Sie einen Watcher-Knoten:
  
1. Öffnen Sie die Skype for Business Server Verwaltungsshell, indem Sie auf Start klicken, auf alle Programme klicken, auf Skype for Business Server 2015 und dann auf Skype for Business Server Verwaltungsshell klicken. 
    
2. Geben Sie in der Verwaltungsshell den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE (stellen Sie sicher, dass Sie den tatsächlichen Pfad zu Ihrer Kopie von Watchernode.msi):
    
```PowerShell
C:\Tools\Watchernode.msi Authentication=TrustedServer
```

> [!NOTE]
> Sie können Watchernode.msi n auch über ein Befehlsfenster ausführen. Klicken Sie zum Öffnen eines Befehlsfensters auf Start, klicken Sie mit der rechten Maustaste auf Eingabeaufforderung, und klicken Sie dann auf Als Administrator ausführen. Wenn das Befehlsfenster geöffnet wird, geben Sie den gleichen Befehl wie in Schritt 2 oben ein. 
  
> [!IMPORTANT]
> Im obigen Befehl wird bei der Authentifizierung für das Name/Wert-Paar die Groß-/Kleinschreibung beachtet. Es muss genau wie dargestellt eingegeben werden. Beispielsweise schlägt dieser Befehl fehl, da nicht die richtige Buchstaben Hülle verwendet wird: 
  
```PowerShell
C:\Tools\Watchernode.msi authentication=trustedserver
```

Der TrustedServer-Modus kann nur für Computer verwendet werden, die sich im Umkreisnetzwerk befinden. Wenn ein Watcher-Knoten im TrustedServer-Modus ausgeführt wird, müssen Administratoren keine Testbenutzer Kennwörter auf dem Computer aufrecht erhalten.
  
## <a name="configure-a-watcher-node-to-use-negotiate"></a>Konfigurieren eines Watcher-Knotens für die Verwendung von Negotiate
<a name="enable_synthetic_trans"> </a>

Wenn sich der Monitor Knoten Computer außerhalb des Umkreisnetzwerks befindet, müssen Sie ein geringfügig anderes Verfahren ausführen, um den Watcher-Knoten so zu konfigurieren, dass synthetische Transaktionen ausgeführt werden: insbesondere sollten Sie keinen vertrauenswürdigen Anwendungspool oder eine vertrauenswürdige Anwendung erstellen. Das bedeutet, dass Sie die nächsten beiden Aufgaben ausführen müssen.
  
### <a name="update-membership-in-the-rtc-local-read-only-administrators-group"></a>Aktualisieren der Mitgliedschaft in der Gruppe "RTC Local Read-Only Administrators"

Wenn sich der Watcher-Knoten außerhalb des Umkreisnetzwerks befindet, müssen Sie das Netzwerkdienstkonto der Gruppe "RTC Local Read-Only Administrators" auf dem Watcher-Knoten Computer hinzufügen, indem Sie das folgende Verfahren auf dem Watcher-Knoten ausführen:
  
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
  
1. Öffnen Sie die Microsoft Skype for Business Server 2015 Management-Shell. Klicken Sie im Startmenü auf alle Programme, klicken Sie auf Microsoft Skype for Business Server 2015, und klicken Sie dann auf Skype for Business Server Verwaltungskonsole. 
    
2. Geben Sie in Skype for Business Server Verwaltungsshell den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE (stellen Sie sicher, dass Sie den tatsächlichen Pfad zu Ihrer Kopie von Watchernode.msi angeben):
    
   ```PowerShell
   c:\Tools\Watchernode.msi Authentication=Negotiate
   ```

> [!NOTE]
> Wie bereits erwähnt, können Watchernode.msi auch über ein Befehlsfenster ausgeführt werden. Klicken Sie zum Öffnen eines Befehlsfensters auf **Start**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und klicken Sie dann auf **Als Administrator ausführen**. Wenn das Befehlsfenster geöffnet wird, geben Sie den gleichen Befehl wie in Schritt 2 oben ein. 
  
Der Aushandlungsmodus wird verwendet, wenn der Monitorknoten nicht als Pool mit vertrauenswürdigen Anwendungen eingerichtet werden kann. In diesem Modus müssen Administratoren Testbenutzerkennwörter für den Monitorknoten verwalten.
  

