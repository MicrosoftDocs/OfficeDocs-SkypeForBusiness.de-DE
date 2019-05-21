---
title: Tabelle "Tabelle" in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: Die Tabelle "MCU" ist eine unterstützende Tabelle. In jedem Datensatz werden Informationen zu einem Konferenzdienst gespeichert. Dazu gehören der Chat-Konferenzdienst und der Telefonie-Konferenzdienst (der als Prozesse auf Front-End-Servern ausgeführt wird) sowie der Webkonferenzdienst und ein/V-Konferenzdienst.
ms.openlocfilehash: fcd12bcc8da7aa6513d78e1a9c4a6f11930065aa
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296042"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a><span data-ttu-id="096a4-105">Tabelle "Tabelle" in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="096a4-105">Mcus table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="096a4-106">Die Tabelle "MCU" ist eine unterstützende Tabelle.</span><span class="sxs-lookup"><span data-stu-id="096a4-106">The Mcus table is a supporting table.</span></span> <span data-ttu-id="096a4-107">In jedem Datensatz werden Informationen zu einem Konferenzdienst gespeichert.</span><span class="sxs-lookup"><span data-stu-id="096a4-107">Each record stores information about one conferencing service.</span></span> <span data-ttu-id="096a4-108">Dazu gehören der Chat-Konferenzdienst und der Telefonie-Konferenzdienst (der als Prozesse auf Front-End-Servern ausgeführt wird) sowie der Webkonferenzdienst und ein/V-Konferenzdienst.</span><span class="sxs-lookup"><span data-stu-id="096a4-108">These can include the IM Conferencing service and the Telephony Conferencing service (which run as processes on front-end servers), and the Web Conferencing service and A/V Conferencing service.</span></span> 
  
|<span data-ttu-id="096a4-109">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="096a4-109">**Column**</span></span>|<span data-ttu-id="096a4-110">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="096a4-110">**Data Type**</span></span>|<span data-ttu-id="096a4-111">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="096a4-111">**Key/Index**</span></span>|<span data-ttu-id="096a4-112">**Details**</span><span class="sxs-lookup"><span data-stu-id="096a4-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="096a4-113">**McuId**</span><span class="sxs-lookup"><span data-stu-id="096a4-113">**McuId**</span></span> <br/> |<span data-ttu-id="096a4-114">int</span><span class="sxs-lookup"><span data-stu-id="096a4-114">int</span></span>  <br/> |<span data-ttu-id="096a4-115">Primary</span><span class="sxs-lookup"><span data-stu-id="096a4-115">Primary</span></span>  <br/> |<span data-ttu-id="096a4-116">Eindeutige Nummer, die diesen Konferenzserver identifiziert.</span><span class="sxs-lookup"><span data-stu-id="096a4-116">Unique number identifying this conferencing server.</span></span>  <br/> |
|<span data-ttu-id="096a4-117">**McuUri**</span><span class="sxs-lookup"><span data-stu-id="096a4-117">**McuUri**</span></span> <br/> |<span data-ttu-id="096a4-118">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="096a4-118">nvarchar(450)</span></span>  <br/> | <br/> | <br/> |
|<span data-ttu-id="096a4-119">**McuTypeId**</span><span class="sxs-lookup"><span data-stu-id="096a4-119">**McuTypeId**</span></span> <br/> |<span data-ttu-id="096a4-120">inyint</span><span class="sxs-lookup"><span data-stu-id="096a4-120">inyint</span></span>  <br/> | <span data-ttu-id="096a4-121">Fremd</span><span class="sxs-lookup"><span data-stu-id="096a4-121">Foreign</span></span> <br/> |<span data-ttu-id="096a4-122">Konferenz Servertyp wie conf: Chat (für IMS) oder conf: Audio-Video.</span><span class="sxs-lookup"><span data-stu-id="096a4-122">Conferencing server type, such as conf:chat (for IMs) or conf:audio-video.</span></span> <span data-ttu-id="096a4-123">Weitere Informationen finden Sie in der [UriTypes-Tabelle](uritypes.md) .</span><span class="sxs-lookup"><span data-stu-id="096a4-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

