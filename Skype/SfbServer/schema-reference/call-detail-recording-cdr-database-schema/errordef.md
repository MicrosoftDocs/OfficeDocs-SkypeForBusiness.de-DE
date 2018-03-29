---
title: ErrorDef-Tabelle in Skype für Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: ErrorDef-Tabelle speichert Informationen zu jeder Art von Fehler, die auftreten können. Jeder Datensatz ist eine Art von Fehler.
ms.openlocfilehash: 4583e1130d257a99d075f2dec0dea80ee6b1390c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a><span data-ttu-id="6062d-104">ErrorDef-Tabelle in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="6062d-104">ErrorDef table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="6062d-105">ErrorDef-Tabelle speichert Informationen zu jeder Art von Fehler, die auftreten können.</span><span class="sxs-lookup"><span data-stu-id="6062d-105">The ErrorDef table stores information about each type of error that may occur.</span></span> <span data-ttu-id="6062d-106">Jeder Datensatz ist eine Art von Fehler.</span><span class="sxs-lookup"><span data-stu-id="6062d-106">Each record is one type of error.</span></span>
  
|<span data-ttu-id="6062d-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="6062d-107">**Column**</span></span>|<span data-ttu-id="6062d-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="6062d-108">**Data Type**</span></span>|<span data-ttu-id="6062d-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="6062d-109">**Key/Index**</span></span>|<span data-ttu-id="6062d-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="6062d-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6062d-111">**Fehler-ID**</span><span class="sxs-lookup"><span data-stu-id="6062d-111">**ErrorId**</span></span> <br/> |<span data-ttu-id="6062d-112">int</span><span class="sxs-lookup"><span data-stu-id="6062d-112">int</span></span>  <br/> |<span data-ttu-id="6062d-113">Primary</span><span class="sxs-lookup"><span data-stu-id="6062d-113">Primary</span></span>  <br/> |<span data-ttu-id="6062d-114">Eindeutige ID-Nummer, die diesen Fehlertyp identifiziert.</span><span class="sxs-lookup"><span data-stu-id="6062d-114">Unique ID number identifying this type of error.</span></span>  <br/> |
|<span data-ttu-id="6062d-115">**ResponseCode**</span><span class="sxs-lookup"><span data-stu-id="6062d-115">**ResponseCode**</span></span> <br/> |<span data-ttu-id="6062d-116">int</span><span class="sxs-lookup"><span data-stu-id="6062d-116">int</span></span>  <br/> | <br/> |<span data-ttu-id="6062d-117">Standardmäßige SIP-Antwortcode diesem Fehler zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="6062d-117">Standard SIP response code associated with this error.</span></span>  <br/> |
|<span data-ttu-id="6062d-118">**MsDiagId**</span><span class="sxs-lookup"><span data-stu-id="6062d-118">**MsDiagId**</span></span> <br/> |<span data-ttu-id="6062d-119">int</span><span class="sxs-lookup"><span data-stu-id="6062d-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="6062d-120">Microsoft-Diagnose-ID.</span><span class="sxs-lookup"><span data-stu-id="6062d-120">Microsoft Diagnostic ID.</span></span>  <br/> |
|<span data-ttu-id="6062d-121">**CallTypeId**</span><span class="sxs-lookup"><span data-stu-id="6062d-121">**CallTypeId**</span></span> <br/> |<span data-ttu-id="6062d-122">Int</span><span class="sxs-lookup"><span data-stu-id="6062d-122">Int</span></span>  <br/> |<span data-ttu-id="6062d-123">Fremdschlüssel</span><span class="sxs-lookup"><span data-stu-id="6062d-123">Foreign</span></span>  <br/> |<span data-ttu-id="6062d-124">Art des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="6062d-124">Type of the call.</span></span> <span data-ttu-id="6062d-125">[CallType-Tabelle in Skype für Business Server 2015](calltype.md) Weitere Informationen finden Sie.</span><span class="sxs-lookup"><span data-stu-id="6062d-125">See the [CallType table in Skype for Business Server 2015](calltype.md) for more information.</span></span> <br/> |
|<span data-ttu-id="6062d-126">**RequestType**</span><span class="sxs-lookup"><span data-stu-id="6062d-126">**RequestType**</span></span> <br/> |<span data-ttu-id="6062d-127">varbinary(33)</span><span class="sxs-lookup"><span data-stu-id="6062d-127">varbinary(33)</span></span>  <br/> | <br/> |<span data-ttu-id="6062d-128">Typ der erfolgreichen Anforderung.</span><span class="sxs-lookup"><span data-stu-id="6062d-128">Type of request that failed.</span></span>  <br/> <span data-ttu-id="6062d-129">Diese Daten können mithilfe der folgenden Syntax in das Textformat konvertiert werden:</span><span class="sxs-lookup"><span data-stu-id="6062d-129">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|<span data-ttu-id="6062d-130">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="6062d-130">**ContentType**</span></span> <br/> |<span data-ttu-id="6062d-131">varbinary(257)</span><span class="sxs-lookup"><span data-stu-id="6062d-131">varbinary(257)</span></span>  <br/> | <br/> |<span data-ttu-id="6062d-132">Inhaltstyp der erfolgreichen Anforderung.</span><span class="sxs-lookup"><span data-stu-id="6062d-132">Content type of the request that failed.</span></span>  <br/> <span data-ttu-id="6062d-133">Diese Daten können mithilfe dieser Syntax in das Textformat in das Textformat konvertiert werden:</span><span class="sxs-lookup"><span data-stu-id="6062d-133">This data can be converted to text format by using this syntaxt:</span></span>  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

