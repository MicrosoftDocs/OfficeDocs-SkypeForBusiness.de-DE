---
title: Zwischen trunk-Routing in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Skype for Business Server bietet grundlegende Sitzungsverwaltung durch die Unterstützung von intertrunk-Routing. '
ms.openlocfilehash: 2c5438f78da78870a5dae8c697d4d30d19a316ce
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274968"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a>Zwischen trunk-Routing in Skype for Business Server

Skype for Business Server bietet grundlegende Sitzungsverwaltung durch die Unterstützung von intertrunk-Routing. Diese Funktion ermöglicht Skype for Business Server die Bereitstellung von Funktionen zur Anrufsteuerung für Downstream-Telefoniesysteme. Durch das Routing zwischen Trunks kann eine IP-Nebenstellenanlage mit einem PSTN-Gateway (Public Switched Telephone Network, Festnetz) verbunden werden, sodass Anrufe von einem Nebenstellentelefon an das Festnetz und eingehende Festnetzanrufe an ein Nebenstellentelefon weitergeleitet werden können. Ebenso kann Skype for Business Server zwei oder mehr IP-PBX-Systeme verbinden, damit Anrufe zwischen PBX-Telefonen von den verschiedenen IP-PBX-Systemen getätigt und empfangen werden können. 


Die folgende Abbildung zeigt die Verbindung zwischen einem PSTN-Gateway und einer IP-Telefonanlage mit Skype for Business Server.

![Interkonnektivität zwischen einem PSTN-Gateway und einer IP-Telefonanlage](../../media/pstn-gateway-ip-pbx.jpg)

Die nächste Abbildung zeigt den Skype for Business-Server, der zwei IP-PBX-Systeme verbindet.

![Skype for Business-Server, der zwei IP-PGX-Systeme verbindet](../../media/two-ip-pbx-systems.jpg)

