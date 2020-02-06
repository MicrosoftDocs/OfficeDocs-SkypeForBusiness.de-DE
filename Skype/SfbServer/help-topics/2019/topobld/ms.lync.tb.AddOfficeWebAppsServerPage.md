---
title: Hinzufügen von Office Web Apps-Servern
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Der Assistent zum Definieren eines neuen Office Web Apps-Servers definiert einen neuen Office Web Apps-Server in Ihrer Bereitstellung. Fügen Sie die folgenden Informationen ein:'
ms.openlocfilehash: 9ca5be070d4a79a2cb011a1e91bd0613f21e8700
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798452"
---
# <a name="add-office-web-apps-server"></a>Hinzufügen von Office Web Apps-Servern

Der Assistent zum **Definieren eines neuen Office Web Apps-Servers** definiert einen neuen Office Web Apps-Server in Ihrer Bereitstellung. Fügen Sie die folgenden Informationen ein:

 **Office Web Apps Server-FQDN**: Geben Sie den vollqualifizierten Domänennamen des Servers ein, auf dem der Office Web Apps-Server gehostet werden soll.

 **Office Web Apps Server Discovery-URL**: Geben Sie den vollständigen URL (Uniform Resource Locator) des Office Web Apps-Servers ein.

> [!TIP]
> Das Standardverhalten der **Office Web Apps Server Discovery-URL** besteht im Erstellen der URL basierend auf dem FQDN des Office Web Apps-Servers im Format: `https://<FQDN of the Office Web Apps Server/hosting/discovery` . Normalerweise ist es nicht erforderlich, das Standardformat zu ändern. Möglicherweise müssen Sie das Standardformat für den Fall ändern, dass der Office Web Apps-Server und die Office Web Apps Server Discovery-URL unterschiedlich sein müssen. Beispielsweise wird der Office Web Apps-Server im Umkreisnetzwerk gespeichert, und es wird eine andere URL basierend auf dem Standort vorhanden sein.

 **Office Web Apps Server wird in einem externen Netzwerk bereitgestellt (also Umkreis/Internet)**: Aktivieren Sie das Kontrollkästchen, wenn der Office Web Apps-Server außerhalb ihrer internen Firewall wie dem Umkreisnetzwerk, externen Netzwerk oder einer anderen Netzwerkzone, die nicht mit Ihrem internen Netzwerk identisch ist, positioniert wird.

## <a name="see-also"></a>Siehe auch

[Components and Topologies for Conferencing](https://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)
