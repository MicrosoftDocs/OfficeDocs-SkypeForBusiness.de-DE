---
title: CodecDescription-Tabelle
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: CodecDescription-Tabelle ordnet eindeutige Codec-IDs dem entsprechenden Codec zu. Codecs dienen zum Codieren digitale Signale für die Übertragung und Übertragung, und klicken Sie dann zum Decodieren Signale für die Wiedergabe. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: 49dea2867ef7614fab3015efbd24e6ec47da8c55
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="codecdescription-table"></a><span data-ttu-id="94cb6-105">CodecDescription-Tabelle</span><span class="sxs-lookup"><span data-stu-id="94cb6-105">CodecDescription table</span></span>
 
<span data-ttu-id="94cb6-106">CodecDescription-Tabelle ordnet eindeutige Codec-IDs dem entsprechenden Codec zu.</span><span class="sxs-lookup"><span data-stu-id="94cb6-106">The CodecDescription table maps unique codec identifiers to their corresponding codec.</span></span> <span data-ttu-id="94cb6-107">Codecs dienen zum Codieren digitale Signale für die Übertragung und Übertragung, und klicken Sie dann zum Decodieren Signale für die Wiedergabe.</span><span class="sxs-lookup"><span data-stu-id="94cb6-107">Codecs are used to encode digital signals for transmission and broadcast, and then to decode those signals for playback.</span></span> <span data-ttu-id="94cb6-108">Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="94cb6-108">This table was introduced in Microsoft Lync Server 2013</span></span>
  
|<span data-ttu-id="94cb6-109">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="94cb6-109">**Column**</span></span>|<span data-ttu-id="94cb6-110">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="94cb6-110">**Data Type**</span></span>|<span data-ttu-id="94cb6-111">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="94cb6-111">**Key/Index**</span></span>|<span data-ttu-id="94cb6-112">**Details**</span><span class="sxs-lookup"><span data-stu-id="94cb6-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="94cb6-113">**Codecdescriptionkey entspricht**</span><span class="sxs-lookup"><span data-stu-id="94cb6-113">**CodecDescriptionKey**</span></span> <br/> |<span data-ttu-id="94cb6-114">smallint</span><span class="sxs-lookup"><span data-stu-id="94cb6-114">smallint</span></span>  <br/> |<span data-ttu-id="94cb6-115">Primary</span><span class="sxs-lookup"><span data-stu-id="94cb6-115">Primary</span></span>  <br/> |<span data-ttu-id="94cb6-116">Eindeutiger Bezeichner, die dem Codec zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="94cb6-116">Unique identifier assigned to the codec.</span></span>  <br/> |
|<span data-ttu-id="94cb6-117">**CodecDescription**</span><span class="sxs-lookup"><span data-stu-id="94cb6-117">**CodecDescription**</span></span> <br/> |<span data-ttu-id="94cb6-118">varchar(256)-Wert</span><span class="sxs-lookup"><span data-stu-id="94cb6-118">varchar(256)</span></span>  <br/> |<span data-ttu-id="94cb6-119">Eindeutige</span><span class="sxs-lookup"><span data-stu-id="94cb6-119">Unique</span></span>  <br/> |<span data-ttu-id="94cb6-120">Eindeutige Beschreibung des Codecs entspricht dem codecdescriptionkey entspricht.</span><span class="sxs-lookup"><span data-stu-id="94cb6-120">Unique description of the codec corresponding to the CodecDescriptionKey.</span></span>  <br/> |
   

