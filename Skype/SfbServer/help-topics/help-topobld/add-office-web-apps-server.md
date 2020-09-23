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
# <a name="add-office-web-apps-server"></a><span data-ttu-id="99923-104">Hinzufügen von Office Web Apps-Servern</span><span class="sxs-lookup"><span data-stu-id="99923-104">Add Office Web Apps Server</span></span>

<span data-ttu-id="99923-105">Der Assistent zum **Definieren eines neuen Office-webapps-Servers** definiert einen neuen Office-webapps-Server in Ihrer Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="99923-105">The **Define New Office Web Apps Server** wizard defines a new Office Web Apps Server in your deployment.</span></span> <span data-ttu-id="99923-106">Geben Sie die folgenden Informationen ein:</span><span class="sxs-lookup"><span data-stu-id="99923-106">You fill in the following information:</span></span>

 <span data-ttu-id="99923-107">**Office-webapps-Server-FQDN**: Geben Sie den vollqualifizierten Domänennamen des Servers ein, auf dem der Office-webapps-Server gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="99923-107">**Office Web Apps Server FQDN**: Type the fully qualified domain name of the server that will host the Office Web Apps Server</span></span>

 <span data-ttu-id="99923-108">**Office webapps Server Discovery-URL**: Geben Sie den vollständigen URL (Uniform Resource Locator) des Office-webapps-Servers ein.</span><span class="sxs-lookup"><span data-stu-id="99923-108">**Office Web Apps Server discovery URL**: Type the full uniform resource locator (URL) of the Office Web Apps Server</span></span>

> [!TIP]
> <span data-ttu-id="99923-109">Das Standardverhalten der **Office webapps Server Discovery-URL** besteht darin, die URL basierend auf dem FQDN des Office-webapps-Servers im folgenden Format zu erstellen: `https://<FQDN of the Office Web Apps Server/hosting/discovery` .</span><span class="sxs-lookup"><span data-stu-id="99923-109">The default behavior of the **Office Web Apps Server discovery URL** is to create the URL based on the FQDN of the Office Web Apps Server in the format: `https://<FQDN of the Office Web Apps Server/hosting/discovery` .</span></span> <span data-ttu-id="99923-110">In den meisten Fällen ist es nicht erforderlich, das Standardformat zu ändern.</span><span class="sxs-lookup"><span data-stu-id="99923-110">In most cases you will not need to change the default format.</span></span> <span data-ttu-id="99923-111">Möglicherweise müssen Sie das Standardformat ändern, falls der Office-webapps-Server und die Office-webapps-Server Erkennungs-URL unterschiedlich sein müssen.</span><span class="sxs-lookup"><span data-stu-id="99923-111">You may need to change the default format in the event that the Office Web Apps Server and the Office Web Apps Server discovery URL must be different.</span></span> <span data-ttu-id="99923-112">Beispielsweise wird Ihr Office-webapps-Server im Umkreisnetzwerk gespeichert, und es wird eine andere URL auf der Grundlage des Speicherorts angegeben.</span><span class="sxs-lookup"><span data-stu-id="99923-112">For example, your Office Web Apps Server is placed in the perimeter network and will have a different URL based on the location.</span></span>

 <span data-ttu-id="99923-113">**Office Web Apps Server wird in einem externen Netzwerk (Perimeter/Internet) bereitgestellt**: Aktivieren Sie das Kontrollkästchen, wenn Ihr Office Web Apps-Server außerhalb ihrer internen Firewall wie das Umkreisnetzwerk, das externe Netzwerk oder eine andere Netzwerkzone positioniert ist, die nicht mit dem internen Netzwerk identisch ist.</span><span class="sxs-lookup"><span data-stu-id="99923-113">**Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**: Select the check box if your Office Web Apps Server is placed outside of your internal firewall, such as the perimeter network, external network, or other network zone that is not the same as your internal network.</span></span>

## <a name="see-also"></a><span data-ttu-id="99923-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="99923-114">See also</span></span>

[<span data-ttu-id="99923-115">Komponenten und Topologien für Konferenzen</span><span class="sxs-lookup"><span data-stu-id="99923-115">Components and Topologies for Conferencing</span></span>](https://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)
