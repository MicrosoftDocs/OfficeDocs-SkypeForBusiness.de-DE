---
title: Get-CcApplianceDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c2fda202-db2f-4122-b630-7df11a697c5f
description: 'Das Cmdlet „Get-CcApplianceDirectory“ ruft das Arbeitsverzeichnis auf dem Hostserver von Skype for Business Cloud Connector Edition ab. In diesem Verzeichnis werden alle Bereitstellungsdateien gespeichert. '
ms.openlocfilehash: 04764f312138132fb34c0979423da5dc4696ee63
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41800845"
---
# <a name="get-ccappliancedirectory"></a><span data-ttu-id="b3847-104">Get-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="b3847-104">Get-CcApplianceDirectory</span></span>
 
<span data-ttu-id="b3847-p102">Das Cmdlet „Get-CcApplianceDirectory“ ruft das Arbeitsverzeichnis auf dem Hostserver von Skype for Business Cloud Connector Edition ab. In diesem Verzeichnis werden alle Bereitstellungsdateien gespeichert. </span><span class="sxs-lookup"><span data-stu-id="b3847-p102">The Get-CcApplianceDirectory cmdlet retrieves the working directory on the Skype for Business Cloud Connector Edition host server. All deployment files are stored in this directory.</span></span> 
  
<span data-ttu-id="b3847-107">Dieses Cmdlet gilt für Skype for Business Cloud Connector Edition 1.4.1 und 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="b3847-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Get-CcApplianceDirectory
```

## <a name="parameters"></a><span data-ttu-id="b3847-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="b3847-108">Parameters</span></span>

<span data-ttu-id="b3847-109">Keine</span><span class="sxs-lookup"><span data-stu-id="b3847-109">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="b3847-110">Beispiele</span><span class="sxs-lookup"><span data-stu-id="b3847-110">Examples</span></span>
<span data-ttu-id="b3847-111"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="b3847-111"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="b3847-112">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="b3847-112">Example 1</span></span>

<span data-ttu-id="b3847-113">Das folgende Beispiel zeigt den aktuellen Ordner, in dem Konfigurations-und Virtual Machine-Dateien von Cloud Connector-Komponenten gespeichert werden:</span><span class="sxs-lookup"><span data-stu-id="b3847-113">The following example shows the current folder where configuration and virtual machine files of Cloud Connector components are stored:</span></span>
  
```powershell
Get-CcApplianceDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="b3847-114">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b3847-114">Detailed Description</span></span>
<span data-ttu-id="b3847-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="b3847-115"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="b3847-116">Das Cmdlet "Get-CcApplianceDirectory" zeigt an, wo alle Konfigurations-und virtuellen Computer Dateien,-Protokolle und externen Zertifikate für die Cloud Connector-Appliance gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="b3847-116">The Get-CcApplianceDirectory cmdlet shows where all configuration and virtual machine files, logs, and external certificates are stored for the Cloud Connector appliance.</span></span>
  
<span data-ttu-id="b3847-117">Jede Cloud Connector-Appliance verfügt über vier Komponenten: Mediationsserver, zentraler Verwaltungsspeicher, Edgeserver und einen Domänen Controller.</span><span class="sxs-lookup"><span data-stu-id="b3847-117">Each Cloud Connector appliance has four components: Mediation Server, Central Management Store, Edge Server, and a Domain Controller.</span></span> <span data-ttu-id="b3847-118">Der Standardordner lautet C:\Users\%USERPROFILE%\CloudConnector\ApplianceRoot.</span><span class="sxs-lookup"><span data-stu-id="b3847-118">The default folder is C:\Users\%userprofile%\CloudConnector\ApplianceRoot.</span></span> <span data-ttu-id="b3847-119">Sie können den Ordner mit dem Cmdlet „Set-CCApplianceDirectory“ ändern.</span><span class="sxs-lookup"><span data-stu-id="b3847-119">You can change this folder by using the Set-CCApplianceDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="b3847-120">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="b3847-120">Input Types</span></span>
<span data-ttu-id="b3847-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b3847-121"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="b3847-p104">Keine. Das Cmdlet „Get-CCApplianceDirectory“ akzeptiert keine Pipelineeingaben.</span><span class="sxs-lookup"><span data-stu-id="b3847-p104">None. The Get-CCApplianceDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="b3847-124">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="b3847-124">Return Types</span></span>
<span data-ttu-id="b3847-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b3847-125"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="b3847-126">Der Befehl gibt einen Dateipfad zurück.</span><span class="sxs-lookup"><span data-stu-id="b3847-126">The command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b3847-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b3847-127">See also</span></span>
<span data-ttu-id="b3847-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b3847-128"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="b3847-129">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="b3847-129">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

