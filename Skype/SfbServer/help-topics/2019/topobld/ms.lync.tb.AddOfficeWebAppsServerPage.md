---
title: Hinzufügen von Office Web Apps-Servern
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
ROBOTS: NOINDEX, NOFOLLOW
description: 'Der Assistent zum Definieren eines neuen Office Web Apps-Servers definiert einen neuen Office Web Apps-Server in Ihrer Bereitstellung. Fügen Sie die folgenden Informationen ein:'
ms.openlocfilehash: 207feb9187c880d43a5ce92eb6e93c6a5eedd44f
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41702770"
---
# <a name="add-office-web-apps-server"></a><span data-ttu-id="bb6f6-104">Hinzufügen von Office Web Apps-Servern</span><span class="sxs-lookup"><span data-stu-id="bb6f6-104">Add Office Web Apps Server</span></span>

<span data-ttu-id="bb6f6-105">Der Assistent zum **Definieren eines neuen Office Web Apps-Servers** definiert einen neuen Office Web Apps-Server in Ihrer Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="bb6f6-105">The **Define New Office Web Apps Server** wizard defines a new Office Web Apps Server in your deployment.</span></span> <span data-ttu-id="bb6f6-106">Fügen Sie die folgenden Informationen ein:</span><span class="sxs-lookup"><span data-stu-id="bb6f6-106">You fill in the following information:</span></span>

 <span data-ttu-id="bb6f6-107">**Office Web Apps Server-FQDN**: Geben Sie den vollqualifizierten Domänennamen des Servers ein, auf dem der Office Web Apps-Server gehostet werden soll.</span><span class="sxs-lookup"><span data-stu-id="bb6f6-107">**Office Web Apps Server FQDN**: Type the fully qualified domain name of the server that will host the Office Web Apps Server</span></span>

 <span data-ttu-id="bb6f6-108">**Office Web Apps Server Discovery-URL**: Geben Sie den vollständigen URL (Uniform Resource Locator) des Office Web Apps-Servers ein.</span><span class="sxs-lookup"><span data-stu-id="bb6f6-108">**Office Web Apps Server discovery URL**: Type the full uniform resource locator (URL) of the Office Web Apps Server</span></span>

> [!TIP]
> <span data-ttu-id="bb6f6-109">Das Standardverhalten der **Office Web Apps Server Discovery-URL** besteht im Erstellen der URL basierend auf dem FQDN des Office Web Apps-Servers im Format: `https://<FQDN of the Office Web Apps Server/hosting/discovery` .</span><span class="sxs-lookup"><span data-stu-id="bb6f6-109">The default behavior of the **Office Web Apps Server discovery URL** is to create the URL based on the FQDN of the Office Web Apps Server in the format: `https://<FQDN of the Office Web Apps Server/hosting/discovery` .</span></span> <span data-ttu-id="bb6f6-110">Normalerweise ist es nicht erforderlich, das Standardformat zu ändern.</span><span class="sxs-lookup"><span data-stu-id="bb6f6-110">In most cases you will not need to change the default format.</span></span> <span data-ttu-id="bb6f6-111">Möglicherweise müssen Sie das Standardformat für den Fall ändern, dass der Office Web Apps-Server und die Office Web Apps Server Discovery-URL unterschiedlich sein müssen.</span><span class="sxs-lookup"><span data-stu-id="bb6f6-111">You may need to change the default format in the event that the Office Web Apps Server and the Office Web Apps Server discovery URL must be different.</span></span> <span data-ttu-id="bb6f6-112">Beispielsweise wird der Office Web Apps-Server im Umkreisnetzwerk gespeichert, und es wird eine andere URL basierend auf dem Standort vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="bb6f6-112">For example, your Office Web Apps Server is placed in the perimeter network and will have a different URL based on the location.</span></span>

 <span data-ttu-id="bb6f6-113">**Office Web Apps Server wird in einem externen Netzwerk bereitgestellt (also Umkreis/Internet)**: Aktivieren Sie das Kontrollkästchen, wenn der Office Web Apps-Server außerhalb ihrer internen Firewall wie dem Umkreisnetzwerk, externen Netzwerk oder einer anderen Netzwerkzone, die nicht mit Ihrem internen Netzwerk identisch ist, positioniert wird.</span><span class="sxs-lookup"><span data-stu-id="bb6f6-113">**Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**: Select the check box if your Office Web Apps Server is placed outside of your internal firewall, such as the perimeter network, external network, or other network zone that is not the same as your internal network.</span></span>

## <a name="see-also"></a><span data-ttu-id="bb6f6-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bb6f6-114">See also</span></span>

[<span data-ttu-id="bb6f6-115">Components and Topologies for Conferencing</span><span class="sxs-lookup"><span data-stu-id="bb6f6-115">Components and Topologies for Conferencing</span></span>](https://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)
