---
title: Definieren eines neuen Trunks
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
description: 'Definieren Sie einen neuen SIP-Trunk (Session Initiation Protocol), indem Sie die folgenden Informationen angeben:'
ms.openlocfilehash: bbed07920bdeddb78217e435e8813c89231cdcc9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833045"
---
# <a name="define-a-new-trunk"></a>Definieren eines neuen Trunks

Definieren Sie einen neuen SIP-Trunk (Session Initiation Protocol), indem Sie die folgenden Informationen angeben:

- **Trunkname**: Eindeutiger Name in der Topologie, mit dem der Trunk identifiziert wird.

- **Zugeordnetes PSTN-Gateway**: Wählen Sie in der Liste ein PSTN-Gateway aus, das in der Bereitstellung vorhanden und konfiguriert ist.

- **Überwachungsport für IP/PSTN-Gateway**: Port, der von der Festnetztelefonanlage oder vom PSTN-Gateway überwacht wird. Der Port muss gegenüber allen anderen Trunküberwachungsports, die in der Bereitstellung definiert sind, eindeutig sein.

- **SIP-Transportprotokoll**: Wählen Sie in der Liste entweder TCP oder TLS aus.

- **Zugeordneter Vermittlungsserver:** Wählen Sie in der Liste einen Vermittlungsserver aus, der in Ihrer Bereitstellung bereitgestellt und konfiguriert ist

- **Zugeordneter Vermittlungsserverport:** Legen Sie den Portwert auf den TCP- oder TLS-Portwert des Vermittlungsservers fest, der von diesem SIP-Trunk verwendet wird.

## <a name="see-also"></a>Siehe auch

[M:N-Trunk in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[Wie kann ich das SIP-Trunking implementieren?](https://technet.microsoft.com/library/273a22b1-8a4c-4187-acf8-c57d5c6598ce.aspx)
