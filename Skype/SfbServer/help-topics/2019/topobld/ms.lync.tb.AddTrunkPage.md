---
title: Definieren eines neuen Trunks
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
ROBOTS: NOINDEX, NOFOLLOW
description: 'Definieren Sie einen neuen Session Initiation Protocol (SIP) Trunk, indem Sie die folgenden Informationen bereitstellen:'
ms.openlocfilehash: 206e2c1f23782bb3648dfc7c2a0eb1f26ca98d3f
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2018
ms.locfileid: "23260629"
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

[M: n-Trunk in Skype für Business Server](../../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[Implementierung von SIP-Trunking](https://technet.microsoft.com/library/273a22b1-8a4c-4187-acf8-c57d5c6598ce.aspx)