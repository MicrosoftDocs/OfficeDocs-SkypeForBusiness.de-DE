---
title: Neuigkeiten in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2017
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e62c9229-b738-45ef-b637-0b58ca8225a4
description: 'Zusammenfassung: Lesen Sie dieses Thema, um mehr über die neuen Funktionen in Skype for Business Server 2015 zu erfahren. Detaillierte Informationen zur neuen Clientumgebung finden Sie unter lync ist jetzt Skype for Business – sehen Sie, was es neues gibt.'
ms.openlocfilehash: e59d158242a5d2dd4b129da3a531749b22e3eadc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34291515"
---
# <a name="whats-new-in-skype-for-business-server-2015"></a>Neuigkeiten in Skype for Business Server 2015

**Zusammenfassung:** In diesem Thema finden Sie Informationen zu den neuen Funktionen in Skype for Business Server 2015. Detaillierte Informationen zur neuen Clientumgebung finden Sie unter [lync ist jetzt Skype for Business – sehen Sie, was es neues](https://go.microsoft.com/fwlink/p/?LinkId=529022)gibt.
  
Lync ist jetzt Skype for Business, eine Kommunikations-und Zusammenarbeitsplattform, die eine von Skype inspirierte Erfahrung mit der unternehmensweiten Sicherheit, Compliance und Kontrolle von lync kombiniert. Skype for Business bietet Funktionen wie Anwesenheits-, Chat-, sprach-und Videoanrufe sowie Onlinebesprechungen. Skype for Business bietet eine neue Clientumgebung, eine neue Server Version und Updates für den Dienst in Office 365. Wenn die Benutzer in Ihrer Organisation bereits mit Skype vertraut sind, werden Sie die Leistungsfähigkeit und Einfachheit von Skype for Business schätzen, wo es einfach ist, Kollegen zu finden und mit Ihnen in Kontakt zu treten. Wenn Benutzer in Ihrer Organisation von lync aus zu Skype for Business kommen, erkennen Sie alle Features, die Sie bereits verwenden, aber in einer neuen neuen Benutzeroberfläche mit vereinfachten Steuerelementen und neuen Ergänzungen. Zusätzlich zur neuen Clientumgebung bietet Skype for Business Server 2015 verschiedene neue Funktionen, um die Verwaltbarkeit von lokalen Servern und Hybridlösungen zu verbessern.
  
Zu den neuen Funktionen in Skype for Business Server 2015 gehören Verbesserungen für:
  
- Benutzererfahrung  
- Unterstützung von Sprache und Video
- Mobilitätsunterstützung
- Verwaltung lokaler Server
- Bereitstellung und Verwaltung von Hybrid-Lösungen
- Unterstützung mehrstufiger Authentifizierung
    
## <a name="user-experience"></a>Benutzererfahrung

Der Skype for Business-Client sieht der Verbraucher Version von Skype sehr ähnlich und verwendet die gleichen Schaltflächen und Symbole. Die Reduzierung der Menüs und eine flachere Aufgabenhierarchie erleichtern den Benutzern das Auffinden von Steuerungen und Befehlen. 
  
Skype for Business umfasst die oben beschriebene neue Benutzererfahrung und die zuvor veröffentlichte lync 2013-Benutzeroberfläche. Durch die Einbeziehung beider Erfahrungen können Unternehmen den Wandel für Ihre Benutzer verwalten, indem Sie den Prozess und die Anzeigedauer des neuen Client-Rollouts steuern. Die standardmäßige Benutzeroberfläche hängt davon ab, welche Version des Servers Sie verwenden. Die Administratoren wählen die bevorzugte Erfahrung, indem Sie das Cmdlet **Set-CsClientPolicy** mit dem Parameter EnableSkypeUI verwenden. Weitere Informationen zum Konfigurieren der Clientumgebung finden Sie unter [Konfigurieren der Clientumgebung mit Skype for Business](deploy/deploy-clients/configure-the-client-experience.md) -und [Desktop-Client-Funktionsvergleich für Skype for Business](plan-your-deployment/clients-and-devices/desktop-feature-comparison.md).
  
> [!NOTE]
> Die lync 2013-Clientumgebung ist keine Option für Skype for Business 2016-Clientversionen. Bevor Sie versuchen, ihre Clientumgebung für die Verwendung des lync 2013-Clients zu konfigurieren, überprüfen Sie die Client Version, um sicherzustellen, dass Sie nicht mit der Zahl 16 beginnt; Beispiel: 16. x.x.x. 
  
## <a name="voice-and-video-improvements"></a>Verbesserung von Sprache und Video

Skype for Business Server 2015 enthält Verbesserungen an sprach-und Videofunktionen, einschließlich der Erfassung und Analyse von Anrufdaten sowie eine verbesserte Interoperabilität mit Video Teleconferencing-Systemen von Drittanbietern.
  
### <a name="call-data-collection-and-analysis"></a>Sammlung und Analyse von Anrufdaten

Mit der Funktion mein Anruf abstimmen können Skype for Business Server 2015-Administratoren Anrufdaten sammeln. Diese Funktion steht nur für lokale Bereitstellungen zur Verfügung. Die Benutzer werden aufgefordert, nach dem Anruf eine Umfrage zu beantworten. Weitere Informationen finden Sie unter [Rate my Call in Skype for Business Server 2015](manage/health-and-monitoring/rate-my-call.md).
  
### <a name="improved-interoperability-with-third-party-video-teleconferencing-systems"></a>Verbesserte Interoperabilität mit externen Telekonferenzsystemen

Der Video-Interop-Server (VIS) fungiert als Vermittler zwischen Skype for Business Server-und Cisco Video Teleconferencing (VTC)-Systemen. Wenn die Benutzer an einer Konferenz teilnehmen, können Sie ab sofort ein VTC-System von Cisco auswählen. Der Video Interoperability Server (VIS) ist als eigenständige Serverrolle für lokale Bereitstellungen implementiert. Weitere Informationen finden Sie unter [Planen des Video-Interop-Servers in Skype for Business Server 2015](plan-your-deployment/video-interop-server.md).
  
### <a name="call-via-work"></a>Anruf über den Arbeitsplatz

Mit der Funktion Anruf über Arbeit können Unternehmensbenutzer Sprachanrufe über den Skype for Business-Client führen. Wenn ein Benutzer einen Sprachanruf ablegt, wird er von Skype for Business an die Telefonanlage oder das PSTN-Telefon des Urhebers weitergeleitet. Wenn der Anrufer das Telefon abnimmt, wird der Anruf an die Zielnummer geleitet. Der Anrufempfänger antwortet, und der Anruf wird mit Skype for Business eingerichtet, das als Control Panel fungiert. Der Urheber kann seine Anwesenheits-und Anrufsteuerungen von Skype for Business aus verwalten. Die Serveradministratoren aktivieren und konfigurieren „Anruf über Arbeit“ für Unternehmen. Weitere Informationen finden Sie unter [Planen von Anrufen über die Arbeit in Skype for Business Server 2015](plan-your-deployment/enterprise-voice-solution/call-via-work.md). 
  
## <a name="mobile-device-support-improvements"></a>Verbesserungen des Supports von mobilen Geräten

Zu den Verbesserungen bei der Unterstützung mobiler Geräte zählen Features zur Verbesserung der mobilen Benutzerfreundlichkeit von Enterprise Edition-Benutzern wie Zugriff auf Konversations Verlauf und Protokolldaten, verbesserte mobile Besprechungs Erlebnisse und Unterstützung für einmaliges Anmelden in Office. Darüber hinaus gibt es Verbesserungen bei der Unterstützung von Android, Leistungsverbesserungen und Features zur Vereinfachung der Integration über das gemeinsame App-Framework. 
  
> [!NOTE]
> Lync 2013 UCWA-Server müssen auf Skype for Business Server 2015 aktualisiert werden, um Mobile Clients zu unterstützen. 
  
### <a name="server-side-conversation-history-is-now-available-on-mobile-devices"></a>Der serverseitige Gesprächsverlauf ist nun auf mobilen Geräten verfügbar

Um mobilen Zugriff auf das Unterhaltungsprotokoll, verpasste Chat-und Anrufprotokoll Daten zu ermöglichen, wird die Archivierung dieser Informationen nun über den Server für alle mobilen Clients verarbeitet. Die automatische Akzeptanzfunktion für Sofortnachrichten verbessert die Zuverlässigkeit, indem Meldungen zu überschrittenen Zeitlimits für Server vermieden werden, wenn ein mobiler Benutzer nicht sofort auf eine Sofortnachricht antwortet. Zur Nutzung der Server basierten Exchange/Outlook-Ordner Integration sind Exchange Server 2013 oder höher sowie aktualisierte Mobile Clients erforderlich. 
  
### <a name="enhanced-meeting-experiences"></a>Verbesserte Besprechungserfahrungen

Die Besprechungsfunktionen, die auf dem Desktop verfügbar sind, sind ab sofort auch für mobile Benutzer verfügbar. Die neuen Funktionen umfassen:
  
- Eine asynchrone Navigation der geteilten PowerPoint-Inhalte
- Fähigkeit des Referenten, die Steuerung von freigegebenen PowerPoint-Inhalten zu übernehmen
- Die Lobby-Verwaltung durch den Referenten, die ein Ablehnen oder Akzeptieren der Teilnehmer ermöglicht
    
### <a name="skype-for-business-on-android-improvements"></a>Skype for Business für Android-Verbesserungen

Skype for Business auf Android bietet nun ähnliche Funktionen wie Skype for Business für IOS und Skype for Business unter Windows:
  
- Gespräche fortführen oder neu aufnehmen
- Unterstützung für Zertifikate und passive Authentifizierung
- Andere zu einem Gespräch einladen
- Gruppengespräche ganz leicht eröffnen
- An Besprechungen teilnehmen, obwohl man kein Skype for Business-Benutzer ist
- Aktivieren von Smartphone-Benutzeroberflächen auf Android-Tablets
- Besprechungen durch Hinzufügen und Entfernen von Teilnehmern verwalten
    
> [!NOTE]
> Diese Funktionen erfordern das Android-Betriebssystem ab Version 4.0. 
  
## <a name="management-of-on-premises-servers"></a>Verwaltung lokaler Server

Skype for Business Server 2015 bietet mehrere neue Features zur Verbesserung der Verwaltbarkeit von lokalen Servern, einschließlich in-Place-Upgrades, intelligentes Setup, verbesserte Patches und Upgrade-Prozesse, verbesserte Kaltstart-Funktion für Front-End-Pools, SQL Server-AlwaysOn Unterstützung sowie zentralisierte Protokollierung und Problembehandlung.
  
### <a name="in-place-upgrade-for-on-premises-servers"></a>Direkte Upgrades für lokale Server

Sie können jetzt lync Server 2013-Systeme auf Skype for Business Server 2015 mithilfe des neuen in-Place-Upgrade-Features aktualisieren, in dem vorhandene lync Server 2013-Hardware-und Server Investitionen verwendet werden, wodurch die Gesamtkosten für die Bereitstellung von Skype for Business Server 2015 reduziert werden.
  
Es gibt zwei Szenarien für die direkten Upgrades: die Methode, bei der Benutzer verschoben werden und es zu keiner Ausfallzeit des Servers kommt, und die Offline-Methode, bei der der Server abgestellt werden muss. Weitere Informationen darüber, welche Upgrade-Methode für Ihr Unternehmen geeignet ist, erhalten Sie unter [Plan to upgrade to Skype for Business Server 2015](plan-your-deployment/upgrade.md). 
  
> [!NOTE]
> Die in-Place-Option steht nicht zur Verfügung, wenn Sie ein Upgrade von lync Server 2010 durchgeführt haben. Weitere Informationen zum Upgrade von lync Server 2010 finden Sie unter [Planen des Upgrades auf Skype for Business Server 2015](plan-your-deployment/upgrade.md). 
  
### <a name="smart-setup"></a>Smart Setup

Das Smart Setup-Feature, das Updates automatisch erkennt und downloadet, ist nun Teil des Setup-Programms. Während des Installationsvorgangs wird der Benutzer gefragt, ob der Installationsvorgang nach Updates suchen soll. Weitere Informationen finden Sie unter [Installieren von Skype for Business Server 2015](deploy/install/install.md).
  
### <a name="improved-front-end-server-patching-and-upgrade-process"></a>Verbesserter Patching- und Upgrade-Prozess für Front-End-Server

Skype for Business Server führt zwei neue Cmdlets ein, mit denen das Upgraden oder Patchen von Front-End-Servern wesentlich einfacher als in früheren Versionen von lync Server ist.
  
Wenn Sie einen Patch anwenden oder andere Wartungsarbeiten an einem Front-End-Server durchführen müssen, geben Sie einfach **Invoke-CsComputerFailOver** ein, und geben Sie den Namen des Servers an. Skype for Business Server verschiebt die Arbeitsauslastung des Servers temporär auf die anderen Server im Pool. Daraufhin können Sie die Wartung vornehmen und dann das Cmdlet **Invoke-CsComputerFailback** verwenden, um den Server wieder zu starten. Wenn Sie auf alle Server im Pool ein Patch anwenden müssen, befolgen Sie einfach diese Vorgehensweise für jeden einzelnen Server nacheinander. Diese neuen Cmdlets ermöglichen Ihnen im Vergleich zu vorherigen Versionen eine viel schnellere Anwendung von Patches auf Server, sorgen für eine höhere Zuverlässigkeit und vereinfachen den Workflow.
  
### <a name="improved-front-end-pool-cold-start-capability"></a>Verbesserte Kaltstart-Fähigkeiten für Fron-End-Pools

Skype for Business Server führt ein neues Cmdlet ein, das den Prozess des Kaltstarts eines gesamten Front-End-Pools vereinfacht und verbessert. Wenn Sie das neue Cmdlet **Start-CsPool** verwenden, überprüft die Voraussetzungen für alle Front-End-Server im Pool und versucht dann, alle Server zu starten. Falls Probleme auftreten sollten, werden Diagnosen durchgeführt und Sie erhalten Meldungen mit Informationen und Vorgehensweisen. In einigen Fällen ist ein Start des Pools sogar dann möglich, wenn einzelne Server nicht gestartet werden können.
  
### <a name="sql-server-alwayson-support-for-on-premises-servers"></a>Unterstützung von SQL Server AlwaysOn für lokale Server

Skype for Business Server 2015 bietet Unterstützung für SQL Server AlwaysOn-Verfügbarkeitsgruppen und SQL Server AlwaysOn-Failovercluster-Instanzen. Zusätzlich zu diesen Features unterstützt Skype for Business Server die Datenbankspiegelung und das SQL Server-Clustering wie in früheren Versionen von lync Server weiterhin.
  
SQL Server AlwaysOn Availability Groups ist eine Lösung für Hochverfügbarkeits-und Disaster Recovery in SQL Server 2012 und SQL Server 2014, die eine Alternative zur Datenbankspiegelung bietet. Eine verfügbarkeitsgruppe unterstützt eine Failover-Umgebung für einen diskreten Satz von Datenbanken (sogenannte Availability-Datenbanken), bei denen ein Failover durchgeführt wird. Eine verfügbarkeitsgruppe unterstützt eine Reihe von Lese-/Schreibzugriff-Primärdatenbanken sowie eine bis vier Gruppen entsprechender sekundärer Datenbanken. Optional können sekundäre Datenbanken für schreibgeschützten Zugriff und für einige Sicherungsvorgänge zur Verfügung gestellt werden.
  
SQL Server-Failover-Cluster Instanzen nutzen die Windows Server-Failover-Clusterfunktion (WSFC), um die lokale hohe Verfügbarkeit durch Redundanz auf Server Ebene zu gewährleisten – eine Failoverclusterinstanz (Failover-Clusterinstanz). Bei einer FCI handelt es sich um eine einzelne Instanz von SQL Server, die über die Windows Server-Failovercluster (WSFC)-Knoten und möglicherweise über mehrere Subnetze installiert ist.
  
Weitere Informationen finden Sie unter [Plan for high availability and disaster recovery in Skype for Business Server 2015](plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
### <a name="centralized-logging-and-troubleshooting-improvements-for-on-premises-servers"></a>Verbesserung der zentralisierten Protokollierung und Fehlerbehebung bei lokalen Servern

Der zentralisierte Protokollierungsdienst ist die bevorzugte Protokollierungs Umgebung für Skype for Business Server 2015. Es gibt keine neuen Funktionen in dieser Version aber die Zuverlässigkeit und die Leistung wurden für den Dienst und den zentralisierten Protokollierungs-Agent (ClsAgent.exe), den ausführbaren Dienst, der mit dem Controller kommuniziert und Befehle erhält, die vom Administrator ausgegeben werden, verbessert.
  
Skype for Business Server 2015 verwendet Windows PowerShell-Cmdlets, um die Protokollierungsdienst-Agents zu verwalten, die Ablaufverfolgung zu initiieren und Berichte zu generieren. (Lync Server 2013 hat ClsController. exe verwendet, um diese Aufgaben auszuführen.)
  
Der zentralisierte Protokollierungsdienst kann auf jedem Skype for Business Server 2015 ausgeführt werden. Die integrierten Szenarien (vordefinierte Ablaufverfolgungen) bleiben erhalten, genauso die Fähigkeit zur Erstellung von benutzerdefinierten Szenarien. Es gibt ein besonderes Szenario, das „AlwaysOn“ genannt wird, dauerhaft ausgeführt wird und den Administratoren die Lokalisierung allgemeiner Probleme nahezu in Echtzeit ermöglicht.
  
Das Snooper-Debugging-Tool wurde ebenfalls aktualisiert, um das Debuggen von Mobilitäts Protokollen zu ermöglichen, und funktioniert mit Geräten, die mit lync 2013 oder Skype for Business Server 2015 verbunden sind. Das Tool steht als Web-Download aus den [Debugging-Tools](https://go.microsoft.com/fwlink/?LinkId=285257)zur Verfügung.
  
## <a name="hybrid-deployment-and-management"></a>Hybrid-Bereitstellung und Verwaltung

Skype for Business Server 2015 ermöglicht die Verwaltung und Verwaltung von Hybrid Bereitstellungsfunktionen durch Einführung der folgenden Features:
  
- Empfehlungen für hybridbereitstellungen auf der Grundlage des Zustands der lokalen Ressourcen des Kunden, wie durch das automatisierte Unterstützungstool "onoffice 365 für automatische Unterstützung" festgelegt.
- Verbesserungen an der Skype for Business Server-Systemsteuerung und dem Skype for Business Server Admin Center, damit Administratoren diese Tools zum Verwalten einer hybridbereitstellung verwenden können.
- Verbesserungen der Systemsteuerung, mit denen sich Administratoren bei einem Office 365-Mandanten anmelden und mit dem Hybrid-Konfigurations-Assistenten Hybrid mit Skype for Business Online einrichten können.
- Control Panel-Unterstützung für das Verschieben von lokalen Benutzern in Skype for Business Online oder das Verschieben von Skype for Business Online-Benutzern zurück in den lokalen Standort.
- Funktionen der Systemsteuerung, um lokale Benutzerobjekte zu identifizieren und zu filtern, die in Skype for Business Online (also Hybrid Benutzer) von lokalen Benutzern verschoben wurden.
- Admin Center-Features zum Identifizieren und Filtern von Cloud-Benutzern, die ursprünglich in Skype for Business Online erstellt wurden, von Hybrid Benutzern, die von lokal in Online migriert wurden.
- Die Möglichkeit zum Verwalten von Hybrid Benutzern über die Systemsteuerung für Eigenschaften, die von lokalen verwaltet werden können, und Admin Center für Eigenschaften, die über Skype for Business Online verwaltbar sind.
- Fähigkeit zur Synchronisierung lokaler Active Directory-Kennwörter mit dem Online-Mandanten dank Passwortsynchronisierung mit DirSync. Wenn diese Funktion konfiguriert wurde, muss AD FS für Partnerauthentifizierung nicht mehr bereitgestellt werden, aber AD FS ist für die mehrstufige Authentifizierung noch immer notwendig. 
- Weitere Unterstützung für die Koexistenz zwischen Skype for Business Online und Exchange lokal.
    
> [!NOTE]
> Es gibt keine Änderung gegenüber der lync Online-2013 und der lokalen Koexistenz-und Supportumgebung für Exchange. 
  
## <a name="multi-factor-authentication"></a>Mehrstufige Authentifizierung

Bei der mehrstufigen Authentifizierung handelt es sich um eine Authentifizierungsmethode, die die Verwendung von mehr als einer Überprüfungsmethode erfordert und den Benutzeranmeldungen und-Transaktionen eine kritische zweite Sicherheitsebene hinzufügt. Beispiel: Sie benötigen einen Benutzernamen und ein Kennwort sowie ein Zertifikat. Skype for Business Server 2015 baut weiterhin auf den mehrstufigen Authentifizierungsfunktionen auf, die in den kumulierten Updates für lync Server 2013 verfügbar sind. Die wesentlichen Änderungen bei der mehrstufigen Authentifizierung sind:
  
- Verwendung der Active Directory-Authentifizierungsbibliothek von Office 2013 SP1 zur Integration von Exchange und SharePoint
- Unterstützung für die mehrstufige Authentifizierungsfunktion im Skype for Business Web App-Client
    
Mit der mehrstufigen Authentifizierung von Skype for Business können nun unterschiedliche Authentifizierungsoptionen auf der Grundlage der geografischen Gegebenheiten bereitgestellt werden. Beispielsweise können Kunden ihre Umgebung so konfigurieren, dass die interne Authentifizierung auf die integrierte Windows-Authentifizierung vertraut, während Mitarbeiter außerhalb des Unternehmens die mehrstufige Authentifizierung nutzen. 
  
Die Skype for Business-mehrstufige Authentifizierungsfunktion ist nahtlos, unabhängig davon:
  
- Geographischer Standort – unabhängig davon, ob sich der Benutzer von innerhalb oder außerhalb der Organisation anmeldet 
- Client/Gerätetyp – welcher Skype for Business-Client verwendet wird und auf welchem Gerät der Client ausgeführt wird (PC, Handy, iPad usw.)
- Konto Standort – ob der Benutzer in einem lokalen Active Directory oder in Azure Active Directory online gehostet wird (Office 365)
