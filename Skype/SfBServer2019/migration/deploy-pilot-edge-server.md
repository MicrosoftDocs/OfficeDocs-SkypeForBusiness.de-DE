---
title: Bereitstellen eines Pilot-Edgeservers
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: In diesem Thema werden die Konfigurationseinstellungen hervorgehoben, die Sie vor der Bereitstellung Ihres Skype for Business Server 2019 Edge-Servers beachten sollten. Die Bereitstellungs-und Konfigurationsprozesse für Skype for Business Server 2019 sind mit Skype for Business Server 2015 sehr ähnlich. In diesem Abschnitt werden nur wichtige Punkte hervorgehoben, die Sie im Rahmen der Bereitstellung des pilotpools berücksichtigen sollten. Detaillierte Anweisungen finden Sie unter Bereitstellen des Zugriffs auf externe Benutzer in Skype for Business Server 2019 in der Bereitstellungsdokumentation, in der der Bereitstellungsprozess beschrieben wird, sowie Konfigurationsinformationen für den Zugriff durch externe Benutzer.
ms.openlocfilehash: c2beb22e2cce608b692884ad9b49fef40cb87058
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813653"
---
# <a name="deploy-pilot-edge-server"></a>Bereitstellen eines Pilot-Edgeservers

In diesem Thema werden die Konfigurationseinstellungen hervorgehoben, die Sie berücksichtigen sollten, bevor Sie Ihren Skype for Business Server 2019 Edge-Server bereitstellen. Die Bereitstellungs-und Konfigurationsprozesse für Skype for Business Server 2019 sind mit Skype for Business Server 2015 sehr ähnlich. In diesem Abschnitt werden nur wichtige Punkte hervorgehoben, die Sie im Rahmen der Bereitstellung des pilotpools berücksichtigen sollten. <!-- For detailed steps, see 
 [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.  -->
  
Wenn Sie im Assistenten zum **Definieren eines neuen Edge-Pools** navigieren, überprüfen Sie die wichtigsten Konfigurationseinstellungen, die in den folgenden Schritten gezeigt werden. Beachten Sie, dass nur wenige Seiten des Assistenten zum **Definieren eines neuen Edge-Pools** angezeigt werden. 
  
### <a name="to-define-an-edge-pool"></a>So definieren Sie einen Edge-Pool

1. Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.
    
2. Navigieren Sie zum Skype for Business Server 2019-Knoten. Klicken Sie mit der rechten Maustaste auf **Edge-Pools**, und klicken Sie auf **neuer Edge-Pool**.
    
     ![Dialogfeld ' neuen Edge-Pool definieren '](../media/migration_ocs_topo_edgepool_page1.JPG)
  
3. Ein Edge-Pool kann ein Pool mit **mehreren Computern** oder ein **einzelner Computerpool**sein.
    
     ![Definieren des Dialogfelds "FQDN des Edge-Pools"](../media/migration_ocs_topo_edgepool_page2.JPG)
  
4. Aktivieren Sie auf der Seite **"Features auswählen** " die Föderation oder den XMPP-Verbund nicht. Föderation und XMPP-Föderation sind beide derzeit über den Legacy-Edgeserver geroutet. Diese Features werden in einer späteren Migrationsphase konfiguriert. 

  
5. Führen Sie die folgenden Assistentenseiten aus: **externe FQDNs**, **definieren Sie die interne IP-Adresse**, und definieren Sie **die externe IP-Adresse**.
    
6. Wählen Sie auf der Seite **Nächster Hop-Server definieren** den Director für den nächsten Hop des Legacy-Edge-Pools aus. 
    
     ![Dialogfeld ' nächster Hop definieren '](../media/migration_ocs_topo_edgepool_page7.JPG)
  
7. Verbinden Sie auf der Seite **Front-End-oder Mediations Pools zuordnen** keinen Pool mit diesem Edge-Pool zu diesem Zeitpunkt. Der externe Mediendatenverkehr wird derzeit über den Legacy-Edgeserver weitergeleitet. Diese Einstellung wird in einer späteren Migrationsphase konfiguriert. 
    
     ![Dialogfeld ' Front-End-Pools zuordnen '](../media/migration_ocs_topo_edgepool_page8.JPG)
  
8. Klicken Sie auf **Fertig stellen**, und **veröffentlichen** Sie die Topologie. 
    
9. Führen Sie die Schritte in der Bereitstellungsdokumentation aus, um die Dateien auf dem neuen Edgeserver zu installieren, Zertifikate zu konfigurieren und die Dienste zu starten. 
<!-- [Install Edge Servers for Skype for Business Server 2019](../deployment/deploying-external-user-access/install-edge-servers.md) in -->
    
Es ist sehr wichtig, dass Sie die Richtlinien in den Themen in der Bereitstellungsdokumentation befolgen. Dieser Abschnitt enthält lediglich einige Anleitungen zu Konfigurationseinstellungen beim Installieren dieser Serverrollen. 
<!-- [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) -->
  
Sie sollten jetzt einen Legacy-Edgeserver parallel zu einer Skype for Business Server 2019 Edge Server-Bereitstellung bereitstellen. Überprüfen Sie, ob beide Bereitstellungen ordnungsgemäß ausgeführt werden, Dienste gestartet sind, und Sie können jede Bereitstellung verwalten, bevor Sie in die nächste Phase wechseln. 
  

