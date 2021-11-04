---
title: Bereitstellen eines Vermittlungsservers im Topologie-Generator in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
description: 'Zusammenfassung: Erfahren Sie, wie Sie einen Vermittlungsserver im Topologie-Generator in Skype for Business Server definieren und bereitstellen.'
ms.openlocfilehash: 9eb3f00d8530739b3a4e9986da14038ff7d6ed26
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60764893"
---
# <a name="deploy-a-mediation-server-in-topology-builder-in-skype-for-business-server"></a>Bereitstellen eines Vermittlungsservers im Topologie-Generator in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie einen Vermittlungsserver im Topologie-Generator in Skype for Business Server definieren und bereitstellen.
  
Die Enterprise-VoIP Workload, Einwahlkonferenzen und erweiterte Enterprise-VoIP Anwendungen (Reaktionsgruppenanwendung, Anwendung zum Parken von Anrufen, Anrufsteuerung usw.) sind in Front-End-Pools verfügbar. Die Funktionalität des Vermittlungsservers ist in den Front-End-Server integriert. Ein separater eigenständiger Vermittlungsserver ist nicht erforderlich. 
  
Die einzige Ausnahme stellt die Konfiguration eines SIP-Trunks zum Herstellen einer Verbindung mit einem Session Border Controller (SBC) für einen Anbieter von Internettelefoniediensten dar. Um ihre Enterprise-VoIP Infrastruktur mit Ihrem SIP-Trunkanbieter zu verbinden, muss ein separater Vermittlungsserver bereitgestellt werden.
  
Die Verbindung zwischen Skype for Business Server (entweder einem Vermittlungsserver, der in einem Front-End-Pool oder einem eigenständigen Vermittlungsserver verbunden ist) und einem Gateway wird als logische Zuordnung definiert, die als Trunk bezeichnet wird. In den Themen in diesem Abschnitt werden die Definition eines Trunks und die Bereitstellung eines eigenständigen Vermittlungsservers beschrieben, wenn Sie eine Verbindung mit einem SIP-Trunk herstellen.
  
## <a name="define-a-mediation-server-in-topology-builder"></a>Definieren eines Vermittlungsservers im Topologie-Generator

Sie können den Vermittlungsserver als gemeinsam zugeordnete Rolle in einem Front-End-Pool hinzufügen oder einen separaten eigenständigen Vermittlungsserverpool definieren.
  
### <a name="to-add-a-mediation-server-to-a-front-end-pool"></a>So fügen Sie einem Front-End-Pool einen Vermittlungsserver hinzu

1. Topologie-Generator starten: Klicken Sie auf **"Start",** auf **"Alle Programme",** auf **Skype for Business Server 2015** und dann auf **Skype for Business Server 2015Topology Builder.**
    
2. Erweitern Sie im Topologie-Generator in der Konsolenstruktur den Namen des Standorts, für den Sie einen Front-End-Pool definieren möchten.
    
3. Klicken Sie in der Konsolenstruktur mit der rechten Maustaste auf den gewünschten Front-End-Pooltyp, und klicken Sie dann auf **"Neuer Front-End-Pool".**
    
4. Navigieren Sie durch den Assistenten **Neuen Front-End-Pool definieren**, bis Sie die Seite **Verbundene Serverrollen auswählen** erreichen.
    
5. Aktivieren Sie unter **"Gemeinsam zugeordnete Serverrollen auswählen"** die Option **"Vermittlungsserver** verbinden".
    
    > [!NOTE]
    > Wenn der ausgewählte Front-End-Pooltyp der Enterprise Edition ist, wird die Vermittlungsserverkomponente auf allen Front-End-Servern dieses Front-End-Pools installiert. 
  
    > [!NOTE]
    > Der vom Vermittlungsserver verwendete **Next-Hoppool** ist der Front-End-Pool, in dem der Vermittlungsserver verbunden ist.
  
    > [!NOTE]
    > Der vom Vermittlungsserver verwendete **Edgepool** ist der gleiche Edgepool, der dem Front-End-Pool zugeordnet ist, in dem der Vermittlungsserver verbunden ist.
  
6. Klicken Sie auf **"Als Standard festlegen",** um diesen Front-End-Pool zu verwenden, um Anrufe an das Telefonfestnetz weiterzuleiten.
    
7. Klicken Sie auf **"Fertig stellen",** wenn Sie das Zuordnen eines oder mehrerer Peers zum Front-End-Pool abgeschlossen haben.
    
    > [!NOTE]
    > Bevor Sie mit dem nächsten Schritt im Enterprise-VoIP Bereitstellungsprozess fortfahren, stellen Sie sicher, dass der Vermittlungsserverpool (d. h. der Front-End-Pool mit der verbundenen Vermittlungsserverkomponente) die angegebenen FQDNs verwendet. 
  
8. Klicken Sie mit der rechten Maustaste auf den Knoten **Skype for Business Server 2015,** und klicken Sie dann auf **"Topologie veröffentlichen".**
    
### <a name="to-add-a-standalone-mediation-server"></a>So fügen Sie einen eigenständigen Vermittlungsserver hinzu

1. Topologie-Generator starten: Klicken Sie auf **"Start",** auf **"Alle Programme",** auf **Skype for Business Server 2015** und dann auf **Skype for Business Server 2015Topology Builder.**
    
2. Erweitern Sie im Topologie-Generator in der Konsolenstruktur den Namen des Standorts, für den Sie einen Vermittlungsserver definieren möchten.
    
3. Klicken Sie in der Konsolenstruktur mit der rechten Maustaste auf den Knoten **"Vermittlungspools",** und klicken Sie dann auf **"Vermittlungsserverpool".**
    
4. Geben Sie unter **"Neuen Vermittlungspool definieren"** den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Vermittlungsserverpools ein.
    
5. Führen Sie anschließend eine der folgenden Aktionen aus:
    
   - Wenn Sie mehrere Vermittlungsserver im Pool bereitstellen möchten, um hohe Verfügbarkeit bereitzustellen, wählen Sie Pool **mit mehreren Computern** aus.
    
     > [!NOTE]
     > Sie müssen [bereitstellen,](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) um Vermittlungsserverpools mit mehreren Vermittlungsservern zu unterstützen.
  
   - Wenn Sie nur einen Vermittlungsserver im Pool bereitstellen möchten, da keine hohe Verfügbarkeit erforderlich ist, wählen Sie **"Pool mit einem Computer"** aus. Überspringen Sie den folgenden Schritt.
    
6. Wenn Sie im vorherigen Schritt **Pool mit mehreren Computern** ausgewählt haben, klicken Sie in **Computer in diesem Pool definieren** auf **Computer-FQDN**, geben Sie die FQDNs der einzelnen Server innerhalb des Pools ein, und klicken Sie anschließend auf **Hinzufügen**. Wiederholen Sie diesen Schritt für alle anderen Vermittlungsserver, die Sie dem Pool hinzufügen möchten. Nachdem Sie alle Computer im Pool definiert haben, klicken Sie auf **Weiter**.
    
7. Klicken Sie auf der Seite **"Nächsten Hop auswählen"** auf **"Nächster Hoppool",** klicken Sie auf den FQDN des Front-End-Pools, der diesen Vermittlungsserverpool verwendet, und klicken Sie dann auf **"Weiter".**
    
8. Führen Sie auf der Seite **Edgeserver auswählen** einen der folgenden Schritte aus:
    
   - Wenn Sie für Enterprise-VoIP aktivierte externe Benutzer PSTN-Konnektivität bereitstellen möchten, klicken Sie unter **"Edgepool auswählen", der von diesem Vermittlungsserver verwendet wird,** auf den FQDN des Edgeserverpools, der diesen Vermittlungsserverpool verwendet, um diesen externen Benutzern PSTN-Konnektivität bereitzustellen, und klicken Sie dann auf **"Weiter".**
    
   - Wenn Sie nicht planen, externe Benutzer für Enterprise-VoIP zu aktivieren, oder wenn Sie Benutzern keine PSTN-Konnektivität bereitstellen möchten, wenn sie sich außerhalb des internen Netzwerks befinden, klicken Sie auf **"Weiter".**
    
9. Klicken Sie mit der rechten Maustaste auf den Knoten **Skype for Business Server 2015,** und klicken Sie dann auf **"Topologie veröffentlichen".**
    
## <a name="define-the-mediation-server-listening-ports"></a>Definieren der Vermittlungsserver-Überwachungsports

Führen Sie die Schritte in diesem Thema aus, um den Topologie-Generator zum Definieren der Überwachungsports zu verwenden, die ein Vermittlungsserver oder Pool eingehende Verbindungen von einem Gatewaypeer akzeptiert.
  
### <a name="to-modify-the-mediation-server-listening-ports"></a>So ändern Sie die Überwachungsports des Vermittlungsservers

1. Topologie-Generator starten: Klicken Sie auf **"Start",** auf **"Alle Programme",** auf **Skype for Business Server 2015** und dann auf **Skype for Business Server 2015Topology Builder.**
    
2. Erweitern Sie im Topologie-Generator in der Konsolenstruktur den Knoten **"Vermittlungspools",** und klicken Sie mit der rechten Maustaste auf den zuvor erstellten Vermittlungsserver.
    
3. Standardmäßig sind die SIP-Überwachungsports auf dem Vermittlungsserver 5070 für TLS-Datenverkehr von Skype for Business Server und 5067 für TLS-Datenverkehr von Peers (z. B. Gateways, Nebenstellenanlagen oder SBCs). Der TCP-Port ist standardmäßig deaktiviert. Wenn Sie über Gateways verfügen, die TLS nicht unterstützen, müssen Sie den TCP-Port aktivieren.
    
4. Geben Sie den gewünschten TLS- oder TCP-Überwachungsportbereich an, der vom Vermittlungsserver eingehende Verbindungen von PSTN-Gateways akzeptiert.
    
    > [!NOTE]
    > Wenn die Option **TCP-Port aktivieren** nicht ausgewählt wird, ist die Eingabe des TCP-Portbereichs nicht erforderlich. Diese Einstellung ist optional.
  

