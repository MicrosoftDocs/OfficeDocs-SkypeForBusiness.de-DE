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
description: 'Zusammenfassung: In diesem Thema erfahren Sie mehr über die Planung Ihrer Konferenztopologie in Skype for Business Server.'
ms.openlocfilehash: dc7c62d45a2ebd84f38cc67ce996ba0ac72aa794
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814095"
---
# <a name="plan-your-conferencing-topology-for-skype-for-business-server"></a>Planen der Konferenztopologie für Skype for Business Server
 
**Zusammenfassung:** Lesen Sie dieses Thema, um mehr über die Planung Ihrer Konferenztopologie in Skype for Business Server zu erfahren.
  
In diesem Thema werden die Grundlagen der Topologie für Konferenzen in Skype for Business Server beschrieben:
  
- Unterstützte Topologien
    
- Überlegungen zu Einwahlkonferenzen
    
- Überlegungen zu Webkonferenzen
    
- Anforderungen für große Besprechungen
    
Weitere Informationen zu Hardware- und Softwareanforderungen finden Sie unter Hardware- und Softwareanforderungen für [Konferenzen in Skype for Business Server.](hardware-and-software-requirements.md)
  
## <a name="supported-topologies"></a>Unterstützte Topologien

In Skype for Business Server wird der Server, auf dem Konferenzdienste ausgeführt werden, immer mit den Front-End-Servern oder Standard Edition-Servern ausgeführt. Wenn Sie Skype for Business Server bereitstellen, werden die Funktionen für Chatkonferenzen automatisch bereitgestellt. Mit dem Topologie-Generator können Sie angeben, ob Web-, Audio- und Videokonferenzen (A/V) und Einwahlkonferenzen bereitgestellt werden. Sie können den Topologie-Generator auch verwenden, um einer vorhandenen Bereitstellung Konferenzen hinzuzufügen. Weitere Informationen zu Topologiegrundlegungen und Kollokationsszenarien finden Sie unter ["Topology Basics for Skype for Business Server".](../../plan-your-deployment/topology-basics/topology-basics.md)
  
Sie können Konferenzen in den folgenden Topologien und Konfigurationen bereitstellen:
  
- Skype for Business Server Standard Edition
    
- Skype for Business Server Enterprise Edition
    
- Mit oder ohne Enterprise-VoIP
    
## <a name="dial-in-conferencing-considerations"></a>Überlegungen zu Einwahlkonferenzen

Wenn Sie Einwahlkonferenzen bereitstellen, müssen Sie Folgendes berücksichtigen:
  
- Einwahlkonferenzen erfordern einen Vermittlungsserver zum Übersetzen von Signalen (und Medien in einigen Konfigurationen) zwischen Skype for Business Server und dem PSTN-Gateway sowie ein PSTN-Gateway zum Übersetzen von Signalen und Medien zwischen dem Vermittlungsserver und dem PSTN-Gateway.
    
   Bevor Sie Einwahlkonferenzen konfigurieren können, müssen Sie entweder Enterprise-VoIP oder einen Vermittlungsserver und mindestens eine der folgenden Bereitstellen:
    
  - PSTN-Gateway
    
  - IP-PBX
    
  - Session Border Controller (SBC) (für einen Internettelefoniedienstanbieter, mit dem Sie eine Verbindung herstellen, indem Sie einen SIP-Trunk konfigurieren)
    
- Sie können den Anwendungsdienst, die Konferenz attendant-Anwendung und die Konferenzankündigungsanwendung an einem zentralen Standort, jedoch nicht an einem Zweigstellenstandort bereitstellen.
    
- Sie müssen Einwahlkonferenzen in jedem Pool bereitstellen, in dem Sie Skype for Business Server-Konferenzen bereitstellen. Sie müssen nicht in jedem Pool Zugriffsnummern zuweisen, aber Sie müssen die Funktion für Einwahlkonferenzen in jedem Pool bereitstellen. Diese Anforderung unterstützt die Funktion für aufgezeichnete Namen, wenn ein Benutzer eine Zugriffsnummer aus einem Pool anruft, um an einer Skype for Business Server-Konferenz in einem anderen Pool teil zu nehmen. 
    
Weitere Informationen finden Sie unter ["Planen von Einwahlkonferenzen in Skype for Business Server".](dial-in-conferencing.md)
  
## <a name="web-conferencing-considerations"></a>Überlegungen zu Webkonferenzen

Für Webkonferenzen ist Folgendes erforderlich: 
  
- Zugriff auf den Dateispeicher, der zum Speichern von Webkonferenzinhalten verwendet wird.
    
- Integration in Office Web Apps Server/Office Online Server, die erforderlich ist, um während einer Konferenz die PowerPoint-Dateien gemeinsam nutzen zu können.
    
> [!NOTE]
> Die neueste Iteration von Office Web Apps Server heißt Office Online Server, das von Skype for Business Server unterstützt wird. Weitere Informationen finden Sie in der [Office Online Server-Dokumentation.](https://technet.microsoft.com/library/jj219456%28v=office.16%29.aspx) 
  
Skype for Business Server bietet die folgenden Möglichkeiten zum Konfigurieren von Office Web Apps Server/Office Online Server. Je nach Ihren Anforderungen können Sie:
  
- **Installieren Sie sowohl Skype for Business Server als auch Office Web Apps Server/Office Online Server lokal hinter der Firewall Ihrer Organisation und in derselben Netzwerkzone.** Bei dieser Topologie wird der externe Zugriff auf Office Web Apps Server/Office Online Server über Den Reverseproxyserver bereitgestellt. Idealerweise sollten Sie Office Web Apps Server/Office Online Server in derselben Netzwerkzone wie Skype for Business Server installieren.
    
    Externe Skype for Business-Clients können über einen Reverseproxyserver eine Verbindung mit Skype for Business Server und Office Web Apps Server/Office Online Server herstellen. Dabei handelt es sich um einen Server, der Anforderungen aus dem Internet übernimmt und an das interne Netzwerk weitersent. (Interne Clients müssen den Reverseproxyserver nicht verwenden, da sie direkt eine Verbindung mit Office Web Apps Server/Office Online Server herstellen können.) Diese Topologie funktioniert am besten, wenn Sie eine dedizierte Office Web Apps Server/Office Online Server-Farm verwenden möchten, die nur von Skype for Business Server verwendet wird.
    
- **Verwenden Sie einen extern bereitgestellten Office Web Apps-Server/Office Online-Server.** In dieser Topologie wird Skype for Business Server lokal bereitgestellt und verwendet einen Office Web Apps-/Office Online-Server, der außerhalb der Skype for Business Server-Netzwerkzone bereitgestellt wird. Dies kann passieren, wenn Office Web Apps Server/Office Online Server von mehreren Anwendungen im Unternehmen gemeinsam genutzt wird und in einem Netzwerk bereitgestellt wird, in dem Skype for Business Server die externe Schnittstelle von Office Web Apps Server/Office Online Server verwenden muss und umgekehrt.
    
    Sie müssen keinen Reverseproxyserver installieren. Stattdessen werden alle Anforderungen vom Office Web Apps Server/Office Online Server an Skype for Business Server über Ihren Edgeserver geroutet. Sowohl Ihre internen als auch Ihre externen Skype for Business-Clients stellen über die externe URL eine Verbindung mit Office Web Apps Server/Office Online Server herzustellen.
    
    Wenn der Office Web Apps Server/Office Online Server außerhalb der internen Firewall bereitgestellt wird, wählen Sie die Option **"Office Web Apps Server** wird in einem externen Netzwerk (d. h. Umkreis/Internet) im Topologie-Generator bereitgestellt" aus.
    
Weitere Informationen finden Sie unter ["Konfigurieren der Integration mit Office Web Apps Server in Skype for Business Server".](../../deploy/deploy-conferencing/office-web-app-server.md) 
  
Unabhängig von der ausgewählten Topologie ist es wichtig, dass die richtigen Firewallports geöffnet werden. Sie müssen sicherstellen, dass DNS-Namen, -IP-Adressen und Ports nicht durch Firewalls auf dem Office Web Apps Server/Office Online Server, dem Lastenausgleichs- oder Skype for Business Server blockiert werden.
  
> [!NOTE]
> Eine weitere Option für den externen Zugriff auf Office Web Apps Server/Office Online Server ist die Bereitstellung des Servers im Umkreisnetzwerk. Wenn Sie dies tun möchten, beachten Sie, dass für das Setup von Office Web Apps Server/Office Online Server der Servercomputer Mitglied Ihrer Active Directory-Domäne sein muss. Es wird empfohlen, Office Web Apps Server/Office Online Server nicht im Umkreisnetzwerk zu installieren, es sei denn, ihre Netzwerkrichtlinie erlaubt Computern im Umkreisnetzwerk, Active Directory-Domänenmitglieder zu sein. Stattdessen sollten Sie Office Web Apps Server/Office Online Server im internen Netzwerk installieren und externen Benutzern Zugriff über Den Reverseproxyserver bereitstellen. 
  
## <a name="topology-requirements-for-large-meetings"></a>Topologieanforderungen für große Besprechungen

Für eine einzelne große Besprechung sind mindestens ein Front-End-Server und ein Back-End-Server erforderlich. Um jedoch hohe Verfügbarkeit zu bieten, empfehlen wir einen Front-End-Serverpool mit gespiegelten Back-End-Servern, wie im folgenden Diagramm dargestellt:
  
**Große Besprechungstopologie**

![Große Besprechungstopologie](../../media/06858900-a262-4a47-96d0-51abd6827064.png)
  
Der Benutzer, der die großen Besprechungen hostet, muss sein Benutzerkonto im Front-End-Pool hosten. Es wird jedoch nicht empfohlen, dass andere Benutzerkonten in diesem Pool gehostet werden. Er sollte nur für diese großen Besprechungen verwendet werden. In diesem Pool sollte ein spezielles Benutzerkonto erstellt werden, das nur zur Durchführung großer Besprechungen verwendet wird. Da die Einstellung für große Besprechungen leistungsoptimiert ist, kann die Verwendung als normaler Benutzer Probleme verursachen, z. B. die Unfähigkeit, eine P2P-Sitzung zu einer Besprechung zu machen, wenn ein Endpunkt im öffentlichen Telefonnetz beteiligt ist.
  
Bei der Verwaltung eines Pools mit genau zwei Front-End-Servern sind spezielle Überlegungen erforderlich. Weitere Informationen finden Sie unter [Topology Basics for Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md) und [Reference topologies for Skype for Business Server 2015](../../plan-your-deployment/topology-basics/reference-topologies.md).
  
Wenn Sie optional eine Notfallwiederherstellungssicherung und ein Failover für den Pool bereitstellen möchten, der für große Besprechungen verwendet wird, können Sie ihn mit einem ähnlich eingerichteten dedizierten Pool in einem anderen Rechenzentrum koppeln. Weitere Informationen finden Sie unter [Plan for high availability and disaster recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
Zusätzliche Notizen zur Topologie:
  
- Zum Speichern von Besprechungsinhalten und zum Speichern der Archivierungsdateien ist eine Dateifreigabe erforderlich, wenn der Archivierungsserver bereitgestellt und aktiviert ist. Die Dateifreigabe kann dem Pool zugeordnet werden oder dieselbe Dateifreigabe sein, die von einem anderen Pool an diesem Standort verwendet wurde, an dem der Pool bereitgestellt wurde. Weitere Informationen zum Konfigurieren der Dateifreigabe finden Sie unter [Erstellen einer Dateifreigabe in Skype for Business Server 2015](../../deploy/install/create-a-file-share.md).
    
- Ein Office Web Apps Server/Office Online Server ist erforderlich, um die Funktionalität der PowerPoint-Präsentation in großen Besprechungen zu aktivieren. Der Office Web Apps Server/Office Online Server kann für den großen Besprechungspool oder denselben Office Web Apps Server/Office Online Server verwendet werden, der von anderen Pools am Standort verwendet wird, an dem der dedizierte Pool bereitgestellt wird. Weitere Informationen finden Sie unter ["Konfigurieren der Integration mit Office Web Apps Server in Skype for Business Server".](../../deploy/deploy-conferencing/office-web-app-server.md) 
    
- Der Lastenausgleich der Front-End-Server erfordert einen Hardwarelastenausgleich für den HTTP-Datenverkehr (z. B. herunterladen von Besprechungsinhalten). DNS-Lastenausgleich wird für den SIP-Datenverkehr empfohlen. Weitere Informationen finden [Sie unter Lastenausgleichsanforderungen für Skype for Business](../../plan-your-deployment/network-requirements/load-balancing.md). 
    
- Wenn Sie den Monitoring Server für den dedizierten großen Besprechungspool verwenden möchten, empfehlen wir die Verwendung des Monitoring Servers und seiner Datenbank, die für alle Front-End-Serverpools in Ihrer Skype for Business Server-Bereitstellung freigegeben sind. Weitere Informationen finden Sie unter ["Planen der Überwachung in Skype for Business Server".](../../plan-your-deployment/monitoring.md)
    

