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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: Die Tabelle Benutzer ist eine unterstützende Tabelle. Jeder Datensatz in der Tabelle speichert Informationen zu einem Benutzer an anrufen oder Sitzungen mit Datensätzen in der Datenbank.
ms.openlocfilehash: 21d03dc2214ac74188094c10a7b53ec84b8a51a9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814803"
---
# <a name="users-table"></a><span data-ttu-id="71478-104">Users-Tabelle</span><span class="sxs-lookup"><span data-stu-id="71478-104">Users table</span></span>
 
<span data-ttu-id="71478-105">Die Tabelle Benutzer ist eine unterstützende Tabelle.</span><span class="sxs-lookup"><span data-stu-id="71478-105">The Users table is a supporting table.</span></span> <span data-ttu-id="71478-106">Jeder Datensatz in der Tabelle speichert Informationen zu einem Benutzer an anrufen oder Sitzungen mit Datensätzen in der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="71478-106">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>
  
|<span data-ttu-id="71478-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="71478-107">**Column**</span></span>|<span data-ttu-id="71478-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="71478-108">**Data Type**</span></span>|<span data-ttu-id="71478-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="71478-109">**Key/Index**</span></span>|<span data-ttu-id="71478-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="71478-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="71478-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="71478-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="71478-112">datetime</span><span class="sxs-lookup"><span data-stu-id="71478-112">datetime</span></span>  <br/> ||<span data-ttu-id="71478-113">Zeitstempel für die interne Verwendung.</span><span class="sxs-lookup"><span data-stu-id="71478-113">Time stamp for internal use.</span></span>  <br/> |
|<span data-ttu-id="71478-114">**UserID**</span><span class="sxs-lookup"><span data-stu-id="71478-114">**UserId**</span></span> <br/> |<span data-ttu-id="71478-115">int</span><span class="sxs-lookup"><span data-stu-id="71478-115">int</span></span>  <br/> |<span data-ttu-id="71478-116">Primary</span><span class="sxs-lookup"><span data-stu-id="71478-116">Primary</span></span>  <br/> |<span data-ttu-id="71478-117">Eindeutige Nummer, die diesen Benutzer kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="71478-117">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="71478-118">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="71478-118">**UserUri**</span></span> <br/> |<span data-ttu-id="71478-119">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="71478-119">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="71478-120">Benutzer-URI.</span><span class="sxs-lookup"><span data-stu-id="71478-120">User URI.</span></span>  <br/> |
|<span data-ttu-id="71478-121">**Mandanten**</span><span class="sxs-lookup"><span data-stu-id="71478-121">**TenantId**</span></span> <br/> |<span data-ttu-id="71478-122">int</span><span class="sxs-lookup"><span data-stu-id="71478-122">int</span></span>  <br/> |<span data-ttu-id="71478-123">Fremd</span><span class="sxs-lookup"><span data-stu-id="71478-123">Foreign</span></span>  <br/> |<span data-ttu-id="71478-124">Die Mandanten-ID des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="71478-124">This user's Tenant ID.</span></span> <span data-ttu-id="71478-125">Weitere Informationen finden Sie in der [Tabelle Mandanten](tenants.md) .</span><span class="sxs-lookup"><span data-stu-id="71478-125">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="71478-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="71478-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="71478-127">int</span><span class="sxs-lookup"><span data-stu-id="71478-127">int</span></span>  <br/> |<span data-ttu-id="71478-128">Fremd</span><span class="sxs-lookup"><span data-stu-id="71478-128">Foreign</span></span>  <br/> |<span data-ttu-id="71478-129">Der URI-Typ des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="71478-129">This user's URI type.</span></span> <span data-ttu-id="71478-130">Weitere Informationen finden Sie in der [UriTypes-Tabelle](uritypes.md) .</span><span class="sxs-lookup"><span data-stu-id="71478-130">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

