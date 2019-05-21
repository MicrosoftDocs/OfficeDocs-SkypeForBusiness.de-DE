---
title: Zwischen trunk-Routing in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
description: Erfahren Sie, wie Skype for Business Server Enterprise-VoIP das Routing zwischen Trunks unterstützt.
ms.openlocfilehash: f590463eced61cf2e8b19a27f7cfc2dd648c63c1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276831"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a>Zwischen trunk-Routing in Skype for Business Server
 
Erfahren Sie, wie Skype for Business Server Enterprise-VoIP das Routing zwischen Trunks unterstützt.
  
Skype for Business Server bietet grundlegende Sitzungsverwaltung durch die Unterstützung von intertrunk-Routing. Auf diese Weise kann Skype for Business Server Funktionen zur Anrufsteuerung für Downstream-Telefoniesysteme bereitstellen. Durch das Routing zwischen Trunks kann eine IP-Nebenstellenanlage mit einem PSTN-Gateway (Public Switched Telephone Network, Festnetz) verbunden werden, sodass Anrufe von einem Nebenstellentelefon an das Festnetz und eingehende Festnetzanrufe an ein Nebenstellentelefon weitergeleitet werden können. Ebenso kann Skype for Business Server zwei oder mehr IP-PBX-Systeme verbinden, damit Anrufe zwischen PBX-Telefonen von den verschiedenen IP-PBX-Systemen getätigt und empfangen werden können. 
  
Die folgende Abbildung zeigt die Verbindung zwischen einem PSTN-Gateway und einer IP-Telefonanlage mit Skype for Business Server.
  
![Lync Server: Verbinden von PSTN-Gateway/IP-PBX (Diagramm)](../../media/inter_trunk01.jpg)
  
Die nächste Abbildung zeigt den Skype for Business-Server, der zwei IP-PBX-Systeme verbindet.
  
![Lync Server: Verbinden von IP-PAX-Systemen (Diagramm)](../../media/inter_trunk02.jpg)
  

