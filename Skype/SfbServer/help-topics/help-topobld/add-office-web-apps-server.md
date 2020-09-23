---
title: Hinzufügen von Office Web Apps-Servern
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Der Assistent zum Definieren eines neuen Office-webapps-Servers definiert einen neuen Office-webapps-Server in Ihrer Bereitstellung. Geben Sie die folgenden Informationen ein:'
ms.openlocfilehash: 9e1726ea4b536e46fdbca5ec3eddce25358cbbbb
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218726"
---
# <a name="add-office-web-apps-server"></a>Hinzufügen von Office Web Apps-Servern

Der Assistent zum **Definieren eines neuen Office-webapps-Servers** definiert einen neuen Office-webapps-Server in Ihrer Bereitstellung. Geben Sie die folgenden Informationen ein:

 **Office-webapps-Server-FQDN**: Geben Sie den vollqualifizierten Domänennamen des Servers ein, auf dem der Office-webapps-Server gehostet wird.

 **Office webapps Server Discovery-URL**: Geben Sie den vollständigen URL (Uniform Resource Locator) des Office-webapps-Servers ein.

> [!TIP]
> Das Standardverhalten der **Office webapps Server Discovery-URL** besteht darin, die URL basierend auf dem FQDN des Office-webapps-Servers im folgenden Format zu erstellen: `https://<FQDN of the Office Web Apps Server/hosting/discovery` . In den meisten Fällen ist es nicht erforderlich, das Standardformat zu ändern. Möglicherweise müssen Sie das Standardformat ändern, falls der Office-webapps-Server und die Office-webapps-Server Erkennungs-URL unterschiedlich sein müssen. Beispielsweise wird Ihr Office-webapps-Server im Umkreisnetzwerk gespeichert, und es wird eine andere URL auf der Grundlage des Speicherorts angegeben.

 **Office Web Apps Server wird in einem externen Netzwerk (Perimeter/Internet) bereitgestellt**: Aktivieren Sie das Kontrollkästchen, wenn Ihr Office Web Apps-Server außerhalb ihrer internen Firewall wie das Umkreisnetzwerk, das externe Netzwerk oder eine andere Netzwerkzone positioniert ist, die nicht mit dem internen Netzwerk identisch ist.

## <a name="see-also"></a>Siehe auch

[Komponenten und Topologien für Konferenzen](https://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)
