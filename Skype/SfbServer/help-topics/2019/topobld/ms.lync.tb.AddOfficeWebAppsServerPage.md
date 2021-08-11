---
title: Hinzufügen eines Office Web Apps-Servers
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
ROBOTS: NOINDEX, NOFOLLOW
description: 'Der Assistent zum Definieren neuer Office Web Apps-Server definiert einen neuen Office Web Apps-Server in Ihrer Bereitstellung. Sie geben die folgenden Informationen ein:'
ms.openlocfilehash: 92dfe7d681453e432c7d1e3fb32377db32995641d5e7e47982db86af8185295a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54302789"
---
# <a name="add-office-web-apps-server"></a>Hinzufügen eines Office Web Apps-Servers

Der Assistent zum **Definieren neuer Office Web Apps-Server** definiert einen neuen Office Web Apps-Server in Ihrer Bereitstellung. Sie geben die folgenden Informationen ein:

 **Office Web Apps Server FQDN:** Geben Sie den vollqualifizierten Domänennamen des Servers ein, der den Office Web Apps-Server hosten soll.

 **Office Web Apps Server Discovery-URL:** Geben Sie den vollständigen URL (Uniform Resource Locator) des Office Web Apps-Servers ein.

> [!TIP]
> Das Standardverhalten der **Office Web Apps Server Discovery-URL** besteht darin, die URL basierend auf dem FQDN des Office Web Apps-Servers im folgenden Format zu erstellen: `https://<FQDN of the Office Web Apps Server/hosting/discovery` . In den meisten Fällen müssen Sie das Standardformat nicht ändern. Möglicherweise müssen Sie das Standardformat für den Fall ändern, dass der Office Web Apps-Server und die Office Web Apps Server Discovery-URL unterschiedlich sein müssen. Ihr Office Web Apps-Server befindet sich beispielsweise im Umkreisnetzwerk und weist basierend auf dem Standort eine andere URL auf.

 **Office Web Apps-Server in einem externen Netzwerk (d. h. Umkreis/Internet) bereitgestellt wird:** Aktivieren Sie das Kontrollkästchen, wenn ihr Office Web Apps-Server außerhalb der internen Firewall platziert wird, z. B. um das Umkreisnetzwerk, das externe Netzwerk oder eine andere Netzwerkzone, die nicht dem internen Netzwerk entspricht.

## <a name="see-also"></a>Siehe auch

[Komponenten und Topologien für Konferenzen](/previous-versions/office/lync-server-2013/lync-server-2013-components-and-topologies-for-conferencing)