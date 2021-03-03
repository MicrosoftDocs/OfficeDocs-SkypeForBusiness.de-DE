---
title: Bereitstellen eines Vermittlungsservers im Topologie-Generator in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
description: 'Zusammenfassung: Informationen zum Definieren und Bereitstellen eines Vermittlungsservers im Topologie-Generator in Skype for Business Server.'
ms.openlocfilehash: b74819d7e68f76392beaa89427b3cf76f24b82d9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49836915"
---
# <a name="deploy-a-mediation-server-in-topology-builder-in-skype-for-business-server"></a>Bereitstellen eines Vermittlungsservers im Topologie-Generator in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie einen Vermittlungsserver im Topologie-Generator in Skype for Business Server definieren und bereitstellen.
  
Die Enterprise-VoIP-Workload, Einwahlkonferenzen und erweiterten Enterprise-VoIP-Anwendungen (Reaktionsgruppe-Anwendung, Anwendung zum Parken von Anrufen, Anrufsteuerung und so weiter) sind in Front-End-Pools verfügbar. Die Funktionalität des Vermittlungsservers ist in den Front-End-Server integrierte. Ein separater eigenständiger Vermittlungsserver ist nicht erforderlich. 
  
Die einzige Ausnahme stellt die Konfiguration eines SIP-Trunks zum Herstellen einer Verbindung mit einem Session Border Controller (SBC) für einen Anbieter von Internettelefoniediensten dar. Um Ihre Enterprise-VoIP mit Ihrem SIP-Trunkanbieter zu verbinden, muss ein separater Vermittlungsserver bereitgestellt werden.
  
Die Verbindung zwischen Skype for Business Server (entweder einem Vermittlungsserver, der auf einem Front-End-Pool oder einem eigenständigen Vermittlungsserver verbunden ist) und einem Gateway wird als logische Zuordnung definiert, die als Trunk bezeichnet wird. In den Themen in diesem Abschnitt werden die Definition eines Trunks und die Bereitstellung eines eigenständigen Vermittlungsservers beschrieben, wenn Sie eine Verbindung mit einem SIP-Trunk herstellen.
  
## <a name="define-a-mediation-server-in-topology-builder"></a>Definieren eines Vermittlungsservers im Topologie-Generator

Sie können einem Front-End-Pool einen Vermittlungsserver als eine ausgeführte Rolle hinzufügen oder einen separaten eigenständigen Vermittlungsserverpool definieren.
  
### <a name="to-add-a-mediation-server-to-a-front-end-pool"></a>So fügen Sie einem Front-End-Pool einen Vermittlungsserver hinzu

1. Starten Sie den Topologie-Generator: Klicken Sie auf **"Start",**"Alle **Programme",** **"Skype for Business Server 2015"** und dann auf **"Skype for Business Server 2015Topology Builder".**
    
2. Erweitern Sie im Topologie-Generator in der Konsolenstruktur den Namen des Standorts, für den Sie einen Front-End-Pool definieren möchten.
    
3. Klicken Sie in der Konsolenstruktur mit der rechten Maustaste auf den Typ des front-End-Pools, den Sie verwenden möchten, und klicken Sie dann auf "Neuer **Front-End-Pool".**
    
4. Navigieren Sie durch den Assistenten **Neuen Front-End-Pool definieren**, bis Sie die Seite **Verbundene Serverrollen auswählen** erreichen.
    
5. Aktivieren **Sie in "Verbindende Serverrollen** auswählen" die Option "Vermittlungsserver **verbinden".**
    
    > [!NOTE]
    > Wenn der ausgewählte Front-End-Pooltyp die Enterprise Edition ist, wird die Vermittlungsserverkomponente auf allen Front-End-Servern dieses Front-End-Pools installiert. 
  
    > [!NOTE]
    > Der **nächste vom Vermittlungsserver** verwendete Hoppool ist der Front-End-Pool, auf dem der Vermittlungsserver ausgeführt wird.
  
    > [!NOTE]
    > Der **vom Vermittlungsserver** verwendete Edgepool ist derselbe Edgepool, der dem Front-End-Pool zugeordnet ist, in dem der Vermittlungsserver verbunden ist.
  
6. Klicken **Sie auf "Standardeinstellung",** um diesen Front-End-Pool zum Routen von Anrufen an das PSTN zu verwenden.
    
7. Klicken **Sie auf** "Fertig stellen", wenn Sie die Zuordnung eines oder von mehreren Peers zum Front-End-Pool abgeschlossen haben.
    
    > [!NOTE]
    > Bevor Sie mit dem nächsten Schritt im Bereitstellungsprozess von Enterprise-VoIP fortfahren, stellen Sie sicher, dass der Vermittlungsserverpool (d. h. der Front-End-Pool mit der Vermittlungsserverkomponente) die angegebenen FQDNs verwendet. 
  
8. Klicken Sie mit der rechten Maustaste auf den **Knoten Skype for Business Server 2015,** und klicken Sie dann auf **"Topologie veröffentlichen".**
    
### <a name="to-add-a-standalone-mediation-server"></a>So fügen Sie einen eigenständigen Vermittlungsserver hinzu

1. Starten Sie den Topologie-Generator: Klicken Sie auf **"Start",**"Alle **Programme",** **"Skype for Business Server 2015"** und dann auf **"Skype for Business Server 2015Topology Builder".**
    
2. Erweitern Sie im Topologie-Generator in der Konsolenstruktur den Namen des Standorts, für den Sie einen Vermittlungsserver definieren möchten.
    
3. Klicken Sie in der Konsolenstruktur mit der rechten Maustaste auf den Knoten "Vermittlungspools", und klicken Sie dann auf **"Vermittlungsserverpool".** 
    
4. Geben **Sie in "Neuen Vermittlungspool definieren"** den vollqualifizierten Domänennamen (FQDN) des Vermittlungsserverpools ein.
    
5. Führen Sie anschließend eine der folgenden Aktionen aus:
    
   - Wenn Sie mehrere Vermittlungsserver im Pool bereitstellen möchten, um hohe Verfügbarkeit zu bieten, wählen Sie Pool mit **mehreren Computern aus.**
    
     > [!NOTE]
     > Sie müssen [die Bereitstellung](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) bereitstellen, um Vermittlungsserverpools mit mehreren Vermittlungsservern zu unterstützen.
  
   - Wenn Sie nur einen Vermittlungsserver im Pool bereitstellen möchten, da keine hohe Verfügbarkeit erforderlich ist, wählen Sie Pool mit **einem Einzelnen Computer aus.** Überspringen Sie den folgenden Schritt.
    
6. Wenn Sie im vorherigen Schritt **Pool mit mehreren Computern** ausgewählt haben, klicken Sie in **Computer in diesem Pool definieren** auf **Computer-FQDN**, geben Sie die FQDNs der einzelnen Server innerhalb des Pools ein, und klicken Sie anschließend auf **Hinzufügen**. Wiederholen Sie diesen Schritt für alle anderen Vermittlungsserver, die Sie dem Pool hinzufügen möchten. Nachdem Sie alle Computer im Pool definiert haben, klicken Sie auf **Weiter**.
    
7. Klicken **Sie** auf der Seite "Nächsten Hop auswählen" auf "Nächster **Hoppool",** klicken Sie auf den FQDN des Front-End-Pools, der diesen Vermittlungsserverpool verwendet, und klicken Sie dann auf **"Weiter".**
    
8. Führen Sie auf der Seite **Edgeserver auswählen** einen der folgenden Schritte aus:
    
   - Wenn Sie externen Benutzern, die für Enterprise-VoIP aktiviert sind, eine Festnetzanbindung bereitstellen möchten, klicken Sie unter **"Edgepool** auswählen", der von diesem Vermittlungsserver verwendet wird, auf den FQDN des Edgeserverpools, der diesen Vermittlungsserverpool verwendet, um diesen externen Benutzern eine Festnetzanbindung zu ermöglichen, und klicken Sie dann auf **"Weiter".**
    
   - Wenn Sie nicht planen, externe Benutzer für Enterprise-VoIP zu aktivieren, oder wenn Sie benutzern keine Festnetzanbindung bereitstellen möchten, wenn sie sich außerhalb des internen Netzwerks befinden, klicken Sie auf **"Weiter".**
    
9. Klicken Sie mit der rechten Maustaste auf den **Knoten Skype for Business Server 2015,** und klicken Sie dann auf **"Topologie veröffentlichen".**
    
## <a name="define-the-mediation-server-listening-ports"></a>Definieren der Abhörports des Vermittlungsservers

Führen Sie die Schritte in diesem Thema aus, um den Topologie-Generator zu verwenden, um die Abhörports zu definieren, die ein Vermittlungsserver oder -pool eingehende Verbindungen von einem Gateway peer akzeptiert.
  
### <a name="to-modify-the-mediation-server-listening-ports"></a>So ändern Sie die Abhörports des Vermittlungsservers

1. Starten Sie den Topologie-Generator: Klicken Sie auf **"Start",**"Alle **Programme",** **"Skype for Business Server 2015"** und dann auf **"Skype for Business Server 2015Topology Builder".**
    
2. Erweitern Sie im Topologie-Generator in  der Konsolenstruktur den Knoten "Vermittlungspools", und klicken Sie mit der rechten Maustaste auf den zuvor erstellten Vermittlungsserver.
    
3. Standardmäßig sind die SIP-Abhörports auf dem Vermittlungsserver 5070 für den TLS-Datenverkehr von Skype for Business Server und 5067 für TLS-Datenverkehr von Peers (z. B. Gateways, Nebenstellenanlagen oder SBCs). Der TCP-Port ist standardmäßig deaktiviert. Wenn Sie über Gateways verfügen, die TLS nicht unterstützen, müssen Sie den TCP-Port aktivieren.
    
4. Geben Sie den gewünschten TLS- oder TCP-Abhörportbereich an, der vom Vermittlungsserver eingehende Verbindungen von PSTN-Gateways akzeptiert.
    
    > [!NOTE]
    > Wenn die Option **TCP-Port aktivieren** nicht ausgewählt wird, ist die Eingabe des TCP-Portbereichs nicht erforderlich. Diese Einstellung ist optional.
  

