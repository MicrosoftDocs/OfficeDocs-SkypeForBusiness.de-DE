---
title: Routing zwischen Trunks in Skype für Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 60e91003e9b1b70393f99ef2ce6d8021fa2e5010
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924220"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a>Routing zwischen Trunks in Skype für Business Server
 
Hier erfahren Sie, wie routing zwischen Trunks Skype für Business Server Enterprise-VoIP unterstützt.
  
Skype für Business Server bietet grundlegende sitzungsverwaltung über die Unterstützung von intertrunk-routing. Auf diese Weise können Skype für Business Server downstream Telefoniesystemen Anruf Steuerelement Funktionen zur Verfügung. Durch das Routing zwischen Trunks kann eine IP-Nebenstellenanlage mit einem PSTN-Gateway (Public Switched Telephone Network, Festnetz) verbunden werden, sodass Anrufe von einem Nebenstellentelefon an das Festnetz und eingehende Festnetzanrufe an ein Nebenstellentelefon weitergeleitet werden können. In ähnlicher Weise kann Skype für Business Server mindestens zwei IP-PBX-Systemen interconnect, damit Anrufe aus den unterschiedlichen IP-PBX-Systemen PBX-Telefone zwischen und platziert werden können. 
  
Die folgende Abbildung zeigt Skype für Business Server zunehmende Verbindung untereinander zwischen einem PSTN-Gateway und IP-Nebenstellenanlage bereitstellen.
  
![Lync Server: Verbinden von PSTN-Gateway/IP-PBX (Diagramm)](../../media/inter_trunk01.jpg)
  
Die folgende Abbildung veranschaulicht Skype für Business Server zwei IP-PBX-Systeme anschließen.
  
![Lync Server: Verbinden von IP-PAX-Systemen (Diagramm)](../../media/inter_trunk02.jpg)
  

