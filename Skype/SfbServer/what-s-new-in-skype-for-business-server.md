---
title: Neuigkeiten in Skype for Business Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e62c9229-b738-45ef-b637-0b58ca8225a4
description: 'Zusammenfassung: Lesen Sie dieses Thema, um Informationen zu neuen Features in Skype für Business Server 2015 zu erhalten. Ausführliche Informationen zu den neuen Client gewohnt sind finden Sie in Lync jetzt Skype für Unternehmen ist – finden Sie unter Neuigkeiten.'
ms.openlocfilehash: 9c5dd3996cb6c15de93b564fa800e01270d92b66
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "21012451"
---
# <a name="whats-new-in-skype-for-business-server-2015"></a>Neuigkeiten in Skype for Business Server 2015

**Zusammenfassung:** Lesen Sie dieses Thema, um Informationen zu neuen Features in Skype für Business Server 2015 erhalten. Ausführliche Informationen zu den neuen Client gewohnt sind finden Sie unter [Lync ist jetzt Skype für Unternehmen – finden Sie unter Neuigkeiten](https://go.microsoft.com/fwlink/p/?LinkId=529022).
  
Lync ist nun Skype für Unternehmen, eine Kommunikation und Zusammenarbeit-Plattform, die eine wünschen inspiriert von Skype mit der Unternehmensklasse Sicherheit, Kompatibilität und Kontrolle von Lync zusammenführt. Skype für Unternehmen bietet Features einschließlich Anwesenheitsinformationen, Sofortnachrichten, VoIP und Videoanrufe und onlinebesprechungen. Skype für Unternehmen bietet einen neuen Client wünschen, eine neue Server-Version und Aktualisierungen an den Dienst in Office 365. Wenn der Benutzer in Ihrer Organisation bereits mit Skype vertraut sind, werden sie zu schätzen wissen die Power und Einfachheit der Skype für Unternehmen, wobei leicht ist zu finden und Verbinden mit Ihren Kollegen. Wenn Benutzer in Ihrer Organisation zu Skype für Unternehmen aus Lync vertraut sind, können sie alle Features erkennen, die Sie bereits verwenden, sondern in einer aktuell neue Benutzeroberfläche mit vereinfacht, Steuerelemente und Ergänzungen. Zusätzlich zu den neuen Client wünschen bietet Skype für Business Server 2015 verschiedene neue Features zur Verbesserung der Verwaltbarkeit von lokalen Servern und hybridlösungen.
  
Neue Funktionen in Skype für Business Server 2015 gehören Verbesserungen an:
  
- Benutzererfahrung  
- Unterstützung von Sprache und Video
- Mobilitätsunterstützung
- Verwaltung lokaler Server
- Bereitstellung und Verwaltung von Hybrid-Lösungen
- Unterstützung mehrstufiger Authentifizierung
    
## <a name="user-experience"></a>Benutzererfahrung

Der Skype für Business-Client die Consumer-Versionen von Skype sehr ähnlich aussieht und die gleichen Schaltflächen und Symbole verwendet. Die Reduzierung der Menüs und eine flachere Aufgabenhierarchie erleichtern den Benutzern das Auffinden von Steuerungen und Befehlen. 
  
Skype für Unternehmen umfasst die neue Benutzeroberfläche, die oben beschriebenen und die Lync 2013-Benutzeroberfläche, die zuvor freigegeben. Die Aufnahme der beiden Erfahrungen kann Unternehmen durch den Prozess steuern und den Zeitpunkt der neuen Client Einführung Änderung für ihre Benutzer verwalten. Die Standard-Benutzeroberfläche, hängt davon ab, welche Version des Servers nutzen. Die Administratoren wählen die bevorzugte Erfahrung, indem Sie das Cmdlet **Set-CsClientPolicy** mit dem Parameter EnableSkypeUI verwenden. Weitere Informationen zum Konfigurieren der Clientumgebung finden Sie unter [Konfigurieren der Clientumgebung mit Skype für Unternehmen](deploy/deploy-clients/configure-the-client-experience.md) und [Desktopclient Featurevergleich für Skype für Unternehmen](plan-your-deployment/clients-and-devices/desktop-feature-comparison.md).
  
> [!NOTE]
> Die Lync 2013-Clientumgebung ist keine Option für Skype für Business 2016 Clientversionen. Bevor Sie versuchen, die Clientumgebung um die Verwendung des Lync 2013-Clients konfigurieren, überprüfen Sie die Clientversion, um sicherzustellen, dass es nicht mit der Nummer 16 gestartet wird; Beispiel: 16.x.x.x. 
  
## <a name="voice-and-video-improvements"></a>Verbesserung von Sprache und Video

Skype für Business Server 2015 enthält Verbesserungen an Funktionalität von Sprach- und Videofunktionen, einschließlich Anruf Datensammlung und Analyse und verbesserte Interoperabilität mit Systemen von Drittanbietern Videokonferenzen.
  
### <a name="call-data-collection-and-analysis"></a>Sammlung und Analyse von Anrufdaten

Rufen Sie meine Rate Feature können Skype für Business Server 2015 Administratoren Anrufdaten erfassen. Diese Funktion steht nur für lokale Bereitstellungen zur Verfügung. Die Benutzer werden aufgefordert, nach dem Anruf eine Umfrage zu beantworten. Weitere Informationen finden Sie unter [Meine Anruf in Skype für Business Server 2015 Rate](manage/health-and-monitoring/rate-my-call.md).
  
### <a name="improved-interoperability-with-third-party-video-teleconferencing-systems"></a>Verbesserte Interoperabilität mit externen Telekonferenzsystemen

Video Interop Server (gegenüber) dient als Vermittlung zwischen Skype für Business Server und Cisco Videokonferenzen (VTC). Wenn die Benutzer an einer Konferenz teilnehmen, können Sie ab sofort ein VTC-System von Cisco auswählen. Der Video Interoperability Server (VIS) ist als eigenständige Serverrolle für lokale Bereitstellungen implementiert. Weitere Informationen finden Sie unter [Planen für Video Interop-Server in Skype für Business Server 2015](plan-your-deployment/video-interop-server.md).
  
### <a name="call-via-work"></a>Anruf über den Arbeitsplatz

Das Feature geschäftlich Anrufen kann Unternehmensbenutzer mit VoIP-Anrufe über die Skype für Business-Client tätigen. Wenn ein Benutzer einen Anruf tätigt, wird es an den Ersteller PBX- oder PSTN-Telefon aus Skype für Unternehmen weitergeleitet. Wenn der Anrufer das Telefon abnimmt, wird der Anruf an die Zielnummer geleitet. Die Anruf-Empfänger Antworten, und der Aufruf ist mit Skype für Unternehmen, die als die Systemsteuerung eingerichtet. Der Absender kann verwalten ihre Anwesenheit und rufen Steuerelemente Skype für Unternehmen. Die Serveradministratoren aktivieren und konfigurieren „Anruf über Arbeit“ für Unternehmen. Weitere Informationen finden Sie unter [Planen von Anrufen über Arbeitsplatz in Skype für Business Server 2015](plan-your-deployment/enterprise-voice-solution/call-via-work.md). 
  
## <a name="mobile-device-support-improvements"></a>Verbesserungen des Supports von mobilen Geräten

Verbesserte Unterstützung für mobile Geräte enthalten Features zur Verbesserung des mobilen Zugriffs für Enterprise Edition-Benutzer, wie der Zugriff auf die Unterhaltung Verlauf und Protokolldateien Daten, erweiterte mobile Besprechung Erfahrungen und Unterstützung für einmaliges Anmelden in Office. Darüber hinaus sind Verbesserungen an die Android Support, leistungsverbesserungen und Funktionen zur Vereinfachung der Integration über das allgemeine App-Framework. 
  
> [!NOTE]
> Lync 2013 UCWA-Server müssen auf Skype für Business Server 2015 zur Unterstützung von mobilen Clients aktualisiert werden. 
  
### <a name="server-side-conversation-history-is-now-available-on-mobile-devices"></a>Der serverseitige Gesprächsverlauf ist nun auf mobilen Geräten verfügbar

Zum Aktivieren des mobilen Zugriffs Unterhaltungen, verpasste Instant Messaging und Protokolldaten Anruf wird dieser Angaben Archivierung jetzt über den Server für alle mobilen Clients verarbeitet. Die automatische Akzeptanzfunktion für Sofortnachrichten verbessert die Zuverlässigkeit, indem Meldungen zu überschrittenen Zeitlimits für Server vermieden werden, wenn ein mobiler Benutzer nicht sofort auf eine Sofortnachricht antwortet. Um die Server-basierte Exchange-/Outlook-Ordner Integration nutzen zu können, sind Exchange Server 2013 oder neuere und aktualisierte mobilen Clients erforderlich. 
  
### <a name="enhanced-meeting-experiences"></a>Verbesserte Besprechungserfahrungen

Die Besprechungsfunktionen, die auf dem Desktop verfügbar sind, sind ab sofort auch für mobile Benutzer verfügbar. Die neuen Funktionen umfassen:
  
- Eine asynchrone Navigation der geteilten PowerPoint-Inhalte
- Vom Referenten Möglichkeit, die Steuerung über freigegebene PowerPoint Content übernehmen
- Die Lobby-Verwaltung durch den Referenten, die ein Ablehnen oder Akzeptieren der Teilnehmer ermöglicht
    
### <a name="skype-for-business-on-android-improvements"></a>Skype für Unternehmen auf Verbesserungen von Android

Skype für Unternehmen auf Android bietet jetzt Features zur Verfügung auf Skype für Unternehmen auf IOS- und Skype für Unternehmen Windows stehen ähnelt:
  
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

Skype für Business Server 2015 bietet verschiedene neue Funktionen zur Verbesserung der Verwaltbarkeit von lokalen Servern, einschließlich direkte Aktualisierung, smart Setup, verbesserte Patchen und Upgrade verarbeitet, verbesserte Front-End-Pool kalt Start-Funktion, SQL Server AlwaysOn Unterstützung und zentralisierte Protokollierung und Problembehandlung.
  
### <a name="in-place-upgrade-for-on-premises-servers"></a>Direkte Upgrades für lokale Server

Sie können Lync Server 2013-Systeme jetzt für Business Server 2015 mithilfe der neuen in-Place Upgrade Funktion, die vorhandene Investitionen in Lync Server 2013 Hardware und Server verwendet wird, wodurch die Gesamtkosten zum Bereitstellen von Skype für Business Server 2015 zu Skype aktualisieren.
  
Es gibt zwei Szenarien für die direkten Upgrades: die Methode, bei der Benutzer verschoben werden und es zu keiner Ausfallzeit des Servers kommt, und die Offline-Methode, bei der der Server abgestellt werden muss. Weitere Informationen zu den Upgrade-Prozedur für Ihr Unternehmen geeignet ist, finden Sie unter [Planen eines Upgrades auf Skype für Business Server 2015](plan-your-deployment/upgrade.md). 
  
> [!NOTE]
> Die in-Place-Option ist nicht verfügbar, wenn Sie ein von Lync Server 2010 Upgrade. Weitere Informationen über das Aktualisieren von Lync Server 2010 finden Sie unter [Planen eines Upgrades auf Skype für Business Server 2015](plan-your-deployment/upgrade.md). 
  
### <a name="smart-setup"></a>Smart Setup

Die intelligente Setup-Funktion, die automatisch erkennt und lädt Updates, ist nun Teil des Setup-Programms. Während der Installation wird der Benutzer gefragt, ob der Installationsvorgang nach Updates suchen soll. Weitere Informationen finden Sie unter [Installieren von Skype für Business Server 2015](deploy/install/install.md).
  
### <a name="improved-front-end-server-patching-and-upgrade-process"></a>Verbesserter Patching- und Upgrade-Prozess für Front-End-Server

Skype für Business Server werden zwei neue Cmdlets, mit denen aktualisieren oder Patchen von Front-End-Servern viel einfacher, als in früheren Versionen von Lync Server vorgestellt.
  
Wenn Sie dazu Anwenden eines Patches oder andere Wartung auf einem Front-End-Server ausführen, geben Sie **Invoke-CsComputerFailOver** und geben Sie einfach Namen des Servers. Skype für Business Server wird der Arbeitslast des Servers vorübergehend auf den anderen Servern im Pool verschoben. Daraufhin können Sie die Wartung vornehmen und dann das Cmdlet **Invoke-CsComputerFailback** verwenden, um den Server wieder zu starten. Wenn Sie auf alle Server im Pool ein Patch anwenden müssen, befolgen Sie einfach diese Vorgehensweise für jeden einzelnen Server nacheinander. Diese neuen Cmdlets ermöglichen Ihnen im Vergleich zu vorherigen Versionen eine viel schnellere Anwendung von Patches auf Server, sorgen für eine höhere Zuverlässigkeit und vereinfachen den Workflow.
  
### <a name="improved-front-end-pool-cold-start-capability"></a>Verbesserte Kaltstart-Fähigkeiten für Fron-End-Pools

Skype für Business Server führt ein neues Cmdlet, das vereinfacht und verbessert die beim kalt-Starten eines gesamten Front-End-Pools. Wenn Sie das neue Cmdlet **Start-CsPool** verwenden, überprüft die Voraussetzungen für alle Front-End-Server im Pool und versucht dann, alle Server zu starten. Falls Probleme auftreten sollten, werden Diagnosen durchgeführt und Sie erhalten Meldungen mit Informationen und Vorgehensweisen. In einigen Fällen ist ein Start des Pools sogar dann möglich, wenn einzelne Server nicht gestartet werden können.
  
### <a name="sql-server-alwayson-support-for-on-premises-servers"></a>Unterstützung von SQL Server AlwaysOn für lokale Server

Skype für Business Server 2015 fügt die Unterstützung für SQL Server AlwaysOn Availability Groups und SQL Server AlwaysOn-Failoverclusterinstanzen hinzu. Zusätzlich zu diesen Features wird weiterhin Skype für Business Server unterstützt Database mirroring und SQL Server-Clustern, wie in früheren Versionen von Lync Server aus.
  
SQL Server AlwaysOn Availability Groups ist eine hohe Verfügbarkeit und Disaster Recovery-Lösung in SQL Server 2012 und SQL Server 2014, das eine Alternative zur datenbankspiegelung bereitstellt. Eine verfügbarkeitsgruppe unterstützt eine Failoverumgebung für einen einzelnen Satz von Datenbanken (wie Verfügbarkeit Datenbanken bezeichnet), die zusammen Failover. Eine verfügbarkeitsgruppe unterstützt einen Satz von Lese-/ Schreibzugriff primäre Datenbanken und bis zu vier Gruppen von entsprechenden sekundären Datenbanken. Optional können sekundäre Datenbanken verfügbar für schreibgeschützten Zugriff und für einige Sicherungsvorgänge vorgenommen werden.
  
SQL Server-Failoverclusterinstanzen nutzen Windows Server Failover Clustering (WSFC) Funktionen für die lokalen hohe Verfügbarkeit durch Redundanz Ebene der Server-Instanz zu gewährleisten – einer Failoverclusterinstanz (FCI). Ein FCI ist eine einzelne Instanz von SQL Server, die über Windows Server Failover Clustering (WSFC)-Knoten und möglicherweise auch über mehrere Subnetze installiert ist.
  
Weitere Informationen finden Sie unter [Planen für hohe Verfügbarkeit und notfallwiederherstellung in Skype für Business Server 2015](plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
### <a name="centralized-logging-and-troubleshooting-improvements-for-on-premises-servers"></a>Verbesserung der zentralisierten Protokollierung und Fehlerbehebung bei lokalen Servern

Der zentralisierte Protokollierungsdienst ist die bevorzugte Protokollierung Umgebung für Skype für Business Server 2015. Es gibt keine neuen Funktionen in dieser Version aber die Zuverlässigkeit und die Leistung wurden für den Dienst und den zentralisierten Protokollierungs-Agent (ClsAgent.exe), den ausführbaren Dienst, der mit dem Controller kommuniziert und Befehle erhält, die vom Administrator ausgegeben werden, verbessert.
  
Skype für Business Server 2015 verwendet Windows PowerShell-Cmdlets zum Verwalten der Protokollierung Dienst-Agents Tracing initiieren und Generieren von Berichten. (Lync Server 2013 verwendet ClsController.exe zum Ausführen dieser Aufgaben).
  
Der zentralisierte Protokollierungsdienst können auf eine beliebige Skype für Business Server 2015 ausführen. Die integrierten Szenarien (vordefinierte Ablaufverfolgungen) bleiben erhalten, genauso die Fähigkeit zur Erstellung von benutzerdefinierten Szenarien. Es gibt ein besonderes Szenario, das „AlwaysOn“ genannt wird, dauerhaft ausgeführt wird und den Administratoren die Lokalisierung allgemeiner Probleme nahezu in Echtzeit ermöglicht.
  
Das Tool zum Debuggen Snooper wurde ebenfalls aktualisiert, um das Debuggen von Mobilität Protokolle zu ermöglichen und mit Geräten in Lync 2013 oder Skype für Business Server 2015 funktionieren. Das Tool ist als Download im Web [Debugging](https://go.microsoft.com/fwlink/?LinkId=285257)Tools verfügbar.
  
## <a name="hybrid-deployment-and-management"></a>Hybrid-Bereitstellung und Verwaltung

Skype für Business Server 2015 ermöglicht hybride Bereitstellung Administrations- und Verwaltungsfunktionen durch die Einführung die folgenden Features:
  
- Empfehlungen für hybridbereitstellungen basierend auf den Status des Kunden lokalen Objekte, wie durch die OnRamp für Office 365 automatisiertes unterstützungstool bestimmt.
- Verbesserungen an der Skype für Business Server-Systemsteuerung und die Skype für Business Server Admin Center, damit Administratoren diese Tools zum Verwalten einer hybridbereitstellung verwenden können.
- Systemsteuerung Verbesserungen, mit denen Administratoren melden Sie sich bei einem Office 365-Mandanten und Einrichten von Hybriden mit Skype für Business Online mithilfe des Assistenten für die hybridkonfiguration zu steuern.
- Steuern Sie Unterstützung zum Migrieren von lokalen Benutzern zu Skype für Business Online oder Verschieben von Skype für Business Online-Benutzer wieder auf lokal Systemsteuerung.
- Systemsteuerung Features zum Erkennen und Filtern von lokalen User-Objekte, die in Skype für Business Online (d. h., hybridbenutzer) verschoben wurden von lokalen Benutzern zu steuern.
- Admin Center zu erkennen und Filtern von cloudbenutzern anfänglichem in Skype für Business Online aus hybridbenutzer Features migriert in Online von lokalen wurde.
- Die Möglichkeit, hybridbenutzer mithilfe der Systemsteuerung für Eigenschaften von lokalen und Admin Center für Eigenschaften von Skype verwaltbaren verwaltbaren für Business Online zu verwalten.
- Fähigkeit zur Synchronisierung lokaler Active Directory-Kennwörter mit dem Online-Mandanten dank Passwortsynchronisierung mit DirSync. Wenn diese Funktion konfiguriert wurde, muss AD FS für Partnerauthentifizierung nicht mehr bereitgestellt werden, aber AD FS ist für die mehrstufige Authentifizierung noch immer notwendig. 
- Unterstützung für die Koexistenz Skype für Business Online und Exchange lokal fortgesetzt.
    
> [!NOTE]
> Es ist keine Änderung gegenüber der Lync Online 2013 und Exchange lokale-Koexistenz und Unterstützung wünschen. 
  
## <a name="multi-factor-authentication"></a>Mehrstufige Authentifizierung

Mehrstufige Authentifizierung ist eine Methode der Authentifizierung, die erfordert die Verwendung von mehr als eine Überprüfungsmethode und benutzeranmeldungen und Transaktionen eine zweite wichtige Sicherheitsebene hinzugefügt. Beispielsweise können einen Benutzernamen und das Kennwort sowie ein Zertifikat. Skype für Business Server 2015 weiterhin auf die mehrstufige Authentifizierungsfeatures in der kumulativen Updates für Lync Server 2013 erstellen. Die wesentlichen Änderungen in mehrstufige Authentifizierung sind:
  
- Verwendung der Active Directory-Authentifizierungsbibliothek von Office 2013 SP1 zur Integration von Exchange und SharePoint
- Unterstützung für das Feature für die mehrstufige Authentifizierung in der Skype für Business Web App-client
    
Mit Skype für Business mehrstufige Authentifizierung ist es möglich, unterschiedliche Authentifizierungsoptionen basierend auf dem geografischen Standort bereitzustellen. Beispielsweise können Kunden ihre Umgebung so konfigurieren, dass die interne Authentifizierung auf die integrierte Windows-Authentifizierung vertraut, während Mitarbeiter außerhalb des Unternehmens die mehrstufige Authentifizierung nutzen. 
  
Die Skype Business mehrstufige Authentifizierung wünschen ist unabhängig von nahtlos:
  
- Geografischen Standort - gibt an, ob der Benutzer von innerhalb oder außerhalb der Organisation anmelden 
- Client-Gerät - welche Skype für Business-Client verwendet werden und welche Geräte der Client ausgeführt wird (PC, Mobile, iPad usw.).
- Pfad - berücksichtigt werden, ob der Benutzer in einer lokalen Active Directory oder in Azure Active Directory Online (O365) gehostet wird