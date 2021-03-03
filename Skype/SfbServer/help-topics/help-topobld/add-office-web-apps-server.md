---
title: Hinzufügen eines Office Web Apps-Servers
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
description: 'Der Assistent zum Definieren eines neuen Office Web Apps Server definiert einen neuen Office Web Apps Server in Ihrer Bereitstellung. Geben Sie die folgenden Informationen ein:'
ms.openlocfilehash: a0d0543576b75e0572abf3fd043a73369d2af136
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828595"
---
# <a name="add-office-web-apps-server"></a>Hinzufügen eines Office Web Apps-Servers

Der **Assistent zum Definieren eines neuen Office Web Apps Server** definiert einen neuen Office Web Apps Server in Ihrer Bereitstellung. Geben Sie die folgenden Informationen ein:

 **FQDN des Office Web Apps Server:** Geben Sie den vollqualifizierten Domänennamen des Servers ein, der den Office Web Apps Server hosten soll.

 **Office Web Apps Server-Such-URL:** Geben Sie die vollständige URL (Uniform Resource Locator) des Office Web Apps Server ein.

> [!TIP]
> Das Standardverhalten der **Office Web Apps Server-Such-URL** besteht im Erstellen der URL basierend auf dem FQDN des Office Web Apps Server im Format: `https://<FQDN of the Office Web Apps Server/hosting/discovery` . In den meisten Fällen müssen Sie das Standardformat nicht ändern. Möglicherweise müssen Sie das Standardformat für den Fall ändern, dass der Office Web Apps Server und die Office Web Apps Server-Discovery-URL unterschiedlich sein müssen. Beispielsweise befindet sich Ihr Office Web Apps Server im Umkreisnetzwerk und hat je nach Standort eine andere URL.

 Office Web Apps Server wird in einem externen Netzwerk (d. h. **Umkreisnetzwerk/Internet)** bereitgestellt: Aktivieren Sie das Kontrollkästchen, wenn sich Ihr Office Web Apps Server außerhalb der internen Firewall befindet, z. B. das Umkreisnetzwerk, das externe Netzwerk oder eine andere Netzwerkzone, die nicht mit dem internen Netzwerk identisch ist.

## <a name="see-also"></a>Siehe auch

[Komponenten und Topologien für Konferenzen](https://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)
