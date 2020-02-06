---
title: Erstellen eines VIS-Pools in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd8c4f7-057f-4360-8e3e-ec29b58f16a8
description: 'Zusammenfassung: Erstellen eines Video-Interop-Server Pools in Skype for Business Server mithilfe des Topologie-Generators.'
ms.openlocfilehash: 474752253312b58b87a3d01f445bd93eabdaf203
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798052"
---
# <a name="create-a-vis-pool-in-skype-for-business-server"></a>Erstellen eines VIS-Pools in Skype for Business Server
 
**Zusammenfassung:** Erstellen Sie einen Video-Interop-Serverpool in Skype for Business Server mithilfe des Topologie-Generators.
  
### <a name="create-a-vis-or-vis-pool-using-topology-builder"></a>Erstellen eines VIS oder VIS-Pools mithilfe des Topologie-Generators

1. Öffnen Sie den Topologie-Generator auf dem Front-End-Server. Klicken Sie im linken Bereich des Topologie-Generators mit der rechten Maustaste auf **Video-Interop-Server Pools** , und wählen Sie **neuer Video-Interop-Server Pool**aus. 
    
2. Dadurch wird ein Assistent zum **Erstellen eines neuen Video-Interop-Serverpools** geöffnet. Geben Sie den Pool-FQDN für den neuen Video-Interop-Server ein, und wählen Sie entweder **dieser Pool hat einen Server** oder **dieser Pool verfügt über mehrere Server** basierend auf Ihrer Anforderung und dann **weiter**.
    
    Wenn Sie einen Video-Interop-Server Pool bereitstellen möchten, um eine höhere Verfügbarkeit zu gewährleisten, wählen Sie **dieser Pool hat mehrere Server**. Bedenken Sie bei dieser Option Folgendes: 
    
    - Sie müssen DNS-Lastenausgleich bereitstellen, um Video-Interop-Server Pools zu unterstützen. 
    
   - Geben Sie auf der nächsten Seite unter **Computer in diesem Pool definieren** im Textfeld den **Computer-FQDN** des jeweiligen Computers im Pool ein und klicken Sie dann auf **Hinzufügen**. Wiederholen Sie diesen Schritt, um einen weiteren Video-Interop-Server zum Pool hinzuzufügen. Wenn Sie alle Computer im Pool definiert haben, klicken Sie auf **Weiter**.
    
     Wenn Sie nur einen Video-Interop-Server im Pool bereitstellen möchten, weil Sie keine höhere Verfügbarkeit benötigen, wählen Sie **diesen Pool hat einen Server** aus, und drücken Sie dann auf **weiter**.
    
3. Wählen Sie in der Dropdownliste den nächsten Hoppool/FE aus und klicken Sie auf **Weiter**.
    
4. Wählen Sie einen Edgepool aus, dem Sie den VIS zuordnen möchten, und klicken Sie auf **Fertig stellen**.
    
5. Legen Sie einen TCP- oder TLS-Port fest.
    
    Wählen Sie im linken Bereich von Topology Builder den neu hinzugefügten Video-Interop-Server aus, klicken Sie mit der rechten Maustaste darauf, und wählen Sie **Eigenschaften bearbeiten**aus. Aktivieren oder aktualisieren Sie den TCP- oder TLS-Port entsprechend Ihrer Anforderung und wählen Sie **OK**. Obwohl TLS standardmäßig hinzugefügt wird, wurde nur TCP mit Cisco Unified Communications Manager (CallManager oder CUCM) vollständig getestet.
    
6. Wählen Sie ein Videogateway aus. Erweitern Sie hierfür „Freigegebene Komponenten“, klicken Sie mit der rechten Maustaste auf **Videogateways** und wählen Sie **Neues Videogateway**.
    
7. Geben Sie den FQDN des Videogateways oder die IP-Adresse ein. Das Videogateway kann sich in einer Unterdomäne oder einer anderen Domäne befinden. Der von den Videotelekonferenzgeräten Ihres Systems verwendete CUCM dient als Videogateway.
    
8. Wählen Sie ggf. IPv4 oder IPv6 aus. Sie können alle konfigurierten IP-Adressen verwenden oder die Dienstnutzung auf die ausgewählten IP-Adressen beschränken.
    
9. Wählen Sie den Überwachungsport des Videogateways aus. Wählen Sie das Transport Protokoll (TCP oder TLS) aus, und ordnen Sie es einem Video-Interop-Server zu, der für einen Video-SIP-Trunk eingerichtet ist. Das Transportprotokoll für das Videogateway sollte mit dem für den VIS konfigurierten Transportprotokoll übereinstimmen.
    
10. Ein entsprechender Video-SIP-Trunk wird nach Abschluss des obigen Schritts hinzugefügt. Klicken Sie mit der rechten Maustaste auf den Video-SIP-Trunk und wählen Sie den soeben hinzugefügten Trunk aus. Der Name des Video-SIP-Trunks, der zugehörige Video-Interop-Server, das SIP-Transport Protokoll und der Port können alle geändert werden. 
    
    > [!NOTE]
    >  Ein Video-Interop-Server unterstützt 1: N Trunks. Daher können mehrere Trunks hinzugefügt werden, die einem einzelnen Video-Interop-Server zugeordnet sind, wobei jeder trunk auf einem anderen Video Gateway beendet wird. Die Einschränkung besteht darin, dass ein bestimmtes Video Gateway nur einen trunk enthält, der für die Bereitstellung von Skype for Business Server definiert werden kann.
  
11. Veröffentlichen Sie das Topologie-Dokument wie unter [Erstellen und Veröffentlichen einer neuen Topologie in Skype for Business Server 2015](../../deploy/install/create-and-publish-new-topology.md)beschrieben.
    
    > [!NOTE]
    > Um die Widerstandsfähigkeit zu verbessern, können Sie einen zweiten Video-Interop-Server oder VIS-Pool oder einen Backup-Front-End-Pool konfigurieren. Weitere Informationen finden Sie unter [Resilienz-Mechanismen](../../plan-your-deployment/video-interop-server.md#resiliency) .
  
Alle mit dem Topologie-Generator ausgeführten Aufgaben sollten nun abgeschlossen sein. Fahren Sie mit der Installation der Software auf dem neuen VIS-Server oder-Server fort.
## <a name="see-also"></a>Siehe auch

[Bereitstellen der VIS-Serverrolle in Skype for Business Server](deploy-the-vis-server-role.md)

[Planen des Video-Interop-Servers in Skype for Business Server](../../plan-your-deployment/video-interop-server.md)
  
[Erstellen und Veröffentlichen einer neuen Topologie in Skype for Business Server 2015](../../deploy/install/create-and-publish-new-topology.md)
