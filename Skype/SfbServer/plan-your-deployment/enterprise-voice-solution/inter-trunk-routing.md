---
title: Routing zwischen Trunks in Skype für Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
description: Hier erfahren Sie, wie routing zwischen Trunks Skype für Business Server Enterprise-VoIP unterstützt.
ms.openlocfilehash: 281e722898655e463c3db281014421ae224c2cec
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32207300"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a>Routing zwischen Trunks in Skype für Business Server
 
Hier erfahren Sie, wie routing zwischen Trunks Skype für Business Server Enterprise-VoIP unterstützt.
  
Skype für Business Server bietet grundlegende sitzungsverwaltung über die Unterstützung von intertrunk-routing. Auf diese Weise können Skype für Business Server downstream Telefoniesystemen Anruf Steuerelement Funktionen zur Verfügung. Durch das Routing zwischen Trunks kann eine IP-Nebenstellenanlage mit einem PSTN-Gateway (Public Switched Telephone Network, Festnetz) verbunden werden, sodass Anrufe von einem Nebenstellentelefon an das Festnetz und eingehende Festnetzanrufe an ein Nebenstellentelefon weitergeleitet werden können. In ähnlicher Weise kann Skype für Business Server mindestens zwei IP-PBX-Systemen interconnect, damit Anrufe aus den unterschiedlichen IP-PBX-Systemen PBX-Telefone zwischen und platziert werden können. 
  
Die folgende Abbildung zeigt Skype für Business Server zunehmende Verbindung untereinander zwischen einem PSTN-Gateway und IP-Nebenstellenanlage bereitstellen.
  
![Lync Server: Verbinden von PSTN-Gateway/IP-PBX (Diagramm)](../../media/inter_trunk01.jpg)
  
Die folgende Abbildung veranschaulicht Skype für Business Server zwei IP-PBX-Systeme anschließen.
  
![Lync Server: Verbinden von IP-PAX-Systemen (Diagramm)](../../media/inter_trunk02.jpg)
  

