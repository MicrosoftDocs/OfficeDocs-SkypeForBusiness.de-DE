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
description: 'Skype for Business Server bietet eine grundlegende Sitzungsverwaltung durch die Unterstützung des Routings zwischenTrunks. '
ms.openlocfilehash: d509b4f9de489e65ed8443fd1aad92e24363fb55
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814125"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a>Routing zwischen Trunks in Skype for Business Server

Skype for Business Server bietet eine grundlegende Sitzungsverwaltung durch die Unterstützung des Routings zwischenTrunks. Diese Funktion ermöglicht Skype for Business Server die Bereitstellung von Anrufsteuerungsfunktionen für nachgelagerte Telefoniesysteme. Das routingübergreifende Routing kann eine IP-PBX-Anlage mit einem Gateway im öffentlichen Telefonnetz (Public Switched Telephone Network, PSTN) verbinden, sodass Anrufe von einem Nebenstellentelefon (Private Branch Exchange, PBX) an das Festnetz und eingehende Festnetzanrufe an ein Nebenstellentelefon geroutet werden können. Auf ähnliche Weise kann Skype for Business Server zwei oder mehr IP-PBX-Systeme miteinander verbinden, sodass Anrufe zwischen Nebenstellentelefonen von den verschiedenen IP-PBX-Systemen an- und empfangen werden können. 


Die folgende Abbildung zeigt, wie Skype for Business Server die Verbindung zwischen einem PSTN-Gateway und einer IP-PBX-Anlage ermöglicht.

![Verbindung zwischen einem PSTN-Gateway und einer IP-PBX-Anlage](../../media/pstn-gateway-ip-pbx.jpg)

Die folgende Abbildung zeigt, wie Skype for Business Server zwei IP-PBX-Systeme verbindet.

![Skype for Business Server verbindet zwei IP-PGX-Systeme](../../media/two-ip-pbx-systems.jpg)

