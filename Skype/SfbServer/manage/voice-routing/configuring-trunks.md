---
title: Konfigurieren von Trunks in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Im Rahmen Enterprise-VoIP Bereitstellung können Sie einen Trunk zwischen einem Vermittlungsserver und einem oder mehreren Peers konfigurieren, um PSTN-Verbindungen (Public Switched Telephone Network) für Enterprise-VoIP Clients und Geräte in Ihrer Organisation bereitzustellen.
ms.openlocfilehash: 318b049c8ebaaa1a2df445bf1158184e3b150a84
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60838517"
---
# <a name="configuring-trunks-in-skype-for-business-server"></a>Konfigurieren von Trunks in Skype for Business Server

Im Rahmen Enterprise-VoIP Bereitstellung können Sie einen Trunk zwischen einem Vermittlungsserver und einem oder mehreren der folgenden Peers konfigurieren, um PSTN-Verbindungen (Public Switched Telephone Network) für Enterprise-VoIP Clients und Geräte in Ihrer Organisation bereitzustellen:

- SIP-Trunkverbindung mit einem Anbieter von Internettelefoniediensten
- PSTN-Gateway
- Nebenstellenanlage (Private Branch Exchange, PBX)

Ausführliche Informationen finden Sie unter [Plan for PSTN connectivity in Skype for Business Server.](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md)

> [!IMPORTANT]
> Bevor Sie mit der Trunkkonfiguration beginnen, überprüfen Sie, ob die Topologie erstellt und der Vermittlungsserver und der Peer konfiguriert und einander zugeordnet wurden. Ausführliche Informationen finden Sie unter [Definieren eines Gateways im Topologie-Generator in Skype for Business Server.](../../deploy/deploy-enterprise-voice/define-a-gateway.md)

> [!NOTE]
> Als Teil der Trunkkonfiguration können Sie die Skype for Business Server Medienumgehungsfunktion aktivieren, mit der Medien den Vermittlungsserver umgehen können. Trunks können mit oder ohne Medienumgehung konfiguriert werden, die Aktivierung dieser Funktion wird jedoch dringend empfohlen. Ausführliche Informationen finden Sie unter [Plan for media bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).
