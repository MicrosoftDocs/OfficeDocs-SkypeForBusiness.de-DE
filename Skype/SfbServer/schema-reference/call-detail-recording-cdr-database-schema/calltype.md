---
title: Tabelle "CallType" in Skype for Business Server 2015
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
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: Die CallType-Tabelle ist eine statische Tabelle, in der die Liste möglicher Anruftypen gespeichert ist.
ms.openlocfilehash: 294af58755e980200d75c899d6110322e2ff774d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815433"
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a><span data-ttu-id="9ee7c-103">Tabelle "CallType" in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="9ee7c-103">CallType table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="9ee7c-104">Die CallType-Tabelle ist eine statische Tabelle, in der die Liste möglicher Anruftypen gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="9ee7c-104">The CallType table is a static table that stores the list of possible call types.</span></span>
  
|<span data-ttu-id="9ee7c-105">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="9ee7c-105">**Column**</span></span>|<span data-ttu-id="9ee7c-106">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="9ee7c-106">**Data Type**</span></span>|<span data-ttu-id="9ee7c-107">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="9ee7c-107">**Key/Index**</span></span>|<span data-ttu-id="9ee7c-108">**Details**</span><span class="sxs-lookup"><span data-stu-id="9ee7c-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9ee7c-109">**CallTypeId**</span><span class="sxs-lookup"><span data-stu-id="9ee7c-109">**CallTypeId**</span></span> <br/> |<span data-ttu-id="9ee7c-110">int</span><span class="sxs-lookup"><span data-stu-id="9ee7c-110">int</span></span>  <br/> |<span data-ttu-id="9ee7c-111">Primary</span><span class="sxs-lookup"><span data-stu-id="9ee7c-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="9ee7c-112">**CallType**</span><span class="sxs-lookup"><span data-stu-id="9ee7c-112">**CallType**</span></span> <br/> |<span data-ttu-id="9ee7c-113">nvarchar</span><span class="sxs-lookup"><span data-stu-id="9ee7c-113">nvarchar</span></span>  <br/> || <span data-ttu-id="9ee7c-114">Zulässige Werte:</span><span class="sxs-lookup"><span data-stu-id="9ee7c-114">Allowed values:</span></span> <br/>  <span data-ttu-id="9ee7c-115">0-unbekannt</span><span class="sxs-lookup"><span data-stu-id="9ee7c-115">0 -- Unknown</span></span> <br/>  <span data-ttu-id="9ee7c-116">1 – Sofortnachrichten</span><span class="sxs-lookup"><span data-stu-id="9ee7c-116">1 - Instant Messaging</span></span> <br/>  <span data-ttu-id="9ee7c-117">2 – Anwendungsfreigabe</span><span class="sxs-lookup"><span data-stu-id="9ee7c-117">2 -- Application Sharing</span></span> <br/>  <span data-ttu-id="9ee7c-118">3-Audio</span><span class="sxs-lookup"><span data-stu-id="9ee7c-118">3 -- Audio</span></span> <br/>  <span data-ttu-id="9ee7c-119">4 – Audio und Video</span><span class="sxs-lookup"><span data-stu-id="9ee7c-119">4 - Audio and Video</span></span> <br/>  <span data-ttu-id="9ee7c-120">5-Dateiübertragung</span><span class="sxs-lookup"><span data-stu-id="9ee7c-120">5 - File Transfer</span></span> <br/> |
   

