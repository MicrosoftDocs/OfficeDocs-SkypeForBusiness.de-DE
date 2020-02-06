---
title: Liste der beständigen Chat Server-Kompatibilitätstabellen in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: Das Compliance-Datenbankschema für beständige Chats besteht aus den folgenden Tabellen.
ms.openlocfilehash: a992f00718d831af1b5a30f08baaf779ea3ee2c1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814763"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a><span data-ttu-id="8493f-103">Liste der beständigen Chat Server-Kompatibilitätstabellen in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8493f-103">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>
 
<span data-ttu-id="8493f-104">Das Compliance-Datenbankschema für beständige Chats besteht aus den folgenden Tabellen.</span><span class="sxs-lookup"><span data-stu-id="8493f-104">The Persistent Chat compliance database schema consists of the following tables.</span></span>
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a><span data-ttu-id="8493f-105">Liste der Kompatibilitätstabellen für beständigen Chat Server</span><span class="sxs-lookup"><span data-stu-id="8493f-105">List of Persistent Chat Server Compliance Tables</span></span>

|<span data-ttu-id="8493f-106">**Tabelle**</span><span class="sxs-lookup"><span data-stu-id="8493f-106">**Table**</span></span>|<span data-ttu-id="8493f-107">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="8493f-107">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="8493f-108">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="8493f-108">tblComplianceData</span></span>](tblcompliancedata.md) <br/> |<span data-ttu-id="8493f-109">Enthält die Konformitätsereignisse, die vom konfigurierten Adapter noch nicht verarbeitet wurden.</span><span class="sxs-lookup"><span data-stu-id="8493f-109">Contains the compliance events that have not yet been processed by the configured adapter.</span></span>  <br/> <span data-ttu-id="8493f-110">Diese Tabelle enthält dauerhafte Chat bezogene Ereignisse wie Chatnachrichten und Dateidownloads.</span><span class="sxs-lookup"><span data-stu-id="8493f-110">This table includes Persistent Chat-related events, such as chat messages and file downloads.</span></span> <span data-ttu-id="8493f-111">(Teilnehmer-Ereignisse werden von der tblComplianceParticipant-Tabelle nachverfolgt.)</span><span class="sxs-lookup"><span data-stu-id="8493f-111">(Participant events are tracked by the tblComplianceParticipant table.)</span></span>  <br/> <span data-ttu-id="8493f-112">(Die Server, die die Ereignisse in dieser Tabelle verarbeitet haben, werden in der tblComplianceFanout-Tabelle aufgelistet.)</span><span class="sxs-lookup"><span data-stu-id="8493f-112">(The servers that processed the events in this table are listed in the tblComplianceFanout table.)</span></span>  <br/> |
|[<span data-ttu-id="8493f-113">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="8493f-113">tblComplianceFanout</span></span>](tblcompliancefanout.md) <br/> |<span data-ttu-id="8493f-114">Enthält die Server, die ein Compliance-Ereignis verarbeitet haben.</span><span class="sxs-lookup"><span data-stu-id="8493f-114">Contains the servers that processed a compliance event.</span></span> <span data-ttu-id="8493f-115">Diese Tabelle ist eng mit der tblComplianceData-Tabelle gekoppelt.</span><span class="sxs-lookup"><span data-stu-id="8493f-115">This table is tightly coupled with the tblComplianceData table.</span></span>  <br/> |
|[<span data-ttu-id="8493f-116">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="8493f-116">tblComplianceParticipant</span></span>](tblcomplianceparticipant.md) <br/> |<span data-ttu-id="8493f-117">Enthält aktuelle Teilnehmer pro Chatdienst und pro Server.</span><span class="sxs-lookup"><span data-stu-id="8493f-117">Contains current participants per chat service and per server.</span></span> <span data-ttu-id="8493f-118">Sie wird auf der Grundlage von Join-und Part-Konformitäts Ereignissen verwaltet, die vom beständigen Chat Dienst empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="8493f-118">It is maintained based on join and part compliance events received from the Persistent Chat service.</span></span>  <br/> |
|[<span data-ttu-id="8493f-119">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="8493f-119">tblComplianceState</span></span>](tblcompliancestate.md) <br/> |<span data-ttu-id="8493f-120">Enthält Informationen zum Kompatibilitätszustand des Pools.</span><span class="sxs-lookup"><span data-stu-id="8493f-120">Contains pool-wide compliance state information.</span></span>  <br/> |
   

