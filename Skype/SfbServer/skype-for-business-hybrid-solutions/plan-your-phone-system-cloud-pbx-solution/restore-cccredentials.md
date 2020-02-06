---
title: Restore-CcCredentials
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: aeca610b-db0a-45cf-95b9-ae9a6bbccb45
description: Das Cmdlet Restore CC-Credentials stellt alle Anmeldeinformationen der aktuellen Skype for Business Cloud Connector Edition-Bereitstellung wieder her.
ms.openlocfilehash: b2cd35b284bcd7e49aabbaa3055c397915565d09
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824241"
---
# <a name="restore-cccredentials"></a><span data-ttu-id="958d3-103">Restore-CcCredentials</span><span class="sxs-lookup"><span data-stu-id="958d3-103">Restore-CcCredentials</span></span>
 
<span data-ttu-id="958d3-104">Das Cmdlet Restore CC-Credentials stellt alle Anmeldeinformationen der aktuellen Skype for Business Cloud Connector Edition-Bereitstellung wieder her.</span><span class="sxs-lookup"><span data-stu-id="958d3-104">The Restore Cc-Credentials cmdlet restores all credentials of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="958d3-105">Dieses Cmdlet gilt für Skype for Business Cloud Connector Edition 2,1.</span><span class="sxs-lookup"><span data-stu-id="958d3-105">This cmdlet applies to Skype for Business Cloud Connector Edition 2.1.</span></span>
  
```powershell
Restore-CcCredentials 
```

## <a name="detailed-description"></a><span data-ttu-id="958d3-106">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="958d3-106">Detailed Description</span></span>

<span data-ttu-id="958d3-107">Das Cmdlet Restore-CcCredentials bereinigt alle Anmeldeinformationen und fordert Sie auf, alle für die aktuelle Skype for Business Cloud Connector-Bereitstellung verwendeten Anmeldeinformationen erneut einzugeben.</span><span class="sxs-lookup"><span data-stu-id="958d3-107">The Restore-CcCredentials cmdlet cleans up all credentials and prompts you to re-enter all the credentials used for the current Skype for Business Cloud Connector deployment.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="958d3-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="958d3-108">Parameters</span></span>

<span data-ttu-id="958d3-109">Keine</span><span class="sxs-lookup"><span data-stu-id="958d3-109">None</span></span>
  
## <a name="input-types"></a><span data-ttu-id="958d3-110">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="958d3-110">Input Types</span></span>

<span data-ttu-id="958d3-111">Keine.</span><span class="sxs-lookup"><span data-stu-id="958d3-111">None.</span></span> <span data-ttu-id="958d3-112">Das Cmdlet "Restore-CcCredentials" akzeptiert keine Pipeline-Eingaben.</span><span class="sxs-lookup"><span data-stu-id="958d3-112">The Restore-CcCredentials cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="958d3-113">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="958d3-113">Return Types</span></span>

<span data-ttu-id="958d3-114">Keine.</span><span class="sxs-lookup"><span data-stu-id="958d3-114">None.</span></span>
  
## <a name="example"></a><span data-ttu-id="958d3-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="958d3-115">Example</span></span>

<span data-ttu-id="958d3-116">Im folgenden Beispiel werden alle Anmeldeinformationen der aktuellen Cloud Connector-Bereitstellung wiederhergestellt:</span><span class="sxs-lookup"><span data-stu-id="958d3-116">The following example restores all credentials of the current Cloud Connector deployment:</span></span>
  
```powershell
    PS C:\>Restore-CcCredentials
```

## <a name="see-also"></a><span data-ttu-id="958d3-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="958d3-117">See also</span></span>

[<span data-ttu-id="958d3-118">Get-CcCredential</span><span class="sxs-lookup"><span data-stu-id="958d3-118">Get-CcCredential</span></span>](get-cccredential.md)
  
[<span data-ttu-id="958d3-119">Set-CcCredential</span><span class="sxs-lookup"><span data-stu-id="958d3-119">Set-CcCredential</span></span>](set-cccredential.md)
  

