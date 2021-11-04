---
title: Hinzufügen eines Survivable Branch Appliance-PSTN
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddBranchOfficeAppliancePstnPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 7c55a43d-2589-48f9-972b-1e48a3dca52a
ROBOTS: NOINDEX, NOFOLLOW
description: 'Zum Definieren des PSTN-Gateways (Public Switched Telephone Network) für eine Survivable Branch Appliance am Zweigstellenstandort muss Folgendes angegeben werden:'
ms.openlocfilehash: 1b8470f88217a5ded93094bc83cc0f31c8c916ca
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60745091"
---
# <a name="add-survivable-branch-appliance-pstn"></a>Hinzufügen eines Survivable Branch Appliance-PSTN
 
Zum Definieren des PSTN-Gateways (Public Switched Telephone Network) für eine Survivable Branch Appliance am Zweigstellenstandort muss Folgendes angegeben werden: 
  
- Ein vollqualifizierter Domänenname (FQDN) oder eine IP-Adresse des Gatewaypeers, dem die Survivable Branch Appliance oder der Survivable Branch Server für das Routing ein- und ausgehender PSTN-Anrufe zugeordnet ist.
    
    > [!IMPORTANT]
    > Beim Definieren einer Survivable Branch Appliance ist dies das Gateway, mit dem sich der Vermittlungsserver in der Survivable Branch Appliance für PSTN-Verbindungen verbindet. 
  
- Der Überwachungsport für SIP-Nachrichten (Session Initiation Protocol). Die Standardports für ein Gateway, eine Nebenstellenanlage oder einen SBC (Session Border Controller) lauten 5066 für Transmission Control Protocol (TCP) und 5067 für TLS (Transport Layer Security). Bei einer Survivable Branch Appliance an einem Zweigstellenstandort lauten die Standardports 5081 für TCP und 5082 für TLS.
    
- Aus Sicherheitsgründen wird der Einsatz von TLS ausdrücklich empfohlen. Konsultieren Sie beim Definieren einer Survivable Branch Appliance die Dokumentation des Herstellers, um sicherzustellen, dass die Survivable Branch Appliance das TLS-Protokoll unterstützt.
    
    > [!IMPORTANT]
    > Aus Sicherheitsgründen wird dringend empfohlen, ein Gateway mit Unterstützung für TLS bereitzustellen. 
  
> [!NOTE]
> Wenn Sie ein PSTN-Gateway hinzufügen möchten, können Sie dieses zu einem späteren Zeitpunkt einrichten. Die Funktionalität ist jedoch eingeschränkt, bis das PSTN-Gateway definiert und konfiguriert ist. 
  

