---
title: Routing zwischen Trunks in Skype for Business Server
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
ms.openlocfilehash: 2c2d2dfd1062414de0d11b9e77d7f9f1993a77a14266a8d121b43bfbc12335da
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54351495"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a>Routing zwischen Trunks in Skype for Business Server

Skype for Business Server bietet eine grundlegende Sitzungsverwaltung durch die Unterstützung des Routings zwischen Trunks. Diese Funktion ermöglicht Skype for Business Server die Bereitstellung von Anrufsteuerungsfunktionen für downstreame Telefoniesysteme. Das Routing zwischen Trunks kann eine IP-Nebenstellenanlage mit einem PSTN-Gateway (Public Switched Telephone Network, Telefonfestnetz) verbinden, sodass Anrufe von einem Nebenstellenanlagetelefon an das Festnetz und eingehende PSTN-Anrufe an ein Nebenstellentelefon weitergeleitet werden können. Auf ähnliche Weise können Skype for Business Server zwei oder mehr IP-Nebenstellenanlagen miteinander verbinden, sodass Anrufe zwischen Nebenstellenanlagentelefonen aus den verschiedenen IP-Nebenstellenanlagen getätigt und empfangen werden können. 


In der folgenden Abbildung wird Skype for Business Server die Verbindungskonnektivität zwischen einem PSTN-Gateway und einer IP-Nebenstellenanlage veranschaulicht.

![Verbindungskonnektivität zwischen einem PSTN-Gateway und einer IP-Nebenstellenanlage](../../media/pstn-gateway-ip-pbx.jpg)

Die nächste Abbildung zeigt Skype for Business Server Verbinden von zwei IP-Nebenstellenanlagen.

![Skype for Business Server verbinden zwei IP-PGX-Systeme](../../media/two-ip-pbx-systems.jpg)

