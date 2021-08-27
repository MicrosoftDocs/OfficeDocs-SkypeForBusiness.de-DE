---
title: Neuigkeiten in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2017
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: e62c9229-b738-45ef-b637-0b58ca8225a4
description: 'Zusammenfassung: Lesen Sie dieses Thema, um mehr über neue Features in Skype for Business Server 2015 zu erfahren. Ausführliche Informationen zur neuen Clientumgebung finden Sie unter "Lync ist jetzt Skype for Business" – erfahren Sie, was neu ist.'
ms.openlocfilehash: df0a16855ab7430e87847a392d263f35c6ec2993
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58617621"
---
# <a name="whats-new-in-skype-for-business-server-2015"></a>Neuigkeiten in Skype for Business Server 2015

**Zusammenfassung:** Lesen Sie dieses Thema, um mehr über neue Features in Skype for Business Server 2015 zu erfahren. Ausführliche Informationen zur neuen Clientumgebung finden Sie unter Lync ist jetzt Skype for Business – sehen Sie sich die [Neuerungen an.](https://go.microsoft.com/fwlink/p/?LinkId=529022)
  
Lync ist jetzt Skype for Business, einer Plattform für Kommunikation und Zusammenarbeit, die eine von Skype inspirierte Oberfläche mit der Sicherheit, Compliance und Kontrolle von Lync auf Unternehmensniveau vereint. Skype for Business bietet Funktionen wie Anwesenheitsinformationen, Chatnachrichten, Sprach- und Videoanrufe sowie Onlinebesprechungen. Skype for Business bietet eine neue Clientumgebung, eine neue Serverversion und Updates für den Dienst in Microsoft 365 oder Office 365. Wenn Benutzer in Ihrer Organisation bereits mit Skype vertraut sind, werden sie die Leistungsfähigkeit und Einfachheit von Skype for Business schätzen, in denen es einfach ist, Kollegen zu finden und sich mit ihnen zu verbinden. Wenn Benutzer in Ihrer Organisation von Lync zu Skype for Business kommen, erkennen sie alle Features, die sie bereits verwenden, aber in einer neuen Oberfläche mit vereinfachten Steuerelementen und neuen Ergänzungen. Zusätzlich zur neuen Clientumgebung bietet Skype for Business Server 2015 mehrere neue Features, um die Verwaltbarkeit von lokalen Servern und Hybridlösungen zu verbessern.
  
Zu den neuen Features in Skype for Business Server 2015 gehören Verbesserungen an:
  
- Verwendung durch den Benutzer  
- Sprach- und Videounterstützung
- Mobile Unterstützung
- Verwaltung von lokalen Servern
- Bereitstellung und Verwaltung von Hybridlösungen
- Unterstützung der mehrstufigen Authentifizierung
    
## <a name="user-experience"></a>Verwendung durch den Benutzer

Der Skype for Business-Client sieht der Consumerversion von Skype sehr ähnlich und verwendet die gleichen Schaltflächen und Symbole. Weniger Menüs und eine flachere Aufgabenhierarchie erleichtern benutzern das schnelle Auffinden der benötigten Steuerelemente und Befehle. 
  
Skype for Business umfasst die oben beschriebene neue Benutzeroberfläche und die zuvor veröffentlichte Lync 2013-Benutzeroberfläche. Die Einbeziehung beider Erfahrungen ermöglicht Es Unternehmen, Änderungen für ihre Benutzer zu verwalten, indem sie den Prozess und das Timing des neuen Clientrollouts steuern. Die Standardbenutzeroberfläche hängt davon ab, welche Version des Servers Sie verwenden. Administratoren wählen die bevorzugte Umgebung mithilfe des Cmdlets **"Set-CsClientPolicy"** mit dem Parameter "EnableSkypeUI" aus. Weitere Informationen zum Konfigurieren der Clientumgebung finden Sie unter [Configure the client experience with Skype for Business](deploy/deploy-clients/configure-the-client-experience.md) and Desktop client feature comparison for [Skype for Business.](plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)
  
> [!NOTE]
> Die Lync 2013-Clientumgebung ist keine Option für Skype for Business 2016-Clientversionen. Bevor Sie versuchen, Ihre Clientumgebung für die Verwendung des Lync 2013-Clients zu konfigurieren, überprüfen Sie die Clientversion, um sicherzustellen, dass sie nicht mit der Nummer 16 beginnt. Beispiel: 16.x.x.x. 
  
## <a name="voice-and-video-improvements"></a>Sprach- und Videoverbesserungen

Skype for Business Server 2015 umfasst Verbesserungen an der Sprach- und Videofunktion, einschließlich der Erfassung und Analyse von Anrufdaten, und verbesserte Interoperabilität mit Videotelekonferenzsystemen von Drittanbietern.
  
### <a name="call-data-collection-and-analysis"></a>Anrufdatensammlung und -analyse

Mit der Funktion "Meinen Anruf bewerten" können Skype for Business Server 2015-Administratoren Anrufdaten sammeln. Dieses Feature ist nur für lokale Bereitstellungen verfügbar. Benutzer werden aufgefordert, nach Abschluss eines Anrufs eine Umfrage zu nehmen. Weitere Informationen finden Sie unter ["Meinen Anruf in Skype for Business Server 2015 bewerten".](manage/health-and-monitoring/rate-my-call.md)
  
### <a name="improved-interoperability-with-third-party-video-teleconferencing-systems"></a>Verbesserte Interoperabilität mit Videotelekonferenzsystemen von Drittanbietern

Der Video-Interoperabilität-Server (VIS) fungiert als Vermittler zwischen Skype for Business Server- und Cisco-Videotelekonferenzsystemen (VTC). Bei der Teilnahme an einer Besprechung können Benutzer jetzt ein Cisco-VTC-System auswählen. Der Video-Interoperabilität-Server (VIS) wird als eigenständige Serverrolle für lokale Bereitstellungen implementiert. Weitere Informationen finden Sie unter [Plan for Video Interop Server in Skype for Business Server 2015.](plan-your-deployment/video-interop-server.md)
  
### <a name="call-via-work"></a>Anruf über den Arbeitsplatz

Mit der Funktion "Anruf über Arbeit" können Unternehmensbenutzer Sprachanrufe über den Skype for Business-Client tätigen. Wenn ein Benutzer einen Sprachanruf abgibt, wird er von Skype for Business an die Nebenstellenanlage oder das FESTNETZ-Telefon des Absenders weitergeleitet. Sobald der Absender das Telefon entgegennimmt, wird der Anruf an die Zielnummer weitergeleitet. Der Anrufempfänger antworte, und der Anruf wird mit Skype for Business als Systemsteuerung eingerichtet. Der Absender kann seine Anwesenheits- und Anrufsteuerelemente über Skype for Business verwalten. Serveradministratoren aktivieren und konfigurieren "Anruf über Arbeit" für das Unternehmen. Weitere Informationen finden Sie unter [Plan for Call Via Work in Skype for Business Server 2015](plan-your-deployment/enterprise-voice-solution/call-via-work.md). 
  
## <a name="mobile-device-support-improvements"></a>Verbesserungen bei der Unterstützung mobiler Geräte

Zu den Verbesserungen bei der Unterstützung mobiler Geräte gehören Features zur Verbesserung der mobilen Benutzererfahrung für Enterprise Edition Benutzer, z. B. Zugriff auf Aufgezeichnete Unterhaltungen und Protokolldaten, erweiterte mobile Besprechungsumgebungen und Unterstützung für einmaliges Anmelden über Office hinweg. Darüber hinaus gibt es Verbesserungen an der Android-Unterstützung, Leistungsverbesserungen und Features, um die Integration über das Common App Framework zu vereinfachen. 
  
> [!NOTE]
> Lync 2013-UCWA-Server müssen auf Skype for Business Server 2015 aktualisiert werden, um mobile Clients zu unterstützen. 
  
### <a name="server-side-conversation-history-is-now-available-on-mobile-devices"></a>Serverseitiger Unterhaltungsverlauf ist jetzt auf mobilen Geräten verfügbar.

Um den mobilen Zugriff auf aufgezeichnete Unterhaltungen, verpasste Chatnachrichten und Anrufprotokolldaten zu ermöglichen, wird die Archivierung dieser Informationen jetzt über den Server für alle mobilen Clients verarbeitet. Die Funktion für die automatische Annahme für Chatnachrichten verbessert die Zuverlässigkeit, indem Timeoutmeldungen für Server verhindert werden, wenn ein mobiler Benutzer nicht sofort auf eine Chatnachricht antwortet. Um die Vorteile der serverbasierten Exchange/Outlook Ordnerintegration nutzen zu können, sind Exchange Server 2013 oder neuere und aktualisierte mobile Clients erforderlich. 
  
### <a name="enhanced-meeting-experiences"></a>Verbesserte Besprechungserfahrungen

Die auf dem Desktop verfügbaren Besprechungsfunktionen sind jetzt auch für mobile Benutzer verfügbar. Zu den neuen Funktionen gehören:
  
- Asynchrone Navigation von freigegebenen PowerPoint Inhalten
- Die Fähigkeit des Referenten, die Kontrolle über freigegebene PowerPoint Inhalte zu übernehmen
- Lobbyverwaltung für Referenten, die es ihnen ermöglicht, Teilnehmer zuzulassen oder zu verweigern
    
### <a name="skype-for-business-on-android-improvements"></a>Verbesserungen bei Skype for Business unter Android

Skype for Business unter Android bietet jetzt Features, die in Skype for Business unter iOS und Skype for Business unter Windows verfügbar sind:
  
- Fortsetzen oder erneutes Beitreten zu Unterhaltungen
- Aktivieren von Zertifikaten und passiver Authentifizierung
- Einladen anderer Personen zu einer Unterhaltung
- Einfaches Starten von Gruppenunterhaltungen
- An einer Besprechung teilnehmen, ohne ein Skype for Business Benutzer zu sein
- Aktivieren der Smartphone-Benutzeroberfläche auf Android-Tablets
- Verwalten von Besprechungen durch Hinzufügen oder Entfernen von Teilnehmern
    
> [!NOTE]
> Für diese Features ist Android OS Version 4.0 oder höher erforderlich. 
  
## <a name="management-of-on-premises-servers"></a>Verwaltung von lokalen Servern

Skype for Business Server 2015 bietet verschiedene neue Features zur Verbesserung der Verwaltbarkeit lokaler Server, einschließlich direktes Upgrade, intelligentes Setup, verbesserte Patching- und Upgradeprozesse, verbesserte Kaltstartfunktion für Front-End-Pools, SQL Server AlwaysOn-Unterstützung sowie zentralisierte Protokollierung und Problembehandlung.
  
### <a name="in-place-upgrade-for-on-premises-servers"></a>Direktes Upgrade für lokale Server

Sie können jetzt Lync Server 2013-Systeme auf Skype for Business Server 2015 aktualisieren, indem Sie das neue direkte Upgradefeature verwenden, das vorhandene Lync Server 2013-Hardware- und Serverinvestitionen verwendet, wodurch die Gesamtkosten für die Bereitstellung Skype for Business Server 2015 reduziert werden.
  
Es gibt zwei Szenarien für direkte Upgrades: die Move User-Methode, die keine Ausfallzeiten erfordert, und die Offline-Methode, die Ausfallzeiten erfordert. Weitere Informationen dazu, welches Upgradeverfahren für Ihr Unternehmen geeignet ist, finden Sie unter ["Planen des Upgrades auf Skype for Business Server 2015".](plan-your-deployment/upgrade.md) 
  
> [!NOTE]
> Die direkte Option ist nicht verfügbar, wenn Sie ein Upgrade von Lync Server 2010 durchführen. Weitere Informationen zum Upgrade von Lync Server 2010 finden Sie unter [Plan to upgrade to Skype for Business Server 2015](plan-your-deployment/upgrade.md). 
  
### <a name="smart-setup"></a>Intelligentes Setup

Das Smart Setup-Feature, das Updates automatisch erkennt und herunterlädt, ist jetzt Teil des Setupprogramms. Während des Installationsvorgangs wird der Benutzer gefragt, ob der Installationsvorgang nach Updates suchen sollte. Weitere Informationen finden Sie unter [Installieren Skype for Business Server 2015.](deploy/install/install.md)
  
### <a name="improved-front-end-server-patching-and-upgrade-process"></a>Verbesserter Patching- und Upgradeprozess für Front-End-Server

Skype for Business Server führt zwei neue Cmdlets ein, die das Upgrade oder Patchen von Front-End-Servern wesentlich einfacher machen als in früheren Versionen von Lync Server.
  
Wenn Sie einen Patch oder eine andere Wartung auf einen Front-End-Server anwenden müssen, geben Sie einfach **Invoke-CsComputerFailOver** ein, und geben Sie den Namen dieses Servers an. Skype for Business Server wird die Workload dieses Servers vorübergehend auf die anderen Server im Pool verschoben. Anschließend können Sie die Wartung durchführen und dann das Cmdlet **Invoke-CsComputerFailback** verwenden, um den Server wieder in Betrieb zu nehmen. Wenn Sie jeden Server in einem Pool patchen müssen, führen Sie einfach dieses Verfahren für jeden Server nacheinander aus. Mit diesen neuen Cmdlets können Sie Server viel schneller patchen als in früheren Versionen und mit mehr Zuverlässigkeit und einem einfacheren Workflow.
  
### <a name="improved-front-end-pool-cold-start-capability"></a>Verbesserte Kaltstartfunktion des Front-End-Pools

Skype for Business Server führt ein neues Cmdlet ein, das den Kaltstart eines gesamten Front-End-Pools vereinfacht und verbessert. Wenn Sie das neue **Start-CsPool-Cmdlet** verwenden, überprüft es die Voraussetzungen für alle Front-End-Server im Pool und versucht dann, jeden Server zu starten. Wenn Probleme auftreten, werden diese diagnostiziert und Sie mit Details und Problemumgehungen benachrichtigt. In einigen Fällen können Sie den Pool auch dann starten, wenn einige der einzelnen Server nicht gestartet werden können.
  
### <a name="sql-server-alwayson-support-for-on-premises-servers"></a>SQL Server AlwaysOn-Unterstützung für lokale Server

Skype for Business Server 2015 bietet Unterstützung für SQL Server AlwaysOn-Verfügbarkeitsgruppen und SQL Server AlwaysOn-Failoverclusterinstanzen. Zusätzlich zu diesen Features unterstützt Skype for Business Server weiterhin Datenbankspiegelung und SQL Server Clustering, wie in früheren Versionen von Lync Server.
  
SQL Server AlwaysOn-Verfügbarkeitsgruppen ist eine Lösung für hohe Verfügbarkeit und Notfallwiederherstellung in SQL Server 2012 und SQL Server 2014, die eine Alternative zur Datenbankspiegelung bietet. Eine Verfügbarkeitsgruppe unterstützt eine Failoverumgebung für eine diskrete Gruppe von Datenbanken (auch als Verfügbarkeitsdatenbanken bezeichnet), die gemeinsam einen Failover ausführen. Eine Verfügbarkeitsgruppe unterstützt eine Reihe primärer Datenbanken mit Lese-/Schreibzugriff und eine bis vier Sätze entsprechender sekundärer Datenbanken. Optional können sekundäre Datenbanken für schreibgeschützten Zugriff und für einige Sicherungsvorgänge zur Verfügung gestellt werden.
  
SQL Server Failoverclusterinstanzen nutzen Windows Serverfailoverclustering (WSFC)-Funktionalität, um lokale hohe Verfügbarkeit durch Redundanz auf Serverinstanzebene bereitzustellen – einer Failoverclusterinstanz (FCI). Eine FCI ist eine einzelne Instanz von SQL Server, die über Windows Serverfailoverclustering (WSFC)-Knoten und möglicherweise über mehrere Subnetze hinweg installiert wird.
  
Weitere Informationen finden Sie unter [Plan for high availability and disaster recovery in Skype for Business Server 2015.](plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
### <a name="centralized-logging-and-troubleshooting-improvements-for-on-premises-servers"></a>Zentrale Protokollierung und Verbesserungen bei der Problembehandlung für lokale Server

Der zentralisierte Protokollierungsdienst ist die bevorzugte Protokollierungsumgebung für Skype for Business Server 2015. Es gibt keine neuen Features in dieser Version, aber Zuverlässigkeit und Leistung wurden sowohl für den Dienst als auch für den zentralisierten Protokollierungsdienst-Agent (ClsAgent.exe) verbessert – die ausführbare Datei des Diensts, die mit dem Controller kommuniziert und Befehle empfängt, die vom Administrator ausgegeben werden.
  
Skype for Business Server 2015 verwendet Windows PowerShell Cmdlets, um die Protokollierungsdienst-Agents zu verwalten, die Ablaufverfolgung zu initiieren und Berichte zu generieren. (Lync Server 2013 verwendet ClsController.exe, um diese Aufgaben auszuführen.)
  
Der zentralisierte Protokollierungsdienst kann auf jedem Skype for Business Server 2015 ausgeführt werden. Die integrierten Szenarien (vordefinierte Ablaufverfolgungen) bleiben identisch, ebenso wie die Möglichkeit, benutzerdefinierte Szenarien zu erstellen. Es gibt ein spezielles Szenario namens AlwaysOn, das immer ausgeführt wird und es Administratoren ermöglicht, häufige Probleme nahezu in Echtzeit zu finden.
  
Das Snooper-Debugtool wurde ebenfalls aktualisiert, um das Debuggen von Mobilitätsprotokollen zu ermöglichen, und funktioniert mit Geräten, die mit Lync 2013 oder Skype for Business Server 2015 verbunden sind. Das Tool steht als Webdownload von [Debugtools](https://go.microsoft.com/fwlink/?LinkId=285257)zur Verfügung.
  
## <a name="hybrid-deployment-and-management"></a>Hybridbereitstellung und -verwaltung

Skype for Business Server 2015 bietet Verwaltungs- und Verwaltungsfunktionen für die Hybridbereitstellung, indem die folgenden Features eingeführt werden:
  
- Empfehlungen für Hybridbereitstellungen basierend auf dem Status der lokalen Ressourcen des Kunden, wie vom OnRamp für Office 365 automatisierten Hilfstool bestimmt.
- Verbesserungen an der Skype for Business Server Systemsteuerung und dem Skype for Business Server Admin Center, sodass Administratoren diese Tools zum Verwalten einer Hybridbereitstellung verwenden können.
- Verbesserungen in der Systemsteuerung, mit denen sich Administratoren bei einem Microsoft 365 oder Office 365 Mandanten anmelden und eine Hybridbereitstellung mit Skype for Business Online mithilfe des Assistenten für die Hybridkonfiguration einrichten können.
- Systemsteuerungsunterstützung für das Verschieben von lokalen Benutzern zu Skype for Business Online oder das Verschieben Skype for Business Onlinebenutzer zurück zu lokalen Benutzern.
- Systemsteuerungsfeatures zum Identifizieren und Filtern von lokalen Benutzerobjekten, die von lokalen Benutzern in Skype for Business Online verschoben wurden (d. h. Hybridbenutzer).
- Admin Center-Features zum Identifizieren und Filtern von Cloudbenutzern, die ursprünglich in Skype for Business Online erstellt wurden, von Hybridbenutzern, die von der lokalen Umgebung zu Online migriert wurden.
- Die Möglichkeit, Hybridbenutzer mithilfe der Systemsteuerung für lokal verwaltbare Eigenschaften und admin Center für Eigenschaften zu verwalten, die über Skype for Business Online verwaltet werden können.
- Die Verwendung der Kennwortsynchronisierung mit DirSync ermöglicht die Synchronisierung lokaler Active Directory-Kennwörter mit dem Onlinemandanten. Wenn dieses Feature konfiguriert ist, entlässt es die Notwendigkeit, AD FS für die Verbundauthentifizierung bereitzustellen, aber AD FS ist weiterhin für die mehrstufige Authentifizierung erforderlich. 
- Fortgesetzte Unterstützung für die Koexistenz zwischen Skype for Business Online und Exchange lokal.
    
> [!NOTE]
> Es gibt keine Änderung von Lync Online 2013 und Exchange lokalen Koexistenz- und Supportumgebung. 
  
## <a name="multi-factor-authentication"></a>Mehrstufige Authentifizierung

Die mehrstufige Authentifizierung ist eine Authentifizierungsmethode, die die Verwendung mehrerer Überprüfungsmethoden erfordert und eine kritische zweite Sicherheitsebene für Benutzeranmeldungen und Transaktionen hinzufügt. Beispiel: Anfordern eines Benutzernamens und Kennworts sowie eines Zertifikats. Skype for Business Server 2015 baut weiterhin auf den Multi-Factor Authentication-Features auf, die in den kumulativen Updates für Lync Server 2013 verfügbar sind. Die wichtigsten Änderungen bei der mehrstufigen Authentifizierung sind:
  
- Verwendung der Active Directory-Authentifizierungsbibliothek Office 2013 SP1 für die Integration in Exchange und SharePoint
- Unterstützung für das Feature für die mehrstufige Authentifizierung im Skype for Business-Web-App-Client
    
Mit Skype for Business mehrstufigen Authentifizierung können jetzt unterschiedliche Authentifizierungsoptionen basierend auf der Geografie bereitgestellt werden. Beispielsweise können Kunden ihre Umgebung so konfigurieren, dass die interne Authentifizierung auf der integrierten Windows-Authentifizierung basiert, während Mitarbeiter, die sich von außerhalb der Organisation authentifizieren, die mehrstufige Authentifizierung verwenden. 
  
Die Skype for Business Multi-Factor Authentication-Erfahrung ist nahtlos, unabhängig von:
  
- Geografischer Standort – Ob sich der Benutzer innerhalb oder außerhalb der Organisation anmeldet 
- Client-/Gerätetyp: Gibt an, auf welchem Skype for Business Client verwendet wird und auf welchem Gerät der Client ausgeführt wird (PC, Mobil, iPad usw.).
- Kontospeicherort – Ob der Benutzer in einem lokalen Active Directory oder in Azure Active Directory Online gehostet wird.
