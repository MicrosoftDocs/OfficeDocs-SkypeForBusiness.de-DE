---
title: tblADCookie
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: "\"tbladcookie\" enthält die aktuellen Cookies Synchronisierung Lightweight Directory Access Protocol (LDAP)."
ms.openlocfilehash: 3e7eeeeae6623bbbb308f4e05c4ab8a4b9a7be50
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213158"
---
# <a name="tbladcookie"></a><span data-ttu-id="15910-103">tblADCookie</span><span class="sxs-lookup"><span data-stu-id="15910-103">tblADCookie</span></span>
 
<span data-ttu-id="15910-104">"tbladcookie" enthält die aktuellen Cookies Synchronisierung Lightweight Directory Access Protocol (LDAP).</span><span class="sxs-lookup"><span data-stu-id="15910-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>
  
<span data-ttu-id="15910-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="15910-105">**Columns**</span></span>

|<span data-ttu-id="15910-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="15910-106">**Column**</span></span>|<span data-ttu-id="15910-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="15910-107">**Type**</span></span>|<span data-ttu-id="15910-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="15910-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="15910-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="15910-109">prinGuid</span></span>  <br/> |<span data-ttu-id="15910-110">GUID, nicht null</span><span class="sxs-lookup"><span data-stu-id="15910-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="15910-111">Prinzipal-GUID der überwachten Domäne.</span><span class="sxs-lookup"><span data-stu-id="15910-111">Principal GUID of the domain being monitored.</span></span>  <br/> |
|<span data-ttu-id="15910-112">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="15910-112">prinDCHost</span></span>  <br/> |<span data-ttu-id="15910-113">Nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="15910-113">nvarchar (255)</span></span>  <br/> |<span data-ttu-id="15910-114">Vollqualifizierter Domänenname (FQDN) des aktuellen Domänencontrollers für Active Directory Domain Services Sync verwendet. Informative Wert hat.</span><span class="sxs-lookup"><span data-stu-id="15910-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span>  <br/> |
|<span data-ttu-id="15910-115">adcContent</span><span class="sxs-lookup"><span data-stu-id="15910-115">adcContent</span></span>  <br/> |<span data-ttu-id="15910-116">Bild (binär)</span><span class="sxs-lookup"><span data-stu-id="15910-116">image (binary)</span></span>  <br/> |<span data-ttu-id="15910-117">Active Directory-Synchronisierung Cookie.</span><span class="sxs-lookup"><span data-stu-id="15910-117">Active Directory Sync cookie.</span></span>  <br/> |
|<span data-ttu-id="15910-118">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="15910-118">lastUpdated</span></span>  <br/> |<span data-ttu-id="15910-119">datetime</span><span class="sxs-lookup"><span data-stu-id="15910-119">datetime</span></span>  <br/> |<span data-ttu-id="15910-120">Zeitstempel mit Aktualisierungszeit der Zeile.</span><span class="sxs-lookup"><span data-stu-id="15910-120">Time stamp with the row update time.</span></span>  <br/> |
|<span data-ttu-id="15910-121">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="15910-121">lockedUntil</span></span>  <br/> |<span data-ttu-id="15910-122">datetime</span><span class="sxs-lookup"><span data-stu-id="15910-122">datetime</span></span>  <br/> |<span data-ttu-id="15910-123">Zeitpunkt, bis die Zeile für Änderungen gesperrt ist.</span><span class="sxs-lookup"><span data-stu-id="15910-123">Time until the row is locked for changes.</span></span> <span data-ttu-id="15910-124">Dies ist Bestandteil eines Software Sperre Mechanismus, das wird sichergestellt, dass nur eine Chat-Dienste zu einem Zeitpunkt der Active Directory-Synchronisierung wird.</span><span class="sxs-lookup"><span data-stu-id="15910-124">This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span>  <br/> |
   
<span data-ttu-id="15910-125">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="15910-125">**Keys**</span></span>

|<span data-ttu-id="15910-126">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="15910-126">**Column(s)**</span></span>|<span data-ttu-id="15910-127">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="15910-127">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="15910-128">prinGuid</span><span class="sxs-lookup"><span data-stu-id="15910-128">prinGuid</span></span>  <br/> |<span data-ttu-id="15910-129">Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="15910-129">Primary key.</span></span>  <br/> |
|<span data-ttu-id="15910-130">prinGuid</span><span class="sxs-lookup"><span data-stu-id="15910-130">prinGuid</span></span>  <br/> |<span data-ttu-id="15910-131">Fremdschlüssel mit Abfrage der Principal.prinGuid-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="15910-131">Foreign key with lookup in Principal.prinGuid table.</span></span>  <br/> |
   

