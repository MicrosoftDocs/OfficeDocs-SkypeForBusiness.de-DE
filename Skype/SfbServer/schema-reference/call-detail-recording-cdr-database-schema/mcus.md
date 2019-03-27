---
title: MCUs-Tabelle in Skype für Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: Die Mcus-Tabelle ist eine Tabelle. Jeder Datensatz speichert Informationen über ein Live Meeting-Dienst. Dazu zählen die Sofortnachrichten-Konferenzdienst und der Telefonie-Konferenzdienst (die als Prozesse auf Front-End-Servern ausgeführt werden), und die-Webkonferenzdienst und A / V-Konferenzdienst.
ms.openlocfilehash: e051af3a77d4f9b8231c122c596a3b6915f6f3e1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30893012"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a><span data-ttu-id="27879-105">MCUs-Tabelle in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="27879-105">Mcus table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="27879-106">Die Mcus-Tabelle ist eine Tabelle.</span><span class="sxs-lookup"><span data-stu-id="27879-106">The Mcus table is a supporting table.</span></span> <span data-ttu-id="27879-107">Jeder Datensatz speichert Informationen über ein Live Meeting-Dienst.</span><span class="sxs-lookup"><span data-stu-id="27879-107">Each record stores information about one conferencing service.</span></span> <span data-ttu-id="27879-108">Dazu zählen die Sofortnachrichten-Konferenzdienst und der Telefonie-Konferenzdienst (die als Prozesse auf Front-End-Servern ausgeführt werden), und die-Webkonferenzdienst und A / V-Konferenzdienst.</span><span class="sxs-lookup"><span data-stu-id="27879-108">These can include the IM Conferencing service and the Telephony Conferencing service (which run as processes on front-end servers), and the Web Conferencing service and A/V Conferencing service.</span></span> 
  
|<span data-ttu-id="27879-109">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="27879-109">**Column**</span></span>|<span data-ttu-id="27879-110">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="27879-110">**Data Type**</span></span>|<span data-ttu-id="27879-111">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="27879-111">**Key/Index**</span></span>|<span data-ttu-id="27879-112">**Details**</span><span class="sxs-lookup"><span data-stu-id="27879-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="27879-113">**McuId**</span><span class="sxs-lookup"><span data-stu-id="27879-113">**McuId**</span></span> <br/> |<span data-ttu-id="27879-114">int</span><span class="sxs-lookup"><span data-stu-id="27879-114">int</span></span>  <br/> |<span data-ttu-id="27879-115">Primary</span><span class="sxs-lookup"><span data-stu-id="27879-115">Primary</span></span>  <br/> |<span data-ttu-id="27879-116">Eindeutige Zahl, die Konferenzserver identifiziert.</span><span class="sxs-lookup"><span data-stu-id="27879-116">Unique number identifying this conferencing server.</span></span>  <br/> |
|<span data-ttu-id="27879-117">**McuUri**</span><span class="sxs-lookup"><span data-stu-id="27879-117">**McuUri**</span></span> <br/> |<span data-ttu-id="27879-118">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="27879-118">nvarchar(450)</span></span>  <br/> | <br/> | <br/> |
|<span data-ttu-id="27879-119">**McuTypeId**</span><span class="sxs-lookup"><span data-stu-id="27879-119">**McuTypeId**</span></span> <br/> |<span data-ttu-id="27879-120">inyint</span><span class="sxs-lookup"><span data-stu-id="27879-120">inyint</span></span>  <br/> | <span data-ttu-id="27879-121">Ausländisch</span><span class="sxs-lookup"><span data-stu-id="27879-121">Foreign</span></span> <br/> |<span data-ttu-id="27879-122">Konferenzservertyp wie Conf:chat (für Sofortnachrichten) oder Conf:audio-video.</span><span class="sxs-lookup"><span data-stu-id="27879-122">Conferencing server type, such as conf:chat (for IMs) or conf:audio-video.</span></span> <span data-ttu-id="27879-123">Finden Sie weitere Informationen der [UriTypes-Tabelle](uritypes.md) .</span><span class="sxs-lookup"><span data-stu-id="27879-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

