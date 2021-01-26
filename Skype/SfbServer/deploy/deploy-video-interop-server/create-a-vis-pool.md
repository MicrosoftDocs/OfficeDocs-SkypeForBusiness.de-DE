---
title: Erstellen eines VIS-Pools in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd8c4f7-057f-4360-8e3e-ec29b58f16a8
description: 'Zusammenfassung: Erstellen sie einen Video-Inop-Serverpool in Skype for Business Server mithilfe des Topologie-Generators.'
ms.openlocfilehash: 7c6f45b232151d99cbce169826c8110cf4a8d494
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802055"
---
# <a name="create-a-vis-pool-in-skype-for-business-server"></a>Erstellen eines VIS-Pools in Skype for Business Server
 
**Zusammenfassung:** Erstellen Eines Video-Inop-Serverpools in Skype for Business Server mithilfe des Topologie-Generators.
  
### <a name="create-a-vis-or-vis-pool-using-topology-builder"></a>Erstellen eines VIS- oder VIS-Pools mithilfe des Topologie-Generators

1. Öffnen Sie den Topologie-Generator auf dem Front-End-Server. Klicken Sie im linken Bereich des  Topologie-Generators mit der rechten Maustaste auf videointeopserverpools, und wählen Sie **"Neuer Video-Inop-Serverpool" aus.** 
    
2. Dadurch wird der Assistent zum Erstellen **eines neuen Assistenten für den Video-Inop-Serverpool** geöffnet. Geben Sie den Pool-FQDN für den neuen Video-In-Op-Server an, und wählen Sie entweder **diesen** Pool mit einem Server aus, oder dieser Pool verfügt basierend auf Ihrer Anforderung über mehrere Server, und drücken Sie dann die nächste **.** 
    
    Wenn Sie einen Video-Inop-Serverpool bereitstellen möchten, um hohe Verfügbarkeit zu bieten, wählen Sie **diesen Pool mit mehreren Servern aus.** Beachten Sie bei dieser Option, dass: 
    
    - Sie müssen den DNS-Lastenausgleich bereitstellen, um Video-Interop-Serverpools zu unterstützen. 
    
   - Geben Sie auf der nächsten Seite unter "Computer **in** diesem Poolelement definieren" den **Computer-FQDN** der einzelnen Server im Pool in das Textfeld ein, und klicken Sie dann auf "Hinzufügen".  Wiederholen Sie diesen Schritt, um dem Pool einen weiteren Videointeopserver hinzuzufügen. Wenn Sie alle Computer im Pool definiert haben, drücken Sie die nächste **.**
    
     Wenn Sie nur einen Videointeopserver im Pool bereitstellen möchten, da keine hohe Verfügbarkeit erforderlich ist, wählen Sie "Dieser **Pool** hat einen Server" aus, und drücken Sie dann **"Weiter".**
    
3. Wählen Sie den nächsten Hoppool/FE aus der Dropdownliste aus, und drücken Sie die **nächste .**
    
4. Wählen Sie einen Edgepool aus, der dem VIS zugeordnet werden soll, und drücken Sie **"Fertig stellen".**
    
5. Festlegen eines TCP- oder TLS-Ports.
    
    Wählen Sie den neu hinzugefügten Video-Inop-Server im linken Bereich des Topologie-Generators aus, klicken Sie mit der rechten Maustaste darauf, und wählen Sie **"Eigenschaften bearbeiten" aus.** Aktivieren oder aktualisieren Sie den TCP- oder TLS-Port nach Ihren Anforderungen, und wählen Sie **OK aus.** Obwohl TLS standardmäßig hinzugefügt wird, wurde nur TCP vollständig mit Cisco Unified Communications Manager (CallManager oder CUCM) getestet.
    
6. Fügen Sie ein Videogateway hinzu. Erweitern Sie dazu freigegebene Komponenten,  klicken Sie mit der rechten Maustaste auf Videogateways, und wählen Sie **"Neues Videogateway" aus.**
    
7. Geben Sie den FQDN oder die IP-Adresse des Videogateways an. Das Videogateway kann sich in einer Unterdomäne oder in einer anderen Domäne befinden. Der CUCM, der von den VTCs Ihres Systems verwendet wird, dient als Videogateway.
    
8. Wählen Sie entweder IPv4 oder IPv6 aus. Sie können alle konfigurierten IP-Adressen verwenden oder die Dienstnutzung auf ausgewählte IP-Adressen beschränken.
    
9. Wählen Sie den Abhörport des Videogateways aus. Wählen Sie das Transportprotokoll (TCP oder TLS) aus, und ordnen Sie es einem Video-Interop-Server zu, der für einen Video-SIP-Trunk eingerichtet ist. Das Transportprotokoll für das Videogateway sollte mit dem für den VIS konfigurierten Transportprotokoll übereinstimmen.
    
10. Nach Abschluss des obigen Schritts wird ein entsprechender SIP-Video-Trunk hinzugefügt. Klicken Sie mit der rechten Maustaste auf den SIP-Video-Trunk, und wählen Sie den Trunk aus, der gerade hinzugefügt wurde. Der Name des Video-SIP-Trunks, der zugehörige Video-Inop-Server, das SIP-Transport-Protokoll und der Port können geändert werden. 
    
    > [!NOTE]
    >  Ein Video-Interop-Server unterstützt 1:N-Trunks. Daher können mehrere Trunks hinzugefügt werden, die einem einzelnen Video-Interop-Server zugeordnet sind, wobei jeder Trunk an einem anderen Videogateway endet. Die Einschränkung ist, dass ein bestimmtes Videogateway nur einen Trunk hat, der für die Skype for Business Server-Bereitstellung definiert werden kann.
  
11. Veröffentlichen Sie das Topologiedokument, wie unter Erstellen und Veröffentlichen einer neuen [Topologie in Skype for Business Server 2015 beschrieben.](../../deploy/install/create-and-publish-new-topology.md)
    
    > [!NOTE]
    > Zur Verbesserung der Resilienz können Sie einen zweiten Video-Interop-Server oder -VIS-Pool oder einen Front-End-Sicherungspool konfigurieren. Weitere [Informationen finden Sie unter "Ausfallsicherheitsmechanismen".](../../plan-your-deployment/video-interop-server.md#resiliency)
  
Alle mit dem Topologie-Generator ausgeführten Aufgaben sollten nun abgeschlossen sein. Fahren Sie mit der Installation der Software auf dem neuen VIS-Server fort.
## <a name="see-also"></a>Weitere Informationen

[Bereitstellen der VIS-Serverrolle in Skype for Business Server](deploy-the-vis-server-role.md)

[Planen des Videointeopservers in Skype for Business Server](../../plan-your-deployment/video-interop-server.md)
  
[Erstellen und Veröffentlichen einer neuen Topologie in Skype for Business Server 2015](../../deploy/install/create-and-publish-new-topology.md)
