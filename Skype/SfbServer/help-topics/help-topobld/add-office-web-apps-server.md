---
title: Hinzufügen von Office Web Apps-Servern
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
ms.openlocfilehash: 41f0d247089639713243124b622f352c04ea364d
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "19503676"
---
# <a name="add-office-web-apps-server"></a><span data-ttu-id="8f625-104">Hinzufügen von Office Web Apps-Servern</span><span class="sxs-lookup"><span data-stu-id="8f625-104">Add Office Web Apps Server</span></span>
 
<span data-ttu-id="8f625-105">Der Assistent für die **Office Web Apps-Server definieren** definiert einen neuen Office Web Apps Server in Ihrer Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="8f625-105">The **Define New Office Web Apps Server** wizard defines a new Office Web Apps Server in your deployment.</span></span> <span data-ttu-id="8f625-106">Fügen Sie die folgenden Informationen ein:</span><span class="sxs-lookup"><span data-stu-id="8f625-106">You fill in the following information:</span></span>
  
 <span data-ttu-id="8f625-107">**Office Web Apps Server-FQDN**: Geben Sie den vollqualifizierten Domänennamen des Servers, auf denen die Office Web Apps-Server gehostet wird</span><span class="sxs-lookup"><span data-stu-id="8f625-107">**Office Web Apps Server FQDN**: Type the fully qualified domain name of the server that will host the Office Web Apps Server</span></span>
  
 <span data-ttu-id="8f625-108">**Office Web Apps Server-Suchdienst-URL**: Geben Sie vollständige uniform Resource Locator (URL) von Office Web Apps-Server</span><span class="sxs-lookup"><span data-stu-id="8f625-108">**Office Web Apps Server discovery URL**: Type the full uniform resource locator (URL) of the Office Web Apps Server</span></span>
  
> [!TIP]
> <span data-ttu-id="8f625-109">Das Standardverhalten des **Office Web Apps Server-Suchdienst-URL** ist die URL basierend auf den FQDN des Office Web Apps-Server im Format erstellen: `https://<FQDN of the Office Web Apps Server/hosting/discovery` .</span><span class="sxs-lookup"><span data-stu-id="8f625-109">The default behavior of the **Office Web Apps Server discovery URL** is to create the URL based on the FQDN of the Office Web Apps Server in the format: `https://<FQDN of the Office Web Apps Server/hosting/discovery` .</span></span> <span data-ttu-id="8f625-110">Normalerweise ist es nicht erforderlich, das Standardformat zu ändern.</span><span class="sxs-lookup"><span data-stu-id="8f625-110">In most cases you will not need to change the default format.</span></span> <span data-ttu-id="8f625-111">Sie müssen das Standardformat zu ändern, die Office Web Apps Server und Office Web Apps Server-Such-URL unterschiedlich sein muss.</span><span class="sxs-lookup"><span data-stu-id="8f625-111">You may need to change the default format in the event that the Office Web Apps Server and the Office Web Apps Server discovery URL must be different.</span></span> <span data-ttu-id="8f625-112">Beispielsweise wird Ihre Office Web Apps-Server im Umkreisnetzwerk befindet und eine andere URL basierend auf dem Standort sind.</span><span class="sxs-lookup"><span data-stu-id="8f625-112">For example, your Office Web Apps Server is placed in the perimeter network and will have a different URL based on the location.</span></span>
  
 <span data-ttu-id="8f625-113">**Office Web Apps Server in einem externen Netzwerk (d. h., Umkreisnetzwerk/Internet) bereitgestellt wird**: Aktivieren Sie das Kontrollkästchen, wenn Ihre Office Web Apps Server außerhalb Ihrer internen Firewall, wie das Umkreisnetzwerk, externes Netzwerk oder andere Netzwerkzone befindet Das ist noch nicht identisch mit dem internen Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="8f625-113">**Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**: Select the check box if your Office Web Apps Server is placed outside of your internal firewall, such as the perimeter network, external network, or other network zone that is not the same as your internal network.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8f625-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8f625-114">See also</span></span>

[<span data-ttu-id="8f625-115">Komponenten und Topologien für Konferenzen</span><span class="sxs-lookup"><span data-stu-id="8f625-115">Components and Topologies for Conferencing</span></span>](http://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)