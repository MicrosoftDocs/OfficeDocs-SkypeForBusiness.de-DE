---
title: Konfigurieren von Trunks in Skype für Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Im Rahmen der Bereitstellung von Enterprise-VoIP können Sie einen Trunk zwischen einem Vermittlungsserver und eines oder mehrerer Peers zum öffentlichen Telefonnetz (PSTN) Netzwerkkonnektivität für Enterprise-VoIP-Clients und Geräte in Ihrer Organisation bereitstellen konfigurieren.
ms.openlocfilehash: 34391e09bb87144252634b572bf0eac6a10fe1d9
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222863"
---
# <a name="configuring-trunks-in-skype-for-business-server"></a>Konfigurieren von Trunks in Skype für Business Server

Im Rahmen der Bereitstellung von Enterprise-VoIP können Sie einen Trunk zwischen einem Vermittlungsserver und mindestens eine der folgenden Peers zum öffentlichen Telefonnetz (PSTN) Netzwerkkonnektivität für Enterprise-VoIP-Clients und Geräte in Ihrer Organisation bereitstellen konfigurieren:

- SIP-Trunkverbindung mit einem Anbieter von Internettelefoniediensten
- PSTN-Gateway
- Nebenstellenanlage (Private Branch Exchange, PBX)

Weitere Informationen hierzu finden Sie unter [Planen der PSTN-Konnektivität in Skype für Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).

> [!IMPORTANT]
> Vor Beginn des trunkkonfiguration stellen Sie sicher, dass die Topologie erstellt wurde und dem Vermittlungsserver und seinen Peer konfiguriert und miteinander verknüpft wurden. Weitere Informationen hierzu finden Sie unter [Definieren eines Gateways im Topologie-Generator in Skype für Business Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).

> [!NOTE]
> Als Bestandteil der trunkkonfiguration können Sie die Skype für Business Server Media Bypass-Feature ermöglicht Medien, für die Umgehung des Vermittlungsservers. Trunks mit oder ohne medienumgehung konfiguriert werden können, aber es wird dringend empfohlen, dass Sie ihn aktivieren. Weitere Informationen hierzu finden Sie unter [Plan für Medien in Skype für Unternehmen zu umgehen](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).