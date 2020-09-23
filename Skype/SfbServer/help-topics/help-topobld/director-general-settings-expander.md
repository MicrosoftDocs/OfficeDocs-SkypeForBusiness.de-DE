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
- CSH
ms.custom:
- ms.lync.tb.DirectorGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2026d0dd-6745-4e53-8b44-acdc378b47d1
description: 'Zum Bearbeiten der Einstellungen für einen vorhandenen Director werden die folgenden Abschnitte angezeigt:'
ms.openlocfilehash: 261593cd7b1f8f79588462cb57eb8ecc517dd4a3
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218986"
---
# <a name="director-general-settings-expander"></a><span data-ttu-id="e619c-103">Allgemeine Einstellungen für Director – Erweiterung</span><span class="sxs-lookup"><span data-stu-id="e619c-103">Director General Settings Expander</span></span>
 
<span data-ttu-id="e619c-104">Zum Bearbeiten der Einstellungen für einen vorhandenen Director werden die folgenden Abschnitte angezeigt:</span><span class="sxs-lookup"><span data-stu-id="e619c-104">To edit the settings for an existing Director, you are presented with the following sections:</span></span>
  
- <span data-ttu-id="e619c-105">Allgemeine Einstellungen</span><span class="sxs-lookup"><span data-stu-id="e619c-105">General settings</span></span>
    
- <span data-ttu-id="e619c-106">Webdienste</span><span class="sxs-lookup"><span data-stu-id="e619c-106">Web services</span></span>
    


## <a name="general-settings"></a><span data-ttu-id="e619c-107">Allgemeine Einstellungen</span><span class="sxs-lookup"><span data-stu-id="e619c-107">General settings</span></span>

<span data-ttu-id="e619c-p101">Vollqualifizierter Domänenname (FQDN) des Director-Pools. Bearbeiten Sie den FQDN des Servers, um den Wert zu ändern. Sie müssen über einen DNS-A-Eintrag (Domain Name System) verfügen, der mit dem neuen Wert übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="e619c-p101">Fully qualified domain name (FQDN) of the Director pool. Edit the FQDN of the server to change the value. You must have a Domain Name System (DNS) host (A) record that coincides with the new value.</span></span>
  
<span data-ttu-id="e619c-111">In **Zuordnungen** können Sie Folgendes bearbeiten oder angeben:</span><span class="sxs-lookup"><span data-stu-id="e619c-111">In **Associations** you can edit or specify the following:</span></span>
  
<span data-ttu-id="e619c-112">Dateifreigabe für den zu verwendenden Director-Pool.</span><span class="sxs-lookup"><span data-stu-id="e619c-112">File share for the Director pool to use.</span></span> <span data-ttu-id="e619c-113">Wählen Sie eine vorhandene Dateifreigabe aus, die bereits im Topologie-Generator definiert wurde, oder klicken Sie auf **neu** , um eine neue Dateifreigabe Definition zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e619c-113">Select an existing file share that has already been defined in Topology Builder, or click **New** to create a new file share definition.</span></span>
  
<span data-ttu-id="e619c-114">SQL Server-Speicher für Überwachung.</span><span class="sxs-lookup"><span data-stu-id="e619c-114">Monitoring SQL Server store.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e619c-p103">Vor Veröffentlichung der neu definierten Topologie muss der angegebene Server bereits vorhanden und der Domäne beigetreten sein. Wenn Sie eine neue Dateifreigabe erstellen, muss die Dateifreigabe auf dem angegebenen Server erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="e619c-p103">Before publishing the newly defined topology, the server that you specify must exist and be joined to the domain. If you created a new file share, the file share must be created on the server that you designate.</span></span> 
  
## <a name="web-services"></a><span data-ttu-id="e619c-117">Webdienste</span><span class="sxs-lookup"><span data-stu-id="e619c-117">Web services</span></span>

<span data-ttu-id="e619c-118">Wenn Sie zusätzliche Einstellungen für die Webdienste im Director-Pool bearbeiten oder angeben möchten, müssen Sie die Einstellungen in den internen und externen Webdiensten ändern oder angeben.</span><span class="sxs-lookup"><span data-stu-id="e619c-118">To edit or specify additional settings for the Web services on the Director pool, you modify or specify settings in the Internal Web services and External Web services.</span></span>
  
<span data-ttu-id="e619c-119">Für **Interne Webdienste** können Sie Folgendes angeben:</span><span class="sxs-lookup"><span data-stu-id="e619c-119">For **Internal web services** you can specify the following:</span></span>
  
> [!CAUTION]
> <span data-ttu-id="e619c-120">Wenn Sie mehr als eine Front-End-Pool oder Front-End-Server der FQDN der externen Webdienste eindeutig sein muss.</span><span class="sxs-lookup"><span data-stu-id="e619c-120">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="e619c-121">Wenn Sie beispielsweise den externen Webdienste-FQDN eines Front-End-Server als **pool01.contoso.com**definieren, können Sie **pool01.contoso.com** nicht für eine andere Front-End-Pool oder Front-End-Server verwenden.</span><span class="sxs-lookup"><span data-stu-id="e619c-121">For example, if you define the external Web services FQDN of a Front End Server as **pool01.contoso.com**, you cannot use **pool01.contoso.com** for another Front End pool or Front End Server.</span></span> <span data-ttu-id="e619c-122">Wenn Sie auch Directors bereitstellen, muss der FQDN für externe Webdienste, der für einen Director-oder Directorpool definiert ist, von einem anderen Director oder Directorpool sowie von Front-End-Pool oder Front-End-Server eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="e619c-122">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="e619c-123">Wenn Sie die internen Webdienste mit einem selbst definierten FQDN außer Kraft setzen möchten, muss jeder FQDN von jedem anderen Front-End-Pool, Director oder einem Directorpool eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="e619c-123">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>
  
<span data-ttu-id="e619c-p105">Wenn Sie die Außerkraftsetzung des FQDN wählen, können Sie einen anderen FQDN für die Identität der internen Webdienste im Pool angeben. In der Standardeinstellung entspricht die Einstellung dem aktuellen Poolnamen, der für den Director-Pool definiert ist.</span><span class="sxs-lookup"><span data-stu-id="e619c-p105">If you select Override FQDN, you can specify a different FQDN for the Internal Web services identity on the pool. By default, the setting is the current pool name as defined for the Director pool.</span></span>
  
<span data-ttu-id="e619c-p106">Sie können für die Bereitstellung erforderliche Überwachungs- und veröffentlichte Ports für HTTP und HTTPS angeben. Die Standardeinstellungen von Port 80 für HTTP und Port 443 für HTTPS sind die gängigsten Einstellungen und müssen in der Regel nicht geändert werden, es sei denn, in Ihrem Organisations- und Infrastrukturentwurf liegen besondere Anforderungen vor.</span><span class="sxs-lookup"><span data-stu-id="e619c-p106">You can specify listening and published ports for HTTP and HTTPS that your deployment requires. The default setting of port 80 for HTTP and port 443 for HTTPS are the most common settings and typically do not need to be changed unless you have specific requirements within your organization and infrastructure design.</span></span>
  
<span data-ttu-id="e619c-128">Für **Externe Webdienste** können Sie Folgendes angeben:</span><span class="sxs-lookup"><span data-stu-id="e619c-128">For **External web services**, you can specify the following:</span></span>
  
<span data-ttu-id="e619c-p107">Sie können den FQDN der externen Webdienste definieren. Der hier angegebene vollqualifizierte Domänenname wird meist von den externen Verbindungsanforderungen bestimmt, z. B. dem Reverseproxy.</span><span class="sxs-lookup"><span data-stu-id="e619c-p107">You can define the FQDN of the External Web services. The FQDN specified here will usually be defined by the requirements of your external connection requirements, such as the reverse proxy.</span></span>
  
<span data-ttu-id="e619c-p108">Sie können für die Bereitstellung erforderliche Überwachungs- und veröffentlichte Ports für HTTP und HTTPS angeben. Anfänglich sind die Standardeinstellungen (Port 8080 für HTTP und Port 4443 für HTTPS) definiert. Sie können diese Einstellungen für die Überwachungsports basierend auf den Anforderungen für den Reverseproxy und das externe Netzwerk ändern. Die veröffentlichten Ports sind auf die Standardeinstellungen Port 80 für HTTP und Port 443 für HTTPS festgelegt. Diese Werte bestimmen, an welchen Ports der Director-Pool oder Director-Server das System auf eingehende Anforderungen überwacht. Diese Werte müssen zumeist nicht geändert werden, es sei denn, es liegt ein Konflikt bei den Portanforderungen des Pools vor. Interne und externe veröffentlichte Ports mit denselben Portwerten werden erwartet. Dies stellt keinen Konflikt dar.</span><span class="sxs-lookup"><span data-stu-id="e619c-p108">You can specify listening and published ports for HTTP and HTTPS that your deployment requires. The default settings of port 8080 for HTTP and port 4443 for HTTPS are defined initially. You change these settings for the listening ports based on what the requirements are for your reverse proxy and external network requirements. The published ports are set to default of port 80 for HTTP and port 443 for HTTPS. These values determine what ports the Director pool or Director server will listen for incoming requests. Typically, these do not need to be changed, unless there is conflict of port requirements on the pool. Internal and external published ports that use the same port values are expected. This is not a conflict.</span></span>
  

