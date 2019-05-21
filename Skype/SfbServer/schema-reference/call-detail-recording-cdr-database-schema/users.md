---
title: Users-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: Die Tabelle Benutzer ist eine unterstützende Tabelle. Jeder Datensatz in der Tabelle speichert Informationen zu einem Benutzer an anrufen oder Sitzungen mit Datensätzen in der Datenbank.
ms.openlocfilehash: 0dcc2fda73305be2bbe6a7a5c546dac0b05f8273
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295699"
---
# <a name="users-table"></a><span data-ttu-id="9706a-104">Users-Tabelle</span><span class="sxs-lookup"><span data-stu-id="9706a-104">Users table</span></span>
 
<span data-ttu-id="9706a-105">Die Tabelle Benutzer ist eine unterstützende Tabelle.</span><span class="sxs-lookup"><span data-stu-id="9706a-105">The Users table is a supporting table.</span></span> <span data-ttu-id="9706a-106">Jeder Datensatz in der Tabelle speichert Informationen zu einem Benutzer an anrufen oder Sitzungen mit Datensätzen in der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="9706a-106">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>
  
|<span data-ttu-id="9706a-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="9706a-107">**Column**</span></span>|<span data-ttu-id="9706a-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="9706a-108">**Data Type**</span></span>|<span data-ttu-id="9706a-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="9706a-109">**Key/Index**</span></span>|<span data-ttu-id="9706a-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="9706a-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9706a-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="9706a-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="9706a-112">datetime</span><span class="sxs-lookup"><span data-stu-id="9706a-112">datetime</span></span>  <br/> ||<span data-ttu-id="9706a-113">Zeitstempel für die interne Verwendung.</span><span class="sxs-lookup"><span data-stu-id="9706a-113">Time stamp for internal use.</span></span>  <br/> |
|<span data-ttu-id="9706a-114">**UserID**</span><span class="sxs-lookup"><span data-stu-id="9706a-114">**UserId**</span></span> <br/> |<span data-ttu-id="9706a-115">int</span><span class="sxs-lookup"><span data-stu-id="9706a-115">int</span></span>  <br/> |<span data-ttu-id="9706a-116">Primary</span><span class="sxs-lookup"><span data-stu-id="9706a-116">Primary</span></span>  <br/> |<span data-ttu-id="9706a-117">Eindeutige Nummer, die diesen Benutzer kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="9706a-117">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="9706a-118">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="9706a-118">**UserUri**</span></span> <br/> |<span data-ttu-id="9706a-119">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9706a-119">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="9706a-120">Benutzer-URI.</span><span class="sxs-lookup"><span data-stu-id="9706a-120">User URI.</span></span>  <br/> |
|<span data-ttu-id="9706a-121">**Mandanten**</span><span class="sxs-lookup"><span data-stu-id="9706a-121">**TenantId**</span></span> <br/> |<span data-ttu-id="9706a-122">int</span><span class="sxs-lookup"><span data-stu-id="9706a-122">int</span></span>  <br/> |<span data-ttu-id="9706a-123">Fremd</span><span class="sxs-lookup"><span data-stu-id="9706a-123">Foreign</span></span>  <br/> |<span data-ttu-id="9706a-124">Die Mandanten-ID des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="9706a-124">This user's Tenant ID.</span></span> <span data-ttu-id="9706a-125">Weitere Informationen finden Sie in der [Tabelle Mandanten](tenants.md) .</span><span class="sxs-lookup"><span data-stu-id="9706a-125">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="9706a-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="9706a-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="9706a-127">int</span><span class="sxs-lookup"><span data-stu-id="9706a-127">int</span></span>  <br/> |<span data-ttu-id="9706a-128">Fremd</span><span class="sxs-lookup"><span data-stu-id="9706a-128">Foreign</span></span>  <br/> |<span data-ttu-id="9706a-129">Der URI-Typ des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="9706a-129">This user's URI type.</span></span> <span data-ttu-id="9706a-130">Weitere Informationen finden Sie in der [UriTypes-Tabelle](uritypes.md) .</span><span class="sxs-lookup"><span data-stu-id="9706a-130">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

