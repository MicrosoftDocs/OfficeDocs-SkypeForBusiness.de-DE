---
title: Neues in Skype for Business Server 2015
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
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e62c9229-b738-45ef-b637-0b58ca8225a4
description: 'Zusammenfassung: Lesen Sie dieses Thema, um mehr über neue Funktionen in Skype for Business Server 2015 zu erfahren. Ausführliche Informationen zur neuen Clienterfahrung finden Sie unter "Lync ist jetzt Skype for Business" – erfahren Sie, was neu ist.'
ms.openlocfilehash: 09774f722020ef750ae16ad01a29873d43d25e76
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827585"
---
# <a name="whats-new-in-skype-for-business-server-2015"></a>Neues in Skype for Business Server 2015

**Zusammenfassung:** In diesem Thema erfahren Sie mehr über neue Funktionen in Skype for Business Server 2015. Ausführliche Informationen zur neuen Clienterfahrung finden Sie unter ["Lync ist jetzt Skype for Business" – erfahren Sie, was neu ist.](https://go.microsoft.com/fwlink/p/?LinkId=529022)
  
Lync ist jetzt Skype for Business, eine Plattform für Kommunikation und Zusammenarbeit, die eine von Skype inspirierte Erfahrung mit der Sicherheit, Compliance und Kontrolle von Lync auf Unternehmensqualität vereint. Skype for Business bietet Funktionen wie Anwesenheit, Chat, Sprach- und Videoanrufe und Onlinebesprechungen. Skype for Business bietet eine neue Clienterfahrung, eine neue Serverversion und Updates für den Dienst in Microsoft 365 oder Office 365. Wenn Benutzer in Ihrer Organisation bereits mit Skype vertraut sind, werden sie die Leistung und Einfachheit von Skype for Business schätzen, wo es einfach ist, Kollegen zu finden und sich mit ihnen zu verbinden. Wenn Benutzer in Ihrer Organisation von Lync aus zu Skype for Business kommen, erkennen sie alle bereits verwendeten Features, aber in einer neuen neuen Schnittstelle mit vereinfachten Steuerelementen und neuen Ergänzungen. Zusätzlich zur neuen Clienterfahrung bietet Skype for Business Server 2015 mehrere neue Features, um die Verwaltbarkeit von lokalen Servern und Hybridlösungen zu verbessern.
  
Zu den neuen Features in Skype for Business Server 2015 gehören Verbesserungen an:
  
- Verwendung durch den Benutzer  
- Sprach- und Videounterstützung
- Mobile Unterstützung
- Verwaltung von lokalen Servern
- Bereitstellung und Verwaltung von Hybridlösungen
- Unterstützung der mehrstufigen Authentifizierung
    
## <a name="user-experience"></a>Verwendung durch den Benutzer

Der Skype for Business-Client sieht der Verbraucherversion von Skype sehr ähnlich aus und verwendet dieselben Schaltflächen und Symbole. Mit weniger Menüs und einer flacheren Aufgabenhierarchie können Benutzer schnell die benötigten Steuerelemente und Befehle finden. 
  
Skype for Business umfasst die oben beschriebene neue Benutzeroberfläche und die zuvor veröffentlichte Lync 2013-Benutzeroberfläche. Durch die Einbeziehung beider Erfahrungen können Unternehmen Änderungen für ihre Benutzer verwalten, indem sie den Prozess und den Zeitpunkt des neuen Clientrollups steuern. Die Standardbenutzererfahrung hängt davon ab, welche Version des Servers Sie verwenden. Administratoren wählen die bevorzugte Benutzererfahrung mithilfe des **Cmdlets "Set-CsClientPolicy"** mit dem Parameter "EnableSkypeUI". Weitere Informationen zum Konfigurieren der Clienterfahrung finden Sie unter "Konfigurieren der Clienterfahrung mit [Skype for Business-](deploy/deploy-clients/configure-the-client-experience.md) und Desktopclientfeaturevergleich [für Skype for Business".](plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)
  
> [!NOTE]
> Die Lync 2013-Clienterfahrung ist keine Option für Skype for Business 2016-Clientversionen. Bevor Sie versuchen, Ihre Clientumgebung für die Verwendung des Lync 2013-Clients zu konfigurieren, überprüfen Sie die Clientversion, um sicherzustellen, dass sie nicht mit der Nummer 16 beginnt. Beispiel: 16.x.x.x. 
  
## <a name="voice-and-video-improvements"></a>Sprach- und Videoverbesserungen

Skype for Business Server 2015 bietet Verbesserungen an der Sprach- und Videofunktionalität, einschließlich der Erfassung und Analyse von Anrufdaten, sowie verbesserte Interoperabilität mit Videotelekonferenzsystemen von Drittanbietern.
  
### <a name="call-data-collection-and-analysis"></a>Sammlung und Analyse von Anrufdaten

Mit der Funktion "Meinen Anruf bewerten" können Skype for Business Server 2015-Administratoren Anrufdaten sammeln. Dieses Feature ist nur für lokale Bereitstellungen verfügbar. Benutzer werden aufgefordert, nach Abschluss eines Anrufs eine Umfrage zu machen. Weitere Informationen finden Sie unter ["Meinen Anruf bewerten" in Skype for Business Server 2015](manage/health-and-monitoring/rate-my-call.md).
  
### <a name="improved-interoperability-with-third-party-video-teleconferencing-systems"></a>Verbesserte Interoperabilität mit Videotelekonferenzsystemen von Drittanbietern

Der Video Interop Server (VIS) fungiert als Vermittler zwischen Skype for Business Server und Cisco Video Teleconferencing (VTC)-Systemen. Bei der Teilnahme an einer Besprechung können Benutzer jetzt ein Cisco-VTC-System auswählen. Der Video Interop Server (VIS) wird als eigenständige Serverrolle für lokale Bereitstellungen implementiert. Weitere Informationen finden Sie unter [Plan for Video Interop Server in Skype for Business Server 2015](plan-your-deployment/video-interop-server.md).
  
### <a name="call-via-work"></a>Anruf über den Arbeitsplatz

Mit der Funktion "Geschäft arbeitsplatz" können Unternehmensbenutzer Sprachanrufe vom Skype for Business-Client aus führen. Wenn ein Benutzer einen Sprachanruf anruft, wird er von Skype for Business an die Nebenstellenanlage oder das Festnetztelefon des Ermittlers geroutet. Sobald der Ermittler das Telefon beantwortet, wird der Anruf an die Zielnummer geleitet. Der Anrufempfänger antwortet, und der Anruf wird mit Skype for Business eingerichtet, das als Systemsteuerung dient. Der Ermittler kann seine Anwesenheits- und Anrufsteuerungen über Skype for Business verwalten. Serveradministratoren aktivieren und konfigurieren "Anruf über Arbeit" für das Unternehmen. Weitere Informationen finden Sie unter [Plan for Call Via Work in Skype for Business Server 2015](plan-your-deployment/enterprise-voice-solution/call-via-work.md). 
  
## <a name="mobile-device-support-improvements"></a>Verbesserungen bei der Unterstützung mobiler Geräte

Zu den Verbesserungen bei der Unterstützung mobiler Geräte gehören Features zur Verbesserung der mobilen Benutzererfahrung für Enterprise Edition-Benutzer, z. B. Zugriff auf aufgezeichnete Unterhaltungen und Protokolldaten, verbesserte mobile Besprechungsumgebungen und Unterstützung für einmaliges Anmelden in Office. Darüber hinaus gibt es Verbesserungen an der Android-Unterstützung, Leistungsverbesserungen und Features, um die Integration über das Common App Framework zu vereinfachen. 
  
> [!NOTE]
> Lync 2013-UCWA-Server müssen auf Skype for Business Server 2015 aktualisiert werden, um mobile Clients zu unterstützen. 
  
### <a name="server-side-conversation-history-is-now-available-on-mobile-devices"></a>Serverseitiger Unterhaltungsverlauf ist jetzt auf mobilen Geräten verfügbar

Um den mobilen Zugriff auf aufgezeichnete Unterhaltungen, verpasste Sofortinformationen und Anrufprotokolldaten zu ermöglichen, wird die Archivierung dieser Informationen jetzt über den Server für alle mobilen Clients verarbeitet. Die Funktion "Automatisches Annehmen" für Sofortnachrichten verbessert die Zuverlässigkeit, indem Server-Time-Out-Nachrichten verhindert werden, wenn ein mobiler Benutzer nicht sofort auf eine Sofortnachrichten reagiert. Um die serverbasierte Integration von Exchange/Outlook-Ordnern nutzen zu können, sind Exchange Server 2013 oder neuere und aktualisierte mobile Clients erforderlich. 
  
### <a name="enhanced-meeting-experiences"></a>Verbesserte Besprechungserfahrungen

Die auf dem Desktop verfügbaren Besprechungsfunktionen sind jetzt auch für mobile Benutzer verfügbar. Zu den neuen Funktionen gehören:
  
- Asynchrone Navigation von freigegebenen PowerPoint-Inhalten
- Die Fähigkeit des Presenters, die Kontrolle über freigegebene PowerPoint-Inhalte zu übernehmen
- Lobbyverwaltung für Moderatoren, sodass sie Teilnehmer zulassen oder verweigern können
    
### <a name="skype-for-business-on-android-improvements"></a>Verbesserungen für Skype for Business unter Android

Skype for Business unter Android bietet jetzt Funktionen, die denen in Skype for Business unter iOS und Skype for Business unter Windows ähneln:
  
- Unterhaltungen fortsetzen oder erneut beitreten
- Aktivieren der Zertifikat- und passiven Authentifizierung
- Einladen anderer Personen zu einer Unterhaltung
- Einfaches Starten von Gruppenunterhaltungen
- Teilnehmen an einer Besprechung ohne Skype for Business-Benutzer
- Aktivieren der Smartphone-UI auf Android-Tablets
- Verwalten von Besprechungen durch Hinzufügen oder Entfernen von Teilnehmern
    
> [!NOTE]
> Für diese Features ist Android OS Version 4.0 oder höher erforderlich. 
  
## <a name="management-of-on-premises-servers"></a>Verwaltung von lokalen Servern

Skype for Business Server 2015 bietet mehrere neue Features, um die Verwaltbarkeit von lokalen Servern zu verbessern, einschließlich eines lokalen Upgrades, intelligentes Setup, verbesserter Patching- und Upgradeprozesse, verbesserter Kaltstartfunktion für Front-End-Pools, SQL Server -AlwaysOn-Unterstützung sowie zentralisierte Protokollierung und Problembehandlung.
  
### <a name="in-place-upgrade-for-on-premises-servers"></a>Lokales Upgrade für lokale Server

Sie können jetzt Lync Server 2013-Systeme auf Skype for Business Server 2015 aktualisieren, indem Sie das neue Feature für das in-Place-Upgrade verwenden, das vorhandene Lync Server 2013-Hardware- und Serverinvestitionen verwendet, wodurch die Gesamtkosten für die Bereitstellung von Skype for Business Server 2015 reduziert werden.
  
Es gibt zwei Szenarien für ein in-Place-Upgrade: die Methode zum Verschieben von Benutzern, die keine Downtime erfordert, und die Offlinemethode, die Ausfallzeiten erfordert. Weitere Informationen dazu, welches Upgradeverfahren für Ihr Unternehmen am richtigen ist, finden Sie unter [Plan to upgrade to Skype for Business Server 2015](plan-your-deployment/upgrade.md). 
  
> [!NOTE]
> Die Option "In-Place" ist nicht verfügbar, wenn Sie ein Upgrade von Lync Server 2010 durchführen. Weitere Informationen zum Upgrade von Lync Server 2010 finden Sie unter [Plan to upgrade to Skype for Business Server 2015](plan-your-deployment/upgrade.md). 
  
### <a name="smart-setup"></a>Intelligentes Setup

Das Smart-Setup-Feature, mit dem Updates automatisch erkannt und heruntergeladen werden, ist nun Teil des Setupprogramms. Während des Installationsvorgangs wird der Benutzer gefragt, ob der Installationsprozess nach Updates suchen soll. Weitere Informationen finden Sie unter ["Installieren von Skype for Business Server 2015".](deploy/install/install.md)
  
### <a name="improved-front-end-server-patching-and-upgrade-process"></a>Verbesserter Patch- und Upgradeprozess für Front-End-Server

Skype for Business Server führt zwei neue Cmdlets ein, die das Upgrade oder Patchen von Front-End-Servern wesentlich einfacher machen als in früheren Versionen von Lync Server.
  
Wenn Sie einen Patch auf einen Front-End-Server anwenden oder eine andere Wartung durchführen müssen, geben Sie einfach **"Invoke-CsComputerFailOver"** ein, und geben Sie den Namen dieses Servers an. Skype for Business Server verschiebt die Arbeitsauslastung dieses Servers vorübergehend auf die anderen Server im Pool. Anschließend können Sie die Wartung durchführen und dann das **Cmdlet "Invoke-CsComputerFailback"** verwenden, um den Server wieder in Betrieb zu setzen. Wenn Sie jeden Server in einem Pool patchen müssen, führen Sie dieses Verfahren für jeden Server nach dem anderen aus. Mit diesen neuen Cmdlets können Sie Server viel schneller patchen als in früheren Versionen, und dies mit einer größeren Zuverlässigkeit und einem einfacheren Workflow.
  
### <a name="improved-front-end-pool-cold-start-capability"></a>Verbesserte Kaltstartfunktion für Front-End-Pools

Skype for Business Server führt ein neues Cmdlet ein, das das Kaltstarten eines gesamten Front-End-Pools vereinfacht und verbessert. Wenn Sie das neue **Cmdlet "Start-CsPool"** verwenden, überprüft es die Voraussetzungen für alle Front-End-Server im Pool und versucht dann, jeden Server zu starten. Wenn Probleme auftreten, werden sie diagnostizieren und Sie mit Details und Problemumgehungen benachrichtigt. In einigen Fällen können Sie den Pool auch dann starten, wenn einige der einzelnen Server nicht gestartet werden können.
  
### <a name="sql-server-alwayson-support-for-on-premises-servers"></a>SQL Server der AlwaysOn-Unterstützung für lokale Server

Skype for Business Server 2015 bietet Sowohl für SQL Server Als auch für SQL Server AlwaysOn-Failoverclusterinstanzen Unterstützung. Zusätzlich zu diesen Features unterstützt Skype for Business Server weiterhin Datenbankspiegelung und SQL Server Clustering, wie in früheren Versionen von Lync Server.
  
SQL Server AlwaysOn Availability Groups ist eine Hochverfügbarkeits- und Notfallwiederherstellungslösung in SQL Server 2012 und SQL Server 2014, die eine Alternative zur Datenbankspiegelung bietet. Eine Verfügbarkeitsgruppe unterstützt eine Failoverumgebung für eine diskrete Gruppe von Datenbanken (auch als Verfügbarkeitsdatenbanken bezeichnet), bei deren Failover ein Failover ausgeführt wird. Eine Verfügbarkeitsgruppe unterstützt eine Reihe von primären Datenbanken mit Lese-/Schreibzugriff und einen bis vier Sätze entsprechender sekundärer Datenbanken. Optional können sekundäre Datenbanken für den schreibgeschützten Zugriff und für einige Sicherungsvorgänge verfügbar gemacht werden.
  
SQL Server Failoverclusterinstanzen nutzen die Windows Server Failover Clustering (WSFC)-Funktionalität, um lokale Hochverfügbarkeit durch Redundanz auf Serverinstanzebene bereitzustellen – eine Failoverclusterinstanz (Failover Cluster Instance, FCI). Eine FCI ist eine einzelne Instanz von SQL Server, die über Windows Server Failover Clustering (WSFC)-Knoten und möglicherweise über mehrere Subnetze hinweg installiert wird.
  
Weitere Informationen finden Sie unter [Plan for high availability and disaster recovery in Skype for Business Server 2015](plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
### <a name="centralized-logging-and-troubleshooting-improvements-for-on-premises-servers"></a>Verbesserungen bei der zentralisierten Protokollierung und Problembehandlung für lokale Server

Der zentralisierte Protokollierungsdienst ist die bevorzugte Protokollierungsumgebung für Skype for Business Server 2015. In dieser Version gibt es keine neuen Features, aber zuverlässigkeit und Leistung wurden sowohl für den Dienst als auch für den Centralized Logging Service Agent (ClsAgent.exe) verbessert – die ausführbare Datei des Diensts, die mit dem Controller kommuniziert und Vom Administrator ausgegebene Befehle empfängt.
  
Skype for Business Server 2015 verwendet Windows PowerShell Cmdlets, um die Protokollierungsdienst-Agents zu verwalten, die Ablaufverfolgung zu initiieren und Berichte zu generieren. (Lync Server 2013 verwendet ClsController.exe zum Ausführen dieser Aufgaben.)
  
Der zentralisierte Protokollierungsdienst kann auf einem beliebigen Skype for Business Server 2015 ausgeführt werden. Die integrierten Szenarien (vordefinierte Ablaufverfolgungen) bleiben unverändert, ebenso wie die Möglichkeit, benutzerdefinierte Szenarien zu erstellen. Es gibt ein spezielles Szenario mit dem Namen "AlwaysOn", das immer ausgeführt wird und es Administratoren ermöglicht, häufige Probleme nahezu in Echtzeit zu finden.
  
Das Snooper-Debugtool wurde ebenfalls aktualisiert, um das Debuggen von Mobilitätsprotokollen zu ermöglichen, und kann mit Geräten verwendet werden, die eine Verbindung mit Lync 2013 oder Skype for Business Server 2015 herstellen. Das Tool steht als Webdownload von [Debuggingtools zur Verfügung.](https://go.microsoft.com/fwlink/?LinkId=285257)
  
## <a name="hybrid-deployment-and-management"></a>Hybridbereitstellung und -verwaltung

Skype for Business Server 2015 ermöglicht die Verwaltung und Verwaltung von Hybridbereitstellungen, indem die folgenden Funktionen eingeführt werden:
  
- Empfehlungen für Hybridbereitstellungen basierend auf dem Status der lokalen Ressourcen des Kunden, wie durch das automatische Unterstützungstool OnRamp für Office 365 bestimmt.
- Verbesserungen an der Skype for Business Server-Systemsteuerung und dem Skype for Business Server Admin Center, damit Administratoren diese Tools verwenden können, um eine Hybridbereitstellung zu verwalten.
- Verbesserungen der Systemsteuerung, mit deren Hilfe sich Administratoren bei einem Microsoft 365- oder Office 365-Mandanten anmelden und eine Hybridbereitstellung mit Skype for Business Online mit dem Assistenten für die Hybridkonfiguration einrichten können.
- Systemsteuerungsunterstützung für das Verschieben von lokalen Benutzern zu Skype for Business Online oder für die Zurückverwandung von Skype for Business Online-Benutzern in die lokale Version.
- Systemsteuerungsfunktionen zum Identifizieren und Filtern von lokalen Benutzerobjekten, die von lokalen Benutzern zu Skype for Business Online (d. h. Hybridbenutzer) verschoben wurden.
- Admin Center-Features zum Identifizieren und Filtern von Cloudbenutzern, die ursprünglich in Skype for Business Online erstellt wurden, von Hybridbenutzern, die von lokal zu Online migriert wurden.
- Die Möglichkeit, Hybridbenutzer mithilfe der Systemsteuerung für Eigenschaften zu verwalten, die lokal verwaltet werden können, und Admin Center für Eigenschaften, die über Skype for Business Online verwaltet werden können.
- Die Verwendung der Kennwortsynchronisierung mit DirSync, die Möglichkeit zum Synchronisieren von lokalen Active Directory-Kennwörtern mit dem Online-Mandanten. Wenn diese Funktion konfiguriert ist, ist die Bereitstellung von AD FS für die Verbundauthentifizierung nicht mehr erforderlich, AD FS ist jedoch weiterhin für die mehrstufige Authentifizierung erforderlich. 
- Kontinuierliche Unterstützung für die Koexistenz zwischen Skype for Business Online und exchange lokal.
    
> [!NOTE]
> Es gibt keine Änderung an der lokalen Koexistenz- und Supporterfahrung von Lync Online 2013 und Exchange. 
  
## <a name="multi-factor-authentication"></a>Mehrstufige Authentifizierung

Bei der mehrstufigen Authentifizierung handelt es sich um eine Authentifizierungsmethode, die die Verwendung von mehreren Überprüfungsmethoden erfordert und eine wichtige zweite Sicherheitsebene für Benutzer bei Anmeldungen und Transaktionen hinzufügt. Beispielsweise müssen Ein Benutzername und Kennwort sowie ein Zertifikat erforderlich sein. Skype for Business Server 2015 baut weiterhin auf den Multi-Factor Authentication-Funktionen auf, die in den kumulativen Updates für Lync Server 2013 verfügbar sind. Die wichtigsten Änderungen bei der mehrstufigen Authentifizierung sind:
  
- Verwenden der Active Directory-Authentifizierungsbibliothek für Office 2013 SP1 für die Integration in Exchange und SharePoint
- Unterstützung für die Multi-Factor Authentication-Funktion im Skype for Business Web App-Client
    
Mit der mehrstufigen Authentifizierung in Skype for Business können sie jetzt je nach Geografie unterschiedliche Authentifizierungsoptionen bereitstellen. Beispielsweise können Kunden ihre Umgebung so konfigurieren, dass die interne Authentifizierung auf der integrierten Windows-Authentifizierung basiert, während Mitarbeiter, die sich von außerhalb der Organisation authentifizieren, die mehrstufige Authentifizierung verwenden. 
  
Die mehrstufige Authentifizierung in Skype for Business ist nahtlos, unabhängig von:
  
- Geografischer Standort – Gibt an, ob sich der Benutzer von innerhalb oder außerhalb der Organisation an- oder abh?nt 
- Client/Gerätetyp – Welcher Skype for Business-Client verwendet wird und auf welchem Gerät der Client ausgeführt wird (PC, Mobil, iPad usw.)
- Kontospeicherort – Gibt an, ob der Benutzer in einem lokalen Active Directory oder in Azure Active Directory Online gehostet wird.
