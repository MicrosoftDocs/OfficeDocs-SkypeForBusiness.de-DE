---
title: Einstellungen für den Vermittlungsdienst – Erweiterung
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FeMediationServiceSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 142c1acd-cdaa-4922-8379-aa1bdf56a964
description: 'Für Vermittlungsserver können Sie Folgendes angeben:'
ms.openlocfilehash: e322b2ffd383c2bd0170852a6fec6c3122251700
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="mediation-service-settings-expander"></a><span data-ttu-id="e3c85-103">Einstellungen für den Vermittlungsdienst – Erweiterung</span><span class="sxs-lookup"><span data-stu-id="e3c85-103">Mediation Service Settings Expander</span></span>
 
<span data-ttu-id="e3c85-104">Für **Vermittlungsserver** können Sie Folgendes angeben:</span><span class="sxs-lookup"><span data-stu-id="e3c85-104">For **Mediation Server**, you can specify the following:</span></span>
  
<span data-ttu-id="e3c85-105">Wenn Sie den Vermittlungsserver auf den Front-End-Pool oder Standard Edition-Server kombinieren, aktivieren Sie das Kontrollkästchen **verbundener Vermittlungsserver aktiviert**.</span><span class="sxs-lookup"><span data-stu-id="e3c85-105">If you are collocating the Mediation Server onto the Front End pool or the Standard Edition server, select the check box **Collocated Mediation Server enabled**.</span></span> <span data-ttu-id="e3c85-106">Wenn Sie nicht, den der Vermittlungsserver zusammenzustellen auswählen, sind keine definierbaren Einstellungen in diesem Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="e3c85-106">If you choose not to collocate the Mediation Server, there are no definable settings in this section.</span></span> 
  
<span data-ttu-id="e3c85-107">Wenn Sie die gemeinsame Ausführung des Vermittlungsservers aktiviert haben, müssen Sie die überwachungsportbereich auf dem Server für Transport Layer Security (TLS) zu definieren.</span><span class="sxs-lookup"><span data-stu-id="e3c85-107">If you have enabled the collocation of the Mediation Server, you need to define the listening port range on the server for Transport Layer Security (TLS).</span></span> <span data-ttu-id="e3c85-108">Standardmäßig ist dieser Port 5067.</span><span class="sxs-lookup"><span data-stu-id="e3c85-108">By default, this port is 5067.</span></span> <span data-ttu-id="e3c85-109">Wenn Sie **Aktivieren TCP-Port**auswählen, müssen Sie einen Port (TCP = Transmission Control Protocol) für den verbundenen Vermittlungsserver definieren.</span><span class="sxs-lookup"><span data-stu-id="e3c85-109">If you select **Enable TCP port**, you must define a Transmission Control Protocol (TCP) port for the collocated Mediation Server.</span></span> <span data-ttu-id="e3c85-110">Dies ist eine optionale Einstellung, und verweisen Sie auf die Anforderungen Ihres Gateways oder öffentlichen Telefonnetz (PSTN) netzwerkanforderungen zu ermitteln, ob dies notwendig ist.</span><span class="sxs-lookup"><span data-stu-id="e3c85-110">This is an optional setting, and you should refer to the requirements of your gateway or public switched telephone network (PSTN) requirements to determine if you need this.</span></span> <span data-ttu-id="e3c85-111">Standardmäßig ist der Wert des TCP-Ports 5068.</span><span class="sxs-lookup"><span data-stu-id="e3c85-111">By default, the TCP port value is 5068.</span></span>
  
<span data-ttu-id="e3c85-112">Definieren Sie PSTN-Gateways, die dem verbundenen Vermittlungsserver zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="e3c85-112">You define PSTN gateways that are associated with the collocated Mediation Server.</span></span> <span data-ttu-id="e3c85-113">Wenn Sie bereits Gateways definiert haben, werden sie zur Verfügung, die der Vermittlungsserver zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="e3c85-113">If you have already defined gateways, they will be available to associate with the Mediation Server.</span></span> 
  
<span data-ttu-id="e3c85-114">Wenn Sie mehr als ein Gateway einen Vermittlungsserver zugeordnet haben, wird das erste Gateway verknüpften Standardgateway sein.</span><span class="sxs-lookup"><span data-stu-id="e3c85-114">If you have more than one gateway associated with a Mediation Server, the first gateway associated will be the default gateway.</span></span> <span data-ttu-id="e3c85-115">Falls Sie ein anderes Gateway als Standardgateway auswählen müssen, markieren Sie das gewünschte Gateway und klicken Sie auf **Als Standard**.</span><span class="sxs-lookup"><span data-stu-id="e3c85-115">If you need to choose another gateway as the default gateway, select the gateway that you want to make the default, and click **Make Default**.</span></span> <span data-ttu-id="e3c85-116">Klicken Sie auf **Festlegung als Standardeinstellung aufheben**, um die Festlegung als Standardeinstellung aufzuheben.</span><span class="sxs-lookup"><span data-stu-id="e3c85-116">To unselect the gateway as the default, click **Unmake Default**.</span></span>
  
<span data-ttu-id="e3c85-117">Ausführliche Informationen zum Definieren und Konfigurieren der Einstellungen für den Enterprise Edition-Front-End-Pool oder Standard Edition-Server finden Sie unter [Defining and Configuring the Topology](http://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) und [Deploying Mediation Servers and Defining Peers](http://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).</span><span class="sxs-lookup"><span data-stu-id="e3c85-117">For details about defining and configuring the settings for the Enterprise Edition Front End pool or Standard Edition server, see [Defining and Configuring the Topology](http://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) and [Deploying Mediation Servers and Defining Peers](http://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).</span></span>
  

