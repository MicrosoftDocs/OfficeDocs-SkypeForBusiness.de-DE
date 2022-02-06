---
title: Hinzufügen eines Office Web Apps-Servers
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
ROBOTS: 'NOINDEX, NOFOLLOW'
description: 'Der Assistent zum Definieren neuer Office Web Apps-Server definiert einen neuen Office Web Apps-Server in Ihrer Bereitstellung. Sie geben die folgenden Informationen ein:'
---

# <a name="add-office-web-apps-server"></a>Hinzufügen eines Office Web Apps-Servers

Der Assistent zum **Definieren neuer Office Web Apps-Server** definiert einen neuen Office Web Apps-Server in Ihrer Bereitstellung. Sie geben die folgenden Informationen ein:

 **Office Web Apps Server FQDN**: Geben Sie den vollqualifizierten Domänennamen des Servers ein, der den Office Web Apps-Server hosten soll.

 **Office Web Apps Server Discovery URL**: Geben Sie den vollständigen URL (Uniform Resource Locator) des Office Web Apps-Servers ein.

> [!TIP]
> Das Standardverhalten der **Office Web Apps Server Discovery-URL** besteht darin, die URL basierend auf dem FQDN des Office Web Apps-Servers im Format zu erstellen: `https://<FQDN of the Office Web Apps Server/hosting/discovery` . In den meisten Fällen müssen Sie das Standardformat nicht ändern. Möglicherweise müssen Sie das Standardformat für den Fall ändern, dass der Office Web Apps-Server und die Office Web Apps-Serverermittlungs-URL unterschiedlich sein müssen. Ihr Office Web Apps-Server befindet sich beispielsweise im Umkreisnetzwerk und weist basierend auf dem Standort eine andere URL auf.

 **Office Web Apps-Server in einem externen Netzwerk bereitgestellt wird (d. h. Umkreis/Internet):** Aktivieren Sie das Kontrollkästchen, wenn ihr Office Web Apps-Server außerhalb der internen Firewall platziert wird, z. B. um das Umkreisnetzwerk, das externe Netzwerk oder eine andere Netzwerkzone, die nicht dem internen Netzwerk entspricht.

## <a name="see-also"></a>Siehe auch

[Komponenten und Topologien für Konferenzen](/previous-versions/office/lync-server-2013/lync-server-2013-components-and-topologies-for-conferencing)