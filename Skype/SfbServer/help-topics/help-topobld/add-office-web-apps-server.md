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
- NOCSH
ms.custom:
- ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
description: 'Der Assistent zum Definieren eines neuen Office Web Apps-Servers definiert einen neuen Office Web Apps-Server in Ihrer Bereitstellung. Fügen Sie die folgenden Informationen ein:'
ms.openlocfilehash: 9f0d9680e57dd55b0a4370364aff23c7f37f57a4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820717"
---
# <a name="add-office-web-apps-server"></a><span data-ttu-id="10c55-104">Hinzufügen von Office Web Apps-Servern</span><span class="sxs-lookup"><span data-stu-id="10c55-104">Add Office Web Apps Server</span></span>

<span data-ttu-id="10c55-105">Der Assistent zum **Definieren eines neuen Office Web Apps-Servers** definiert einen neuen Office Web Apps-Server in Ihrer Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="10c55-105">The **Define New Office Web Apps Server** wizard defines a new Office Web Apps Server in your deployment.</span></span> <span data-ttu-id="10c55-106">Fügen Sie die folgenden Informationen ein:</span><span class="sxs-lookup"><span data-stu-id="10c55-106">You fill in the following information:</span></span>

 <span data-ttu-id="10c55-107">**Office Web Apps Server-FQDN**: Geben Sie den vollqualifizierten Domänennamen des Servers ein, auf dem der Office Web Apps-Server gehostet werden soll.</span><span class="sxs-lookup"><span data-stu-id="10c55-107">**Office Web Apps Server FQDN**: Type the fully qualified domain name of the server that will host the Office Web Apps Server</span></span>

 <span data-ttu-id="10c55-108">**Office Web Apps Server Discovery-URL**: Geben Sie den vollständigen URL (Uniform Resource Locator) des Office Web Apps-Servers ein.</span><span class="sxs-lookup"><span data-stu-id="10c55-108">**Office Web Apps Server discovery URL**: Type the full uniform resource locator (URL) of the Office Web Apps Server</span></span>

> [!TIP]
> <span data-ttu-id="10c55-109">Das Standardverhalten der **Office Web Apps Server Discovery-URL** besteht im Erstellen der URL basierend auf dem FQDN des Office Web Apps-Servers im Format: `https://<FQDN of the Office Web Apps Server/hosting/discovery` .</span><span class="sxs-lookup"><span data-stu-id="10c55-109">The default behavior of the **Office Web Apps Server discovery URL** is to create the URL based on the FQDN of the Office Web Apps Server in the format: `https://<FQDN of the Office Web Apps Server/hosting/discovery` .</span></span> <span data-ttu-id="10c55-110">Normalerweise ist es nicht erforderlich, das Standardformat zu ändern.</span><span class="sxs-lookup"><span data-stu-id="10c55-110">In most cases you will not need to change the default format.</span></span> <span data-ttu-id="10c55-111">Möglicherweise müssen Sie das Standardformat für den Fall ändern, dass der Office Web Apps-Server und die Office Web Apps Server Discovery-URL unterschiedlich sein müssen.</span><span class="sxs-lookup"><span data-stu-id="10c55-111">You may need to change the default format in the event that the Office Web Apps Server and the Office Web Apps Server discovery URL must be different.</span></span> <span data-ttu-id="10c55-112">Beispielsweise wird der Office Web Apps-Server im Umkreisnetzwerk gespeichert, und es wird eine andere URL basierend auf dem Standort vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="10c55-112">For example, your Office Web Apps Server is placed in the perimeter network and will have a different URL based on the location.</span></span>

 <span data-ttu-id="10c55-113">**Office Web Apps Server wird in einem externen Netzwerk bereitgestellt (also Umkreis/Internet)**: Aktivieren Sie das Kontrollkästchen, wenn der Office Web Apps-Server außerhalb ihrer internen Firewall wie dem Umkreisnetzwerk, externen Netzwerk oder einer anderen Netzwerkzone, die nicht mit Ihrem internen Netzwerk identisch ist, positioniert wird.</span><span class="sxs-lookup"><span data-stu-id="10c55-113">**Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**: Select the check box if your Office Web Apps Server is placed outside of your internal firewall, such as the perimeter network, external network, or other network zone that is not the same as your internal network.</span></span>

## <a name="see-also"></a><span data-ttu-id="10c55-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="10c55-114">See also</span></span>

[<span data-ttu-id="10c55-115">Components and Topologies for Conferencing</span><span class="sxs-lookup"><span data-stu-id="10c55-115">Components and Topologies for Conferencing</span></span>](https://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)
