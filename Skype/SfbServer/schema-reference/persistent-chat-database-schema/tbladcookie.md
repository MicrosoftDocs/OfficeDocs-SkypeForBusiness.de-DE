---
title: tblADCookie
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: "\"tbladcookie\" enthält die aktuellen Cookies Synchronisierung Lightweight Directory Access Protocol (LDAP)."
ms.openlocfilehash: d990d02e73be9a4d6178037a314e36add448ad40
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929945"
---
# <a name="tbladcookie"></a><span data-ttu-id="7d253-103">tblADCookie</span><span class="sxs-lookup"><span data-stu-id="7d253-103">tblADCookie</span></span>
 
<span data-ttu-id="7d253-104">"tbladcookie" enthält die aktuellen Cookies Synchronisierung Lightweight Directory Access Protocol (LDAP).</span><span class="sxs-lookup"><span data-stu-id="7d253-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>
  
<span data-ttu-id="7d253-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="7d253-105">**Columns**</span></span>

|<span data-ttu-id="7d253-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="7d253-106">**Column**</span></span>|<span data-ttu-id="7d253-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="7d253-107">**Type**</span></span>|<span data-ttu-id="7d253-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="7d253-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7d253-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="7d253-109">prinGuid</span></span>  <br/> |<span data-ttu-id="7d253-110">GUID, nicht null</span><span class="sxs-lookup"><span data-stu-id="7d253-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="7d253-111">Prinzipal-GUID der überwachten Domäne.</span><span class="sxs-lookup"><span data-stu-id="7d253-111">Principal GUID of the domain being monitored.</span></span>  <br/> |
|<span data-ttu-id="7d253-112">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="7d253-112">prinDCHost</span></span>  <br/> |<span data-ttu-id="7d253-113">Nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="7d253-113">nvarchar (255)</span></span>  <br/> |<span data-ttu-id="7d253-114">Vollqualifizierter Domänenname (FQDN) des aktuellen Domänencontrollers für Active Directory Domain Services Sync verwendet. Informative Wert hat.</span><span class="sxs-lookup"><span data-stu-id="7d253-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span>  <br/> |
|<span data-ttu-id="7d253-115">adcContent</span><span class="sxs-lookup"><span data-stu-id="7d253-115">adcContent</span></span>  <br/> |<span data-ttu-id="7d253-116">Bild (binär)</span><span class="sxs-lookup"><span data-stu-id="7d253-116">image (binary)</span></span>  <br/> |<span data-ttu-id="7d253-117">Active Directory-Synchronisierung Cookie.</span><span class="sxs-lookup"><span data-stu-id="7d253-117">Active Directory Sync cookie.</span></span>  <br/> |
|<span data-ttu-id="7d253-118">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="7d253-118">lastUpdated</span></span>  <br/> |<span data-ttu-id="7d253-119">datetime</span><span class="sxs-lookup"><span data-stu-id="7d253-119">datetime</span></span>  <br/> |<span data-ttu-id="7d253-120">Zeitstempel mit Aktualisierungszeit der Zeile.</span><span class="sxs-lookup"><span data-stu-id="7d253-120">Time stamp with the row update time.</span></span>  <br/> |
|<span data-ttu-id="7d253-121">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="7d253-121">lockedUntil</span></span>  <br/> |<span data-ttu-id="7d253-122">datetime</span><span class="sxs-lookup"><span data-stu-id="7d253-122">datetime</span></span>  <br/> |<span data-ttu-id="7d253-123">Zeitpunkt, bis die Zeile für Änderungen gesperrt ist.</span><span class="sxs-lookup"><span data-stu-id="7d253-123">Time until the row is locked for changes.</span></span> <span data-ttu-id="7d253-124">Dies ist Bestandteil eines Software Sperre Mechanismus, das wird sichergestellt, dass nur eine Chat-Dienste zu einem Zeitpunkt der Active Directory-Synchronisierung wird.</span><span class="sxs-lookup"><span data-stu-id="7d253-124">This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span>  <br/> |
   
<span data-ttu-id="7d253-125">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="7d253-125">**Keys**</span></span>

|<span data-ttu-id="7d253-126">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="7d253-126">**Column(s)**</span></span>|<span data-ttu-id="7d253-127">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="7d253-127">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7d253-128">prinGuid</span><span class="sxs-lookup"><span data-stu-id="7d253-128">prinGuid</span></span>  <br/> |<span data-ttu-id="7d253-129">Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="7d253-129">Primary key.</span></span>  <br/> |
|<span data-ttu-id="7d253-130">prinGuid</span><span class="sxs-lookup"><span data-stu-id="7d253-130">prinGuid</span></span>  <br/> |<span data-ttu-id="7d253-131">Fremdschlüssel mit Abfrage der Principal.prinGuid-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="7d253-131">Foreign key with lookup in Principal.prinGuid table.</span></span>  <br/> |
   

