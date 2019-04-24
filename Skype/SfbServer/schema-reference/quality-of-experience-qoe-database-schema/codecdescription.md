---
title: CodecDescription-Tabelle
ms.reviewer: ''
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
ms.openlocfilehash: efda27afe9312c25add8be0f74364384aed53b3e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212270"
---
# <a name="codecdescription-table"></a><span data-ttu-id="9d86c-105">CodecDescription-Tabelle</span><span class="sxs-lookup"><span data-stu-id="9d86c-105">CodecDescription table</span></span>
 
<span data-ttu-id="9d86c-106">CodecDescription-Tabelle ordnet eindeutige Codec-IDs dem entsprechenden Codec zu.</span><span class="sxs-lookup"><span data-stu-id="9d86c-106">The CodecDescription table maps unique codec identifiers to their corresponding codec.</span></span> <span data-ttu-id="9d86c-107">Codecs dienen zum Codieren digitale Signale für die Übertragung und Übertragung, und klicken Sie dann zum Decodieren Signale für die Wiedergabe.</span><span class="sxs-lookup"><span data-stu-id="9d86c-107">Codecs are used to encode digital signals for transmission and broadcast, and then to decode those signals for playback.</span></span> <span data-ttu-id="9d86c-108">Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="9d86c-108">This table was introduced in Microsoft Lync Server 2013</span></span>
  
|<span data-ttu-id="9d86c-109">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="9d86c-109">**Column**</span></span>|<span data-ttu-id="9d86c-110">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="9d86c-110">**Data Type**</span></span>|<span data-ttu-id="9d86c-111">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="9d86c-111">**Key/Index**</span></span>|<span data-ttu-id="9d86c-112">**Details**</span><span class="sxs-lookup"><span data-stu-id="9d86c-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9d86c-113">**Codecdescriptionkey entspricht**</span><span class="sxs-lookup"><span data-stu-id="9d86c-113">**CodecDescriptionKey**</span></span> <br/> |<span data-ttu-id="9d86c-114">smallint</span><span class="sxs-lookup"><span data-stu-id="9d86c-114">smallint</span></span>  <br/> |<span data-ttu-id="9d86c-115">Primary</span><span class="sxs-lookup"><span data-stu-id="9d86c-115">Primary</span></span>  <br/> |<span data-ttu-id="9d86c-116">Eindeutiger Bezeichner, die dem Codec zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="9d86c-116">Unique identifier assigned to the codec.</span></span>  <br/> |
|<span data-ttu-id="9d86c-117">**CodecDescription**</span><span class="sxs-lookup"><span data-stu-id="9d86c-117">**CodecDescription**</span></span> <br/> |<span data-ttu-id="9d86c-118">varchar(256)-Wert</span><span class="sxs-lookup"><span data-stu-id="9d86c-118">varchar(256)</span></span>  <br/> |<span data-ttu-id="9d86c-119">Eindeutige</span><span class="sxs-lookup"><span data-stu-id="9d86c-119">Unique</span></span>  <br/> |<span data-ttu-id="9d86c-120">Eindeutige Beschreibung des Codecs entspricht dem codecdescriptionkey entspricht.</span><span class="sxs-lookup"><span data-stu-id="9d86c-120">Unique description of the codec corresponding to the CodecDescriptionKey.</span></span>  <br/> |
   

