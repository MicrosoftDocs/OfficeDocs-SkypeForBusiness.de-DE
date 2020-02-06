---
title: tblADCookie
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
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: tblADCookie enthält die aktuellen LDAP-Synchronisierungs Cookies (Lightweight Directory Access Protocol).
ms.openlocfilehash: c9a4c666a5fe4a76ecb3685f60f1208ec3ea88ed
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814703"
---
# <a name="tbladcookie"></a><span data-ttu-id="a4a2e-103">tblADCookie</span><span class="sxs-lookup"><span data-stu-id="a4a2e-103">tblADCookie</span></span>
 
<span data-ttu-id="a4a2e-104">tblADCookie enthält die aktuellen LDAP-Synchronisierungs Cookies (Lightweight Directory Access Protocol).</span><span class="sxs-lookup"><span data-stu-id="a4a2e-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>
  
<span data-ttu-id="a4a2e-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="a4a2e-105">**Columns**</span></span>

|<span data-ttu-id="a4a2e-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="a4a2e-106">**Column**</span></span>|<span data-ttu-id="a4a2e-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="a4a2e-107">**Type**</span></span>|<span data-ttu-id="a4a2e-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="a4a2e-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a4a2e-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="a4a2e-109">prinGuid</span></span>  <br/> |<span data-ttu-id="a4a2e-110">GUID, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="a4a2e-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="a4a2e-111">Prinzipal-GUID der zu überwachenden Domäne.</span><span class="sxs-lookup"><span data-stu-id="a4a2e-111">Principal GUID of the domain being monitored.</span></span>  <br/> |
|<span data-ttu-id="a4a2e-112">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="a4a2e-112">prinDCHost</span></span>  <br/> |<span data-ttu-id="a4a2e-113">nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="a4a2e-113">nvarchar (255)</span></span>  <br/> |<span data-ttu-id="a4a2e-114">Vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des aktuellen Domänencontrollers, der für die Synchronisierung von Active Directory-Domänendiensten verwendet wird. Hat einen Informationswert.</span><span class="sxs-lookup"><span data-stu-id="a4a2e-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span>  <br/> |
|<span data-ttu-id="a4a2e-115">adcContent</span><span class="sxs-lookup"><span data-stu-id="a4a2e-115">adcContent</span></span>  <br/> |<span data-ttu-id="a4a2e-116">Bild (binär)</span><span class="sxs-lookup"><span data-stu-id="a4a2e-116">image (binary)</span></span>  <br/> |<span data-ttu-id="a4a2e-117">Active Directory-Synchronisierungs Cookie</span><span class="sxs-lookup"><span data-stu-id="a4a2e-117">Active Directory Sync cookie.</span></span>  <br/> |
|<span data-ttu-id="a4a2e-118">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="a4a2e-118">lastUpdated</span></span>  <br/> |<span data-ttu-id="a4a2e-119">datetime</span><span class="sxs-lookup"><span data-stu-id="a4a2e-119">datetime</span></span>  <br/> |<span data-ttu-id="a4a2e-120">Zeitstempel mit der Zeilen Aktualisierungszeit.</span><span class="sxs-lookup"><span data-stu-id="a4a2e-120">Time stamp with the row update time.</span></span>  <br/> |
|<span data-ttu-id="a4a2e-121">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="a4a2e-121">lockedUntil</span></span>  <br/> |<span data-ttu-id="a4a2e-122">datetime</span><span class="sxs-lookup"><span data-stu-id="a4a2e-122">datetime</span></span>  <br/> |<span data-ttu-id="a4a2e-123">Zeit, bis die Zeile für Änderungen gesperrt ist.</span><span class="sxs-lookup"><span data-stu-id="a4a2e-123">Time until the row is locked for changes.</span></span> <span data-ttu-id="a4a2e-124">Dies ist Teil eines Software-Interlock-Mechanismus, der sicherstellt, dass nur einer der Chat Dienste die Active Directory-Synchronisierung gleichzeitig durchführt.</span><span class="sxs-lookup"><span data-stu-id="a4a2e-124">This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span>  <br/> |
   
<span data-ttu-id="a4a2e-125">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="a4a2e-125">**Keys**</span></span>

|<span data-ttu-id="a4a2e-126">**Spalte (n)**</span><span class="sxs-lookup"><span data-stu-id="a4a2e-126">**Column(s)**</span></span>|<span data-ttu-id="a4a2e-127">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="a4a2e-127">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a4a2e-128">prinGuid</span><span class="sxs-lookup"><span data-stu-id="a4a2e-128">prinGuid</span></span>  <br/> |<span data-ttu-id="a4a2e-129">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="a4a2e-129">Primary key.</span></span>  <br/> |
|<span data-ttu-id="a4a2e-130">prinGuid</span><span class="sxs-lookup"><span data-stu-id="a4a2e-130">prinGuid</span></span>  <br/> |<span data-ttu-id="a4a2e-131">Fremdschlüssel mit Lookup in der Principal. prinGuid-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="a4a2e-131">Foreign key with lookup in Principal.prinGuid table.</span></span>  <br/> |
   

