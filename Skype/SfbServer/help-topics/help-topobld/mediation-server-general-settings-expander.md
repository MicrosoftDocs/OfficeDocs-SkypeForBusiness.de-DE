---
title: Allgemeine Einstellungen des Vermittlungsservers – Erweiterung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/14/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.MediationServerGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0e0ad9f0-27d5-4975-ae88-0b8ff8a4c514
ms.openlocfilehash: bd3047832b23604f87a1e298a42798b13bb6822a
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215166"
---
# <a name="mediation-server-general-settings-expander"></a><span data-ttu-id="f7da4-102">Allgemeine Einstellungen des Vermittlungsservers – Erweiterung</span><span class="sxs-lookup"><span data-stu-id="f7da4-102">Mediation Server General Settings Expander</span></span>
 


## <a name="general-settings"></a><span data-ttu-id="f7da4-103">Allgemeine Einstellungen</span><span class="sxs-lookup"><span data-stu-id="f7da4-103">General settings</span></span>

<span data-ttu-id="f7da4-p101">Vollqualifizierter Domänenname (FQDN) des Vermittlungsserverpools oder Vermittlungsservers. Bearbeiten Sie den FQDN des Servers, um den Wert zu ändern. Sie müssen über einen DNS-A-Eintrag (Domain Name System) verfügen, der mit dem neuen Wert übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="f7da4-p101">Fully qualified domain name (FQDN) of the Mediation Server pool or Mediation Server. Edit the FQDN of the server to change the value. You must have a Domain Name System (DNS) host (A) record that coincides with the new value.</span></span>
  
<span data-ttu-id="f7da4-107">Im Abschnitt **Zuordnungen** wählen Sie einen Edgeserver oder Edgeserverpool aus, der dem Vermittlungsserverpool oder Vermittlungsserver zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="f7da4-107">In the **Associations** section, you select an Edge Server or Edge Server pool to associate with the Mediation Server pool or Mediation Server.</span></span> <span data-ttu-id="f7da4-108">Sie wählen die Kante aus, die von den Medienkomponenten des Vermittlungsserver für externe Benutzer Enterprise-VoIP verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f7da4-108">You select the Edge that the Mediation Server's media components will use for External user Enterprise Voice.</span></span>
  
<span data-ttu-id="f7da4-109">Wenn gegenwärtig kein Edgeserver definiert ist und der Vermittlungsserver einem Edgeserver zugeordnet werden muss, klicken Sie auf **Neu**, und definieren Sie den neuen Edgeserver oder Edgeserverpool im Assistenten zum Definieren des neuen Edgeserverpools.</span><span class="sxs-lookup"><span data-stu-id="f7da4-109">If you do not have an Edge Server currently defined and need to associate the Mediation Server with an Edge Server, click **New** and define the new Edge Server or Edge Server pool in the Define the New Edge pool wizard.</span></span>
  
## <a name="next-hop-settings"></a><span data-ttu-id="f7da4-110">Einstellungen für nächsten Hop</span><span class="sxs-lookup"><span data-stu-id="f7da4-110">Next hop settings</span></span>

<span data-ttu-id="f7da4-111">Zum Angeben des nächsten Hops eines Vermittlungsserverpools oder Vermittlungsservers wählen Sie den definierten Front-End-Pool der Enterprise Edition oder den Front-End-Server der Standard Edition aus der Dropdownliste aus.</span><span class="sxs-lookup"><span data-stu-id="f7da4-111">You specify the Mediation Server pool or Mediation Server next hop by selecting the defined Enterprise Edition Front End pool or Standard Edition Front End Server from the drop-down list.</span></span> <span data-ttu-id="f7da4-112">Ein Director oder Director-Pool kann nicht als nächster Hop für einen Vermittlungsserverpool oder Vermittlungsserver ausgewählt werden und wird daher nicht in der Liste aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="f7da4-112">A Director or Director pool is not a valid selection for a Mediation Server pool or Mediation Server next hop, and will not appear in the list.</span></span> <span data-ttu-id="f7da4-113">Klicken Sie auf **OK** , um die Änderungen zu akzeptieren und zu speichern.</span><span class="sxs-lookup"><span data-stu-id="f7da4-113">Click **OK** to accept and save your changes.</span></span> <span data-ttu-id="f7da4-114">Klicken Sie auf **Abbrechen**, um Ihre Änderungen zu verwerfen und die Eigenschaftenseite zu schließen.</span><span class="sxs-lookup"><span data-stu-id="f7da4-114">Click **Cancel** to discard your changes and exit the properties page.</span></span>
  
## <a name="pstn-gateway-settings"></a><span data-ttu-id="f7da4-115">Einstellungen für PSTN-Gateway</span><span class="sxs-lookup"><span data-stu-id="f7da4-115">PSTN gateway settings</span></span>

1. <span data-ttu-id="f7da4-p104">Sie definieren PSTN-Gateways, die dem Vermittlungsserverpool oder Vermittlungsserver zugeordnet werden. Wenn bereits Gateways definiert wurden, stehen sie für eine Zuordnung zum Vermittlungsserver zur Verfügung. Wenn Sie die Kollokation des Vermittlungsservers aktivieren, müssen Sie den Überwachungsport der Poolserver für Transport Layer Security (TLS) festlegen. Standardmäßig lautet dieser Port 5067. Wenn Sie **TCP-Port aktivieren** aktivieren, müssen Sie für den verbundenen Vermittlungsserver einen TCP-Port (Transmission Control Protocol) angeben. Diese Einstellung ist optional. Überprüfen Sie die Gateway- bzw. PSTN-Anforderungen dahingehend, ob diese Einstellung erforderlich ist. Standardmäßig ist der Wert des TCP-Ports auf 5068 festgelegt.</span><span class="sxs-lookup"><span data-stu-id="f7da4-p104">You define PSTN gateways that are associated with the Mediation Server pool or Mediation Server. If you have already defined gateways, they will be available to associate with the Mediation Server. If you enable the collocation of the Mediation Server, define the listening port range on the pool servers for Transport Layer Security (TLS). By default, this port is 5067. If you select **Enable TCP port**, you must define a Transmission Control Protocol (TCP) port for the collocated Mediation Server. This is an optional setting, and you should refer to the requirements of your gateway or PSTN requirements to determine if you need this. By default, the TCP port value is 5068.</span></span>
    
2. <span data-ttu-id="f7da4-p105">Trunks, die dem verbundenen Vermittlungsserver zugeordnet sind. Wenn bereits Trunks definiert wurden, stehen sie für eine Zuordnung zum Vermittlungsserver zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="f7da4-p105">Trunks that are associated with the collocated Mediation Server. If you have already defined trunks, they will be available to associate with the Mediation Server.</span></span> 
    
3. <span data-ttu-id="f7da4-p106">Falls einem Vermittlungsserver mehr als ein Trunk zugeordnet ist, können Sie einen Trunk als Standard angeben, indem Sie den Trunk auswählen und auf **Als Standardeinstellung festlegen** klicken. Klicken Sie auf **Festlegung als Standardeinstellung aufheben**, um die Festlegung als Standardeinstellung aufzuheben.</span><span class="sxs-lookup"><span data-stu-id="f7da4-p106">If you have more than one trunk associated with a Mediation Server, you can specify a default trunk by selecting the trunk and then clicking **Make Default**. To unselect a gateway as the default, click **Unmake Default**.</span></span> 
    

