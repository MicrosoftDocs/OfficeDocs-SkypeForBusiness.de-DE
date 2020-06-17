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
description: In diesem Thema werden Konfigurationseinstellungen hervorgehoben, die Sie vor der Bereitstellung Ihrer Skype for Business Server 2019 Edgeserver beachten sollten. Die Bereitstellungs-und Konfigurationsprozesse für Skype for Business Server 2019 ähneln Skype for Business Server 2015. In diesem Abschnitt sind nur die wichtigsten zu beachtenden Punkte für die Bereitstellung Ihres Pilotpools hervorgehoben. Ausführliche Anweisungen finden Sie unter Deploying External User Access in Skype for Business Server 2019 in der Bereitstellungsdokumentation, in der der Bereitstellungsprozess beschrieben wird und der auch Konfigurationsinformationen für den Zugriff durch externe Benutzer enthält.
ms.openlocfilehash: 00c371b917f2649dba9011fbbce6162b153822d1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752867"
---
# <a name="deploy-pilot-edge-server"></a>Bereitstellen eines Pilot-Edgeservers

In diesem Thema werden die Konfigurationseinstellungen hervorgehoben, die Sie vor der Bereitstellung Ihrer Skype for Business Server 2019 Edgeserver beachten sollten. Die Bereitstellungs-und Konfigurationsprozesse für Skype for Business Server 2019 ähneln Skype for Business Server 2015. In diesem Abschnitt sind nur die wichtigsten zu beachtenden Punkte für die Bereitstellung Ihres Pilotpools hervorgehoben. <!-- For detailed steps, see 
 [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.  -->
  
As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps. Note that only a few pages of the **Define New Edge Pool** wizard are shown. 
  
### <a name="to-define-an-edge-pool"></a>So definieren Sie einen Edge-Pool

1. Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.
    
2. Navigieren Sie zum Knoten Skype for Business Server 2019. Klicken Sie mit der rechten Maustaste auf **Edgepools**, und klicken Sie dann auf **Neuer Edgepool**.
    
     ![Definieren des Dialogfelds "neuer Edge-Pool"](../media/migration_ocs_topo_edgepool_page1.JPG)
  
3. Ein Edgepool ist entweder ein **Pool mit mehreren Computern** oder ein **Pool mit einem Computer**.
    
     ![Definieren des Dialogfelds für den FQDN des Edge-Pools](../media/migration_ocs_topo_edgepool_page2.JPG)
  
4. Aktivieren Sie auf der Seite **Funktionen auswählen** nicht den Verbund oder den XMPP-Partnerverbund. Der Partnerverbund und der XMPP-Verbund werden derzeit über die Legacy Edgeserver weitergeleitet. Diese Funktionen werden in einer späteren Phase der Migration konfiguriert. 

  
5. Beenden Sie die folgenden Assistentenseiten: **externe FQDNs**, **definieren Sie die interne IP-Adresse**, und **definieren Sie die externe IP-Adresse**.
    
6. Wählen Sie auf der Seite **nächsten Hop-Server definieren** den Director für den nächsten Hop der Legacy Edgepool aus. 
    
     ![Definieren des nächsten Hops (Dialogfeld)](../media/migration_ocs_topo_edgepool_page7.JPG)
  
7. Verknüpfen Sie auf der Seite **Front-End-oder Vermittlungs Pools zuordnen** keinen Pool mit diesem Edgepool zu diesem Zeitpunkt. Der externe Mediendatenverkehr wird derzeit über die Legacy Edgeserver weitergeleitet. Diese Einstellung wird in einer späteren Phase der Migration konfiguriert. 
    
     ![Dialogfeld "Front-End-Pools zuordnen"](../media/migration_ocs_topo_edgepool_page8.JPG)
  
8. Klicken Sie auf **Fertig stellen**, und **veröffentlichen** Sie dann die Topologie. 
    
9. Führen Sie die Schritte in der Bereitstellungsdokumentation aus, um die Dateien auf dem neuen Edgeserver zu installieren, Zertifikate zu konfigurieren und die Dienste zu starten. 
<!-- [Install Edge Servers for Skype for Business Server 2019](../deployment/deploying-external-user-access/install-edge-servers.md) in -->
    
Es ist sehr wichtig, dass Sie die Richtlinien in den Themen in der Bereitstellungsdokumentation befolgen. Dieser Abschnitt stellt lediglich einen Leitfaden für die Konfigurationseinstellungen beim Installieren dieser Serverrollen dar. 
<!-- [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) -->
  
Sie sollten nun eine Legacy Edgeserver bereitstellen, die parallel mit einer Skype for Business Server 2019-Edge-Server-Bereitstellung bereitgestellt wird. Stellen Sie sicher, dass beide Bereitstellungen ordnungsgemäß ausgeführt werden, die Dienste gestartet sind, und Sie beide Bereitstellungen verwalten können, bevor Sie mit der nächsten Phase fortfahren. 
  

