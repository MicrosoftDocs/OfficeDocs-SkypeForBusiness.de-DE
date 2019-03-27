---
title: Deaktivieren Sie TLS 1.0/1.1 in Skype für Business Server 2015
ms.reviewer: ''
ms.author: heidip
author: heidip
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Zusammenfassung: Vorbereiten Sie und implementieren Sie in Ihren Umgebungen deaktivieren TLS 1.0 und 1.1.'
ms.openlocfilehash: c10be59bb3e14ccb0a3ac315891789e8a0e2ce64
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30886603"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a><span data-ttu-id="c6034-103">Deaktivieren Sie TLS 1.0/1.1 in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="c6034-103">Disable TLS 1.0/1.1 in Skype for Business Server 2015</span></span>

<span data-ttu-id="c6034-104">Der Zweck dieses Artikels ist der erforderlichen Richtlinien für die Sie zum Vorbereiten und implementieren Sie deaktivieren TLS 1.0 und 1.1 in Ihrer Umgebung bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="c6034-104">The purpose of this article is to provide the necessary guidance for you to prepare for and implement disabling TLS 1.0 and 1.1 in your environments.</span></span> <span data-ttu-id="c6034-105">Dieser Prozess erfordert umfassende Planung und Vorbereitung.</span><span class="sxs-lookup"><span data-stu-id="c6034-105">This process requires extensive planning and preparation.</span></span> <span data-ttu-id="c6034-106">Lesen Sie bitte aufmerksam sämtliche Informationen in diesem Artikel, wie Sie Ihren Plan Deaktivieren von TLS 1.0 und 1.1 für Ihre Organisation vornehmen.</span><span class="sxs-lookup"><span data-stu-id="c6034-106">Please carefully review all of the information in this article as you make your plan to disable TLS 1.0 and 1.1 for your organization.</span></span> <span data-ttu-id="c6034-107">Beachten Sie, dass es gibt viele externe Abhängigkeiten und Konnektivität Bedingungen, die durch das Deaktivieren von TLS 1.0/1.1 beeinträchtigt werden könnte, so stark planen und Testen garantiert ist.</span><span class="sxs-lookup"><span data-stu-id="c6034-107">Note that there are many external dependencies and connectivity conditions that could be impacted by disabling TLS 1.0/1.1, so extensive planning and testing is warranted.</span></span>

## <a name="in-this-article"></a><span data-ttu-id="c6034-108">In diesem Artikel</span><span class="sxs-lookup"><span data-stu-id="c6034-108">In this article</span></span>

- [<span data-ttu-id="c6034-109">Hintergrund und des Umfangs</span><span class="sxs-lookup"><span data-stu-id="c6034-109">Background and scope</span></span>](#background)
- [<span data-ttu-id="c6034-110">Erforderliche Komponenten und verarbeiten</span><span class="sxs-lookup"><span data-stu-id="c6034-110">Prerequisites and process</span></span>](#prerequisites-and-process)
- [<span data-ttu-id="c6034-111">Erweiterte Bereitstellungsszenarien</span><span class="sxs-lookup"><span data-stu-id="c6034-111">Advanced deployment scenarios</span></span>](#advanced-deployment-scenarios)

## <a name="background"></a><span data-ttu-id="c6034-112">Hintergrund</span><span class="sxs-lookup"><span data-stu-id="c6034-112">Background</span></span>

<span data-ttu-id="c6034-113">Die primäre Treiber für die Bereitstellung von TLS 1.0 und 1.1 Disable-Unterstützung für Skype für Business Server lokal sind Payment Card Industry (PCI) Security Standards Council und Federal Information Processing Standards (engl.).</span><span class="sxs-lookup"><span data-stu-id="c6034-113">The primary drivers for providing TLS 1.0 and 1.1 disable support for Skype for Business Server On-Premises are Payment Card Industry (PCI) Security Standards Council and Federal Information Processing Standards requirements.</span></span> <span data-ttu-id="c6034-114">Weitere Informationen für PCI-Anforderungen finden Sie [hier](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).</span><span class="sxs-lookup"><span data-stu-id="c6034-114">More information for PCI requirements can be found [here](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).</span></span>  <span data-ttu-id="c6034-115">Microsoft kann nicht Hilfestellung für unabhängig davon, ob Ihre Organisation erforderlich ist, diese oder anderen Vorschriften einhalten.</span><span class="sxs-lookup"><span data-stu-id="c6034-115">Microsoft cannot provide guidance on whether or not your organization is required to adhere to these or other requirements.</span></span> <span data-ttu-id="c6034-116">Sie müssen ermitteln, ob es für TLS 1.0 und/oder 1.1 in Ihren Umgebungen deaktivieren erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="c6034-116">You must determine if it is required for you to disable TLS 1.0 and/or 1.1 in your environments.</span></span>

<span data-ttu-id="c6034-117">Microsoft hat ein Whitepaper über TLS verfügbaren [hier](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)hergestellt und sollten auch im Hintergrund Lesen in diesen [Exchange-Blog](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c6034-117">Microsoft has produced a white paper on TLS available [here](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/), and we also recommend the background reading available in this [Exchange blog](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).</span></span>

## <a name="supportability-scope"></a><span data-ttu-id="c6034-118">Support-Bereich</span><span class="sxs-lookup"><span data-stu-id="c6034-118">Supportability Scope</span></span>

<span data-ttu-id="c6034-119">*Bereich* bezieht sich auf unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c6034-119">*Scope* refers to supportability boundaries.</span></span> <span data-ttu-id="c6034-120">Für Skype für Business Server lokal bedeutet, dass *im Bereich* wir vollständig unterstützen, und Deaktivieren der TLS 1.0 und 1.1 für die aufgeführten Produktversionen getestet.</span><span class="sxs-lookup"><span data-stu-id="c6034-120">For Skype for Business Server On-Premises, *in scope* means we fully support and have tested disabling of TLS 1.0 and 1.1 for the listed product versions.</span></span> <span data-ttu-id="c6034-121">*Derzeit untersuchten* bedeutet, dass nur die; Wir sind aktiv untersuchen, verwenden Sie diese Produkte in den Bereich aus, für TLS-Unterstützung deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="c6034-121">*Currently being investigated* means just that; we are actively investigating bringing these products into scope for TLS disable support.</span></span> <span data-ttu-id="c6034-122">*Außerhalb des Gültigkeitsbereichs* bedeutet, dass diese Produktversionen deaktivieren TLS 1.0 oder 1.1 nicht unterstützt und funktioniert nicht, mit Ausnahmefällen.</span><span class="sxs-lookup"><span data-stu-id="c6034-122">*Out of scope* means these product versions do not support disabling TLS 1.0 or 1.1 and will not work, with noted exceptions.</span></span>

### <a name="fully-tested-and-supported-servers"></a><span data-ttu-id="c6034-123">Vollständig getesteten und unterstützten Server</span><span class="sxs-lookup"><span data-stu-id="c6034-123">Fully tested and supported servers</span></span>

- <span data-ttu-id="c6034-124">Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="c6034-124">Skype for Business Server 2019</span></span>
- <span data-ttu-id="c6034-125">Skype für Business Server 2015 CU6 HF2 6.0.9319.516 ([update März 2018](https://support.microsoft.com/en-us/help/4086059/march-2018-cumulative-update-6-0-9319-516-for-skype-for-business)) und höher auf:</span><span class="sxs-lookup"><span data-stu-id="c6034-125">Skype for Business Server 2015 CU6 HF2 6.0.9319.516 ([March 2018 update](https://support.microsoft.com/en-us/help/4086059/march-2018-cumulative-update-6-0-9319-516-for-skype-for-business)) and higher on:</span></span> 
    - <span data-ttu-id="c6034-126">Windows Server 2012 (mit KB 3140245 oder vorrangiges Update), 2012 R2 oder 2016</span><span class="sxs-lookup"><span data-stu-id="c6034-126">Windows Server 2012 (with KB 3140245 or superseding update), 2012 R2 or 2016</span></span>
- <span data-ttu-id="c6034-127">In-Place Upgrade Skype für Business Server 2015 mit CU6 HF2 und höher auf</span><span class="sxs-lookup"><span data-stu-id="c6034-127">In-place Upgraded Skype for Business Server 2015, with CU6 HF2 and higher on</span></span> 
    - <span data-ttu-id="c6034-128">Windows Server 2008 R2, 2012 (mit KB [3140245](https://support.microsoft.com/en-us/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) oder vorrangiges Update) oder 2012 R2</span><span class="sxs-lookup"><span data-stu-id="c6034-128">Windows Server 2008 R2, 2012 (with KB [3140245](https://support.microsoft.com/en-us/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), or 2012 R2</span></span>
- <span data-ttu-id="c6034-129">Exchange-Diensten und Outlook Web App mit RU19 von Exchange Server 2010 SP3 oder höher, Anleitung [hier](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span><span class="sxs-lookup"><span data-stu-id="c6034-129">Exchange Connectivity and Outlook Web App with Exchange Server 2010 SP3 RU19 or higher, guidance [here](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span></span>
- <span data-ttu-id="c6034-130">Survivable Branch Appliance (SBA) mit Skype für Business Server 2015 CU6 HF2 oder höher (Vergewissern Sie sich mit Ihrem Lieferanten, dass sie die geeignete Updates gepackt und für Ihre Anwendung zur Verfügung gestellt wurde haben)</span><span class="sxs-lookup"><span data-stu-id="c6034-130">Survivable Branch Appliance (SBA) with Skype for Business Server 2015 CU6 HF2 or higher (confirm with your vendor that they packaged the appropiate updates and have been made available for your appliance)</span></span>
- <span data-ttu-id="c6034-131">Survivable Branch Server (SBS) mit Skype für Business Server 2015 CU6 HF2 oder höher</span><span class="sxs-lookup"><span data-stu-id="c6034-131">Survivable Branch Server (SBS) with Skype for Business Server 2015 CU6 HF2 or higher</span></span>
- <span data-ttu-id="c6034-132">Dies ist Lync Server 2013 **Edge Rolle nur**, da edgerolle eine Abhängigkeit nicht auf Windows Fabric 1.0 verfügt.</span><span class="sxs-lookup"><span data-stu-id="c6034-132">Lync Server 2013 **Edge Role Only**, this is because Edge role does not have a dependency on Windows Fabric 1.0.</span></span>


### <a name="fully-tested-and-supported-clients"></a><span data-ttu-id="c6034-133">Vollständig getestete und unterstützte clients</span><span class="sxs-lookup"><span data-stu-id="c6034-133">Fully tested and supported clients</span></span>

- <span data-ttu-id="c6034-134">Lync 2013 (Skype für Unternehmen) Desktopclient, MSI und C2R, einschließlich Basic [15.0.5023.1000 und höher](https://support.microsoft.com/en-us/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span><span class="sxs-lookup"><span data-stu-id="c6034-134">Lync 2013 (Skype for Business) Desktop Client, MSI and C2R, including Basic [15.0.5023.1000 and higher](https://support.microsoft.com/en-us/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span></span>
- <span data-ttu-id="c6034-135">Skype für Business 2016 Desktop Client MSI [16.0.4678.1000 und höher](https://support.microsoft.com/en-us/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), einschließlich Basic</span><span class="sxs-lookup"><span data-stu-id="c6034-135">Skype for Business 2016 Desktop Client, MSI [16.0.4678.1000 and higher](https://support.microsoft.com/en-us/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), including Basic</span></span>
- <span data-ttu-id="c6034-136">Skype für Business 2016 klicken Sie auf Ausführen, sind die [April 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) -Updates erforderlich:</span><span class="sxs-lookup"><span data-stu-id="c6034-136">Skype for Business 2016 Click to Run Require the [April 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) Updates:</span></span> 
    - <span data-ttu-id="c6034-137">Monatliche und Semikolons pro Jahr als Ziel, 16\.0\.9126\.2152 und höher</span><span class="sxs-lookup"><span data-stu-id="c6034-137">Monthly and Semi-Annual Targeted, 16\.0\.9126\.2152 and higher</span></span>
    - <span data-ttu-id="c6034-138">Semikolons jährlichen und zurückgestellt Kanal, 16\.0\.8431\.2242 und höher</span><span class="sxs-lookup"><span data-stu-id="c6034-138">Semi-Annual and Deferred Channel, 16\.0\.8431\.2242 and higher</span></span>
- <span data-ttu-id="c6034-139">Skype für Unternehmen auf Mac 16.15 und höher</span><span class="sxs-lookup"><span data-stu-id="c6034-139">Skype for Business on Mac 16.15 and higher</span></span>
- <span data-ttu-id="c6034-140">Skype für geschäftliche für iOS und Android 6.19 und höher</span><span class="sxs-lookup"><span data-stu-id="c6034-140">Skype for Business for iOS and Android 6.19 and higher</span></span>
- <span data-ttu-id="c6034-141">Skype Web App 2015 CU6 HF2 und höher (im Lieferumfang von Server)</span><span class="sxs-lookup"><span data-stu-id="c6034-141">Skype Web App 2015 CU6 HF2 and higher (ships with Server)</span></span>

### <a name="currently-being-investigated"></a><span data-ttu-id="c6034-142">Derzeit untersuchten</span><span class="sxs-lookup"><span data-stu-id="c6034-142">Currently being investigated</span></span>

#### <a name="devices"></a><span data-ttu-id="c6034-143">Geräte</span><span class="sxs-lookup"><span data-stu-id="c6034-143">Devices</span></span>

- <span data-ttu-id="c6034-144">Lync-Chatroom-System (auch bekannt als</span><span class="sxs-lookup"><span data-stu-id="c6034-144">Lync Room System (a.k.a.</span></span> <span data-ttu-id="c6034-145">SRSv1)</span><span class="sxs-lookup"><span data-stu-id="c6034-145">SRSv1)</span></span>
- <span data-ttu-id="c6034-146">Skype-Chatroom-Systemen v2 (auch bekannt als</span><span class="sxs-lookup"><span data-stu-id="c6034-146">Skype Room Systems v2 (a.k.a.</span></span> <span data-ttu-id="c6034-147">SRSv2)</span><span class="sxs-lookup"><span data-stu-id="c6034-147">SRSv2)</span></span>
- <span data-ttu-id="c6034-148">Surface Hub</span><span class="sxs-lookup"><span data-stu-id="c6034-148">Surface Hub</span></span>
- <span data-ttu-id="c6034-149">2015 basieren Survivable Branch Appliance (SBA) oder Survivable Branch Server (SBS)</span><span class="sxs-lookup"><span data-stu-id="c6034-149">2015 based Survivable Branch Appliance (SBA) or Survivable Branch Server (SBS)</span></span>

#### <a name="other"></a><span data-ttu-id="c6034-150">Andere</span><span class="sxs-lookup"><span data-stu-id="c6034-150">Other</span></span>

- <span data-ttu-id="c6034-151">Rufen Sie Quality Dashboard (neue Installation nach TLS 1.0, 1.1 deaktiviert wurden, finden Sie weiter unten) \*</span><span class="sxs-lookup"><span data-stu-id="c6034-151">Call Quality Dashboard (new install after TLS 1.0, 1.1 have been disabled, see below)\*</span></span>
 
### <a name="out-of-scope"></a><span data-ttu-id="c6034-152">Außerhalb des Gültigkeitsbereichs</span><span class="sxs-lookup"><span data-stu-id="c6034-152">Out of scope</span></span>

<span data-ttu-id="c6034-153">Wenn nicht anders angegeben die folgenden Produkte sind nicht im Gültigkeitsbereich für die Unterstützung für TLS 1.0/1.1 deaktivieren und funktioniert nicht in einer Umgebung, in dem TLS 1.0 und 1.1 deaktiviert wurden.</span><span class="sxs-lookup"><span data-stu-id="c6034-153">Except where noted, the following products are not in scope for TLS 1.0/1.1 disable support and will not function in an environment where TLS 1.0 and 1.1 have been disabled.</span></span>  <span data-ttu-id="c6034-154">Dies bedeutet: Wenn Sie dennoch außerhalb des Bereichs Servern oder Clients nutzen, müssen Sie aktualisieren oder entfernen Sie diese Option, wenn Sie TLS 1.0/1.1 an einer beliebigen Stelle in Ihrem Skype für Business Server-Bereitstellung lokal nicht deaktiviert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="c6034-154">What this means: if you still utilize out-of-scope servers or clients, you must update or remove these if you need to disable TLS 1.0/1.1 anywhere in your Skype for Business Server on-premises deployment.</span></span>

- <span data-ttu-id="c6034-155">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6034-155">Lync Server 2013</span></span>
- <span data-ttu-id="c6034-156">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="c6034-156">Lync Server 2010</span></span>
- <span data-ttu-id="c6034-157">WindowsServer 2008 als auch eine untere</span><span class="sxs-lookup"><span data-stu-id="c6034-157">Windows Server 2008 and lower</span></span>
- <span data-ttu-id="c6034-158">Lync für Mac 2011</span><span class="sxs-lookup"><span data-stu-id="c6034-158">Lync for Mac 2011</span></span>
- <span data-ttu-id="c6034-159">Lync 2013 für Mobile - iOS, iPad, Android oder Windows Phone</span><span class="sxs-lookup"><span data-stu-id="c6034-159">Lync 2013 for Mobile - iOS, iPad, Android or Windows Phone</span></span>
- <span data-ttu-id="c6034-160">Lync "MX" Windows Store-client</span><span class="sxs-lookup"><span data-stu-id="c6034-160">Lync "MX" Windows Store client</span></span>
- <span data-ttu-id="c6034-161">Alle Lync 2010-clients</span><span class="sxs-lookup"><span data-stu-id="c6034-161">All Lync 2010 clients</span></span>
- <span data-ttu-id="c6034-162">Lync Phone Edition - aktualisierter Leitfaden [hier](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).</span><span class="sxs-lookup"><span data-stu-id="c6034-162">Lync Phone Edition - updated guidance [here](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).</span></span>
- <span data-ttu-id="c6034-163">2013 basierte Survivable Branch Appliance (SBA) oder Survivable Branch Server (SBS)</span><span class="sxs-lookup"><span data-stu-id="c6034-163">2013 based Survivable Branch Appliance (SBA) or Survivable Branch Server (SBS)</span></span>
- <span data-ttu-id="c6034-164">Cloud-Connector-Edition (CCE)</span><span class="sxs-lookup"><span data-stu-id="c6034-164">Cloud Connector Edition (CCE)</span></span>
- <span data-ttu-id="c6034-165">Microsoft Skype for Business für Windows Phone</span><span class="sxs-lookup"><span data-stu-id="c6034-165">Skype for Business for Windows Phone</span></span>

### <a name="exceptions"></a><span data-ttu-id="c6034-166">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="c6034-166">Exceptions</span></span>

#### <a name="lync-server-2013"></a><span data-ttu-id="c6034-167">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6034-167">Lync Server 2013</span></span>

<span data-ttu-id="c6034-168">Lync Server 2013 übernimmt eine Abhängigkeit Windows Fabric Version 1.0.</span><span class="sxs-lookup"><span data-stu-id="c6034-168">Lync Server 2013 takes a dependency on Windows Fabric version 1.0.</span></span>  <span data-ttu-id="c6034-169">In der Phase Design für Lync Server 2013 wurde gewählt, Windows Fabric 1.0 für die überzeugender und neue verteilte Architektur Replikation, hohe Verfügbarkeit und Fehlertoleranz bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="c6034-169">In the design phase for Lync Server 2013, Windows Fabric 1.0 was chosen for its compelling and new distributed architecture to provide replication, high availability, and fault tolerance.</span></span>  <span data-ttu-id="c6034-170">Im Laufe der Zeit beide Skype für Business Server und Windows Fabric haben erheblich verbessert diese gemeinsame Architektur mit erhebliche überarbeiten in späteren Versionen.</span><span class="sxs-lookup"><span data-stu-id="c6034-170">Over time, both Skype for Business Server and Windows Fabric have greatly improved this joint architecture with significant re-design in subsequent versions.</span></span>  <span data-ttu-id="c6034-171">Aktuelle Skype für Business 2015 Server wird Windows Fabric 3.0, beispielsweise verwendet.</span><span class="sxs-lookup"><span data-stu-id="c6034-171">Current Skype for Business 2015 Server uses Windows Fabric 3.0, for example.</span></span>

<span data-ttu-id="c6034-172">Windows Fabric 1.0 **unterstützt TLS 1.2 leider nicht.  Jedoch empfohlen wird werden Aktualisieren von Lync Server 2013 TLS 1.2 entwickelt**.</span><span class="sxs-lookup"><span data-stu-id="c6034-172">Unfortunately, Windows Fabric 1.0 **does not support TLS 1.2.  However, we will be updating Lync Server 2013 to work with TLS 1.2**.</span></span> <span data-ttu-id="c6034-173">Dadurch wird das nächste kumulative Update für Lync Server 2013 stammen.</span><span class="sxs-lookup"><span data-stu-id="c6034-173">This will be coming in the next Cumulative Update for Lync Server 2013.</span></span>  <span data-ttu-id="c6034-174">Wir bieten immer noch die Unterstützung für TLS 1.2 Koexistenz, Migration, Verbund- und hybridkonfiguration Szenarien zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="c6034-174">We're providing TLS 1.2 support to enable co-existence, migration, federation, and hybrid scenarios.</span></span>

<span data-ttu-id="c6034-175">Wenn Ihre Organisation Deaktivieren von TLS 1.0 und 1.1 erforderlich ist und Sie zurzeit Lync Server 2013 verwenden, empfehlen wir Sie beim Planen beginnen, mit der Möglichkeit möglicherweise müssen Sie bei direkten Upgrades oder Side-by-Side migrieren (neuen Pools, Benutzer verschieben) zu Skype für Business Server 2015 oder höher.</span><span class="sxs-lookup"><span data-stu-id="c6034-175">If your organization is required to disable TLS 1.0 and 1.1, and you currently use Lync Server 2013, we recommend you begin your planning process, with the possibility you may have to In-place upgrade or Side-by-Side migrate (new pools, move users) to Skype for Business Server 2015 or higher.</span></span>  <span data-ttu-id="c6034-176">Oder Sie möchten die Beschleunigung der Migration auf Skype für Business Online.</span><span class="sxs-lookup"><span data-stu-id="c6034-176">Or you may want to accelerate migration to Skype for Business Online.</span></span>

#### <a name="call-quality-dashboard"></a><span data-ttu-id="c6034-177">Anrufqualitäts-Dashboard</span><span class="sxs-lookup"><span data-stu-id="c6034-177">Call Quality Dashboard</span></span>

<span data-ttu-id="c6034-178">Lokale aufrufen Qualitätsdashboard ist derzeit abhängig von TLS 1.0 während der Neuinstallation (erstmalig in Ihrer lokalen Umgebung installieren).</span><span class="sxs-lookup"><span data-stu-id="c6034-178">On-Premises Call Quality Dashboard currently has a dependency on TLS 1.0 during new install (first time installing into your On-Premises environments).</span></span>  <span data-ttu-id="c6034-179">Wir sind zurzeit untersucht dieses Problem und ein Update in naher Zukunft freigeben möchten.</span><span class="sxs-lookup"><span data-stu-id="c6034-179">We are currently investigating this issue and plan to release a fix in the near future.</span></span>  <span data-ttu-id="c6034-180">Wenn Sie beabsichtigen, installieren CQD und TLS 1.0 auch deaktivieren, wird empfohlen, dass Sie zuerst CQD-Installation abgeschlossen, und fahren mit TLS 1.0 zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="c6034-180">If you are planning to install CQD and also disable TLS 1.0, we recommend that you complete CQD installation first, and then proceed with TLS 1.0 disabling.</span></span>

#### <a name="third-party-devices"></a><span data-ttu-id="c6034-181">Drittanbieter-Geräte</span><span class="sxs-lookup"><span data-stu-id="c6034-181">Third-party devices</span></span>

<span data-ttu-id="c6034-182">Auf Geräten von Drittanbietern wie 3PIP Telefone unbedingt-Video-Konferenzen Reverseproxys und zum Lastenausgleich, TLS 1.2 Supportability überprüfen und sorgfältig getestet und Kontaktaufnahme mit dem Hersteller bei Bedarf.</span><span class="sxs-lookup"><span data-stu-id="c6034-182">On third-party devices such as 3PIP phones, Video conferencing, Reverse Proxies and Load Balancers, be sure to validate TLS 1.2 supportability, test carefully, and contact the vendor if needed.</span></span>

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a><span data-ttu-id="c6034-183">Verbund-Überlegungen beim Deaktivieren von TLS 1.0/1.1 auf Edge-Servern</span><span class="sxs-lookup"><span data-stu-id="c6034-183">Federation considerations when disabling TLS 1.0/1.1 on Edge servers</span></span>

<span data-ttu-id="c6034-184">Sie müssen sorgfältig planen und berücksichtigen die Auswirkungen der TLS 1.0/1.1 auf Edge-Servern deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="c6034-184">You must carefully plan for and consider the impact of disabling TLS 1.0/1.1 on your Edge servers.</span></span>  <span data-ttu-id="c6034-185">Sobald TLS 1.0 und 1.1 deaktiviert sind, können Sie feststellen, dass anderen Organisationen sind nicht mehr in der Lage, Verbund mit Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="c6034-185">Once TLS 1.0 and 1.1 are disabled, you may find that other organizations are no longer be able to federate with your organization.</span></span>

<span data-ttu-id="c6034-186">Sie können entscheiden, wenn Sie TLS 1.0/1.1 auf Edge-Servern zum Aufrechterhalten der Abwärtskompatibilität mit nicht gepatcht (SfB 2015, Lync 2013) aktiviert oder externen Systemen mit älteren (2010).</span><span class="sxs-lookup"><span data-stu-id="c6034-186">You may opt to keep TLS 1.0/1.1 enabled on your Edge servers to maintain backward compatibility with non-patched (SfB 2015, Lync 2013) or older (2010) external systems.</span></span>

<span data-ttu-id="c6034-187">Microsoft kann nicht Rat oder Recommendations angeben, auf unabhängig davon, ob Ihr Netzwerk Edge (oder jedes Netzwerk) unter PCI-Standards liegt. muss von der einzelnen Unternehmen bestimmt werden.</span><span class="sxs-lookup"><span data-stu-id="c6034-187">Microsoft cannot provide advice or recommendations on whether or not your Edge network (or any network) falls under PCI standard; that must be determined by the individual company.</span></span>

<span data-ttu-id="c6034-188">Skype für Business Online kann TLS 1.2 heute, sodass keine Auswirkung auf Hybrid/Verbund mit Online erwartet wird.</span><span class="sxs-lookup"><span data-stu-id="c6034-188">Skype for Business Online is capable of TLS 1.2 today, so no impact to Hybrid/Federation with Online is expected.</span></span>

<span data-ttu-id="c6034-189">PIC (Public IM Connectivity) mit Skype Consumer-Dienst: wir davon ausgehen, dass TLS 1.0/1.1 um [Skype-Konnektivität](../../deploy/deploy-skype-connectivity.md); beeinträchtigen deaktivieren Microsoft PIC-Gateways sind bereits TLS 1.2 werden können.</span><span class="sxs-lookup"><span data-stu-id="c6034-189">PIC (Public IM Connectivity) to Skype Consumer service: We do not expect disabling TLS 1.0/1.1 to impact [Skype Connectivity](../../deploy/deploy-skype-connectivity.md); Microsoft PIC Gateways are already TLS 1.2 capable.</span></span>

## <a name="prerequisites-and-process"></a><span data-ttu-id="c6034-190">Erforderliche Komponenten und verarbeiten</span><span class="sxs-lookup"><span data-stu-id="c6034-190">Prerequisites and process</span></span>

<span data-ttu-id="c6034-191">Außer oben nicht anders angegeben, einmal TLS 1.0 und 1.1 deaktivierte außerhalb des Bereichs Server sind, funktionieren Clients und Geräten ordnungsgemäß oder überhaupt mehr.</span><span class="sxs-lookup"><span data-stu-id="c6034-191">Except where noted above, once TLS 1.0 and 1.1 are disabled out-of-scope servers, clients and devices will longer function properly, or at all.</span></span> <span data-ttu-id="c6034-192">Dies kann bedeuten, dass müssen Sie unterbrechen, und warten Sie aktualisierter Leitfaden von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c6034-192">This may mean you need to pause and wait for updated guidance from Microsoft.</span></span> <span data-ttu-id="c6034-193">Nachdem Sie sind davon überzeugt, dass Anforderungen entsprechen und ein Plans zum Adresse Lücken haben, fahren Sie fort.</span><span class="sxs-lookup"><span data-stu-id="c6034-193">Once you are satisfied that you meet all requirements and have a plan to address gaps, proceed.</span></span>

<span data-ttu-id="c6034-194">Auf allgemeiner Ebene während Skype für Business Server 2019 für Verfahren bei der Installation bereit ist erforderlich Skype für Business Server 2015, dass Sie CU6 HF2, Anwenden von Updates für vorausgesetzte .NET und SQL, Bereitstellung von erforderlichen Registrierungsschlüssel und schließlich eine Separate installieren Roundrobin der OS-Konfiguration (d. h. deaktivieren TLS 1.0 und 1.1 über den Registrierungs-Dateiimport) aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="c6034-194">At a high level, while Skype for Business Server 2019 is ready for procedure at install, Skype for Business Server 2015 will require that you install CU6 HF2, applying pre-requisite updates to .NET and SQL, deploying prerequisite registry keys, and finally a separate round of OS configuration updates (i.e. disabling TLS 1.0 and 1.1 via registry file import).</span></span> <span data-ttu-id="c6034-195">Es ist von entscheidender Bedeutung, dass Sie alle erforderlichen Komponenten, einschließlich Skype für Business Server 2015 CU6 HF2 deaktivieren TLS 1.0 und 1.1 auf allen Servern in Ihrer Umgebung vor der Installation abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="c6034-195">It is critically important that you complete installation of all prerequisites, including Skype for Business Server 2015 CU6 HF2, prior to disabling TLS 1.0 and 1.1 on any server in your environment.</span></span> <span data-ttu-id="c6034-196">Jeder Skype für Business Server, einschließlich Edge-Rolle und SQL-Back-Ends, erfordert die Updates.</span><span class="sxs-lookup"><span data-stu-id="c6034-196">Every Skype for Business server, including Edge role and SQL Backends, requires the updates.</span></span> <span data-ttu-id="c6034-197">Außerdem sicherstellen Sie, dass alle unterstützten (im Gültigkeitsbereich)-Clients, die mindestens erforderlichen Versionen aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="c6034-197">Also ensure that all supported (in-scope) clients have been updated to the required minimum versions.</span></span> <span data-ttu-id="c6034-198">Vergessen Sie nicht, Verwaltungscomputer sowie zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="c6034-198">Don’t forget to update management workstations as well.</span></span>

<span data-ttu-id="c6034-199">Wir möchten die übliche Reihenfolge der Vorgänge von "innen nach außen" führen für das Upgrade von Skype für Unternehmensserver.</span><span class="sxs-lookup"><span data-stu-id="c6034-199">We want to follow the usual order of operations of "inside out" for upgrading Skype for Business servers.</span></span> <span data-ttu-id="c6034-200">Behandeln von Director-Pools, Persistent Chat und gepaart Pools in die gleiche Weise wie gewohnt verwenden.</span><span class="sxs-lookup"><span data-stu-id="c6034-200">Treat Director pools, Persistent chat, and Paired Pools in the same manner you normally would.</span></span> <span data-ttu-id="c6034-201">Reihenfolge und Methoden für das Upgrade fallen [hier](topology.md) und [hier](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span><span class="sxs-lookup"><span data-stu-id="c6034-201">Order and methods for upgrade are covered [here](topology.md) and [here](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span></span>

### <a name="high-level-process"></a><span data-ttu-id="c6034-202">Allgemeine Prozess</span><span class="sxs-lookup"><span data-stu-id="c6034-202">High-level process</span></span>

1. <span data-ttu-id="c6034-203">Testen Sie alle Schritte im Lab vor dem Konfigurieren von Produktionsservern.</span><span class="sxs-lookup"><span data-stu-id="c6034-203">Test all steps in your lab prior to configuring production servers.</span></span>
2. <span data-ttu-id="c6034-204">Sichern Sie und bewahren Sie eine Kopie der exportierten Registrierung auf jedem einzelnen Server aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="c6034-204">Back up and preserve a copy of exported registry on each and every individual server to be updated.</span></span> <span data-ttu-id="c6034-205">Registrierung zwischen Servern kann nicht freigegeben werden. Sie enthalten eindeutige computerbasierte Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="c6034-205">You cannot share registries between servers; they contain unique machine-based keys.</span></span>
3. <span data-ttu-id="c6034-206">Aktualisieren Sie alle Skype für 2015 Business Server, auf CU6 HF2 oder höher.</span><span class="sxs-lookup"><span data-stu-id="c6034-206">Upgrade all Skype for Business 2015 servers to CU6 HF2 or higher.</span></span> <span data-ttu-id="c6034-207">(Für Skype für Business Server 2019, ist keine CU erforderlich)</span><span class="sxs-lookup"><span data-stu-id="c6034-207">(For Skype for Business Server 2019, no CU is needed)</span></span>
4. <span data-ttu-id="c6034-208">Installieren Sie alle erforderlichen Komponenten auf allen Servern.</span><span class="sxs-lookup"><span data-stu-id="c6034-208">Install all prerequisites to all servers.</span></span>
5. <span data-ttu-id="c6034-209">Bereitstellen von erforderlichen Registrierungsschlüssel.</span><span class="sxs-lookup"><span data-stu-id="c6034-209">Deploy prerequisite registry keys.</span></span>
6. <span data-ttu-id="c6034-210">Stellen Sie sicher, dass alle im Gültigkeitsbereich Clients aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="c6034-210">Ensure that all in-scope clients are updated.</span></span>
7. <span data-ttu-id="c6034-211">Deaktivieren Sie TLS 1.0 und 1.1 über Registrierung importieren.</span><span class="sxs-lookup"><span data-stu-id="c6034-211">Disable TLS 1.0 and 1.1 via registry import.</span></span>
8. <span data-ttu-id="c6034-212">Überprüfen Sie, dass Arbeitslasten wie erwartet funktionieren.</span><span class="sxs-lookup"><span data-stu-id="c6034-212">Validate that workloads are functioning as expected.</span></span>
    - <span data-ttu-id="c6034-213">Wenn Probleme auftreten, zu beheben, oder</span><span class="sxs-lookup"><span data-stu-id="c6034-213">If problems are encountered, troubleshoot and resolve, or</span></span>
    - <span data-ttu-id="c6034-214">Wiederherstellen der Registrierung aus Schritt 2 zum erneuten Aktivieren von TLS 1.0 und 1.1</span><span class="sxs-lookup"><span data-stu-id="c6034-214">Restore registry from step 2 to re-enable TLS 1.0 and 1.1</span></span>
9. <span data-ttu-id="c6034-215">Überprüfen Sie, dass nur TLS 1.2 verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c6034-215">Validate that only TLS 1.2 is being used.</span></span>

### <a name="install-prerequisites-to-all-servers"></a><span data-ttu-id="c6034-216">Installieren der erforderlichen Komponenten auf allen Servern</span><span class="sxs-lookup"><span data-stu-id="c6034-216">Install prerequisites to all servers</span></span>

<span data-ttu-id="c6034-217">Umfassende Abhängigkeit aktualisieren ist erforderlich, bevor Sie beginnen, TLS 1.0 und 1.1 auf Betriebssystemebene in Ihrer Skype für Business Server 2015 Bereitstellungen zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="c6034-217">Extensive dependency updating is required before you begin to disable TLS 1.0 and 1.1 at the operating system level in your Skype for Business Server 2015 deployments.</span></span> <span data-ttu-id="c6034-218">Im folgenden werden die minimalen Versionen, die TLS 1.2 unterstützen können.</span><span class="sxs-lookup"><span data-stu-id="c6034-218">The following are the minimum versions that can support TLS 1.2.</span></span> <span data-ttu-id="c6034-219">Stellen Sie alle erforderlichen Updates über jede Skype für Business Server in Ihrer Umgebung bereit, bevor Sie beginnen, deaktivieren TLS 1.0 und 1.1.</span><span class="sxs-lookup"><span data-stu-id="c6034-219">Deploy all prerequisite updates across every Skype for Business server in your environment before you begin disabling TLS 1.0 and 1.1.</span></span>

- <span data-ttu-id="c6034-220">Skype für Business Server 2015 CU6 HF2 6.0.9319.516 ([update März 2018](https://support.microsoft.com/en-us/help/4086059/march-2018-cumulative-update-6-0-9319-516-for-skype-for-business)) oder höher</span><span class="sxs-lookup"><span data-stu-id="c6034-220">Skype for Business Server 2015 CU6 HF2 6.0.9319.516 ([March 2018 update](https://support.microsoft.com/en-us/help/4086059/march-2018-cumulative-update-6-0-9319-516-for-skype-for-business)) or higher</span></span>
- <span data-ttu-id="c6034-221">[.NET Framework 4.7](https://www.microsoft.com/en-us/download/details.aspx?id=55167) oder höher mit SchUseStrongCrypto aktiviert in der Registrierung (siehe unten)</span><span class="sxs-lookup"><span data-stu-id="c6034-221">[.NET Framework 4.7](https://www.microsoft.com/en-us/download/details.aspx?id=55167) or higher with SchUseStrongCrypto enabled in the registry (provided below)</span></span>
- <span data-ttu-id="c6034-222">SQL muss auf allen Skype für Business 2015-Server und -Back-Ends aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="c6034-222">SQL must be updated on all Skype for Business 2015 servers and backends.</span></span> <span data-ttu-id="c6034-223">Aktualisieren Sie Enterprise Edition-Pool SQL-Back-Ends zuerst, klicken Sie dann ihre jeweiligen FEs.</span><span class="sxs-lookup"><span data-stu-id="c6034-223">Update Enterprise Edition Pool SQL Backends first, then their respective FEs.</span></span> 
    - <span data-ttu-id="c6034-224">SQL Server 2014 SP1 + CU5 ([Link](https://support.microsoft.com/help/3130926)) oder höher / SQL Server 2012 SP2 + CU16 oder höher / RTM-Version von SQL Server 2014 + CU12 ([Link](https://support.microsoft.com/en-us/help/3130923/cumulative-update-12-for-sql-server-2014)) oder höher / SQL Server 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="c6034-224">SQL Server 2014 SP1 + CU5 ([link](https://support.microsoft.com/help/3130926)), or higher / SQL Server 2012 SP2 + CU16 or higher/ SQL Server 2014 RTM + CU12 ([link](https://support.microsoft.com/en-us/help/3130923/cumulative-update-12-for-sql-server-2014)) or higher / SQL Server 2014 SP2</span></span>
    - <span data-ttu-id="c6034-225">SQL Server Native Client für SQL Server 2012 ([Link](https://www.microsoft.com/en-us/download/details.aspx?id=50402))</span><span class="sxs-lookup"><span data-stu-id="c6034-225">SQL Server Native Client for SQL Server 2012 ([link](https://www.microsoft.com/en-us/download/details.aspx?id=50402))</span></span>
    - <span data-ttu-id="c6034-226">Microsoft ODBC-Treiber 11 für SQL Server ([Link](https://www.microsoft.com/en-us/download/details.aspx?id=36434)) oder höher</span><span class="sxs-lookup"><span data-stu-id="c6034-226">Microsoft ODBC Driver 11 for SQL Server ([link](https://www.microsoft.com/en-us/download/details.aspx?id=36434)), or higher</span></span>
    - <span data-ttu-id="c6034-227">Gemeinsame Management Objects für SQL Server 2014 SP2 ([Link](https://www.microsoft.com/en-in/download/details.aspx?id=42295))</span><span class="sxs-lookup"><span data-stu-id="c6034-227">Shared Management Objects for SQL Server 2014 SP2 ([link](https://www.microsoft.com/en-in/download/details.aspx?id=42295))</span></span>
    - <span data-ttu-id="c6034-228">SQLSysClrTypes für SQLServer 2014 SP2 ([Link](https://www.microsoft.com/en-in/download/details.aspx?id=42295))</span><span class="sxs-lookup"><span data-stu-id="c6034-228">SQLSysClrTypes for SQL server 2014 SP2 ([link](https://www.microsoft.com/en-in/download/details.aspx?id=42295))</span></span>

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a><span data-ttu-id="c6034-229">Grundlegende Schritte zum Installieren der erforderlichen Komponenten in empfohlene Reihenfolge der Vorgänge</span><span class="sxs-lookup"><span data-stu-id="c6034-229">Basic steps to install pre-requisites, in recommended order of operations</span></span>

1. <span data-ttu-id="c6034-230">Installieren Sie die Skype für Business Server CU6HF2 (6.0.9319.516) auf allen Servern zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="c6034-230">Install the Skype for Business Server CU6HF2 (6.0.9319.516) update to all servers.</span></span> 
    1. <span data-ttu-id="c6034-231">Installieren des Updates und den Updater-Komponenten.</span><span class="sxs-lookup"><span data-stu-id="c6034-231">Install the update to components using the updater.</span></span>
    2. <span data-ttu-id="c6034-232">Aktualisieren von Datenbanken entsprechend dokumentierte Verfahren.</span><span class="sxs-lookup"><span data-stu-id="c6034-232">Update databases according to documented procedures.</span></span> <span data-ttu-id="c6034-233">Anweisungen sind unter dokumentiert [https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span><span class="sxs-lookup"><span data-stu-id="c6034-233">Instructions are documented at [https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span></span>
    3. <span data-ttu-id="c6034-234">Produktfunktionen in der Bereitstellung, bevor Sie mit anderen Änderungen zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="c6034-234">Validate product functionality in the deployment prior to moving forward with any other changes.</span></span>
2. <span data-ttu-id="c6034-235">Laden Sie .NET 4.7 Offline Installer.</span><span class="sxs-lookup"><span data-stu-id="c6034-235">Download .NET 4.7 Offline Installer.</span></span> 
    1. <span data-ttu-id="c6034-236">Referenz:[https://www.microsoft.com/en-us/download/details.aspx?id=55167](https://www.microsoft.com/en-us/download/details.aspx?id=55167)</span><span class="sxs-lookup"><span data-stu-id="c6034-236">Reference: [https://www.microsoft.com/en-us/download/details.aspx?id=55167](https://www.microsoft.com/en-us/download/details.aspx?id=55167)</span></span>
    2. <span data-ttu-id="c6034-237">Stellen Sie sicher, dass Skype für Business Server 2015 Dienste auf dem Front-End-Server beendet werden.</span><span class="sxs-lookup"><span data-stu-id="c6034-237">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
    3. <span data-ttu-id="c6034-238">Referenz:[https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="c6034-238">Reference: [https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)</span></span>
    4. <span data-ttu-id="c6034-239">Ex (Standard Edition): Stop – CsWindowsServices</span><span class="sxs-lookup"><span data-stu-id="c6034-239">Ex (Standard Edition): Stop-CsWindowsServices</span></span>
    5. <span data-ttu-id="c6034-240">Ex (Enterprise Edition): Aufruf-CsComputerFailover</span><span class="sxs-lookup"><span data-stu-id="c6034-240">Ex (Enterprise Edition): Invoke-CsComputerFailover</span></span>
    6. <span data-ttu-id="c6034-241">Führen Sie das Installer-Paket.</span><span class="sxs-lookup"><span data-stu-id="c6034-241">Run the installer package.</span></span>
    7. <span data-ttu-id="c6034-242">Starten Sie den Server neu.</span><span class="sxs-lookup"><span data-stu-id="c6034-242">Reboot the server.</span></span>
3. <span data-ttu-id="c6034-243">Aktualisieren Sie SQL Express 2014 auf allen Servern.</span><span class="sxs-lookup"><span data-stu-id="c6034-243">Update SQL Express 2014 on all servers.</span></span> 
    1. <span data-ttu-id="c6034-244">Referenz:[https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span><span class="sxs-lookup"><span data-stu-id="c6034-244">Reference: [https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span></span>
    2. <span data-ttu-id="c6034-245">SQL 2014 SP2 herunterladen</span><span class="sxs-lookup"><span data-stu-id="c6034-245">Download SQL 2014 SP2</span></span> 
        - <span data-ttu-id="c6034-246">Referenz:[https://www.microsoft.com/en-us/download/details.aspx?id=53168](https://www.microsoft.com/en-us/download/details.aspx?id=53168)</span><span class="sxs-lookup"><span data-stu-id="c6034-246">Reference: [https://www.microsoft.com/en-us/download/details.aspx?id=53168](https://www.microsoft.com/en-us/download/details.aspx?id=53168)</span></span>
    3. <span data-ttu-id="c6034-247">Kopieren Sie die Installationsmedien in einen Ordner auf dem Server (Ex: C:\01_2014SqlSp2)</span><span class="sxs-lookup"><span data-stu-id="c6034-247">Copy the installation media to a folder on the server (Ex: C:\01_2014SqlSp2)</span></span>
    4. <span data-ttu-id="c6034-248">Sicherstellen von Skype für Business Server 2015 Dienste auf dem Front-End-Server beendet werden</span><span class="sxs-lookup"><span data-stu-id="c6034-248">Ensure Skype for Business Server 2015 services are stopped on the Front End server</span></span> 
        - <span data-ttu-id="c6034-249">Ex (Standard Edition): Stop-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="c6034-249">Ex (Standard Edition): Stop-CsWindowsService</span></span>
        - <span data-ttu-id="c6034-250">Ex (Enterprise Edition): Aufruf-CsComputerFailove</span><span class="sxs-lookup"><span data-stu-id="c6034-250">Ex (Enterprise Edition): Invoke-CsComputerFailove</span></span>
    5. <span data-ttu-id="c6034-251">Öffnen Sie ein Eingabeaufforderungsfenster Admin, und aktualisieren Sie alle installierten Komponenten und Instanzen</span><span class="sxs-lookup"><span data-stu-id="c6034-251">Open an Admin Command Prompt, and upgrade all installed components and instances</span></span> 
        - <span data-ttu-id="c6034-252">Beispiel: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action = Patch allinstances</span><span class="sxs-lookup"><span data-stu-id="c6034-252">Example: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances</span></span>
4. <span data-ttu-id="c6034-253">Aktualisieren Sie SQL Native Client.</span><span class="sxs-lookup"><span data-stu-id="c6034-253">Update SQL Native Client.</span></span> 
    1. <span data-ttu-id="c6034-254">Referenz: [https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span><span class="sxs-lookup"><span data-stu-id="c6034-254">Reference: [https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span></span>
    2. <span data-ttu-id="c6034-255">Laden Sie aus[https://www.microsoft.com/en-us/download/details.aspx?id=50402](https://www.microsoft.com/en-us/download/details.aspx?id=50402)</span><span class="sxs-lookup"><span data-stu-id="c6034-255">Download from [https://www.microsoft.com/en-us/download/details.aspx?id=50402](https://www.microsoft.com/en-us/download/details.aspx?id=50402)</span></span>
    3. <span data-ttu-id="c6034-256">Stellen Sie sicher Skype für Business Server 2015 Dienste auf dem Front-End-Server beendet werden.</span><span class="sxs-lookup"><span data-stu-id="c6034-256">Ensure Skype for Business Server 2015 services are stopped on the Front End server.</span></span> 
        - <span data-ttu-id="c6034-257">Ex (Standard Edition): Stop – CsWindowsServices</span><span class="sxs-lookup"><span data-stu-id="c6034-257">Ex (Standard Edition): Stop-CsWindowsServices</span></span>
        - <span data-ttu-id="c6034-258">Ex (Enterprise Edition): Aufruf-CsComputerFailove</span><span class="sxs-lookup"><span data-stu-id="c6034-258">Ex (Enterprise Edition): Invoke-CsComputerFailove</span></span>
    4. <span data-ttu-id="c6034-259">Beenden Sie die Ausführung von installierten SQL-Instanzen</span><span class="sxs-lookup"><span data-stu-id="c6034-259">Stop the SQL instances installed from running</span></span> 
        - <span data-ttu-id="c6034-260">Beispiel: Get-Service "MSSQL$ RTCLOCAL" | STOP-Dienst</span><span class="sxs-lookup"><span data-stu-id="c6034-260">Ex: Get-Service 'MSSQL$RTCLOCAL' | Stop-Servic</span></span>
        - <span data-ttu-id="c6034-261">Beispiel: Get-Service 'MSSQL$ LYNCLOCAL' | STOP-Dienst</span><span class="sxs-lookup"><span data-stu-id="c6034-261">Ex: Get-Service 'MSSQL$LYNCLOCAL' | Stop-Servic</span></span>
        - <span data-ttu-id="c6034-262">Ex (nur Standard Edition): Get-Service "MSSQL$ RTC" | STOP-Dienst</span><span class="sxs-lookup"><span data-stu-id="c6034-262">Ex (Standard Edition Only): Get-Service 'MSSQL$RTC' | Stop-Servic</span></span>
    5. <span data-ttu-id="c6034-263">Installieren Sie das Update.</span><span class="sxs-lookup"><span data-stu-id="c6034-263">Install the update.</span></span>
5. <span data-ttu-id="c6034-264">ODBC-Treiber 11 für SQLServer zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="c6034-264">Update ODBC Driver 11 for SQL Server.</span></span> 
    1. <span data-ttu-id="c6034-265">Referenz: [https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span><span class="sxs-lookup"><span data-stu-id="c6034-265">Reference: [https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span></span>
    2. <span data-ttu-id="c6034-266">Laden Sie aus[https://www.microsoft.com/en-us/download/confirmation.aspx?id=36434](https://www.microsoft.com/en-us/download/confirmation.aspx?id=36434)</span><span class="sxs-lookup"><span data-stu-id="c6034-266">Download from [https://www.microsoft.com/en-us/download/confirmation.aspx?id=36434](https://www.microsoft.com/en-us/download/confirmation.aspx?id=36434)</span></span>
    3. <span data-ttu-id="c6034-267">Stellen Sie sicher, dass Skype für Business Server 2015 Dienste auf dem Front-End-Server beendet werden</span><span class="sxs-lookup"><span data-stu-id="c6034-267">Ensure that Skype for Business Server 2015 services are stopped on the Front End server</span></span> 
        - <span data-ttu-id="c6034-268">Ex (Standard Edition): Stop-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="c6034-268">Ex (Standard Edition): Stop-CsWindowsService</span></span>
        - <span data-ttu-id="c6034-269">Ex (Enterprise Edition): Aufruf-CsComputerFailove</span><span class="sxs-lookup"><span data-stu-id="c6034-269">Ex (Enterprise Edition): Invoke-CsComputerFailove</span></span>
    4. <span data-ttu-id="c6034-270">Installieren Sie das Update.</span><span class="sxs-lookup"><span data-stu-id="c6034-270">Install the update.</span></span>
6. <span data-ttu-id="c6034-271">Bereitstellen von erforderlichen Registrierungsschlüssel.</span><span class="sxs-lookup"><span data-stu-id="c6034-271">Deploy prerequisite registry keys.</span></span>

### <a name="pre-requisite-registry-keys"></a><span data-ttu-id="c6034-272">Vorausgesetzte Registrierungsschlüssel</span><span class="sxs-lookup"><span data-stu-id="c6034-272">Pre-requisite registry keys</span></span>

<span data-ttu-id="c6034-273">Kopieren und Einfügen den folgenden Test in Notepad ein umbenennen Sie TLSPreReq.reg oder einen Namen Ihrer Wahl, und importieren:</span><span class="sxs-lookup"><span data-stu-id="c6034-273">Copy/paste the following test into Notepad and rename TLSPreReq.reg or a name of your choice, then import:</span></span>

```
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v2.0.50727]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v4.0.30319]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v2.0.50727]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v4.0.30319]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp]

"DefaultSecureProtocols"=dword:00000AA0

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp]

"DefaultSecureProtocols"=dword:00000AA0

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2\Client]

"DisabledByDefault"=dword:00000000

"Enabled"=dword:00000001

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2\Server]

"DisabledByDefault"=dword:00000000

"Enabled"=dword:00000001
```

<span data-ttu-id="c6034-274">Für SQL sollten Back zu deaktivierende enden für Enterprise Edition-Pools, erforderliche Komponenten und TLS wie SQL oder OS Updates behandelt werden. finden Sie unter:[https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span><span class="sxs-lookup"><span data-stu-id="c6034-274">For SQL back ends for Enterprise Edition Pools, prerequisites and TLS disable should be treated as any SQL or OS updates would; refer to: [https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span></span>

<span data-ttu-id="c6034-275">Während der erforderlichen Anwendung und die Schritte deaktivieren TLS kombiniert werden können, empfehlen wir dringend, alle erforderlichen Komponenten vor dem Fortfahren mit der Deaktivierung von TLS 1.0 und 1.1 auf Betriebssystemebene angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="c6034-275">While both the prerequisite application and TLS disabling steps can be combined, we strongly recommend all prerequisites be applied before proceeding with disabling of TLS 1.0 and 1.1 at the operating system level.</span></span> <span data-ttu-id="c6034-276">Der beste Practice Ansatz wäre die Umgebung vorbereiten, indem Sie alle erforderlichen Komponenten, überprüfen, dass alle Arbeitslasten ordnungsgemäß und wie erwartet funktionieren und Fortfahren mit TLS 1.0/1.1 deaktivieren Sie dann zu einem späteren Zeitpunkt bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="c6034-276">The best practice approach would be to prepare the environment by deploying all prerequisites, validating that workloads all function correctly and as expected, and then proceeding with TLS 1.0/1.1 disable at a later time.</span></span>

### <a name="disable-tls-10-and-11-via-registry-import"></a><span data-ttu-id="c6034-277">Deaktivieren von TLS 1.0 und 1.1 über Registrierung importieren</span><span class="sxs-lookup"><span data-stu-id="c6034-277">Disable TLS 1.0 and 1.1 via registry import</span></span>

<span data-ttu-id="c6034-278">Vor dem Fortfahren Sie mit den nächsten Schritten, *Stellen Sie sicher, dass Sie alle erforderlichen Komponenten abgeschlossen und Skype für Unternehmensserver aktualisiert haben*.</span><span class="sxs-lookup"><span data-stu-id="c6034-278">Before you proceed with the next steps, *make sure you have completed all prerequisites and updated Skype for Business Servers*.</span></span>

<span data-ttu-id="c6034-279">Kopieren Sie den folgenden Text in eine Editor-Datei, und benennen Sie sie **TLSDisable.reg**:</span><span class="sxs-lookup"><span data-stu-id="c6034-279">Copy the following text into a Notepad file and rename it **TLSDisable.reg**:</span></span>

```
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Cryptography\Configuration\SSL\00010002]

"Functions"="TLS_ECDHE_ECDSA_WITH_AES_256_GCM_SHA384_P384,TLS_ECDHE_ECDSA_WITH_AES_128_GCM_SHA256_P256,TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384_P384,TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256_P256,TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA384_P384,TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA256_P256,TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384_P384,TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256_P256,TLS_RSA_WITH_AES_256_GCM_SHA384,TLS_RSA_WITH_AES_128_GCM_SHA256,TLS_RSA_WITH_AES_256_CBC_SHA256,TLS_RSA_WITH_AES_128_CBC_SHA256"

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL]

"AllowInsecureRenegoClients"=dword:00000000

"AllowInsecureRenegoServers"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\AES 128/128]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\AES 256/256]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\DES 56/56]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\NULL]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 128/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 40/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 56/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 56/56]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 128/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 40/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 56/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 64/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\Triple DES 168]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\MD5]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA256]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA384]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA512]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms\Diffie-Hellman]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms\ECDH]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms\PKCS]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\Multi-Protocol Unified Hello]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\Multi-Protocol Unified Hello\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\Multi-Protocol Unified Hello\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\PCT 1.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\PCT 1.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\PCT 1.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 3.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 3.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 3.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000
```

<span data-ttu-id="c6034-280">Importieren Sie die REG-Datei auf jedem Server, die Sie TLS 1.0 deaktivieren möchten und 1.1.</span><span class="sxs-lookup"><span data-stu-id="c6034-280">Import the .reg file on each server you wish to disable TLS 1.0 and 1.1.</span></span> <span data-ttu-id="c6034-281">Starten Sie den Server neu.</span><span class="sxs-lookup"><span data-stu-id="c6034-281">Reboot the server.</span></span> <span data-ttu-id="c6034-282">Sobald die Dienste wieder online geschaltet haben, fahren Sie mit den nächsten Server.</span><span class="sxs-lookup"><span data-stu-id="c6034-282">Once the services have come back online, move to the next server.</span></span> <span data-ttu-id="c6034-283">Die Vorgehensweise für Enterprise Edition-Pools ist identisch, die Sie für jedes Update OS ausführen würden.</span><span class="sxs-lookup"><span data-stu-id="c6034-283">The approach for Enterprise Edition Pools is the same you would take for any OS update.</span></span>

<span data-ttu-id="c6034-284">Sie haben möglicherweise bemerkt, dass wir mehr als einfach zu deaktivieren, TLS 1.0 und 1.1 hier machen.</span><span class="sxs-lookup"><span data-stu-id="c6034-284">You may have noticed we are doing more than just disabling TLS 1.0 and 1.1 here.</span></span> <span data-ttu-id="c6034-285">Wir sind Chiffre-Suite neu anordnen (siehe oben) und das Deaktivieren der einige ältere schwache Chiffre unterstützen.</span><span class="sxs-lookup"><span data-stu-id="c6034-285">We are supporting Cipher Suite re-order (as shown above) and the disabling of some older weak ciphers.</span></span> <span data-ttu-id="c6034-286">Hierbei handelt es sich beim ersten wir diese Änderungen SCHANNEL und Kryptografie-API auf Skype offiziell für Business Server unterstützt haben, und es ist wichtig, beachten Sie, dass diese Änderungen nur sind, die wir unterstützen und zu diesem Zeitpunkt getestet.</span><span class="sxs-lookup"><span data-stu-id="c6034-286">This is the first time we have officially supported these changes to SCHANNEL and Crypto API on Skype for Business Server, and it is important to note that these changes are the only ones we support and have tested at this time.</span></span> <span data-ttu-id="c6034-287">Wir sollten weitere Konfigurationen in der Zukunft, aber jetzt darf nicht geändert werden in der Implementierung die Registrierung-Importdatei.</span><span class="sxs-lookup"><span data-stu-id="c6034-287">We may consider additional configurations in the future, but for now, please do not modify the registry import file in your implementation.</span></span>

### <a name="validate-that-workloads-are-functioning-as-expected"></a><span data-ttu-id="c6034-288">Überprüfen Sie, dass Arbeitslasten wie erwartet funktionieren</span><span class="sxs-lookup"><span data-stu-id="c6034-288">Validate that workloads are functioning as expected</span></span>

<span data-ttu-id="c6034-289">Nachdem TLS 1.0 und 1.1 in Ihrer Umgebung deaktiviert haben, stellen Sie sicher, dass alle Ihre wichtigsten Arbeitslasten wie erwartet funktionieren, beispielsweise Sofortnachrichten & Anwesenheit, P2P-Aufrufe, Enterprise-VoIP, usw..</span><span class="sxs-lookup"><span data-stu-id="c6034-289">Once TLS 1.0 and 1.1 have been disabled in your environment, ensure that all your main workloads are functioning as expected, such as IM & Presence, P2P calls, Enterprise Voice, etc.</span></span>

<span data-ttu-id="c6034-290">**Überprüfen Sie nur TLS 1.2 verwendet wird**</span><span class="sxs-lookup"><span data-stu-id="c6034-290">**Validate only TLS 1.2 is being used**</span></span>

<span data-ttu-id="c6034-291">Haben Sie Ihre Security Team führen Sie eine neue Überwachung Skype für Business-Datenverkehr, um sicherzustellen, dass das ältere TLS 1.0 Protokolle und 1.1 nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c6034-291">Have your Security Team perform a new audit of Skype for Business traffic to ensure that the older protocols TLS 1.0 and 1.1 are no longer in use.</span></span>

<span data-ttu-id="c6034-292">Alternativ können Sie Internet Explorer verwenden, TLS-Verbindungen an Webdienste von Skype für Business Server 2015 nach getestet TLS 1.0 und TLS 1.1 deaktiviert wurden.</span><span class="sxs-lookup"><span data-stu-id="c6034-292">Alternatively, you can use Internet Explorer to test TLS connections to web services from Skype for Business Server 2015 after TLS 1.0 and TLS 1.1 have been disabled.</span></span>

1. <span data-ttu-id="c6034-293">Starten Sie Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="c6034-293">Launch Internet Explorer.</span></span>
2. <span data-ttu-id="c6034-294">Wählen Sie **Extras** > **Internetoptionen**.</span><span class="sxs-lookup"><span data-stu-id="c6034-294">Select **Tools** > **Internet Options**.</span></span>
3. <span data-ttu-id="c6034-295">Wählen Sie die Registerkarte **Erweitert** .</span><span class="sxs-lookup"><span data-stu-id="c6034-295">Select the **Advanced** tab.</span></span>
4. <span data-ttu-id="c6034-296">Klicken Sie unter **Einstellungen**führen Sie einen Bildlauf nach unten.</span><span class="sxs-lookup"><span data-stu-id="c6034-296">Under **Settings**, scroll to the bottom.</span></span>
5. <span data-ttu-id="c6034-297">Stellen Sie sicher, dass TLS 1.0, TLS 1.1 und TLS 1.2 aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="c6034-297">Verify that TLS 1.0, TLS 1.1, and TLS 1.2 are enabled.</span></span>
6. <span data-ttu-id="c6034-298">Durchsuchen Sie den internen Webdienst-URL des Pools SfB 2015 (sollte erfolgreich eine Verbindung herstellen).</span><span class="sxs-lookup"><span data-stu-id="c6034-298">Browse the Internal Web Service URL of your SfB 2015 pool (should connect successfully).</span></span>
7. <span data-ttu-id="c6034-299">Wechseln Sie wieder in den Internet Explorer, und deaktivieren Sie nur die Option zur **Verwendung von TLS 1.2** .</span><span class="sxs-lookup"><span data-stu-id="c6034-299">Go back into Internet Explorer and disable the option to **Use TLS 1.2** only.</span></span>
8. <span data-ttu-id="c6034-300">Durchsuchen Sie den internen Webdienst-URL des SfB 2015 Pools erneut (sollte fehlschlagen Verbindung).</span><span class="sxs-lookup"><span data-stu-id="c6034-300">Browse the Internal Web Service URL of your SfB 2015 pool again (should fail to connect).</span></span>

![Internetoptionen](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a><span data-ttu-id="c6034-302">Erweiterte Bereitstellungsszenarien</span><span class="sxs-lookup"><span data-stu-id="c6034-302">Advanced deployment scenarios</span></span>

<span data-ttu-id="c6034-303">Da einige Abhängigkeit erforderliche Komponenten zur Unterstützung von TLS 1.2 in Skype für Business Server 2015 erforderlich sind, fehl aus der RTM-Medien installieren auf einem beliebigen System, auf dem TLS 1.0 und 1.1 deaktiviert wurden.</span><span class="sxs-lookup"><span data-stu-id="c6034-303">Because some dependency prerequisites are required to support TLS 1.2 in Skype for Business Ser 2015, installing from RTM media will fail on any system where TLS 1.0 and 1.1 have been disabled.</span></span>

<span data-ttu-id="c6034-304">**Bereitstellen von neuen Standard Edition-Server oder Enterprise Edition-Pools, sobald TLS 1.0 und 1.1 in Ihrer Umgebung deaktiviert sind.**</span><span class="sxs-lookup"><span data-stu-id="c6034-304">**Deploying New Standard Edition Servers or Enterprise Edition Pools once TLS 1.0 and 1.1 have been disabled in your environment.**</span></span>

<span data-ttu-id="c6034-305">**Option 1:** Verwenden Sie [SmartSetup](../../deploy/install/install-skype-for-business-server.md).</span><span class="sxs-lookup"><span data-stu-id="c6034-305">**Option 1:** Use [SmartSetup](../../deploy/install/install-skype-for-business-server.md).</span></span> <span data-ttu-id="c6034-306">Beachten Sie, dass wir die aktualisierten SQL-Binärdateien in einer zukünftigen CU zur Erfüllung SmartSetup aktualisieren, und in diesem Artikel werden in der Zukunft aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="c6034-306">Note that we are updating SmartSetup to accommodate the updated SQL binaries in a future CU, and will update this article in the future.</span></span>

<span data-ttu-id="c6034-307">**Option 2:** Vor der Installation lokalen SQL Server-Instanzen (RTCLOCAL und LYNCLOCAL)</span><span class="sxs-lookup"><span data-stu-id="c6034-307">**Option 2:** Pre-install local SQL instances (RTCLOCAL and LYNCLOCAL)</span></span>

1. <span data-ttu-id="c6034-308">Laden und SQL Express 2014 SP2 (SQLEXPR_x64.exe) in lokalen Ordner auf FE kopieren.</span><span class="sxs-lookup"><span data-stu-id="c6034-308">Download and copy SQL Express 2014 SP2 (SQLEXPR_x64.exe) to local folder on FE.</span></span> <span data-ttu-id="c6034-309">Nehmen wir an Ordner Pfad <SQL_FOLDER_PATH>.</span><span class="sxs-lookup"><span data-stu-id="c6034-309">Let’s say folder path <SQL_FOLDER_PATH>.</span></span>
2. <span data-ttu-id="c6034-310">Starten Sie PowerShell oder im Eingabeaufforderungsfenster, und navigieren Sie zu <SQL_FOLDER_PATH>.</span><span class="sxs-lookup"><span data-stu-id="c6034-310">Launch PowerShell or Command Prompt and navigate to <SQL_FOLDER_PATH>.</span></span>
3. <span data-ttu-id="c6034-311">Erstellen Sie durch Ausführen des folgenden Befehls die RTCLOCAL-SQL-Instanz.</span><span class="sxs-lookup"><span data-stu-id="c6034-311">Create the RTCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="c6034-312">Warten, bis SQLEXPR_x64.exe beendet, bevor Sie fortfahren ist:</span><span class="sxs-lookup"><span data-stu-id="c6034-312">Wait until SQLEXPR_x64.exe finishes before proceeding:</span></span>

    <span data-ttu-id="c6034-313">SQLEXPR_x64.exe/q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED = 0 /HIDECONSOLE /ACTION = Installation/Funktionen = SQLEngine, Tools/InstanceName = RTCLOCAL /TCPENABLED = 1 /SQLSVCACCOUNT = "NT-Autorität\Netzwerkdienst" /SQLSYSADMINACCOUNTS = "Builtin\ Administrators"/BROWSERSVCSTARTUPTYPE ="Automatisch"/AGTSVCACCOUNT ="NT-AUTORITÄT\NetworkService"/SQLSVCSTARTUPTYPE = Automatis</span><span class="sxs-lookup"><span data-stu-id="c6034-313">SQLEXPR_x64.exe  /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=RTCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automati</span></span>
1. <span data-ttu-id="c6034-314">Erstellen Sie durch Ausführen des folgenden Befehls die LYNCLOCAL SQL-Instanz.</span><span class="sxs-lookup"><span data-stu-id="c6034-314">Create the LYNCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="c6034-315">Warten, bis SQLEXPR_x64.exe beendet, bevor Sie mit dem nächsten Schritt fortfahren ist:</span><span class="sxs-lookup"><span data-stu-id="c6034-315">Wait until SQLEXPR_x64.exe finishes before proceeding to the next step:</span></span>

    <span data-ttu-id="c6034-316">SQLEXPR_x64.exe/q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED = 0 /HIDECONSOLE /ACTION = Installation/Funktionen = SQLEngine, Tools/InstanceName = LYNCLOCAL /TCPENABLED = 1 /SQLSVCACCOUNT = "NT-Autorität\Netzwerkdienst" /SQLSYSADMINACCOUNTS = "Builtin\ Administrators"/BROWSERSVCSTARTUPTYPE ="Automatisch"/AGTSVCACCOUNT ="NT-AUTORITÄT\NetworkService"/SQLSVCSTARTUPTYPE = automatische</span><span class="sxs-lookup"><span data-stu-id="c6034-316">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=LYNCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automatic</span></span>
1. <span data-ttu-id="c6034-317">Skype für Business Server 2015 RTM Setup ausführen.</span><span class="sxs-lookup"><span data-stu-id="c6034-317">Run Skype for Business Server 2015 RTM setup.</span></span>
2. <span data-ttu-id="c6034-318">Führen Sie die restlichen Schritte vom Abschnitt erforderlichen Komponenten.</span><span class="sxs-lookup"><span data-stu-id="c6034-318">Follow the remaining steps from the prerequisites section above.</span></span>

<span data-ttu-id="c6034-319">**Option 3:** Sie können auch manuell Binärdateien in einer lokalen Installationsverzeichnis Medien wie folgt ersetzen:</span><span class="sxs-lookup"><span data-stu-id="c6034-319">**Option 3:** You may also manually replace binaries in a local installation media directory as follows:</span></span>

1. [<span data-ttu-id="c6034-320">Installieren der erforderlichen Komponenten für Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="c6034-320">Install prerequisites for Skype for Business Server</span></span>](../../deploy/install/install-prerequisites.md)  
2. 2. <span data-ttu-id="c6034-321">Installieren von .NET 4.7:</span><span class="sxs-lookup"><span data-stu-id="c6034-321">Install .NET 4.7:</span></span> 
      - <span data-ttu-id="c6034-322">**Hinweis:** Wir zunächst wird die Unterstützung für .NET 4.7 in Skype für Business Server 2015 CU5 oder höher (6.0.9319.281) eingeführt.</span><span class="sxs-lookup"><span data-stu-id="c6034-322">**Note:** We first introduced support for .NET 4.7 in Skype for Business Server 2015 CU5+ (6.0.9319.281).</span></span> <span data-ttu-id="c6034-323">Aus diesem Grund wird in den späteren Schritten unten wir Hauptkomponenten vor der Installation Hauptfenster aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="c6034-323">Therefore, in later steps below we will be updating Core Components prior to the main install.</span></span>
      - <span data-ttu-id="c6034-324">Download: https://www.microsoft.com/en-us/download/details.aspx?id=55167.</span><span class="sxs-lookup"><span data-stu-id="c6034-324">Download: https://www.microsoft.com/en-us/download/details.aspx?id=55167.</span></span>
      - <span data-ttu-id="c6034-325">Referenz: [Software, die vor einem Skype für Business Server 2015 Bereitstellung installiert werden muss](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span><span class="sxs-lookup"><span data-stu-id="c6034-325">Reference: [Software that should be installed before a Skype for Business Server 2015 deployment](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span></span>
3. <span data-ttu-id="c6034-326">Kopieren Sie die ISO-Dateien/Ordner:</span><span class="sxs-lookup"><span data-stu-id="c6034-326">Copy ISO Files/Folders:</span></span> 
    - <span data-ttu-id="c6034-327">Mit der Skype für Business Server 2015 ISO zugeordnet ist, öffnen Sie das Stammverzeichnis des Laufwerks, wird es als angefügt (Ex: D:\) im Datei-Explorer.</span><span class="sxs-lookup"><span data-stu-id="c6034-327">With the Skype for Business Server 2015 ISO attached, open the root directory of the drive it is attached as (Ex: D:\) in File Explorer.</span></span>
    - <span data-ttu-id="c6034-328">Kopieren Sie alle Ordner und Dateien in einen Ordner auf einem lokalen Datenträger (Ex: C:\SkypeForBusiness2015ISO).</span><span class="sxs-lookup"><span data-stu-id="c6034-328">Copy all folders and files to a folder on a local disk (Ex: C:\SkypeForBusiness2015ISO).</span></span>
    - <span data-ttu-id="c6034-329">**Hinweis:** Einige Dateien müssen vor dem Installieren von Komponenten aus, für die Unterstützung von TLS 1.2 aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="c6034-329">**Note:** Prior to installing components, some files will need to be updated for support of TLS 1.2.</span></span>
4. <span data-ttu-id="c6034-330">Ersetzen Sie die MSI-EXE-Pakete:</span><span class="sxs-lookup"><span data-stu-id="c6034-330">Replace MSI/EXE Packages:</span></span> 
    - <span data-ttu-id="c6034-331">Ersetzen Sie die vorhandenen Pakete MSI und EXE-Datei im Ordner "/ Setup/amd64 /" des Installationsmediums auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="c6034-331">Replace the existing MSI and EXE packages in the /Setup/amd64/ folder of the installation media on the local machine.</span></span>
    - <span data-ttu-id="c6034-332">SQL 2014 SP2 Express:https://www.microsoft.com/en-us/download/details.aspx?id=53167</span><span class="sxs-lookup"><span data-stu-id="c6034-332">SQL 2014 SP2 Express: https://www.microsoft.com/en-us/download/details.aspx?id=53167</span></span> 
        - <span data-ttu-id="c6034-333">Benennen Sie auf dem lokalen Computer SQLEXPR_x64, und Ersetzen Sie die vorhandene Datei in das Setup/amd64/Ordner der-Installationsmedien.</span><span class="sxs-lookup"><span data-stu-id="c6034-333">Rename to SQLEXPR_x64 on the local machine, and replace the existing file in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="c6034-334">SQL Native Client:https://www.microsoft.com/en-us/download/details.aspx?id=50402</span><span class="sxs-lookup"><span data-stu-id="c6034-334">SQL Native Client: https://www.microsoft.com/en-us/download/details.aspx?id=50402</span></span> 
        - <span data-ttu-id="c6034-335">**Hinweis:** Benennen Sie dies bei Bedarf sqlncli.msi, und klicken Sie dann ersetzen die vorhandene Datei, die in der Setup/amd64 vorhanden ist/Ordner der-Installationsmedien.</span><span class="sxs-lookup"><span data-stu-id="c6034-335">**Note:** Rename this if necessary to sqlncli.msi, and then replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="c6034-336">SQL Management Objects:https://www.microsoft.com/en-us/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="c6034-336">SQL Management Objects: https://www.microsoft.com/en-us/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="c6034-337">**Hinweis:** Das Feature Pack müssen viele Elemente, die heruntergeladen werden können.</span><span class="sxs-lookup"><span data-stu-id="c6034-337">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="c6034-338">Wählen Sie nur SharedManagementObjects.msi herunterladen.</span><span class="sxs-lookup"><span data-stu-id="c6034-338">Select to download SharedManagementObjects.msi only.</span></span>
        - <span data-ttu-id="c6034-339">**Hinweis:** Ersetzen Sie die vorhandene Datei, die in der Setup/amd64 vorhanden ist/Ordner der-Installationsmedien.</span><span class="sxs-lookup"><span data-stu-id="c6034-339">**Note:** Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="c6034-340">SQL-CLR-Typen:https://www.microsoft.com/en-us/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="c6034-340">SQL CLR Types: https://www.microsoft.com/en-us/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="c6034-341">**Hinweis:** Das Feature Pack müssen viele Elemente, die heruntergeladen werden können.</span><span class="sxs-lookup"><span data-stu-id="c6034-341">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="c6034-342">Wählen Sie nur CQLSysClrTypes.msi herunterladen</span><span class="sxs-lookup"><span data-stu-id="c6034-342">Select to download CQLSysClrTypes.msi only</span></span>
        - <span data-ttu-id="c6034-343">**Hinweis**: Ersetzen Sie die vorhandene Datei, die in der Setup/amd64 vorhanden ist/Ordner der-Installationsmedien.</span><span class="sxs-lookup"><span data-stu-id="c6034-343">**Note**: Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
5. <span data-ttu-id="c6034-344">Installieren Sie die Hauptkomponenten:</span><span class="sxs-lookup"><span data-stu-id="c6034-344">Install Core Components:</span></span> 
    - <span data-ttu-id="c6034-345">Führen Sie Setup.exe von der Setup/amd64/Ordner der-Installationsmedien.</span><span class="sxs-lookup"><span data-stu-id="c6034-345">Run Setup.exe from the Setup/amd64/ folder of the installation media.</span></span> <span data-ttu-id="c6034-346">Führen Sie die Anweisungen, um die Hauptkomponenten installieren</span><span class="sxs-lookup"><span data-stu-id="c6034-346">Follow the instructions to install Core Components</span></span>
    - <span data-ttu-id="c6034-347">Hauptkomponenten zu schließen.</span><span class="sxs-lookup"><span data-stu-id="c6034-347">Close Core Components.</span></span>
6. <span data-ttu-id="c6034-348">Aktualisieren Sie die Hauptkomponenten:</span><span class="sxs-lookup"><span data-stu-id="c6034-348">Update Core Components:</span></span> 
    - <span data-ttu-id="c6034-349">Laden Sie die Skype für Business Update-Installationsprogramm.</span><span class="sxs-lookup"><span data-stu-id="c6034-349">Download the Skype for Business Update Installer.</span></span>
    - <span data-ttu-id="c6034-350">Führen Sie das Installationsprogramm, um die Hauptkomponenten zu aktualisieren, und installieren die Leistungsindikatoren.</span><span class="sxs-lookup"><span data-stu-id="c6034-350">Run the installer to update Core Components and install the performance counters.</span></span>
    - <span data-ttu-id="c6034-351">**Hinweis:** Die Version von CU6HF2 wird das Feature für automatische Updates derzeit nur bis CU6 zu installieren.</span><span class="sxs-lookup"><span data-stu-id="c6034-351">**Note:** As of the release of CU6HF2, the auto-update feature currently only will install up to CU6.</span></span> <span data-ttu-id="c6034-352">Aus diesem Grund muss der Updater separat ausgeführt werden, um Hauptkomponenten auf 6.0.9319.516 zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="c6034-352">Therefore, the updater must be run separately to update Core Components to 6.0.9319.516.</span></span>
    - <span data-ttu-id="c6034-353">Referenz:https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015</span><span class="sxs-lookup"><span data-stu-id="c6034-353">Reference: https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015</span></span>
7. <span data-ttu-id="c6034-354">Installieren der Verwaltungstools (Optional):</span><span class="sxs-lookup"><span data-stu-id="c6034-354">Install Administrative Tools (Optional):</span></span> 
    - <span data-ttu-id="c6034-355">Hiermit wird die Microsoft SQL Server 2012 Native Client sowie SQL Server 2014 Management Objects (x64) und Microsoft System CLR-Typen für SQL Server 2014 (x64) verwenden die aktualisierten Dateien installiert.</span><span class="sxs-lookup"><span data-stu-id="c6034-355">This will install the Microsoft SQL Server 2012 Native Client, SQL Server 2014 Management Objects (x64), and Microsoft System CLR Types for SQL Server 2014 (x64) using the updated files.</span></span> <span data-ttu-id="c6034-356">Darüber hinaus wird der Skype für Business Server 2015 Topologie-Generator und der Systemsteuerung auf dem lokalen Computer verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="c6034-356">Additionally, the Skype for Business Server 2015 Topology Builder and Control Panel will be available on the local machine.</span></span>
8. <span data-ttu-id="c6034-357">Lokalen Konfigurationsspeicher installieren (Schritt 1):</span><span class="sxs-lookup"><span data-stu-id="c6034-357">Install Local Configuration Store (Step 1):</span></span> 
     - <span data-ttu-id="c6034-358">Öffnen Sie den Bereitstellungs-Assistenten, klicken Sie auf Installieren oder aktualisieren Skype für Business Server-System und klicken Sie auf **Ausführen** , in Schritt 1: lokalen Konfigurationsspeicher installieren.</span><span class="sxs-lookup"><span data-stu-id="c6034-358">Open the Deployment Wizard, click Install or Update Skype for Business Server System, and click on **Run** at Step 1: Install Local Configuration Store.</span></span>
     - <span data-ttu-id="c6034-359">Klicken Sie auf **Weiter** im Dialogfeld **Lokalen Konfigurationsspeicher installieren** .</span><span class="sxs-lookup"><span data-stu-id="c6034-359">Click **Next** in the **Install Local Configuration Store** dialog box.</span></span>
     <span data-ttu-id="c6034-360">![Dialogfeld lokalen Konfigurationsspeicher installieren](../../media/local-configuration-store.png)</span><span class="sxs-lookup"><span data-stu-id="c6034-360">![Install Local Configuration Store dialog box](../../media/local-configuration-store.png)</span></span>
     - <span data-ttu-id="c6034-361">Überprüfen Sie die Ergebnisse, und stellen Sie sicher, dass der Status der Aufgabe abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="c6034-361">Review the results, and ensure that the Task Status is Completed.</span></span> <span data-ttu-id="c6034-362">Überprüfen Sie die daraus resultierende Protokolldatei durch Klicken auf **Protokoll anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="c6034-362">Review the resulting log file by clicking **View Log**.</span></span>
     <span data-ttu-id="c6034-363">![Aufgabenstatus wird als abgeschlossen](../../media/local-configuration-task-completed.png)</span><span class="sxs-lookup"><span data-stu-id="c6034-363">![Task status shows as Completed](../../media/local-configuration-task-completed.png)</span></span>
     - <span data-ttu-id="c6034-364">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="c6034-364">Click **Finish**.</span></span>
9. <span data-ttu-id="c6034-365">Einrichten oder Entfernen von Skype für Business Server-Komponenten (Schritt2):</span><span class="sxs-lookup"><span data-stu-id="c6034-365">Set up or remove Skype for Business Server Components (Step 2):</span></span>
    - <span data-ttu-id="c6034-366">Öffnen Sie den Bereitstellungs-Assistenten, klicken Sie auf **installieren oder aktualisieren Skype für Business Server-System**und klicken Sie auf **Ausführen** , um Schritt2: Einrichten oder Entfernen von Skype für Business Server-Komponenten</span><span class="sxs-lookup"><span data-stu-id="c6034-366">Open the Deployment Wizard, click **Install or Update Skype for Business Server System**, and click **Run** at Step 2: Set up or Remove Skype for Business Server Components</span></span>
    - <span data-ttu-id="c6034-367">Klicken Sie auf **nächste** in das Festlegen von Skype für Business Server-Komponenten (Dialogfeld).</span><span class="sxs-lookup"><span data-stu-id="c6034-367">Click **Next** in the Set Up Skype for Business Server Components dialog box.</span></span>
    <span data-ttu-id="c6034-368">![Das Festlegen von Skype für Fenster Business Server-Komponenten](../../media/set-up-skype-for-business-server-components-window.png)</span><span class="sxs-lookup"><span data-stu-id="c6034-368">![the Set Up Skype for Business Server Components window](../../media/set-up-skype-for-business-server-components-window.png)</span></span>
    - <span data-ttu-id="c6034-369">Überprüfen Sie die melden Sie sich mit Protokoll anzeigen, und Überprüfen von Setup ohne Probleme abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="c6034-369">Review the log using View Log, and validate that setup completed without issues.</span></span> 
    - <span data-ttu-id="c6034-370">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="c6034-370">Click **Finish**.</span></span>
10. <span data-ttu-id="c6034-371">Zusätzliche Installation und Konfiguration nach Bedarf fort (Sie können fortsetzen normalen Installationsverfahren zu diesem Zeitpunkt).</span><span class="sxs-lookup"><span data-stu-id="c6034-371">Proceed with additional installation and configuration as required (you can resume normal installation procedures at this point).</span></span>
