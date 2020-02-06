---
title: Zwischen trunk-Routing in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Skype for Business Server bietet grundlegende Sitzungsverwaltung durch die Unterstützung von intertrunk-Routing. '
ms.openlocfilehash: c3381c6ae6bd86c416e6bd3349cf54d6fb530a08
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816965"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a>Zwischen trunk-Routing in Skype for Business Server

Skype for Business Server bietet grundlegende Sitzungsverwaltung durch die Unterstützung von intertrunk-Routing. Diese Funktion ermöglicht Skype for Business Server die Bereitstellung von Funktionen zur Anrufsteuerung für Downstream-Telefoniesysteme. Durch das Routing zwischen Trunks kann eine IP-Nebenstellenanlage mit einem PSTN-Gateway (Public Switched Telephone Network, Festnetz) verbunden werden, sodass Anrufe von einem Nebenstellentelefon an das Festnetz und eingehende Festnetzanrufe an ein Nebenstellentelefon weitergeleitet werden können. Ebenso kann Skype for Business Server zwei oder mehr IP-PBX-Systeme verbinden, damit Anrufe zwischen PBX-Telefonen von den verschiedenen IP-PBX-Systemen getätigt und empfangen werden können. 


Die folgende Abbildung zeigt die Verbindung zwischen einem PSTN-Gateway und einer IP-Telefonanlage mit Skype for Business Server.

![Interkonnektivität zwischen einem PSTN-Gateway und einer IP-Telefonanlage](../../media/pstn-gateway-ip-pbx.jpg)

Die nächste Abbildung zeigt den Skype for Business-Server, der zwei IP-PBX-Systeme verbindet.

![Skype for Business-Server, der zwei IP-PGX-Systeme verbindet](../../media/two-ip-pbx-systems.jpg)

