---
title: Get-CcSiteLogDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6625494d-1b63-4d99-a589-c8c69c4addba
description: 'Das Cmdlet „Get-CcSiteLogDirectory“ zeigt das aktuelle Verzeichnis an, in dem die Protokolle auf Standortebene für Skype for Business Cloud Connector Edition gespeichert werden. '
ms.openlocfilehash: cace3ce3757294adbb3c55db24c619925f55ce5a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799885"
---
# <a name="get-ccsitelogdirectory"></a><span data-ttu-id="81e76-103">Get-CcSiteLogDirectory</span><span class="sxs-lookup"><span data-stu-id="81e76-103">Get-CcSiteLogDirectory</span></span>
 
<span data-ttu-id="81e76-104">Das Cmdlet „Get-CcSiteLogDirectory“ zeigt das aktuelle Verzeichnis an, in dem die Protokolle auf Standortebene für Skype for Business Cloud Connector Edition gespeichert werden. </span><span class="sxs-lookup"><span data-stu-id="81e76-104">The Get-CcSiteLogDirectory cmdlet shows the current directory where the site level logs for Skype for Business Cloud Connector Edition are stored.</span></span> 
  
<span data-ttu-id="81e76-105">Dieses Cmdlet gilt für Skype for Business Cloud Connector Edition 1.4.1 und 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="81e76-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Get-CcSiteLogDirectory
```

## <a name="parameters"></a><span data-ttu-id="81e76-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="81e76-106">Parameters</span></span>

<span data-ttu-id="81e76-107">Keine</span><span class="sxs-lookup"><span data-stu-id="81e76-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="81e76-108">Beispiele</span><span class="sxs-lookup"><span data-stu-id="81e76-108">Examples</span></span>
<span data-ttu-id="81e76-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="81e76-109"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="81e76-110">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="81e76-110">Example 1</span></span>

<span data-ttu-id="81e76-111">Das folgende Beispiel zeigt den aktuellen Ordner, in dem die Protokolldateien für die Cloud Connector-Website gespeichert sind:</span><span class="sxs-lookup"><span data-stu-id="81e76-111">The following example shows the current folder where the log files for the Cloud Connector site are stored:</span></span>
  
```powershell
Get-CcSiteLogDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="81e76-112">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="81e76-112">Detailed Description</span></span>
<span data-ttu-id="81e76-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="81e76-113"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="81e76-114">Der Standardordner lautet C:\Users\%USERPROFILE%\CloudConnector\SiteRoot\Logs.</span><span class="sxs-lookup"><span data-stu-id="81e76-114">The default folder is C:\Users\%userprofile%\CloudConnector\SiteRoot\Logs.</span></span> <span data-ttu-id="81e76-115">Sie können den Ordner ändern, indem Sie das Cmdlet „Set-CcSiteDirectory“ ausführen.</span><span class="sxs-lookup"><span data-stu-id="81e76-115">You can change the folder by running the Set-CcSiteDirectory cmdlet.</span></span> <span data-ttu-id="81e76-116">Es gibt kein separates Cmdlet, das nur den Speicherort des Protokollordners, aber nicht das Standortverzeichnis ändert.</span><span class="sxs-lookup"><span data-stu-id="81e76-116">There is no separate cmdlet that changes only the log folder location without changing the site directory.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="81e76-117">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="81e76-117">Input Types</span></span>
<span data-ttu-id="81e76-118"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="81e76-118"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="81e76-p102">Keine. Das Cmdlet „Get-CcSiteLogDirectory“ akzeptiert keine Pipelineeingaben.</span><span class="sxs-lookup"><span data-stu-id="81e76-p102">None. The Get-CcSiteLogDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="81e76-121">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="81e76-121">Return Types</span></span>
<span data-ttu-id="81e76-122"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="81e76-122"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="81e76-123">Der Befehl gibt einen Dateipfad zurück.</span><span class="sxs-lookup"><span data-stu-id="81e76-123">The command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="81e76-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="81e76-124">See also</span></span>
<span data-ttu-id="81e76-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="81e76-125"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="81e76-126">Set-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="81e76-126">Set-CcSiteDirectory</span></span>](set-ccsitedirectory.md)
  

