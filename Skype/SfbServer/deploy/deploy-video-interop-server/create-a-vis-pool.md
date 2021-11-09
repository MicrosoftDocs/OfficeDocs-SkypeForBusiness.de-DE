---
title: Erstellen eines VIS-Pools in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: abd8c4f7-057f-4360-8e3e-ec29b58f16a8
description: 'Zusammenfassung: Erstellen eines Video-Interoperabilität-Serverpools in Skype for Business Server mithilfe des Topologie-Generators.'
ms.openlocfilehash: 3c16381e1fceaf280571f2927d8123bc6861dd5c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60864332"
---
# <a name="create-a-vis-pool-in-skype-for-business-server"></a>Erstellen eines VIS-Pools in Skype for Business Server
 
**Zusammenfassung:** Erstellen Sie einen Video-Interoperabilität-Serverpool in Skype for Business Server mithilfe des Topologie-Generators.
  
### <a name="create-a-vis-or-vis-pool-using-topology-builder"></a>Erstellen eines VIS- oder VIS-Pools mithilfe des Topologie-Generators

1. Öffnen Sie den Topologie-Generator auf dem Front-End-Server. Klicken Sie im linken Bereich des Topologie-Generators mit der rechten Maustaste auf **Video-Interoperabilität-Serverpools,** und wählen Sie **"Neuer Video-Interoperabilität-Serverpool" aus.** 
    
2. Dadurch wird ein neuer Assistent **zum Erstellen eines Video-Interoperabilität-Serverpools** geöffnet. Geben Sie den Pool-FQDN für den neuen Video-Interoperabilitätsserver an, und wählen Sie entweder **"Dieser Pool verfügt** über einen Server" oder "Dieser Pool verfügt basierend auf Ihrer Anforderung über mehrere **Server",** und drücken Sie dann **"Weiter".**
    
    Wenn Sie einen Video-Interoperabilität-Serverpool bereitstellen möchten, um hohe Verfügbarkeit bereitzustellen, wählen Sie **Diesen Pool mit mehreren Servern** aus. Beachten Sie bei dieser Option Folgendes: 
    
    - Sie müssen den DNS-Lastenausgleich bereitstellen, um Video-Interoperabilität-Serverpools zu unterstützen. 
    
   - Geben Sie auf der nächsten Seite für **"Computer in diesem Poolelement definieren"** den **Computer-FQDN** jedes Servers im Pool in das Textfeld ein, und klicken Sie dann auf **"Hinzufügen".** Wiederholen Sie diesen Schritt, um dem Pool einen weiteren Video-Interoperabilitätsserver hinzuzufügen. Wenn Sie alle Computer im Pool definiert haben, drücken Sie **"Weiter".**
    
     Wenn Sie nur einen Video-Interoperabilitätsserver im Pool bereitstellen möchten, da keine hohe Verfügbarkeit erforderlich **ist,** wählen Sie Diesen Pool mit einem Server aus, und drücken Sie **"Weiter".**
    
3. Wählen Sie den nächsten Hoppool/FE aus der Dropdownliste aus, und drücken Sie **"Weiter".**
    
4. Wählen Sie einen Edgepool aus, der dem VIS zugeordnet werden soll, und drücken **Sie "Fertig stellen".**
    
5. Legen Sie einen TCP- oder TLS-Port fest.
    
    Wählen Sie im linken Bereich des Topologie-Generators den neu hinzugefügten Video-Interoperabilitätsserver aus, klicken Sie mit der rechten Maustaste darauf, und wählen Sie **"Eigenschaften bearbeiten"** aus. Aktivieren oder aktualisieren Sie den TCP- oder TLS-Port gemäß Ihrer Anforderung, und wählen Sie **"OK"** aus. Obwohl standardmäßig TLS hinzugefügt wird, wurde nur TCP vollständig mit Cisco Unified Communications Manager (CallManager oder CUCM) getestet.
    
6. Fügen Sie ein Videogateway hinzu. Erweitern Sie dazu freigegebene Komponenten, klicken Sie mit der rechten Maustaste auf **Videogateways,** und wählen Sie **"Neues Videogateway"** aus.
    
7. Geben Sie den FQDN oder die IP-Adresse des Videogateways an. Das Videogateway kann sich in einer Unterdomäne oder einer anderen Domäne befinden. Das von den VTCs Ihres Systems verwendete CUCM dient als Videogateway.
    
8. Wählen Sie je nach Bedarf entweder IPv4 oder IPv6 aus. Sie können alle konfigurierten IP-Adressen verwenden oder die Dienstnutzung auf ausgewählte IP-Adressen beschränken.
    
9. Wählen Sie den Überwachungsport des Videogateways aus. Wählen Sie das Transportprotokoll (TCP oder TLS) aus, und ordnen Sie es einem Video-Interoperabilitätsserver zu, der für einen Video-SIP-Trunk eingerichtet ist. Das Transportprotokoll für das Videogateway sollte mit dem für den VIS konfigurierten Transportprotokoll übereinstimmen.
    
10. Nach Abschluss des obigen Schritts wird ein entsprechender SIP-Videotrunk hinzugefügt. Klicken Sie mit der rechten Maustaste auf den SIP-Videotrunk, und wählen Sie den Trunk aus, der soeben hinzugefügt wurde. Der Name des Video-SIP-Trunks, der zugeordnete Video-Interoperabilität-Server, das SIP-Transportprotokoll und der Port können geändert werden. 
    
    > [!NOTE]
    >  Ein Video-Interoperabilität-Server unterstützt 1:N-Trunks. Daher können mehrere Trunks hinzugefügt werden, die einem einzelnen Video-Interoperabilitätsserver zugeordnet sind, wobei jeder Trunk auf einem anderen Videogateway beendet wird. Die Einschränkung besteht darin, dass ein bestimmtes Videogateway nur über einen Trunk verfügt, der für die Skype for Business Server Bereitstellung definiert werden kann.
  
11. Veröffentlichen Sie das Topologiedokument wie unter [Erstellen und Veröffentlichen einer neuen Topologie in Skype for Business Server 2015](../../deploy/install/create-and-publish-new-topology.md)beschrieben.
    
    > [!NOTE]
    > Um die Ausfallsicherheit zu verbessern, sollten Sie einen zweiten Video-Interoperabilitätsserver oder VIS-Pool oder einen Front-End-Sicherungspool konfigurieren. Weitere Informationen finden Sie unter [Resilienzmechanismen.](../../plan-your-deployment/video-interop-server.md#resiliency)
  
Alle mithilfe des Topologie-Generators ausgeführten Aufgaben sollten jetzt abgeschlossen sein. Fahren Sie mit der Installation der Software auf dem neuen VIS-Server oder den neuen Vis-Servern fort.
## <a name="see-also"></a>Siehe auch

[Bereitstellen der VIS-Serverrolle in Skype for Business Server](deploy-the-vis-server-role.md)

[Plan for Video Interop Server in Skype for Business Server](../../plan-your-deployment/video-interop-server.md)
  
[Erstellen und Veröffentlichen einer neuen Topologie in Skype for Business Server 2015](../../deploy/install/create-and-publish-new-topology.md)
