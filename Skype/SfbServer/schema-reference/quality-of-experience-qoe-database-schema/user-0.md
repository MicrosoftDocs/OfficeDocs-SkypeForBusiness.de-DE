---
title: User-Tabelle
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: Die Benutzer-Tabelle ist eine Tabelle, die eine Liste der verschiedenen Benutzer gespeichert, die in der Datenbank aufgezeichnet Sitzungen teilgenommen haben. Jeder Datensatz in der Tabelle steht für einen Benutzer.
ms.openlocfilehash: fcdc8682b86432613af79d5e4d2abbdb248fef0f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881674"
---
# <a name="user-table"></a><span data-ttu-id="d37c0-104">User-Tabelle</span><span class="sxs-lookup"><span data-stu-id="d37c0-104">User table</span></span>
 
<span data-ttu-id="d37c0-105">Die Benutzer-Tabelle ist eine Tabelle, die eine Liste der verschiedenen Benutzer gespeichert, die in der Datenbank aufgezeichnet Sitzungen teilgenommen haben.</span><span class="sxs-lookup"><span data-stu-id="d37c0-105">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database.</span></span> <span data-ttu-id="d37c0-106">Jeder Datensatz in der Tabelle steht für einen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="d37c0-106">Each record in the table represents one user.</span></span>
  
|<span data-ttu-id="d37c0-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="d37c0-107">**Column**</span></span>|<span data-ttu-id="d37c0-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="d37c0-108">**Data Type**</span></span>|<span data-ttu-id="d37c0-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="d37c0-109">**Key/Index**</span></span>|<span data-ttu-id="d37c0-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="d37c0-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d37c0-111">**UserKey**</span><span class="sxs-lookup"><span data-stu-id="d37c0-111">**UserKey**</span></span> <br/> |<span data-ttu-id="d37c0-112">int</span><span class="sxs-lookup"><span data-stu-id="d37c0-112">int</span></span>  <br/> |<span data-ttu-id="d37c0-113">Primary</span><span class="sxs-lookup"><span data-stu-id="d37c0-113">Primary</span></span>  <br/> |<span data-ttu-id="d37c0-114">Eindeutige Zahl, die diesen Benutzer identifiziert.</span><span class="sxs-lookup"><span data-stu-id="d37c0-114">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="d37c0-115">**URI**</span><span class="sxs-lookup"><span data-stu-id="d37c0-115">**URI**</span></span> <br/> |<span data-ttu-id="d37c0-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="d37c0-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="d37c0-117">Eindeutige</span><span class="sxs-lookup"><span data-stu-id="d37c0-117">Unique</span></span>  <br/> |<span data-ttu-id="d37c0-118">URI-Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="d37c0-118">URI string.</span></span>  <br/> |
|<span data-ttu-id="d37c0-119">**URIType**</span><span class="sxs-lookup"><span data-stu-id="d37c0-119">**URIType**</span></span> <br/> |<span data-ttu-id="d37c0-120">int</span><span class="sxs-lookup"><span data-stu-id="d37c0-120">int</span></span>  <br/> ||<span data-ttu-id="d37c0-121">1 ist Unbekannter URI-Typ.</span><span class="sxs-lookup"><span data-stu-id="d37c0-121">1 is unknown URI type.</span></span>  <br/> <span data-ttu-id="d37c0-122">2 ist der URI des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="d37c0-122">2 is user URI.</span></span>  <br/> <span data-ttu-id="d37c0-123">4 ist die Konferenz-URI.</span><span class="sxs-lookup"><span data-stu-id="d37c0-123">4 is conference URI.</span></span>  <br/> <span data-ttu-id="d37c0-124">8 ist Telefon-URI.</span><span class="sxs-lookup"><span data-stu-id="d37c0-124">8 is phone URI.</span></span>  <br/> |
|<span data-ttu-id="d37c0-125">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="d37c0-125">**TenantKey**</span></span> <br/> |<span data-ttu-id="d37c0-126">int</span><span class="sxs-lookup"><span data-stu-id="d37c0-126">int</span></span>  <br/> |<span data-ttu-id="d37c0-127">Ausländisch</span><span class="sxs-lookup"><span data-stu-id="d37c0-127">Foreign</span></span>  <br/> |<span data-ttu-id="d37c0-128">Mandant des Benutzers, verwiesen von Tenant-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="d37c0-128">Tenant of the user, referenced from tenant table.</span></span>  <br/> |
|<span data-ttu-id="d37c0-129">**LastPoorCallTime**</span><span class="sxs-lookup"><span data-stu-id="d37c0-129">**LastPoorCallTime**</span></span> <br/> |<span data-ttu-id="d37c0-130">datetime</span><span class="sxs-lookup"><span data-stu-id="d37c0-130">datetime</span></span>  <br/> ||<span data-ttu-id="d37c0-131">Letzter Zeitstempel, wenn der Benutzer einen Anruf mit schlechten Audioqualität hatte.</span><span class="sxs-lookup"><span data-stu-id="d37c0-131">Latest time stamp when the user had a poor audio call.</span></span>  <br/> |
|<span data-ttu-id="d37c0-132">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="d37c0-132">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="d37c0-133">datetime</span><span class="sxs-lookup"><span data-stu-id="d37c0-133">datetime</span></span>  <br/> ||<span data-ttu-id="d37c0-134">Nur zur internen Verwendung.</span><span class="sxs-lookup"><span data-stu-id="d37c0-134">For internal use only.</span></span>  <br/> |
   

