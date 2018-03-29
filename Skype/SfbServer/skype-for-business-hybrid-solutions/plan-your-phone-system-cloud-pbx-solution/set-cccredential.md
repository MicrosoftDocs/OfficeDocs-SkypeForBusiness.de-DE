---
title: Set-CcCredential
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 784ff94a-4b33-4dbd-ba74-27acc3eb6954
description: 'Das Cmdlet „Set-CcCredential“ legt die Anmeldeinformationen der aktuellen Skype for Business Cloud Connector Edition-Bereitstellung fest. '
ms.openlocfilehash: 7680f863ccf082ddb8359c7d3fcefc2c058b6a40
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="set-cccredential"></a><span data-ttu-id="aa4cf-103">Set-CcCredential</span><span class="sxs-lookup"><span data-stu-id="aa4cf-103">Set-CcCredential</span></span>
 
<span data-ttu-id="aa4cf-104">Das Cmdlet „Set-CcCredential“ legt die Anmeldeinformationen der aktuellen Skype for Business Cloud Connector Edition-Bereitstellung fest. </span><span class="sxs-lookup"><span data-stu-id="aa4cf-104">The Set-CcCredential cmdlet sets the credential of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="aa4cf-105">Mit Cloud Connector, Version 2.0 und höher kann mit diesem Cmdlet auch die Kontoinformationen für die virtuellen Computer-Administrator und Domänenadministrator festlegen.</span><span class="sxs-lookup"><span data-stu-id="aa4cf-105">With Cloud Connector version 2.0 and later, this cmdlet can also set the account information for the virtual machine administrator and for the domain administrator.</span></span>
  
```
Set-CcCredential [[-AccountType] <string> {TenantAdmin}]
```

## <a name="examples"></a><span data-ttu-id="aa4cf-106">Beispiele</span><span class="sxs-lookup"><span data-stu-id="aa4cf-106">Examples</span></span>
<span data-ttu-id="aa4cf-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="aa4cf-107"></span></span>

### <a name="example-1"></a><span data-ttu-id="aa4cf-108">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="aa4cf-108">Example 1</span></span>

<span data-ttu-id="aa4cf-109">Im folgenden Beispiel werden der Kontoname und das Kennwort für den Mandantenadministrator angegeben:</span><span class="sxs-lookup"><span data-stu-id="aa4cf-109">The following example specifies the account name and password for the tenant administrator:</span></span>
  
```
Set-CcCredential -AccountType "TenantAdmin"
```

## <a name="detailed-description"></a><span data-ttu-id="aa4cf-110">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="aa4cf-110">Detailed Description</span></span>
<span data-ttu-id="aa4cf-111"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="aa4cf-111"></span></span>

<span data-ttu-id="aa4cf-112">Das Cmdlet „Set-CcCredential“ legt den Kontonamen und das Kennwort für den Mandantenadministrator fest.</span><span class="sxs-lookup"><span data-stu-id="aa4cf-112">The Set-CcCredential cmdlet sets the account name and password for the tenant administrator.</span></span> <span data-ttu-id="aa4cf-113">Für Versionen vor Version 2.0 muss dieser Administrator einer Office 365 globaler Administrator sein.</span><span class="sxs-lookup"><span data-stu-id="aa4cf-113">For releases prior to 2.0, this administrator must be an Office 365 Global Administrator.</span></span> <span data-ttu-id="aa4cf-114">Cloud-Connector wird dieses Konto verwendet, um Konfigurationsinformationen erhalten möchten, legen Sie die Konfiguration der Office 365-Mandanten Konfigurationsparameter und Aktualisierungsstatus Appliance.</span><span class="sxs-lookup"><span data-stu-id="aa4cf-114">Cloud Connector uses this account to get configuration information, set configuration parameters, and update appliance status to the Office 365 tenant configuration.</span></span> <span data-ttu-id="aa4cf-115">Mit Version 2.0 und höher, können Sie dieses Cmdlet zum Aktualisieren der Kennwörter für die Konten VmAdmin und DomainAdmin "verwenden.</span><span class="sxs-lookup"><span data-stu-id="aa4cf-115">With release 2.0 and later, you can also use this cmdlet to update the passwords for the VmAdmin and DomainAdmin accounts.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="aa4cf-116">Parameter</span><span class="sxs-lookup"><span data-stu-id="aa4cf-116">Parameters</span></span>
<span data-ttu-id="aa4cf-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="aa4cf-117"></span></span>

|<span data-ttu-id="aa4cf-118">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="aa4cf-118">**Parameter**</span></span>|<span data-ttu-id="aa4cf-119">**Erforderlich**</span><span class="sxs-lookup"><span data-stu-id="aa4cf-119">**Required**</span></span>|<span data-ttu-id="aa4cf-120">**Typ**</span><span class="sxs-lookup"><span data-stu-id="aa4cf-120">**Type**</span></span>|<span data-ttu-id="aa4cf-121">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="aa4cf-121">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="aa4cf-122">AccountType</span><span class="sxs-lookup"><span data-stu-id="aa4cf-122">AccountType</span></span> <br/> | <span data-ttu-id="aa4cf-123">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="aa4cf-123">Required</span></span> <br/> |<span data-ttu-id="aa4cf-124">System.String</span><span class="sxs-lookup"><span data-stu-id="aa4cf-124">System.String</span></span>  <br/> | <span data-ttu-id="aa4cf-125"> Der Parameterwert muss „TenantAdmin“ „VmAdmin“ oder „DomainAdmin“ lauten.</span><span class="sxs-lookup"><span data-stu-id="aa4cf-125">Parameter value must be "TenantAdmin", "VmAdmin", or "DomainAdmin".</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="aa4cf-126">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="aa4cf-126">Input Types</span></span>
<span data-ttu-id="aa4cf-127"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="aa4cf-127"></span></span>

<span data-ttu-id="aa4cf-p102">Keine. Das Cmdlet „Set-CcCredential“ akzeptiert keine Pipelineeingaben.</span><span class="sxs-lookup"><span data-stu-id="aa4cf-p102">None. The Set-CcCredential cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="aa4cf-130">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="aa4cf-130">Return Types</span></span>
<span data-ttu-id="aa4cf-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="aa4cf-131"></span></span>

<span data-ttu-id="aa4cf-132">Keine</span><span class="sxs-lookup"><span data-stu-id="aa4cf-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="aa4cf-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aa4cf-133">See also</span></span>
<span data-ttu-id="aa4cf-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="aa4cf-134"></span></span>

[<span data-ttu-id="aa4cf-135">Get-CcCredential</span><span class="sxs-lookup"><span data-stu-id="aa4cf-135">Get-CcCredential</span></span>](get-cccredential.md)
  

