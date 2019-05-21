---
title: Allgemeine Einstellungen des Vermittlungsservers – Erweiterung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MediationServerGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0e0ad9f0-27d5-4975-ae88-0b8ff8a4c514
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 5ce9c16fe44f26bf43a6fdd9a9850ed741efdaa0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299230"
---
# <a name="mediation-server-general-settings-expander"></a><span data-ttu-id="2e1d3-102">Allgemeine Einstellungen des Vermittlungsservers – Erweiterung</span><span class="sxs-lookup"><span data-stu-id="2e1d3-102">Mediation Server General Settings Expander</span></span>
 


## <a name="general-settings"></a><span data-ttu-id="2e1d3-103">Allgemeine Einstellungen</span><span class="sxs-lookup"><span data-stu-id="2e1d3-103">General settings</span></span>

<span data-ttu-id="2e1d3-104">Vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Vermittlungsserver Pools oder des Vermittlungsservers.</span><span class="sxs-lookup"><span data-stu-id="2e1d3-104">Fully qualified domain name (FQDN) of the Mediation Server pool or Mediation Server.</span></span> <span data-ttu-id="2e1d3-105">Bearbeiten Sie den FQDN des Servers, um den Wert zu ändern.</span><span class="sxs-lookup"><span data-stu-id="2e1d3-105">Edit the FQDN of the server to change the value.</span></span> <span data-ttu-id="2e1d3-106">Sie müssen über einen DNS-A-Eintrag (Domain Name System) verfügen, der mit dem neuen Wert übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="2e1d3-106">You must have a Domain Name System (DNS) host (A) record that coincides with the new value.</span></span>
  
<span data-ttu-id="2e1d3-107">Im Abschnitt **Zuordnungen** wählen Sie einen Edgeserver oder Edgeserver-Pool aus, der dem vermittlungsserverpool oder Vermittlungsserver zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="2e1d3-107">In the **Associations** section, you select an Edge Server or Edge Server pool to associate with the Mediation Server pool or Mediation Server.</span></span> <span data-ttu-id="2e1d3-108">Sie wählen den Edge aus, den die Medienkomponenten des Vermittlungsservers für externe Benutzer Enterprise-VoIP verwenden werden.</span><span class="sxs-lookup"><span data-stu-id="2e1d3-108">You select the Edge that the Mediation Server's media components will use for External user Enterprise Voice.</span></span>
  
<span data-ttu-id="2e1d3-109">Wenn Sie noch keinen Edgeserver definiert haben und den Vermittlungsserver einem Edgeserver zuordnen müssen, klicken Sie auf **neu** , und definieren Sie im Assistenten zum Definieren des neuen Edge-Pools den neuen Edge-Server oder den Edge-Serverpool.</span><span class="sxs-lookup"><span data-stu-id="2e1d3-109">If you do not have an Edge Server currently defined and need to associate the Mediation Server with an Edge Server, click **New** and define the new Edge Server or Edge Server pool in the Define the New Edge pool wizard.</span></span>
  
## <a name="next-hop-settings"></a><span data-ttu-id="2e1d3-110">Einstellungen für nächsten Hop</span><span class="sxs-lookup"><span data-stu-id="2e1d3-110">Next hop settings</span></span>

<span data-ttu-id="2e1d3-111">Sie geben den vermittlungsserverpool oder den Vermittlungsserver nächsten Hop an, indem Sie den definierten Enterprise Edition-Front-End-Pool oder den Standard Edition-Front-End-Server aus der Dropdownliste auswählen.</span><span class="sxs-lookup"><span data-stu-id="2e1d3-111">You specify the Mediation Server pool or Mediation Server next hop by selecting the defined Enterprise Edition Front End pool or Standard Edition Front End Server from the drop-down list.</span></span> <span data-ttu-id="2e1d3-112">Ein Director-oder Director-Pool ist keine gültige Auswahl für einen vermittlungsserverpool oder Vermittlungsserver nächster Hop und wird nicht in der Liste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2e1d3-112">A Director or Director pool is not a valid selection for a Mediation Server pool or Mediation Server next hop, and will not appear in the list.</span></span> <span data-ttu-id="2e1d3-113">Klicken Sie auf **OK** , um die Änderungen zu übernehmen und zu speichern.</span><span class="sxs-lookup"><span data-stu-id="2e1d3-113">Click **OK** to accept and save your changes.</span></span> <span data-ttu-id="2e1d3-114">Klicken Sie auf **Abbrechen**, um Ihre Änderungen zu verwerfen und die Eigenschaftenseite zu schließen.</span><span class="sxs-lookup"><span data-stu-id="2e1d3-114">Click **Cancel** to discard your changes and exit the properties page.</span></span>
  
## <a name="pstn-gateway-settings"></a><span data-ttu-id="2e1d3-115">Einstellungen für PSTN-Gateway</span><span class="sxs-lookup"><span data-stu-id="2e1d3-115">PSTN gateway settings</span></span>

1. <span data-ttu-id="2e1d3-116">Sie definieren PSTN-Gateways, die dem vermittlungsserverpool oder Vermittlungsserver zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="2e1d3-116">You define PSTN gateways that are associated with the Mediation Server pool or Mediation Server.</span></span> <span data-ttu-id="2e1d3-117">Wenn Sie bereits Gateways definiert haben, stehen diese dem Vermittlungs Server zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="2e1d3-117">If you have already defined gateways, they will be available to associate with the Mediation Server.</span></span> <span data-ttu-id="2e1d3-118">Wenn Sie die Zusammenlegung des Vermittlungsservers aktivieren, definieren Sie den Überwachungs Portbereich auf den Pool Servern für TLS (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="2e1d3-118">If you enable the collocation of the Mediation Server, define the listening port range on the pool servers for Transport Layer Security (TLS).</span></span> <span data-ttu-id="2e1d3-119">Standardmäßig ist dieser Port 5067.</span><span class="sxs-lookup"><span data-stu-id="2e1d3-119">By default, this port is 5067.</span></span> <span data-ttu-id="2e1d3-120">Wenn Sie **TCP-Port aktivieren**auswählen, müssen Sie einen TCP-Port (Transmission Control Protocol) für den beiliegenden Vermittlungs Server definieren.</span><span class="sxs-lookup"><span data-stu-id="2e1d3-120">If you select **Enable TCP port**, you must define a Transmission Control Protocol (TCP) port for the collocated Mediation Server.</span></span> <span data-ttu-id="2e1d3-121">Hierbei handelt es sich um eine optionale Einstellung, und Sie sollten sich auf die Anforderungen Ihrer Gateway-oder PSTN-Anforderungen beziehen, um festzustellen, ob dies erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="2e1d3-121">This is an optional setting, and you should refer to the requirements of your gateway or PSTN requirements to determine if you need this.</span></span> <span data-ttu-id="2e1d3-122">Standardmäßig ist der TCP-Port-Wert 5068.</span><span class="sxs-lookup"><span data-stu-id="2e1d3-122">By default, the TCP port value is 5068.</span></span>
    
2. <span data-ttu-id="2e1d3-p105">Trunks, die dem verbundenen Vermittlungsserver zugeordnet sind. Wenn bereits Trunks definiert wurden, stehen sie für eine Zuordnung zum Vermittlungsserver zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="2e1d3-p105">Trunks that are associated with the collocated Mediation Server. If you have already defined trunks, they will be available to associate with the Mediation Server.</span></span> 
    
3. <span data-ttu-id="2e1d3-125">Wenn einem Vermittlungs Server mehr als ein trunk zugeordnet ist, können Sie einen Standard trunk angeben, indem Sie den trunk auswählen und dann auf **Standard**festlegen klicken.</span><span class="sxs-lookup"><span data-stu-id="2e1d3-125">If you have more than one trunk associated with a Mediation Server, you can specify a default trunk by selecting the trunk and then clicking **Make Default**.</span></span> <span data-ttu-id="2e1d3-126">Klicken Sie auf **Festlegung als Standardeinstellung aufheben**, um die Festlegung eines Gateways als Standard aufzuheben.</span><span class="sxs-lookup"><span data-stu-id="2e1d3-126">To unselect a gateway as the default, click **Unmake Default**.</span></span> 
    

