---
title: Bereitstellen eines Vermittlungsservers im Topologie-Generator in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie einen Vermittlungs Server im Topologie-Generator in Skype for Business Server definieren und bereitstellen.'
ms.openlocfilehash: 61b90bb874d96579d975a1672238a7427350a5dc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34284648"
---
# <a name="deploy-a-mediation-server-in-topology-builder-in-skype-for-business-server"></a>Bereitstellen eines Vermittlungsservers im Topologie-Generator in Skype for Business Server
 
**Zusammenfassung:** Hier erfahren Sie, wie Sie einen Vermittlungs Server im Topologie-Generator in Skype for Business Server definieren und bereitstellen.
  
Die Enterprise-VoIP-Arbeitsauslastung, Einwahlkonferenzen und erweiterte Enterprise-VoIP-Anwendungen (reaktionsgruppenanwendung, Anruf Park Anwendung, Anrufsteuerung (CAC) usw.) stehen in Front-End-Pools zur Verfügung. Die Funktionalität des Vermittlungsservers ist in den Front-End-Server integriert. Ein separater eigenständiger Vermittlungs Server ist nicht erforderlich. 
  
Die einzige Ausnahme stellt die Konfiguration eines SIP-Trunks zum Herstellen einer Verbindung mit einem Session Border Controller (SBC) für einen Anbieter von Internettelefoniediensten dar. Wenn Sie Ihre Enterprise-VoIP-Infrastruktur mit Ihrem SIP-Trunk-Anbieter verbinden möchten, muss ein separater Vermittlungs Server bereitgestellt werden.
  
Die Verbindung zwischen Skype for Business Server (einem Vermittlungsserver, der sich auf einem Front-End-Pool oder einem eigenständigen Vermittlungsserver befindet) und einem Gateway wird als logische Assoziation namens "Trunk" definiert. In den Themen in diesem Abschnitt wird beschrieben, wie Sie einen trunk definieren und wie Sie einen eigenständigen Vermittlungs Server bereitstellen, wenn Sie eine Verbindung mit einem SIP-Stamm herstellen.
  
## <a name="define-a-mediation-server-in-topology-builder"></a>Definieren eines Vermittlungsservers im Topologie-Generator

Sie können Mediation Server als zusammenhängende Rolle in einem Front-End-Pool hinzufügen oder einen separaten eigenständigen vermittlungsserverpool definieren.
  
### <a name="to-add-a-mediation-server-to-a-front-end-pool"></a>So fügen Sie einen Vermittlungs Server zu einem Front-End-Pool hinzu

1. Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype for Business Server 2015**, und klicken Sie dann auf **Skype for Business Server 2015Topology Builder**.
    
2. Erweitern Sie im Topologie-Generator in der Konsolenstruktur den Namen der Website, für die Sie einen Front-End-Pool definieren möchten.
    
3. Klicken Sie in der Konsolenstruktur mit der rechten Maustaste auf den Typ des gewünschten Front-End-Pools, und klicken Sie dann auf **neuer Front-End-Pool.**..
    
4. Navigieren Sie durch den Assistenten **Neuen Front-End-Pool definieren**, bis Sie die Seite **Verbundene Serverrollen auswählen** erreichen.
    
5. Aktivieren Sie unter **ausgewählte Serverrollen auswählen**die Option **Collocate-Vermittlungsserver**.
    
    > [!NOTE]
    > Wenn der Typ des ausgewählten Front-End-Pools die Enterprise-Edition ist, wird die Mediation Server-Komponente auf allen Front-End-Servern dieses Front-End-Pools installiert. 
  
    > [!NOTE]
    > Der vom Vermittlungsserver verwendete **Next Hop-Pool** ist der Front-End-Pool, in dem sich der Vermittlungsserver befindet.
  
    > [!NOTE]
    > Der vom Vermittlungsserver verwendete **Edge-Pool** ist derselbe Edge-Pool, der dem Front-End-Pool zugeordnet ist, in dem sich der Vermittlungsserver befindet.
  
6. Klicken Sie auf als **Standard festlegen** , um diesen Front-End-Pool zum Weiterleiten von Anrufen an das PSTN zu verwenden.
    
7. Klicken Sie auf **Fertig stellen** , wenn Sie mit dem Verknüpfen eines oder mehrerer Peers mit dem Front-End-Pool fertig sind.
    
    > [!NOTE]
    > Bevor Sie mit dem nächsten Schritt des Enterprise-VoIP-Bereitstellungsprozesses fortfahren, stellen Sie sicher, dass der vermittlungsserverpool (also der Front-End-Pool mit der Mediationsserver Komponente) die von Ihnen angegebenen FQDNs verwendet. 
  
8. Klicken Sie mit der rechten Maustaste auf den Knoten **Skype for Business Server 2015** , und klicken Sie dann auf **Topologie veröffentlichen**.
    
### <a name="to-add-a-standalone-mediation-server"></a>So fügen Sie einen eigenständigen Vermittlungsserver hinzu

1. Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype for Business Server 2015**, und klicken Sie dann auf **Skype for Business Server 2015Topology Builder**.
    
2. Erweitern Sie im Topologie-Generator in der Konsolenstruktur den Namen der Website, für die Sie einen Vermittlungs Server definieren möchten.
    
3. Klicken Sie in der Konsolenstruktur mit der rechten Maustaste auf den Knoten **Mediations Pools** , und klicken Sie dann auf **Vermittlungs Server Pool**.
    
4. Geben Sie unter **neuen Mediations Pool definieren**den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Mediation Server Pools ein.
    
5. Führen Sie anschließend eine der folgenden Aktionen aus:
    
   - Wenn Sie mehrere Vermittlungsserver im Pool bereitstellen möchten, um eine höhere Verfügbarkeit zu gewährleisten, wählen Sie den **Pool für mehrere Computer**aus.
    
     > [!NOTE]
     > Sie müssen [Bereitstellen](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) , um Vermittlungsserver Pools mit mehreren Vermittlungsservern zu unterstützen.
  
   - Wenn Sie nur einen Vermittlungs Server im Pool bereitstellen möchten, weil Sie keine höhere Verfügbarkeit benötigen, wählen Sie den **Pool für einzelne Computer**aus. Überspringen Sie den folgenden Schritt.
    
6. Wenn Sie im vorherigen Schritt **Pool mit mehreren Computern** ausgewählt haben, klicken Sie in **Computer in diesem Pool definieren** auf **Computer-FQDN**, geben Sie die FQDNs der einzelnen Server innerhalb des Pools ein und klicken Sie anschließend auf **Hinzufügen**. Wiederholen Sie diesen Schritt für alle anderen Vermittlungsserver, die Sie dem Pool hinzufügen möchten. Nachdem Sie alle Computer im Pool definiert haben, klicken Sie auf **Weiter**.
    
7. Klicken Sie auf der Seite **Nächster Hop auswählen** auf **Nächster Hop-Pool**, klicken Sie auf den FQDN des Front-End-Pools, in dem dieser Vermittlungs Server Pool verwendet wird, und klicken Sie dann auf **weiter**.
    
8. Führen Sie auf der Seite **Edgeserver auswählen** einen der folgenden Schritte aus:
    
   - Wenn Sie die PSTN-Konnektivität für externe Benutzer bereitstellen möchten, die für Enterprise-VoIP aktiviert sind, klicken Sie unter Wählen Sie den **von diesem Vermittlungsserver verwendeten Edge-Pool**aus auf den FQDN des Edgeserver-Pools, der diesen vermittlungsserverpool verwendet, um die PSTN-Konnektivität für Diese externen Benutzer aus, und klicken Sie dann auf **weiter**.
    
   - Wenn Sie nicht beabsichtigen, externe Benutzer für Enterprise-VoIP zu aktivieren, oder wenn Sie keine PSTN-Konnektivität für Benutzer bereitstellen möchten, wenn diese sich außerhalb des internen Netzwerks befinden, klicken Sie auf **weiter**.
    
9. Klicken Sie mit der rechten Maustaste auf den Knoten **Skype for Business Server 2015** , und klicken Sie dann auf **Topologie veröffentlichen**.
    
## <a name="define-the-mediation-server-listening-ports"></a>Definieren der Abhör Anschlüsse des Vermittlungsservers

Führen Sie die Schritte in diesem Thema aus, um mithilfe des Topologie-Generators die Abhör Anschlüsse zu definieren, die von einem Vermittlungs Server oder-Pool eingehende Verbindungen von einem Gateway-Peer akzeptiert werden.
  
### <a name="to-modify-the-mediation-server-listening-ports"></a>So ändern Sie die Abhör Anschlüsse des Vermittlungsservers

1. Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype for Business Server 2015**, und klicken Sie dann auf **Skype for Business Server 2015Topology Builder**.
    
2. Erweitern Sie im Topologie-Generator in der Konsolenstruktur den Knoten **Mediations Pools** , und klicken Sie mit der rechten Maustaste auf den zuvor erstellten Mediations Server.
    
3. Standardmäßig sind die SIP-Abhör Anschlüsse auf dem Vermittlungsserver 5070 für den TLS-Datenverkehr von Skype for Business Server und 5067 für TLS-Datenverkehr von Peers (wie Gateways, TK oder SBCS). Der TCP-Port ist standardmäßig deaktiviert. Wenn Sie über Gateways verfügen, die TLS nicht unterstützen, müssen Sie den TCP-Port aktivieren.
    
4. Geben Sie den gewünschten TLS-oder TCP-Überwachungs Portbereich an der Vermittlungs Server akzeptiert eingehende Verbindungen von PSTN-Gateways.
    
    > [!NOTE]
    > Wenn die Option **TCP-Port aktivieren** nicht ausgewählt wird, ist die Eingabe des TCP-Portbereichs nicht erforderlich. Diese Einstellung ist optional.
  

