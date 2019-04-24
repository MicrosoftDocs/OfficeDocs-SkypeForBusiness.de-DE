---
title: DeRegisterType-Tabelle in Skype für Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: DeRegisterType-Tabelle handelt es sich um eine statische Tabelle, die die Liste der möglichen Benutzer speichert eine Aufhebung der Registrierung Typen, z. B. "vom Client initiierte", "Registrierung abgelaufen" oder "Client reagiert."
ms.openlocfilehash: be6fd10388c9f85315554605fd491aafa9d3a0d0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213193"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a><span data-ttu-id="23a15-103">DeRegisterType-Tabelle in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="23a15-103">DeRegisterType table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="23a15-104">DeRegisterType-Tabelle handelt es sich um eine statische Tabelle, die die Liste der möglichen Benutzer speichert eine Aufhebung der Registrierung Typen, z. B. "vom Client initiierte", "Registrierung abgelaufen" oder "Client reagiert."</span><span class="sxs-lookup"><span data-stu-id="23a15-104">The DeRegisterType table is a static table that stores the list of possible user de-registers types, such as 'client initiated', 'registration expired', or 'client stopped responding.'</span></span>
  
|<span data-ttu-id="23a15-105">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="23a15-105">**Column**</span></span>|<span data-ttu-id="23a15-106">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="23a15-106">**Data Type**</span></span>|<span data-ttu-id="23a15-107">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="23a15-107">**Key/Index**</span></span>|<span data-ttu-id="23a15-108">**Details**</span><span class="sxs-lookup"><span data-stu-id="23a15-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="23a15-109">**DeRegisterTypeId**</span><span class="sxs-lookup"><span data-stu-id="23a15-109">**DeRegisterTypeId**</span></span> <br/> |<span data-ttu-id="23a15-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="23a15-110">tinyint</span></span>  <br/> |<span data-ttu-id="23a15-111">Primary</span><span class="sxs-lookup"><span data-stu-id="23a15-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="23a15-112">**DeRegisterReason**</span><span class="sxs-lookup"><span data-stu-id="23a15-112">**DeRegisterReason**</span></span> <br/> |<span data-ttu-id="23a15-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="23a15-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="23a15-114">Zulässige Werte:</span><span class="sxs-lookup"><span data-stu-id="23a15-114">Allowed values:</span></span> <br/>  <span data-ttu-id="23a15-115">0 – unbekannt</span><span class="sxs-lookup"><span data-stu-id="23a15-115">0 -- Unknown</span></span> <br/>  <span data-ttu-id="23a15-116">1 – der Client initiiert die Registrierung aufgehoben</span><span class="sxs-lookup"><span data-stu-id="23a15-116">1 -- Client Initiated Deregistration</span></span> <br/>  <span data-ttu-id="23a15-117">2--Registrierung abgelaufen</span><span class="sxs-lookup"><span data-stu-id="23a15-117">2 -- Registration Expired</span></span> <br/>  <span data-ttu-id="23a15-118">3 – Clientabsturz</span><span class="sxs-lookup"><span data-stu-id="23a15-118">3 - Client crashed</span></span> <br/>  <span data-ttu-id="23a15-119">4--Benutzerattribute geändert</span><span class="sxs-lookup"><span data-stu-id="23a15-119">4 -- User Attributes Changed</span></span> <br/>  <span data-ttu-id="23a15-120">5 – bevorzugte Registrierungsstelle geändert</span><span class="sxs-lookup"><span data-stu-id="23a15-120">5 - Preferred Registrar Changed</span></span> <br/>  <span data-ttu-id="23a15-121">6--Legacyclient In Survival Mode</span><span class="sxs-lookup"><span data-stu-id="23a15-121">6 -- Legacy Client In Survival Mode</span></span> <br/> |
   

