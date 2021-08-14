---
title: 'Skype for Business Server: Routing zwischen Trunks'
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Skype for Business Server bietet eine grundlegende Sitzungsverwaltung durch die Unterstützung des Routings zwischen Trunks. '
ms.openlocfilehash: 694fc707711ae804bade0935e0fb9f34e89dbb93
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2021
ms.locfileid: "58234370"
---
# <a name="skype-for-business-server-inter-trunk-routing"></a>Skype for Business Server: Routing zwischen Trunks

Skype for Business Server bietet eine grundlegende Sitzungsverwaltung durch die Unterstützung des Routings zwischen Trunks. Diese Funktion ermöglicht Skype for Business Server die Bereitstellung von Anrufsteuerungsfunktionen für downstreame Telefoniesysteme. Das Routing zwischen Trunks kann eine IP-Nebenstellenanlage mit einem PSTN-Gateway (Public Switched Telephone Network, Telefonfestnetz) verbinden, sodass Anrufe von einem Nebenstellenanlagetelefon an das Festnetz und eingehende PSTN-Anrufe an ein Nebenstellentelefon weitergeleitet werden können. Auf ähnliche Weise können Skype for Business Server zwei oder mehr IP-Nebenstellenanlagen miteinander verbinden, sodass Anrufe zwischen Nebenstellenanlagen aus den verschiedenen IP-Nebenstellenanlagen getätigt und empfangen werden können. 


In der folgenden Abbildung wird veranschaulicht, Skype for Business Server die Verbindungskonnektivität zwischen einem PSTN-Gateway und einer IP-Nebenstellenanlage ermöglicht.

![Verbindungskonnektivität zwischen einem PSTN-Gateway und einer IP-Nebenstellenanlage](../../media/pstn-gateway-ip-pbx.jpg)

Die nächste Abbildung zeigt Skype for Business Server Verbinden von zwei IP-Nebenstellenanlagen.

![Skype for Business Server verbinden zwei IP-PGX-Systeme](../../media/two-ip-pbx-systems.jpg)

