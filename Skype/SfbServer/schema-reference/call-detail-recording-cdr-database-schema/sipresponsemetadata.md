---
title: SIPResponseMetaData-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: Das SIPResponseMetaDataTable enthält eine Liste der SIP-Antwortcodes sowie die Klassifizierung und Definition der einzelnen Codes. Diese Codes werden als Reaktion auf Ereignisse generiert, die sich auf SIP-Geräte und SIP-Kommunikationssitzungen auswirken. So wird beispielsweise der Antwortcode 403 generiert, wenn ein SIP-Gerät eine Anforderung stellt, aber der Server lehnt die Anerkennung dieser Anforderung ab.
ms.openlocfilehash: 2c302793dc9f9c53d445d231a261bf43a0c385df
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814893"
---
# <a name="sipresponsemetadata-table"></a><span data-ttu-id="43da7-104">SIPResponseMetaData-Tabelle</span><span class="sxs-lookup"><span data-stu-id="43da7-104">SIPResponseMetaData table</span></span>
 
<span data-ttu-id="43da7-105">Das SIPResponseMetaDataTable enthält eine Liste der SIP-Antwortcodes sowie die Klassifizierung und Definition der einzelnen Codes.</span><span class="sxs-lookup"><span data-stu-id="43da7-105">The SIPResponseMetaDataTable contains a list of SIP response codes and the classification and definition of each of those codes.</span></span> <span data-ttu-id="43da7-106">Diese Codes werden als Reaktion auf Ereignisse generiert, die sich auf SIP-Geräte und SIP-Kommunikationssitzungen auswirken. So wird beispielsweise der Antwortcode 403 generiert, wenn ein SIP-Gerät eine Anforderung stellt, aber der Server lehnt die Anerkennung dieser Anforderung ab.</span><span class="sxs-lookup"><span data-stu-id="43da7-106">These codes are generated in response to events affecting SIP devices and SIP communication sessions; for example, the response code 403 is generated when a SIP device makes a request, but the server declines to honor that request.</span></span>
  
<span data-ttu-id="43da7-107">Diese Tabelle wurde in Skype for Business Server 2015 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="43da7-107">This table was introduced in Skype for Business Server 2015.</span></span>
  
|<span data-ttu-id="43da7-108">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="43da7-108">**Column**</span></span>|<span data-ttu-id="43da7-109">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="43da7-109">**Data Type**</span></span>|<span data-ttu-id="43da7-110">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="43da7-110">**Key/Index**</span></span>|<span data-ttu-id="43da7-111">**Details**</span><span class="sxs-lookup"><span data-stu-id="43da7-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="43da7-112">**Response Code**</span><span class="sxs-lookup"><span data-stu-id="43da7-112">**ResponseCode**</span></span> <br/> |<span data-ttu-id="43da7-113">int</span><span class="sxs-lookup"><span data-stu-id="43da7-113">int</span></span>  <br/> |<span data-ttu-id="43da7-114">Primary</span><span class="sxs-lookup"><span data-stu-id="43da7-114">Primary</span></span>  <br/> |<span data-ttu-id="43da7-115">Numerischer Wert, der den SIP-Antwortcode darstellt.</span><span class="sxs-lookup"><span data-stu-id="43da7-115">Numeric value that represents the SIP response code.</span></span>  <br/> |
|<span data-ttu-id="43da7-116">**Klasse**</span><span class="sxs-lookup"><span data-stu-id="43da7-116">**Class**</span></span> <br/> |<span data-ttu-id="43da7-117">int</span><span class="sxs-lookup"><span data-stu-id="43da7-117">int</span></span>  <br/> || <span data-ttu-id="43da7-118">Allgemeine Klassifizierung für den Antwortcode.</span><span class="sxs-lookup"><span data-stu-id="43da7-118">General classification for the response code.</span></span> <span data-ttu-id="43da7-119">Zu den Klassifizierungen gehören:</span><span class="sxs-lookup"><span data-stu-id="43da7-119">Classifications include:</span></span> <br/>  <span data-ttu-id="43da7-120">1 – Informations Antworten</span><span class="sxs-lookup"><span data-stu-id="43da7-120">1 - Informational Responses</span></span> <br/>  <span data-ttu-id="43da7-121">2 – erfolgreiche Antworten</span><span class="sxs-lookup"><span data-stu-id="43da7-121">2 - Successful Responses</span></span> <br/>  <span data-ttu-id="43da7-122">3-Umleitungsantworten</span><span class="sxs-lookup"><span data-stu-id="43da7-122">3 - Redirection Responses</span></span> <br/>  <span data-ttu-id="43da7-123">4 – Antworten auf Client Fehler</span><span class="sxs-lookup"><span data-stu-id="43da7-123">4 - Client Failure Responses</span></span> <br/>  <span data-ttu-id="43da7-124">5 – Server Fehlerantworten</span><span class="sxs-lookup"><span data-stu-id="43da7-124">5 -- Server Failure Responses</span></span> <br/>  <span data-ttu-id="43da7-125">6 – globale Fehlerantwort</span><span class="sxs-lookup"><span data-stu-id="43da7-125">6 - Global Failure Response</span></span> <br/> |
|<span data-ttu-id="43da7-126">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="43da7-126">**Description**</span></span> <br/> |<span data-ttu-id="43da7-127">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="43da7-127">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="43da7-128">Beschreibung des SIP-Antwortcodes.</span><span class="sxs-lookup"><span data-stu-id="43da7-128">Description of the SIP response code.</span></span> <span data-ttu-id="43da7-129">Antwortcode 181 weist beispielsweise die folgende Beschreibung auf:</span><span class="sxs-lookup"><span data-stu-id="43da7-129">For example, response code 181 has the following description:</span></span>  <br/> <span data-ttu-id="43da7-130">Anruf wird weitergeleitet</span><span class="sxs-lookup"><span data-stu-id="43da7-130">Call Is Being Forwarded</span></span>  <br/> |
   

