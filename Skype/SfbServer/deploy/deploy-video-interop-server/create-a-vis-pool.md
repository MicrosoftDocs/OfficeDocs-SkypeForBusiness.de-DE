---
title: Erstellen eines VIS-Pools in Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd8c4f7-057f-4360-8e3e-ec29b58f16a8
description: 'Zusammenfassung: Erstellen Sie einen Video Interop-Serverpool in Skype für Business Server 2015 des Topologie-Generators.'
ms.openlocfilehash: 89fcdf34480bc9b99295993d28e32ca547f07893
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2018
---
# <a name="create-a-vis-pool-in-skype-for-business-server-2015"></a>Erstellen eines VIS-Pools in Skype for Business Server 2015
 
**Zusammenfassung:** Erstellen Sie einen Video Interop-Serverpool in Skype für Business Server 2015 des Topologie-Generators.
  
### <a name="create-a-vis-or-vis-pool-using-topology-builder"></a>Erstellen eines VIS oder VIS-Pools mithilfe des Topologie-Generators

1. Öffnen Sie den Topologie-Generator auf dem Front-End-Server. Im linken Bereich des Topologie-Generator, klicken Sie mit der rechten Maustaste auf ** Video Interop Server Pools **, und wählen Sie **Neue Video Interop-Serverpool**. 
    
2. Ein Assistenten zum **Erstellen einer neuen Video Interop-Serverpool** wird geöffnet. Geben Sie den Pool-FQDN für den neuen Video Interop-Server, und wählen Sie entweder **diesem Pool einen Server** oder **Pool verfügt über mehrere Server** basierend auf Ihrer Anforderung aus, drücken Sie dann auf **Weiter**.
    
    Wenn Sie einen Video Interop-Serverpool, um hohe Verfügbarkeit bereitstellen möchten, wählen Sie **in diesem Pool verfügt über mehrere Server**. Bedenken Sie bei dieser Option Folgendes: 
    
    - Sie müssen die DNS-Lastenausgleich zur Unterstützung von Video Interop-Server-Pools bereitstellen. 
    
   - Geben Sie auf der nächsten Seite unter **Computer in diesem Pool definieren** im Textfeld den **Computer-FQDN** des jeweiligen Computers im Pool ein und klicken Sie dann auf **Hinzufügen**. Wiederholen Sie diesen Schritt, um einen weiteren Video Interop Server zum Pool hinzuzufügen. Wenn Sie alle Computer im Pool definiert haben, klicken Sie auf **Weiter**.
    
    Wenn Sie nur ein Video Interop-Server im Pool bereitstellen, da Sie keine hohe Verfügbarkeit erforderlich möchten, wählen Sie **in diesem Pool hat einen Server** aus, und klicken Sie auf **Weiter**.
    
3. Wählen Sie in der Dropdownliste den nächsten Hoppool/FE aus und klicken Sie auf **Weiter**.
    
4. Wählen Sie einen Edgepool aus, dem Sie den VIS zuordnen möchten, und klicken Sie auf **Fertig stellen**.
    
5. Legen Sie einen TCP- oder TLS-Port fest.
    
    Wählen Sie den neu hinzugefügten Video Interop-Server aus der Topologie-Generator im linken, klicken Sie rechten Maustaste darauf, und wählen Sie **Eigenschaften bearbeiten**. Aktivieren oder aktualisieren Sie den TCP- oder TLS-Port entsprechend Ihrer Anforderung und wählen Sie **OK**. Obwohl TLS standardmäßig aktiviert ist, wurde nur TCP vollständig mit CUCM getestet.
    
6. Wählen Sie ein Videogateway aus. Erweitern Sie hierfür „Freigegebene Komponenten“, klicken Sie mit der rechten Maustaste auf **Videogateways** und wählen Sie **Neues Videogateway**.
    
7. Geben Sie den FQDN des Videogateways oder die IP-Adresse ein. Das Videogateway kann sich in einer Unterdomäne oder einer anderen Domäne befinden. Der von den Videotelekonferenzgeräten Ihres Systems verwendete CUCM dient als Videogateway.
    
8. Wählen Sie ggf. IPv4 oder IPv6 aus. Sie können alle konfigurierten IP-Adressen verwenden oder die Dienstnutzung auf die ausgewählten IP-Adressen beschränken.
    
9. Wählen Sie den Überwachungsport des Videogateways aus. Wählen Sie das Transportprotokoll (TCP oder TLS), und verknüpfen Sie ihn mit einem Video Interop-Server, der für einen SIP-Trunk video eingerichtet ist. Das Transportprotokoll für das Videogateway sollte mit dem für den VIS konfigurierten Transportprotokoll übereinstimmen.
    
10. Ein entsprechender Video-SIP-Trunk wird nach Abschluss des obigen Schritts hinzugefügt. Klicken Sie mit der rechten Maustaste auf den Video-SIP-Trunk und wählen Sie den soeben hinzugefügten Trunk aus. Die video-SIP-Trunk-Name, Video Interop-Server-SIP-Transportprotokoll zugeordnet und kann alle Port geändert werden. 
    
    > [!NOTE]
    >  Ein Video Interop-Server unterstützt 1: n-Trunks. Daher können mehrere Trunks die zugeordnet, mit einem einzelnen Server zur Video-Interop, wobei jeden Trunk auf einem anderen Video Gateway beendet werden hinzugefügt. Die Einschränkung ist einem bestimmten Gateway Video nur einen einzigen Trunk verfügt, die an die Skype für Business Server-Bereitstellung definiert werden kann.
  
11. Veröffentlichen Sie das Topologiedokument gemäß [Erstellen und veröffentlichen Sie die neue Topologie in Skype für Business Server 2015](../../deploy/install/create-and-publish-new-topology.md).
    
    > [!NOTE]
    > Um ausfallsicherheit zu verbessern, sollten Sie einen zweiten Interop Videoserver oder gegenüber Pool oder einem Front-End-Sicherungspool konfigurieren. Weitere Informationen hierzu finden Sie unter [Resiliency mechanisms](../../plan-your-deployment/video-interop-server.md#resiliency).
  
Alle mithilfe des Topologie-Generators durchgeführten Aufgaben sollten jetzt abgeschlossen sein. Installieren Sie nun die Software auf dem neuen VIS-Server bzw. den neuen VIS-Servern.
## <a name="see-also"></a>Siehe auch

#### 

[Bereitstellen der Serverrolle gegenüber in Skype für Business Server 2015](deploy-the-vis-server-role.md)

[Planen der Interop-Videoserver in Skype für Business Server 2015](../../plan-your-deployment/video-interop-server.md)
  
[Erstellen Sie und veröffentlichen Sie die neue Topologie in Skype für Business Server 2015](../../deploy/install/create-and-publish-new-topology.md)

