---
title: Get-CcSiteDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a243758e-6774-4437-ad2e-d5cea5f04eb6
description: Das Cmdlet „Get-CcSiteDirectory“ zeigt das aktuelle Verzeichnis an, in dem die Konfigurationsdateien auf Standortebene gespeichert werden. Der Ordner enthält die Installationsdateien für die Basis-VHD und für Skype for Business Cloud Connector Edition. In diesem Ordner sollten für alle anderen Einheiten einer Cloud-Connector-Website freigegeben werden.
ms.openlocfilehash: d0869f3cbd1c43e523107a0ff8dce6fd769889a8
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30882397"
---
# <a name="get-ccsitedirectory"></a><span data-ttu-id="caad3-105">Get-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="caad3-105">Get-CcSiteDirectory</span></span>
 
<span data-ttu-id="caad3-106">Das Cmdlet „Get-CcSiteDirectory“ zeigt das aktuelle Verzeichnis an, in dem die Konfigurationsdateien auf Standortebene gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="caad3-106">The Get-CcSiteDirectory cmdlet shows the current directory where site level configuration files are stored.</span></span> <span data-ttu-id="caad3-107">Der Ordner enthält die Installationsdateien für die Basis-VHD und für Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="caad3-107">The folder contains the base VHD and Skype for Business Cloud Connector Edition installation files.</span></span> <span data-ttu-id="caad3-108">In diesem Ordner sollten für alle anderen Einheiten einer Cloud-Connector-Website freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="caad3-108">This folder should be shared with all other appliances of a Cloud Connector site.</span></span>
  
<span data-ttu-id="caad3-109">Dieses Cmdlet gilt für Cloud Connector Edition 1.4.1 und 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="caad3-109">This cmdlet applies to Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Get-CcSiteDirectory
```

## <a name="parameters"></a><span data-ttu-id="caad3-110">Parameter</span><span class="sxs-lookup"><span data-stu-id="caad3-110">Parameters</span></span>

<span data-ttu-id="caad3-111">Keine</span><span class="sxs-lookup"><span data-stu-id="caad3-111">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="caad3-112">Beispiele</span><span class="sxs-lookup"><span data-stu-id="caad3-112">Examples</span></span>
<span data-ttu-id="caad3-113"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="caad3-113"></span></span>

### <a name="example-1"></a><span data-ttu-id="caad3-114">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="caad3-114">Example 1</span></span>

<span data-ttu-id="caad3-115">Im folgenden Beispiel wird den aktuellen Ordner, in dem die Konfiguration und virtuelle Computer Dateien Cloud Connector Komponenten gespeichert sind:</span><span class="sxs-lookup"><span data-stu-id="caad3-115">The following example shows the current folder where the configuration and virtual machines files of Cloud Connector components are stored:</span></span>
  
```
Get-CcSiteDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="caad3-116">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="caad3-116">Detailed Description</span></span>
<span data-ttu-id="caad3-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="caad3-117"></span></span>

<span data-ttu-id="caad3-118">Um Gateway Affinität und hohe Verfügbarkeit zu ermöglichen, können in Websites Cloud Connector Appliances kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="caad3-118">To provide gateway affinity and high availability, Cloud Connector appliances can be combined in sites.</span></span> <span data-ttu-id="caad3-119">Benutzer werden anstelle von Cloud-Connector Appliances zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="caad3-119">Users are assigned to sites instead of Cloud Connector appliances.</span></span> <span data-ttu-id="caad3-120">Jeder Standort verfügt über einen freigegebenen Ordner, in dem die Installationsdateien für die Basis-VHD und für Cloud Connector gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="caad3-120">Each site has a shared folder where the base VHD and Cloud Connector installation files are stored.</span></span> <span data-ttu-id="caad3-121">Verwenden Sie diesen Ordner Appliances während der Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="caad3-121">Appliances use this folder during the deployment.</span></span> <span data-ttu-id="caad3-122">Der Standardordner ist C:\Users\%userprofile%\CloudConnector\SiteRoot.</span><span class="sxs-lookup"><span data-stu-id="caad3-122">The default folder is C:\Users\%userprofile%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="caad3-123">Sie können den Pfad mit dem Cmdlet „Set-CcSiteDirectory“ ändern.</span><span class="sxs-lookup"><span data-stu-id="caad3-123">You can change the path by using the Set-CcSiteDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="caad3-124">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="caad3-124">Input Types</span></span>
<span data-ttu-id="caad3-125"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="caad3-125"></span></span>

<span data-ttu-id="caad3-p104">Keine. Das Cmdlet „Get-CcSiteDirectory“ akzeptiert keine Pipelineeingaben.</span><span class="sxs-lookup"><span data-stu-id="caad3-p104">None. The Get-CcSiteDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="caad3-128">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="caad3-128">Return Types</span></span>
<span data-ttu-id="caad3-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="caad3-129"></span></span>

<span data-ttu-id="caad3-130">Dieser Befehl gibt einen Dateipfad zurück.</span><span class="sxs-lookup"><span data-stu-id="caad3-130">This command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="caad3-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="caad3-131">See also</span></span>
<span data-ttu-id="caad3-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="caad3-132"></span></span>

[<span data-ttu-id="caad3-133">Set-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="caad3-133">Set-CcSiteDirectory</span></span>](set-ccsitedirectory.md)
  

