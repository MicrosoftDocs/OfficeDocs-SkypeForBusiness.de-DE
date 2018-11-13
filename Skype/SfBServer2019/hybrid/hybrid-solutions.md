---
title: Skype für hybridlösungen Business
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 5/18/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Eine Erläuterung zu den verfügbaren hybridlösungen in Skype für Business Server 2019.
ms.openlocfilehash: 2909f524d1b9984fe01700a89d1bf6dc1b70f100
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295369"
---
HINWEIS: DIE FOLGENDEN WERDEN AUS 2015 KOPIERT UND WIRD AUSGEFÜHRT. Zusätzliche laufender Platzhalterinhalt finden Sie [unter](#placeholder-topic-for-hybrid-solutions).


# <a name="skype-for-business-hybrid-solutions"></a>Skype für hybridlösungen Business

Hier finden Sie Informationen zur Planung einer Skype für Business hybridbereitstellung. 
  
In diesem Thema werden verschiedene Hybridkonfigurationen vorgestellt, die Ihnen bei der Ermittlung der für Ihr Unternehmen am besten geeigneten Konfiguration helfen sollen. Anschließend können Sie mehr zu der für Sie interessanten Konfiguration lesen, indem Sie den Links in diesem Thema folgen. Das Thema enthält die folgenden Abschnitte:
  
- [Hybridkonfigurationen für Skype for Business](hybrid-solutions.md#BKMK_HybridConfigurations)
    
- [Fügen Sie Skype für Business Online in Ihre vorhandenen Skype für geschäftsumgebung lokale hinzu](hybrid-solutions.md#BKMK_HybridConnectivity)
    
- [Nutzen Sie Telefonsystem in Office 365 (Cloud, PBX)](hybrid-solutions.md#BKMK_CloudPBX)
    
- [Integrieren in Exchange und SharePoint](hybrid-solutions.md#BKMK_IntegratewExchangeSharePoint)
    
- [Aufgaben zum Planen und Konfigurieren einer Hybridumgebung](hybrid-solutions.md#BKMK_Tasks)
    
- [Weitere Informationen](hybrid-solutions.md#BKMK_MoreInfo)
    
## <a name="skype-for-business-hybrid-configurations"></a>Hybridkonfigurationen für Skype for Business
<a name="BKMK_HybridConfigurations"> </a>

Skype für Unternehmen unterstützt mehrere hybridkonfigurationen. Sie können Skype für Business Online in Ihre vorhandenen Skype für geschäftsumgebung lokale hinzugefügt werden, zu integrieren Ihrer Skype für die Business-Bereitstellung mit Exchange Online und SharePoint Online und nutzen Sie Telefonsystem in Office 365 (Cloud, PBX) – Microsofts Technologie zum Aktivieren von Remote Call Control und (Private Branch Exchange, PBX) Funktionen in Office 365 Cloud mit Skype für Business Online. 
  
Mit einem Skype für die hybridbereitstellung Business kombinieren Sie einen Skype für Business Online-Abonnement mit Ihrer lokalen Skype Business angeboten werden soll. Sie können Software-as-a-Service-Management-Kenntnisse in Ihrer Organisation erstellen und Ihrer Skype für Unternehmensbenutzer in Ihrem eigenen Tempo in die Cloud zu verschieben. Die Benutzer, die sich in der Cloud befinden können Telefonsystem in Office 365 nutzen Beibehaltung Ihrer lokalen-Konnektivität (Public Switched Telephone Network, PSTN).
  
Behalten Sie mit einem Skype Business hybridkonfiguration Folgendes beachten:
  
- Obwohl möglicherweise einige Benutzer lokal und einige online verwaltet werden, gehören alle Benutzer zur gleichen SIP-Domäne (Session Initiation-Protokoll), beispielsweise „contoso.com“.
    
- Sie können Benutzer von Skype für Unternehmen lokal zu Skype für Business Online im Laufe der Zeit im Terminplan migrieren.
    
- Sie können die Bereitstellung in andere Microsoft Office 365-Anwendungen wie beispielsweise Exchange Online und SharePoint Online integrieren.
    
- Sie können die Bereitstellung in Exchange und SharePoint integrieren.
    
- Sie können Skype-Livekonferenzen nutzen.
    
- Sie können PSTN-Konferenzen nutzen.
    
## <a name="add-skype-for-business-online-into-your-existing-on-premises-skype-for-business-environment"></a>Fügen Sie Skype für Business Online in Ihre vorhandenen Skype für geschäftsumgebung lokale hinzu
<a name="BKMK_HybridConnectivity"> </a>

Hybridkonnektivität zwischen Skype für Business Server und Skype für Business Online bedeutet, dass Benutzer einer Domäne, z. B. "contoso.com", zwischen der Verwendung von Skype für Business Server lokal und Skype für Business Online verteilt sind. Einige der Domänenbenutzer werden lokal verwaltet, andere dagegen online. Sie können Ihre lokale Bereitstellung für hybride mit Skype für Business Online konfigurieren und mit Active Directory-Synchronisierung können Sie Ihre lokalen und online-Benutzer synchronisiert. 
  
Das folgende Diagramm zeigt, wie Sie Skype für Business Online in Ihre vorhandenen lokalen Skype für Business-Umgebung ermöglicht es Ihnen, die Benutzer in der Cloud in Ihrem eigenen Tempo verschieben hinzufügen können:
  
![Skype for Business-Hybridkonfiguration](../../sfbserver/media/4580f2c8-7008-4c6e-826c-020d0f2d1636.png)
  
Weitere Informationen finden Sie unter [hybridkonnektivität zwischen Skype für Business Server und Skype für Business Online oder Teams planen](plan-hybrid-connectivity.md) und [Konfigurieren von hybridkonnektivität zwischen Skype für Business Server und Skype für Business Online](configure-hybrid-connectivity.md).
  
## <a name="take-advantage-of-phone-system-in-office-365-cloud-pbx"></a>Nutzen Sie Telefonsystem in Office 365 (Cloud, PBX)
<a name="BKMK_CloudPBX"> </a>

 Telefonsystem in Office 365 (Cloud, PBX) ist die Microsoft Technologie für Remote Call Control und (Private Branch Exchange, PBX) Funktionen in Office 365 Cloud mit Skype für Business Online aktivieren. Telefonsystem in Office 365 können Sie Ihre vorhandene PBX-System mit einem Satz von Features von Office 365 übermittelt und nahtlose Integration in Microsoft Cloud-produktivitätserfahrung ersetzen.
  
Microsoft bietet zusätzlich zu den zwei Telefonsystem in Office 365-Hybrid-Dienstangebote, Telefonsystem in Office 365 mit Aufrufen planen – ein Dienst aufrufen PSTN – für eine all-in-Cloud-Lösung, die keine lokalen Server-Bereitstellung erforderlich sind. Wenn Sie entscheiden, ob Telefonsystem in Office 365 mit Aufrufen planen die richtige Lösung für Ihre Organisation möglicherweise, finden Sie unter [Telefonsystem in Office 365-Lösungen](../../sfbserver/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-your-phone-system-cloud-pbx-solution.md#BKMK_PBXOfferings).
  
Es gibt zwei Telefonsystem in Office 365 Hybrid angeboten: 
  
- [Telefonsystem in Office 365 mit der lokale Konnektivität bereitgestellt, die von Ihrer Skype für Business Server-Bereitstellung](hybrid-solutions.md#BKMK_Server)
    
- [In Office 365 mit der lokale Konnektivität von Skype für Business Server Cloud Connector Edition bereitgestellten Telefonsystem](hybrid-solutions.md#BKMK_CCE)
    
### <a name="phone-system-in-office-365-with-on-premises-connectivity-provided-by-your-skype-for-business-server-deployment"></a>Telefonsystem in Office 365 mit der lokale Konnektivität bereitgestellt, die von Ihrer Skype für Business Server-Bereitstellung
<a name="BKMK_Server"> </a>

Diese Konfiguration besteht aus einer Skype für Business Server lokale Bereitstellung für hybride PSTN geändert. Können Benutzer in Ihrer Organisation, die sich in der Cloud befinden PBX-Dienste von Microsoft-Cloud empfangen, aber PSTN-Anbindung über Enterprise-VoIP auf Ihrem lokalen Skype für die Bereitstellung von Business Server bereitgestellt wird. 
  
![Cloud PBX with Skype for Business Server-Bereitstellung](../../sfbserver/media/d4136bbc-b01e-469c-bf94-90ba59c61cda.png)
  
Diese Konfiguration ist in folgenden Fällen am besten geeignet: 
  
- Ihre Nebenstellenanlage bietet keine einzigartigen Funktionen, auf die Sie weiterhin angewiesen sind.
    
- Planen der aufrufenden Office 365 PSTN-Dienst aufrufen ist in Ihrer Region nicht verfügbar.
    
- Sie haben eine vorhandene Lync oder Skype für Business Server-Bereitstellung.
    
Weitere Informationen finden Sie unter [Planen von Telefonsystem in Office 365 mit lokalen PSTN-Konnektivität in Skype für Business Server](../../sfbserver/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity.md) und [Aktivieren von Benutzern für Telefonsystem in Office 365 mit lokalen PSTN-Konnektivität in Skype für Business Server](../../sfbserver/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system.md).
  
### <a name="phone-system-in-office-365-with-on-premises-connectivity-provided-by-skype-for-business-server-cloud-connector-edition"></a>In Office 365 mit der lokale Konnektivität von Skype für Business Server Cloud Connector Edition bereitgestellten Telefonsystem
<a name="BKMK_CCE"> </a>

Diese Konfiguration besteht aus einer Gruppe von gepackten virtuellen Computern (VMs), die lokale PSTN-Anbindung zu implementieren. Durch eine minimale Skype für Business Server-Topologie in einer virtualisierten Umgebung bereitstellen, können Benutzer in Ihrer Organisation, die sich in der Cloud befinden PBX-Dienste von Microsoft-Cloud empfangen, aber PSTN-Anbindung über die vorhandenen lokalen VoIP bereitgestellt wird Infrastruktur. 
  
![CloudPBXCloudConnectorEdition](../../sfbserver/media/7a6ee221-bfe1-422b-ac44-6446db6b766c.png)
  
Diese Konfiguration ist in folgenden Fällen am besten geeignet:
  
- Ihre Nebenstellenanlage bietet keine einzigartigen Funktionen, auf die Sie weiterhin angewiesen sind.
    
- Planen der aufrufenden Office 365 PSTN-Dienst aufrufen ist in Ihrer Region nicht verfügbar.
    
- Sie müssen keiner vorhandenen Lync oder Skype für Business Server-Bereitstellung.
    
Weitere Informationen finden Sie unter [Planen von Skype für Business Cloud Connector Edition](../../sfbserver/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition.md).
  
## <a name="integrate-with-exchange-and-sharepoint"></a>Integrieren in Exchange und SharePoint
<a name="BKMK_IntegratewExchangeSharePoint"> </a>

Eine Skype Business hybridkonfiguration können Sie andere Microsoft Office 365-Anwendungen, einschließlich Exchange Online und SharePoint Online zu integrieren.
  
### <a name="skype-for-business-server-with-exchange-online-and-sharepoint-online"></a>Skype for Business Server mit Exchange Online und SharePoint Online

Sie können Skype für Business Server mit Exchange Online und SharePoint Online integrieren, wie im folgenden Diagramm dargestellt:
  
![Skype for Business Server mit Exchange Online und SharePoint Online](../../sfbserver/media/9f456ed2-8777-4a20-a519-c87dfc56b7f5.png)
  
Integrieren von Skype für Business Server mit Exchange Online und SharePoint Online bietet verschiedene Vorteile. Sie haben folgende Möglichkeiten:
  
- Verwenden Sie den vollen Funktionsumfang von Skype für Business Server.
    
- Nutzen Ihrer vorhandenen lokalen Telefonausstattung, beispielsweise Nebenstellenanlagen
    
- Verwenden von Exchange Online für E-Mail, Verlagern der Belastung durch lokale E-Mail-Server und lokalen Speicher
    
- Verwenden von SharePoint Online für Zusammenarbeit, Verlagern der Belastung durch die Wartung lokaler SharePoint-Server
    
- Verwenden von Skype für Unternehmen, Exchange und SharePoint integriert Features, einschließlich Unified Messaging (UM) in Office 365.
    
Weitere Informationen finden Sie unter [Plan to integrate Skype for Business and Exchange](../../SfbServer/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md).
  
### <a name="exchange-server-with-skype-for-business-online"></a>Exchange Server mit Skype for Business Online

Sie können Exchange Server mit Skype für Business Online integrieren, wie im folgenden Diagramm dargestellt:
  
![Integration von Exchange mit Skype for Business Online](../../sfbserver/media/e8ca44ad-f47c-46a3-9cef-8fe7deafd615.png)
  
Integration von Exchange Server mit Skype für Business Online bietet die folgenden Vorteile:
  
- Nutzen Ihrer vorhandenen Exchange-Infrastruktur
    
- Verwenden Sie Skype für Business Online für Anwesenheits-, SOFORTNACHRICHTEN- und Funktionen. 
    
Weitere Informationen finden Sie unter [Plan to integrate Skype for Business and Exchange](../../SfbServer/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md).
  
## <a name="tasks-for-planning-and-configuring-a-hybrid-environment"></a>Aufgaben zum Planen und Konfigurieren einer Hybridumgebung
<a name="BKMK_Tasks"> </a>

Skype für Unternehmen bietet einen umfassenden Satz an Funktionen, unabhängig davon, wie Sie Ihre Bereitstellung planen. Die ausgewählte Architektur bestimmt, für welche IT-Aufgaben Sie zuständig sind und welche Sie im Rahmen Ihres Abonnements kostenpflichtig an Microsoft übertragen können. Unabhängig davon, welche Architektur für Ihre Organisation am besten geeignet ist, fallen fünf Kernaufgaben immer in Ihren Zuständigkeitsbereich:
  
- **Netzwerke und Konnektivität** – sicher, dass Netzwerkkapazität und Verfügbarkeit durch Firewalls, Proxyservern, Gateways und über WAN-Verbindungen Datenquellenanbieters führen Sie eine Bewertung Netzwerk oder indem mit einem Partner führen Sie die Bewertung.
    
- **Daten Governance &amp; rechteverwaltung** – Ihre sensiblen Daten klassifizieren und sicherstellen, dass es geschützt und überwacht, wo sie gespeichert ist, und zwar während der Übertragung.
    
- **Clientendpunkte** - herstellen, messen und Erzwingen von modernen Sicherheitsstandards auf Geräten, die Zugriff auf Ihre Daten und Objekte verwendet werden.
    
- **Konto &amp; Management zugreifen** – einrichten ein Profils für "normal" Kontoaktivitäten und ungewöhnliche Aktivitäten warnen.
    
- **Identität** – Verwenden Sie für alle Identitäten durch Hardware oder mehrstufige Authentifizierung (Multi-Factor Authentication, MFA) gesicherte Anmeldeinformationen. 
    
Zusätzlich zu den architekturbezogenen Aufgaben, die Sie für die lokale Umgebung ausführen, müssen Sie Folgendes tun:
  
- Planen und Entwerfen der Anforderungen für die Identitätsverwaltung, einschließlich der Integration lokaler Identitäten in Office 365
    
- Sicherstellen der Netzwerkkapazität und -verfügbarkeit
    
- Erwerben von SSL-Zertifikaten von Drittanbietern, um für Office 365-Dienstangebote Sicherheit auf Unternehmensniveau bereitzustellen
    
- Entscheiden, ob Sie die Verbindung mit Office 365 über IPv6 (Internetprotokoll, Version 6) herstellen möchten
    
- Bestimmen Sie, wie viel Integration mit lokalen und online Skype-Versionen für Unternehmen, Exchange und SharePoint erwünscht ist. 
    
- Bestimmen, welches Proxyservergerät für Anforderungen von Office 365 verwendet werden soll
    
Sie müssen auch ausführen führen Sie IT-Spezialisten Aufgaben zum Implementieren Ihrer Skype für Business-hybridumgebung:
  
- Stellen Sie sicher, dass Sie einen Microsoft Office 365-Mandanten mit Skype für Business Online aktiviert haben.
    
- Implementieren des Plans für die Identitätsverwaltung  
    
- Planen und Implementieren von internen und externen DNS-Einträgen und von DNS-Routing
    
- Konfigurieren Ihres Proxys oder Ihrer Firewall für die Office 365-Anforderungen im Hinblick auf IP-Adressen und URLs
    
- Verwalten von Benutzerkonten und Skype für Business Online-Einstellungen. 
    
- Konfigurieren des Proxyservergeräts (falls erforderlich)  
    
- Konfigurieren der Integration von Funktionen in lokale und Onlineversionen von Exchange Server und SharePoint
    
## <a name="for-more-information"></a>Weitere Informationen
<a name="BKMK_MoreInfo"> </a>

Weitere Informationen finden Sie in den folgenden Ressourcen:
  
- [Ressourcen zur Cloud-IT-Architektur von Microsoft](https://aka.ms/clouditarch)
    
- [Microsoft-Cloud-Identität für Enterprise-Architekten](https://docs.microsoft.com/en-us/office365/enterprise/microsoft-cloud-it-architecture-resources#identity)
    
- [Vorbereiten Ihrer Organisation für Office 365 Enterprise](https://aka.ms/O365EntPrep)
    
- [Planen der hybridkonnektivität zwischen Skype für Business Server und Skype Business Online oder Teams](plan-hybrid-connectivity.md)
    
- [Konfigurieren Sie hybridkonnektivität zwischen Skype für Business Server und Skype für Business Online](configure-hybrid-connectivity.md)
    
- [Telefonsystem in Office 365 (engl.)](../../sfbserver/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-your-phone-system-cloud-pbx-solution.md#BKMK_PBXOfferings)
    
- [Plan to integrate Skype for Business and Exchange](../../SfbServer/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)
    
Eine Posterversion dieses Themas können Sie hier herunterladen:
  
- [Architekturmodelle für Skype for Business (PDF-Version)](https://download.microsoft.com/download/7/7/4/7741262C-A60D-41F7-863B-99BF5964FBFE/Skype%20for%20Business%20Architectural%20Models.pdf)
    
- [Architekturmodelle für Skype for Business (Visio-Version)](https://download.microsoft.com/download/7/7/4/7741262C-A60D-41F7-863B-99BF5964FBFE/Skype%20for%20Business%20Architectural%20Models.vsd)
    

### <a name="placeholder-topic-for-hybrid-solutions"></a>PLATZHALTERTHEMA FÜR HYBRIDLÖSUNGEN 

IN BEARBEITUNG...


Möglicherweise kennen Sie auch den Begriff „Hybridtelefonie“. Damit sind lokale VoIP-Trunks gemeint, die Funktionen für in der Cloud verwaltete Benutzer bereitstellen. Hybridtelefonie ermöglicht die Migration zur Cloud, während die lokale VoIP-Konfiguration erhalten bleibt. Wenn Sie bereits über eine Skype for Business Server-Bereitstellung verfügen und Hybridtelefonie aktivieren möchten, müssen Sie zunächst eine Umgebung mit geteilter Domäne konfigurieren. 
  
Angenommen, Ihr Unternehmen verfügt über eine große Felds Mobil Organisation unterstützt werden, die erfordert minimale Nebenstellenanlage VoIP, aber umfassende Smartphone verwenden. Sie können diese Benutzer in die Cloud verschieben, um von den Vorteilen des von Microsoft angebotenen Telefonsystems in Office 365 (Cloud-PBX) zu profitieren. Wenn Ihr Unternehmen auch eine große lokale Callcenter, die als Teil Ihrer lokalen PBX erweitert, komplexer Kontakt Center Software erforderlich sind verfügt, können Sie diese Benutzer lokal zu lassen. Sowohl die online verwalteten als auch die lokal verwalteten Benutzer verfügen durch die lokale Bereitstellung über PSTN-Anbindung.
  
Das folgende Diagramm zeigt eine Skype for Business-Bereitstellung mit Hybridtelefonie:
  
![Skype for Business mit geteilter Domäne und Cloud-PBX](../../sfbserver/media/5e755772-269e-45ce-8b48-2e06ababfe6c.png)
  
Weitere Informationen zum Einrichten einer Hybrid-VoIP-Lösung mit Ihrer Skype für Business Server-Bereitstellung finden Sie unter [Planen von Telefonsystem in Office 365 mit lokalen PSTN-Konnektivität in Skype für Business Server](../../sfbserver/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity.md). 
  
Sie können auch konfigurieren, hybridbereitstellungen für die Integration in lokale Exchange und SharePoint oder mit Microsoft Office 365-Anwendungen, einschließlich Exchange Online und SharePoint Online. Außerdem können Sie eine Hybridtelefonielösung konfigurieren, für die keine vollständige Skype for Business Server-Bereitstellung mit Cloud Connector Edition erforderlich ist. Weitere Informationen zu allen Skype für hybridlösungen für geschäftliche und zum Planen Ihrer in der Cloud verschieben finden Sie unter [Skype für Business hybridlösungen](hybrid-solutions.md).


## <a name="exchange-co-existence"></a>Koexistenz mit Exchange
<a name="BKMK_Exchange"> </a>

Berücksichtigen Sie im Hinblick auf die Unterstützung von Koexistenz mit Exchange die folgenden Punkte:
  
- Bewährt hat sich das Postfach des Benutzers zu Exchange Online verschieben, vor dem Verschieben des Benutzers Skype für Unternehmen privat.
    
- Benutzer mit lokalen Exchange-Postfächern werden mit den folgenden Einschränkungen unterstützt:
    
  - Clientanmeldung: Die Benutzer müssen sich möglicherweise zweimal beim Skype for Business-Client anmelden.
    
  - Server Seite Unterhaltungen, Archivierung, Unified Contact Store, HighRes Foto erfordert Exchange 2013 oder höher, und Sie müssen die OAuth-Server zu-Server-Kommunikation aktivieren. Weitere Informationen finden Sie unter [Manage Server-zu-Server-Authentifizierung (OAuth) und partneranwendungen in Skype für Business Server 2015](https://technet.microsoft.com/en-us/library/jj204817.aspx).
    
Details zur Koexistenz mit Exchange Server, einschließlich Unterstützungskriterien und Einschränkungen in verschiedenen Kombinationen aus lokaler Bereitstellung und Onlinebereitstellung, finden Sie unter [Unterstützung von Features](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support) in [Plan to integrate Skype for Business and Exchange](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md).



**TERMINOLOGIE**

OU erhalten weitere Informationen zu Active Directory-Konfiguration in den Abschnitten, die folgen. Zuerst möchten wir Ihnen jedoch einen Überblick über die Begriffe und Akronyme geben, die in den folgenden Diagrammen und in vielen der Themen zur hybriden Konnektivität verwendet werden:
  
- PSTN – Public Switched Telephone Network (Telefonfestnetz)
    
- PBX – Private Branch Exchange (Nebenstellenanlage)
    
- Telefonsystem – das von Microsoft angebotene Cloud-PBX-Telefonsystem
    
- Trunk - Telefonie-Zeile, die an das Telefonfestnetz Nebenstellenanlagen verbindet – möglicherweise ein Trunk Session Initiation Protocol (SIP) verwenden – A Voice over Internet Protocol (VoIP) – oder die ältere Time Division Multiplexing (TDM)-Technologie 
    
- SBC – Session Border Controller – ein Gerät, das als Firewall und Router in Telefonienetzwerken dient. Ein SBC bietet zum Beispiel Sicherheit, Konnektivität, Interoperabilität und Dienstqualität (Quality of Service, QoS). 
    
- PSTN-Gateway – ein Gerät, das in Telefonienetzwerken als Router dient und größtenteils die gleichen Funktionen wie ein SBC bietet (mit Ausnahme von Sicherheit und NAT-Traversal)
    
Das folgende Diagramm zeigt einen Skype Business "Split-Domäne" hybridkonfiguration. Die Benutzer A und B werden online verwaltet, können aber von lokalen Benutzern ermittelt werden. Die Benutzer C und D werden lokal verwaltet, können aber von Onlinebenutzern ermittelt werden.
  

