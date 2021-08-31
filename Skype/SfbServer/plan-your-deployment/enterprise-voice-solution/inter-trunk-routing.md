---
title: Informationen zum Routing zwischen Trunks in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
description: Erfahren Sie, wie Skype for Business Server Enterprise-VoIP das Routing zwischen Trunks unterstützt.
ms.openlocfilehash: 5a44f9e269985312e31d827254dd7bbfae10bcfd
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "58731814"
---
# <a name="about-inter-trunk-routing-in-skype-for-business-server"></a>Informationen zum Routing zwischen Trunks in Skype for Business Server
 
Erfahren Sie, wie Skype for Business Server Enterprise-VoIP das Routing zwischen Trunks unterstützt.
  
Skype for Business Server bietet eine grundlegende Sitzungsverwaltung durch die Unterstützung des Routings zwischen Trunks. Dies ermöglicht Skype for Business Server die Bereitstellung von Anrufsteuerungsfunktionen für downstreame Telefoniesysteme. Das Routing zwischen Trunks kann eine IP-Nebenstellenanlage mit einem PSTN-Gateway (Public Switched Telephone Network, Telefonfestnetz) verbinden, sodass Anrufe von einem Nebenstellenanlagetelefon an das Festnetz und eingehende PSTN-Anrufe an ein Nebenstellentelefon weitergeleitet werden können. Auf ähnliche Weise können Skype for Business Server zwei oder mehr IP-Nebenstellenanlagen miteinander verbinden, sodass Anrufe zwischen Nebenstellenanlagen aus den verschiedenen IP-Nebenstellenanlagen getätigt und empfangen werden können. 
  
In der folgenden Abbildung wird veranschaulicht, Skype for Business Server die Verbindungskonnektivität zwischen einem PSTN-Gateway und einer IP-Nebenstellenanlage ermöglicht.
  
![Lync Server verbindet PSTN-Gateway/IP-NEBENSTELLENANLAGE-Diagramm.](../../media/inter_trunk01.jpg)
  
In der nächsten Abbildung wird veranschaulicht, Skype for Business Server zwei IP-Nebenstellenanlagen verbunden werden.
  
![Lync Server- Verbindungsdiagramm für IP-PAX-Systeme.](../../media/inter_trunk02.jpg)
  

