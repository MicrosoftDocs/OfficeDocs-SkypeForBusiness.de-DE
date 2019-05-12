---
title: Users-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: Die Benutzer-Tabelle ist eine Tabelle. Jeder Datensatz in der Tabelle speichert Informationen zu einem Benutzer Beteiligten in anrufen und Sitzungen, die Datensätze in der Datenbank verfügen.
ms.openlocfilehash: fbe3ff7d2570f78cdf3b3418629fb9fd6209d944
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929987"
---
# <a name="users-table"></a><span data-ttu-id="03762-104">Users-Tabelle</span><span class="sxs-lookup"><span data-stu-id="03762-104">Users table</span></span>
 
<span data-ttu-id="03762-105">Die Benutzer-Tabelle ist eine Tabelle.</span><span class="sxs-lookup"><span data-stu-id="03762-105">The Users table is a supporting table.</span></span> <span data-ttu-id="03762-106">Jeder Datensatz in der Tabelle speichert Informationen zu einem Benutzer Beteiligten in anrufen und Sitzungen, die Datensätze in der Datenbank verfügen.</span><span class="sxs-lookup"><span data-stu-id="03762-106">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>
  
|<span data-ttu-id="03762-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="03762-107">**Column**</span></span>|<span data-ttu-id="03762-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="03762-108">**Data Type**</span></span>|<span data-ttu-id="03762-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="03762-109">**Key/Index**</span></span>|<span data-ttu-id="03762-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="03762-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="03762-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="03762-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="03762-112">datetime</span><span class="sxs-lookup"><span data-stu-id="03762-112">datetime</span></span>  <br/> ||<span data-ttu-id="03762-113">Zeitstempel für die interne Verwendung.</span><span class="sxs-lookup"><span data-stu-id="03762-113">Time stamp for internal use.</span></span>  <br/> |
|<span data-ttu-id="03762-114">**Benutzer-ID**</span><span class="sxs-lookup"><span data-stu-id="03762-114">**UserId**</span></span> <br/> |<span data-ttu-id="03762-115">int</span><span class="sxs-lookup"><span data-stu-id="03762-115">int</span></span>  <br/> |<span data-ttu-id="03762-116">Primary</span><span class="sxs-lookup"><span data-stu-id="03762-116">Primary</span></span>  <br/> |<span data-ttu-id="03762-117">Eindeutige Zahl, die diesen Benutzer identifiziert.</span><span class="sxs-lookup"><span data-stu-id="03762-117">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="03762-118">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="03762-118">**UserUri**</span></span> <br/> |<span data-ttu-id="03762-119">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="03762-119">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="03762-120">Der URI des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="03762-120">User URI.</span></span>  <br/> |
|<span data-ttu-id="03762-121">**TenantId**</span><span class="sxs-lookup"><span data-stu-id="03762-121">**TenantId**</span></span> <br/> |<span data-ttu-id="03762-122">int</span><span class="sxs-lookup"><span data-stu-id="03762-122">int</span></span>  <br/> |<span data-ttu-id="03762-123">Ausländisch</span><span class="sxs-lookup"><span data-stu-id="03762-123">Foreign</span></span>  <br/> |<span data-ttu-id="03762-124">Mandanten-ID des Benutzers</span><span class="sxs-lookup"><span data-stu-id="03762-124">This user's Tenant ID.</span></span> <span data-ttu-id="03762-125">Finden Sie weitere Informationen der [Tenants-Tabelle](tenants.md) .</span><span class="sxs-lookup"><span data-stu-id="03762-125">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="03762-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="03762-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="03762-127">int</span><span class="sxs-lookup"><span data-stu-id="03762-127">int</span></span>  <br/> |<span data-ttu-id="03762-128">Ausländisch</span><span class="sxs-lookup"><span data-stu-id="03762-128">Foreign</span></span>  <br/> |<span data-ttu-id="03762-129">URI-Typ des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="03762-129">This user's URI type.</span></span> <span data-ttu-id="03762-130">Finden Sie weitere Informationen der [UriTypes-Tabelle](uritypes.md) .</span><span class="sxs-lookup"><span data-stu-id="03762-130">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

