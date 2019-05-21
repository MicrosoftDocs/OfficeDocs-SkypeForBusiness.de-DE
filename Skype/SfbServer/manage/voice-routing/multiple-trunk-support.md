---
title: Mehrere trunk-Unterstützung in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Die Skype for Business Server-Funktionalität unterstützt mehrere Zuordnungen zwischen Gateways und Vermittlungsservern. Diese Zuordnungen werden durch Definieren eines Trunks erstellt, bei dem es sich um eine logische Zuordnung zwischen einem Vermittlungs Server Pool und einem PSTN-Gateway (Public Switched Telephone Network), Sitzungs Grenz Controller (SBC) oder IP-PBX handelt. Verwenden Sie den Topologie-Generator, um Gateways mit Vermittlungsservern (also Trunks) zu verknüpfen.
ms.openlocfilehash: a6a0134ee04d939a10aaf9e36c81124d085af5aa
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274912"
---
# <a name="multiple-trunk-support-in-skype-for-business-server"></a><span data-ttu-id="3b2ec-105">Mehrere trunk-Unterstützung in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="3b2ec-105">Multiple trunk support in Skype for Business Server</span></span>

<span data-ttu-id="3b2ec-106">Die Skype for Business Server-Funktionalität unterstützt mehrere Zuordnungen zwischen Gateways und Vermittlungsservern.</span><span class="sxs-lookup"><span data-stu-id="3b2ec-106">Skype for Business Server functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="3b2ec-107">Diese Zuordnungen werden durch Definieren eines Trunks erstellt, bei dem es sich um eine logische Zuordnung zwischen einem Vermittlungs Server Pool und einem PSTN-Gateway (Public Switched Telephone Network), Sitzungs Grenz Controller (SBC) oder IP-PBX handelt.</span><span class="sxs-lookup"><span data-stu-id="3b2ec-107">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="3b2ec-108">Verwenden Sie den Topologie-Generator, um Gateways mit Vermittlungsservern (also Trunks) zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="3b2ec-108">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>

- <span data-ttu-id="3b2ec-109">Um einen trunk in Skype for Business Server zuzuweisen oder zu entfernen, müssen Sie zuerst einen trunk in Topology Builder definieren.</span><span class="sxs-lookup"><span data-stu-id="3b2ec-109">To assign or remove a trunk in Skype for Business Server, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="3b2ec-110">Ein trunk besteht aus der folgenden Zuordnung: vollständig qualifizierter Domänenname (Fully Qualified Domain Name, FQDN), Mediation Server-Abhör Port, Gateway-FQDN und Gateway-Abhör Port.</span><span class="sxs-lookup"><span data-stu-id="3b2ec-110">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>
- <span data-ttu-id="3b2ec-111">Zum Konfigurieren mehrerer Trunks können Sie mehrere Zuordnungen zwischen dem gleichen Gateway und dem Vermittlungs Server erstellen.</span><span class="sxs-lookup"><span data-stu-id="3b2ec-111">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="3b2ec-112">Dies bietet zusätzliche Widerstandsfähigkeit für die Enterprise-VoIP-Infrastruktur, die besonders in interoperational-Szenarien (Private Branch Exchange) verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="3b2ec-112">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span> 

<span data-ttu-id="3b2ec-113">Beim Definieren eines Trunks muss er einer Route zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="3b2ec-113">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="3b2ec-114">Um einen trunk einer Route zuzuordnen, definieren Sie einen einfachen Namen für den trunk im Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="3b2ec-114">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="3b2ec-115">Dieser einfache Name wird als trunk-Name in der Skype for Business Server-Systemsteuerung verwendet, in der Trunks mit Routen verknüpft werden können.</span><span class="sxs-lookup"><span data-stu-id="3b2ec-115">This simple name is used as the trunk name in the Skype for Business Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="3b2ec-116">Der einfache trunk-Name wird als Gateway-Name aus der Skype for Business Server-Verwaltungsshell verwendet.</span><span class="sxs-lookup"><span data-stu-id="3b2ec-116">The simple trunk name is used as the gateway name from the Skype for Business Server Management Shell.</span></span>

`New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}`

<span data-ttu-id="3b2ec-117">Der Administrator muss einen Standard trunk auswählen, der einem Vermittlungs Server zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="3b2ec-117">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="3b2ec-118">Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den zugehörigen Vermittlungs Server, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="3b2ec-118">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="3b2ec-119">Geben Sie das Standardgateway für den Vermittlungs Server an.</span><span class="sxs-lookup"><span data-stu-id="3b2ec-119">Specify the default gateway for the Mediation Server.</span></span> 

<span data-ttu-id="3b2ec-120">Das folgende Diagramm zeigt die verschiedenen Trunks, die für jeden Vermittlungs Server und jedes Gateway definiert sind.</span><span class="sxs-lookup"><span data-stu-id="3b2ec-120">The following diagram illustrates the multiple trunks that are defined for each Mediation Server and gateway.</span></span> 

![Mehrere trunk-Aufgaben](../../media/multiple-trunk-assignments.jpg)
