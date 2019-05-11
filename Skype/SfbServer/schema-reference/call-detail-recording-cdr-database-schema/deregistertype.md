---
title: DeRegisterType-Tabelle in Skype für Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: DeRegisterType-Tabelle handelt es sich um eine statische Tabelle, die die Liste der möglichen Benutzer speichert eine Aufhebung der Registrierung Typen, z. B. "vom Client initiierte", "Registrierung abgelaufen" oder "Client reagiert."
ms.openlocfilehash: 958de5dd537f391ca75936ad86a84cb6fed0778d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901173"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a><span data-ttu-id="75ac8-103">DeRegisterType-Tabelle in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="75ac8-103">DeRegisterType table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="75ac8-104">DeRegisterType-Tabelle handelt es sich um eine statische Tabelle, die die Liste der möglichen Benutzer speichert eine Aufhebung der Registrierung Typen, z. B. "vom Client initiierte", "Registrierung abgelaufen" oder "Client reagiert."</span><span class="sxs-lookup"><span data-stu-id="75ac8-104">The DeRegisterType table is a static table that stores the list of possible user de-registers types, such as 'client initiated', 'registration expired', or 'client stopped responding.'</span></span>
  
|<span data-ttu-id="75ac8-105">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="75ac8-105">**Column**</span></span>|<span data-ttu-id="75ac8-106">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="75ac8-106">**Data Type**</span></span>|<span data-ttu-id="75ac8-107">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="75ac8-107">**Key/Index**</span></span>|<span data-ttu-id="75ac8-108">**Details**</span><span class="sxs-lookup"><span data-stu-id="75ac8-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="75ac8-109">**DeRegisterTypeId**</span><span class="sxs-lookup"><span data-stu-id="75ac8-109">**DeRegisterTypeId**</span></span> <br/> |<span data-ttu-id="75ac8-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="75ac8-110">tinyint</span></span>  <br/> |<span data-ttu-id="75ac8-111">Primary</span><span class="sxs-lookup"><span data-stu-id="75ac8-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="75ac8-112">**DeRegisterReason**</span><span class="sxs-lookup"><span data-stu-id="75ac8-112">**DeRegisterReason**</span></span> <br/> |<span data-ttu-id="75ac8-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="75ac8-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="75ac8-114">Zulässige Werte:</span><span class="sxs-lookup"><span data-stu-id="75ac8-114">Allowed values:</span></span> <br/>  <span data-ttu-id="75ac8-115">0 – unbekannt</span><span class="sxs-lookup"><span data-stu-id="75ac8-115">0 -- Unknown</span></span> <br/>  <span data-ttu-id="75ac8-116">1 – der Client initiiert die Registrierung aufgehoben</span><span class="sxs-lookup"><span data-stu-id="75ac8-116">1 -- Client Initiated Deregistration</span></span> <br/>  <span data-ttu-id="75ac8-117">2--Registrierung abgelaufen</span><span class="sxs-lookup"><span data-stu-id="75ac8-117">2 -- Registration Expired</span></span> <br/>  <span data-ttu-id="75ac8-118">3 – Clientabsturz</span><span class="sxs-lookup"><span data-stu-id="75ac8-118">3 - Client crashed</span></span> <br/>  <span data-ttu-id="75ac8-119">4--Benutzerattribute geändert</span><span class="sxs-lookup"><span data-stu-id="75ac8-119">4 -- User Attributes Changed</span></span> <br/>  <span data-ttu-id="75ac8-120">5 – bevorzugte Registrierungsstelle geändert</span><span class="sxs-lookup"><span data-stu-id="75ac8-120">5 - Preferred Registrar Changed</span></span> <br/>  <span data-ttu-id="75ac8-121">6--Legacyclient In Survival Mode</span><span class="sxs-lookup"><span data-stu-id="75ac8-121">6 -- Legacy Client In Survival Mode</span></span> <br/> |
   

