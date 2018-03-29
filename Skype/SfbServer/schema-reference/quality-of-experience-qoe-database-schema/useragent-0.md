---
title: UserAgent-Ansicht
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: UserAgent-Ansicht speichert Informationen über die Benutzeragents, die an Sitzungen beteiligt waren, die Datensätze in der Datenbank verfügen. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: 8df1d45ed1272a886a440aded79a9c4e04c1bae8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="useragent-view"></a><span data-ttu-id="9974e-104">UserAgent-Ansicht</span><span class="sxs-lookup"><span data-stu-id="9974e-104">UserAgent view</span></span>
 
<span data-ttu-id="9974e-105">UserAgent-Ansicht speichert Informationen über die Benutzeragents, die an Sitzungen beteiligt waren, die Datensätze in der Datenbank verfügen.</span><span class="sxs-lookup"><span data-stu-id="9974e-105">The UserAgent View stores information about the user agents that have been involved in sessions that have records in the database.</span></span> <span data-ttu-id="9974e-106">Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="9974e-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="9974e-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="9974e-107">**Column**</span></span>|<span data-ttu-id="9974e-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="9974e-108">**Data Type**</span></span>|<span data-ttu-id="9974e-109">**Details**</span><span class="sxs-lookup"><span data-stu-id="9974e-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9974e-110">UserAgentKey</span><span class="sxs-lookup"><span data-stu-id="9974e-110">UserAgentKey</span></span>  <br/> |<span data-ttu-id="9974e-111">int</span><span class="sxs-lookup"><span data-stu-id="9974e-111">int</span></span>  <br/> |<span data-ttu-id="9974e-112">Eindeutige Zahl, die diesen Benutzer-Agent identifiziert.</span><span class="sxs-lookup"><span data-stu-id="9974e-112">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="9974e-113">UserAgent</span><span class="sxs-lookup"><span data-stu-id="9974e-113">UserAgent</span></span>  <br/> |<span data-ttu-id="9974e-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9974e-114">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="9974e-115">Benutzeragenten-Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="9974e-115">User agent string.</span></span>  <br/> |
|<span data-ttu-id="9974e-116">UAType</span><span class="sxs-lookup"><span data-stu-id="9974e-116">UAType</span></span>  <br/> |<span data-ttu-id="9974e-117">smallint</span><span class="sxs-lookup"><span data-stu-id="9974e-117">smallint</span></span>  <br/> |<span data-ttu-id="9974e-118">Typ des Benutzer-Agent.</span><span class="sxs-lookup"><span data-stu-id="9974e-118">Type of user agent.</span></span> <span data-ttu-id="9974e-119">Finden Sie weitere Details der [UserAgent-Tabelle](useragent.md) .</span><span class="sxs-lookup"><span data-stu-id="9974e-119">See the [UserAgent table](useragent.md) for more details.</span></span> <br/> |
|<span data-ttu-id="9974e-120">UACategory</span><span class="sxs-lookup"><span data-stu-id="9974e-120">UACategory</span></span>  <br/> |<span data-ttu-id="9974e-121">nvarchar(64)</span><span class="sxs-lookup"><span data-stu-id="9974e-121">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="9974e-122">Die Kategorie, der Benutzer-Agent gehört.</span><span class="sxs-lookup"><span data-stu-id="9974e-122">Category that the user agent belongs to.</span></span> <span data-ttu-id="9974e-123">Der Benutzer-Agent Conferencing_Attendant_1.0 beispielsweise die UACategory CAA gehört.</span><span class="sxs-lookup"><span data-stu-id="9974e-123">For example, the user agent Conferencing_Attendant_1.0 belongs to the UACategory CAA.</span></span>  <br/> |
   

