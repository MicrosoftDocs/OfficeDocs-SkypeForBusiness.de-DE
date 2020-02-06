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
description: 'Zusammenfassung: Lesen Sie dieses Thema, um Informationen zum Planen Ihrer Konferenz Topologie in Skype for Business Server zu erhalten.'
ms.openlocfilehash: 1b9d9024d90b4bd847c763747dad7a5f96616aa3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816014"
---
# <a name="plan-your-conferencing-topology-for-skype-for-business-server"></a>Planen der Konferenz Topologie für Skype for Business Server
 
**Zusammenfassung:** In diesem Thema erfahren Sie, wie Sie Ihre Konferenz Topologie in Skype for Business Server planen.
  
In diesem Thema werden die Grundlagen der Topologie für Konferenzen in Skype for Business Server beschrieben:
  
- Unterstützte Topologien
    
- Überlegungen hinsichtlich Einwahlkonferenzen
    
- Überlegungen hinsichtlich Webkonferenzen
    
- Systemvoraussetzungen für große Besprechungen
    
Weitere Informationen zu den Hardware-und Softwareanforderungen finden Sie unter [Hardware-und Softwareanforderungen für Konferenzen in Skype for Business Server](hardware-and-software-requirements.md).
  
## <a name="supported-topologies"></a>Unterstützte Topologien

In Skype for Business Server ist der Server, auf dem Konferenzdienste ausgeführt werden, immer mit den Front-End-Servern oder Standard Edition-Servern verbunden. Bei der Bereitstellung von Skype for Business Server werden Sofortnachrichten-Konferenzfunktionen automatisch bereitgestellt. Über den Topologie-Generator können Sie dann entscheiden, ob Sie Web-, A/V- und Einwahlkonferenzen bereitstellen möchten. Den Topologie-Generator können Sie außerdem nutzen, um die Konferenzfunktion zu einer vorhandenen Bereitstellung hinzuzufügen. Ausführliche Informationen zu Topologie-Grundlagen und Zusammenarbeitsszenarien finden Sie unter [Topologie-Grundlagen für Skype for Business Server](../../plan-your-deployment/topology-basics/topology-basics.md).
  
Sie können Konferenzfunktionen in folgenden Topologien und Konfigurationen bereitstellen:
  
- Skype for Business Server Standard Edition
    
- Skype for Business Server Enterprise Edition
    
- Mit oder ohne Enterprise Voice
    
## <a name="dial-in-conferencing-considerations"></a>Überlegungen hinsichtlich Einwahlkonferenzen

Bei der Bereitstellung von Einwahlkonferenzen müssen Sie Folgendes berücksichtigen:
  
- Für Einwahlkonferenzen ist ein Vermittlungs Server erforderlich, um Signalisierungen (und Medien in einigen Konfigurationen) zwischen Skype for Business Server und dem PSTN-Gateway zu übersetzen, und ein PSTN-Gateway, um Signalisierungs-und Medien Verbindungen zwischen dem Vermittlungsserver und dem PSTN-Gateway zu übersetzen. .
    
   Bevor Sie Einwahlkonferenzen konfigurieren können, müssen Sie entweder Enterprise Voice oder einen Vermittlungsserver und mindestens eine der folgenden Komponenten bereitstellen:
    
  - PSTN-Gateway
    
  - IP-Nebenstellenanlage
    
  - Session Border Controller (SBC) (für einen Anbieter von Internettelefoniediensten, mit dem durch Konfigurieren eines SIP-Trunks eine Verbindung hergestellt wird)
    
- Sie können den Application Service, die Konferenzzentrale und die Konferenzankündigungsanwendung an einem zentralen Standort bereitstellen, aber nicht an einem Zweigstellenstandort.
    
- Sie müssen in jedem Pool, in dem Sie Skype for Business Server Conferencing bereitstellen, Einwahlkonferenzen bereitstellen. Sie müssen nicht in jedem Pool Zugriffsnummern zuweisen, aber Sie müssen die Funktion für Einwahlkonferenzen in jedem Pool bereitstellen. Diese Anforderung unterstützt das Feature "aufgezeichnete Namen", wenn ein Benutzer eine Zugriffsnummer aus einem Pool anruft, um an einer Skype for Business Server-Konferenz in einem anderen Pool teilzunehmen. 
    
Weitere Informationen finden Sie unter [Planen von Einwahlkonferenzen in Skype for Business Server](dial-in-conferencing.md).
  
## <a name="web-conferencing-considerations"></a>Überlegungen hinsichtlich Webkonferenzen

Für die Webkonferenzfunktion sind folgende Komponenten erforderlich: 
  
- Zugriff auf den Dateispeicher, der zum Speichern von Webkonferenzinhalten verwendet wird.
    
- Integration in den Office Web App-/Office Online-Server. Dies ist für die Freigabe von PowerPoint-Dateien während einer Konferenz erforderlich.
    
> [!NOTE]
> Die neueste Iteration von Office Web Apps Server heißt Office Online Server, das von Skype for Business Server unterstützt wird. Weitere Informationen finden Sie in der [Office Online Server-Dokumentation](https://technet.microsoft.com/en-us/library/jj219456%28v=office.16%29.aspx). 
  
Skype for Business Server bietet die folgenden Möglichkeiten zum Konfigurieren von Office Web Apps Server/Office Online Server. Je nach Ihren Anforderungen können Sie:
  
- **Installieren Sie Skype for Business Server und Office Web Apps Server/Office Online Server lokal hinter der Firewall Ihrer Organisation und in derselben Netzwerkzone.** Bei dieser Topologie wird externer Zugriff auf Office Web Apps Server/Office Online Server über den Reverse Proxy Server bereitgestellt. Im Idealfall sollten Sie Office Web Apps Server/Office Online Server in derselben Netzwerkzone wie Skype for Business Server installieren.
    
    Externe Skype for Business-Clients können eine Verbindung mit Skype for Business Server und Office Web Apps Server/Office Online Server herstellen, indem Sie einen Reverseproxy verwenden, bei dem es sich um einen Server handelt, der Anforderungen aus dem Internet annimmt und diese an das interne Netzwerk weiterleitet. (Interne Clients müssen den Reverse Proxy Server nicht verwenden, da Sie eine direkte Verbindung mit Office Web Apps Server/Office Online Server herstellen können.) Diese Topologie funktioniert am besten, wenn Sie eine dedizierte Office Web Apps-Server/Office Online-Serverfarm verwenden möchten, die nur von Skype for Business Server verwendet wird.
    
- **Verwenden Sie einen extern bereitgestellten Office Web Apps-Server/Office Online-Server.** In dieser Topologie wird Skype for Business Server lokal bereitgestellt und verwendet einen Office Web Apps-Server/Office Online-Server, der außerhalb der Skype for Business Server-Netzwerkzone bereitgestellt wird. Dies kann vorkommen, wenn Office Web Apps Server/Office Online Server für mehrere Anwendungen im Unternehmen freigegeben wurde und in einem Netzwerk bereitgestellt wird, das von Skype for Business Server zur Verwendung der externen Schnittstelle von Office Web Apps Server/Office Online Server und umgekehrt benötigt wird.
    
    Sie müssen keinen Reverse-Proxy-Server installieren; Stattdessen werden alle Anforderungen vom Office Web Apps-Server/Office Online-Server an den Skype for Business-Server über Ihren Edgeserver weitergeleitet. Sowohl Ihre internen als auch Ihre externen Skype for Business-Clients stellen mithilfe der externen URL eine Verbindung mit Office Web Apps Server/Office Online Server her.
    
    Wenn der Office Web App-/Office Online-Server außerhalb Ihrer internen Firewall bereitgestellt ist, aktivieren Sie im Topologie-Generator die Option **Office Web App-/Office Online-Server ist in einem externen Netzwerk (d. h. Umkreis/Internet) bereitgestellt**.
    
Weitere Informationen finden Sie unter [Konfigurieren der Integration in Office Web Apps Server in Skype for Business Server](../../deploy/deploy-conferencing/office-web-app-server.md). 
  
Unabhängig von der ausgewählten Topologie ist es entscheidend, dass die korrekten Firewallports geöffnet sind. Sie müssen sicherstellen, dass DNS-Namen, IP-Adressen und Ports nicht von Firewalls auf dem Office Web Apps-Server/Office Online-Server, dem Lastenausgleichsmodul oder Skype for Business Server blockiert werden.
  
> [!NOTE]
> Eine weitere Option zum Bereitstellen von externem Zugriff auf den Office Web App-/Office Online-Server besteht darin, den Server im Umkreisnetzwerk bereitzustellen. Wenn Sie sich dafür entscheiden, denken Sie daran, dass für das Setup des Office Web App-/Office Online-Servers der Servercomputer ein Mitglied der Active Directory-Domäne sein muss. Es wird davon abgeraten, den Office Web App-/Office Online-Server im Umkreisnetzwerk zu installieren, es sei denn, Ihre Netzwerkrichtlinie lässt zu, dass Computer im Umkreisnetzwerk Active Directory-Domänenmitglieder sind. Stattdessen sollten Sie den Office Web Apps/Office Online-Server im internen Netzwerk installieren und externen Benutzern Zugriff über Ihren Reverseproxyserver ermöglichen.  
  
## <a name="topology-requirements-for-large-meetings"></a>Anforderungen an die Topologien von großen Besprechungen

Bei einer einzigen großen Besprechung sind mindestens ein Front-End und ein Back-End-Server erforderlich. Damit jedoch eine hohe Verfügbarkeit geboten werden kann, wird, wie in der folgenden Übersicht dargestellt, ein Front-End-Server-Pool mit gespiegelten Back-End-Servern empfohlen:
  
**Topologie für eine große Besprechung**

![Topologie für eine große Besprechung](../../media/06858900-a262-4a47-96d0-51abd6827064.png)
  
Der Benutzer, der die umfangreichen Besprechungen hostet, muss sein Benutzerkonto im Front-End-Pool verwaltet haben. Es wird jedoch nicht empfohlen, andere Benutzerkonten in diesem Pool zu hosten. Verwenden Sie Sie stattdessen nur für die umfangreichen Besprechungen. Die bewährte Methode besteht darin, ein spezielles Benutzerkonto in diesem Pool zu erstellen, das nur zum Hosten großer Besprechungen verwendet wird. Da die große Besprechungs Einstellung für die Leistung optimiert ist, kann die Verwendung als normaler Benutzer Probleme haben, beispielsweise die Unfähigkeit, eine P2P-Sitzung zu einer Besprechung zu bewerben, wenn ein PSTN-Endpunkt involviert ist.
  
Bei der Verwaltung eines Pools mit genau zwei Front-End-Servern sind spezielle Überlegungen erforderlich. Weitere Informationen finden Sie unter [Topology Basics for Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md) und [Reference topologies for Skype for Business Server 2015](../../plan-your-deployment/topology-basics/reference-topologies.md).
  
Wenn Sie zusätzlich optional eine Sicherung zur Notfallwiederherstellung und ein Failover für den für große Besprechungen verwendeten Pool bereitstellen möchten, können Sie ihn auch gemeinsam mit einem ähnlich eingerichteten dedizierten Pool in einem anderen Rechenzentrum verwenden. Ausführliche Informationen finden Sie unter [Planen von Höchstverfügbarkeit und Disaster Recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
Zusätzliche Notizen zur Topologie:
  
- Eine Dateifreigabe ist erforderlich, um Besprechungsinhalte zu speichern und um, wenn ein Archivierungsserver bereitgestellt und aktiviert wurde, die Archivierungsdateien zu speichern. Die Dateifreigabe kann dem Pool zugeordnet werden oder dieselbe Dateifreigabe sein, die von einem anderen Pool an diesem Standort verwendet wurde, an dem der Pool bereitgestellt wurde. Details zum Konfigurieren der Dateifreigabe finden Sie unter [Erstellen einer Dateifreigabe in Skype for Business Server 2015](../../deploy/install/create-a-file-share.md).
    
- Zur Aktivierung der PowerPoint-Präsentationsfunktion in großen Besprechungen ist ein Office Web App-/Office Online-Server erforderlich. Der Office Web App-/Office Online-Server kann einem großen Besprechungspool zugeordnet werden oder es kann auch derselbe Office Web App-/Office Online-Server sein, der von anderen Pools an diesem Standort verwendet wurde, an dem der dedizierte Pool bereitgestellt wurde. Weitere Informationen finden Sie unter [Konfigurieren der Integration in Office Web Apps Server in Skype for Business Server](../../deploy/deploy-conferencing/office-web-app-server.md). 
    
- Bei einem Lastenausgleich für die Front-End-Server ist ein Hardwaregerät zum Lastenausgleich für den HTTP-Datenverkehr (z. B. beim Herunterladen von Besprechungsinhalten) erforderlich. DNS-Lastenausgleich wird für den SIP-Datenverkehr empfohlen. Ausführliche Informationen finden Sie unter [Load balancing requirements for Skype for Business](../../plan-your-deployment/network-requirements/load-balancing.md). 
    
- Wenn Sie den Monitoring Server für den dedizierten groß Besprechungs Pool verwenden möchten, empfehlen wir die Verwendung des Überwachungsservers und der zugehörigen Datenbank, die für alle Front-End-Server Pools in Ihrer Skype for Business Server-Bereitstellung freigegeben sind. Weitere Informationen finden Sie unter [Planen der Überwachung in Skype for Business Server](../../plan-your-deployment/monitoring.md).
    

