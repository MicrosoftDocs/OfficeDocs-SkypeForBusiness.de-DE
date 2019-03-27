---
title: Unterstützung mehrerer Trunks in Skype für Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype-Funktionen, Business Server unterstützt mehrere Zuordnungen zwischen Gateways und Vermittlungsservern. Diese Zuordnungen werden geändert, indem ein Trunk eine logische Zuordnung zwischen einem vermittlungsserverpool und einem Gateway public switched Telephone Network (Telefonfestnetz PSTN), Session Border Controller (SBC) oder IP-PBX ist zu definieren. Verwenden Sie den Topologie-Generator Vermittlungsserver (d. h., Trunks) Gateways zugeordnet.
ms.openlocfilehash: 5d093bee56597474f0cefcf1053536774f2eb795
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30896567"
---
# <a name="multiple-trunk-support-in-skype-for-business-server"></a><span data-ttu-id="1dcac-105">Unterstützung mehrerer Trunks in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="1dcac-105">Multiple trunk support in Skype for Business Server</span></span>

<span data-ttu-id="1dcac-106">Skype-Funktionen, Business Server unterstützt mehrere Zuordnungen zwischen Gateways und Vermittlungsservern.</span><span class="sxs-lookup"><span data-stu-id="1dcac-106">Skype for Business Server functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="1dcac-107">Diese Zuordnungen werden geändert, indem ein Trunk eine logische Zuordnung zwischen einem vermittlungsserverpool und einem Gateway public switched Telephone Network (Telefonfestnetz PSTN), Session Border Controller (SBC) oder IP-PBX ist zu definieren.</span><span class="sxs-lookup"><span data-stu-id="1dcac-107">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="1dcac-108">Verwenden Sie den Topologie-Generator Vermittlungsserver (d. h., Trunks) Gateways zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="1dcac-108">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>

- <span data-ttu-id="1dcac-109">Zum Zuweisen oder Entfernen eines Trunks in Skype für Business Server, müssen Sie zuerst einen Trunk im Topologie-Generator definieren.</span><span class="sxs-lookup"><span data-stu-id="1dcac-109">To assign or remove a trunk in Skype for Business Server, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="1dcac-110">Ein Trunk umfasst die folgenden Zuordnung: Vermittlungsserver vollqualifizierter Domänenname (FQDN), den Vermittlungsserver Überwachungsport, FQDN des Gateways und den Überwachungsport des Gateways.</span><span class="sxs-lookup"><span data-stu-id="1dcac-110">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>
- <span data-ttu-id="1dcac-111">Um mehrere Trunks zu konfigurieren, können Sie mehrere Zuordnungen zwischen dem gleichen Gateway und dem Vermittlungsserver erstellen.</span><span class="sxs-lookup"><span data-stu-id="1dcac-111">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="1dcac-112">Dadurch wird die zusätzliche Flexibilität mit der Enterprise-VoIP-Infrastruktur in private Branch Exchange, (Nebenstellenanlage PBX) interoperational Szenarien besonders nützlich ist.</span><span class="sxs-lookup"><span data-stu-id="1dcac-112">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span> 

<span data-ttu-id="1dcac-113">Beim Definieren eines Trunks muss er einer Route zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="1dcac-113">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="1dcac-114">Um einen Trunk einer Route zuzuordnen, definieren Sie einen einfachen Namen für die Trunks im Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="1dcac-114">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="1dcac-115">Diese einfache Name wird als den trunknamen in der Skype Business Server-Systemsteuerung verwendet, in dem Trunks Routen zugeordnet werden kann.</span><span class="sxs-lookup"><span data-stu-id="1dcac-115">This simple name is used as the trunk name in the Skype for Business Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="1dcac-116">Der einfachen trunknamen dient als Gateway-Namen aus der Skype für Business Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="1dcac-116">The simple trunk name is used as the gateway name from the Skype for Business Server Management Shell.</span></span>

`New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}`

<span data-ttu-id="1dcac-117">Der Administrator muss einen Standard-Trunk zugeordnet eines Vermittlungsservers auswählen.</span><span class="sxs-lookup"><span data-stu-id="1dcac-117">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="1dcac-118">Topologie-Generator mit der rechten Maustaste zugeordneter Vermittlungsserver, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="1dcac-118">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="1dcac-119">Geben Sie den Standard-Gateway für den Vermittlungsserver.</span><span class="sxs-lookup"><span data-stu-id="1dcac-119">Specify the default gateway for the Mediation Server.</span></span> 

<span data-ttu-id="1dcac-120">Das folgende Diagramm veranschaulicht die mehrere Trunks, die für jeden Vermittlungsserver und dem Gateway definiert sind.</span><span class="sxs-lookup"><span data-stu-id="1dcac-120">The following diagram illustrates the multiple trunks that are defined for each Mediation Server and gateway.</span></span> 

![Mehrere Trunk-Zuordnungen](../../media/multiple-trunk-assignments.jpg)
