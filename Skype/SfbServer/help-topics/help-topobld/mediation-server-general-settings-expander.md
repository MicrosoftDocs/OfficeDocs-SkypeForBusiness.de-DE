---
title: Allgemeine Einstellungen des Vermittlungsservers – Erweiterung
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 4/14/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MediationServerGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0e0ad9f0-27d5-4975-ae88-0b8ff8a4c514
ms.openlocfilehash: ecb8a924bc72dd8220ab5d40481418cbec78737a
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20969852"
---
# <a name="mediation-server-general-settings-expander"></a><span data-ttu-id="80f08-102">Allgemeine Einstellungen des Vermittlungsservers – Erweiterung</span><span class="sxs-lookup"><span data-stu-id="80f08-102">Mediation Server General Settings Expander</span></span>
 


## <a name="general-settings"></a><span data-ttu-id="80f08-103">Allgemeine Einstellungen</span><span class="sxs-lookup"><span data-stu-id="80f08-103">General settings</span></span>

<span data-ttu-id="80f08-104">Vollqualifizierter Domänenname (FQDN) des vermittlungsserverpool oder Vermittlungsserver.</span><span class="sxs-lookup"><span data-stu-id="80f08-104">Fully qualified domain name (FQDN) of the Mediation Server pool or Mediation Server.</span></span> <span data-ttu-id="80f08-105">Bearbeiten Sie den FQDN des Servers, um den Wert zu ändern.</span><span class="sxs-lookup"><span data-stu-id="80f08-105">Edit the FQDN of the server to change the value.</span></span> <span data-ttu-id="80f08-106">Sie müssen über einen DNS-A-Eintrag (Domain Name System) verfügen, der mit dem neuen Wert übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="80f08-106">You must have a Domain Name System (DNS) host (A) record that coincides with the new value.</span></span>
  
<span data-ttu-id="80f08-107">Klicken Sie im Abschnitt **Zuordnungen** wählen Sie ein Edge-Server oder Pool für Edge-Server den vermittlungsserverpool oder Vermittlungsserver zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="80f08-107">In the **Associations** section, you select an Edge Server or Edge Server pool to associate with the Mediation Server pool or Mediation Server.</span></span> <span data-ttu-id="80f08-108">Sie wählen Sie die Kante, die der Vermittlungsserver Media-Komponenten für externe Benutzer Enterprise-VoIP verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="80f08-108">You select the Edge that the Mediation Server's media components will use for External user Enterprise Voice.</span></span>
  
<span data-ttu-id="80f08-109">Wenn Sie keine definiert einen Edge-Server zurzeit und Zuordnen des Vermittlungsservers mit einem Edge-Server, klicken Sie auf **neu** , und definieren den neuen Edge-Server oder Edge-Server-Pool definieren des Assistenten zum neuen Edge-Pools müssen.</span><span class="sxs-lookup"><span data-stu-id="80f08-109">If you do not have an Edge Server currently defined and need to associate the Mediation Server with an Edge Server, click **New** and define the new Edge Server or Edge Server pool in the Define the New Edge pool wizard.</span></span>
  
## <a name="next-hop-settings"></a><span data-ttu-id="80f08-110">Einstellungen für nächsten Hop</span><span class="sxs-lookup"><span data-stu-id="80f08-110">Next hop settings</span></span>

<span data-ttu-id="80f08-111">Sie geben Sie den vermittlungsserverpool oder Vermittlungsserver Nächster Hop, indem Sie den definierten Enterprise Edition-Front-End-Pool oder Standard Edition-Front-End-Server aus der Dropdown-Liste auswählen.</span><span class="sxs-lookup"><span data-stu-id="80f08-111">You specify the Mediation Server pool or Mediation Server next hop by selecting the defined Enterprise Edition Front End pool or Standard Edition Front End Server from the drop-down list.</span></span> <span data-ttu-id="80f08-112">Ein Director oder Director Pool ist keine gültige Auswahl für einen vermittlungsserverpool oder Vermittlungsserver Nächster Hop und nicht in der Liste angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="80f08-112">A Director or Director pool is not a valid selection for a Mediation Server pool or Mediation Server next hop, and will not appear in the list.</span></span> <span data-ttu-id="80f08-113">Klicken Sie auf **OK** , um zu akzeptieren und Ihre Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="80f08-113">Click **OK** to accept and save your changes.</span></span> <span data-ttu-id="80f08-114">Klicken Sie auf **Abbrechen**, um Ihre Änderungen zu verwerfen und die Eigenschaftenseite zu schließen.</span><span class="sxs-lookup"><span data-stu-id="80f08-114">Click **Cancel** to discard your changes and exit the properties page.</span></span>
  
## <a name="pstn-gateway-settings"></a><span data-ttu-id="80f08-115">Einstellungen für PSTN-Gateway</span><span class="sxs-lookup"><span data-stu-id="80f08-115">PSTN gateway settings</span></span>

1. <span data-ttu-id="80f08-116">Definieren Sie PSTN-Gateways, die den vermittlungsserverpool oder Vermittlungsserver zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="80f08-116">You define PSTN gateways that are associated with the Mediation Server pool or Mediation Server.</span></span> <span data-ttu-id="80f08-117">Wenn Sie bereits Gateways definiert haben, werden sie zur Verfügung, die der Vermittlungsserver zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="80f08-117">If you have already defined gateways, they will be available to associate with the Mediation Server.</span></span> <span data-ttu-id="80f08-118">Wenn Sie die gemeinsame Ausführung des Vermittlungsservers aktivieren, definieren Sie die überwachungsportbereich auf den Pool-Servern für Transport Layer Security (TLS).</span><span class="sxs-lookup"><span data-stu-id="80f08-118">If you enable the collocation of the Mediation Server, define the listening port range on the pool servers for Transport Layer Security (TLS).</span></span> <span data-ttu-id="80f08-119">Standardmäßig ist dieser Port 5067.</span><span class="sxs-lookup"><span data-stu-id="80f08-119">By default, this port is 5067.</span></span> <span data-ttu-id="80f08-120">Wenn Sie **Aktivieren TCP-Port**auswählen, müssen Sie einen Port (TCP = Transmission Control Protocol) für den verbundenen Vermittlungsserver definieren.</span><span class="sxs-lookup"><span data-stu-id="80f08-120">If you select **Enable TCP port**, you must define a Transmission Control Protocol (TCP) port for the collocated Mediation Server.</span></span> <span data-ttu-id="80f08-121">Dies ist eine optionale Einstellung, und verweisen Sie auf die Anforderungen Ihres Gateways oder PSTN-Anforderungen zu ermitteln, ob dies notwendig ist.</span><span class="sxs-lookup"><span data-stu-id="80f08-121">This is an optional setting, and you should refer to the requirements of your gateway or PSTN requirements to determine if you need this.</span></span> <span data-ttu-id="80f08-122">Standardmäßig ist der Wert des TCP-Ports 5068.</span><span class="sxs-lookup"><span data-stu-id="80f08-122">By default, the TCP port value is 5068.</span></span>
    
2. <span data-ttu-id="80f08-p105">Trunks, die dem verbundenen Vermittlungsserver zugeordnet sind. Wenn bereits Trunks definiert wurden, stehen sie für eine Zuordnung zum Vermittlungsserver zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="80f08-p105">Trunks that are associated with the collocated Mediation Server. If you have already defined trunks, they will be available to associate with the Mediation Server.</span></span> 
    
3. <span data-ttu-id="80f08-125">Wenn Sie mehrere Trunks einen Vermittlungsserver zugeordnet haben, können Sie einen Standard-Trunk angeben, indem dem Trunk auswählen und dann auf **Als Standard**.</span><span class="sxs-lookup"><span data-stu-id="80f08-125">If you have more than one trunk associated with a Mediation Server, you can specify a default trunk by selecting the trunk and then clicking **Make Default**.</span></span> <span data-ttu-id="80f08-126">Klicken Sie auf **Festlegung als Standardeinstellung aufheben**, um die Festlegung eines Gateways als Standard aufzuheben.</span><span class="sxs-lookup"><span data-stu-id="80f08-126">To unselect a gateway as the default, click **Unmake Default**.</span></span> 
    

