---
title: Konfigurieren von Trunks in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Im Rahmen der Bereitstellung von Enterprise-VoIP können Sie einen trunk zwischen einem Vermittlungs Server und einem oder mehreren Peers konfigurieren, um die PSTN-Konnektivität (Public Switched Telephone Network) für Enterprise-VoIP-Clients und-Geräte in Ihrer Organisation bereitzustellen.
ms.openlocfilehash: c350723720dccee069a28a4d9aa2c40517f6d1bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275003"
---
# <a name="configuring-trunks-in-skype-for-business-server"></a>Konfigurieren von Trunks in Skype for Business Server

Im Rahmen der Enterprise-VoIP-Bereitstellung können Sie einen trunk zwischen einem Vermittlungs Server und einem oder mehreren der folgenden Peers konfigurieren, um die PSTN-Konnektivität (Public Switched Telephone Network) für Enterprise-VoIP-Clients und-Geräte in Ihrer Organisation bereitzustellen:

- SIP-Trunkverbindung mit einem Anbieter von Internettelefoniediensten
- PSTN-Gateway
- Nebenstellenanlage (Private Branch Exchange, PBX)

Ausführliche Informationen finden Sie unter [Planen der PSTN-Konnektivität in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).

> [!IMPORTANT]
> Bevor Sie die trunk-Konfiguration beginnen, stellen Sie sicher, dass die Topologie erstellt wurde und dass der Vermittlungs Server und sein Peer konfiguriert und miteinander verknüpft wurden. Ausführliche Informationen finden Sie unter [Definieren eines Gateways im Topologie-Generator in Skype for Business Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).

> [!NOTE]
> Als Teil der trunk-Konfiguration können Sie die Medien Umgehungsfunktion von Skype for Business Server aktivieren, mit der Medien den Vermittlungsserver umgehen können. Trunks kann entweder mit oder ohne aktivierte medienumgehung konfiguriert werden, wir empfehlen jedoch dringend, diese zu aktivieren. Ausführliche Informationen finden Sie unter [Planen der medienumgehung in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).
