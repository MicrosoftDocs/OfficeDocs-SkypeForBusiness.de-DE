---
title: UriTypes-Tabelle
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
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: Die UriTypes-Tabelle enthält die verschiedenen URI-Typen (Uniform Resource Identifier), die in Skype for Business Server 2015 überwacht werden.
ms.openlocfilehash: 81cd00503f88eac03f952b63ef7a3bd9464c1f51
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814843"
---
# <a name="uritypes-table"></a><span data-ttu-id="40f18-103">UriTypes-Tabelle</span><span class="sxs-lookup"><span data-stu-id="40f18-103">UriTypes table</span></span>
 
<span data-ttu-id="40f18-104">Die UriTypes-Tabelle enthält die verschiedenen URI-Typen (Uniform Resource Identifier), die in Skype for Business Server 2015 überwacht werden.</span><span class="sxs-lookup"><span data-stu-id="40f18-104">The UriTypes Table contains the different URI (Uniform resource identifier) types monitored in Skype for Business Server 2015.</span></span>

<span data-ttu-id="40f18-105">Wenn die CDR-DB erstellt wird, werden zwei Datensätze erstellt, die PhoneUri und UserUri darstellen, und Datensätze, die danach erstellt wurden, werden dynamisch UriTypeId zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="40f18-105">When the CDR DB is created, two records to represent PhoneUri and UserUri are created, and records created after that are dynamically assigned UriTypeId.</span></span> 
  
|<span data-ttu-id="40f18-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="40f18-106">**Column**</span></span>|<span data-ttu-id="40f18-107">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="40f18-107">**Data Type**</span></span>|<span data-ttu-id="40f18-108">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="40f18-108">**Key/Index**</span></span>|<span data-ttu-id="40f18-109">**Details**</span><span class="sxs-lookup"><span data-stu-id="40f18-109">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="40f18-110">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="40f18-110">**UriTypeId**</span></span> <br/> |<span data-ttu-id="40f18-111">tinyint</span><span class="sxs-lookup"><span data-stu-id="40f18-111">tinyint</span></span>  <br/> |<span data-ttu-id="40f18-112">Primary</span><span class="sxs-lookup"><span data-stu-id="40f18-112">Primary</span></span>  <br/> |<span data-ttu-id="40f18-113">Eindeutiger Bezeichner, der einem URI-Typ zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="40f18-113">Unique identifier assigned to a URI type.</span></span>  <br/> <span data-ttu-id="40f18-114">Mögliche Werte: 0 bis 255</span><span class="sxs-lookup"><span data-stu-id="40f18-114">Possible values - 0 to 255</span></span> |
|<span data-ttu-id="40f18-115">**UriType**</span><span class="sxs-lookup"><span data-stu-id="40f18-115">**UriType**</span></span> <br/> |<span data-ttu-id="40f18-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="40f18-116">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="40f18-117">Beschreibungen der verschiedenen URI-Typen.</span><span class="sxs-lookup"><span data-stu-id="40f18-117">Descriptions of the different URI types.</span></span> <span data-ttu-id="40f18-118">Die folgenden Werte sind bereits zugewiesen:</span><span class="sxs-lookup"><span data-stu-id="40f18-118">The following values are pre-assigned:</span></span> <br/>  <span data-ttu-id="40f18-119">1-Phone-URI</span><span class="sxs-lookup"><span data-stu-id="40f18-119">1 - Phone Uri</span></span> <br/>  <span data-ttu-id="40f18-120">0-Benutzer-URI</span><span class="sxs-lookup"><span data-stu-id="40f18-120">0 - User Uri</span></span> <br/> <br/>  <span data-ttu-id="40f18-121">Weitere mögliche Typen sind:</span><span class="sxs-lookup"><span data-stu-id="40f18-121">Other possible types include:</span></span> <br/><span data-ttu-id="40f18-122">conf:applicationsharing</span><span class="sxs-lookup"><span data-stu-id="40f18-122">conf:applicationsharing</span></span> <br/> <span data-ttu-id="40f18-123">conf:audio-video</span><span class="sxs-lookup"><span data-stu-id="40f18-123">conf:audio-video</span></span><br/> <span data-ttu-id="40f18-124">conf: Chat</span><span class="sxs-lookup"><span data-stu-id="40f18-124">conf:chat</span></span><br/>    <span data-ttu-id="40f18-125">conf:focus</span><span class="sxs-lookup"><span data-stu-id="40f18-125">conf:focus</span></span><br/>   <span data-ttu-id="40f18-126">MRAS</span><span class="sxs-lookup"><span data-stu-id="40f18-126">mras</span></span><br/>
