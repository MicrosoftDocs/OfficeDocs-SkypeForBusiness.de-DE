---
title: Tabelle "deregistertype" in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: Die Tabelle "deregistertype" ist eine statische Tabelle, in der die Liste der möglichen Benutzer deregister-Typen wie "Client initiiert", "Registrierung abgelaufen" oder "Client reagiert nicht mehr" gespeichert ist.
ms.openlocfilehash: 794f8f98ffe20cd69b63fd2084fee38ed055d40f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296350"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a><span data-ttu-id="41386-103">Tabelle "deregistertype" in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="41386-103">DeRegisterType table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="41386-104">Die Tabelle "deregistertype" ist eine statische Tabelle, in der die Liste der möglichen Benutzer deregister-Typen wie "Client initiiert", "Registrierung abgelaufen" oder "Client reagiert nicht mehr" gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="41386-104">The DeRegisterType table is a static table that stores the list of possible user de-registers types, such as 'client initiated', 'registration expired', or 'client stopped responding.'</span></span>
  
|<span data-ttu-id="41386-105">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="41386-105">**Column**</span></span>|<span data-ttu-id="41386-106">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="41386-106">**Data Type**</span></span>|<span data-ttu-id="41386-107">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="41386-107">**Key/Index**</span></span>|<span data-ttu-id="41386-108">**Details**</span><span class="sxs-lookup"><span data-stu-id="41386-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="41386-109">**DeRegisterTypeId**</span><span class="sxs-lookup"><span data-stu-id="41386-109">**DeRegisterTypeId**</span></span> <br/> |<span data-ttu-id="41386-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="41386-110">tinyint</span></span>  <br/> |<span data-ttu-id="41386-111">Primary</span><span class="sxs-lookup"><span data-stu-id="41386-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="41386-112">**DeRegisterReason**</span><span class="sxs-lookup"><span data-stu-id="41386-112">**DeRegisterReason**</span></span> <br/> |<span data-ttu-id="41386-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="41386-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="41386-114">Zulässige Werte:</span><span class="sxs-lookup"><span data-stu-id="41386-114">Allowed values:</span></span> <br/>  <span data-ttu-id="41386-115">0-unbekannt</span><span class="sxs-lookup"><span data-stu-id="41386-115">0 -- Unknown</span></span> <br/>  <span data-ttu-id="41386-116">1-Client initiierte Deregistrierung</span><span class="sxs-lookup"><span data-stu-id="41386-116">1 -- Client Initiated Deregistration</span></span> <br/>  <span data-ttu-id="41386-117">2 – Registrierung abgelaufen</span><span class="sxs-lookup"><span data-stu-id="41386-117">2 -- Registration Expired</span></span> <br/>  <span data-ttu-id="41386-118">3-Client stürzte ab</span><span class="sxs-lookup"><span data-stu-id="41386-118">3 - Client crashed</span></span> <br/>  <span data-ttu-id="41386-119">4 – Benutzerattribute geändert</span><span class="sxs-lookup"><span data-stu-id="41386-119">4 -- User Attributes Changed</span></span> <br/>  <span data-ttu-id="41386-120">5-bevorzugte Registrierungsstelle geändert</span><span class="sxs-lookup"><span data-stu-id="41386-120">5 - Preferred Registrar Changed</span></span> <br/>  <span data-ttu-id="41386-121">6 – Legacy-Client im Survival-Modus</span><span class="sxs-lookup"><span data-stu-id="41386-121">6 -- Legacy Client In Survival Mode</span></span> <br/> |
   

