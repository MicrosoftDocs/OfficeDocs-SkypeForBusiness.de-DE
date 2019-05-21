---
title: Einstellungen für den Vermittlungsdienst – Erweiterung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FeMediationServiceSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 142c1acd-cdaa-4922-8379-aa1bdf56a964
description: 'Für Vermittlungsserver können Sie Folgendes angeben:'
ms.openlocfilehash: fcff87faeb5911d12806f80499c2b2f0d63caff3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34285603"
---
# <a name="mediation-service-settings-expander"></a><span data-ttu-id="7fa17-103">Einstellungen für den Vermittlungsdienst – Erweiterung</span><span class="sxs-lookup"><span data-stu-id="7fa17-103">Mediation Service Settings Expander</span></span>

<span data-ttu-id="7fa17-104">Für **Vermittlungsserver** können Sie Folgendes angeben:</span><span class="sxs-lookup"><span data-stu-id="7fa17-104">For **Mediation Server**, you can specify the following:</span></span>

<span data-ttu-id="7fa17-105">Wenn Sie den Vermittlungsserver auf dem Front-End-Pool oder auf dem Standard Edition-Server abstimmen, aktivieren Sie das Kontrollkästchen für den **Mediationsserver aktiviert**.</span><span class="sxs-lookup"><span data-stu-id="7fa17-105">If you are collocating the Mediation Server onto the Front End pool or the Standard Edition server, select the check box **Collocated Mediation Server enabled**.</span></span> <span data-ttu-id="7fa17-106">Wenn Sie den Vermittlungs Server nicht collocate möchten, gibt es in diesem Abschnitt keine definierbaren Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="7fa17-106">If you choose not to collocate the Mediation Server, there are no definable settings in this section.</span></span>

<span data-ttu-id="7fa17-107">Wenn Sie die Übertragung des Vermittlungsservers aktiviert haben, müssen Sie den Überwachungs Portbereich auf dem Server für TLS (Transport Layer Security) definieren.</span><span class="sxs-lookup"><span data-stu-id="7fa17-107">If you have enabled the collocation of the Mediation Server, you need to define the listening port range on the server for Transport Layer Security (TLS).</span></span> <span data-ttu-id="7fa17-108">Standardmäßig ist dieser Port 5067.</span><span class="sxs-lookup"><span data-stu-id="7fa17-108">By default, this port is 5067.</span></span> <span data-ttu-id="7fa17-109">Wenn Sie **TCP-Port aktivieren**auswählen, müssen Sie einen TCP-Port (Transmission Control Protocol) für den beiliegenden Vermittlungs Server definieren.</span><span class="sxs-lookup"><span data-stu-id="7fa17-109">If you select **Enable TCP port**, you must define a Transmission Control Protocol (TCP) port for the collocated Mediation Server.</span></span> <span data-ttu-id="7fa17-110">Hierbei handelt es sich um eine optionale Einstellung, auf die Sie sich beziehen sollten, um festzustellen, ob dies erforderlich ist, wenn Sie sich auf die Anforderungen Ihres Gateways oder der PSTN-Anforderungen (Public Switched Telephone Network) beziehen</span><span class="sxs-lookup"><span data-stu-id="7fa17-110">This is an optional setting, and you should refer to the requirements of your gateway or public switched telephone network (PSTN) requirements to determine if you need this.</span></span> <span data-ttu-id="7fa17-111">Standardmäßig ist der TCP-Port-Wert 5068.</span><span class="sxs-lookup"><span data-stu-id="7fa17-111">By default, the TCP port value is 5068.</span></span>

<span data-ttu-id="7fa17-112">Sie definieren PSTN-Gateways, die dem zusammengefassten Vermittlungs Server zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="7fa17-112">You define PSTN gateways that are associated with the collocated Mediation Server.</span></span> <span data-ttu-id="7fa17-113">Wenn Sie bereits Gateways definiert haben, stehen diese dem Vermittlungs Server zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="7fa17-113">If you have already defined gateways, they will be available to associate with the Mediation Server.</span></span>

<span data-ttu-id="7fa17-114">Wenn einem Vermittlungs Server mehr als ein Gateway zugeordnet ist, ist das erste zugeordnete Gateway das Standardgateway.</span><span class="sxs-lookup"><span data-stu-id="7fa17-114">If you have more than one gateway associated with a Mediation Server, the first gateway associated will be the default gateway.</span></span> <span data-ttu-id="7fa17-115">Falls Sie ein anderes Gateway als Standardgateway auswählen müssen, markieren Sie das gewünschte Gateway und klicken Sie auf **Als Standard**.</span><span class="sxs-lookup"><span data-stu-id="7fa17-115">If you need to choose another gateway as the default gateway, select the gateway that you want to make the default, and click **Make Default**.</span></span> <span data-ttu-id="7fa17-116">Klicken Sie auf **Festlegung als Standardeinstellung aufheben**, um die Festlegung als Standardeinstellung aufzuheben.</span><span class="sxs-lookup"><span data-stu-id="7fa17-116">To unselect the gateway as the default, click **Unmake Default**.</span></span>

<span data-ttu-id="7fa17-117">Details zum Definieren und Konfigurieren der Einstellungen für den Enterprise Edition-Front-End-Pool oder Standard Edition-Server finden Sie unter [definieren und Konfigurieren der Topologie](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) und [Bereitstellen von Vermittlungsservern und definieren](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx)von Peers.</span><span class="sxs-lookup"><span data-stu-id="7fa17-117">For details about defining and configuring the settings for the Enterprise Edition Front End pool or Standard Edition server, see [Defining and Configuring the Topology](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) and [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).</span></span>


