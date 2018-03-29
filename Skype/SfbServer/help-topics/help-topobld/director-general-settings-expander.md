---
title: Allgemeine Director Einstellungen – Erweiterung
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.DirectorGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2026d0dd-6745-4e53-8b44-acdc378b47d1
description: 'Zum Bearbeiten der Einstellungen für einen vorhandenen Director werden in den folgenden Abschnitten bearbeitet:'
ms.openlocfilehash: e806f917dbcfe3e626410d3bb76caad3c40ed5d3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="director-general-settings-expander"></a><span data-ttu-id="5f939-103">Allgemeine Director Einstellungen – Erweiterung</span><span class="sxs-lookup"><span data-stu-id="5f939-103">Director General Settings Expander</span></span>
 
<span data-ttu-id="5f939-104">Zum Bearbeiten der Einstellungen für einen vorhandenen Director werden in den folgenden Abschnitten bearbeitet:</span><span class="sxs-lookup"><span data-stu-id="5f939-104">To edit the settings for an existing Director, you are presented with the following sections:</span></span>
  
- <span data-ttu-id="5f939-105">Allgemeine Einstellungen</span><span class="sxs-lookup"><span data-stu-id="5f939-105">General settings</span></span>
    
- <span data-ttu-id="5f939-106">Webdienste</span><span class="sxs-lookup"><span data-stu-id="5f939-106">Web services</span></span>
    
## 

### <a name="general-settings"></a><span data-ttu-id="5f939-107">Allgemeine Einstellungen</span><span class="sxs-lookup"><span data-stu-id="5f939-107">General settings</span></span>

<span data-ttu-id="5f939-108">Vollqualifizierter Domänenname (FQDN) des Director-Pools.</span><span class="sxs-lookup"><span data-stu-id="5f939-108">Fully qualified domain name (FQDN) of the Director pool.</span></span> <span data-ttu-id="5f939-109">Bearbeiten Sie den FQDN des Servers, um den Wert zu ändern.</span><span class="sxs-lookup"><span data-stu-id="5f939-109">Edit the FQDN of the server to change the value.</span></span> <span data-ttu-id="5f939-110">Sie müssen über einen DNS-A-Eintrag (Domain Name System) verfügen, der mit dem neuen Wert übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="5f939-110">You must have a Domain Name System (DNS) host (A) record that coincides with the new value.</span></span>
  
<span data-ttu-id="5f939-111">In **Zuordnungen** können Sie Folgendes bearbeiten oder angeben:</span><span class="sxs-lookup"><span data-stu-id="5f939-111">In **Associations** you can edit or specify the following:</span></span>
  
<span data-ttu-id="5f939-112">Dateifreigabe für den Director-Pool verwenden.</span><span class="sxs-lookup"><span data-stu-id="5f939-112">File share for the Director pool to use.</span></span> <span data-ttu-id="5f939-113">Wählen Sie eine vorhandene Dateifreigabe, die bereits im Topologie-Generator definiert wurde, oder klicken Sie auf **neu** , um eine neue Datei freigeben Definition erstellen.</span><span class="sxs-lookup"><span data-stu-id="5f939-113">Select an existing file share that has already been defined in Topology Builder, or click **New** to create a new file share definition.</span></span>
  
<span data-ttu-id="5f939-114">Überwachen der SQL Server-Speicher.</span><span class="sxs-lookup"><span data-stu-id="5f939-114">Monitoring SQL Server store.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="5f939-115">Vor Veröffentlichung der neu definierten Topologie muss der angegebene Server bereits vorhanden und der Domäne beigetreten sein.</span><span class="sxs-lookup"><span data-stu-id="5f939-115">Before publishing the newly defined topology, the server that you specify must exist and be joined to the domain.</span></span> <span data-ttu-id="5f939-116">Wenn Sie eine neue Dateifreigabe erstellt haben, muss die Dateifreigabe auf dem Server erstellt werden, die Sie festlegen.</span><span class="sxs-lookup"><span data-stu-id="5f939-116">If you created a new file share, the file share must be created on the server that you designate.</span></span> 
  
### <a name="web-services"></a><span data-ttu-id="5f939-117">Webdienste</span><span class="sxs-lookup"><span data-stu-id="5f939-117">Web services</span></span>

<span data-ttu-id="5f939-118">Zum Bearbeiten, oder geben Sie zusätzliche Einstellungen für die Webdienste im Director-Pool, ändern oder Angeben von Einstellungen in der internen und externen Webdiensten.</span><span class="sxs-lookup"><span data-stu-id="5f939-118">To edit or specify additional settings for the Web services on the Director pool, you modify or specify settings in the Internal Web services and External Web services.</span></span>
  
<span data-ttu-id="5f939-119">Für die **interne Webdienste** können Sie Folgendes angeben:</span><span class="sxs-lookup"><span data-stu-id="5f939-119">For **Internal web services** you can specify the following:</span></span>
  
> [!CAUTION]
> <span data-ttu-id="5f939-120">Wenn Sie mehrere Front-End-Pool oder Front-End-Server verfügen muss die externen Webdienste FQDN eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="5f939-120">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="5f939-121">Wenn Sie die externen Webdienste-FQDN des Front-End-Server als **"pool01.contoso.com"**definieren, können nicht Sie beispielsweise **"pool01.contoso.com"** für einen anderen Front-End-Pool oder Front-End-Server verwenden.</span><span class="sxs-lookup"><span data-stu-id="5f939-121">For example, if you define the external Web services FQDN of a Front End Server as **pool01.contoso.com**, you cannot use **pool01.contoso.com** for another Front End pool or Front End Server.</span></span> <span data-ttu-id="5f939-122">Wenn Sie auch Director-Server bereitstellen, die externe Webdienste-FQDN für alle Director definierten oder Director-Pool muss aus einem anderen eindeutig sein Director oder Director-Pools sowie alle Front-End-Pool oder Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="5f939-122">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="5f939-123">Wenn Sie die internen Webdienste mit einem selbstdefinierten FQDN überschreiben möchten, muss jeder FQDN eines anderen Front-End-Pools, Director oder Director-Pool eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="5f939-123">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>
  
<span data-ttu-id="5f939-124">Wenn Sie den FQDN überschreiben auswählen, können Sie einen unterschiedlichen FQDN für die Identität der interne Web Services auf den Pool angeben.</span><span class="sxs-lookup"><span data-stu-id="5f939-124">If you select Override FQDN, you can specify a different FQDN for the Internal Web services identity on the pool.</span></span> <span data-ttu-id="5f939-125">Standardmäßig ist die Einstellung der aktuellen Poolname für den Director-Pool definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="5f939-125">By default, the setting is the current pool name as defined for the Director pool.</span></span>
  
<span data-ttu-id="5f939-126">Sie können überwachen und veröffentlichten Ports angeben, für HTTP und HTTPS, die Ihre Bereitstellung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="5f939-126">You can specify listening and published ports for HTTP and HTTPS that your deployment requires.</span></span> <span data-ttu-id="5f939-127">Die Standardeinstellung von Port 80 für HTTP und Port 443 für HTTPS sind die am häufigsten verwendeten Einstellungen und müssen in der Regel nicht geändert werden, wenn Sie spezifische Anforderungen innerhalb Ihrer Organisation und den Entwurf der Infrastruktur für verfügen.</span><span class="sxs-lookup"><span data-stu-id="5f939-127">The default setting of port 80 for HTTP and port 443 for HTTPS are the most common settings and typically do not need to be changed unless you have specific requirements within your organization and infrastructure design.</span></span>
  
<span data-ttu-id="5f939-128">Für **externe Webdienste**können Sie Folgendes angeben:</span><span class="sxs-lookup"><span data-stu-id="5f939-128">For **External web services**, you can specify the following:</span></span>
  
<span data-ttu-id="5f939-129">Sie können den FQDN der externen Webdienste definieren.</span><span class="sxs-lookup"><span data-stu-id="5f939-129">You can define the FQDN of the External Web services.</span></span> <span data-ttu-id="5f939-130">Der hier angegebene FQDN wird meist von den externen Verbindungsanforderungen bestimmt, z. B. dem Reverseproxy.</span><span class="sxs-lookup"><span data-stu-id="5f939-130">The FQDN specified here will usually be defined by the requirements of your external connection requirements, such as the reverse proxy.</span></span>
  
<span data-ttu-id="5f939-131">Sie können überwachen und veröffentlichten Ports angeben, für HTTP und HTTPS, die Ihre Bereitstellung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="5f939-131">You can specify listening and published ports for HTTP and HTTPS that your deployment requires.</span></span> <span data-ttu-id="5f939-132">Die Standardeinstellungen der Port 8080 für HTTP und Port 4443 für HTTPS werden zunächst definiert.</span><span class="sxs-lookup"><span data-stu-id="5f939-132">The default settings of port 8080 for HTTP and port 4443 for HTTPS are defined initially.</span></span> <span data-ttu-id="5f939-133">Sie können diese Einstellungen für die Überwachungsports basierend auf den Anforderungen für den Reverseproxy und das externe Netzwerk ändern.</span><span class="sxs-lookup"><span data-stu-id="5f939-133">You change these settings for the listening ports based on what the requirements are for your reverse proxy and external network requirements.</span></span> <span data-ttu-id="5f939-134">Die veröffentlichten Ports werden festgelegt auf Standardwert von Port 80 für HTTP und Port 443 für HTTPS.</span><span class="sxs-lookup"><span data-stu-id="5f939-134">The published ports are set to default of port 80 for HTTP and port 443 for HTTPS.</span></span> <span data-ttu-id="5f939-135">Diese Werte bestimmen, welche Ports für eingehende Anforderungen den Director-Pool oder Director-Server überwacht wird.</span><span class="sxs-lookup"><span data-stu-id="5f939-135">These values determine what ports the Director pool or Director server will listen for incoming requests.</span></span> <span data-ttu-id="5f939-136">In der Regel müssen diese nicht geändert werden, es sei denn, der Anforderungen in Bezug auf den Pool Konflikt vorliegt.</span><span class="sxs-lookup"><span data-stu-id="5f939-136">Typically, these do not need to be changed, unless there is conflict of port requirements on the pool.</span></span> <span data-ttu-id="5f939-137">Interne und externe veröffentlichten Ports, die dieselben Portwerte wie verwenden sollten.</span><span class="sxs-lookup"><span data-stu-id="5f939-137">Internal and external published ports that use the same port values are expected.</span></span> <span data-ttu-id="5f939-138">Dies ist kein Konflikt.</span><span class="sxs-lookup"><span data-stu-id="5f939-138">This is not a conflict.</span></span>
  

