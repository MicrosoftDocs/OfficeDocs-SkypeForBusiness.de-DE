---
title: Routing zwischen Trunks in Skype für Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Skype für Business Server bietet grundlegende sitzungsverwaltung über die Unterstützung von intertrunk-routing. '
ms.openlocfilehash: a1486d24c0681df44085db754fda380d653c636b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920513"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a>Routing zwischen Trunks in Skype für Business Server

Skype für Business Server bietet grundlegende sitzungsverwaltung über die Unterstützung von intertrunk-routing. Diese Funktion ermöglicht Skype für Business Server downstream Telefoniesystemen Anruf Steuerelement Funktionen zur Verfügung. Durch das Routing zwischen Trunks kann eine IP-Nebenstellenanlage mit einem PSTN-Gateway (Public Switched Telephone Network, Festnetz) verbunden werden, sodass Anrufe von einem Nebenstellentelefon an das Festnetz und eingehende Festnetzanrufe an ein Nebenstellentelefon weitergeleitet werden können. In ähnlicher Weise kann Skype für Business Server mindestens zwei IP-PBX-Systemen interconnect, damit Anrufe aus den unterschiedlichen IP-PBX-Systemen PBX-Telefone zwischen und platziert werden können. 


Die folgende Abbildung zeigt Skype für Business Server zunehmende Verbindung untereinander zwischen einem PSTN-Gateway und IP-Nebenstellenanlage bereitstellen.

![Zunehmende Verbindung untereinander zwischen einem PSTN-Gateway und IP-Nebenstellenanlage](../../media/pstn-gateway-ip-pbx.jpg)

Die folgende Abbildung veranschaulicht Skype für Business Server zwei IP-PBX-Systeme anschließen.

![Skype für Business Server zwei IP-PGX Systeme](../../media/two-ip-pbx-systems.jpg)

