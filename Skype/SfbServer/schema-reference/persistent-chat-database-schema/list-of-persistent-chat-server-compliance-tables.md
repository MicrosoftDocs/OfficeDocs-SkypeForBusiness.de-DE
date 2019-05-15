---
title: Liste der kompatibilitätstabellen für Persistent Chat Server in Skype für Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: Das beständigen Chat Compliance-Datenbankschema besteht aus den folgenden Tabellen.
ms.openlocfilehash: e17b2e52bdeb65ff4c77377cb913da212f20ecf0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929889"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a><span data-ttu-id="8a7a9-103">Liste der kompatibilitätstabellen für Persistent Chat Server in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="8a7a9-103">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>
 
<span data-ttu-id="8a7a9-104">Das beständigen Chat Compliance-Datenbankschema besteht aus den folgenden Tabellen.</span><span class="sxs-lookup"><span data-stu-id="8a7a9-104">The Persistent Chat compliance database schema consists of the following tables.</span></span>
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a><span data-ttu-id="8a7a9-105">Liste der Kompatibilitätstabellen für Persistent Chat Server</span><span class="sxs-lookup"><span data-stu-id="8a7a9-105">List of Persistent Chat Server Compliance Tables</span></span>

|<span data-ttu-id="8a7a9-106">**Tabelle**</span><span class="sxs-lookup"><span data-stu-id="8a7a9-106">**Table**</span></span>|<span data-ttu-id="8a7a9-107">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="8a7a9-107">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="8a7a9-108">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="8a7a9-108">tblComplianceData</span></span>](tblcompliancedata.md) <br/> |<span data-ttu-id="8a7a9-109">Enthält die genehmigungsereignisse, die noch nicht vom konfigurierten Adapter verarbeitet wurden.</span><span class="sxs-lookup"><span data-stu-id="8a7a9-109">Contains the compliance events that have not yet been processed by the configured adapter.</span></span>  <br/> <span data-ttu-id="8a7a9-110">Die folgende Tabelle enthält die Persistent Chat-bezogenen Ereignisse wie Chatnachrichten und Dateidownloads.</span><span class="sxs-lookup"><span data-stu-id="8a7a9-110">This table includes Persistent Chat-related events, such as chat messages and file downloads.</span></span> <span data-ttu-id="8a7a9-111">(Teilnehmer Ereignisse werden von der Tabelle TblComplianceParticipant nachverfolgt.)</span><span class="sxs-lookup"><span data-stu-id="8a7a9-111">(Participant events are tracked by the tblComplianceParticipant table.)</span></span>  <br/> <span data-ttu-id="8a7a9-112">(Die Server, die die Ereignisse in dieser Tabelle verarbeitet wurden, werden in der TblComplianceFanout-Tabelle aufgelistet.)</span><span class="sxs-lookup"><span data-stu-id="8a7a9-112">(The servers that processed the events in this table are listed in the tblComplianceFanout table.)</span></span>  <br/> |
|[<span data-ttu-id="8a7a9-113">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="8a7a9-113">tblComplianceFanout</span></span>](tblcompliancefanout.md) <br/> |<span data-ttu-id="8a7a9-114">Enthält die Server, die ein kompatibilitätsereignis verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="8a7a9-114">Contains the servers that processed a compliance event.</span></span> <span data-ttu-id="8a7a9-115">In dieser Tabelle ist eng mit der Tabelle "tblcompliancedata" gekoppelt.</span><span class="sxs-lookup"><span data-stu-id="8a7a9-115">This table is tightly coupled with the tblComplianceData table.</span></span>  <br/> |
|[<span data-ttu-id="8a7a9-116">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="8a7a9-116">tblComplianceParticipant</span></span>](tblcomplianceparticipant.md) <br/> |<span data-ttu-id="8a7a9-117">Enthält die aktuellen Teilnehmer pro Chatdienst und pro Server.</span><span class="sxs-lookup"><span data-stu-id="8a7a9-117">Contains current participants per chat service and per server.</span></span> <span data-ttu-id="8a7a9-118">Es wird beibehalten, basierend auf Verbindungs- und Teil Konformitätsereignisse von Persistent Chat-Dienst empfangen wurden.</span><span class="sxs-lookup"><span data-stu-id="8a7a9-118">It is maintained based on join and part compliance events received from the Persistent Chat service.</span></span>  <br/> |
|[<span data-ttu-id="8a7a9-119">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="8a7a9-119">tblComplianceState</span></span>](tblcompliancestate.md) <br/> |<span data-ttu-id="8a7a9-120">Enthält poolweite Informationen zum kompatibilitätszustand.</span><span class="sxs-lookup"><span data-stu-id="8a7a9-120">Contains pool-wide compliance state information.</span></span>  <br/> |
   

