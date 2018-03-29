---
title: "\"tbladcookie\""
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
ms.openlocfilehash: bc2c0657caa66a0420bc493bf4b688a2a081db36
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="tbladcookie"></a><span data-ttu-id="ef50f-103">"tbladcookie"</span><span class="sxs-lookup"><span data-stu-id="ef50f-103">tblADCookie</span></span>
 
<span data-ttu-id="ef50f-104">"tbladcookie" enthält die aktuellen Cookies Synchronisierung Lightweight Directory Access Protocol (LDAP).</span><span class="sxs-lookup"><span data-stu-id="ef50f-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>
  
<span data-ttu-id="ef50f-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="ef50f-105">**Columns**</span></span>

|<span data-ttu-id="ef50f-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="ef50f-106">**Column**</span></span>|<span data-ttu-id="ef50f-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="ef50f-107">**Type**</span></span>|<span data-ttu-id="ef50f-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="ef50f-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ef50f-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="ef50f-109">prinGuid</span></span>  <br/> |<span data-ttu-id="ef50f-110">GUID, nicht null</span><span class="sxs-lookup"><span data-stu-id="ef50f-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="ef50f-111">Prinzipal-GUID der überwachten Domäne.</span><span class="sxs-lookup"><span data-stu-id="ef50f-111">Principal GUID of the domain being monitored.</span></span>  <br/> |
|<span data-ttu-id="ef50f-112">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="ef50f-112">prinDCHost</span></span>  <br/> |<span data-ttu-id="ef50f-113">Nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="ef50f-113">nvarchar (255)</span></span>  <br/> |<span data-ttu-id="ef50f-114">Vollqualifizierter Domänenname (FQDN) des aktuellen Domänencontrollers für Active Directory Domain Services Sync verwendet. Informative Wert hat.</span><span class="sxs-lookup"><span data-stu-id="ef50f-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span>  <br/> |
|<span data-ttu-id="ef50f-115">adcContent</span><span class="sxs-lookup"><span data-stu-id="ef50f-115">adcContent</span></span>  <br/> |<span data-ttu-id="ef50f-116">Bild (binär)</span><span class="sxs-lookup"><span data-stu-id="ef50f-116">image (binary)</span></span>  <br/> |<span data-ttu-id="ef50f-117">Active Directory-Synchronisierung Cookie.</span><span class="sxs-lookup"><span data-stu-id="ef50f-117">Active Directory Sync cookie.</span></span>  <br/> |
|<span data-ttu-id="ef50f-118">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="ef50f-118">lastUpdated</span></span>  <br/> |<span data-ttu-id="ef50f-119">datetime</span><span class="sxs-lookup"><span data-stu-id="ef50f-119">datetime</span></span>  <br/> |<span data-ttu-id="ef50f-120">Zeitstempel mit Aktualisierungszeit der Zeile.</span><span class="sxs-lookup"><span data-stu-id="ef50f-120">Time stamp with the row update time.</span></span>  <br/> |
|<span data-ttu-id="ef50f-121">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="ef50f-121">lockedUntil</span></span>  <br/> |<span data-ttu-id="ef50f-122">datetime</span><span class="sxs-lookup"><span data-stu-id="ef50f-122">datetime</span></span>  <br/> |<span data-ttu-id="ef50f-123">Zeitpunkt, bis die Zeile für Änderungen gesperrt ist.</span><span class="sxs-lookup"><span data-stu-id="ef50f-123">Time until the row is locked for changes.</span></span> <span data-ttu-id="ef50f-124">Dies ist Bestandteil eines Software Sperre Mechanismus, das wird sichergestellt, dass nur eine Chat-Dienste zu einem Zeitpunkt der Active Directory-Synchronisierung wird.</span><span class="sxs-lookup"><span data-stu-id="ef50f-124">This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span>  <br/> |
   
<span data-ttu-id="ef50f-125">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="ef50f-125">**Keys**</span></span>

|<span data-ttu-id="ef50f-126">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="ef50f-126">**Column(s)**</span></span>|<span data-ttu-id="ef50f-127">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="ef50f-127">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ef50f-128">prinGuid</span><span class="sxs-lookup"><span data-stu-id="ef50f-128">prinGuid</span></span>  <br/> |<span data-ttu-id="ef50f-129">Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="ef50f-129">Primary key.</span></span>  <br/> |
|<span data-ttu-id="ef50f-130">prinGuid</span><span class="sxs-lookup"><span data-stu-id="ef50f-130">prinGuid</span></span>  <br/> |<span data-ttu-id="ef50f-131">Fremdschlüssel mit Abfrage der Principal.prinGuid-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="ef50f-131">Foreign key with lookup in Principal.prinGuid table.</span></span>  <br/> |
   

