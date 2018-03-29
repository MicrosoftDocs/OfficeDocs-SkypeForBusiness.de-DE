---
title: Get-CcApplianceDirectory
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c2fda202-db2f-4122-b630-7df11a697c5f
description: 'Das Cmdlet „Get-CcApplianceDirectory“ ruft das Arbeitsverzeichnis auf dem Hostserver von Skype for Business Cloud Connector Edition ab. In diesem Verzeichnis werden alle Bereitstellungsdateien gespeichert. '
ms.openlocfilehash: c5c445e6017d8af81b681b70bbabcf2ba8bedd78
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="get-ccappliancedirectory"></a><span data-ttu-id="62c6c-104">Get-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="62c6c-104">Get-CcApplianceDirectory</span></span>
 
<span data-ttu-id="62c6c-p102">Das Cmdlet „Get-CcApplianceDirectory“ ruft das Arbeitsverzeichnis auf dem Hostserver von Skype for Business Cloud Connector Edition ab. In diesem Verzeichnis werden alle Bereitstellungsdateien gespeichert. </span><span class="sxs-lookup"><span data-stu-id="62c6c-p102">The Get-CcApplianceDirectory cmdlet retrieves the working directory on the Skype for Business Cloud Connector Edition host server. All deployment files are stored in this directory.</span></span> 
  
<span data-ttu-id="62c6c-107">Dieses Cmdlet gilt für Skype for Business Cloud Connector Edition 1.4.1 und 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="62c6c-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Get-CcApplianceDirectory
```

## <a name="parameters"></a><span data-ttu-id="62c6c-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="62c6c-108">Parameters</span></span>

<span data-ttu-id="62c6c-109">Keine</span><span class="sxs-lookup"><span data-stu-id="62c6c-109">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="62c6c-110">Beispiele</span><span class="sxs-lookup"><span data-stu-id="62c6c-110">Examples</span></span>
<span data-ttu-id="62c6c-111"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="62c6c-111"></span></span>

### <a name="example-1"></a><span data-ttu-id="62c6c-112">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="62c6c-112">Example 1</span></span>

<span data-ttu-id="62c6c-113">Im folgenden Beispiel wird den aktuellen Ordner, in dem Konfiguration und dem virtuellen Computer Dateien Cloud Connector Komponenten gespeichert sind:</span><span class="sxs-lookup"><span data-stu-id="62c6c-113">The following example shows the current folder where configuration and virtual machine files of Cloud Connector components are stored:</span></span>
  
```
Get-CcApplianceDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="62c6c-114">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="62c6c-114">Detailed Description</span></span>
<span data-ttu-id="62c6c-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="62c6c-115"></span></span>

<span data-ttu-id="62c6c-116">Das Cmdlet Get-CcApplianceDirectory veranschaulicht, in dem alle Konfigurations-und virtuellen Computer, Protokolle und externe Zertifikate für die Cloud Connector Appliance gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="62c6c-116">The Get-CcApplianceDirectory cmdlet shows where all configuration and virtual machine files, logs, and external certificates are stored for the Cloud Connector appliance.</span></span>
  
<span data-ttu-id="62c6c-117">Jede Appliance Cloud Connector besteht aus vier Komponenten: Vermittlungsserver, zentralen Verwaltungsspeichers, Edge-Server und einem Domänencontroller.</span><span class="sxs-lookup"><span data-stu-id="62c6c-117">Each Cloud Connector appliance has four components: Mediation Server, Central Management Store, Edge Server, and a Domain Controller.</span></span> <span data-ttu-id="62c6c-118">Der Standardordner ist C:\Users\%userprofile%\CloudConnector\ApplianceRoot.</span><span class="sxs-lookup"><span data-stu-id="62c6c-118">The default folder is C:\Users\%userprofile%\CloudConnector\ApplianceRoot.</span></span> <span data-ttu-id="62c6c-119">Sie können den Ordner mit dem Cmdlet „Set-CCApplianceDirectory“ ändern.</span><span class="sxs-lookup"><span data-stu-id="62c6c-119">You can change this folder by using the Set-CCApplianceDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="62c6c-120">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="62c6c-120">Input Types</span></span>
<span data-ttu-id="62c6c-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="62c6c-121"></span></span>

<span data-ttu-id="62c6c-p104">Keine. Das Cmdlet „Get-CCApplianceDirectory“ akzeptiert keine Pipelineeingaben.</span><span class="sxs-lookup"><span data-stu-id="62c6c-p104">None. The Get-CCApplianceDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="62c6c-124">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="62c6c-124">Return Types</span></span>
<span data-ttu-id="62c6c-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="62c6c-125"></span></span>

<span data-ttu-id="62c6c-126">Der Befehl gibt einen Dateipfad zurück.</span><span class="sxs-lookup"><span data-stu-id="62c6c-126">The command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="62c6c-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="62c6c-127">See also</span></span>
<span data-ttu-id="62c6c-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="62c6c-128"></span></span>

[<span data-ttu-id="62c6c-129">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="62c6c-129">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

