---
title: Einstellungen für den Vermittlungsdienst – Erweiterung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FeMediationServiceSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 142c1acd-cdaa-4922-8379-aa1bdf56a964
description: 'Für Vermittlungsserver können Sie Folgendes angeben:'
ms.openlocfilehash: 9a6da594452b4675b3eed1ca734fa3b54c9117b9
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215146"
---
# <a name="mediation-service-settings-expander"></a><span data-ttu-id="f598f-103">Einstellungen für den Vermittlungsdienst – Erweiterung</span><span class="sxs-lookup"><span data-stu-id="f598f-103">Mediation Service Settings Expander</span></span>

<span data-ttu-id="f598f-104">Für **Vermittlungsserver** können Sie Folgendes angeben:</span><span class="sxs-lookup"><span data-stu-id="f598f-104">For **Mediation Server**, you can specify the following:</span></span>

<span data-ttu-id="f598f-105">Wenn Sie das Vermittlungsserver auf dem Front-End-Pool oder dem Standard Edition-Server abstimmen, aktivieren Sie das Kontrollkästchen verbunden **Vermittlungsserver aktiviert**.</span><span class="sxs-lookup"><span data-stu-id="f598f-105">If you are collocating the Mediation Server onto the Front End pool or the Standard Edition server, select the check box **Collocated Mediation Server enabled**.</span></span> <span data-ttu-id="f598f-106">Wenn Sie die Vermittlungsserver nicht collocate, gibt es in diesem Abschnitt keine definierbaren Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="f598f-106">If you choose not to collocate the Mediation Server, there are no definable settings in this section.</span></span>

<span data-ttu-id="f598f-p102">Wenn Sie die gemeinsame Ausführung des Vermittlungsservers aktiviert haben, müssen Sie den Überwachungsportbereich des Servers für Transport Layer Security (TLS) festlegen. Standardmäßig lautet dieser Port 5067. Wenn Sie **TCP-Port aktivieren** aktivieren, müssen Sie für den verbundenen Vermittlungsserver einen TCP-Port (Transmission Control Protocol) angeben. Diese Einstellung ist optional. Überprüfen Sie die Gateway- bzw. PSTN-Anforderungen (Public Switched Telephone Network, Telefonfestnetz) dahingehend, ob diese Einstellung erforderlich ist. Standardmäßig ist der Wert des TCP-Ports auf 5068 festgelegt.</span><span class="sxs-lookup"><span data-stu-id="f598f-p102">If you have enabled the collocation of the Mediation Server, you need to define the listening port range on the server for Transport Layer Security (TLS). By default, this port is 5067. If you select **Enable TCP port**, you must define a Transmission Control Protocol (TCP) port for the collocated Mediation Server. This is an optional setting, and you should refer to the requirements of your gateway or public switched telephone network (PSTN) requirements to determine if you need this. By default, the TCP port value is 5068.</span></span>

<span data-ttu-id="f598f-p103">Sie definieren PSTN-Gateways, die dem verbundenen Vermittlungsserver zugeordnet sind. Wenn bereits Gateways definiert wurden, stehen sie für eine Zuordnung zum Vermittlungsserver zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="f598f-p103">You define PSTN gateways that are associated with the collocated Mediation Server. If you have already defined gateways, they will be available to associate with the Mediation Server.</span></span>

<span data-ttu-id="f598f-p104">Wenn einem Vermittlungsserver mehrere Gateways zugeordnet sind, ist das erste zugeordnete Gateway das Standardgateway. Falls Sie ein anderes Gateway als Standardgateway auswählen müssen, markieren Sie das gewünschte Gateway, und klicken Sie auf **Als Standard**. Klicken Sie auf **Festlegung als Standardeinstellung aufheben**, um die Festlegung als Standardeinstellung aufzuheben.</span><span class="sxs-lookup"><span data-stu-id="f598f-p104">If you have more than one gateway associated with a Mediation Server, the first gateway associated will be the default gateway. If you need to choose another gateway as the default gateway, select the gateway that you want to make the default, and click **Make Default**. To unselect the gateway as the default, click **Unmake Default**.</span></span>

<span data-ttu-id="f598f-117">Ausführliche Informationen zum Definieren und Konfigurieren der Einstellungen für die Enterprise Edition-Front-End-Pool oder-Standard Edition-Server finden Sie unter [definieren und Konfigurieren der Topologie](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) und [Bereitstellen von Vermittlungsservern und Definieren von Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).</span><span class="sxs-lookup"><span data-stu-id="f598f-117">For details about defining and configuring the settings for the Enterprise Edition Front End pool or Standard Edition server, see [Defining and Configuring the Topology](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) and [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).</span></span>


