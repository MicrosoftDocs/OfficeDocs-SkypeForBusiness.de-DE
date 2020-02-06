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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: Die Tabelle "MCU" ist eine unterstützende Tabelle. In jedem Datensatz werden Informationen zu einem Konferenzdienst gespeichert. Dazu gehören der Chat-Konferenzdienst und der Telefonie-Konferenzdienst (der als Prozesse auf Front-End-Servern ausgeführt wird) sowie der Webkonferenzdienst und ein/V-Konferenzdienst.
ms.openlocfilehash: 1e5141ee2a103e540d3ac50e99de0036f31262d7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815063"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a><span data-ttu-id="a787f-105">Tabelle "Tabelle" in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="a787f-105">Mcus table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a787f-106">Die Tabelle "MCU" ist eine unterstützende Tabelle.</span><span class="sxs-lookup"><span data-stu-id="a787f-106">The Mcus table is a supporting table.</span></span> <span data-ttu-id="a787f-107">In jedem Datensatz werden Informationen zu einem Konferenzdienst gespeichert.</span><span class="sxs-lookup"><span data-stu-id="a787f-107">Each record stores information about one conferencing service.</span></span> <span data-ttu-id="a787f-108">Dazu gehören der Chat-Konferenzdienst und der Telefonie-Konferenzdienst (der als Prozesse auf Front-End-Servern ausgeführt wird) sowie der Webkonferenzdienst und ein/V-Konferenzdienst.</span><span class="sxs-lookup"><span data-stu-id="a787f-108">These can include the IM Conferencing service and the Telephony Conferencing service (which run as processes on front-end servers), and the Web Conferencing service and A/V Conferencing service.</span></span> 
  
|<span data-ttu-id="a787f-109">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="a787f-109">**Column**</span></span>|<span data-ttu-id="a787f-110">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="a787f-110">**Data Type**</span></span>|<span data-ttu-id="a787f-111">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="a787f-111">**Key/Index**</span></span>|<span data-ttu-id="a787f-112">**Details**</span><span class="sxs-lookup"><span data-stu-id="a787f-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a787f-113">**McuId**</span><span class="sxs-lookup"><span data-stu-id="a787f-113">**McuId**</span></span> <br/> |<span data-ttu-id="a787f-114">int</span><span class="sxs-lookup"><span data-stu-id="a787f-114">int</span></span>  <br/> |<span data-ttu-id="a787f-115">Primary</span><span class="sxs-lookup"><span data-stu-id="a787f-115">Primary</span></span>  <br/> |<span data-ttu-id="a787f-116">Eindeutige Nummer, die diesen Konferenzserver identifiziert.</span><span class="sxs-lookup"><span data-stu-id="a787f-116">Unique number identifying this conferencing server.</span></span>  <br/> |
|<span data-ttu-id="a787f-117">**McuUri**</span><span class="sxs-lookup"><span data-stu-id="a787f-117">**McuUri**</span></span> <br/> |<span data-ttu-id="a787f-118">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="a787f-118">nvarchar(450)</span></span>  <br/> | <br/> | <br/> |
|<span data-ttu-id="a787f-119">**McuTypeId**</span><span class="sxs-lookup"><span data-stu-id="a787f-119">**McuTypeId**</span></span> <br/> |<span data-ttu-id="a787f-120">inyint</span><span class="sxs-lookup"><span data-stu-id="a787f-120">inyint</span></span>  <br/> | <span data-ttu-id="a787f-121">Fremd</span><span class="sxs-lookup"><span data-stu-id="a787f-121">Foreign</span></span> <br/> |<span data-ttu-id="a787f-122">Konferenz Servertyp wie conf: Chat (für IMS) oder conf: Audio-Video.</span><span class="sxs-lookup"><span data-stu-id="a787f-122">Conferencing server type, such as conf:chat (for IMs) or conf:audio-video.</span></span> <span data-ttu-id="a787f-123">Weitere Informationen finden Sie in der [UriTypes-Tabelle](uritypes.md) .</span><span class="sxs-lookup"><span data-stu-id="a787f-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

