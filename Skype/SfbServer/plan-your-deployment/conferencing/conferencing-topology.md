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
ms.localizationpriority: medium
ms.assetid: 7392dfa7-791a-4723-88ff-0ef8a9ef11c8
description: 'Zusammenfassung: Lesen Sie dieses Thema, um mehr über die Planung Ihrer Konferenztopologie in Skype for Business Server zu erfahren.'
ms.openlocfilehash: d5a048603e68b020f0aba750a4dd34cfd334f182
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58599910"
---
# <a name="plan-your-conferencing-topology-for-skype-for-business-server"></a>Planen der Konferenztopologie für Skype for Business Server
 
**Zusammenfassung:** Lesen Sie dieses Thema, um mehr über die Planung Ihrer Konferenztopologie in Skype for Business Server zu erfahren.
  
In diesem Thema werden die Topologiegrundlagen für Konferenzen in Skype for Business Server beschrieben:
  
- Unterstützte Topologien
    
- Überlegungen zu Einwahlkonferenzen
    
- Überlegungen zu Webkonferenzen
    
- Anforderungen für große Besprechungen
    
Weitere Informationen zu Hardware- und Softwareanforderungen finden Sie unter [Hardware- und Softwareanforderungen für Konferenzen in Skype for Business Server.](hardware-and-software-requirements.md)
  
## <a name="supported-topologies"></a>Unterstützte Topologien

In Skype for Business Server wird der Server, auf dem Konferenzdienste ausgeführt werden, immer mit den Front-End-Servern oder Standard Edition Servern verbunden. Wenn Sie Skype for Business Server bereitstellen, werden die Chatkonferenzfunktionen automatisch bereitgestellt. Mithilfe des Topologie-Generators können Sie angeben, ob Web-, Audio- und Videokonferenzen (A/V) und Einwahlkonferenzen bereitgestellt werden sollen. Sie können den Topologie-Generator auch verwenden, um einer vorhandenen Bereitstellung Konferenzen hinzuzufügen. Ausführliche Informationen zu Topologiegrundlagen und Kollokationsszenarien finden Sie unter [Topologiegrundlagen für Skype for Business Server.](../../plan-your-deployment/topology-basics/topology-basics.md)
  
Sie können Konferenzen in den folgenden Topologien und Konfigurationen bereitstellen:
  
- Skype for Business Server Standard Edition
    
- Skype for Business Server Enterprise Edition
    
- Mit oder ohne Enterprise-VoIP
    
## <a name="dial-in-conferencing-considerations"></a>Überlegungen zu Einwahlkonferenzen

Wenn Sie Einwahlkonferenzen bereitstellen, müssen Sie Folgendes berücksichtigen:
  
- Einwahlkonferenzen erfordern einen Vermittlungsserver zum Übersetzen von Signalen (und Medien in einigen Konfigurationen) zwischen Skype for Business Server und dem PSTN-Gateway sowie ein PSTN-Gateway zum Übersetzen von Signalen und Medien zwischen dem Vermittlungsserver und dem PSTN-Gateway.
    
   Bevor Sie Einwahlkonferenzen konfigurieren können, müssen Sie entweder Enterprise-VoIP oder einen Vermittlungsserver und mindestens eine der folgenden Optionen bereitstellen:
    
  - PSTN-Gateway
    
  - IP-Nebenstellenanlage
    
  - Session Border Controller (SBC) (für einen Internettelefoniedienstanbieter, mit dem Sie eine Verbindung herstellen, indem Sie einen SIP-Trunk konfigurieren)
    
- Sie können den Anwendungsdienst, Konferenzzentralenanwendung und Konferenzankündigungsanwendung an einem zentralen Standort, aber nicht an einer Zweigstelle bereitstellen.
    
- Sie müssen Einwahlkonferenzen in jedem Pool bereitstellen, in dem Sie Skype for Business Server Konferenzen bereitstellen. Sie müssen nicht in jedem Pool Zugriffsnummern zuweisen, aber Sie müssen das Feature für Einwahlkonferenzen in jedem Pool bereitstellen. Diese Anforderung unterstützt das Feature für aufgezeichnete Namen, wenn ein Benutzer eine Zugriffsnummer aus einem Pool aufruft, um an einer Skype for Business Server Konferenz in einem anderen Pool teilzunehmen. 
    
Weitere Informationen finden Sie unter [Plan for dial-in conferencing in Skype for Business Server](dial-in-conferencing.md).
  
## <a name="web-conferencing-considerations"></a>Überlegungen zu Webkonferenzen

Webkonferenzen erfordern Folgendes: 
  
- Zugriff auf den Dateispeicher, der zum Speichern von Webkonferenzinhalten verwendet wird.
    
- Integration in Office Web Apps-Server/Office Online Server, was erforderlich ist, um während einer Konferenz PowerPoint Dateien freizugeben.
    
> [!NOTE]
> Die neueste Iteration von Office Web Apps-Server heißt Office Online Server, die von Skype for Business Server unterstützt wird. Weitere Informationen finden Sie in der [Office Online Server Dokumentation.](/officeonlineserver/office-online-server) 
  
Skype for Business Server bietet die folgenden Möglichkeiten zum Konfigurieren Office Web Apps-Servers/Office Online Server. Je nach Ihren Anforderungen können Sie folgende Aktionen ausführen:
  
- **Installieren Sie sowohl Skype for Business Server als auch Office Web Apps-Server/Office Online Server lokal hinter der Firewall Ihrer Organisation und in derselben Netzwerkzone.** Mit dieser Topologie wird der externe Zugriff auf Office Web Apps-Server/Office Online Server über den Reverseproxyserver bereitgestellt. Idealerweise sollten Sie Office Web Apps-Server/Office Online Server in derselben Netzwerkzone wie Skype for Business Server installieren.
    
    Externe Skype for Business Clients können eine Verbindung mit Skype for Business Server und Office Web Apps-Server/Office Online Server herstellen, indem sie einen Reverseproxyserver verwenden, bei dem es sich um einen Server handelt, der Anforderungen aus dem Internet entgegennimmt und an das interne Netzwerk weiterleitet. (Interne Clients müssen den Reverseproxyserver nicht verwenden, da sie eine direkte Verbindung mit Office Web Apps-Server/Office Online Server herstellen können.) Diese Topologie funktioniert am besten, wenn Sie einen dedizierten Office Web Apps-Server/Office Online Server-Farm verwenden möchten, der nur von Skype for Business Server verwendet wird.
    
- **Verwenden Sie einen extern bereitgestellten Office Web Apps-Server/Office Online Server.** In dieser Topologie wird Skype for Business Server lokal bereitgestellt und verwendet einen Office Web Apps-Server/Office Online Server, der außerhalb der Skype for Business Server Netzwerkzone bereitgestellt wird. Dies kann passieren, wenn Office Web Apps-Server/Office Online Server für mehrere Anwendungen im Unternehmen freigegeben und in einem Netzwerk bereitgestellt wird, das Skype for Business Server zur Verwendung der externen Schnittstelle von Office Web Apps Server/Office Online Server und umgekehrt benötigt.
    
    Sie müssen keinen Reverseproxyserver installieren. Stattdessen werden alle Anforderungen vom Office Web Apps-Server/Office Online Server an Skype for Business Server über den Edgeserver weitergeleitet. Sowohl Die internen als auch die externen Skype for Business Clients stellen über die externe URL eine Verbindung mit Office Web Apps-Server/Office Online Server her.
    
    Wenn der Office Web Apps-Server/Office Online Server außerhalb der internen Firewall bereitgestellt wird, wählen Sie die Option **aus, Office Web Apps-Server in einem externen Netzwerk** (d. h. Umkreis/Internet) im Topologie-Generator bereitgestellt wird.
    
Weitere Informationen finden Sie unter Konfigurieren der [Integration mit Office Web Apps Server in Skype for Business Server.](../../deploy/deploy-conferencing/office-web-app-server.md) 
  
Unabhängig von der ausgewählten Topologie ist es wichtig, dass die richtigen Firewallports geöffnet werden. Sie müssen sicherstellen, dass DNS-Namen, IP-Adressen und Ports nicht durch Firewalls auf dem Office Web Apps-Server/Office Online Server, dem Lastenausgleich oder Skype for Business Server blockiert werden.
  
> [!NOTE]
> Eine weitere Option für den externen Zugriff auf Office Web Apps-Server/Office Online Server ist die Bereitstellung des Servers im Umkreisnetzwerk. Wenn Sie sich dafür entscheiden, denken Sie daran, dass Office Web Apps Server/Office Online Server Setup erfordert, dass der Servercomputer Mitglied Ihrer Active Directory-Domäne ist. Es wird empfohlen, Office Web Apps-Server/Office Online Server nicht im Umkreisnetzwerk zu installieren, es sei denn, ihre Netzwerkrichtlinie lässt zu, dass Computer im Umkreisnetzwerk Active Directory-Domänenmitglieder sind. Stattdessen sollten Sie Office Web Apps-Server/Office Online Server im internen Netzwerk installieren und externen Benutzerzugriff über den Reverseproxyserver gewähren. 
  
## <a name="topology-requirements-for-large-meetings"></a>Topologieanforderungen für große Besprechungen

Eine einzelne große Besprechung erfordert mindestens einen Front-End-Server und einen Back-End-Server. Um hohe Verfügbarkeit zu gewährleisten, empfehlen wir jedoch einen zwei Front-End-Serverpool mit gespiegelten Back-End-Servern, wie im folgenden Diagramm dargestellt:
  
**Topologie für große Besprechungen**

![Topologie für große Besprechungen](../../media/06858900-a262-4a47-96d0-51abd6827064.png)
  
Der Benutzer, der die großen Besprechungen hostet, muss sein Benutzerkonto im Front-End-Pool verwaltet haben. Es wird jedoch nicht empfohlen, dass andere Benutzerkonten in diesem Pool gehostet werden. Er sollte nur für diese großen Besprechungen verwendet werden. In diesem Pool sollte ein spezielles Benutzerkonto erstellt werden, das nur zur Durchführung großer Besprechungen verwendet wird. Da die Einstellung für große Besprechungen für die Leistung optimiert ist, kann die Verwendung als normaler Benutzer Probleme haben, z. B. die Unfähigkeit, eine P2P-Sitzung zu einer Besprechung hochzustufen, wenn ein PSTN-Endpunkt beteiligt ist.
  
Bei der Verwaltung eines Pools mit genau zwei Front-End-Servern sind spezielle Überlegungen erforderlich. Weitere Informationen finden Sie unter [Topologiegrundlagen für Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md) und [Referenztopologien für Skype for Business Server 2015.](../../plan-your-deployment/topology-basics/reference-topologies.md)
  
Wenn Sie optional eine Sicherung der Notfallwiederherstellung und ein Failover für den Pool bereitstellen möchten, der für große Besprechungen verwendet wird, können Sie ihn mit einem ähnlich eingerichteten dedizierten Pool in einem anderen Rechenzentrum koppeln. Ausführliche Informationen finden Sie unter [Plan for high availability and disaster recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
Zusätzliche Notizen zur Topologie:
  
- Eine Dateifreigabe ist zum Speichern von Besprechungsinhalten und, wenn der Archivierungsserver bereitgestellt und aktiviert ist, zum Speichern der Archivierungsdateien erforderlich. Die Dateifreigabe kann dem Pool zugeordnet werden oder dieselbe Dateifreigabe sein, die von einem anderen Pool an diesem Standort verwendet wurde, an dem der Pool bereitgestellt wurde. Ausführliche Informationen zum Konfigurieren der Dateifreigabe finden Sie unter [Erstellen einer Dateifreigabe in Skype for Business Server 2015.](../../deploy/install/create-a-file-share.md)
    
- Ein Office Web Apps-Server/Office Online Server ist erforderlich, um die PowerPoint Präsentationsfunktion in großen Besprechungen zu aktivieren. Der Office Web Apps-Server/Office Online Server kann für den großen Besprechungspool vorgesehen sein oder Office Web Apps-Server/Office Online Server, die von anderen Pools am Standort verwendet werden, an dem der dedizierte Pool bereitgestellt wird. Weitere Informationen finden Sie unter Konfigurieren der [Integration mit Office Web Apps Server in Skype for Business Server.](../../deploy/deploy-conferencing/office-web-app-server.md) 
    
- Für den Lastenausgleich der Front-End-Server ist ein Hardwarelastenausgleich für den HTTP-Datenverkehr (z. B. herunterladen von Besprechungsinhalten) erforderlich. DNS-Lastenausgleich wird für den SIP-Datenverkehr empfohlen. Ausführliche Informationen finden Sie unter [load balancing requirements for Skype for Business](../../plan-your-deployment/network-requirements/load-balancing.md). 
    
- Wenn Sie den Monitoring Server für den dedizierten Pool für große Besprechungen verwenden möchten, empfehlen wir die Verwendung des Überwachungsservers und seiner Datenbank, die für alle Front-End-Serverpools in Ihrer Skype for Business Server Bereitstellung freigegeben sind. Weitere Informationen finden Sie unter [Plan for monitoring in Skype for Business Server](../../plan-your-deployment/monitoring.md).
