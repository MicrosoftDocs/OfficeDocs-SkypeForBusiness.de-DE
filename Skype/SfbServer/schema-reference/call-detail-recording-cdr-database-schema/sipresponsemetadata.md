---
title: SIPResponseMetaData-Tabelle
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: Die SIPResponseMetaDataTable enthält eine Liste der SIP-Antwortcodes und der Klassifizierung und Definition der einzelnen Codes. Diese Codes werden als Antwort für Ereignisse, die SIP-Geräte generiert und SIP-kommunikationssitzungen; der Antwortcode 403 wird beispielsweise generiert, wenn ein SIP-Gerät eine Anforderung sendet, aber der Server die Anforderung annehmen ablehnt.
ms.openlocfilehash: 7b60ffff90434c341fcf15fb75ddc93ac9f26201
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30878210"
---
# <a name="sipresponsemetadata-table"></a><span data-ttu-id="e2a4c-104">SIPResponseMetaData-Tabelle</span><span class="sxs-lookup"><span data-stu-id="e2a4c-104">SIPResponseMetaData table</span></span>
 
<span data-ttu-id="e2a4c-105">Die SIPResponseMetaDataTable enthält eine Liste der SIP-Antwortcodes und der Klassifizierung und Definition der einzelnen Codes.</span><span class="sxs-lookup"><span data-stu-id="e2a4c-105">The SIPResponseMetaDataTable contains a list of SIP response codes and the classification and definition of each of those codes.</span></span> <span data-ttu-id="e2a4c-106">Diese Codes werden als Antwort für Ereignisse, die SIP-Geräte generiert und SIP-kommunikationssitzungen; der Antwortcode 403 wird beispielsweise generiert, wenn ein SIP-Gerät eine Anforderung sendet, aber der Server die Anforderung annehmen ablehnt.</span><span class="sxs-lookup"><span data-stu-id="e2a4c-106">These codes are generated in response to events affecting SIP devices and SIP communication sessions; for example, the response code 403 is generated when a SIP device makes a request, but the server declines to honor that request.</span></span>
  
<span data-ttu-id="e2a4c-107">Diese Tabelle wurde in Skype für Business Server 2015 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e2a4c-107">This table was introduced in Skype for Business Server 2015.</span></span>
  
|<span data-ttu-id="e2a4c-108">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="e2a4c-108">**Column**</span></span>|<span data-ttu-id="e2a4c-109">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="e2a4c-109">**Data Type**</span></span>|<span data-ttu-id="e2a4c-110">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="e2a4c-110">**Key/Index**</span></span>|<span data-ttu-id="e2a4c-111">**Details**</span><span class="sxs-lookup"><span data-stu-id="e2a4c-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e2a4c-112">**ResponseCode**</span><span class="sxs-lookup"><span data-stu-id="e2a4c-112">**ResponseCode**</span></span> <br/> |<span data-ttu-id="e2a4c-113">int</span><span class="sxs-lookup"><span data-stu-id="e2a4c-113">int</span></span>  <br/> |<span data-ttu-id="e2a4c-114">Primary</span><span class="sxs-lookup"><span data-stu-id="e2a4c-114">Primary</span></span>  <br/> |<span data-ttu-id="e2a4c-115">Numerische Wert, der den SIP-Antwortcode repräsentiert.</span><span class="sxs-lookup"><span data-stu-id="e2a4c-115">Numeric value that represents the SIP response code.</span></span>  <br/> |
|<span data-ttu-id="e2a4c-116">**Klasse**</span><span class="sxs-lookup"><span data-stu-id="e2a4c-116">**Class**</span></span> <br/> |<span data-ttu-id="e2a4c-117">int</span><span class="sxs-lookup"><span data-stu-id="e2a4c-117">int</span></span>  <br/> || <span data-ttu-id="e2a4c-118">Allgemeine Klassifizierung für die Antwortcode.</span><span class="sxs-lookup"><span data-stu-id="e2a4c-118">General classification for the response code.</span></span> <span data-ttu-id="e2a4c-119">Klassifikationen umfassen:</span><span class="sxs-lookup"><span data-stu-id="e2a4c-119">Classifications include:</span></span> <br/>  <span data-ttu-id="e2a4c-120">1 – informative Antworten</span><span class="sxs-lookup"><span data-stu-id="e2a4c-120">1 - Informational Responses</span></span> <br/>  <span data-ttu-id="e2a4c-121">2 – erfolgreiche Antworten</span><span class="sxs-lookup"><span data-stu-id="e2a4c-121">2 - Successful Responses</span></span> <br/>  <span data-ttu-id="e2a4c-122">3 – Umleitungsantworten</span><span class="sxs-lookup"><span data-stu-id="e2a4c-122">3 - Redirection Responses</span></span> <br/>  <span data-ttu-id="e2a4c-123">4 – Clientfehlerantworten</span><span class="sxs-lookup"><span data-stu-id="e2a4c-123">4 - Client Failure Responses</span></span> <br/>  <span data-ttu-id="e2a4c-124">5 – Serverfehlerantworten</span><span class="sxs-lookup"><span data-stu-id="e2a4c-124">5 -- Server Failure Responses</span></span> <br/>  <span data-ttu-id="e2a4c-125">6 – globale Fehlerantworten</span><span class="sxs-lookup"><span data-stu-id="e2a4c-125">6 - Global Failure Response</span></span> <br/> |
|<span data-ttu-id="e2a4c-126">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="e2a4c-126">**Description**</span></span> <br/> |<span data-ttu-id="e2a4c-127">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e2a4c-127">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="e2a4c-128">Beschreibung des SIP-Antwortcode.</span><span class="sxs-lookup"><span data-stu-id="e2a4c-128">Description of the SIP response code.</span></span> <span data-ttu-id="e2a4c-129">Antwortcode 181 verfügt beispielsweise über die folgenden Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="e2a4c-129">For example, response code 181 has the following description:</span></span>  <br/> <span data-ttu-id="e2a4c-130">Anruf wird weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="e2a4c-130">Call Is Being Forwarded</span></span>  <br/> |
   

