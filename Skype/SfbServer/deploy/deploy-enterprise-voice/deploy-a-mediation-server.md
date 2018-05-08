---
title: Bereitstellen eines Vermittlungsservers im Topologie-Generator in Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
description: 'Zusammenfassung: Informationen Sie zum Definieren und Bereitstellen eines Vermittlungsservers im Topologie-Generator in Skype für Business Server 2015.'
ms.openlocfilehash: 1923b75f36690cf6c4ab49cb69591032b188ace5
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="deploy-a-mediation-server-in-topology-builder-in-skype-for-business-server-2015"></a>Bereitstellen eines Vermittlungsservers im Topologie-Generator in Skype for Business Server 2015
 
**Zusammenfassung:** Informationen Sie zum Definieren und Bereitstellen eines Vermittlungsservers im Topologie-Generator in Skype für Business Server 2015.
  
Die Enterprise-VoIP-Arbeitslast, einwahlkonferenzen und erweiterte Enterprise-VoIP-Anwendungen (reaktionsgruppenanwendung, anrufparkanwendung, die anrufsteuerung (CAC) usw.) sind in Front-End-Pools verfügbar. Die Funktionalität des Vermittlungsservers ist in der Front-End-Server integriert. Einen separaten eigenständigen Vermittlungsserver ist nicht erforderlich. 
  
Die einzige Ausnahme stellt die Konfiguration eines SIP-Trunks zum Herstellen einer Verbindung mit einem Session Border Controller (SBC) für einen Anbieter von Internettelefoniediensten dar. Zum Verbinden Ihrer Enterprise-VoIP-Infrastruktur mit SIP-Trunk-Dienstanbieter müssen einen getrennten Vermittlungsserver bereitgestellt werden.
  
Die Verbindung zwischen Skype für Business Server (entweder ein Vermittlungsserver gemeinsam auf einem Front-End-Pool oder den eigenständigen Vermittlungsserver ausgeführt) und einem Gateway wird als eine logische Zuordnung mit dem Namen eines Trunks definiert. In den Themen in diesem Abschnitt beschreiben einen Trunk zu definieren und wie Sie einen eigenständigen Vermittlungsserver bereitstellen, wenn Sie einen SIP-Trunk herstellen.
  
## <a name="define-a-mediation-server-in-topology-builder"></a>Definieren eines Vermittlungsservers im Topologie-Generator

Sie können Vermittlungsserver als auf einem Front-End-Pool verbundenen Rolle hinzufügen oder ein separates eigenständigen vermittlungsserverpool definieren.
  
### <a name="to-add-a-mediation-server-to-a-front-end-pool"></a>So fügen Sie einen Vermittlungsserver auf einem Front-End-Pool hinzu

1. Starten des Topologie-Generators: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype für Business Server 2015**, und klicken Sie dann auf **Skype für Business Server 2015Topology-Generator**.
    
2. Erweitern Sie im Topologie-Generator in der Konsolenstruktur den Namen der Website für die Sie einen Front-End-Pool definieren möchten.
    
3. In der Konsolenstruktur mit der rechten Maustaste in des Typs des gewünschten Front-End-Pool, und klicken Sie dann auf **neue Front-End-Pool..**.
    
4. Navigieren Sie durch den Assistenten **Neuen Front-End-Pool definieren**, bis Sie die Seite **Verbundene Serverrollen auswählen** erreichen.
    
5. **Verbundene Serverrollen auswählen**aktivieren Sie die Option **Mediation Server verbinden**.
    
    > [!NOTE]
    > Wenn der Typ des Front-End-Pools, den Sie ausgewählt haben die Enterprise Edition ist, dann wird die Mediation Server-Komponente auf allen Front-End-Servern von diesem Front-End-Pool installiert. 
  
    > [!NOTE]
    > **Nächster hoppool** vom Vermittlungsserver verwendet werden den Front-End-Pool, in dem der Vermittlungsserver verbunden ist.
  
    > [!NOTE]
    > Der **Edge-Pool** für die vom Vermittlungsserver werden auf den gleichen Edge-Pool verknüpft ist, mit dem Front-End-Pool, in dem der Vermittlungsserver verbunden ist.
  
6. Klicken Sie auf **Als Standardeinstellung festlegen** , um diesem Front-End-Pool verwenden, um Anrufe an das Telefonfestnetz weiterzuleiten.
    
7. Klicken Sie auf **Fertig stellen** , wenn Sie einen oder mehrere Peers auf den Front-End-Pool zuordnen fertig sind.
    
    > [!NOTE]
    > Bevor Sie mit dem nächsten Schritt des Bereitstellungsprozesses für Enterprise-VoIP fortfahren, stellen Sie sicher, dass der Mediation Server-Pool (d. h. Front-End-Pool mit der Komponente Vermittlungsserver gemeinsam ausgeführt) die FQDNs verwendet, die Sie angegeben haben. 
  
8. Maustaste auf den Knoten **Skype für Business Server 2015** , und klicken Sie dann auf **Topologie veröffentlichen**.
    
### <a name="to-add-a-standalone-mediation-server"></a>So fügen Sie einen eigenständigen Vermittlungsserver hinzu

1. Starten des Topologie-Generators: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype für Business Server 2015**, und klicken Sie dann auf **Skype für Business Server 2015Topology-Generator**.
    
2. Erweitern Sie im Topologie-Generator in der Konsolenstruktur den Namen der Website für die Sie einen Vermittlungsserver definieren möchten.
    
3. In der Konsolenstruktur mit der rechten Maustaste in des Knotens **vermittlungspools** , und klicken Sie dann auf **vermittlungsserverpool**.
    
4. Geben Sie im **Neuen Vermittlungspool definieren**den Vermittlungsserver Pool vollqualifizierten Domänennamen (FQDN).
    
5. Führen Sie anschließend eine der folgenden Aktionen aus:
    
   - Wenn Sie mehrere Vermittlungsserver im Pool, um hohe Verfügbarkeit bereitstellen möchten, wählen Sie **Pool mit mehreren Computern**.
    
    > [!NOTE]
    > Sie müssen bereitstellen (... /.. / plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) vermittlungsserverpools unterstützt, die mehrere Mediation Server verfügen.
  
   - Wenn Sie nur einen Vermittlungsserver im Pool bereitstellen, da Sie keine hohe Verfügbarkeit erforderlich möchten, wählen Sie **Pool mit einem Computer**. Überspringen Sie den folgenden Schritt.
    
6. Wenn Sie im vorherigen Schritt **Pool mit mehreren Computern** ausgewählt haben, klicken Sie in **Computer in diesem Pool definieren** auf **Computer-FQDN**, geben Sie die FQDNs der einzelnen Server innerhalb des Pools ein und klicken Sie anschließend auf **Hinzufügen**. Wiederholen Sie diesen Schritt für alle anderen Vermittlungsserver, die Sie dem Pool hinzufügen möchten. Nachdem Sie alle Computer im Pool definiert haben, klicken Sie auf **Weiter**.
    
7. Klicken Sie auf der Seite **Auswählen des nächsten Hops** klicken Sie auf **Nächster hoppool**, klicken Sie auf den FQDN des Front-End-Pools, die diesem Pool Mediation Server verwenden, und klicken Sie dann auf **Weiter**.
    
8. Führen Sie auf der Seite **Edgeserver auswählen** einen der folgenden Schritte aus:
    
   - Wenn Sie PSTN-Konnektivität für externe Benutzer für Enterprise-VoIP aktiviert bereitstellen möchten unter **Wählen Sie Edgepool, die von diesem Vermittlungsserver verwendet wird**, klicken Sie auf den FQDN des Edge-Server-Pools, der diesen Mediation Server-Pool verwendet wird, um PSTN-Anbindung zu bieten Diese externen Benutzer, und klicken Sie dann auf **Weiter**.
    
   - Wenn Sie nicht vorhaben, damit externe Benutzer für Enterprise-VoIP können oder nicht PSTN-Anbindung für Benutzer bereitstellen, wenn sie außerhalb des internen Netzwerks sind möchten, klicken Sie auf **Weiter**.
    
9. Maustaste auf den Knoten **Skype für Business Server 2015** , und klicken Sie dann auf **Topologie veröffentlichen**.
    
## <a name="define-the-mediation-server-listening-ports"></a>Definieren Sie die Mediation Server überwacht Ports

Führen Sie die Schritte in diesem Thema zum Topologie-Generator verwenden, um die Überwachungsports Definieren eines Vermittlungsservers oder Pool werden eingehende Verbindungen von einem gatewaypeer akzeptiert.
  
### <a name="to-modify-the-mediation-server-listening-ports"></a>So ändern Sie die Mediation Server überwacht Ports

1. Starten des Topologie-Generators: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype für Business Server 2015**, und klicken Sie dann auf **Skype für Business Server 2015Topology-Generator**.
    
2. Im Topologie-Generator, in der Konsolenstruktur erweitern Sie den Knoten **vermittlungspools** , und mit der rechten Maustaste in den zuvor erstellten Vermittlungsserver.
    
3. Standardmäßig sind die SIP-Überwachungsports auf dem Vermittlungsserver für TLS-Datenverkehr von Skype für Business Server 5070 und 5067 für TLS-Datenverkehr von Kollegen (z. B. Gateways, PBXes oder SBCs). Der TCP-Port ist standardmäßig deaktiviert. Wenn Sie über Gateways verfügen, die TLS nicht unterstützen, müssen Sie den TCP-Port aktivieren.
    
4. Geben Sie die gewünschten TLS oder TCP-überwachungsportbereich der Vermittlungsserver eingehende Verbindungen von PSTN-Gateways akzeptiert wird.
    
    > [!NOTE]
    > Wenn die Option **TCP-Port aktivieren** nicht ausgewählt wird, ist die Eingabe des TCP-Portbereichs nicht erforderlich. Diese Einstellung ist optional.
  

