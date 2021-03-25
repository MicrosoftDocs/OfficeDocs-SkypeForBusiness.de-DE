---
title: Planen der Konferenztopologie für Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7392dfa7-791a-4723-88ff-0ef8a9ef11c8
description: 'Summary: Read this topic to learn about planning your conferencing topology in Skype for Business Server.'
ms.openlocfilehash: acf1fecc4ab7c3ea19ca9b65b9ff2ffa2a1e93d1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121583"
---
# <a name="plan-your-conferencing-topology-for-skype-for-business-server"></a>Planen der Konferenztopologie für Skype for Business Server
 
**Zusammenfassung:** Lesen Sie dieses Thema, um mehr über die Planung Ihrer Konferenztopologie in Skype for Business Server zu erfahren.
  
In diesem Thema werden die Grundlagen der Topologie für Konferenzen in Skype for Business Server beschrieben:
  
- Unterstützte Topologien
    
- Überlegungen zu Einwahlkonferenzen
    
- Überlegungen zu Webkonferenzen
    
- Anforderungen für große Besprechungen
    
Weitere Informationen zu Hardware- und Softwareanforderungen finden Sie unter Hardware- und [Softwareanforderungen](hardware-and-software-requirements.md)für Konferenzen in Skype for Business Server .
  
## <a name="supported-topologies"></a>Unterstützte Topologien

In Skype for Business Server ist der Server, auf dem Konferenzdienste ausgeführt werden, immer mit den Front-End-Servern oder Standard Edition-Servern kollidiert. Wenn Sie Skype for Business Server bereitstellen, werden automatisch Chatkonferenzfunktionen bereitgestellt. Sie können angeben, ob Web-, Audio- und Videokonferenzen (A/V) und Einwahlkonferenzen mithilfe des Topologie-Generators bereitgestellt werden. Sie können auch den Topologie-Generator verwenden, um einer vorhandenen Bereitstellung Konferenzen hinzuzufügen. Weitere Informationen zu den Grundlagen der Topologie und Zuteilungsszenarien finden Sie unter [Topology Basics for Skype for Business Server](../../plan-your-deployment/topology-basics/topology-basics.md).
  
Sie können Konferenzen in den folgenden Topologien und Konfigurationen bereitstellen:
  
- Skype for Business Server Standard Edition
    
- Skype for Business Server Enterprise Edition
    
- Mit oder ohne Enterprise-VoIP
    
## <a name="dial-in-conferencing-considerations"></a>Überlegungen zu Einwahlkonferenzen

Wenn Sie Einwahlkonferenzen bereitstellen, müssen Sie Folgendes berücksichtigen:
  
- Einwahlkonferenzen erfordern einen Vermittlungsserver zum Übersetzen von Signalen (und Medien in einigen Konfigurationen) zwischen Skype for Business Server und dem PSTN-Gateway sowie ein PSTN-Gateway zum Übersetzen von Signalen und Medien zwischen dem Vermittlungsserver und dem PSTN-Gateway.
    
   Bevor Sie Einwahlkonferenzen konfigurieren können, müssen Sie entweder Enterprise-VoIP oder einen Vermittlungsserver und mindestens einen der folgenden Server bereitstellen:
    
  - PSTN-Gateway
    
  - IP-PBX
    
  - Session Border Controller (SBC) (für einen Internettelefoniedienstanbieter, mit dem Sie eine Verbindung herstellen, indem Sie einen SIP-Trunk konfigurieren)
    
- Sie können den Anwendungsdienst, die Konferenz attendant-Anwendung und die Konferenzansageanwendung an einem zentralen Standort, aber nicht an einem Zweigstellenstandort bereitstellen.
    
- Sie müssen Einwahlkonferenzen in jedem Pool bereitstellen, in dem Sie Skype for Business Server-Konferenzen bereitstellen. Sie müssen nicht in jedem Pool Zugriffsnummern zuweisen, aber Sie müssen das Feature für Einwahlkonferenzen in jedem Pool bereitstellen. Diese Anforderung unterstützt das Aufgezeichnete Namensfeature, wenn ein Benutzer eine Zugriffsnummer aus einem Pool aufruft, um an einer Skype for Business Server-Konferenz in einem anderen Pool teil zu nehmen. 
    
Weitere Informationen finden Sie unter [Plan for Dial-in conferencing in Skype for Business Server](dial-in-conferencing.md).
  
## <a name="web-conferencing-considerations"></a>Überlegungen zu Webkonferenzen

Webkonferenzen erfordern Folgendes: 
  
- Zugriff auf den Dateispeicher, der zum Speichern von Webkonferenzinhalten verwendet wird.
    
- Integration in Office Web Apps Server/Office Online Server, die zum Freigeben von PowerPoint-Dateien während einer Konferenz erforderlich ist.
    
> [!NOTE]
> Die neueste Iteration von Office Web Apps Server heißt Office Online Server, das von Skype for Business Server unterstützt wird. Weitere Informationen finden Sie in der [Office Online Server-Dokumentation](/officeonlineserver/office-online-server). 
  
Skype for Business Server bietet die folgenden Möglichkeiten zum Konfigurieren von Office Web Apps Server/Office Online Server. Je nach Ihren Anforderungen können Sie:
  
- **Installieren Sie sowohl Skype for Business Server als auch Office Web Apps Server/Office Online Server lokal hinter der Firewall Ihrer Organisation und in derselben Netzwerkzone.** Mit dieser Topologie wird der externe Zugriff auf Office Web Apps Server/Office Online Server über Ihren Reverseproxyserver bereitgestellt. Im Idealfall sollten Sie Office Web Apps Server/Office Online Server in derselben Netzwerkzone wie Skype for Business Server installieren.
    
    Externe Skype for Business-Clients können eine Verbindung mit Skype for Business Server und office Web Apps Server/Office Online Server über einen Reverseproxyserver herstellen, bei dem es sich um einen Server handelt, der Anforderungen aus dem Internet übernimmt und an das interne Netzwerk weitersen. (Interne Clients müssen den Reverseproxyserver nicht verwenden, da sie direkt eine Verbindung mit Office Web Apps Server/Office Online Server herstellen können.) Diese Topologie funktioniert am besten, wenn Sie eine dedizierte Office Web Apps Server/Office Online Server-Farm verwenden möchten, die nur von Skype for Business Server verwendet wird.
    
- **Verwenden Sie einen extern bereitgestellten Office Web Apps Server/Office Online Server.** In dieser Topologie wird Skype for Business Server lokal bereitgestellt und verwendet einen Office Web Apps Server/Office Online Server, der außerhalb der Skype for Business Server-Netzwerkzone bereitgestellt wird. Dies kann passieren, wenn Office Web Apps Server/Office Online Server für mehrere Anwendungen im Unternehmen freigegeben wird und in einem Netzwerk bereitgestellt wird, in dem Skype for Business Server die externe Schnittstelle von Office Web Apps Server/Office Online Server verwenden muss und umgekehrt.
    
    Sie müssen keinen Reverseproxyserver installieren. Stattdessen werden alle Anforderungen vom Office Web Apps Server/Office Online Server an Skype for Business Server über Ihren Edgeserver geroutet. Sowohl Ihre internen als auch Ihre externen Skype for Business-Clients stellen über die externe URL eine Verbindung mit Office Web Apps Server/Office Online Server herzustellen.
    
    Wenn der Office Web Apps Server/Office Online Server außerhalb Der internen Firewall bereitgestellt wird, wählen Sie die Option **Office Web Apps Server wird in** einem externen Netzwerk (d. h. Umkreis/Internet) im Topologie-Generator bereitgestellt.
    
Weitere Informationen finden Sie unter [Configure integration with Office Web Apps Server in Skype for Business Server](../../deploy/deploy-conferencing/office-web-app-server.md). 
  
Unabhängig von der ausgewählten Topologie ist es wichtig, dass die richtigen Firewallports geöffnet werden. Sie müssen sicherstellen, dass DNS-Namen, IP-Adressen und Ports nicht von Firewalls auf dem Office Web Apps Server/Office Online Server, dem Lastenausgleich oder Skype for Business Server blockiert werden.
  
> [!NOTE]
> Eine weitere Option für den externen Zugriff auf Office Web Apps Server/Office Online Server ist die Bereitstellung des Servers im Umkreisnetzwerk. Wenn Sie dies tun möchten, beachten Sie, dass für das Einrichten von Office Web Apps Server/Office Online Server der Servercomputer Mitglied Ihrer Active Directory-Domäne sein muss. Es sei denn, Ihre Netzwerkrichtlinie lässt zu, dass Computer im Umkreisnetzwerk Active Directory-Domänenmitglieder sind, es wird empfohlen, Office Web Apps Server/Office Online Server nicht im Umkreisnetzwerk zu installieren. Stattdessen sollten Sie Office Web Apps Server/Office Online Server im internen Netzwerk installieren und externen Benutzerzugriff über Ihren Reverseproxyserver bereitstellen. 
  
## <a name="topology-requirements-for-large-meetings"></a>Topologieanforderungen für große Besprechungen

Eine einzelne große Besprechung erfordert mindestens einen Front-End-Server und einen Back-End-Server. Um jedoch hohe Verfügbarkeit zu bieten, empfehlen wir einen zwei Front-End-Serverpool mit gespiegelten Back-End-Servern, wie im folgenden Diagramm dargestellt:
  
**Große Besprechungstopologie**

![Große Besprechungstopologie](../../media/06858900-a262-4a47-96d0-51abd6827064.png)
  
Der Benutzer, der die großen Besprechungen hostet, muss sein Benutzerkonto im Front-End-Pool haben. Es wird jedoch nicht empfohlen, dass andere Benutzerkonten in diesem Pool gehostet werden. Er sollte nur für diese großen Besprechungen verwendet werden. In diesem Pool sollte ein spezielles Benutzerkonto erstellt werden, das nur zur Durchführung großer Besprechungen verwendet wird. Da die Einstellung für große Besprechungen für die Leistung optimiert ist, kann die Verwendung als normaler Benutzer Probleme haben, z. B. die Unfähigkeit, eine P2P-Sitzung in eine Besprechung zu bewerben, wenn ein PSTN-Endpunkt beteiligt ist.
  
Bei der Verwaltung eines Pools mit genau zwei Front-End-Servern sind spezielle Überlegungen erforderlich. Weitere Informationen finden Sie unter [Topology Basics for Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md) und [Referenztopologien für Skype for Business Server 2015](../../plan-your-deployment/topology-basics/reference-topologies.md).
  
Wenn Sie optional Notfallwiederherstellungssicherung und Failover für den Pool bereitstellen möchten, der für große Besprechungen verwendet wird, können Sie ihn mit einem ähnlich eingerichteten dedizierten Pool in einem anderen Rechenzentrum koppeln. Weitere Informationen finden Sie unter [Plan for high availability and disaster recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
Zusätzliche Notizen zur Topologie:
  
- Eine Dateifreigabe ist erforderlich, um Besprechungsinhalte zu speichern und, wenn Archivierungsserver bereitgestellt und aktiviert ist, zum Speichern der Archivierungsdateien. Die Dateifreigabe kann dem Pool zugeordnet werden oder dieselbe Dateifreigabe sein, die von einem anderen Pool an diesem Standort verwendet wurde, an dem der Pool bereitgestellt wurde. Weitere Informationen zum Konfigurieren der Dateifreigabe finden Sie unter [Create a file share in Skype for Business Server 2015](../../deploy/install/create-a-file-share.md).
    
- Ein Office Web Apps Server/Office Online Server ist erforderlich, um die PowerPoint-Präsentationsfunktionen in großen Besprechungen zu aktivieren. Der Office Web Apps Server/Office Online Server kann für den großen Besprechungspool oder denselben Office Web Apps Server/Office Online Server verwendet werden, der von anderen Pools am Standort verwendet wird, an dem der dedizierte Pool bereitgestellt wird. Weitere Informationen finden Sie unter [Configure integration with Office Web Apps Server in Skype for Business Server](../../deploy/deploy-conferencing/office-web-app-server.md). 
    
- Für den Lastenausgleich der Front-End-Server ist ein Hardwarelastenausgleich für den HTTP-Datenverkehr erforderlich (z. B. Download von Besprechungsinhalten). DNS-Lastenausgleich wird für den SIP-Datenverkehr empfohlen. Weitere Informationen finden Sie [unter Lastenausgleichsanforderungen für Skype for Business](../../plan-your-deployment/network-requirements/load-balancing.md). 
    
- Wenn Sie Monitoring Server für den dedizierten pool für große Besprechungen verwenden möchten, wird empfohlen, den Monitoring Server und seine Datenbank zu verwenden, die für alle Front-End-Serverpools in Ihrer Skype for Business Server-Bereitstellung freigegeben sind. Weitere Informationen finden Sie unter [Plan for monitoring in Skype for Business Server](../../plan-your-deployment/monitoring.md).
