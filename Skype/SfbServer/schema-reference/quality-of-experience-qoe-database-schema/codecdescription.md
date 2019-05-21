---
title: CodecDescription-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: Die CodecDescription-Tabelle ordnet eindeutige Codec-IDs dem zugehörigen Codec zu. Codecs werden verwendet, um digitale Signale für die Übertragung und Übertragung zu kodieren und diese Signale zur Wiedergabe zu decodieren. Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.
ms.openlocfilehash: 678b458757c54385b608d89efd6b2c621c6cd42f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295041"
---
# <a name="codecdescription-table"></a><span data-ttu-id="7468b-105">CodecDescription-Tabelle</span><span class="sxs-lookup"><span data-stu-id="7468b-105">CodecDescription table</span></span>
 
<span data-ttu-id="7468b-106">Die CodecDescription-Tabelle ordnet eindeutige Codec-IDs dem zugehörigen Codec zu.</span><span class="sxs-lookup"><span data-stu-id="7468b-106">The CodecDescription table maps unique codec identifiers to their corresponding codec.</span></span> <span data-ttu-id="7468b-107">Codecs werden verwendet, um digitale Signale für die Übertragung und Übertragung zu kodieren und diese Signale zur Wiedergabe zu decodieren.</span><span class="sxs-lookup"><span data-stu-id="7468b-107">Codecs are used to encode digital signals for transmission and broadcast, and then to decode those signals for playback.</span></span> <span data-ttu-id="7468b-108">Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="7468b-108">This table was introduced in Microsoft Lync Server 2013</span></span>
  
|<span data-ttu-id="7468b-109">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="7468b-109">**Column**</span></span>|<span data-ttu-id="7468b-110">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="7468b-110">**Data Type**</span></span>|<span data-ttu-id="7468b-111">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="7468b-111">**Key/Index**</span></span>|<span data-ttu-id="7468b-112">**Details**</span><span class="sxs-lookup"><span data-stu-id="7468b-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7468b-113">**CodecDescriptionKey**</span><span class="sxs-lookup"><span data-stu-id="7468b-113">**CodecDescriptionKey**</span></span> <br/> |<span data-ttu-id="7468b-114">smallint</span><span class="sxs-lookup"><span data-stu-id="7468b-114">smallint</span></span>  <br/> |<span data-ttu-id="7468b-115">Primary</span><span class="sxs-lookup"><span data-stu-id="7468b-115">Primary</span></span>  <br/> |<span data-ttu-id="7468b-116">Eindeutiger Bezeichner, der dem Codec zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="7468b-116">Unique identifier assigned to the codec.</span></span>  <br/> |
|<span data-ttu-id="7468b-117">**CodecDescription**</span><span class="sxs-lookup"><span data-stu-id="7468b-117">**CodecDescription**</span></span> <br/> |<span data-ttu-id="7468b-118">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="7468b-118">varchar(256)</span></span>  <br/> |<span data-ttu-id="7468b-119">Eindeutigen</span><span class="sxs-lookup"><span data-stu-id="7468b-119">Unique</span></span>  <br/> |<span data-ttu-id="7468b-120">Eindeutige Beschreibung des Codecs, der dem CodecDescriptionKey entspricht.</span><span class="sxs-lookup"><span data-stu-id="7468b-120">Unique description of the codec corresponding to the CodecDescriptionKey.</span></span>  <br/> |
   

