---
title: ErrorDef-Tabelle in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: In der ErrorDef-Tabelle werden Informationen zu den einzelnen Fehlertypen gespeichert, die auftreten können. Jeder Datensatz ist eine Art von Fehler.
ms.openlocfilehash: c6157bb62df47b8fcb1cd158605c5a357e623adf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296280"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a><span data-ttu-id="4d877-104">ErrorDef-Tabelle in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="4d877-104">ErrorDef table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="4d877-105">In der ErrorDef-Tabelle werden Informationen zu den einzelnen Fehlertypen gespeichert, die auftreten können.</span><span class="sxs-lookup"><span data-stu-id="4d877-105">The ErrorDef table stores information about each type of error that may occur.</span></span> <span data-ttu-id="4d877-106">Jeder Datensatz ist eine Art von Fehler.</span><span class="sxs-lookup"><span data-stu-id="4d877-106">Each record is one type of error.</span></span>
  
|<span data-ttu-id="4d877-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="4d877-107">**Column**</span></span>|<span data-ttu-id="4d877-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="4d877-108">**Data Type**</span></span>|<span data-ttu-id="4d877-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="4d877-109">**Key/Index**</span></span>|<span data-ttu-id="4d877-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="4d877-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4d877-111">**ErrorID**</span><span class="sxs-lookup"><span data-stu-id="4d877-111">**ErrorId**</span></span> <br/> |<span data-ttu-id="4d877-112">int</span><span class="sxs-lookup"><span data-stu-id="4d877-112">int</span></span>  <br/> |<span data-ttu-id="4d877-113">Primary</span><span class="sxs-lookup"><span data-stu-id="4d877-113">Primary</span></span>  <br/> |<span data-ttu-id="4d877-114">Eindeutige ID-Nummer, die diese Art von Fehler kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="4d877-114">Unique ID number identifying this type of error.</span></span>  <br/> |
|<span data-ttu-id="4d877-115">**Response Code**</span><span class="sxs-lookup"><span data-stu-id="4d877-115">**ResponseCode**</span></span> <br/> |<span data-ttu-id="4d877-116">int</span><span class="sxs-lookup"><span data-stu-id="4d877-116">int</span></span>  <br/> | <br/> |<span data-ttu-id="4d877-117">Standard mäßiger SIP-Antwortcode, der diesem Fehler zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="4d877-117">Standard SIP response code associated with this error.</span></span>  <br/> |
|<span data-ttu-id="4d877-118">**MsDiagId**</span><span class="sxs-lookup"><span data-stu-id="4d877-118">**MsDiagId**</span></span> <br/> |<span data-ttu-id="4d877-119">int</span><span class="sxs-lookup"><span data-stu-id="4d877-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="4d877-120">Microsoft-Diagnose-ID.</span><span class="sxs-lookup"><span data-stu-id="4d877-120">Microsoft Diagnostic ID.</span></span>  <br/> |
|<span data-ttu-id="4d877-121">**CallTypeId**</span><span class="sxs-lookup"><span data-stu-id="4d877-121">**CallTypeId**</span></span> <br/> |<span data-ttu-id="4d877-122">Int</span><span class="sxs-lookup"><span data-stu-id="4d877-122">Int</span></span>  <br/> |<span data-ttu-id="4d877-123">Fremd</span><span class="sxs-lookup"><span data-stu-id="4d877-123">Foreign</span></span>  <br/> |<span data-ttu-id="4d877-124">Der Typ des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="4d877-124">Type of the call.</span></span> <span data-ttu-id="4d877-125">Weitere Informationen finden Sie in der Tabelle "CallType" [in Skype for Business Server 2015](calltype.md) .</span><span class="sxs-lookup"><span data-stu-id="4d877-125">See the [CallType table in Skype for Business Server 2015](calltype.md) for more information.</span></span> <br/> |
|<span data-ttu-id="4d877-126">**RequestType**</span><span class="sxs-lookup"><span data-stu-id="4d877-126">**RequestType**</span></span> <br/> |<span data-ttu-id="4d877-127">varbinary (33)</span><span class="sxs-lookup"><span data-stu-id="4d877-127">varbinary(33)</span></span>  <br/> | <br/> |<span data-ttu-id="4d877-128">Der Typ der fehlgeschlagenen Anforderung.</span><span class="sxs-lookup"><span data-stu-id="4d877-128">Type of request that failed.</span></span>  <br/> <span data-ttu-id="4d877-129">Diese Daten können mithilfe der folgenden Syntax in das Text Format konvertiert werden:</span><span class="sxs-lookup"><span data-stu-id="4d877-129">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|<span data-ttu-id="4d877-130">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="4d877-130">**ContentType**</span></span> <br/> |<span data-ttu-id="4d877-131">varbinary (257)</span><span class="sxs-lookup"><span data-stu-id="4d877-131">varbinary(257)</span></span>  <br/> | <br/> |<span data-ttu-id="4d877-132">Inhaltstyp der fehlgeschlagenen Anforderung.</span><span class="sxs-lookup"><span data-stu-id="4d877-132">Content type of the request that failed.</span></span>  <br/> <span data-ttu-id="4d877-133">Diese Daten können mithilfe dieser Syntax in das Text Format konvertiert werden:</span><span class="sxs-lookup"><span data-stu-id="4d877-133">This data can be converted to text format by using this syntaxt:</span></span>  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

