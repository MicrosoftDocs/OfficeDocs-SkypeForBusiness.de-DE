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
description: Im Rahmen Enterprise-VoIP können Sie einen Trunk zwischen einem Vermittlungsserver und einem oder mehreren Peers konfigurieren, um Konnektivität über das Telefonnetz (Public Switched Telephone Network, PSTN) für Enterprise-VoIP Clients und Geräte in Ihrer Organisation zu ermöglichen.
ms.openlocfilehash: 57b8635d635c0fd0b8c41c95f92af768ff84dfd4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800115"
---
# <a name="configuring-trunks-in-skype-for-business-server"></a>Konfigurieren von Trunks in Skype for Business Server

Im Rahmen der Enterprise-VoIP können Sie einen Trunk zwischen einem Vermittlungsserver und einem oder mehreren der folgenden Peers konfigurieren, um Konnektivität über das Telefonnetz (Public Switched Telephone Network, PSTN) für Enterprise-VoIP-Clients und -Geräte in Ihrer Organisation zu ermöglichen:

- SIP-Trunkverbindung mit einem Anbieter von Internettelefoniediensten
- PSTN-Gateway
- Nebenstellenanlage (Private Branch Exchange, PBX)

Weitere Informationen finden Sie unter [Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).

> [!IMPORTANT]
> Bevor Sie mit der Trunkkonfiguration beginnen, überprüfen Sie, ob die Topologie erstellt und der Vermittlungsserver und der Peer konfiguriert und einander zugeordnet wurden. Weitere Informationen finden Sie unter [Definieren eines Gateways im Topologie-Generator in Skype for Business Server.](../../deploy/deploy-enterprise-voice/define-a-gateway.md)

> [!NOTE]
> Im Rahmen der Trunkkonfiguration können Sie die Medienumgehungsfunktion von Skype for Business Server aktivieren, mit der Medien den Vermittlungsserver umgehen können. Trunks können mit oder ohne Medienumgehung konfiguriert werden, die Aktivierung dieser Funktion wird jedoch dringend empfohlen. Weitere Informationen finden Sie unter ["Planen der Medienumgehung in Skype for Business".](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
