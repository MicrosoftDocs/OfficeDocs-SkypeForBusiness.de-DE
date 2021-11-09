---
title: Definieren eines neuen Trunks
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
ROBOTS: NOINDEX, NOFOLLOW
description: 'Definieren Sie einen neuen SIP-Trunk (Session Initiation Protocol), indem Sie die folgenden Informationen angeben:'
ms.openlocfilehash: 7e6c80b3f5762dc409a47ee4b9e6f7ff9053b84c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60836897"
---
# <a name="define-a-new-trunk"></a>Definieren eines neuen Trunks

Definieren Sie einen neuen SIP-Trunk (Session Initiation Protocol), indem Sie die folgenden Informationen angeben:

- **Trunkname**: Eindeutiger Name in der Topologie, mit dem der Trunk identifiziert wird.

- **Zugeordnetes PSTN-Gateway**: Wählen Sie in der Liste ein PSTN-Gateway aus, das in der Bereitstellung vorhanden und konfiguriert ist.

- **Überwachungsport für IP/PSTN-Gateway**: Port, der von der Festnetztelefonanlage oder vom PSTN-Gateway überwacht wird. Der Port muss gegenüber allen anderen Trunküberwachungsports, die in der Bereitstellung definiert sind, eindeutig sein.

- **SIP-Transportprotokoll**: Wählen Sie in der Liste entweder TCP oder TLS aus.

- **Zugeordneter Vermittlungsserver:** Wählen Sie in der Liste einen Vermittlungsserver aus, der in Ihrer Bereitstellung bereitgestellt und konfiguriert ist

- **Zugeordneter Vermittlungsserverport:** Legen Sie den Portwert auf den TCP- oder TLS-Portwert des Vermittlungsservers fest, den dieser SIP-Trunk verwendet.

## <a name="see-also"></a>Siehe auch

[M:N-Trunk in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[Wie implementiere ich SIP-Trunking?](/previous-versions/office/lync-server-2013/lync-server-2013-how-do-i-implement-sip-trunking)