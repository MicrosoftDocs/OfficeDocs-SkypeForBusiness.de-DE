---
title: 'Skype for Business Server: Routing zwischen Trunks'
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 'Skype for Business Server bietet eine grundlegende Sitzungsverwaltung durch die Unterstützung des Routings zwischen Trunks. '
ms.openlocfilehash: ea21bf8e3697dc4b06b562f709d88903666cf3c5
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60774745"
---
# <a name="skype-for-business-server-inter-trunk-routing"></a>Skype for Business Server: Routing zwischen Trunks

Skype for Business Server bietet eine grundlegende Sitzungsverwaltung durch die Unterstützung des Routings zwischen Trunks. Diese Funktion ermöglicht Skype for Business Server die Bereitstellung von Anrufsteuerungsfunktionen für downstreame Telefoniesysteme. Das Routing zwischen Trunks kann eine IP-Nebenstellenanlage mit einem PSTN-Gateway (Public Switched Telephone Network, Telefonfestnetz) verbinden, sodass Anrufe von einem Nebenstellenanlagetelefon an das Festnetz und eingehende PSTN-Anrufe an ein Nebenstellentelefon weitergeleitet werden können. Auf ähnliche Weise können Skype for Business Server zwei oder mehr IP-Nebenstellenanlagen miteinander verbinden, sodass Anrufe zwischen Nebenstellenanlagen aus den verschiedenen IP-Nebenstellenanlagen getätigt und empfangen werden können. 


Die folgende Abbildung veranschaulicht Skype for Business Server die Verbindungskonnektivität zwischen einem PSTN-Gateway und einer IP-Nebenstellenanlage bereitstellen.

![Verbindungskonnektivität zwischen einem PSTN-Gateway und einer IP-Nebenstellenanlage.](../../media/pstn-gateway-ip-pbx.jpg)

In der nächsten Abbildung wird veranschaulicht, Skype for Business Server zwei IP-Nebenstellenanlagen verbunden werden.

![Skype for Business Server verbinden zwei IP-PGX-Systeme.](../../media/two-ip-pbx-systems.jpg)

