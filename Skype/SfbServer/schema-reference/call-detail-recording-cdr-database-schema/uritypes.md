---
title: UriTypes-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: UriTypes-Tabelle sind die unterschiedlichen URI (Uniform Resource Identifier) Typen in Skype für Business Server 2015 überwacht.
ms.openlocfilehash: 72704715ff5e5fd3a354b75b0aa6baff45ecea54
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930269"
---
# <a name="uritypes-table"></a><span data-ttu-id="88bca-103">UriTypes-Tabelle</span><span class="sxs-lookup"><span data-stu-id="88bca-103">UriTypes table</span></span>
 
<span data-ttu-id="88bca-104">UriTypes-Tabelle sind die unterschiedlichen URI (Uniform Resource Identifier) Typen in Skype für Business Server 2015 überwacht.</span><span class="sxs-lookup"><span data-stu-id="88bca-104">The UriTypes Table contains the different URI (Uniform resource identifier) types monitored in Skype for Business Server 2015.</span></span>

<span data-ttu-id="88bca-105">Wenn der CDR-DB erstellt wird, werden zwei Datensätze zur Darstellung von PhoneUri und UserUri erstellt, und Einträge erstellt, die dynamisch UriTypeId zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="88bca-105">When the CDR DB is created, two records to represent PhoneUri and UserUri are created, and records created after that are dynamically assigned UriTypeId.</span></span> 
  
|<span data-ttu-id="88bca-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="88bca-106">**Column**</span></span>|<span data-ttu-id="88bca-107">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="88bca-107">**Data Type**</span></span>|<span data-ttu-id="88bca-108">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="88bca-108">**Key/Index**</span></span>|<span data-ttu-id="88bca-109">**Details**</span><span class="sxs-lookup"><span data-stu-id="88bca-109">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="88bca-110">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="88bca-110">**UriTypeId**</span></span> <br/> |<span data-ttu-id="88bca-111">tinyint</span><span class="sxs-lookup"><span data-stu-id="88bca-111">tinyint</span></span>  <br/> |<span data-ttu-id="88bca-112">Primary</span><span class="sxs-lookup"><span data-stu-id="88bca-112">Primary</span></span>  <br/> |<span data-ttu-id="88bca-113">Eindeutiger Bezeichner, einem URI-Typ zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="88bca-113">Unique identifier assigned to a URI type.</span></span>  <br/> <span data-ttu-id="88bca-114">Mögliche Werte - zwischen 0 und 255</span><span class="sxs-lookup"><span data-stu-id="88bca-114">Possible values - 0 to 255</span></span> |
|<span data-ttu-id="88bca-115">**UriType**</span><span class="sxs-lookup"><span data-stu-id="88bca-115">**UriType**</span></span> <br/> |<span data-ttu-id="88bca-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="88bca-116">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="88bca-117">Eine Beschreibung der verschiedenen URI.</span><span class="sxs-lookup"><span data-stu-id="88bca-117">Descriptions of the different URI types.</span></span> <span data-ttu-id="88bca-118">Die folgenden Werte sind zugeordnete:</span><span class="sxs-lookup"><span data-stu-id="88bca-118">The following values are pre-assigned:</span></span> <br/>  <span data-ttu-id="88bca-119">1 – Telefon-Uri</span><span class="sxs-lookup"><span data-stu-id="88bca-119">1 - Phone Uri</span></span> <br/>  <span data-ttu-id="88bca-120">0 - Benutzer-Uri</span><span class="sxs-lookup"><span data-stu-id="88bca-120">0 - User Uri</span></span> <br/> <br/>  <span data-ttu-id="88bca-121">Andere mögliche Typen sind:</span><span class="sxs-lookup"><span data-stu-id="88bca-121">Other possible types include:</span></span> <br/><span data-ttu-id="88bca-122">conf:applicationsharing</span><span class="sxs-lookup"><span data-stu-id="88bca-122">conf:applicationsharing</span></span> <br/> <span data-ttu-id="88bca-123">conf:audio-video</span><span class="sxs-lookup"><span data-stu-id="88bca-123">conf:audio-video</span></span><br/> <span data-ttu-id="88bca-124">conf:Chat</span><span class="sxs-lookup"><span data-stu-id="88bca-124">conf:chat</span></span><br/>    <span data-ttu-id="88bca-125">conf:focus</span><span class="sxs-lookup"><span data-stu-id="88bca-125">conf:focus</span></span><br/>   <span data-ttu-id="88bca-126">MRAS</span><span class="sxs-lookup"><span data-stu-id="88bca-126">mras</span></span><br/>
