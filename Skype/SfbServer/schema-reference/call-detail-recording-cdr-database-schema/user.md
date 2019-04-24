---
title: User-Ansicht
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: Die Ansicht des Benutzers speichert Informationen zu Benutzer wurden beteiligt anrufen und Sitzungen, die Datensätze in der Datenbank verfügen. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: 9e631c101660e8f14bca25f019f5d991a0d9aadd
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213179"
---
# <a name="user-view"></a><span data-ttu-id="375c6-104">User-Ansicht</span><span class="sxs-lookup"><span data-stu-id="375c6-104">User view</span></span>
 
<span data-ttu-id="375c6-105">Die Ansicht des Benutzers speichert Informationen zu Benutzer wurden beteiligt anrufen und Sitzungen, die Datensätze in der Datenbank verfügen.</span><span class="sxs-lookup"><span data-stu-id="375c6-105">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="375c6-106">Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="375c6-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="375c6-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="375c6-107">**Column**</span></span>|<span data-ttu-id="375c6-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="375c6-108">**Data Type**</span></span>|<span data-ttu-id="375c6-109">**Details**</span><span class="sxs-lookup"><span data-stu-id="375c6-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="375c6-110">Benutzer-ID</span><span class="sxs-lookup"><span data-stu-id="375c6-110">UserId</span></span>  <br/> |<span data-ttu-id="375c6-111">int</span><span class="sxs-lookup"><span data-stu-id="375c6-111">int</span></span>  <br/> |<span data-ttu-id="375c6-112">Eindeutige Zahl, die diesen Benutzer identifiziert.</span><span class="sxs-lookup"><span data-stu-id="375c6-112">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="375c6-113">UserUri</span><span class="sxs-lookup"><span data-stu-id="375c6-113">UserUri</span></span>  <br/> |<span data-ttu-id="375c6-114">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="375c6-114">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="375c6-115">Der URI des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="375c6-115">Uri of the user.</span></span>  <br/> |
|<span data-ttu-id="375c6-116">TenantKey</span><span class="sxs-lookup"><span data-stu-id="375c6-116">TenantKey</span></span>  <br/> |<span data-ttu-id="375c6-117">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="375c6-117">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="375c6-118">Mandant des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="375c6-118">Tenant of user.</span></span> <span data-ttu-id="375c6-119">Finden Sie weitere Informationen der [Tenants-Tabelle](tenants.md) .</span><span class="sxs-lookup"><span data-stu-id="375c6-119">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="375c6-120">UriType</span><span class="sxs-lookup"><span data-stu-id="375c6-120">UriType</span></span>  <br/> |<span data-ttu-id="375c6-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="375c6-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="375c6-122">Typ des Benutzer-URI.</span><span class="sxs-lookup"><span data-stu-id="375c6-122">Type of user URI.</span></span> <span data-ttu-id="375c6-123">Finden Sie weitere Informationen der [UriTypes-Tabelle](uritypes.md) .</span><span class="sxs-lookup"><span data-stu-id="375c6-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

