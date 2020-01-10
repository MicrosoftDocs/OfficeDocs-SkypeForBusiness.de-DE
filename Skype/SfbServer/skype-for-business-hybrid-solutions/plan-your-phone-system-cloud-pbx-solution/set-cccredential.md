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
localization_priority: Normal
ms.assetid: 784ff94a-4b33-4dbd-ba74-27acc3eb6954
description: 'Das Cmdlet „Set-CcCredential“ legt die Anmeldeinformationen der aktuellen Skype for Business Cloud Connector Edition-Bereitstellung fest. '
ms.openlocfilehash: bcb88f11fb78d995e6d8271593c2e09bb0b11d22
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003215"
---
# <a name="set-cccredential"></a><span data-ttu-id="b2ea5-103">Set-CcCredential</span><span class="sxs-lookup"><span data-stu-id="b2ea5-103">Set-CcCredential</span></span>
 
<span data-ttu-id="b2ea5-104">Das Cmdlet „Set-CcCredential“ legt die Anmeldeinformationen der aktuellen Skype for Business Cloud Connector Edition-Bereitstellung fest. </span><span class="sxs-lookup"><span data-stu-id="b2ea5-104">The Set-CcCredential cmdlet sets the credential of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="b2ea5-105">Mit Cloud Connector, Version 2,0 und höher, kann dieses Cmdlet auch die Kontoinformationen für den Virtual Machine-Administrator und für den Domänenadministrator einrichten.</span><span class="sxs-lookup"><span data-stu-id="b2ea5-105">With Cloud Connector version 2.0 and later, this cmdlet can also set the account information for the virtual machine administrator and for the domain administrator.</span></span>
  
```powershell
Set-CcCredential [[-AccountType] <string> {TenantAdmin}]
```

## <a name="examples"></a><span data-ttu-id="b2ea5-106">Beispiele</span><span class="sxs-lookup"><span data-stu-id="b2ea5-106">Examples</span></span>
<span data-ttu-id="b2ea5-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="b2ea5-107"></span></span>

### <a name="example-1"></a><span data-ttu-id="b2ea5-108">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="b2ea5-108">Example 1</span></span>

<span data-ttu-id="b2ea5-109">Im folgenden Beispiel werden der Kontoname und das Kennwort für den Mandantenadministrator angegeben:</span><span class="sxs-lookup"><span data-stu-id="b2ea5-109">The following example specifies the account name and password for the tenant administrator:</span></span>
  
```powershell
Set-CcCredential -AccountType "TenantAdmin"
```

## <a name="detailed-description"></a><span data-ttu-id="b2ea5-110">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b2ea5-110">Detailed Description</span></span>
<span data-ttu-id="b2ea5-111"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="b2ea5-111"></span></span>

<span data-ttu-id="b2ea5-112">Das Cmdlet „Set-CcCredential“ legt den Kontonamen und das Kennwort für den Mandantenadministrator fest.</span><span class="sxs-lookup"><span data-stu-id="b2ea5-112">The Set-CcCredential cmdlet sets the account name and password for the tenant administrator.</span></span> <span data-ttu-id="b2ea5-113">Für Versionen vor Version 2.0 muss dieser Administrator ein globaler Office 365-Administrator sein.</span><span class="sxs-lookup"><span data-stu-id="b2ea5-113">For releases prior to 2.0, this administrator must be an Office 365 Global Administrator.</span></span> <span data-ttu-id="b2ea5-114">Cloud Connector verwendet dieses Konto, um Konfigurationsinformationen abzurufen, Konfigurationsparameter einzurichten und den Appliance-Status auf die Office 365-Mandanten Konfiguration zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="b2ea5-114">Cloud Connector uses this account to get configuration information, set configuration parameters, and update appliance status to the Office 365 tenant configuration.</span></span> <span data-ttu-id="b2ea5-115">Mit Version 2,0 und höher können Sie auch dieses Cmdlet verwenden, um die Kennwörter für die VmAdmin-und DomainAdmin-Konten zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="b2ea5-115">With release 2.0 and later, you can also use this cmdlet to update the passwords for the VmAdmin and DomainAdmin accounts.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="b2ea5-116">Parameter</span><span class="sxs-lookup"><span data-stu-id="b2ea5-116">Parameters</span></span>
<span data-ttu-id="b2ea5-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="b2ea5-117"></span></span>

|<span data-ttu-id="b2ea5-118">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="b2ea5-118">**Parameter**</span></span>|<span data-ttu-id="b2ea5-119">**Erforderlich**</span><span class="sxs-lookup"><span data-stu-id="b2ea5-119">**Required**</span></span>|<span data-ttu-id="b2ea5-120">**Typ**</span><span class="sxs-lookup"><span data-stu-id="b2ea5-120">**Type**</span></span>|<span data-ttu-id="b2ea5-121">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="b2ea5-121">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="b2ea5-122"> AccountType</span><span class="sxs-lookup"><span data-stu-id="b2ea5-122">AccountType</span></span> <br/> | <span data-ttu-id="b2ea5-123">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="b2ea5-123">Required</span></span> <br/> |<span data-ttu-id="b2ea5-124">System.String</span><span class="sxs-lookup"><span data-stu-id="b2ea5-124">System.String</span></span>  <br/> | <span data-ttu-id="b2ea5-125"> Der Parameterwert muss „TenantAdmin“ „VmAdmin“ oder „DomainAdmin“ lauten.</span><span class="sxs-lookup"><span data-stu-id="b2ea5-125">Parameter value must be "TenantAdmin", "VmAdmin", or "DomainAdmin".</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="b2ea5-126">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="b2ea5-126">Input Types</span></span>
<span data-ttu-id="b2ea5-127"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b2ea5-127"></span></span>

<span data-ttu-id="b2ea5-p102">Keine. Das Cmdlet „Set-CcCredential“ akzeptiert keine Pipelineeingaben.</span><span class="sxs-lookup"><span data-stu-id="b2ea5-p102">None. The Set-CcCredential cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="b2ea5-130">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="b2ea5-130">Return Types</span></span>
<span data-ttu-id="b2ea5-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b2ea5-131"></span></span>

<span data-ttu-id="b2ea5-132">Keine</span><span class="sxs-lookup"><span data-stu-id="b2ea5-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b2ea5-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b2ea5-133">See also</span></span>
<span data-ttu-id="b2ea5-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b2ea5-134"></span></span>

[<span data-ttu-id="b2ea5-135">Get-CcCredential</span><span class="sxs-lookup"><span data-stu-id="b2ea5-135">Get-CcCredential</span></span>](get-cccredential.md)
  

