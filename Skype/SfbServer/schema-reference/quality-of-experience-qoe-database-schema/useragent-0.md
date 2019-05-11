---
title: UserAgent-Ansicht
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: UserAgent-Ansicht speichert Informationen über die Benutzeragents, die an Sitzungen beteiligt waren, die Datensätze in der Datenbank verfügen. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: 942093ece5706115cc4e90171c09df8a8a169b09
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33907024"
---
# <a name="useragent-view"></a><span data-ttu-id="8ebdb-104">UserAgent-Ansicht</span><span class="sxs-lookup"><span data-stu-id="8ebdb-104">UserAgent view</span></span>
 
<span data-ttu-id="8ebdb-105">UserAgent-Ansicht speichert Informationen über die Benutzeragents, die an Sitzungen beteiligt waren, die Datensätze in der Datenbank verfügen.</span><span class="sxs-lookup"><span data-stu-id="8ebdb-105">The UserAgent View stores information about the user agents that have been involved in sessions that have records in the database.</span></span> <span data-ttu-id="8ebdb-106">Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="8ebdb-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="8ebdb-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="8ebdb-107">**Column**</span></span>|<span data-ttu-id="8ebdb-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="8ebdb-108">**Data Type**</span></span>|<span data-ttu-id="8ebdb-109">**Details**</span><span class="sxs-lookup"><span data-stu-id="8ebdb-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8ebdb-110">UserAgentKey</span><span class="sxs-lookup"><span data-stu-id="8ebdb-110">UserAgentKey</span></span>  <br/> |<span data-ttu-id="8ebdb-111">int</span><span class="sxs-lookup"><span data-stu-id="8ebdb-111">int</span></span>  <br/> |<span data-ttu-id="8ebdb-112">Eindeutige Zahl, die diesen Benutzer-Agent identifiziert.</span><span class="sxs-lookup"><span data-stu-id="8ebdb-112">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="8ebdb-113">UserAgent</span><span class="sxs-lookup"><span data-stu-id="8ebdb-113">UserAgent</span></span>  <br/> |<span data-ttu-id="8ebdb-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="8ebdb-114">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="8ebdb-115">Benutzeragenten-Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="8ebdb-115">User agent string.</span></span>  <br/> |
|<span data-ttu-id="8ebdb-116">UAType</span><span class="sxs-lookup"><span data-stu-id="8ebdb-116">UAType</span></span>  <br/> |<span data-ttu-id="8ebdb-117">smallint</span><span class="sxs-lookup"><span data-stu-id="8ebdb-117">smallint</span></span>  <br/> |<span data-ttu-id="8ebdb-118">Typ des Benutzer-Agent.</span><span class="sxs-lookup"><span data-stu-id="8ebdb-118">Type of user agent.</span></span> <span data-ttu-id="8ebdb-119">Finden Sie weitere Details der [UserAgent-Tabelle](useragent.md) .</span><span class="sxs-lookup"><span data-stu-id="8ebdb-119">See the [UserAgent table](useragent.md) for more details.</span></span> <br/> |
|<span data-ttu-id="8ebdb-120">UACategory</span><span class="sxs-lookup"><span data-stu-id="8ebdb-120">UACategory</span></span>  <br/> |<span data-ttu-id="8ebdb-121">nvarchar(64)</span><span class="sxs-lookup"><span data-stu-id="8ebdb-121">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="8ebdb-122">Die Kategorie, der Benutzer-Agent gehört.</span><span class="sxs-lookup"><span data-stu-id="8ebdb-122">Category that the user agent belongs to.</span></span> <span data-ttu-id="8ebdb-123">Der Benutzer-Agent Conferencing_Attendant_1.0 beispielsweise die UACategory CAA gehört.</span><span class="sxs-lookup"><span data-stu-id="8ebdb-123">For example, the user agent Conferencing_Attendant_1.0 belongs to the UACategory CAA.</span></span>  <br/> |
   

