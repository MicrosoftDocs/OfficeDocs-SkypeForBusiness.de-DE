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
localization_priority: Normal
ms.assetid: c2fda202-db2f-4122-b630-7df11a697c5f
description: 'Das Cmdlet „Get-CcApplianceDirectory“ ruft das Arbeitsverzeichnis auf dem Hostserver von Skype for Business Cloud Connector Edition ab. In diesem Verzeichnis werden alle Bereitstellungsdateien gespeichert. '
ms.openlocfilehash: ada1b587b738d882f81557e61438d6642aa03fff
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287391"
---
# <a name="get-ccappliancedirectory"></a><span data-ttu-id="c834e-104">Get-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="c834e-104">Get-CcApplianceDirectory</span></span>
 
<span data-ttu-id="c834e-p102">Das Cmdlet „Get-CcApplianceDirectory“ ruft das Arbeitsverzeichnis auf dem Hostserver von Skype for Business Cloud Connector Edition ab. In diesem Verzeichnis werden alle Bereitstellungsdateien gespeichert. </span><span class="sxs-lookup"><span data-stu-id="c834e-p102">The Get-CcApplianceDirectory cmdlet retrieves the working directory on the Skype for Business Cloud Connector Edition host server. All deployment files are stored in this directory.</span></span> 
  
<span data-ttu-id="c834e-107">Dieses Cmdlet gilt für Skype for Business Cloud Connector Edition 1.4.1 und 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="c834e-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Get-CcApplianceDirectory
```

## <a name="parameters"></a><span data-ttu-id="c834e-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="c834e-108">Parameters</span></span>

<span data-ttu-id="c834e-109">Keine</span><span class="sxs-lookup"><span data-stu-id="c834e-109">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="c834e-110">Beispiele</span><span class="sxs-lookup"><span data-stu-id="c834e-110">Examples</span></span>
<span data-ttu-id="c834e-111"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="c834e-111"></span></span>

### <a name="example-1"></a><span data-ttu-id="c834e-112">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="c834e-112">Example 1</span></span>

<span data-ttu-id="c834e-113">Das folgende Beispiel zeigt den aktuellen Ordner, in dem Konfigurations-und Virtual Machine-Dateien von Cloud Connector-Komponenten gespeichert werden:</span><span class="sxs-lookup"><span data-stu-id="c834e-113">The following example shows the current folder where configuration and virtual machine files of Cloud Connector components are stored:</span></span>
  
```
Get-CcApplianceDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="c834e-114">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c834e-114">Detailed Description</span></span>
<span data-ttu-id="c834e-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="c834e-115"></span></span>

<span data-ttu-id="c834e-116">Das Cmdlet "Get-CcApplianceDirectory" zeigt an, wo alle Konfigurations-und virtuellen Computer Dateien,-Protokolle und externen Zertifikate für die Cloud Connector-Appliance gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="c834e-116">The Get-CcApplianceDirectory cmdlet shows where all configuration and virtual machine files, logs, and external certificates are stored for the Cloud Connector appliance.</span></span>
  
<span data-ttu-id="c834e-117">Jede Cloud Connector-Appliance verfügt über vier Komponenten: Mediationsserver, zentraler Verwaltungsspeicher, Edgeserver und einen Domänen Controller.</span><span class="sxs-lookup"><span data-stu-id="c834e-117">Each Cloud Connector appliance has four components: Mediation Server, Central Management Store, Edge Server, and a Domain Controller.</span></span> <span data-ttu-id="c834e-118">Der Standardordner lautet C:\Users\%USERPROFILE%\CloudConnector\ApplianceRoot.</span><span class="sxs-lookup"><span data-stu-id="c834e-118">The default folder is C:\Users\%userprofile%\CloudConnector\ApplianceRoot.</span></span> <span data-ttu-id="c834e-119">Sie können den Ordner mit dem Cmdlet „Set-CCApplianceDirectory“ ändern.</span><span class="sxs-lookup"><span data-stu-id="c834e-119">You can change this folder by using the Set-CCApplianceDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="c834e-120">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="c834e-120">Input Types</span></span>
<span data-ttu-id="c834e-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c834e-121"></span></span>

<span data-ttu-id="c834e-p104">Keine. Das Cmdlet „Get-CCApplianceDirectory“ akzeptiert keine Pipelineeingaben.</span><span class="sxs-lookup"><span data-stu-id="c834e-p104">None. The Get-CCApplianceDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="c834e-124">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="c834e-124">Return Types</span></span>
<span data-ttu-id="c834e-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c834e-125"></span></span>

<span data-ttu-id="c834e-126">Der Befehl gibt einen Dateipfad zurück.</span><span class="sxs-lookup"><span data-stu-id="c834e-126">The command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c834e-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c834e-127">See also</span></span>
<span data-ttu-id="c834e-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c834e-128"></span></span>

[<span data-ttu-id="c834e-129">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="c834e-129">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

