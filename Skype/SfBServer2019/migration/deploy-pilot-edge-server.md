---
title: Bereitstellen eines Pilot-Edgeservers
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: In diesem Thema werden die Konfigurationseinstellungen, die Sie kennen sollten, bevor Sie Ihre Skype für Business Server 2019 Edge-Server bereitstellen müssen. Die Bereitstellung und Konfiguration Prozesse für Skype für Business Server 2019 sind Skype für Business Server 2015 sehr ähnlich. In diesem Abschnitt werden nur die wichtigsten Punkte, die Sie als Teil Ihrer Bereitstellung eines pilotpools berücksichtigen sollten. Ausführliche Schritte finden Sie unter Deploying Zugriff durch externe Benutzer in Skype für Business Server 2019 in der Bereitstellungsdokumentation, wird der Bereitstellungsprozess beschrieben und bietet auch Konfigurationsinformationen für den Zugriff externer Benutzer.
ms.openlocfilehash: 5b755d0ba8802c47a176cb3375a87b6523f35fad
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876198"
---
# <a name="deploy-pilot-edge-server"></a>Bereitstellen eines Pilot-Edgeservers

In diesem Thema werden die Konfigurationseinstellungen, die, denen Sie berücksichtigen sollten vor der Bereitstellung von Ihrer Skype für Business Server 2019 Edge-Server, behandelt. Die Bereitstellung und Konfiguration Prozesse für Skype für Business Server 2019 sind Skype für Business Server 2015 sehr ähnlich. In diesem Abschnitt werden nur die wichtigsten Punkte, die Sie als Teil Ihrer Bereitstellung eines pilotpools berücksichtigen sollten. <!-- For detailed steps, see 
 [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.  -->
  
Navigieren Sie durch den Assistenten **Neuen Edgepool definieren** , überprüfen Sie die wichtigsten Konfigurationseinstellungen in den folgenden Schritten dargestellt. Beachten Sie, dass nur ein paar Seiten des Assistenten **Neues Edge-Pool definieren** angezeigt werden. 
  
### <a name="to-define-an-edge-pool"></a>So definieren Sie einen Edge-Pool

1. Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.
    
2. Navigieren Sie zu der Skype für Business Server 2019 Knoten. Maustaste auf **edgepools**, und klicken Sie auf **Neuer edgepool**.
    
     ![Das Dialogfeld neuen Edgepool definieren](../media/migration_ocs_topo_edgepool_page1.JPG)
  
3. Ein edgepool kann es sich um einen **Pool mit mehreren Computern** oder **Pool mit einem Computer**sein.
    
     ![Definieren der Edge-Pool-FQDN (Dialogfeld)](../media/migration_ocs_topo_edgepool_page2.JPG)
  
4. Aktivieren Sie auf der Seite **Features auswählen** nicht verbunden oder XMPP-Verbund. Verbund und XMPP-Verbund werden beide derzeit über Edgeserver der Vorversion weitergeleitet. Diese Funktionen werden in einer späteren Phase der Migration konfiguriert. 

  
5. Weiterhin die folgenden Seiten des Assistenten ausfüllen: **Externe FQDNs**, **die interne IP-Adresse definieren**und **die externe IP-Adresse definieren**.
    
6. Wählen Sie auf der Seite **Server für den nächsten Hop definieren** den Director für den nächsten Hop des edgepool der Vorgängerversion. 
    
     ![Definieren der nächsten Hop (Dialogfeld)](../media/migration_ocs_topo_edgepool_page7.JPG)
  
7. Auf der Seite **Front-End zuordnen oder vermittlungspools** nicht zuordnen eines Pools mit diesen edgepool zu diesem Zeitpunkt. Externe Mediendatenverkehr wird derzeit über Edgeserver der Vorversion geleitet. Diese Einstellung wird in einer späteren Phase der Migration konfiguriert werden. 
    
     ![Ordnen Sie im Dialogfeld Front-End-Pools](../media/migration_ocs_topo_edgepool_page8.JPG)
  
8. Klicken Sie auf **Fertig stellen**, und klicken Sie dann **Veröffentlichen** der Topologie. 
    
9. Führen Sie die Schritte in der Bereitstellungsdokumentation aus, um die Dateien auf dem neuen Edge-Server installieren, Zertifikate zu konfigurieren und Starten der Dienste aus. 
<!-- [Install Edge Servers for Skype for Business Server 2019](../deployment/deploying-external-user-access/install-edge-servers.md) in -->
    
Es ist sehr wichtig, dass die Einhaltung der Richtlinien in den Themen in der Bereitstellungsdokumentation. In diesem Abschnitt Exportvorgängen lediglich einige Hinweise auf Konfigurationseinstellungen für diese Serverrollen zu installieren. 
<!-- [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) -->
  
Sie haben jetzt einen legacy Edge-Server parallel mit einer Skype für Business Server 2019 Edge-Server-Bereitstellung bereitgestellt. Stellen Sie sicher, dass sowohl Bereitstellungen ordnungsgemäß ausgeführt werden, Dienste gestartet sind, und Sie beide Bereitstellungen vor dem Verschieben in die nächste Phase verwalten können. 
  

