---
title: Hinzufügen von Front-End-Computern
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7fe2522-1bd2-416a-9dbb-51cacea9c6e0
description: Geben Sie den vollqualifizierten Domänennamen jedes Computers an, der diesem Pool als Front-End-Server hinzugefügt werden soll. Nach dem Hinzufügen eines Computers zur Liste können Sie den vollqualifizierten Domänennamen des Computers zu einem beliebigen Zeitpunkt vor der Veröffentlichung der Topologie aktualisieren oder aus dem Pool entfernen. Wenn Sie den vollqualifizierten Domänennamen nach dem Veröffentlichen der Topologie ändern möchten, müssen Sie den Server im Topologie-Generator löschen und dem Pool anschließend einen neuen Server mit dem neuen vollqualifizierten Domänennamen hinzufügen. Ausführliche Informationen zum Hinzufügen eines Front-End-Pools zur Topologie finden Sie unter Definieren und Konfigurieren eines Front-End-Pools in der Bereitstellungsdokumentation.
ms.openlocfilehash: 69837016022f30453a287b6264936e20ec4883ca
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218316"
---
# <a name="add-front-end-machine"></a><span data-ttu-id="07b87-106">Hinzufügen von Front-End-Computern</span><span class="sxs-lookup"><span data-stu-id="07b87-106">Add Front End Machine</span></span>

<span data-ttu-id="07b87-107">Geben Sie den vollqualifizierten Domänennamen jedes Computers an, der diesem Pool als Front-End-Server hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="07b87-107">Specify the fully qualified domain name (FQDN) of each computer that you want to add as a Front End Server in this pool.</span></span> <span data-ttu-id="07b87-108">Nach dem Hinzufügen eines Computers zur Liste können Sie den vollqualifizierten Domänennamen des Computers zu einem beliebigen Zeitpunkt vor der Veröffentlichung der Topologie aktualisieren oder aus dem Pool entfernen.</span><span class="sxs-lookup"><span data-stu-id="07b87-108">After adding a computer to the list, you can update the FQDN of the computer or remove it from the pool at any time prior to publishing the topology.</span></span> <span data-ttu-id="07b87-109">Wenn Sie den vollqualifizierten Domänennamen nach dem Veröffentlichen der Topologie ändern möchten, müssen Sie den Server im Topologie-Generator löschen und dem Pool anschließend einen neuen Server mit dem neuen vollqualifizierten Domänennamen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="07b87-109">After you publish the topology, changing the FQDN requires deleting the server in Topology Builder and then adding a new server to the pool with the new FQDN.</span></span> <span data-ttu-id="07b87-110">Ausführliche Informationen zum Hinzufügen eines Front-End-Pools zur Topologie finden Sie unter [Definieren und Konfigurieren eines Front-End-Pools](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="07b87-110">For details about adding a Front End pool to the topology, see [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) in the Deployment documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="07b87-111">Beachten Sie, dass der Topologie-Generator angibt, dass Sie bis zu 20 Front-End-Server in einem Pool haben können.</span><span class="sxs-lookup"><span data-stu-id="07b87-111">Note that Topology Builder indicates that you can have up to 20 Front End Servers in a pool.</span></span> <span data-ttu-id="07b87-112">Die maximal unterstützte Anzahl von Servern ist 12.</span><span class="sxs-lookup"><span data-stu-id="07b87-112">The maximum supported number of servers is 12.</span></span> <span data-ttu-id="07b87-113">Im Fabric können bis zu 20 statefull-Server definiert sein, von denen 12 gleichzeitig aktiv sein und online sein können.</span><span class="sxs-lookup"><span data-stu-id="07b87-113">You can have up to 20 statefull servers defined in the fabric, of which 12 can be active and online at any one time.</span></span>


