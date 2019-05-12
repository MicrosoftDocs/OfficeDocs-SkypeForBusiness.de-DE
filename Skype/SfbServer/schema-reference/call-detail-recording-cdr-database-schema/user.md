---
title: User-Ansicht
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: Die Ansicht des Benutzers speichert Informationen zu Benutzer wurden beteiligt anrufen und Sitzungen, die Datensätze in der Datenbank verfügen. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: f4e255f2de8dd087308ee46c64ef301cc0e9d390
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930078"
---
# <a name="user-view"></a><span data-ttu-id="c2ce3-104">User-Ansicht</span><span class="sxs-lookup"><span data-stu-id="c2ce3-104">User view</span></span>
 
<span data-ttu-id="c2ce3-105">Die Ansicht des Benutzers speichert Informationen zu Benutzer wurden beteiligt anrufen und Sitzungen, die Datensätze in der Datenbank verfügen.</span><span class="sxs-lookup"><span data-stu-id="c2ce3-105">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="c2ce3-106">Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="c2ce3-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="c2ce3-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="c2ce3-107">**Column**</span></span>|<span data-ttu-id="c2ce3-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="c2ce3-108">**Data Type**</span></span>|<span data-ttu-id="c2ce3-109">**Details**</span><span class="sxs-lookup"><span data-stu-id="c2ce3-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c2ce3-110">Benutzer-ID</span><span class="sxs-lookup"><span data-stu-id="c2ce3-110">UserId</span></span>  <br/> |<span data-ttu-id="c2ce3-111">int</span><span class="sxs-lookup"><span data-stu-id="c2ce3-111">int</span></span>  <br/> |<span data-ttu-id="c2ce3-112">Eindeutige Zahl, die diesen Benutzer identifiziert.</span><span class="sxs-lookup"><span data-stu-id="c2ce3-112">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="c2ce3-113">UserUri</span><span class="sxs-lookup"><span data-stu-id="c2ce3-113">UserUri</span></span>  <br/> |<span data-ttu-id="c2ce3-114">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="c2ce3-114">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="c2ce3-115">Der URI des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="c2ce3-115">Uri of the user.</span></span>  <br/> |
|<span data-ttu-id="c2ce3-116">TenantKey</span><span class="sxs-lookup"><span data-stu-id="c2ce3-116">TenantKey</span></span>  <br/> |<span data-ttu-id="c2ce3-117">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="c2ce3-117">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="c2ce3-118">Mandant des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="c2ce3-118">Tenant of user.</span></span> <span data-ttu-id="c2ce3-119">Finden Sie weitere Informationen der [Tenants-Tabelle](tenants.md) .</span><span class="sxs-lookup"><span data-stu-id="c2ce3-119">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="c2ce3-120">UriType</span><span class="sxs-lookup"><span data-stu-id="c2ce3-120">UriType</span></span>  <br/> |<span data-ttu-id="c2ce3-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c2ce3-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="c2ce3-122">Typ des Benutzer-URI.</span><span class="sxs-lookup"><span data-stu-id="c2ce3-122">Type of user URI.</span></span> <span data-ttu-id="c2ce3-123">Finden Sie weitere Informationen der [UriTypes-Tabelle](uritypes.md) .</span><span class="sxs-lookup"><span data-stu-id="c2ce3-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

