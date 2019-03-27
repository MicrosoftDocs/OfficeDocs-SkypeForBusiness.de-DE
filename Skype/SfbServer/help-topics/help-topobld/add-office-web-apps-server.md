---
title: Hinzufügen von Office Web Apps-Servern
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
description: 'Der Assistent für die Office Web Apps-Server definieren definiert einen neuen Office Web Apps Server in Ihrer Bereitstellung. Fügen Sie die folgenden Informationen ein:'
ms.openlocfilehash: 79f07ab88f62ba9b7e886b06b6d7c89143cd7380
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30873319"
---
# <a name="add-office-web-apps-server"></a>Hinzufügen von Office Web Apps-Servern

Der Assistent für die **Office Web Apps-Server definieren** definiert einen neuen Office Web Apps Server in Ihrer Bereitstellung. Fügen Sie die folgenden Informationen ein:

 **Office Web Apps Server-FQDN**: Geben Sie den vollqualifizierten Domänennamen des Servers, auf denen die Office Web Apps-Server gehostet wird

 **Office Web Apps Server-Suchdienst-URL**: Geben Sie vollständige uniform Resource Locator (URL) von Office Web Apps-Server

> [!TIP]
> Das Standardverhalten des **Office Web Apps Server-Suchdienst-URL** ist die URL basierend auf den FQDN des Office Web Apps-Server im Format erstellen: `https://<FQDN of the Office Web Apps Server/hosting/discovery` . Normalerweise ist es nicht erforderlich, das Standardformat zu ändern. Sie müssen das Standardformat zu ändern, die Office Web Apps Server und Office Web Apps Server-Such-URL unterschiedlich sein muss. Beispielsweise wird Ihre Office Web Apps-Server im Umkreisnetzwerk befindet und eine andere URL basierend auf dem Standort sind.

 **Office Web Apps Server in einem externen Netzwerk (d. h., Umkreisnetzwerk/Internet) bereitgestellt wird**: Aktivieren Sie das Kontrollkästchen, wenn Ihre Office Web Apps Server außerhalb Ihrer internen Firewall, wie das Umkreisnetzwerk, externes Netzwerk oder andere Netzwerkzone befindet Das ist noch nicht identisch mit dem internen Netzwerk.

## <a name="see-also"></a>Siehe auch

[Components and Topologies for Conferencing](https://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)
