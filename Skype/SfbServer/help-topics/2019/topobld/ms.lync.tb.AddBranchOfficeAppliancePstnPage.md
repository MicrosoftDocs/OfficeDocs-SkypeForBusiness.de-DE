---
title: Hinzufügen eines Survivable Branch-Anwendungs-PSTN
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddBranchOfficeAppliancePstnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7c55a43d-2589-48f9-972b-1e48a3dca52a
description: 'Um das Gateway public switched Telephone Network, (PSTN) für eine Survivable Branch Appliance am Zweigstellenstandort definieren, geben Sie Folgendes ein:'
ms.openlocfilehash: 7357beacc93e9fbfede068802c5e849416096a0e
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/21/2018
ms.locfileid: "19996884"
---
# <a name="add-survivable-branch-appliance-pstn"></a>Hinzufügen eines Survivable Branch-Anwendungs-PSTN
 
Um das Gateway public switched Telephone Network, (PSTN) für eine Survivable Branch Appliance am Zweigstellenstandort definieren, geben Sie Folgendes ein: 
  
- PSTN-Anrufe einen vollqualifizierten Domänennamen (FQDN) oder die IP-Adresse für den gatewaypeer, dass die Survivable Branch Appliance oder einen Survivable Branch Server für das routing von eingehenden und ausgehenden zugeordnet ist.
    
    > [!IMPORTANT]
    > Wenn Sie eine Survivable Branch Appliance definieren, ist dies das Gateway, mit dem der Vermittlungsserver in der Survivable Branch Appliance für PSTN-Anbindung verbinden möchten. 
  
- Der Überwachungsport für SIP-Nachrichten (Session Initiation Protocol). Die Standardports für ein Gateway, eine Nebenstellenanlage oder einen SBC (Session Border Controller) lauten 5066 für Transmission Control Protocol (TCP) und 5067 für TLS (Transport Layer Security). Bei einer Survivable Branch-Anwendung an einer Zweigstelle lauten die Standardports 5081 für TCP und 5082 für TLS.
    
- Aus Sicherheitsgründen wird der Einsatz von TLS (Transport Layer Security) ausdrücklich empfohlen. Wenn Sie eine Survivable Branch Appliance definieren, finden Sie in der Herstellerdokumentation Survivable Branch Appliance, um sicherzustellen, dass Ihre Survivable Branch Appliance das TLS-Protokoll unterstützt.
    
    > [!IMPORTANT]
    > Aus Sicherheitsgründen wird dringend empfohlen, ein Gateway mit Unterstützung für TLS bereitzustellen. 
  
> [!NOTE]
> Wenn Sie ein PSTN-Gateway hinzufügen möchten, können Sie dieses zu einem späteren Zeitpunkt einrichten. Die Funktionalität ist jedoch eingeschränkt, bis das PSTN-Gateway definiert und konfiguriert ist. 
  

