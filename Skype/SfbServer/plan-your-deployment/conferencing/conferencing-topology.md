---
title: Planen der Konferenz Topologie für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7392dfa7-791a-4723-88ff-0ef8a9ef11c8
description: 'Zusammenfassung: in diesem Thema erfahren Sie mehr über die Planung Ihrer Konferenz Topologie in Skype for Business Server.'
ms.openlocfilehash: 68ee859979deb7d977ee546e711474d0b6ba06e5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030779"
---
# <a name="plan-your-conferencing-topology-for-skype-for-business-server"></a>Planen der Konferenz Topologie für Skype for Business Server
 
**Zusammenfassung:** In diesem Thema erfahren Sie mehr über die Planung Ihrer Konferenz Topologie in Skype for Business Server.
  
In diesem Thema werden die Grundlagen der Topologie für Konferenzen in Skype for Business Server beschrieben:
  
- Unterstützte Topologien
    
- Überlegungen zu Einwahlkonferenzen
    
- Überlegungen zu Webkonferenzen
    
- Anforderungen für große Besprechungen
    
Weitere Informationen zu Hardware-und Softwareanforderungen finden Sie unter [Hardware-und Softwareanforderungen für Konferenzen in Skype for Business Server](hardware-and-software-requirements.md).
  
## <a name="supported-topologies"></a>Unterstützte Topologien

In Skype for Business Server ist der Server, auf dem die Konferenzdienste ausgeführt werden, immer mit den Front-End-Servern oder Standard Edition-Servern verbunden. Wenn Sie Skype for Business Server bereitstellen, werden Chat Konferenzfunktionen automatisch bereitgestellt. Sie können angeben, ob Sie Webparts, Audio-und Video (A/V) und Einwahlkonferenzen mithilfe des Topologie-Generators bereitstellen möchten. Sie können auch den Topologie-Generator verwenden, um einer vorhandenen Bereitstellung Konferenzen hinzuzufügen. Ausführliche Informationen zu Topologie-Grundlagen und Zusammenstellungs Szenarien finden Sie unter [Topologie Basics for Skype for Business Server](../../plan-your-deployment/topology-basics/topology-basics.md).
  
Sie können Konferenzen in den folgenden Topologien und Konfigurationen bereitstellen:
  
- Skype for Business Server Standard Edition
    
- Skype for Business Server Enterprise Edition
    
- Mit oder ohne Enterprise-VoIP
    
## <a name="dial-in-conferencing-considerations"></a>Überlegungen zu Einwahlkonferenzen

Wenn Sie Einwahlkonferenzen bereitstellen, müssen Sie Folgendes berücksichtigen:
  
- Einwahlkonferenzen erfordern eine Vermittlungsserver zum Übersetzen von Signalen (und Medien in einigen Konfigurationen) zwischen Skype for Business Server und dem PSTN-Gateway sowie ein PSTN-Gateway zum Übersetzen von Signal-und Mediendaten zwischen der Vermittlungsserver und dem PSTN-Gateway. .
    
   Bevor Sie Einwahlkonferenzen konfigurieren können, müssen Sie entweder Enterprise-VoIP oder eine Vermittlungsserver und mindestens eine der folgenden bereitstellen:
    
  - PSTN-Gateway
    
  - IP-Nebenstellenanlage
    
  - Session Border Controller (SBC) (für einen Internet Telefonie-Dienstanbieter, zu dem Sie eine Verbindung herstellen, indem Sie einen SIP-Trunk konfigurieren)
    
- Sie können die Anwendungsdienst, Konferenzzentrale und Konferenzankündigungsanwendung an einem zentralen Standort bereitstellen, jedoch nicht an einem Zweigstellenstandort.
    
- Sie müssen Einwahlkonferenzen in jedem Pool bereitstellen, in dem Sie Skype for Business Server Konferenzen bereitstellen. Sie müssen in keinem Pool Zugriffsnummern zuweisen, aber Sie müssen das Feature für Einwahlkonferenzen in jedem Pool bereitstellen. Diese Anforderung unterstützt das Feature für aufgezeichnete Namen, wenn ein Benutzer eine Zugriffsnummer aus einem Pool aufruft, um an einer Skype for Business Server Konferenz in einem anderen Pool teilzunehmen. 
    
Weitere Informationen finden Sie unter [Planen von Einwahlkonferenzen in Skype for Business Server](dial-in-conferencing.md).
  
## <a name="web-conferencing-considerations"></a>Überlegungen zu Webkonferenzen

Für Webkonferenzen müssen folgende Anforderungen gelten: 
  
- Zugriff auf den Dateispeicher, der zum Speichern von Webkonferenzinhalten verwendet wird.
    
- Integration mit Office-webapps Server/Office Online-Server, der erforderlich ist, um PowerPoint-Dateien während einer Konferenz freizugeben.
    
> [!NOTE]
> Die neueste Iteration von Office-webapps Server wird Office Online Server benannt, der von Skype for Business Server unterstützt wird. Weitere Informationen finden Sie in der [Dokumentation zum Office Online Server](https://technet.microsoft.com/library/jj219456%28v=office.16%29.aspx). 
  
Skype for Business Server bietet die folgenden Möglichkeiten zum Konfigurieren von Office-webapps Server/Office Online-Server. Je nach Ihren Anforderungen können Sie Folgendes tun:
  
- **Installieren Sie sowohl Skype for Business Server als auch Office-webapps Server/Office Online-Server lokal hinter der Firewall Ihrer Organisation und in derselben Netzwerkzone.** Mit dieser Topologie wird der externe Zugriff auf Office-webapps Server/Office Online-Server über den Reverseproxy bereitgestellt. Idealerweise sollten Sie Office-webapps Server/Office Online-Server in derselben Netzwerkzone wie Skype for Business Server installieren.
    
    Externe Skype for Business Clients können eine Verbindung mit Skype for Business Server und zu Office Web Apps Server/Office Online Server herstellen, indem Sie einen Reverseproxy verwenden, bei dem es sich um einen Server handelt, der Anforderungen aus dem Internet aufnimmt und an das interne Netzwerk weiterleitet. (Interne Clients müssen nicht den Reverseproxy verwenden, da Sie direkt eine Verbindung mit Office-webapps Server/Office Online Server herstellen können.) Diese Topologie eignet sich am besten, wenn Sie eine dedizierte Office-webapps Server/Office Online Serverfarm verwenden möchten, die nur von Skype for Business Server verwendet wird.
    
- **Verwenden Sie einen extern bereitgestellten Office webapps Server/Office Online-Server.** In dieser Topologie wird Skype for Business Server lokal bereitgestellt und verwendet einen Office-webapps Server/Office Online-Server, der außerhalb der Skype for Business Server Netzwerkzone bereitgestellt wird. Dies kann vorkommen, wenn Office-webapps Server/Office Online-Server für mehrere Anwendungen in der Corporation freigegeben und in einem Netzwerk bereitgestellt wird, das Skype for Business Server für die Verwendung der externen Schnittstelle von Office-webapps Server/Office Online Server und umgekehrt benötigt.
    
    Sie müssen keinen Reverse-Proxy Server installieren; Stattdessen werden alle Anforderungen vom Office-webapps Server/Office Online-Server an Skype for Business Server über Ihren Edgeserver weitergeleitet. Sowohl die internen als auch die externen Skype for Business Clients stellen mithilfe der externen URL eine Verbindung zu Office-webapps Server/Office Online Server her.
    
    Wenn der Office Web Apps Server/Office Online-Server außerhalb ihrer internen Firewall bereitgestellt wird, wählen Sie die Option **Office Web Apps Server wird in einem externen Netzwerk** (d. Umkreis/Internet) im Topologie-Generator bereitgestellt.
    
Weitere Informationen finden Sie unter [configure Integration with Office Internet apps Server in Skype for Business Server](../../deploy/deploy-conferencing/office-web-app-server.md). 
  
Unabhängig von der ausgewählten Topologie ist es wichtig, dass die richtigen Firewall-Ports geöffnet werden. Sie müssen sicherstellen, dass DNS-Namen, IP-Adressen und Ports nicht von Firewalls auf dem Office-webapps Server/Office Online-Server, dem Lastenausgleichsmodul oder Skype for Business Server blockiert werden.
  
> [!NOTE]
> Eine weitere Option für die Bereitstellung von externem Zugriff auf Office-webapps Server/Office Online Server besteht darin, den Server im Umkreisnetzwerk bereitzustellen. Wenn Sie sich dafür entscheiden, müssen Sie Bedenken, dass der Server Computer für Office-webapps Server/Office Online Server Setup Mitglied Ihrer Active Directory Domäne sein muss. Wenn Ihre Netzwerkrichtlinie Computer im Umkreisnetzwerk nicht Active Directory Domänenmitgliedern zulässt, wird empfohlen, dass Sie Office-webapps Server/Office Online-Server nicht im Umkreisnetzwerk installieren. Stattdessen sollten Sie Office-webapps Server/Office Online-Server im internen Netzwerk installieren und externen Benutzern Zugriff über den Reverseproxy ermöglichen. 
  
## <a name="topology-requirements-for-large-meetings"></a>Topologie-Anforderungen für große Besprechungen

Eine einzelne große Besprechung erfordert mindestens eine Front-End-Server und einen Back-End-Server. Um eine hohe Verfügbarkeit zu gewährleisten, empfehlen wir jedoch einen zwei Front-End-Server Pool mit gespiegelten Back-End-Servern, wie im folgenden Diagramm dargestellt:
  
**Große Besprechungs Topologie**

![Große Besprechungs Topologie](../../media/06858900-a262-4a47-96d0-51abd6827064.png)
  
Der Benutzer, der die großen Besprechungen hostet, muss das Benutzerkonto in Front-End-Pool verwaltet haben. Es wird jedoch nicht empfohlen, dass andere Benutzerkonten in diesem Pool gehostet werden. Er sollte nur für diese großen Besprechungen verwendet werden. In diesem Pool sollte ein spezielles Benutzerkonto erstellt werden, das nur zur Durchführung großer Besprechungen verwendet wird. Da die Einstellung für große Besprechungen für die Leistung optimiert ist, kann die Verwendung als normaler Benutzer Probleme verursachen, beispielsweise die Unfähigkeit, eine P2P-Sitzung zu einer Besprechung zu heraufstufen, wenn ein PSTN-Endpunkt beteiligt ist.
  
Bei der Verwaltung eines Pools mit genau zwei Front-End-Servern sind spezielle Überlegungen erforderlich. Weitere Informationen finden Sie unter [Grundlagen der Topologie für Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md) und Referenz Topologien [für Skype for Business Server 2015](../../plan-your-deployment/topology-basics/reference-topologies.md).
  
Wenn Sie optional Notfall Wiederherstellungs Sicherungen und Failover für den für große Besprechungen verwendeten Pool bereitstellen möchten, können Sie diese mit einem ähnlich eingerichteten dedizierten Pool in einem anderen Rechenzentrum koppeln. Ausführliche Informationen finden Sie unter [Plan for High Availability and Disaster Recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
Zusätzliche Notizen zur Topologie:
  
- Eine Dateifreigabe ist zum Speichern der Archivierungsdateien erforderlich, wenn der Besprechungsinhalt gespeichert wird und wenn Archivierungsserver bereitgestellt und aktiviert ist. Die Dateifreigabe kann dem Pool zugeordnet werden oder dieselbe Dateifreigabe sein, die von einem anderen Pool an diesem Standort verwendet wurde, an dem der Pool bereitgestellt wurde. Ausführliche Informationen zum Konfigurieren der Dateifreigabe finden Sie unter [Erstellen einer Dateifreigabe in Skype for Business Server 2015](../../deploy/install/create-a-file-share.md).
    
- Für die Aktivierung der PowerPoint-Präsentations Funktionalität in großen Besprechungen ist ein Office-webapps Server/Office Online Server erforderlich. Der Office Web Apps Server/Office Online-Server kann für den großen Besprechungs Pool reserviert werden, oder es kann sich um denselben Office Web Apps Server/Office Online-Server handeln, der von anderen Pools an dem Standort verwendet wird, an dem der dedizierte Pool bereitgestellt wird. Weitere Informationen finden Sie unter [configure Integration with Office Internet apps Server in Skype for Business Server](../../deploy/deploy-conferencing/office-web-app-server.md). 
    
- Für den Lastenausgleich der Front-End-Server ist ein Hardwarelastenausgleich für den HTTP-Datenverkehr erforderlich (beispielsweise das Herunterladen von Besprechungsinhalten). DNS-Lastenausgleich wird für den SIP-Datenverkehr empfohlen. Ausführliche Informationen finden Sie unter [Lastenausgleichsanforderungen für Skype for Business](../../plan-your-deployment/network-requirements/load-balancing.md). 
    
- Wenn Sie Monitoring Server für den dedizierten großen Besprechungs Pool verwenden möchten, empfehlen wir die Verwendung der Monitoring Server und der zugehörigen Datenbank, die für alle Front-End-Server Pools in Ihrer Skype for Business Server-Bereitstellung freigegeben sind. Weitere Informationen finden Sie unter [Plan for Monitoring in Skype for Business Server](../../plan-your-deployment/monitoring.md).
    

