---
title: Set-CcCredential
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 784ff94a-4b33-4dbd-ba74-27acc3eb6954
description: Das Cmdlet Set-CcCredential legt die Anmeldeinformationen der aktuellen Skype for Business Cloud Connector Edition-Bereitstellung fest.
ms.openlocfilehash: 3717eb0dcaa46bb6708f40ecb7f94869f24774a2
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221569"
---
# <a name="set-cccredential"></a><span data-ttu-id="7ced7-103">Set-CcCredential</span><span class="sxs-lookup"><span data-stu-id="7ced7-103">Set-CcCredential</span></span>
 
<span data-ttu-id="7ced7-104">Das Cmdlet Set-CcCredential legt die Anmeldeinformationen der aktuellen Skype for Business Cloud Connector Edition-Bereitstellung fest.</span><span class="sxs-lookup"><span data-stu-id="7ced7-104">The Set-CcCredential cmdlet sets the credential of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="7ced7-105">Mit Cloud Connector Version 2,0 und höher können mit diesem Cmdlet auch die Kontoinformationen für den Administrator des virtuellen Computers und für den Domänenadministrator festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="7ced7-105">With Cloud Connector version 2.0 and later, this cmdlet can also set the account information for the virtual machine administrator and for the domain administrator.</span></span>
  
```powershell
Set-CcCredential [[-AccountType] <string> {TenantAdmin}]
```

## <a name="examples"></a><span data-ttu-id="7ced7-106">Beispiele</span><span class="sxs-lookup"><span data-stu-id="7ced7-106">Examples</span></span>
<span data-ttu-id="7ced7-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="7ced7-107"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="7ced7-108">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="7ced7-108">Example 1</span></span>

<span data-ttu-id="7ced7-109">Das folgende Beispiel gibt den Kontonamen und das Kennwort für den mandantenadministrator an:</span><span class="sxs-lookup"><span data-stu-id="7ced7-109">The following example specifies the account name and password for the tenant administrator:</span></span>
  
```powershell
Set-CcCredential -AccountType "TenantAdmin"
```

## <a name="detailed-description"></a><span data-ttu-id="7ced7-110">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7ced7-110">Detailed Description</span></span>
<span data-ttu-id="7ced7-111"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="7ced7-111"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="7ced7-112">Das Cmdlet Set-CcCredential legt den Kontonamen und das Kennwort für den mandantenadministrator fest.</span><span class="sxs-lookup"><span data-stu-id="7ced7-112">The Set-CcCredential cmdlet sets the account name and password for the tenant administrator.</span></span> <span data-ttu-id="7ced7-113">Für Releases vor 2,0 muss dieser Administrator ein globaler Administrator sein.</span><span class="sxs-lookup"><span data-stu-id="7ced7-113">For releases prior to 2.0, this administrator must be a Global Administrator.</span></span> <span data-ttu-id="7ced7-114">Cloud Connector verwendet dieses Konto, um Konfigurationsinformationen abzurufen, Konfigurationsparameter festzulegen und den Appliance-Status auf die Microsoft 365-oder Office 365-Organisationskonfiguration zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="7ced7-114">Cloud Connector uses this account to get configuration information, set configuration parameters, and update appliance status to the Microsoft 365 or Office 365 organization configuration.</span></span> <span data-ttu-id="7ced7-115">Mit Version 2,0 und höher können Sie dieses Cmdlet auch zum Aktualisieren der Kennwörter für die "vmadmin"-und DomainAdmin-Konten verwenden.</span><span class="sxs-lookup"><span data-stu-id="7ced7-115">With release 2.0 and later, you can also use this cmdlet to update the passwords for the VmAdmin and DomainAdmin accounts.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="7ced7-116">Parameter</span><span class="sxs-lookup"><span data-stu-id="7ced7-116">Parameters</span></span>
<span data-ttu-id="7ced7-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="7ced7-117"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="7ced7-118">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="7ced7-118">**Parameter**</span></span>|<span data-ttu-id="7ced7-119">**Required**</span><span class="sxs-lookup"><span data-stu-id="7ced7-119">**Required**</span></span>|<span data-ttu-id="7ced7-120">**Typ**</span><span class="sxs-lookup"><span data-stu-id="7ced7-120">**Type**</span></span>|<span data-ttu-id="7ced7-121">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="7ced7-121">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="7ced7-122">AccountType</span><span class="sxs-lookup"><span data-stu-id="7ced7-122">AccountType</span></span> <br/> | <span data-ttu-id="7ced7-123">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="7ced7-123">Required</span></span> <br/> |<span data-ttu-id="7ced7-124">System.String</span><span class="sxs-lookup"><span data-stu-id="7ced7-124">System.String</span></span>  <br/> | <span data-ttu-id="7ced7-125">Der Parameter Wert muss "TenantAdmin", "" vmadmin "" oder "DomainAdmin" lauten.</span><span class="sxs-lookup"><span data-stu-id="7ced7-125">Parameter value must be "TenantAdmin", "VmAdmin", or "DomainAdmin".</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="7ced7-126">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="7ced7-126">Input Types</span></span>
<span data-ttu-id="7ced7-127"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="7ced7-127"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="7ced7-128">Keine.</span><span class="sxs-lookup"><span data-stu-id="7ced7-128">None.</span></span> <span data-ttu-id="7ced7-129">Das Cmdlet "Sets-CcCredential" akzeptiert keine weitergeleitete Eingabe.</span><span class="sxs-lookup"><span data-stu-id="7ced7-129">The Set-CcCredential cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="7ced7-130">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="7ced7-130">Return Types</span></span>
<span data-ttu-id="7ced7-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="7ced7-131"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="7ced7-132">Keine</span><span class="sxs-lookup"><span data-stu-id="7ced7-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7ced7-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7ced7-133">See also</span></span>
<span data-ttu-id="7ced7-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="7ced7-134"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="7ced7-135">Get-CcCredential</span><span class="sxs-lookup"><span data-stu-id="7ced7-135">Get-CcCredential</span></span>](get-cccredential.md)
  

