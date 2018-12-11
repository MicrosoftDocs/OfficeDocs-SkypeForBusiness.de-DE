---
title: Routing zwischen Trunks in Skype für Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Skype für Business Server bietet grundlegende sitzungsverwaltung über die Unterstützung von intertrunk-routing. '
ms.openlocfilehash: 66ee1f0cb9e37587d3c581b895528e27e7fad6c0
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222814"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a>Routing zwischen Trunks in Skype für Business Server

Skype für Business Server bietet grundlegende sitzungsverwaltung über die Unterstützung von intertrunk-routing. Diese Funktion ermöglicht Skype für Business Server downstream Telefoniesystemen Anruf Steuerelement Funktionen zur Verfügung. Durch das Routing zwischen Trunks kann eine IP-Nebenstellenanlage mit einem PSTN-Gateway (Public Switched Telephone Network, Festnetz) verbunden werden, sodass Anrufe von einem Nebenstellentelefon an das Festnetz und eingehende Festnetzanrufe an ein Nebenstellentelefon weitergeleitet werden können. In ähnlicher Weise kann Skype für Business Server mindestens zwei IP-PBX-Systemen interconnect, damit Anrufe aus den unterschiedlichen IP-PBX-Systemen PBX-Telefone zwischen und platziert werden können. 


Die folgende Abbildung zeigt Skype für Business Server zunehmende Verbindung untereinander zwischen einem PSTN-Gateway und IP-Nebenstellenanlage bereitstellen.

![Zunehmende Verbindung untereinander zwischen einem PSTN-Gateway und IP-Nebenstellenanlage](../../media/pstn-gateway-ip-pbx.jpg)

Die folgende Abbildung veranschaulicht Skype für Business Server zwei IP-PBX-Systeme anschließen.

![Skype für Business Server zwei IP-PGX Systeme](../../media/two-ip-pbx-systems.jpg)

