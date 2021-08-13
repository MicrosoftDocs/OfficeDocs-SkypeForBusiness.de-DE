---
title: Konfigurieren von Trunks in Skype for Business Server
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
description: Im Rahmen Enterprise-VoIP Bereitstellung können Sie einen Trunk zwischen einem Vermittlungsserver und einem oder mehreren Peers konfigurieren, um PSTN-Verbindungen (Public Switched Telephone Network) für Enterprise-VoIP Clients und Geräte in Ihrer Organisation bereitzustellen.
ms.openlocfilehash: 82491d566e36ce819456c3d2a8983f97dd6c4f17d4d7cece71a066342d48efea
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54333457"
---
# <a name="configuring-trunks-in-skype-for-business-server"></a>Konfigurieren von Trunks in Skype for Business Server

Im Rahmen Enterprise-VoIP Bereitstellung können Sie einen Trunk zwischen einem Vermittlungsserver und einem oder mehreren der folgenden Peers konfigurieren, um PSTN-Verbindungen (Public Switched Telephone Network) für Enterprise-VoIP Clients und Geräte in Ihrer Organisation bereitzustellen:

- SIP-Trunkverbindung mit einem Anbieter von Internettelefoniediensten
- PSTN-Gateway
- Nebenstellenanlage (Private Branch Exchange, PBX)

Ausführliche Informationen finden Sie unter [Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).

> [!IMPORTANT]
> Bevor Sie mit der Trunkkonfiguration beginnen, überprüfen Sie, ob die Topologie erstellt und der Vermittlungsserver und der Peer konfiguriert und einander zugeordnet wurden. Ausführliche Informationen finden Sie unter [Definieren eines Gateways im Topologie-Generator in Skype for Business Server.](../../deploy/deploy-enterprise-voice/define-a-gateway.md)

> [!NOTE]
> Als Teil der Trunkkonfiguration können Sie die Skype for Business Server Medienumgehungsfunktion aktivieren, mit der Medien den Vermittlungsserver umgehen können. Trunks können mit oder ohne Medienumgehung konfiguriert werden, die Aktivierung dieser Funktion wird jedoch dringend empfohlen. Ausführliche Informationen finden Sie unter [Plan for media bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).
