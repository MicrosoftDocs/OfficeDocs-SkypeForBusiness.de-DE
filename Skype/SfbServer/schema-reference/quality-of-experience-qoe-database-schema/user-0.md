---
title: User-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: Die Tabelle Benutzer ist eine unterstützende Tabelle, in der eine Liste der verschiedenen Benutzer gespeichert ist, die an Sitzungen teilgenommen haben, die in der Datenbank aufgezeichnet wurden. Jeder Datensatz in der Tabelle steht für einen Benutzer.
ms.openlocfilehash: a9f72793d3b287406b1b3b7e1ad360e7f5abc598
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294614"
---
# <a name="user-table"></a><span data-ttu-id="c201b-104">User-Tabelle</span><span class="sxs-lookup"><span data-stu-id="c201b-104">User table</span></span>
 
<span data-ttu-id="c201b-105">Die Tabelle Benutzer ist eine unterstützende Tabelle, in der eine Liste der verschiedenen Benutzer gespeichert ist, die an Sitzungen teilgenommen haben, die in der Datenbank aufgezeichnet wurden.</span><span class="sxs-lookup"><span data-stu-id="c201b-105">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database.</span></span> <span data-ttu-id="c201b-106">Jeder Datensatz in der Tabelle steht für einen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="c201b-106">Each record in the table represents one user.</span></span>
  
|<span data-ttu-id="c201b-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="c201b-107">**Column**</span></span>|<span data-ttu-id="c201b-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="c201b-108">**Data Type**</span></span>|<span data-ttu-id="c201b-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="c201b-109">**Key/Index**</span></span>|<span data-ttu-id="c201b-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="c201b-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c201b-111">**UserKey**</span><span class="sxs-lookup"><span data-stu-id="c201b-111">**UserKey**</span></span> <br/> |<span data-ttu-id="c201b-112">int</span><span class="sxs-lookup"><span data-stu-id="c201b-112">int</span></span>  <br/> |<span data-ttu-id="c201b-113">Primary</span><span class="sxs-lookup"><span data-stu-id="c201b-113">Primary</span></span>  <br/> |<span data-ttu-id="c201b-114">Eindeutige Nummer, die diesen Benutzer kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="c201b-114">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="c201b-115">**URI**</span><span class="sxs-lookup"><span data-stu-id="c201b-115">**URI**</span></span> <br/> |<span data-ttu-id="c201b-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c201b-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="c201b-117">Eindeutigen</span><span class="sxs-lookup"><span data-stu-id="c201b-117">Unique</span></span>  <br/> |<span data-ttu-id="c201b-118">URI-Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="c201b-118">URI string.</span></span>  <br/> |
|<span data-ttu-id="c201b-119">**URIType**</span><span class="sxs-lookup"><span data-stu-id="c201b-119">**URIType**</span></span> <br/> |<span data-ttu-id="c201b-120">int</span><span class="sxs-lookup"><span data-stu-id="c201b-120">int</span></span>  <br/> ||<span data-ttu-id="c201b-121">1 ist ein Unbekannter URI-Typ.</span><span class="sxs-lookup"><span data-stu-id="c201b-121">1 is unknown URI type.</span></span>  <br/> <span data-ttu-id="c201b-122">2 ist ein Benutzer-URI.</span><span class="sxs-lookup"><span data-stu-id="c201b-122">2 is user URI.</span></span>  <br/> <span data-ttu-id="c201b-123">4 ist Konferenz-URI.</span><span class="sxs-lookup"><span data-stu-id="c201b-123">4 is conference URI.</span></span>  <br/> <span data-ttu-id="c201b-124">8 ist ein Telefon-URI.</span><span class="sxs-lookup"><span data-stu-id="c201b-124">8 is phone URI.</span></span>  <br/> |
|<span data-ttu-id="c201b-125">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="c201b-125">**TenantKey**</span></span> <br/> |<span data-ttu-id="c201b-126">int</span><span class="sxs-lookup"><span data-stu-id="c201b-126">int</span></span>  <br/> |<span data-ttu-id="c201b-127">Fremd</span><span class="sxs-lookup"><span data-stu-id="c201b-127">Foreign</span></span>  <br/> |<span data-ttu-id="c201b-128">Der Mandant des Benutzers, auf den die Mandantentabelle verweist.</span><span class="sxs-lookup"><span data-stu-id="c201b-128">Tenant of the user, referenced from tenant table.</span></span>  <br/> |
|<span data-ttu-id="c201b-129">**LastPoorCallTime**</span><span class="sxs-lookup"><span data-stu-id="c201b-129">**LastPoorCallTime**</span></span> <br/> |<span data-ttu-id="c201b-130">datetime</span><span class="sxs-lookup"><span data-stu-id="c201b-130">datetime</span></span>  <br/> ||<span data-ttu-id="c201b-131">Letzter Zeitstempel, wenn der Benutzer einen schlechten Audioanruf hatte.</span><span class="sxs-lookup"><span data-stu-id="c201b-131">Latest time stamp when the user had a poor audio call.</span></span>  <br/> |
|<span data-ttu-id="c201b-132">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="c201b-132">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="c201b-133">datetime</span><span class="sxs-lookup"><span data-stu-id="c201b-133">datetime</span></span>  <br/> ||<span data-ttu-id="c201b-134">Nur für interne Verwendung.</span><span class="sxs-lookup"><span data-stu-id="c201b-134">For internal use only.</span></span>  <br/> |
   

