---
title: Planen von Skype für Business Server Ihrer konferenztopologie
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7392dfa7-791a-4723-88ff-0ef8a9ef11c8
description: 'Zusammenfassung: Lesen Sie dieses Thema aus, um Informationen zum Planen Ihrer Topologie Conferencing in Skype für Business Server.'
ms.openlocfilehash: e6269986bd5c011f43b5f6374053441e3aca54ec
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214474"
---
# <a name="plan-your-conferencing-topology-for-skype-for-business-server"></a>Planen von Skype für Business Server Ihrer konferenztopologie
 
**Zusammenfassung:** Lesen Sie dieses Thema aus, um Informationen zum Planen Ihrer Topologie Conferencing in Skype für Business Server.
  
In diesem Thema werden die topologiegrundlagen für Konferenzen in Skype für Business Server:
  
- Unterstützte Topologien
    
- Überlegungen hinsichtlich Einwahlkonferenzen
    
- Überlegungen hinsichtlich Webkonferenzen
    
- Systemvoraussetzungen für große Besprechungen
    
Weitere Informationen zu Hardware-und softwareanforderungen finden Sie unter [Hardware und Software-Anforderungen für Konferenzen in Skype für Business Server](hardware-and-software-requirements.md).
  
## <a name="supported-topologies"></a>Unterstützte Topologien

In Skype für Business Server wird der Server mit Konferenzdienste immer mit den Front-End-Server oder Standard Edition-Servern kombiniert. Wenn Sie Skype für Business Server bereitstellen, werden automatisch Instant Messaging-Konferenzfunktionen bereitgestellt. Über den Topologie-Generator können Sie dann entscheiden, ob Sie Web-, A/V- und Einwahlkonferenzen bereitstellen möchten. Den Topologie-Generator können Sie außerdem nutzen, um die Konferenzfunktion zu einer vorhandenen Bereitstellung hinzuzufügen. Ausführliche Informationen zu topologiegrundlagen und Kollokation Szenarien finden Sie unter [Grundlagen der Topologie Skype für Business Server](../../plan-your-deployment/topology-basics/topology-basics.md).
  
Sie können Konferenzfunktionen in folgenden Topologien und Konfigurationen bereitstellen:
  
- Skype für Business Server Standard Edition
    
- Skype für Business Server Enterprise Edition
    
- Mit oder ohne Enterprise Voice
    
## <a name="dial-in-conferencing-considerations"></a>Überlegungen hinsichtlich Einwahlkonferenzen

Bei der Bereitstellung von Einwahlkonferenzen müssen Sie Folgendes berücksichtigen:
  
- Einwahlkonferenzen erfordert einen Vermittlungsserver zu übersetzen Signale (und Medien in einigen Konfigurationen) zwischen Skype für Business Server und dem PSTN-Gateway und ein PSTN-Gateway Signale und Medien zwischen dem Vermittlungsserver und PSTN-Gateway übersetzen .
    
   Bevor Sie Einwahlkonferenzen konfigurieren können, müssen Sie entweder Enterprise Voice oder einen Vermittlungsserver und mindestens eine der folgenden Komponenten bereitstellen:
    
  - PSTN-Gateway
    
  - IP-Nebenstellenanlage
    
  - Session Border Controller (SBC) (für einen Anbieter von Internettelefoniediensten, mit dem durch Konfigurieren eines SIP-Trunks eine Verbindung hergestellt wird)
    
- Sie können den Application Service, die Konferenzzentrale und die Konferenzankündigungsanwendung an einem zentralen Standort bereitstellen, aber nicht an einem Zweigstellenstandort.
    
- Sie müssen einwahlkonferenzen in jedem Pool bereitstellen, auf dem Sie Skype für Business Server Konferenzen bereitstellen. Sie müssen nicht in jedem Pool Zugriffsnummern zuweisen, aber Sie müssen die Funktion für Einwahlkonferenzen in jedem Pool bereitstellen. Diese Anforderung unterstützt die Aufzeichnung Ihres Namens-Funktion, wenn ein Benutzer von einem Pool einen Skype für Business Server-Konferenz in einen anderen Pool Teilnahme an eine Zugriffsnummer aufruft. 
    
Weitere Informationen finden Sie unter [Planen von einwahlkonferenzen in Skype für Business Server](dial-in-conferencing.md).
  
## <a name="web-conferencing-considerations"></a>Überlegungen hinsichtlich Webkonferenzen

Für die Webkonferenzfunktion sind folgende Komponenten erforderlich: 
  
- Zugriff auf den Dateispeicher, der zum Speichern von Webkonferenzinhalten verwendet wird.
    
- Integration in den Office Web App-/Office Online-Server. Dies ist für die Freigabe von PowerPoint-Dateien während einer Konferenz erforderlich.
    
> [!NOTE]
> Die neueste Iteration des Office Web Apps Server heißt Office Online-Server, die von Skype für Business Server unterstützt wird. Weitere Informationen finden Sie in der [Dokumentation zur Office Online-Server](https://technet.microsoft.com/en-us/library/jj219456%28v=office.16%29.aspx). 
  
Skype für Business Server bietet die folgenden Methoden zum Konfigurieren von Office Web Apps Server/Office Online Server. Abhängig von Ihren Anforderungen können Sie die folgenden Schritte ausführen:
  
- **Installieren Sie beide Skype für Business Server und Office Web Apps Server/Office Online Server lokal hinter der Firewall Ihrer Organisation, und klicken Sie in der gleichen Netzwerkzone.** With this topology, external access to Office Web Apps Server/Office Online Server will be provided through your reverse proxy server. Idealerweise sollten Sie Office Web Apps Server/Office Online Server in der gleichen Netzwerkzone als Skype für Business Server installieren.
    
    Externe Skype für Business-Clients kann Skype für Business Server und Office Web Apps Server/Office Online Server verbinden, mithilfe eines Reverseproxyservers, d. h. ein Server, der Anfragen aus dem Internet annimmt und an das interne Netzwerk weiterleitet. (Interne Clients führen Sie den Reverseproxyserver verwendet werden, da sie direkt mit Office Web Apps Server/Office Online Server verbinden können nicht erforderlich.) Diese Topologie funktioniert am besten, wenn Sie möchten eine dedizierte Office Web Apps Server/Office Online Server-Farm verwenden, die nur von Skype für Business Server verwendet wird.
    
- **Verwenden eines extern bereitgestellten Office Web Apps Server/Office Online Server an.** In dieser Topologie Skype für Business Server lokal bereitgestellt ist, und verwendet einen Office Web Apps Server/Office Online Server, die außerhalb der Skype für Netzwerkzone Business Server bereitgestellt wird. Dies kann vorkommen, wenn Office Web Apps Server/Office Online Server im Unternehmen anwendungsübergreifende freigegeben ist und in einem Netzwerk, dass Skype Business Server verwenden die externe Schnittstelle des Office Web Apps Server/Office Online Server bereitgestellt wird und umgekehrt.
    
    Sie müssen nicht reverse-Proxyserver zu installieren. In diesem Fall werden alle Anfragen von Office Web Apps Server/Office Online Server an Skype für Business Server über den Edge-Server weitergeleitet. Internen und Ihre externe Skype für Business Clients Verbinden mit Office Web Apps Server/Office Online Server über die externe URL.
    
    Wenn der Office Web App-/Office Online-Server außerhalb Ihrer internen Firewall bereitgestellt ist, aktivieren Sie im Topologie-Generator die Option **Office Web App-/Office Online-Server ist in einem externen Netzwerk (d. h. Umkreis/Internet) bereitgestellt**.
    
Weitere Informationen finden Sie unter [Konfigurieren der Integration mit Office Web Apps Server in Skype für Business Server](../../deploy/deploy-conferencing/office-web-app-server.md). 
  
Unabhängig von der ausgewählten Topologie ist es entscheidend, dass die korrekten Firewallports geöffnet sind. Sie müssen sicherstellen, dass DNS-Namen, IP-Adressen und Ports nicht durch Firewalls für Office Web Apps Server/Office Online Server, das System zum Lastenausgleich oder Skype für Business Server blockiert werden.
  
> [!NOTE]
> Eine weitere Option zum Bereitstellen von externem Zugriff auf den Office Web App-/Office Online-Server besteht darin, den Server im Umkreisnetzwerk bereitzustellen. Wenn Sie sich dafür entscheiden, denken Sie daran, dass für das Setup des Office Web App-/Office Online-Servers der Servercomputer ein Mitglied der Active Directory-Domäne sein muss. Es wird davon abgeraten, den Office Web App-/Office Online-Server im Umkreisnetzwerk zu installieren, es sei denn, Ihre Netzwerkrichtlinie lässt zu, dass Computer im Umkreisnetzwerk Active Directory-Domänenmitglieder sind. Stattdessen sollten Sie den Office Web Apps/Office Online-Server im internen Netzwerk installieren und externen Benutzern Zugriff über Ihren Reverseproxyserver ermöglichen.  
  
## <a name="topology-requirements-for-large-meetings"></a>Anforderungen an die Topologien von großen Besprechungen

Bei einer einzigen großen Besprechung sind mindestens ein Front-End und ein Back-End-Server erforderlich. Damit jedoch eine hohe Verfügbarkeit geboten werden kann, wird, wie in der folgenden Übersicht dargestellt, ein Front-End-Server-Pool mit gespiegelten Back-End-Servern empfohlen:
  
**Topologie für eine große Besprechung**

![Topologie für eine große Besprechung](../../media/06858900-a262-4a47-96d0-51abd6827064.png)
  
Der Benutzer, die großen Besprechungen hostet, benötigen ihre Benutzer Konto verwaltet in Front-End-Pool. Jedoch empfohlen nicht, dass Sie anderen Benutzerkonten in diesem Pool hosten. Verwenden Sie es stattdessen nur für großen Besprechungen. Bewährt hat, erstellen Sie ein besonderes Benutzerkonto in diesem Pool nur für große Besprechungen Host verwendet werden. Da die große Besprechung-Einstellung für die Leistung optimiert ist, ihn als normaler Benutzer verwenden möglicherweise Probleme wie der fehlenden zur Förderung einer P2P-Sitzung zu einer Besprechung, wenn ein PSTN-Endpunkt beteiligt ist.
  
Bei der Verwaltung eines Pools mit genau zwei Front-End-Servern sind spezielle Überlegungen erforderlich. Weitere Informationen finden Sie unter [Topology Basics for Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md) und [Reference topologies for Skype for Business Server 2015](../../plan-your-deployment/topology-basics/reference-topologies.md).
  
Wenn Sie zusätzlich optional eine Sicherung zur Notfallwiederherstellung und ein Failover für den für große Besprechungen verwendeten Pool bereitstellen möchten, können Sie ihn auch gemeinsam mit einem ähnlich eingerichteten dedizierten Pool in einem anderen Rechenzentrum verwenden. Weitere Informationen hierzu finden Sie unter [Planen für hohe Verfügbarkeit und notfallwiederherstellung in Skype für Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
Zusätzliche Notizen zur Topologie:
  
- Eine Dateifreigabe ist erforderlich, um Besprechungsinhalte zu speichern und um, wenn ein Archivierungsserver bereitgestellt und aktiviert wurde, die Archivierungsdateien zu speichern. Die Dateifreigabe kann dem Pool zugeordnet werden oder dieselbe Dateifreigabe sein, die von einem anderen Pool an diesem Standort verwendet wurde, an dem der Pool bereitgestellt wurde. Ausführliche Informationen zum Konfigurieren der Dateifreigabe finden Sie unter [Erstellen einer Dateifreigabe in Skype für Business Server 2015](../../deploy/install/create-a-file-share.md).
    
- Zur Aktivierung der PowerPoint-Präsentationsfunktion in großen Besprechungen ist ein Office Web App-/Office Online-Server erforderlich. Der Office Web App-/Office Online-Server kann einem großen Besprechungspool zugeordnet werden oder es kann auch derselbe Office Web App-/Office Online-Server sein, der von anderen Pools an diesem Standort verwendet wurde, an dem der dedizierte Pool bereitgestellt wurde. Weitere Informationen finden Sie unter [Konfigurieren der Integration mit Office Web Apps Server in Skype für Business Server](../../deploy/deploy-conferencing/office-web-app-server.md). 
    
- Bei einem Lastenausgleich für die Front-End-Server ist ein Hardwaregerät zum Lastenausgleich für den HTTP-Datenverkehr (z. B. beim Herunterladen von Besprechungsinhalten) erforderlich. DNS-Lastenausgleich wird für den SIP-Datenverkehr empfohlen. Ausführliche Informationen finden Sie unter [Load balancing requirements for Skype for Business](../../plan-your-deployment/network-requirements/load-balancing.md). 
    
- Wenn Sie Monitoring Server für den dedizierten großen besprechungspool verwenden möchten, sollten mit dem Monitoring Server und die Datenbank, die gemeinsam genutzt werden auf allen Front-End-Server-Pools in Ihrer Skype für Business Server-Bereitstellung. Weitere Informationen finden Sie unter [Planen der Überwachung in Skype für Business Server](../../plan-your-deployment/monitoring.md).
    

