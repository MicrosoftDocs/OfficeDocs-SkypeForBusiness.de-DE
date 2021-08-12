---
title: Bereitstellen eines Pilot-Edgeservers
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: In diesem Thema werden die Konfigurationseinstellungen behandelt, die Sie vor der Bereitstellung Ihres Skype for Business Server 2019-Edgeservers beachten sollten. Die Bereitstellungs- und Konfigurationsprozesse für Skype for Business Server 2019 sind Skype for Business Server 2015 sehr ähnlich. In diesem Abschnitt sind nur die wichtigsten zu beachtenden Punkte für die Bereitstellung Ihres Pilotpools hervorgehoben. Ausführliche Schritte finden Sie unter Deploying external user access in Skype for Business Server 2019 in der Bereitstellungsdokumentation, in der der Bereitstellungsprozess beschrieben wird und konfigurationsbezogene Informationen für den externen Benutzerzugriff bereitgestellt werden.
ms.openlocfilehash: 24202bc84be67453eeff321b268f44769d5b11a8eafcd6d93098db7c7b8537fc
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54315081"
---
# <a name="deploy-pilot-edge-server"></a>Bereitstellen eines Pilot-Edgeservers

In diesem Thema werden die Konfigurationseinstellungen behandelt, die Sie beachten sollten, bevor Sie Ihren Skype for Business Server 2019-Edgeserver bereitstellen. Die Bereitstellungs- und Konfigurationsprozesse für Skype for Business Server 2019 sind Skype for Business Server 2015 sehr ähnlich. In diesem Abschnitt sind nur die wichtigsten zu beachtenden Punkte für die Bereitstellung Ihres Pilotpools hervorgehoben. <!-- For detailed steps, see 
 [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.  -->
  
Überprüfen Sie beim Navigieren durch den Assistenten zum **Definieren eines neuen Edgepools** die in den folgenden Schritten dargestellten wichtigen Konfigurationseinstellungen. Beachten Sie, dass nur einige der Seiten des Assistenten zum **Definieren eines neuen Edgepools** abgebildet sind. 
  
### <a name="to-define-an-edge-pool"></a>So definieren Sie einen Edgepool

1. Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.
    
2. Navigieren Sie zum Knoten Skype for Business Server 2019. Klicken Sie mit der rechten Maustaste auf **Edgepools**, und klicken Sie dann auf **Neuer Edgepool**.
    
     ![Definieren des Dialogfelds "Neuer Edgepool"](../media/migration_ocs_topo_edgepool_page1.JPG)
  
3. Ein Edgepool ist entweder ein **Pool mit mehreren Computern** oder ein **Pool mit einem Computer**.
    
     ![Definieren des Edgepool-FQDN-Dialogfelds](../media/migration_ocs_topo_edgepool_page2.JPG)
  
4. Aktivieren Sie auf der Seite **Funktionen auswählen** nicht den Verbund oder den XMPP-Partnerverbund. Partnerverbund und XMPP-Partnerverbund werden derzeit beide über den älteren Edgeserver weitergeleitet. Diese Funktionen werden in einer späteren Phase der Migration konfiguriert. 

  
5. Führen Sie die folgenden Assistentenseiten aus: **Externe FQDNs,** **Definieren der internen IP-Adresse** und Definieren der externen **IP-Adresse.**
    
6. Wählen Sie auf der Seite **"Nächsten Hopserver definieren"** den Director für den nächsten Hop des älteren Edgepools aus. 
    
     ![Definieren des Dialogfelds "Nächster Hop"](../media/migration_ocs_topo_edgepool_page7.JPG)
  
7. Ordnen Sie auf der Seite **"Front-End- oder Vermittlungspools zuordnen"** zu diesem Zeitpunkt keinen Pool diesem Edgepool zu. Der externe Mediendatenverkehr wird derzeit über den älteren Edgeserver weitergeleitet. Diese Einstellung wird in einer späteren Phase der Migration konfiguriert. 
    
     ![Dialogfeld "Front-End-Pools zuordnen"](../media/migration_ocs_topo_edgepool_page8.JPG)
  
8. Klicken Sie auf **Fertig stellen,** und **veröffentlichen Sie** dann die Topologie. 
    
9. Führen Sie die Schritte in der Bereitstellungsdokumentation aus, um die Dateien auf dem neuen Edgeserver zu installieren, Zertifikate zu konfigurieren und die Dienste zu starten. 
<!-- [Install Edge Servers for Skype for Business Server 2019](../deployment/deploying-external-user-access/install-edge-servers.md) in -->
    
Es ist sehr wichtig, dass Sie die Richtlinien in den Themen in der Bereitstellungsdokumentation befolgen. Dieser Abschnitt stellt lediglich einen Leitfaden für die Konfigurationseinstellungen beim Installieren dieser Serverrollen dar. 
<!-- [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) -->
  
Sie sollten jetzt parallel zu einer Skype for Business Server 2019-Edgeserverbereitstellung einen älteren Edgeserver bereitgestellt haben. Stellen Sie sicher, dass beide Bereitstellungen ordnungsgemäß ausgeführt werden, die Dienste gestartet sind, und Sie beide Bereitstellungen verwalten können, bevor Sie mit der nächsten Phase fortfahren. 
  

