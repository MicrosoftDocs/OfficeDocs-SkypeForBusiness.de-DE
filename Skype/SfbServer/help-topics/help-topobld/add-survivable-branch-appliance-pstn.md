---
title: Hinzufügen eines Survivable Branch-Anwendungs-PSTN
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddBranchOfficeAppliancePstnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7c55a43d-2589-48f9-972b-1e48a3dca52a
description: 'Wenn Sie das PSTN-Gateway (Public Switched Telephone Network) für eine Survivable Branch-Appliance an einer Zweigstelle definieren möchten, geben Sie Folgendes an:'
ms.openlocfilehash: d5ba39a79f7810a64776efcd7b7c47488fe93d2b
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41697950"
---
# <a name="add-survivable-branch-appliance-pstn"></a>Hinzufügen eines Survivable Branch-Anwendungs-PSTN
 
Wenn Sie das PSTN-Gateway (Public Switched Telephone Network) für eine Survivable Branch-Appliance an einer Zweigstelle definieren möchten, geben Sie Folgendes an: 
  
- Einen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) oder eine IP-Adresse für den Gateway-Peer, dem die überlebensfähige Verzweigungs-oder Survivable Branch-Server für das Routing von eingehenden und ausgehenden PSTN-anrufen zugeordnet ist
    
    > [!IMPORTANT]
    > Wenn Sie eine Survivable Branch-Appliance definieren, ist dies das Gateway, auf das der Vermittlungs Server innerhalb der Survivable Branch-Appliance für PSTN-Konnektivität zugreifen kann. 
  
- Der Überwachungsport für SIP-Nachrichten (Session Initiation Protocol). Die Standardports für ein Gateway, eine Nebenstellenanlage oder einen SBC (Session Border Controller) lauten 5066 für Transmission Control Protocol (TCP) und 5067 für TLS (Transport Layer Security). Bei einer Survivable Branch-Anwendung an einer Zweigstelle lauten die Standardports 5081 für TCP und 5082 für TLS.
    
- Aus Sicherheitsgründen wird der Einsatz von TLS (Transport Layer Security) ausdrücklich empfohlen. Wenn Sie eine Survivable Branch-Appliance definieren, lesen Sie in der Dokumentation Ihres Survivable Branch Appliance-Herstellers nach, ob Ihre Survivable Branch-Appliance das TLS-Protokoll unterstützt.
    
    > [!IMPORTANT]
    > Aus Sicherheitsgründen wird dringend empfohlen, ein Gateway mit Unterstützung für TLS bereitzustellen. 
  
> [!NOTE]
> Wenn Sie ein PSTN-Gateway hinzufügen möchten, können Sie dieses zu einem späteren Zeitpunkt einrichten. Die Funktionalität ist jedoch eingeschränkt, bis das PSTN-Gateway definiert und konfiguriert ist. 
  

