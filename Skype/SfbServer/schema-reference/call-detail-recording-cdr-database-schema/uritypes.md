---
title: UriTypes-Tabelle
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: UriTypes-Tabelle sind die unterschiedlichen URI (Uniform Resource Identifier) Typen in Skype für Business Server 2015 überwacht.
ms.openlocfilehash: cb9c131901a322f9d22c8d29aa52a73dc27c9ea1
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212761"
---
# <a name="uritypes-table"></a><span data-ttu-id="af1ac-103">UriTypes-Tabelle</span><span class="sxs-lookup"><span data-stu-id="af1ac-103">UriTypes table</span></span>
 
<span data-ttu-id="af1ac-104">UriTypes-Tabelle sind die unterschiedlichen URI (Uniform Resource Identifier) Typen in Skype für Business Server 2015 überwacht.</span><span class="sxs-lookup"><span data-stu-id="af1ac-104">The UriTypes Table contains the different URI (Uniform resource identifier) types monitored in Skype for Business Server 2015.</span></span>

<span data-ttu-id="af1ac-105">Wenn der CDR-DB erstellt wird, werden zwei Datensätze zur Darstellung von PhoneUri und UserUri erstellt, und Einträge erstellt, die dynamisch UriTypeId zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="af1ac-105">When the CDR DB is created, two records to represent PhoneUri and UserUri are created, and records created after that are dynamically assigned UriTypeId.</span></span> 
  
|<span data-ttu-id="af1ac-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="af1ac-106">**Column**</span></span>|<span data-ttu-id="af1ac-107">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="af1ac-107">**Data Type**</span></span>|<span data-ttu-id="af1ac-108">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="af1ac-108">**Key/Index**</span></span>|<span data-ttu-id="af1ac-109">**Details**</span><span class="sxs-lookup"><span data-stu-id="af1ac-109">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="af1ac-110">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="af1ac-110">**UriTypeId**</span></span> <br/> |<span data-ttu-id="af1ac-111">tinyint</span><span class="sxs-lookup"><span data-stu-id="af1ac-111">tinyint</span></span>  <br/> |<span data-ttu-id="af1ac-112">Primary</span><span class="sxs-lookup"><span data-stu-id="af1ac-112">Primary</span></span>  <br/> |<span data-ttu-id="af1ac-113">Eindeutiger Bezeichner, einem URI-Typ zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="af1ac-113">Unique identifier assigned to a URI type.</span></span>  <br/> <span data-ttu-id="af1ac-114">Mögliche Werte - zwischen 0 und 255</span><span class="sxs-lookup"><span data-stu-id="af1ac-114">Possible values - 0 to 255</span></span> |
|<span data-ttu-id="af1ac-115">**UriType**</span><span class="sxs-lookup"><span data-stu-id="af1ac-115">**UriType**</span></span> <br/> |<span data-ttu-id="af1ac-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="af1ac-116">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="af1ac-117">Eine Beschreibung der verschiedenen URI.</span><span class="sxs-lookup"><span data-stu-id="af1ac-117">Descriptions of the different URI types.</span></span> <span data-ttu-id="af1ac-118">Die folgenden Werte sind zugeordnete:</span><span class="sxs-lookup"><span data-stu-id="af1ac-118">The following values are pre-assigned:</span></span> <br/>  <span data-ttu-id="af1ac-119">1 – Telefon-Uri</span><span class="sxs-lookup"><span data-stu-id="af1ac-119">1 - Phone Uri</span></span> <br/>  <span data-ttu-id="af1ac-120">0 - Benutzer-Uri</span><span class="sxs-lookup"><span data-stu-id="af1ac-120">0 - User Uri</span></span> <br/> <br/>  <span data-ttu-id="af1ac-121">Andere mögliche Typen sind:</span><span class="sxs-lookup"><span data-stu-id="af1ac-121">Other possible types include:</span></span> <br/><span data-ttu-id="af1ac-122">conf:applicationsharing</span><span class="sxs-lookup"><span data-stu-id="af1ac-122">conf:applicationsharing</span></span> <br/> <span data-ttu-id="af1ac-123">conf:audio-video</span><span class="sxs-lookup"><span data-stu-id="af1ac-123">conf:audio-video</span></span><br/> <span data-ttu-id="af1ac-124">conf:Chat</span><span class="sxs-lookup"><span data-stu-id="af1ac-124">conf:chat</span></span><br/>    <span data-ttu-id="af1ac-125">conf:focus</span><span class="sxs-lookup"><span data-stu-id="af1ac-125">conf:focus</span></span><br/>   <span data-ttu-id="af1ac-126">MRAS</span><span class="sxs-lookup"><span data-stu-id="af1ac-126">mras</span></span><br/>
