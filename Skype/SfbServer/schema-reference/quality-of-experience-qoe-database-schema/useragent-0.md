---
title: UserAgent-Ansicht
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
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: Die UserAgent-Ansicht speichert Informationen zu den Benutzer-Agents, die an Sitzungen teilgenommen haben, die Datensätze in der Datenbank aufweisen. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.
ms.openlocfilehash: 76ac99b1fdadbeb6817b36483f4fe5762db47333
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805083"
---
# <a name="useragent-view"></a><span data-ttu-id="3f89e-104">UserAgent-Ansicht</span><span class="sxs-lookup"><span data-stu-id="3f89e-104">UserAgent view</span></span>
 
<span data-ttu-id="3f89e-105">Die UserAgent-Ansicht speichert Informationen zu den Benutzer-Agents, die an Sitzungen teilgenommen haben, die Datensätze in der Datenbank aufweisen.</span><span class="sxs-lookup"><span data-stu-id="3f89e-105">The UserAgent View stores information about the user agents that have been involved in sessions that have records in the database.</span></span> <span data-ttu-id="3f89e-106">Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="3f89e-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="3f89e-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="3f89e-107">**Column**</span></span>|<span data-ttu-id="3f89e-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="3f89e-108">**Data Type**</span></span>|<span data-ttu-id="3f89e-109">**Details**</span><span class="sxs-lookup"><span data-stu-id="3f89e-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3f89e-110">UserAgentKey</span><span class="sxs-lookup"><span data-stu-id="3f89e-110">UserAgentKey</span></span>  <br/> |<span data-ttu-id="3f89e-111">int</span><span class="sxs-lookup"><span data-stu-id="3f89e-111">int</span></span>  <br/> |<span data-ttu-id="3f89e-112">Eindeutige Nummer, die diesen Benutzer-Agent kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="3f89e-112">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="3f89e-113">UserAgent</span><span class="sxs-lookup"><span data-stu-id="3f89e-113">UserAgent</span></span>  <br/> |<span data-ttu-id="3f89e-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="3f89e-114">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="3f89e-115">Benutzer-Agent-Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="3f89e-115">User agent string.</span></span>  <br/> |
|<span data-ttu-id="3f89e-116">UAType</span><span class="sxs-lookup"><span data-stu-id="3f89e-116">UAType</span></span>  <br/> |<span data-ttu-id="3f89e-117">smallint</span><span class="sxs-lookup"><span data-stu-id="3f89e-117">smallint</span></span>  <br/> |<span data-ttu-id="3f89e-118">Der Typ des Benutzer-Agents.</span><span class="sxs-lookup"><span data-stu-id="3f89e-118">Type of user agent.</span></span> <span data-ttu-id="3f89e-119">Weitere Informationen finden Sie in der [userAgent-Tabelle](useragent.md) .</span><span class="sxs-lookup"><span data-stu-id="3f89e-119">See the [UserAgent table](useragent.md) for more details.</span></span> <br/> |
|<span data-ttu-id="3f89e-120">UACategory</span><span class="sxs-lookup"><span data-stu-id="3f89e-120">UACategory</span></span>  <br/> |<span data-ttu-id="3f89e-121">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="3f89e-121">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="3f89e-122">Die Kategorie, zu der der Benutzer-Agent gehört.</span><span class="sxs-lookup"><span data-stu-id="3f89e-122">Category that the user agent belongs to.</span></span> <span data-ttu-id="3f89e-123">Beispielsweise gehört der Benutzer-Agent Conferencing_Attendant_1 .0 zu UACategory CAA.</span><span class="sxs-lookup"><span data-stu-id="3f89e-123">For example, the user agent Conferencing_Attendant_1.0 belongs to the UACategory CAA.</span></span>  <br/> |
   

