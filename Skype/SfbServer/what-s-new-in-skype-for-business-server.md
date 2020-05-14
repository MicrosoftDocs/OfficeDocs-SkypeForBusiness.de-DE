---
title: Neuerungen in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2017
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e62c9229-b738-45ef-b637-0b58ca8225a4
description: 'Zusammenfassung: in diesem Thema erfahren Sie mehr über die neuen Features in Skype for Business Server 2015. Ausführliche Informationen zu den neuen Clientfunktionen finden Sie unter lync ist jetzt Skype for Business--siehe What es New.'
ms.openlocfilehash: b8d0d8334977b5367419991d1bcabba303718c89
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221085"
---
# <a name="whats-new-in-skype-for-business-server-2015"></a>Neuerungen in Skype for Business Server 2015

**Zusammenfassung:** In diesem Thema erfahren Sie mehr über die neuen Features in Skype for Business Server 2015. Ausführliche Informationen zu den neuen Clientfunktionen finden Sie unter [lync ist jetzt Skype for Business--siehe What es New](https://go.microsoft.com/fwlink/p/?LinkId=529022).
  
Lync ist jetzt Skype for Business, eine Kommunikations-und Zusammenarbeitsplattform, die eine von Skype inspirierte Erfahrung mit der unternehmensweiten Sicherheit, Compliance und Steuerung von lync vereint. Skype for Business bietet Funktionen wie Anwesenheits-, Chat-, sprach-und Videoanrufe sowie Onlinebesprechungen. Skype for Business bietet eine neue Clientumgebung, eine neue Server Version und Updates für den Dienst in Microsoft 365 oder Office 365. Wenn Benutzer in Ihrer Organisation bereits mit Skype vertraut sind, werden Sie die Leistungsfähigkeit und Einfachheit von Skype for Business schätzen, in der Sie einfach zu finden sind und sich mit Kollegen verbinden können. Wenn Benutzer in Ihrer Organisation aus lync Skype for Business kommen, erkennen Sie alle Features, die Sie bereits verwenden, aber in einer neuen neuen Benutzeroberfläche mit vereinfachten Steuerelementen und neuen Ergänzungen. Zusätzlich zur neuen Clientumgebung bietet Skype for Business Server 2015 mehrere neue Features, um die Verwaltbarkeit von lokalen Servern und Hybridlösungen zu verbessern.
  
Zu den neuen Features in Skype for Business Server 2015 gehören Verbesserungen für:
  
- Benutzererfahrung  
- Sprach-und Videounterstützung
- Mobile Unterstützung
- Verwaltung von lokalen Servern
- Bereitstellung und Verwaltung von Hybridlösungen
- Unterstützung für mehrstufige Authentifizierung
    
## <a name="user-experience"></a>Benutzererfahrung

Der Skype for Business-Client sieht sehr ähnlich wie die consumerversion von Skype aus und verwendet die gleichen Schaltflächen und Symbole. Weniger Menüs und eine flache Aufgabenhierarchie erleichtern Benutzern das schnelle Auffinden der benötigten Steuerelemente und Befehle. 
  
Skype for Business enthält die oben beschriebene neue Benutzeroberfläche und die zuvor freigegebene lync 2013 Benutzeroberfläche. Die Einbeziehung beider Erfahrungen ermöglicht es Unternehmen, Änderungen für Ihre Benutzer zu verwalten, indem der Prozess und die Zeitplanung des neuen Client-Rollouts gesteuert werden. Die standardmäßige Benutzererfahrung hängt davon ab, welche Version des Servers Sie verwenden. Administratoren wählen die bevorzugte Benutzeroberfläche mithilfe des Cmdlets " **CsClientPolicy** " mit dem Parameter "EnableSkypeUI" aus. Weitere Informationen zum Konfigurieren der Clientumgebung finden Sie unter [Konfigurieren der Clientumgebung mit Skype for Business](deploy/deploy-clients/configure-the-client-experience.md) -und [Desktop Client-Funktionsvergleich für Skype for Business](plan-your-deployment/clients-and-devices/desktop-feature-comparison.md).
  
> [!NOTE]
> Die lync 2013 Clienterfahrung ist keine Option für Skype for Business 2016-Clientversionen. Bevor Sie versuchen, ihre Clientumgebung für die Verwendung des lync 2013 Clients zu konfigurieren, überprüfen Sie die Client Version, um sicherzustellen, dass Sie nicht mit der Nummer 16 beginnt; Beispiel: 16. x.x.x. 
  
## <a name="voice-and-video-improvements"></a>Sprach-und Videoverbesserungen

Skype for Business Server 2015 umfasst Verbesserungen an der Sprach-und Videofunktionalität, einschließlich der Anruf Datenerfassung und-Analyse sowie einer verbesserten Interoperabilität mit Video Teleconferencing-Systemen von Drittanbietern.
  
### <a name="call-data-collection-and-analysis"></a>Sammlung und Analyse von Anrufdaten

Mit der Funktion "meine Anrufe bewerten" können Skype for Business Server 2015 Administratoren Anrufdaten erfassen. Dieses Feature ist nur für lokale Bereitstellungen verfügbar. Benutzer werden aufgefordert, eine Umfrage nach Abschluss eines Anrufs durchzuführen. Weitere Informationen finden Sie unter [meinen Anruf in Skype for Business Server 2015 bewerten](manage/health-and-monitoring/rate-my-call.md).
  
### <a name="improved-interoperability-with-third-party-video-teleconferencing-systems"></a>Verbesserte Interoperabilität mit Video Teleconferencing-Systemen von Drittanbietern

Der Video-Interop-Server (VIS) fungiert als Vermittler zwischen Skype for Business Server-und Cisco-Video Teleconferencing-Systemen (VTC). Bei der Teilnahme an einer Besprechung können Benutzer nun ein Cisco-VTC-System auswählen. Der Video-Interop-Server (VIS) wird als eigenständige Server Rolle für lokale Bereitstellungen implementiert. Weitere Informationen finden Sie unter [Plan for Video Interop Server in Skype for Business Server 2015](plan-your-deployment/video-interop-server.md).
  
### <a name="call-via-work"></a>Anruf über den Arbeitsplatz

Das Feature "Anruf über Arbeit" ermöglicht es Unternehmensbenutzern, Sprachanrufe vom Skype for Business-Client aus zu tätigen. Wenn ein Benutzer einen VoIP-Anruf tätigt, wird er von Skype for Business an die PBX-Anlage oder das PSTN-Telefon des Auftraggebers weitergeleitet. Sobald der Absender das Telefon beantwortet, wird der Anruf an die Zielrufnummer weitergeleitet. Der Anrufempfänger antwortet, und der Anruf wird mit Skype for Business als Systemsteuerung fungiert eingerichtet. Der Absender kann seine Anwesenheits-und Anrufsteuerungen in Skype for Business verwalten. Server Administratoren aktivieren und konfigurieren die Funktion "Anruf über Arbeit" für das Unternehmen. Weitere Informationen finden Sie unter [Planen von Anrufen über Arbeit in Skype for Business Server 2015](plan-your-deployment/enterprise-voice-solution/call-via-work.md). 
  
## <a name="mobile-device-support-improvements"></a>Verbesserungen bei der mobilen Geräteunterstützung

Zu den Verbesserungen bei der Unterstützung mobiler Geräte gehören Features zur Verbesserung der mobilen Benutzerfreundlichkeit von Enterprise Edition-Benutzern wie Zugriff auf Unterhaltungs Historie und Protokolldaten, erweiterte mobile Besprechungs Erlebnisse und Unterstützung für einmaliges Anmelden in Office. Darüber hinaus gibt es Verbesserungen an Android-Unterstützung, Leistungsverbesserungen und Features zur Vereinfachung der Integration über das allgemeine App-Framework. 
  
> [!NOTE]
> Lync 2013 UCWA-Server müssen auf Skype for Business Server 2015 aktualisiert werden, um Mobile Clients zu unterstützen. 
  
### <a name="server-side-conversation-history-is-now-available-on-mobile-devices"></a>Server seitige Unterhaltungs Historie ist jetzt auf mobilen Geräten verfügbar

Um mobilen Zugriff auf Unterhaltungs Historie, verpasste Chat-und Anrufprotokoll Daten zu ermöglichen, wird die Archivierung dieser Informationen nun über den Server für alle mobilen Clients verarbeitet. Die automatische Annahme Funktion für Sofortnachrichten verbessert die Zuverlässigkeit, indem Servertimeout Meldungen verhindert werden, wenn ein mobiler Benutzer nicht sofort auf einen Chat antwortet. Um die serverbasierte Exchange/Outlook-Ordner Integration nutzen zu können, sind Exchange Server 2013 oder neuere und aktualisierte Mobile Clients erforderlich. 
  
### <a name="enhanced-meeting-experiences"></a>Erweiterte Besprechungs Erlebnisse

Die auf dem Desktop verfügbaren Besprechungsfunktionen stehen nun auch mobilen Benutzern zur Verfügung. Zu den neuen Funktionen gehören:
  
- Asynchrone Navigation von freigegebenen PowerPoint-Inhalten
- Fähigkeit des Referenten, die Steuerung von freigegebenen PowerPoint-Inhalten zu übernehmen
- Lobby Management für Referenten, sodass Teilnehmer zugelassen oder verweigert werden können
    
### <a name="skype-for-business-on-android-improvements"></a>Skype for Business auf Android-Verbesserungen

Skype for Business auf Android bietet nun ähnliche Funktionen wie in Skype for Business unter IOS und Skype for Business unter Windows:
  
- Fortsetzen oder erneutes beitreten von Unterhaltungen
- Aktivieren des Zertifikats und der passiven Authentifizierung
- Einladen anderer Personen in eine Unterhaltung
- Einfaches starten von Gruppenunterhaltungen
- An einer Besprechung teilnehmen, ohne Skype for Business Benutzer zu sein
- Aktivieren der Smartphone-Benutzeroberfläche auf Android-Tablets
- Verwalten von Besprechungen durch Hinzufügen oder Entfernen von Teilnehmern
    
> [!NOTE]
> Für diese Features ist Android OS Version 4,0 oder höher erforderlich. 
  
## <a name="management-of-on-premises-servers"></a>Verwaltung von lokalen Servern

Skype for Business Server 2015 bietet mehrere neue Features zur Verbesserung der Verwaltbarkeit von lokalen Servern, einschließlich direktes Upgrade, intelligentes Setup, verbesserte Patches und Upgrade-Prozesse, verbesserte Front-End-Pool kaltstartfunktion, SQL Server AlwaysOn-Unterstützung sowie zentralisierte Protokollierung und Problembehandlung.
  
### <a name="in-place-upgrade-for-on-premises-servers"></a>Direktes Upgrade für lokale Server

Sie können nun lync Server 2013 Systeme auf Skype for Business Server 2015 mithilfe des neuen in-Place-Upgrades-Features aktualisieren, das vorhandene lync Server 2013 Hardware-und Server Investitionen verwendet, wodurch die Gesamtkosten für die Bereitstellung von Skype for Business Server 2015 gesenkt werden.
  
Für ein direktes Upgrade stehen zwei Szenarien zur Verfügung: die Methode "Benutzer verlegen", die keine Ausfallzeit erfordert, und die Offline-Methode, bei der Ausfallzeiten erforderlich sind. Weitere Informationen dazu, welches Aktualisierungsverfahren für Ihr Unternehmen geeignet ist, finden Sie unter [Plan to Upgrade to Skype for Business Server 2015](plan-your-deployment/upgrade.md). 
  
> [!NOTE]
> Die in-Place-Option ist nicht verfügbar, wenn Sie ein Upgrade von lync Server 2010 durchführen. Weitere Informationen zum Upgrade von lync Server 2010 finden Sie unter [Plan to Upgrade to Skype for Business Server 2015](plan-your-deployment/upgrade.md). 
  
### <a name="smart-setup"></a>Intelligentes Setup

Das Feature für die intelligente Installation, mit dem Updates automatisch erkannt und heruntergeladen werden, ist nun Bestandteil des Setupprogramms. Während des Installationsvorgangs wird der Benutzer gefragt, ob der Installationsprozess nach Updates suchen soll. Weitere Informationen finden Sie unter [install Skype for Business Server 2015](deploy/install/install.md).
  
### <a name="improved-front-end-server-patching-and-upgrade-process"></a>Verbesserte Front-End-Server Patching und Upgrade-Prozess

In Skype for Business Server werden zwei neue Cmdlets vorgestellt, mit denen das Upgraden oder Patchen von Front-End-Servern wesentlich einfacher ist als in früheren Versionen von lync Server.
  
Wenn Sie einen Patch anwenden oder eine andere Wartung für eine Front-End-Server durchführen müssen, geben Sie einfach **Invoke-CsComputerFailOver** ein, und geben Sie den Namen des Servers an. Skype for Business Server verschiebt die Arbeitsauslastung des Servers temporär auf die anderen Server im Pool. Anschließend können Sie die Wartung durchführen und dann das Cmdlet **Invoke-CsComputerFailback** verwenden, um den Server wieder in Betrieb zu nehmen. Wenn Sie jeden Server in einem Pool patchen müssen, führen Sie einfach dieses Verfahren für jeden Server einzeln aus. Mit diesen neuen Cmdlets können Sie Server viel schneller als in früheren Versionen Patchen und mit größerer Zuverlässigkeit und einfacheren Workflows arbeiten.
  
### <a name="improved-front-end-pool-cold-start-capability"></a>Verbesserte Front-End-Pool kaltstartfunktion

In Skype for Business Server wird ein neues Cmdlet eingeführt, das den Prozess des Kaltstarts einer ganzen Front-End-Pool vereinfacht und verbessert. Wenn Sie das neue Cmdlet **Start-CsPool** verwenden, werden die Voraussetzungen für alle Front-End-Server im Pool überprüft, und anschließend wird versucht, jeden Server zu starten. Wenn Probleme auftreten, werden diese diagnostiziert und Warnungen mit Details und Problemumgehungen angezeigt. In einigen Fällen können Sie den Pool auch dann starten, wenn einige der einzelnen Server nicht gestartet werden können.
  
### <a name="sql-server-alwayson-support-for-on-premises-servers"></a>SQL Server AlwaysOn-Unterstützung für lokale Server

Skype for Business Server 2015 unterstützt sowohl SQL Server AlwaysOn-Verfügbarkeitsgruppen als auch SQL Server AlwaysOn-Failover-Cluster Instanzen. Zusätzlich zu diesen Features unterstützt Skype for Business Server wie in früheren Versionen von lync Server weiterhin die Unterstützung für Datenbankspiegelung und SQL Server Clustering.
  
SQL Server AlwaysOn-Verfügbarkeitsgruppen ist eine Lösung für hohe Verfügbarkeit und Notfallwiederherstellung in SQL Server 2012 und SQL Server 2014, die eine Alternative zur Datenbankspiegelung bietet. Eine verfügbarkeitsgruppe unterstützt eine Failover-Umgebung für einen diskreten Daten Banksatz (als verfügbarkeitsdatenbanken bezeichnet), bei dem ein Failover gemeinsam ausgeführt wird. Eine verfügbarkeitsgruppe unterstützt eine Reihe von primären Datenbanken mit Lese-/Schreibzugriff sowie 1 bis 4 Sätze mit entsprechenden sekundären Datenbanken. Optional können sekundäre Datenbanken für den schreibgeschützten Zugriff und für einige Sicherungsvorgänge zur Verfügung gestellt werden.
  
SQL Server Failover-Cluster Instanzen nutzen die WSFC-Funktionen (Windows Server Failover Clustering), um eine lokale hohe Verfügbarkeit durch Redundanz auf Server Ebene – eine Failoverclusterinstanz (Failover Cluster Instance) – bereitzustellen. Eine FCI ist eine einzelne Instanz von SQL Server, die über Windows Server-Failoverclustering-Knoten (WSFC) und möglicherweise über mehrere Subnetze hinweg installiert wird.
  
Weitere Informationen finden Sie unter [Plan for High Availability and Disaster Recovery in Skype for Business Server 2015](plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
### <a name="centralized-logging-and-troubleshooting-improvements-for-on-premises-servers"></a>Zentralisierte Protokollierung und Verbesserungen bei der Problembehandlung für lokale Server

Der zentralisierte Protokollierungsdienst ist die bevorzugte Protokollierungs Umgebung für Skype for Business Server 2015. In dieser Version gibt es keine neuen Features, aber Zuverlässigkeit und Leistung wurden für den Dienst und den zentralen Protokollierungsdienst-Agent (ClsAgent. exe) verbessert – die ausführbare Dienstdatei, die mit dem Controller kommuniziert und Befehle empfängt, die vom Administrator ausgegeben werden.
  
Skype for Business Server 2015 verwendet Windows PowerShell-Cmdlets zum Verwalten der Protokollierungsdienst-Agents, zum Initiieren der Ablaufverfolgung und zum Generieren von Berichten. (Lync Server 2013 zum Ausführen dieser Aufgaben ClsController. exe verwendet.)
  
Der zentralisierte Protokollierungsdienst kann auf jedem beliebigen Skype for Business Server 2015 ausgeführt werden. Die integrierten Szenarien (vordefinierte Ablaufverfolgungen) bleiben unverändert, ebenso wie die Möglichkeit, benutzerdefinierte Szenarien zu erstellen. Es gibt ein spezielles Szenario namens "AlwaysOn", das immer aktiv ist und es Administratoren ermöglicht, häufige Probleme in nahezu Echtzeit zu ermitteln.
  
Das Snooper-Debugging-Tool wurde ebenfalls aktualisiert, um das Debuggen von Mobilitäts Protokollen zu ermöglichen, und kann mit Geräten verwendet werden, die eine Verbindung mit lync 2013 oder Skype for Business Server 2015 herstellen. Das Tool steht als Webdownload aus Debugging- [Tools](https://go.microsoft.com/fwlink/?LinkId=285257)zur Verfügung.
  
## <a name="hybrid-deployment-and-management"></a>Hybrid Bereitstellung und-Verwaltung

Skype for Business Server 2015 ermöglicht die Bereitstellung von Verwaltungs-und Verwaltungsfunktionen für die hybridbereitstellung durch Einführung der folgenden Features:
  
- Empfehlungen für hybridbereitstellungen basierend auf dem Status der lokalen Ressourcen des Kunden, wie durch das Tool "onramp für Office 365 automatische Unterstützung" bestimmt.
- Verbesserungen an der Skype for Business Server-Systemsteuerung und dem Skype for Business Server Admin Center, sodass Administratoren diese Tools zum Verwalten einer hybridbereitstellung verwenden können.
- Verbesserungen der Systemsteuerung, mit denen sich Administratoren bei einem Microsoft 365-oder Office 365-Mandanten anmelden und Hybrid mit Skype for Business Online mithilfe des Assistenten für die Hybrid Konfiguration einrichten können.
- Unterstützung der Systemsteuerung zum Verschieben von lokalen Benutzern zum Skype for Business Online oder Verschieben von Skype for Business Online Benutzern zurück ins lokal.
- Funktionen der Systemsteuerung zum Identifizieren und Filtern von lokalen Benutzerobjekten, die in Skype for Business Online (Hybrid Benutzer) von lokalen Benutzern verschoben wurden.
- Admin Center-Funktionen zum Identifizieren und Filtern von Cloud-Benutzern, die ursprünglich in Skype for Business Online von Hybrid Benutzern erstellt wurden, die von lokal zu Online migriert wurden.
- Die Möglichkeit zum Verwalten von Hybrid Benutzern mithilfe der Systemsteuerung für Eigenschaften, die über das lokale Verwaltungskonsole verwaltet werden können, und Admin Center für Eigenschaften, die über Skype for Business Online verwaltbar sind.
- Verwenden der Kennwortsynchronisierung mit Dirsync, der Möglichkeit, lokale Active Directory Kennwörter mit dem Online Mandanten zu synchronisieren. Wenn diese Funktion konfiguriert ist, ist es nicht mehr erforderlich, AD FS für die Verbundauthentifizierung bereitzustellen, aber AD FS ist weiterhin für die mehrstufige Authentifizierung erforderlich. 
- Kontinuierliche Unterstützung der Koexistenz zwischen Skype for Business Online und Exchange lokal.
    
> [!NOTE]
> Es gibt keine Änderung gegenüber der lync Online 2013 und Exchange lokale Koexistenz und Supporterfahrung. 
  
## <a name="multi-factor-authentication"></a>Mehrstufige Authentifizierung

Bei der mehrstufigen Authentifizierung handelt es sich um eine Authentifizierungsmethode, die die Verwendung von mehr als einer Überprüfungsmethode erfordert und den Benutzeranmeldungen und-Transaktionen eine kritische zweite Sicherheitsebene hinzufügt. Beispielsweise benötigen Sie einen Benutzernamen und ein Kennwort sowie ein Zertifikat. Skype for Business Server 2015 baut weiterhin auf den mehrstufigen Authentifizierungsfunktionen auf, die in den lync Server 2013 kumulativen Updates verfügbar sind. Die wesentlichen Änderungen bei der mehrstufigen Authentifizierung lauten wie folgt:
  
- Verwenden der Office 2013 SP1 Active Directory-Authentifizierungsbibliothek für die Integration in Exchange und SharePoint
- Unterstützung für die mehrstufige Authentifizierungsfunktion im Skype for Business-Webanwendungs-Client
    
Mit Skype for Business mehrstufigen Authentifizierung können nun unterschiedliche Authentifizierungsoptionen basierend auf der Geografie bereitgestellt werden. Kunden können beispielsweise Ihre Umgebung so konfigurieren, dass die interne Authentifizierung von der integrierten Windows-Authentifizierung abhängt, während bei Mitarbeitern, die sich außerhalb der Organisation authentifizieren, die mehrstufige Authentifizierung verwendet wird. 
  
Die Skype for Business Erfahrung mit mehrstufiger Authentifizierung ist nahtlos unabhängig von folgenden Faktoren:
  
- Geografischer Standort-ob der Benutzer sich innerhalb oder außerhalb der Organisation anmeldet 
- Client/Gerätetyp – welcher Skype for Business Client verwendet wird und auf welchem Gerät der Client betrieben wird (PC, Mobiltelefon, iPad usw.)
- Konto Speicherort – ob der Benutzer in einer lokalen Active Directory oder in Azure Active Directory online gehostet wird.
