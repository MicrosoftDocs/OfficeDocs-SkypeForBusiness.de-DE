---
title: Definieren eines neuen Trunks
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
description: 'Definieren Sie einen neuen Session Initiation Protocol (SIP) Trunk, indem Sie die folgenden Informationen bereitstellen:'
ms.openlocfilehash: 669f896e9a51a2f7f229a065a867f8ce8e48bcdc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33903782"
---
# <a name="define-a-new-trunk"></a>Definieren eines neuen Trunks

Definieren Sie einen neuen Session Initiation Protocol (SIP) Trunk, indem Sie die folgenden Informationen bereitstellen:

- **Trunkname**: eindeutiger Name in der Topologie, die diesem Trunk identifiziert werden können

- **Zugeordnete PSTN-Gateway**: Wählen Sie ein PSTN-Gateway bereitgestellt und konfiguriert in Ihrer Bereitstellung aus der Liste aus.

- **Überwachungsport für IP/PSTN-Gateway**: Port, der die IP-Nebenstellenanlage oder PSTN-Gateways überwacht wird. Muss eindeutig aus allen anderen Trunk Überwachungsports in Ihrer Bereitstellung konfiguriert sein

- **SIP-Transportprotokoll**: Wählen Sie aus der Liste entweder TCP oder TLS

- **Zugeordneter Vermittlungsserver**: Wählen Sie aus der Liste einen Vermittlungsserver, die bereitgestellt und in der Bereitstellung konfiguriert ist

- **Zugeordneter Vermittlungsserver Port**: Legen Sie den Wert für Port auf den TCP oder TLS-Portwert des Vermittlungsservers, die diesem SIP-Trunk verwendet werden soll

## <a name="see-also"></a>Siehe auch

[M:N-Trunk in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[Implementierung SIP-trunking](https://technet.microsoft.com/library/273a22b1-8a4c-4187-acf8-c57d5c6598ce.aspx)
