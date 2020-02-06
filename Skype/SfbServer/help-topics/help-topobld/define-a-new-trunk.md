---
title: Definieren eines neuen Trunks
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
description: 'Sie definieren einen neuen SIP-Trunk (Session Initiation Protocol), indem Sie die folgenden Informationen bereitstellen:'
ms.openlocfilehash: 9b3d42500c57723b13d9c74668b3c4ad7159301b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820217"
---
# <a name="define-a-new-trunk"></a>Definieren eines neuen Trunks

Sie definieren einen neuen SIP-Trunk (Session Initiation Protocol), indem Sie die folgenden Informationen bereitstellen:

- **Trunk Name**: eindeutiger Name in Ihrer Topologie, mit dem dieser trunk identifiziert wird

- **Zugeordnetes PSTN-Gateway**: Wählen Sie ein bereitgestelltes und konfiguriertes PSTN-Gateway in Ihrer Bereitstellung aus der Liste aus.

- **Abhör-Port für das IP/PSTN-Gateway**: Port, den das IP-PBX-oder PSTN-Gateway anhört. Muss für alle anderen trunk-Abhör Anschlüsse eindeutig sein, die in Ihrer Bereitstellung konfiguriert sind

- **SIP-Transport Protokoll**: Wählen Sie in der Liste entweder TCP oder TLS aus.

- **Zugeordneter Vermittlungsserver**: Wählen Sie in der Liste einen Vermittlungsserver aus, der in Ihrer Bereitstellung bereitgestellt und konfiguriert wird.

- **Zugeordneter Vermittlungsserver-Port**: setzen Sie den Portwert gleich dem TCP-oder TLS-Portwert des Vermittlungsservers, den dieser SIP-Trunk verwenden soll.

## <a name="see-also"></a>Siehe auch

[M:N-Trunk in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[Wie kann ich SIP-Trunking implementieren?](https://technet.microsoft.com/library/273a22b1-8a4c-4187-acf8-c57d5c6598ce.aspx)
