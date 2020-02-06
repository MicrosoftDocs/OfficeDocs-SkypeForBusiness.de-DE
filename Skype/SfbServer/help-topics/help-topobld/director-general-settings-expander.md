---
title: Allgemeine Einstellungen für Director – Erweiterung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.DirectorGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2026d0dd-6745-4e53-8b44-acdc378b47d1
description: 'Wenn Sie die Einstellungen für einen vorhandenen Director bearbeiten möchten, werden Ihnen die folgenden Abschnitte angezeigt:'
ms.openlocfilehash: e6fb587484cd4024e69c8630e49f95a978ec747a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820127"
---
# <a name="director-general-settings-expander"></a><span data-ttu-id="aa451-103">Allgemeine Einstellungen für Director – Erweiterung</span><span class="sxs-lookup"><span data-stu-id="aa451-103">Director General Settings Expander</span></span>
 
<span data-ttu-id="aa451-104">Wenn Sie die Einstellungen für einen vorhandenen Director bearbeiten möchten, werden Ihnen die folgenden Abschnitte angezeigt:</span><span class="sxs-lookup"><span data-stu-id="aa451-104">To edit the settings for an existing Director, you are presented with the following sections:</span></span>
  
- <span data-ttu-id="aa451-105">Allgemeine Einstellungen</span><span class="sxs-lookup"><span data-stu-id="aa451-105">General settings</span></span>
    
- <span data-ttu-id="aa451-106">Webdienste</span><span class="sxs-lookup"><span data-stu-id="aa451-106">Web services</span></span>
    


## <a name="general-settings"></a><span data-ttu-id="aa451-107">Allgemeine Einstellungen</span><span class="sxs-lookup"><span data-stu-id="aa451-107">General settings</span></span>

<span data-ttu-id="aa451-108">Vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Director-Pools.</span><span class="sxs-lookup"><span data-stu-id="aa451-108">Fully qualified domain name (FQDN) of the Director pool.</span></span> <span data-ttu-id="aa451-109">Bearbeiten Sie den FQDN des Servers, um den Wert zu ändern.</span><span class="sxs-lookup"><span data-stu-id="aa451-109">Edit the FQDN of the server to change the value.</span></span> <span data-ttu-id="aa451-110">Sie müssen über einen DNS-A-Eintrag (Domain Name System) verfügen, der mit dem neuen Wert übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="aa451-110">You must have a Domain Name System (DNS) host (A) record that coincides with the new value.</span></span>
  
<span data-ttu-id="aa451-111">In **Zuordnungen** können Sie Folgendes bearbeiten oder angeben:</span><span class="sxs-lookup"><span data-stu-id="aa451-111">In **Associations** you can edit or specify the following:</span></span>
  
<span data-ttu-id="aa451-112">Dateifreigabe, die der Director-Pool verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="aa451-112">File share for the Director pool to use.</span></span> <span data-ttu-id="aa451-113">Wählen Sie eine vorhandene Dateifreigabe aus, die bereits im Topologie-Generator definiert wurde, oder klicken Sie auf **neu** , um eine neue Dateifreigabe Definition zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="aa451-113">Select an existing file share that has already been defined in Topology Builder, or click **New** to create a new file share definition.</span></span>
  
<span data-ttu-id="aa451-114">Überwachen des SQL Server-Speichers</span><span class="sxs-lookup"><span data-stu-id="aa451-114">Monitoring SQL Server store.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="aa451-115">Vor Veröffentlichung der neu definierten Topologie muss der angegebene Server bereits vorhanden und der Domäne beigetreten sein.</span><span class="sxs-lookup"><span data-stu-id="aa451-115">Before publishing the newly defined topology, the server that you specify must exist and be joined to the domain.</span></span> <span data-ttu-id="aa451-116">Wenn Sie eine neue Dateifreigabe erstellt haben, muss die Dateifreigabe auf dem von Ihnen festgelegten Server erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="aa451-116">If you created a new file share, the file share must be created on the server that you designate.</span></span> 
  
## <a name="web-services"></a><span data-ttu-id="aa451-117">Webdienste</span><span class="sxs-lookup"><span data-stu-id="aa451-117">Web services</span></span>

<span data-ttu-id="aa451-118">Zum Bearbeiten oder angeben zusätzlicher Einstellungen für die Webdienste im Director-Pool ändern oder spezifizieren Sie die Einstellungen in den internen Webdiensten und externen Webdiensten.</span><span class="sxs-lookup"><span data-stu-id="aa451-118">To edit or specify additional settings for the Web services on the Director pool, you modify or specify settings in the Internal Web services and External Web services.</span></span>
  
<span data-ttu-id="aa451-119">Bei **internen Webdiensten** können Sie Folgendes angeben:</span><span class="sxs-lookup"><span data-stu-id="aa451-119">For **Internal web services** you can specify the following:</span></span>
  
> [!CAUTION]
> <span data-ttu-id="aa451-120">Wenn Sie über mehr als einen Front-End-Pool oder Front-End-Server verfügen, muss der FQDN der externen Webdienste eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="aa451-120">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="aa451-121">Wenn Sie beispielsweise den FQDN eines externen Webdiensts eines Front-End-Servers als **pool01.contoso.com**definieren, können Sie **pool01.contoso.com** nicht für einen anderen Front-End-Pool oder Front-End-Server verwenden.</span><span class="sxs-lookup"><span data-stu-id="aa451-121">For example, if you define the external Web services FQDN of a Front End Server as **pool01.contoso.com**, you cannot use **pool01.contoso.com** for another Front End pool or Front End Server.</span></span> <span data-ttu-id="aa451-122">Wenn Sie Directors auch bereitstellen, müssen die für Director-oder Director-Pools definierten externen Webdienst-FQDN für jeden anderen Director-oder Director-Pool sowie für jeden Front-End-Pool oder Front-End-Server eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="aa451-122">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="aa451-123">Wenn Sie sich entscheiden, die internen Webdienste mit einem selbst definierten FQDN zu überschreiben, muss jeder FQDN für jeden anderen Front-End-Pool, Director oder Director-Pool eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="aa451-123">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>
  
<span data-ttu-id="aa451-124">Wenn Sie Vollqualifizierten Domänennamen außer Kraft setzen auswählen, können Sie einen anderen FQDN für die Identität Interne Webdienste im Pool angeben.</span><span class="sxs-lookup"><span data-stu-id="aa451-124">If you select Override FQDN, you can specify a different FQDN for the Internal Web services identity on the pool.</span></span> <span data-ttu-id="aa451-125">Standardmäßig ist die Einstellung der Name des aktuellen Pools, wie er für den Director-Pool definiert ist.</span><span class="sxs-lookup"><span data-stu-id="aa451-125">By default, the setting is the current pool name as defined for the Director pool.</span></span>
  
<span data-ttu-id="aa451-126">Sie können Überwachungs-und veröffentlichte Ports für http und HTTPS angeben, die für die Bereitstellung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="aa451-126">You can specify listening and published ports for HTTP and HTTPS that your deployment requires.</span></span> <span data-ttu-id="aa451-127">Die Standardeinstellung von Port 80 für http und Port 443 für HTTPS sind die am häufigsten verwendeten Einstellungen, die normalerweise nicht geändert werden müssen, es sei denn, Sie verfügen über bestimmte Anforderungen innerhalb Ihres Unternehmens-und Infrastruktur Designs.</span><span class="sxs-lookup"><span data-stu-id="aa451-127">The default setting of port 80 for HTTP and port 443 for HTTPS are the most common settings and typically do not need to be changed unless you have specific requirements within your organization and infrastructure design.</span></span>
  
<span data-ttu-id="aa451-128">Bei **externen Webdiensten**können Sie Folgendes angeben:</span><span class="sxs-lookup"><span data-stu-id="aa451-128">For **External web services**, you can specify the following:</span></span>
  
<span data-ttu-id="aa451-129">Sie können den FQDN der externen Webdienste definieren.</span><span class="sxs-lookup"><span data-stu-id="aa451-129">You can define the FQDN of the External Web services.</span></span> <span data-ttu-id="aa451-130">Der hier angegebene FQDN wird meist von den externen Verbindungsanforderungen bestimmt, z. B. dem Reverseproxy.</span><span class="sxs-lookup"><span data-stu-id="aa451-130">The FQDN specified here will usually be defined by the requirements of your external connection requirements, such as the reverse proxy.</span></span>
  
<span data-ttu-id="aa451-131">Sie können Überwachungs-und veröffentlichte Ports für http und HTTPS angeben, die für die Bereitstellung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="aa451-131">You can specify listening and published ports for HTTP and HTTPS that your deployment requires.</span></span> <span data-ttu-id="aa451-132">Die Standardeinstellungen von Port 8080 für http und Port 4443 für HTTPS werden zunächst definiert.</span><span class="sxs-lookup"><span data-stu-id="aa451-132">The default settings of port 8080 for HTTP and port 4443 for HTTPS are defined initially.</span></span> <span data-ttu-id="aa451-133">Sie können diese Einstellungen für die Überwachungsports basierend auf den Anforderungen für den Reverseproxy und das externe Netzwerk ändern.</span><span class="sxs-lookup"><span data-stu-id="aa451-133">You change these settings for the listening ports based on what the requirements are for your reverse proxy and external network requirements.</span></span> <span data-ttu-id="aa451-134">Die veröffentlichten Ports sind auf Standard Port 80 für http und Port 443 für HTTPS eingestellt.</span><span class="sxs-lookup"><span data-stu-id="aa451-134">The published ports are set to default of port 80 for HTTP and port 443 for HTTPS.</span></span> <span data-ttu-id="aa451-135">Diese Werte legen fest, welche Ports der Director-Pool oder Director-Server auf eingehende Anforderungen überwacht.</span><span class="sxs-lookup"><span data-stu-id="aa451-135">These values determine what ports the Director pool or Director server will listen for incoming requests.</span></span> <span data-ttu-id="aa451-136">In der Regel müssen diese nicht geändert werden, es sei denn, es gibt einen Konflikt zwischen den Portanforderungen im Pool.</span><span class="sxs-lookup"><span data-stu-id="aa451-136">Typically, these do not need to be changed, unless there is conflict of port requirements on the pool.</span></span> <span data-ttu-id="aa451-137">Interne und externe veröffentlichte Ports, die die gleichen Portwerte verwenden, werden erwartet.</span><span class="sxs-lookup"><span data-stu-id="aa451-137">Internal and external published ports that use the same port values are expected.</span></span> <span data-ttu-id="aa451-138">Dies ist kein Konflikt.</span><span class="sxs-lookup"><span data-stu-id="aa451-138">This is not a conflict.</span></span>
  

