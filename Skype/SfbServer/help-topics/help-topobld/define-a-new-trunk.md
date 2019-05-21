---
title: Definieren eines neuen Trunks
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
description: 'Sie definieren einen neuen SIP-Trunk (Session Initiation Protocol), indem Sie die folgenden Informationen bereitstellen:'
ms.openlocfilehash: c66d5999d6aa5bad0e9c16f8d466d82b941a630b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305922"
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
