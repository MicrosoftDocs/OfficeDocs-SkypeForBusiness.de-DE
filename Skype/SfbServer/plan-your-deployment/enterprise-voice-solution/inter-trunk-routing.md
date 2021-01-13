---
title: Routing zwischen Trunks in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
description: Erfahren Sie, wie Skype for Business Server Enterprise-VoIP Routing zwischen Trunks unterstützt.
ms.openlocfilehash: fc03f0df530be12ad1d08148850c11d8f92a2791
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825596"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a>Routing zwischen Trunks in Skype for Business Server
 
Erfahren Sie, wie Skype for Business Server Enterprise-VoIP Routing zwischen Trunks unterstützt.
  
Skype for Business Server bietet eine grundlegende Sitzungsverwaltung durch die Unterstützung des Routings zwischenTrunks. Auf diese Weise kann Skype for Business Server Funktionen für die Anrufsteuerung für nachgelagerte Telefoniesysteme bereitstellen. Das routingübergreifende Routing kann eine IP-PBX-Anlage mit einem Gateway im öffentlichen Telefonnetz (Public Switched Telephone Network, PSTN) verbinden, sodass Anrufe von einem Nebenstellentelefon (Private Branch Exchange, PBX) an das Festnetz und eingehende Festnetzanrufe an ein Nebenstellentelefon geroutet werden können. Auf ähnliche Weise kann Skype for Business Server zwei oder mehr IP-PBX-Systeme miteinander verbinden, sodass Anrufe zwischen Nebenstellentelefonen von den verschiedenen IP-PBX-Systemen an- und empfangen werden können. 
  
Die folgende Abbildung zeigt, wie Skype for Business Server die Verbindung zwischen einem PSTN-Gateway und einer IP-PBX-Anlage ermöglicht.
  
![Lync Server: Verbinden des PSTN-Gateways/IP-PBX-Diagramms](../../media/inter_trunk01.jpg)
  
Die folgende Abbildung zeigt, wie Skype for Business Server zwei IP-PBX-Systeme verbindet.
  
![Diagramm für Lync Server, das IP-DESSRG-Systeme miteinander verbindet](../../media/inter_trunk02.jpg)
  

