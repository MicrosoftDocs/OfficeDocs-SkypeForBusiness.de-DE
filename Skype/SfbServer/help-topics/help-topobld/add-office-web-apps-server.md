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
description: 'Der Assistent Neuen Office Web Apps Server definieren definiert einen neuen Office Web Apps Server in Ihrer Bereitstellung. Sie geben die folgenden Informationen ein:'
ms.openlocfilehash: 002566fb77539745d1d0023159e9af7852b1ecdc
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119704"
---
# <a name="add-office-web-apps-server"></a>Hinzufügen eines Office Web Apps-Servers

Der **Assistent Neuen Office Web Apps Server definieren** definiert einen neuen Office Web Apps Server in Ihrer Bereitstellung. Sie geben die folgenden Informationen ein:

 **Office Web Apps Server FQDN**: Geben Sie den vollqualifizierten Domänennamen des Servers ein, der den Office Web Apps Server hosten soll

 **Office Web Apps Server-Discovery-URL**: Geben Sie den vollständigen einheitlichen Ressourcen-Locator (URL) des Office Web Apps Server ein.

> [!TIP]
> Das Standardverhalten der **Office Web Apps Server-Discovery-URL** besteht im Erstellen der URL basierend auf dem FQDN des Office Web Apps Server im Format: `https://<FQDN of the Office Web Apps Server/hosting/discovery` . In den meisten Fällen müssen Sie das Standardformat nicht ändern. Möglicherweise müssen Sie das Standardformat ändern, wenn der Office Web Apps Server und die Office Web Apps Server-Discovery-URL unterschiedlich sein müssen. Ihr Office Web Apps Server wird beispielsweise im Umkreisnetzwerk platziert und hat eine andere URL basierend auf dem Standort.

 Office Web Apps Server wird in einem externen Netzwerk (d. h. **Umkreis/Internet)** bereitgestellt: Aktivieren Sie das Kontrollkästchen, wenn Sich Ihr Office Web Apps Server außerhalb Ihrer internen Firewall befindet, z. B. das Umkreisnetzwerk, das externe Netzwerk oder eine andere Netzwerkzone, die nicht mit dem internen Netzwerk identisch ist.

## <a name="see-also"></a>Siehe auch

[Komponenten und Topologien für Konferenzen](/previous-versions/office/lync-server-2013/lync-server-2013-components-and-topologies-for-conferencing)