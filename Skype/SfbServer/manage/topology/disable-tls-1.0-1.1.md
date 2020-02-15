---
title: Deaktivieren von TLS 1.0/1.1 in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Zusammenfassung: Vorbereiten und Implementieren der Deaktivierung von TLS 1,0 und 1,1 in ihren Umgebungen.'
ms.openlocfilehash: 0a25060463ed3b67db8ca523171c2bc48660293d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42012748"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a><span data-ttu-id="3daa9-103">Deaktivieren von TLS 1.0/1.1 in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="3daa9-103">Disable TLS 1.0/1.1 in Skype for Business Server 2015</span></span>

<span data-ttu-id="3daa9-104">Der Zweck dieses Artikels besteht darin, die erforderlichen Anleitungen für die Vorbereitung und Implementierung der Deaktivierung von TLS 1,0 und 1,1 in ihren Umgebungen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="3daa9-104">The purpose of this article is to provide the necessary guidance for you to prepare for and implement disabling TLS 1.0 and 1.1 in your environments.</span></span> <span data-ttu-id="3daa9-105">Dieser Vorgang erfordert eine umfassende Planung und Vorbereitung.</span><span class="sxs-lookup"><span data-stu-id="3daa9-105">This process requires extensive planning and preparation.</span></span> <span data-ttu-id="3daa9-106">Lesen Sie sorgfältig alle Informationen in diesem Artikel, wenn Sie den Plan zum Deaktivieren von TLS 1,0 und 1,1 für Ihre Organisation erstellen.</span><span class="sxs-lookup"><span data-stu-id="3daa9-106">Please carefully review all of the information in this article as you make your plan to disable TLS 1.0 and 1.1 for your organization.</span></span> <span data-ttu-id="3daa9-107">Beachten Sie, dass es viele externe Abhängigkeiten und Verbindungsbedingungen gibt, die durch Deaktivieren von TLS 1.0/1.1 beeinträchtigt werden könnten, sodass umfangreiche Planung und Tests gewährleistet sind.</span><span class="sxs-lookup"><span data-stu-id="3daa9-107">Note that there are many external dependencies and connectivity conditions that could be impacted by disabling TLS 1.0/1.1, so extensive planning and testing is warranted.</span></span>

## <a name="in-this-article"></a><span data-ttu-id="3daa9-108">Inhalt dieses Artikels</span><span class="sxs-lookup"><span data-stu-id="3daa9-108">In this article</span></span>

- [<span data-ttu-id="3daa9-109">Hintergrund und Bereich</span><span class="sxs-lookup"><span data-stu-id="3daa9-109">Background and scope</span></span>](#background)
- [<span data-ttu-id="3daa9-110">Voraussetzungen und Prozess</span><span class="sxs-lookup"><span data-stu-id="3daa9-110">Prerequisites and process</span></span>](#prerequisites-and-process)
- [<span data-ttu-id="3daa9-111">Erweiterte Bereitstellungsszenarien</span><span class="sxs-lookup"><span data-stu-id="3daa9-111">Advanced deployment scenarios</span></span>](#advanced-deployment-scenarios)

## <a name="background"></a><span data-ttu-id="3daa9-112">Hintergrund</span><span class="sxs-lookup"><span data-stu-id="3daa9-112">Background</span></span>

<span data-ttu-id="3daa9-113">Die primären Treiber für die Bereitstellung von TLS 1,0 und 1,1 deaktivieren Unterstützung für Skype for Business Server lokal sind die Standards für die Informationsverarbeitung (Payment Card Industry, PCI) Security Standards Council und Federal Information Processing.</span><span class="sxs-lookup"><span data-stu-id="3daa9-113">The primary drivers for providing TLS 1.0 and 1.1 disable support for Skype for Business Server On-Premises are Payment Card Industry (PCI) Security Standards Council and Federal Information Processing Standards requirements.</span></span> <span data-ttu-id="3daa9-114">Weitere Informationen zu PCI-Anforderungen finden Sie [hier](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).</span><span class="sxs-lookup"><span data-stu-id="3daa9-114">More information for PCI requirements can be found [here](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).</span></span>  <span data-ttu-id="3daa9-115">Microsoft kann keine Anleitungen dazu geben, ob Ihre Organisation diese oder andere Anforderungen einhalten muss.</span><span class="sxs-lookup"><span data-stu-id="3daa9-115">Microsoft cannot provide guidance on whether or not your organization is required to adhere to these or other requirements.</span></span> <span data-ttu-id="3daa9-116">Sie müssen feststellen, ob Sie TLS 1,0 und/oder 1,1 in ihren Umgebungen deaktivieren müssen.</span><span class="sxs-lookup"><span data-stu-id="3daa9-116">You must determine if it is required for you to disable TLS 1.0 and/or 1.1 in your environments.</span></span>

<span data-ttu-id="3daa9-117">Microsoft hat ein Whitepaper zu TLS erstellt, das [hier](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)verfügbar ist, und wir empfehlen auch das in diesem [Exchange-Blog](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)verfügbare Hintergrund Lesematerial.</span><span class="sxs-lookup"><span data-stu-id="3daa9-117">Microsoft has produced a white paper on TLS available [here](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/), and we also recommend the background reading available in this [Exchange blog](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).</span></span>

## <a name="supportability-scope"></a><span data-ttu-id="3daa9-118">Unterstützungsbereich</span><span class="sxs-lookup"><span data-stu-id="3daa9-118">Supportability Scope</span></span>

<span data-ttu-id="3daa9-119">Der *Bereich* bezieht sich auf Unterstützungsgrenzen.</span><span class="sxs-lookup"><span data-stu-id="3daa9-119">*Scope* refers to supportability boundaries.</span></span> <span data-ttu-id="3daa9-120">*Vollständig getestet und unterstützt* bedeutet, dass wir die Deaktivierung von TLS 1,0 und 1,1 für die aufgeführten Produktversionen vollständig unterstützen und getestet haben.</span><span class="sxs-lookup"><span data-stu-id="3daa9-120">*Fully tested and supported* means we fully support and have tested disabling of TLS 1.0 and 1.1 for the listed product versions.</span></span> <span data-ttu-id="3daa9-121">*Derzeit untersucht wird* , bedeutet nur, dass; Wir untersuchen aktiv, diese Produkte in den Geltungsbereich der TLS-Deaktivierungs Unterstützung zu bringen.</span><span class="sxs-lookup"><span data-stu-id="3daa9-121">*Currently being investigated* means just that; we are actively investigating bringing these products into scope for TLS disable support.</span></span> <span data-ttu-id="3daa9-122">*Außerhalb des Bereichs* bedeutet, dass diese Produktversionen die Deaktivierung von TLS 1,0 oder 1,1 nicht unterstützen, und es kann nicht mit bekannten Ausnahmen funktionieren.</span><span class="sxs-lookup"><span data-stu-id="3daa9-122">*Out of scope* means these product versions do not support disabling TLS 1.0 or 1.1 and will not work, with noted exceptions.</span></span>

### <a name="fully-tested-and-supported-servers"></a><span data-ttu-id="3daa9-123">Vollständig getestete und unterstützte Server</span><span class="sxs-lookup"><span data-stu-id="3daa9-123">Fully tested and supported servers</span></span>

- <span data-ttu-id="3daa9-124">Skype for Business Server 2019 ku1 17.0.2046.123 (Juni 2019) oder höher</span><span class="sxs-lookup"><span data-stu-id="3daa9-124">Skype for Business Server 2019 CU1 17.0.2046.123 (June 2019) or higher</span></span>
- <span data-ttu-id="3daa9-125">Skype for Business Server 2015 ku9 6.0.9319.548 (Mai 2019) oder höher auf Windows Server 2012 (mit KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) oder einem abgelösten Update), 2012 R2 oder 2016.</span><span class="sxs-lookup"><span data-stu-id="3daa9-125">Skype for Business Server 2015 CU9 6.0.9319.548 (May 2019) or higher on Windows Server 2012 (with KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), 2012 R2 or 2016.</span></span>
- <span data-ttu-id="3daa9-126">In-Place-Upgrade Skype for Business Server 2015 mit ku9 6.0.9319.548 (Mai 2019) oder höher auf Windows Server 2008 R2, 2012 (mit KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) oder Ersetzen von Updates) oder 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="3daa9-126">In-place Upgraded Skype for Business Server 2015, with CU9 6.0.9319.548 (May 2019) or higher on Windows Server 2008 R2, 2012 (with KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), or 2012 R2.</span></span>
- <span data-ttu-id="3daa9-127">Exchange-Konnektivität und Outlook Web App mit Exchange Server 2010 SP3 RU19 oder höher, Anleitung [hier](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span><span class="sxs-lookup"><span data-stu-id="3daa9-127">Exchange Connectivity and Outlook Web App with Exchange Server 2010 SP3 RU19 or higher, guidance [here](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span></span>
- <span data-ttu-id="3daa9-128">Survivable Branch Appliance (SBA) mit Skype for Business Server 2015 CU6 HF2 oder höher (bestätigen Sie mit Ihrem Anbieter, dass Sie die entsprechenden Updates verpackt haben und für Ihre Appliance zur Verfügung gestellt wurden)</span><span class="sxs-lookup"><span data-stu-id="3daa9-128">Survivable Branch Appliance (SBA) with Skype for Business Server 2015 CU6 HF2 or higher (confirm with your vendor that they packaged the appropiate updates and have been made available for your appliance)</span></span>
- <span data-ttu-id="3daa9-129">Survivable Branch Server (SBS) mit Skype for Business Server 2015 CU6 HF2 oder höher</span><span class="sxs-lookup"><span data-stu-id="3daa9-129">Survivable Branch Server (SBS) with Skype for Business Server 2015 CU6 HF2 or higher</span></span>
- <span data-ttu-id="3daa9-130">Nur lync Server 2013- **Edge-Rolle**, dies liegt daran, dass die Edge-Rolle keine Abhängigkeit von Windows Fabric 1,0 hat.</span><span class="sxs-lookup"><span data-stu-id="3daa9-130">Lync Server 2013 **Edge Role Only**, this is because Edge role does not have a dependency on Windows Fabric 1.0.</span></span>

### <a name="fully-tested-and-supported-clients"></a><span data-ttu-id="3daa9-131">Vollständig getestete und unterstützte Clients</span><span class="sxs-lookup"><span data-stu-id="3daa9-131">Fully tested and supported clients</span></span>

- <span data-ttu-id="3daa9-132">Lync 2013 (Skype for Business) Desktop Client, MSI und C2R, einschließlich grundlegender [15.0.5023.1000 oder höher](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span><span class="sxs-lookup"><span data-stu-id="3daa9-132">Lync 2013 (Skype for Business) Desktop Client, MSI and C2R, including Basic [15.0.5023.1000 or higher](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span></span>
- <span data-ttu-id="3daa9-133">Skype for Business 2016 Desktop Client, MSI [16.0.4678.1000 oder höher](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), einschließlich Basic</span><span class="sxs-lookup"><span data-stu-id="3daa9-133">Skype for Business 2016 Desktop Client, MSI [16.0.4678.1000 or higher](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), including Basic</span></span>
- <span data-ttu-id="3daa9-134">Skype for Business 2016 klicken Sie auf Ausführen erfordern die Updates vom [April 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) :</span><span class="sxs-lookup"><span data-stu-id="3daa9-134">Skype for Business 2016 Click to Run Require the [April 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) Updates:</span></span> 
    - <span data-ttu-id="3daa9-135">Monatliches und halbjährliches Ziel,\.16\.0\.9126 2152 oder höher</span><span class="sxs-lookup"><span data-stu-id="3daa9-135">Monthly and Semi-Annual Targeted, 16\.0\.9126\.2152 or higher</span></span>
    - <span data-ttu-id="3daa9-136">Halbjährlicher und verzögerter Kanal, 16\.0\.8431\.2242 oder höher</span><span class="sxs-lookup"><span data-stu-id="3daa9-136">Semi-Annual and Deferred Channel, 16\.0\.8431\.2242 or higher</span></span>
- <span data-ttu-id="3daa9-137">Skype for Business auf Mac 16,15 oder höher</span><span class="sxs-lookup"><span data-stu-id="3daa9-137">Skype for Business on Mac 16.15 or higher</span></span>
- <span data-ttu-id="3daa9-138">Skype for Business für IOS und Android 6,19 oder höher</span><span class="sxs-lookup"><span data-stu-id="3daa9-138">Skype for Business for iOS and Android 6.19 or higher</span></span>
- <span data-ttu-id="3daa9-139">Microsoft Teams-Räume (bisher als Skype Room System v2 SRS v2 bezeichnet) 4.0.64.0 (Dezember 2018) oder höher</span><span class="sxs-lookup"><span data-stu-id="3daa9-139">Microsoft Teams Rooms (previously known as Skype Room System V2 SRS V2) 4.0.64.0 (December 2018) or higher</span></span>
- <span data-ttu-id="3daa9-140">Surface Hub-Update für Team Edition basierend auf KB4499162 (Mai 2019, OS Build 15063,1835) oder höher</span><span class="sxs-lookup"><span data-stu-id="3daa9-140">Surface Hub update for Team edition based on KB4499162 (May 2019, OS Build 15063.1835) or higher</span></span>
- <span data-ttu-id="3daa9-141">Skype-Webanwendung 2015 CU6 HF2 oder höher (mit Server ausgeliefert)</span><span class="sxs-lookup"><span data-stu-id="3daa9-141">Skype Web App 2015 CU6 HF2 or higher (ships with Server)</span></span>

### <a name="currently-being-investigated"></a><span data-ttu-id="3daa9-142">Derzeit untersucht</span><span class="sxs-lookup"><span data-stu-id="3daa9-142">Currently being investigated</span></span>

- <span data-ttu-id="3daa9-143">Anruf Qualitäts Dashboard (neue Installation nach TLS 1,0, 1,1 wurden deaktiviert, siehe unten) \*</span><span class="sxs-lookup"><span data-stu-id="3daa9-143">Call Quality Dashboard (new install after TLS 1.0, 1.1 have been disabled, see below)\*</span></span>
 
### <a name="out-of-scope"></a><span data-ttu-id="3daa9-144">Nicht inbegriffen</span><span class="sxs-lookup"><span data-stu-id="3daa9-144">Out of scope</span></span>

<span data-ttu-id="3daa9-145">Sofern nicht anders angegeben, sind die folgenden Produkte nicht im Bereich für TLS 1.0/1.1 Disable Support und funktionieren nicht in einer Umgebung, in der TLS 1,0 und 1,1 deaktiviert wurden.</span><span class="sxs-lookup"><span data-stu-id="3daa9-145">Except where noted, the following products are not in scope for TLS 1.0/1.1 disable support and will not function in an environment where TLS 1.0 and 1.1 have been disabled.</span></span> <span data-ttu-id="3daa9-146">Was das bedeutet: Wenn Sie weiterhin out-of-Scope-Server oder-Clients verwenden, müssen Sie diese aktualisieren oder entfernen, wenn Sie TLS 1.0/1.1 Anywhere in Ihrer Skype for Business Server lokalen Bereitstellung deaktivieren müssen.</span><span class="sxs-lookup"><span data-stu-id="3daa9-146">What this means: if you still utilize out-of-scope servers or clients, you must update or remove these if you need to disable TLS 1.0/1.1 anywhere in your Skype for Business Server on-premises deployment.</span></span>

- <span data-ttu-id="3daa9-147">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3daa9-147">Lync Server 2013</span></span>
- <span data-ttu-id="3daa9-148">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="3daa9-148">Lync Server 2010</span></span>
- <span data-ttu-id="3daa9-149">Windows Server 2008 oder niedriger</span><span class="sxs-lookup"><span data-stu-id="3daa9-149">Windows Server 2008 or lower</span></span>
- <span data-ttu-id="3daa9-150">Lync für Mac 2011</span><span class="sxs-lookup"><span data-stu-id="3daa9-150">Lync for Mac 2011</span></span>
- <span data-ttu-id="3daa9-151">Lync 2013 für Mobile-IOS, iPad, Android oder Windows Phone</span><span class="sxs-lookup"><span data-stu-id="3daa9-151">Lync 2013 for Mobile - iOS, iPad, Android or Windows Phone</span></span>
- <span data-ttu-id="3daa9-152">Lync "MX" Windows Store-Client</span><span class="sxs-lookup"><span data-stu-id="3daa9-152">Lync "MX" Windows Store client</span></span>
- <span data-ttu-id="3daa9-153">Lync Room System (aka</span><span class="sxs-lookup"><span data-stu-id="3daa9-153">Lync Room System (a.k.a.</span></span> <span data-ttu-id="3daa9-154">SRSv1).</span><span class="sxs-lookup"><span data-stu-id="3daa9-154">SRSv1).</span></span> <span data-ttu-id="3daa9-155">LRS hat am 9. Oktober 2018 das Ende der Unterstützung erreicht und wird nicht zur Unterstützung von TLS 1,2 aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="3daa9-155">LRS reached end of support on October 9, 2018 and will not be updated to support TLS 1.2.</span></span>
- <span data-ttu-id="3daa9-156">Alle lync 2010 Clients</span><span class="sxs-lookup"><span data-stu-id="3daa9-156">All Lync 2010 clients</span></span>
- <span data-ttu-id="3daa9-157">Lync Phone Edition-Anleitung [hier](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035)aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="3daa9-157">Lync Phone Edition - updated guidance [here](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).</span></span>
- <span data-ttu-id="3daa9-158">2013 basierte Survivable Branch Appliance (SBA) oder Survivable Branch Server (SBS)</span><span class="sxs-lookup"><span data-stu-id="3daa9-158">2013 based Survivable Branch Appliance (SBA) or Survivable Branch Server (SBS)</span></span>
- <span data-ttu-id="3daa9-159">Cloud Connector Edition (CCE)</span><span class="sxs-lookup"><span data-stu-id="3daa9-159">Cloud Connector Edition (CCE)</span></span>
- <span data-ttu-id="3daa9-160">Skype for Business für Windows Phone</span><span class="sxs-lookup"><span data-stu-id="3daa9-160">Skype for Business for Windows Phone</span></span>

### <a name="exceptions"></a><span data-ttu-id="3daa9-161">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="3daa9-161">Exceptions</span></span>

#### <a name="lync-server-2013"></a><span data-ttu-id="3daa9-162">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3daa9-162">Lync Server 2013</span></span>

<span data-ttu-id="3daa9-163">Lync Server 2013 übernimmt eine Abhängigkeit von Windows Fabric, Version 1,0.</span><span class="sxs-lookup"><span data-stu-id="3daa9-163">Lync Server 2013 takes a dependency on Windows Fabric version 1.0.</span></span>  <span data-ttu-id="3daa9-164">In der Entwurfsphase für lync Server 2013 wurde Windows Fabric 1,0 für die überzeugende und neue verteilte Architektur ausgewählt, um Replikation, hohe Verfügbarkeit und Fehlertoleranz bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="3daa9-164">In the design phase for Lync Server 2013, Windows Fabric 1.0 was chosen for its compelling and new distributed architecture to provide replication, high availability, and fault tolerance.</span></span>  <span data-ttu-id="3daa9-165">Im Laufe der Zeit haben sowohl Skype for Business Server als auch Windows Fabric diese gemeinsame Architektur mit erheblichem Re-Design in den nachfolgenden Versionen erheblich verbessert.</span><span class="sxs-lookup"><span data-stu-id="3daa9-165">Over time, both Skype for Business Server and Windows Fabric have greatly improved this joint architecture with significant re-design in subsequent versions.</span></span>  <span data-ttu-id="3daa9-166">Der aktuelle Skype for Business 2015 Server verwendet beispielsweise Windows Fabric 3,0.</span><span class="sxs-lookup"><span data-stu-id="3daa9-166">Current Skype for Business 2015 Server uses Windows Fabric 3.0, for example.</span></span>

<span data-ttu-id="3daa9-167">Leider unterstützt Windows Fabric 1,0 **TLS 1,2 nicht.  Wir werden jedoch lync Server 2013 aktualisieren, um mit TLS 1,2 zu arbeiten**.</span><span class="sxs-lookup"><span data-stu-id="3daa9-167">Unfortunately, Windows Fabric 1.0 **does not support TLS 1.2.  However, we will be updating Lync Server 2013 to work with TLS 1.2**.</span></span> <span data-ttu-id="3daa9-168">Dieser wird im nächsten kumulativen Update für lync Server 2013 bereit stehen.</span><span class="sxs-lookup"><span data-stu-id="3daa9-168">This will be coming in the next Cumulative Update for Lync Server 2013.</span></span>  <span data-ttu-id="3daa9-169">Wir bieten TLS 1,2-Unterstützung, um Koexistenz-, Migrations-, Verbund-und Hybrid Szenarien zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="3daa9-169">We're providing TLS 1.2 support to enable co-existence, migration, federation, and hybrid scenarios.</span></span>

<span data-ttu-id="3daa9-170">Wenn Ihre Organisation TLS 1,0 und 1,1 deaktivieren muss und Sie derzeit lync Server 2013 verwenden, empfehlen wir Ihnen, ihren Planungsprozess mit der Möglichkeit zu beginnen, dass Sie möglicherweise ein direktes Upgrade oder eine parallele Migration (neue Pools, Benutzer verschieben) zu Skype for Business Server 2015 oder höher.</span><span class="sxs-lookup"><span data-stu-id="3daa9-170">If your organization is required to disable TLS 1.0 and 1.1, and you currently use Lync Server 2013, we recommend you begin your planning process, with the possibility you may have to In-place upgrade or Side-by-Side migrate (new pools, move users) to Skype for Business Server 2015 or higher.</span></span>  <span data-ttu-id="3daa9-171">Möglicherweise möchten Sie die Migration zu Skype for Business Online beschleunigen.</span><span class="sxs-lookup"><span data-stu-id="3daa9-171">Or you may want to accelerate migration to Skype for Business Online.</span></span>

#### <a name="call-quality-dashboard"></a><span data-ttu-id="3daa9-172">Anruf Qualitäts Dashboard</span><span class="sxs-lookup"><span data-stu-id="3daa9-172">Call Quality Dashboard</span></span>

<span data-ttu-id="3daa9-173">Das lokale Anruf Qualitäts Dashboard verfügt derzeit über eine Abhängigkeit von TLS 1,0 bei der Neuinstallation (erstmalige Installation in Ihrer lokalen Umgebung).</span><span class="sxs-lookup"><span data-stu-id="3daa9-173">On-Premises Call Quality Dashboard currently has a dependency on TLS 1.0 during new install (first time installing into your On-Premises environments).</span></span>  <span data-ttu-id="3daa9-174">Wir untersuchen derzeit dieses Problem und planen, eine Korrektur in naher Zukunft freizugeben.</span><span class="sxs-lookup"><span data-stu-id="3daa9-174">We are currently investigating this issue and plan to release a fix in the near future.</span></span>  <span data-ttu-id="3daa9-175">Wenn Sie planen, CQD zu installieren und außerdem TLS 1,0 zu deaktivieren, wird empfohlen, zuerst die CQD-Installation abzuschließen und dann mit der Deaktivierung von TLS 1,0 fortzufahren.</span><span class="sxs-lookup"><span data-stu-id="3daa9-175">If you are planning to install CQD and also disable TLS 1.0, we recommend that you complete CQD installation first, and then proceed with TLS 1.0 disabling.</span></span>

#### <a name="third-party-devices"></a><span data-ttu-id="3daa9-176">Geräte von Drittanbietern</span><span class="sxs-lookup"><span data-stu-id="3daa9-176">Third-party devices</span></span>

<span data-ttu-id="3daa9-177">Auf Drittanbietergeräten wie 3PIP-Telefonen, Video Konferenzen, Reverse-Proxies und Lastenausgleichs stellen müssen Sie die TLS 1,2-Unterstützung validieren, sorgfältig testen und bei Bedarf den Anbieter kontaktieren.</span><span class="sxs-lookup"><span data-stu-id="3daa9-177">On third-party devices such as 3PIP phones, Video conferencing, Reverse Proxies and Load Balancers, be sure to validate TLS 1.2 supportability, test carefully, and contact the vendor if needed.</span></span>

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a><span data-ttu-id="3daa9-178">Überlegungen zum Verbund beim Deaktivieren von TLS 1.0/1.1 auf Edge-Servern</span><span class="sxs-lookup"><span data-stu-id="3daa9-178">Federation considerations when disabling TLS 1.0/1.1 on Edge servers</span></span>

<span data-ttu-id="3daa9-179">Sie müssen die Auswirkungen der Deaktivierung von TLS 1.0/1.1 auf Ihren Edge-Servern sorgfältig planen und berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="3daa9-179">You must carefully plan for and consider the impact of disabling TLS 1.0/1.1 on your Edge servers.</span></span>  <span data-ttu-id="3daa9-180">Wenn TLS 1,0 und 1,1 deaktiviert sind, können Sie feststellen, dass andere Organisationen nicht mehr in der Lage sind, mit Ihrer Organisation zu verbünden.</span><span class="sxs-lookup"><span data-stu-id="3daa9-180">Once TLS 1.0 and 1.1 are disabled, you may find that other organizations are no longer be able to federate with your organization.</span></span>

<span data-ttu-id="3daa9-181">Sie können sich dafür entscheiden, TLS 1.0/1.1 auf Ihren Edge-Servern aktiviert zu halten, um die Abwärtskompatibilität mit externen Systemen ohne Patches (SFB 2015, lync 2013) oder älteren (2010) beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="3daa9-181">You may opt to keep TLS 1.0/1.1 enabled on your Edge servers to maintain backward compatibility with non-patched (SfB 2015, Lync 2013) or older (2010) external systems.</span></span>

<span data-ttu-id="3daa9-182">Microsoft kann keine Ratschläge oder Empfehlungen dazu abgeben, ob Ihr Edge-Netzwerk (oder ein beliebiges Netzwerk) unter den PCI-Standard fällt oder nicht. Dies muss durch das jeweilige Unternehmen bestimmt werden.</span><span class="sxs-lookup"><span data-stu-id="3daa9-182">Microsoft cannot provide advice or recommendations on whether or not your Edge network (or any network) falls under PCI standard; that must be determined by the individual company.</span></span>

<span data-ttu-id="3daa9-183">Skype for Business Online ist in der Lage, TLS 1,2 heute, so dass keine Auswirkungen auf Hybrid-/Verbund mit Online erwartet wird.</span><span class="sxs-lookup"><span data-stu-id="3daa9-183">Skype for Business Online is capable of TLS 1.2 today, so no impact to Hybrid/Federation with Online is expected.</span></span>

<span data-ttu-id="3daa9-184">PIC (Public Chat Connectivity) an Skype Consumer Service: Es wird nicht erwartet, dass die Deaktivierung von TLS 1.0/1.1 die [Skype-Konnektivität](../../deploy/deploy-skype-connectivity.md)beeinträchtigt; Microsoft PIC-Gateways sind bereits TLS 1,2-fähig.</span><span class="sxs-lookup"><span data-stu-id="3daa9-184">PIC (Public IM Connectivity) to Skype Consumer service: We do not expect disabling TLS 1.0/1.1 to impact [Skype Connectivity](../../deploy/deploy-skype-connectivity.md); Microsoft PIC Gateways are already TLS 1.2 capable.</span></span>

## <a name="prerequisites-and-process"></a><span data-ttu-id="3daa9-185">Voraussetzungen und Prozess</span><span class="sxs-lookup"><span data-stu-id="3daa9-185">Prerequisites and process</span></span>

<span data-ttu-id="3daa9-186">Wenn TLS 1,0 und 1,1 außerhalb des Bereichs Server deaktiviert sind, funktionieren Clients und Geräte auch länger ordnungsgemäß oder überhaupt nicht, sofern nicht weiter oben erwähnt.</span><span class="sxs-lookup"><span data-stu-id="3daa9-186">Except where noted above, once TLS 1.0 and 1.1 are disabled out-of-scope servers, clients and devices will longer function properly, or at all.</span></span> <span data-ttu-id="3daa9-187">Dies kann bedeuten, dass Sie unterbrechen und auf aktualisierte Anleitungen von Microsoft warten müssen.</span><span class="sxs-lookup"><span data-stu-id="3daa9-187">This may mean you need to pause and wait for updated guidance from Microsoft.</span></span> <span data-ttu-id="3daa9-188">Wenn Sie sicher sind, dass Sie alle Anforderungen erfüllen und einen Plan zum Beheben von Lücken haben, fahren Sie fort.</span><span class="sxs-lookup"><span data-stu-id="3daa9-188">Once you are satisfied that you meet all requirements and have a plan to address gaps, proceed.</span></span>

<span data-ttu-id="3daa9-189">Auf einer hohen Ebene, während Skype for Business Server 2019 bei der Installation zur Verfügung steht, benötigen Skype for Business Server 2015 die Installation von ku9, das Anwenden von Voraussetzungen für .net und SQL, das Bereitstellen von erforderlichen Registrierungsschlüsseln und schließlich eine separate Round of OS Configuration Updates (dh Deaktivieren von TLS 1,0 und 1,1 über den Registrierungsdatei Import).</span><span class="sxs-lookup"><span data-stu-id="3daa9-189">At a high level, while Skype for Business Server 2019 is ready for procedure at install, Skype for Business Server 2015 will require that you install CU9, applying pre-requisite updates to .NET and SQL, deploying prerequisite registry keys, and finally a separate round of OS configuration updates (i.e. disabling TLS 1.0 and 1.1 via registry file import).</span></span> <span data-ttu-id="3daa9-190">Es ist äußerst wichtig, dass Sie die Installation aller Voraussetzungen, einschließlich Skype for Business Server 2015 CU6 HF2, abschließen, bevor Sie TLS 1,0 und 1,1 auf einem beliebigen Server in Ihrer Umgebung deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="3daa9-190">It is critically important that you complete installation of all prerequisites, including Skype for Business Server 2015 CU6 HF2, prior to disabling TLS 1.0 and 1.1 on any server in your environment.</span></span> <span data-ttu-id="3daa9-191">Jeder Skype for Business Server, einschließlich Edge-Rolle und SQL-Backends, erfordert die Updates.</span><span class="sxs-lookup"><span data-stu-id="3daa9-191">Every Skype for Business server, including Edge role and SQL Backends, requires the updates.</span></span> <span data-ttu-id="3daa9-192">Stellen Sie außerdem sicher, dass alle unterstützten (in-Scope) Clients auf die erforderlichen minimal Versionen aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="3daa9-192">Also ensure that all supported (in-scope) clients have been updated to the required minimum versions.</span></span> <span data-ttu-id="3daa9-193">Vergessen Sie nicht, auch die Verwaltungsarbeitsstationen zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="3daa9-193">Don’t forget to update management workstations as well.</span></span>

<span data-ttu-id="3daa9-194">Wir möchten die übliche Reihenfolge der Vorgänge von "Inside Out" für das Upgrade von Skype for Business Servern befolgen.</span><span class="sxs-lookup"><span data-stu-id="3daa9-194">We want to follow the usual order of operations of "inside out" for upgrading Skype for Business servers.</span></span> <span data-ttu-id="3daa9-195">Behandeln Sie Director-Pools, beständigen Chat und verbundene Pools auf die gleiche Weise wie normalerweise.</span><span class="sxs-lookup"><span data-stu-id="3daa9-195">Treat Director pools, Persistent chat, and Paired Pools in the same manner you normally would.</span></span> <span data-ttu-id="3daa9-196">Die Reihenfolge und die Methoden für das Upgrade werden [hier](topology.md) und [hier](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)behandelt.</span><span class="sxs-lookup"><span data-stu-id="3daa9-196">Order and methods for upgrade are covered [here](topology.md) and [here](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>

### <a name="high-level-process"></a><span data-ttu-id="3daa9-197">High-Level-Prozess</span><span class="sxs-lookup"><span data-stu-id="3daa9-197">High-level process</span></span>

1. <span data-ttu-id="3daa9-198">Testen Sie alle Schritte in der Übungseinheit vor dem Konfigurieren von Produktionsservern.</span><span class="sxs-lookup"><span data-stu-id="3daa9-198">Test all steps in your lab prior to configuring production servers.</span></span>
2. <span data-ttu-id="3daa9-199">Sichern und bewahren Sie eine Kopie der exportierten Registrierung auf jedem einzelnen Server, der aktualisiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="3daa9-199">Back up and preserve a copy of exported registry on each and every individual server to be updated.</span></span> <span data-ttu-id="3daa9-200">Sie können keine Registrierungen zwischen Servern freigeben; Sie enthalten eindeutige computerbasierte Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="3daa9-200">You cannot share registries between servers; they contain unique machine-based keys.</span></span>
3. <span data-ttu-id="3daa9-201">Aktualisieren Sie alle Skype for Business 2015 Server auf ku9 oder höher.</span><span class="sxs-lookup"><span data-stu-id="3daa9-201">Upgrade all Skype for Business 2015 servers to CU9 or higher.</span></span> <span data-ttu-id="3daa9-202">Für Skype for Business Server 2019 ein Upgrade auf ku1 oder höher durchführen.</span><span class="sxs-lookup"><span data-stu-id="3daa9-202">For Skype for Business Server 2019, upgrade to CU1 or higher.</span></span>
4. <span data-ttu-id="3daa9-203">Installieren Sie alle erforderlichen Komponenten auf allen Servern.</span><span class="sxs-lookup"><span data-stu-id="3daa9-203">Install all prerequisites to all servers.</span></span>
5. <span data-ttu-id="3daa9-204">Bereitstellen von erforderlichen Registrierungsschlüsseln</span><span class="sxs-lookup"><span data-stu-id="3daa9-204">Deploy prerequisite registry keys.</span></span>
6. <span data-ttu-id="3daa9-205">Stellen Sie sicher, dass alle in-Scope-Clients aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="3daa9-205">Ensure that all in-scope clients are updated.</span></span>
7. <span data-ttu-id="3daa9-206">Deaktivieren Sie TLS 1,0 und 1,1 über den Registrierungs Import.</span><span class="sxs-lookup"><span data-stu-id="3daa9-206">Disable TLS 1.0 and 1.1 via registry import.</span></span>
8. <span data-ttu-id="3daa9-207">Überprüfen, ob Arbeitsauslastungen wie erwartet funktionieren.</span><span class="sxs-lookup"><span data-stu-id="3daa9-207">Validate that workloads are functioning as expected.</span></span>
    - <span data-ttu-id="3daa9-208">Wenn Probleme auftreten, beheben und beheben oder</span><span class="sxs-lookup"><span data-stu-id="3daa9-208">If problems are encountered, troubleshoot and resolve, or</span></span>
    - <span data-ttu-id="3daa9-209">Wiederherstellen der Registrierung aus Schritt 2 zur erneuten Aktivierung von TLS 1,0 und 1,1</span><span class="sxs-lookup"><span data-stu-id="3daa9-209">Restore registry from step 2 to re-enable TLS 1.0 and 1.1</span></span>
9. <span data-ttu-id="3daa9-210">Überprüfen Sie, dass nur TLS 1,2 verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3daa9-210">Validate that only TLS 1.2 is being used.</span></span>

### <a name="install-prerequisites-to-all-servers"></a><span data-ttu-id="3daa9-211">Installieren der erforderlichen Komponenten auf allen Servern</span><span class="sxs-lookup"><span data-stu-id="3daa9-211">Install prerequisites to all servers</span></span>

<span data-ttu-id="3daa9-212">Bevor Sie mit dem Deaktivieren von TLS 1,0 und 1,1 auf Betriebssystemebene in Ihren Skype for Business Server 2015-Bereitstellungen beginnen, ist eine umfassende Abhängigkeits Aktualisierung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="3daa9-212">Extensive dependency updating is required before you begin to disable TLS 1.0 and 1.1 at the operating system level in your Skype for Business Server 2015 deployments.</span></span> <span data-ttu-id="3daa9-213">Im folgenden sind die Mindestversionen aufgeführt, die TLS 1,2 unterstützen können.</span><span class="sxs-lookup"><span data-stu-id="3daa9-213">The following are the minimum versions that can support TLS 1.2.</span></span> <span data-ttu-id="3daa9-214">Stellen Sie alle erforderlichen Updates auf allen Skype for Business Servern in Ihrer Umgebung bereit, bevor Sie mit dem Deaktivieren von TLS 1,0 und 1,1 beginnen.</span><span class="sxs-lookup"><span data-stu-id="3daa9-214">Deploy all prerequisite updates across every Skype for Business server in your environment before you begin disabling TLS 1.0 and 1.1.</span></span>

- <span data-ttu-id="3daa9-215">Skype for Business Server 2015 ku9 6.0.9319.548 (Mai 2019) oder höher</span><span class="sxs-lookup"><span data-stu-id="3daa9-215">Skype for Business Server 2015 CU9 6.0.9319.548 (May 2019) or higher</span></span>
- <span data-ttu-id="3daa9-216">[.NET Framework 4,7](https://www.microsoft.com/download/details.aspx?id=55167) oder höher mit aktivierter SchUseStrongCrypto in der Registrierung (unten bereitgestellt)</span><span class="sxs-lookup"><span data-stu-id="3daa9-216">[.NET Framework 4.7](https://www.microsoft.com/download/details.aspx?id=55167) or higher with SchUseStrongCrypto enabled in the registry (provided below)</span></span>
- <span data-ttu-id="3daa9-217">SQL muss auf allen Skype for Business 2015 Servern und Backends aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="3daa9-217">SQL must be updated on all Skype for Business 2015 servers and backends.</span></span> <span data-ttu-id="3daa9-218">Aktualisieren Sie den Enterprise Edition-Pool SQL-Backends zuerst, dann ihre jeweiligen Fes.</span><span class="sxs-lookup"><span data-stu-id="3daa9-218">Update Enterprise Edition Pool SQL Backends first, then their respective FEs.</span></span> 
    - <span data-ttu-id="3daa9-219">[SQL Server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926)oder höher/SQL Server 2012 SP2 + ku16 oder höher/ [SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014)oder höher/SQL Server 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="3daa9-219">[SQL Server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926), or higher / SQL Server 2012 SP2 + CU16 or higher / [SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014), or higher / SQL Server 2014 SP2</span></span>
     - [<span data-ttu-id="3daa9-220">SQL Server Native Client für SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="3daa9-220">SQL Server Native Client for SQL Server 2012</span></span>](https://www.microsoft.com/download/details.aspx?id=50402)
     - <span data-ttu-id="3daa9-221">[Microsoft ODBC Driver 11 für SQL Server](https://www.microsoft.com/download/details.aspx?id=36434)oder höher</span><span class="sxs-lookup"><span data-stu-id="3daa9-221">[Microsoft ODBC Driver 11 for SQL Server](https://www.microsoft.com/download/details.aspx?id=36434), or higher</span></span>
     - [<span data-ttu-id="3daa9-222">Gemeinsam genutzte Verwaltungsobjekte für SQL Server 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="3daa9-222">Shared Management Objects for SQL Server 2014 SP2</span></span>](https://www.microsoft.com/download/details.aspx?id=53164)
     - [<span data-ttu-id="3daa9-223">SQLSysClrTypes für SQL Server 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="3daa9-223">SQLSysClrTypes for SQL server 2014 SP2</span></span>](https://www.microsoft.com/download/details.aspx?id=42295)

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a><span data-ttu-id="3daa9-224">Grundlegende Schritte zur Installation von Voraussetzungen in der empfohlenen Reihenfolge von Vorgängen</span><span class="sxs-lookup"><span data-stu-id="3daa9-224">Basic steps to install pre-requisites, in recommended order of operations</span></span>

1. <span data-ttu-id="3daa9-225">Installieren Sie das Skype for Business Server ku9-Update auf allen Servern.</span><span class="sxs-lookup"><span data-stu-id="3daa9-225">Install the Skype for Business Server CU9 update to all servers.</span></span> 
    1. <span data-ttu-id="3daa9-226">Installieren Sie das Update für Komponenten mit dem Updater.</span><span class="sxs-lookup"><span data-stu-id="3daa9-226">Install the update to components using the updater.</span></span>
    2. <span data-ttu-id="3daa9-227">Aktualisieren von Datenbankennach dokumentierten Verfahren.</span><span class="sxs-lookup"><span data-stu-id="3daa9-227">Update databases according to documented procedures.</span></span> <span data-ttu-id="3daa9-228">Informationen zu Skype for Business Server 2015 finden Sie unter KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span><span class="sxs-lookup"><span data-stu-id="3daa9-228">For Skype for Business Server 2015, see KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>
    3. <span data-ttu-id="3daa9-229">Überprüfen Sie die Produktfunktionalität in der Bereitstellung, bevor Sie mit anderen Änderungen fortfahren.</span><span class="sxs-lookup"><span data-stu-id="3daa9-229">Validate product functionality in the deployment prior to moving forward with any other changes.</span></span>
2. <span data-ttu-id="3daa9-230">Laden Sie .NET 4,7 Offline Installer herunter.</span><span class="sxs-lookup"><span data-stu-id="3daa9-230">Download .NET 4.7 Offline Installer.</span></span> 
    1. <span data-ttu-id="3daa9-231">Referenz[https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)</span><span class="sxs-lookup"><span data-stu-id="3daa9-231">Reference: [https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)</span></span>
    2. <span data-ttu-id="3daa9-232">Stellen Sie sicher, dass Skype for Business Server 2015 Dienste auf dem Front-End-Server angehalten werden.</span><span class="sxs-lookup"><span data-stu-id="3daa9-232">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
    3. <span data-ttu-id="3daa9-233">Referenz[https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="3daa9-233">Reference: [https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span></span>
    4. <span data-ttu-id="3daa9-234">Ex (Standard Edition):```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="3daa9-234">Ex (Standard Edition): ```Stop-CsWindowsService```</span></span>
    5. <span data-ttu-id="3daa9-235">Ex (Enterprise Edition):```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="3daa9-235">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    6. <span data-ttu-id="3daa9-236">Führen Sie das Installationspaket aus.</span><span class="sxs-lookup"><span data-stu-id="3daa9-236">Run the installer package.</span></span>
    7. <span data-ttu-id="3daa9-237">Starten Sie den Server neu.</span><span class="sxs-lookup"><span data-stu-id="3daa9-237">Reboot the server.</span></span>
3. <span data-ttu-id="3daa9-238">Aktualisieren Sie SQL Express 2014 auf allen Servern.</span><span class="sxs-lookup"><span data-stu-id="3daa9-238">Update SQL Express 2014 on all servers.</span></span> 
    1. <span data-ttu-id="3daa9-239">Referenz[https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span><span class="sxs-lookup"><span data-stu-id="3daa9-239">Reference: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span></span>
    2. <span data-ttu-id="3daa9-240">Herunterladen von SQL 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="3daa9-240">Download SQL 2014 SP2</span></span> 
        - <span data-ttu-id="3daa9-241">Referenz[https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)</span><span class="sxs-lookup"><span data-stu-id="3daa9-241">Reference: [https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)</span></span>
    3. <span data-ttu-id="3daa9-242">Kopieren Sie das Installationsmedium in einen Ordner auf dem Server (z. b.: \ 01_2014SqlSp2).</span><span class="sxs-lookup"><span data-stu-id="3daa9-242">Copy the installation media to a folder on the server (Ex: C:\01_2014SqlSp2)</span></span>
    4. <span data-ttu-id="3daa9-243">Sicherstellen, dass Skype for Business Server 2015 Dienste auf dem Front-End-Server angehalten werden</span><span class="sxs-lookup"><span data-stu-id="3daa9-243">Ensure Skype for Business Server 2015 services are stopped on the Front End server</span></span> 
        - <span data-ttu-id="3daa9-244">Ex (Standard Edition):```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="3daa9-244">Ex (Standard Edition): ```Stop-CsWindowsService```</span></span>
        - <span data-ttu-id="3daa9-245">Ex (Enterprise Edition):```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="3daa9-245">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    5. <span data-ttu-id="3daa9-246">Öffnen einer Administrator-Eingabeaufforderung und Aktualisieren aller installierten Komponenten und Instanzen</span><span class="sxs-lookup"><span data-stu-id="3daa9-246">Open an Admin Command Prompt, and upgrade all installed components and instances</span></span> 
        - <span data-ttu-id="3daa9-247">Beispiel: c \ 01_2014SqlSp2 \sqlserver2014sp2-kb3171021-x64-ENU.exe/QS-Parameter/IAcceptSQLServerLicenseTerms/Action = Patch/AllInstances</span><span class="sxs-lookup"><span data-stu-id="3daa9-247">Example: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances</span></span>
4. <span data-ttu-id="3daa9-248">Aktualisieren von SQL Native Client.</span><span class="sxs-lookup"><span data-stu-id="3daa9-248">Update SQL Native Client.</span></span> 
    1. <span data-ttu-id="3daa9-249">Referenz: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span><span class="sxs-lookup"><span data-stu-id="3daa9-249">Reference: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span></span>
    2. <span data-ttu-id="3daa9-250">Herunterladen von[https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)</span><span class="sxs-lookup"><span data-stu-id="3daa9-250">Download from [https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)</span></span>
    3. <span data-ttu-id="3daa9-251">Stellen Sie sicher, dass Skype for Business Server 2015 Dienste auf dem Front-End-Server angehalten wurden.</span><span class="sxs-lookup"><span data-stu-id="3daa9-251">Ensure Skype for Business Server 2015 services are stopped on the Front End server.</span></span> 
        - <span data-ttu-id="3daa9-252">Ex (Standard Edition):```Stop-CsWindowsServices```</span><span class="sxs-lookup"><span data-stu-id="3daa9-252">Ex (Standard Edition): ```Stop-CsWindowsServices```</span></span>
        - <span data-ttu-id="3daa9-253">Ex (Enterprise Edition):```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="3daa9-253">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    4. <span data-ttu-id="3daa9-254">Beenden der Ausführung von SQL-Instanzen</span><span class="sxs-lookup"><span data-stu-id="3daa9-254">Stop the SQL instances installed from running</span></span> 
        - <span data-ttu-id="3daa9-255">Ex```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="3daa9-255">Ex: ```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```</span></span>
        - <span data-ttu-id="3daa9-256">Ex```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="3daa9-256">Ex: ```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```</span></span>
        - <span data-ttu-id="3daa9-257">Ex (nur Standard Edition):```Get-Service 'MSSQL$RTC' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="3daa9-257">Ex (Standard Edition Only): ```Get-Service 'MSSQL$RTC' | Stop-Service```</span></span>
    5. <span data-ttu-id="3daa9-258">Installieren Sie das Update.</span><span class="sxs-lookup"><span data-stu-id="3daa9-258">Install the update.</span></span>
5. <span data-ttu-id="3daa9-259">Aktualisieren Sie den ODBC-Treiber 11 für SQL Server, um die Unterstützung für TLS 1,2 (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)) einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="3daa9-259">Update ODBC Driver 11 for SQL Server to include support for TLS 1.2 (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)).</span></span>
    1. <span data-ttu-id="3daa9-260">Laden Sie [ODBC Driver 11 für SQL Server-Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434)herunter.</span><span class="sxs-lookup"><span data-stu-id="3daa9-260">Download [ODBC Driver 11 for SQL Server - Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434).</span></span>
    2. <span data-ttu-id="3daa9-261">Stellen Sie sicher, dass Skype for Business Server 2015 Dienste auf dem Front-End-Server angehalten werden.</span><span class="sxs-lookup"><span data-stu-id="3daa9-261">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
        - <span data-ttu-id="3daa9-262">Beispiel (Standard Edition):```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="3daa9-262">Example (Standard Edition): ```Stop-CsWindowsService```</span></span>
        - <span data-ttu-id="3daa9-263">Beispiel (Enterprise Edition):```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="3daa9-263">Example (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    3. <span data-ttu-id="3daa9-264">Installieren Sie das Update.</span><span class="sxs-lookup"><span data-stu-id="3daa9-264">Install the update.</span></span>
6. <span data-ttu-id="3daa9-265">Bereitstellen von erforderlichen Registrierungsschlüsseln</span><span class="sxs-lookup"><span data-stu-id="3daa9-265">Deploy prerequisite registry keys.</span></span>

### <a name="pre-requisite-registry-keys"></a><span data-ttu-id="3daa9-266">Voraussetzungen für Registrierungsschlüssel</span><span class="sxs-lookup"><span data-stu-id="3daa9-266">Pre-requisite registry keys</span></span>

<span data-ttu-id="3daa9-267">Kopieren/fügen Sie den folgenden Test in Notepad ein, und benennen Sie TLSPreReq. reg oder einen Namen Ihrer Wahl um, und importieren Sie dann:</span><span class="sxs-lookup"><span data-stu-id="3daa9-267">Copy/paste the following test into Notepad and rename TLSPreReq.reg or a name of your choice, then import:</span></span>

```console
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

<span data-ttu-id="3daa9-268">Für SQL-Back-Ends für Enterprise Edition-Pools sollten Voraussetzungen und TLS-Deaktivierung wie alle SQL-oder BS-Updates behandelt werden; Siehe:[https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span><span class="sxs-lookup"><span data-stu-id="3daa9-268">For SQL back ends for Enterprise Edition Pools, prerequisites and TLS disable should be treated as any SQL or OS updates would; refer to: [https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span></span>

<span data-ttu-id="3daa9-269">Zwar können sowohl die erforderlichen Schritte für die erforderliche Anwendung als auch die TLS-Deaktivierung kombiniert werden, es wird jedoch dringend empfohlen, alle Voraussetzungen anzuwenden, bevor Sie mit dem Deaktivieren von TLS 1,0 und 1,1 auf Betriebssystemebene fortfahren.</span><span class="sxs-lookup"><span data-stu-id="3daa9-269">While both the prerequisite application and TLS disabling steps can be combined, we strongly recommend all prerequisites be applied before proceeding with disabling of TLS 1.0 and 1.1 at the operating system level.</span></span> <span data-ttu-id="3daa9-270">Die bewährte Methode besteht darin, die Umgebung vorzubereiten, indem Sie alle Voraussetzungen bereitstellen, überprüfen, ob die Arbeitslasten ordnungsgemäß und wie erwartet funktionieren, und dann zu einem späteren Zeitpunkt mit der TLS 1.0/1.1-Deaktivierung fortfahren.</span><span class="sxs-lookup"><span data-stu-id="3daa9-270">The best practice approach would be to prepare the environment by deploying all prerequisites, validating that workloads all function correctly and as expected, and then proceeding with TLS 1.0/1.1 disable at a later time.</span></span>

### <a name="disable-tls-10-and-11-via-registry-import"></a><span data-ttu-id="3daa9-271">Deaktivieren von TLS 1,0 und 1,1 über den Registrierungs Import</span><span class="sxs-lookup"><span data-stu-id="3daa9-271">Disable TLS 1.0 and 1.1 via registry import</span></span>

<span data-ttu-id="3daa9-272">Bevor Sie mit den nächsten Schritten fortfahren, *Stellen Sie sicher, dass Sie alle Voraussetzungen erfüllt und Skype for Business Server aktualisiert haben*.</span><span class="sxs-lookup"><span data-stu-id="3daa9-272">Before you proceed with the next steps, *make sure you have completed all prerequisites and updated Skype for Business Servers*.</span></span>

<span data-ttu-id="3daa9-273">Kopieren Sie den folgenden Text in eine Notepad-Datei, und benennen Sie Sie **TLSDisable. reg**um:</span><span class="sxs-lookup"><span data-stu-id="3daa9-273">Copy the following text into a Notepad file and rename it **TLSDisable.reg**:</span></span>

```console
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

<span data-ttu-id="3daa9-274">Importieren Sie die reg-Datei auf jedem Server, auf dem TLS 1,0 und 1,1 deaktiviert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="3daa9-274">Import the .reg file on each server you wish to disable TLS 1.0 and 1.1.</span></span> <span data-ttu-id="3daa9-275">Starten Sie den Server neu.</span><span class="sxs-lookup"><span data-stu-id="3daa9-275">Reboot the server.</span></span> <span data-ttu-id="3daa9-276">Wenn die Dienste wieder online sind, navigieren Sie zum nächsten Server.</span><span class="sxs-lookup"><span data-stu-id="3daa9-276">Once the services have come back online, move to the next server.</span></span> <span data-ttu-id="3daa9-277">Der Ansatz für Enterprise Edition-Pools ist die gleiche, die Sie für jedes Betriebssystemupdate ausführen würden.</span><span class="sxs-lookup"><span data-stu-id="3daa9-277">The approach for Enterprise Edition Pools is the same you would take for any OS update.</span></span>

<span data-ttu-id="3daa9-278">Sie haben vielleicht bemerkt, dass wir mehr tun, als nur TLS 1,0 und 1,1 hier zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="3daa9-278">You may have noticed we are doing more than just disabling TLS 1.0 and 1.1 here.</span></span> <span data-ttu-id="3daa9-279">Wir unterstützen die erneute Reihenfolge von Cipher Suite (siehe oben) und die Deaktivierung einiger älterer schwacher Chiffren.</span><span class="sxs-lookup"><span data-stu-id="3daa9-279">We are supporting Cipher Suite re-order (as shown above) and the disabling of some older weak ciphers.</span></span> <span data-ttu-id="3daa9-280">Dies ist das erste Mal, dass wir diese Änderungen an SChannel und der Crypto-API auf Skype for Business Server offiziell unterstützt haben, und es ist wichtig zu beachten, dass diese Änderungen die einzigen sind, die wir unterstützen und zu diesem Zeitpunkt getestet haben.</span><span class="sxs-lookup"><span data-stu-id="3daa9-280">This is the first time we have officially supported these changes to SCHANNEL and Crypto API on Skype for Business Server, and it is important to note that these changes are the only ones we support and have tested at this time.</span></span> <span data-ttu-id="3daa9-281">Wir können in Zukunft zusätzliche Konfigurationen in Frage stellen, aber jetzt sollten Sie die Registrierungs Importdatei nicht in ihrer Implementierung ändern.</span><span class="sxs-lookup"><span data-stu-id="3daa9-281">We may consider additional configurations in the future, but for now, please do not modify the registry import file in your implementation.</span></span>

### <a name="validate-that-workloads-are-functioning-as-expected"></a><span data-ttu-id="3daa9-282">Überprüfen, ob Arbeitsauslastungen wie erwartet funktionieren</span><span class="sxs-lookup"><span data-stu-id="3daa9-282">Validate that workloads are functioning as expected</span></span>

<span data-ttu-id="3daa9-283">Nachdem TLS 1,0 und 1,1 in Ihrer Umgebung deaktiviert wurden, stellen Sie sicher, dass alle Ihre Haupt Arbeitslasten wie erwartet funktionieren, beispielsweise Chat & Anwesenheit, P2P-Anrufe, Enterprise-VoIP usw.</span><span class="sxs-lookup"><span data-stu-id="3daa9-283">Once TLS 1.0 and 1.1 have been disabled in your environment, ensure that all your main workloads are functioning as expected, such as IM & Presence, P2P calls, Enterprise Voice, etc.</span></span>

<span data-ttu-id="3daa9-284">**Überprüfen, ob nur TLS 1,2 verwendet wird**</span><span class="sxs-lookup"><span data-stu-id="3daa9-284">**Validate only TLS 1.2 is being used**</span></span>

<span data-ttu-id="3daa9-285">Lassen Sie Ihr Sicherheits Team eine neue Überprüfung Skype for Business Datenverkehrs durchführen, um sicherzustellen, dass die älteren Protokolle TLS 1,0 und 1,1 nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3daa9-285">Have your Security Team perform a new audit of Skype for Business traffic to ensure that the older protocols TLS 1.0 and 1.1 are no longer in use.</span></span>

<span data-ttu-id="3daa9-286">Alternativ können Sie Internet Explorer verwenden, um TLS-Verbindungen mit Webdiensten von Skype for Business Server 2015 zu testen, nachdem TLS 1,0 und TLS 1,1 deaktiviert wurden.</span><span class="sxs-lookup"><span data-stu-id="3daa9-286">Alternatively, you can use Internet Explorer to test TLS connections to web services from Skype for Business Server 2015 after TLS 1.0 and TLS 1.1 have been disabled.</span></span>

1. <span data-ttu-id="3daa9-287">Starten Sie Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="3daa9-287">Launch Internet Explorer.</span></span>
2. <span data-ttu-id="3daa9-288">Wählen Sie **Extras** > **Internet Optionen**aus.</span><span class="sxs-lookup"><span data-stu-id="3daa9-288">Select **Tools** > **Internet Options**.</span></span>
3. <span data-ttu-id="3daa9-289">Wählen Sie die Registerkarte **erweitert** aus.</span><span class="sxs-lookup"><span data-stu-id="3daa9-289">Select the **Advanced** tab.</span></span>
4. <span data-ttu-id="3daa9-290">Scrollen Sie unter **Einstellungen**nach unten.</span><span class="sxs-lookup"><span data-stu-id="3daa9-290">Under **Settings**, scroll to the bottom.</span></span>
5. <span data-ttu-id="3daa9-291">Stellen Sie sicher, dass TLS 1,0, TLS 1,1 und TLS 1,2 aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="3daa9-291">Verify that TLS 1.0, TLS 1.1, and TLS 1.2 are enabled.</span></span>
6. <span data-ttu-id="3daa9-292">Durchsuchen Sie die interne Webdienst-URL Ihres SFB 2015-Pools (sollte erfolgreich eine Verbindung herstellen).</span><span class="sxs-lookup"><span data-stu-id="3daa9-292">Browse the Internal Web Service URL of your SfB 2015 pool (should connect successfully).</span></span>
7. <span data-ttu-id="3daa9-293">Wechseln Sie zurück in Internet Explorer, und deaktivieren Sie die Option nur **TLS 1,2 verwenden** .</span><span class="sxs-lookup"><span data-stu-id="3daa9-293">Go back into Internet Explorer and disable the option to **Use TLS 1.2** only.</span></span>
8. <span data-ttu-id="3daa9-294">Durchsuchen Sie die interne Webdienst-URL Ihres SFB 2015-Pools erneut (sollte keine Verbindung hergestellt werden).</span><span class="sxs-lookup"><span data-stu-id="3daa9-294">Browse the Internal Web Service URL of your SfB 2015 pool again (should fail to connect).</span></span>

![Internet Optionen](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a><span data-ttu-id="3daa9-296">Erweiterte Bereitstellungsszenarien</span><span class="sxs-lookup"><span data-stu-id="3daa9-296">Advanced deployment scenarios</span></span>

<span data-ttu-id="3daa9-297">Da für die Unterstützung von TLS 1,2 in Skype for Business ser 2015 einige erforderliche Abhängigkeiten erforderlich sind, kann die Installation von RTM-Medien auf jedem System fehlschlagen, auf dem TLS 1,0 und 1,1 deaktiviert wurden.</span><span class="sxs-lookup"><span data-stu-id="3daa9-297">Because some dependency prerequisites are required to support TLS 1.2 in Skype for Business Ser 2015, installing from RTM media will fail on any system where TLS 1.0 and 1.1 have been disabled.</span></span>

<span data-ttu-id="3daa9-298">**Bereitstellen neuer Standard Edition-Server oder Enterprise Edition-Pools, wenn TLS 1,0 und 1,1 in Ihrer Umgebung deaktiviert wurden.**</span><span class="sxs-lookup"><span data-stu-id="3daa9-298">**Deploying New Standard Edition Servers or Enterprise Edition Pools once TLS 1.0 and 1.1 have been disabled in your environment.**</span></span>

<span data-ttu-id="3daa9-299">**Option 1:** Verwenden Sie [SmartSetup](../../deploy/install/install-skype-for-business-server.md).</span><span class="sxs-lookup"><span data-stu-id="3daa9-299">**Option 1:** Use [SmartSetup](../../deploy/install/install-skype-for-business-server.md).</span></span> <span data-ttu-id="3daa9-300">Beachten Sie, dass wir SmartSetup aktualisieren, um die aktualisierten SQL-Binärdateien in einer zukünftigen Cu aufzunehmen, und diesen Artikel in Zukunft aktualisieren werden.</span><span class="sxs-lookup"><span data-stu-id="3daa9-300">Note that we are updating SmartSetup to accommodate the updated SQL binaries in a future CU, and will update this article in the future.</span></span>

<span data-ttu-id="3daa9-301">**Option 2:** Lokale SQL-Instanzen vorab installieren (RTCLOCAL und LYNCLOCAL)</span><span class="sxs-lookup"><span data-stu-id="3daa9-301">**Option 2:** Pre-install local SQL instances (RTCLOCAL and LYNCLOCAL)</span></span>

1. <span data-ttu-id="3daa9-302">Laden Sie SQL Express 2014 SP2 (SQLEXPR_x64. exe) in den lokalen Ordner auf FE herunter, und kopieren Sie es.</span><span class="sxs-lookup"><span data-stu-id="3daa9-302">Download and copy SQL Express 2014 SP2 (SQLEXPR_x64.exe) to local folder on FE.</span></span> <span data-ttu-id="3daa9-303">Angenommen, der Ordnerpfad <SQL_FOLDER_PATH>.</span><span class="sxs-lookup"><span data-stu-id="3daa9-303">Let’s say folder path <SQL_FOLDER_PATH>.</span></span>
2. <span data-ttu-id="3daa9-304">Starten Sie PowerShell oder Eingabeaufforderung, und navigieren Sie zu <SQL_FOLDER_PATH>.</span><span class="sxs-lookup"><span data-stu-id="3daa9-304">Launch PowerShell or Command Prompt and navigate to <SQL_FOLDER_PATH>.</span></span>
3. <span data-ttu-id="3daa9-305">Erstellen Sie die RTCLOCAL-SQL-Instanz, indem Sie den folgenden Befehl ausführen.</span><span class="sxs-lookup"><span data-stu-id="3daa9-305">Create the RTCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="3daa9-306">Warten Sie, bis SQLEXPR_x64. exe abgeschlossen ist, bevor Sie fortfahren:</span><span class="sxs-lookup"><span data-stu-id="3daa9-306">Wait until SQLEXPR_x64.exe finishes before proceeding:</span></span>

    <span data-ttu-id="3daa9-307">SQLEXPR_x64. exe/q/IACCEPTSQLSERVERLICENSETERMS/UPDATEENABLED = 0/HIDECONSOLE/Action = install/Features = SQLEngine, Tools/instanceName = RTCLOCAL/TCPENABLED = 1/SQLSVCACCOUNT = "NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "VORDEFINIERT\Administratoren"/BROWSERSVCSTARTUPTYPE = "Automatic"/AGTSVCACCOUNT = "NTAUTHORITY\NetworkService"/SQLSVCSTARTUPTYPE = automati</span><span class="sxs-lookup"><span data-stu-id="3daa9-307">SQLEXPR_x64.exe  /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=RTCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automati</span></span>
1. <span data-ttu-id="3daa9-308">Erstellen Sie die LYNCLOCAL-SQL-Instanz, indem Sie den folgenden Befehl ausführen.</span><span class="sxs-lookup"><span data-stu-id="3daa9-308">Create the LYNCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="3daa9-309">Warten Sie, bis SQLEXPR_x64. exe abgeschlossen ist, bevor Sie mit dem nächsten Schritt fortfahren:</span><span class="sxs-lookup"><span data-stu-id="3daa9-309">Wait until SQLEXPR_x64.exe finishes before proceeding to the next step:</span></span>

    <span data-ttu-id="3daa9-310">SQLEXPR_x64. exe/q/IACCEPTSQLSERVERLICENSETERMS/UPDATEENABLED = 0/HIDECONSOLE/Action = install/Features = SQLEngine, Tools/instanceName = LYNCLOCAL/TCPENABLED = 1/SQLSVCACCOUNT = "NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "VORDEFINIERT\Administratoren"/BROWSERSVCSTARTUPTYPE = "Automatic"/AGTSVCACCOUNT = "NTAUTHORITY\NetworkService"/SQLSVCSTARTUPTYPE = Automatic</span><span class="sxs-lookup"><span data-stu-id="3daa9-310">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=LYNCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automatic</span></span>
1. <span data-ttu-id="3daa9-311">Führen Sie Skype for Business Server 2015 RTM-Setup aus.</span><span class="sxs-lookup"><span data-stu-id="3daa9-311">Run Skype for Business Server 2015 RTM setup.</span></span>
2. <span data-ttu-id="3daa9-312">Befolgen Sie die restlichen Schritte im Abschnitt Voraussetzungen weiter oben.</span><span class="sxs-lookup"><span data-stu-id="3daa9-312">Follow the remaining steps from the prerequisites section above.</span></span>

<span data-ttu-id="3daa9-313">**Option 3:** Sie können Binärdateien auch manuell in einem lokalen Installationsmedien Verzeichnis wie folgt ersetzen:</span><span class="sxs-lookup"><span data-stu-id="3daa9-313">**Option 3:** You may also manually replace binaries in a local installation media directory as follows:</span></span>

1. [<span data-ttu-id="3daa9-314">Installieren der Voraussetzungen für Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="3daa9-314">Install prerequisites for Skype for Business Server</span></span>](../../deploy/install/install-prerequisites.md)  
2. <span data-ttu-id="3daa9-315">Installieren von .NET 4,7:</span><span class="sxs-lookup"><span data-stu-id="3daa9-315">Install .NET 4.7:</span></span> 
      - <span data-ttu-id="3daa9-316">**Hinweis:** Wir haben zunächst die Unterstützung für .NET 4,7 in Skype for Business Server 2015 CU5 (6.0.9319.281) eingeführt.</span><span class="sxs-lookup"><span data-stu-id="3daa9-316">**Note:** We first introduced support for .NET 4.7 in Skype for Business Server 2015 CU5 (6.0.9319.281).</span></span> <span data-ttu-id="3daa9-317">In den nachfolgenden Schritten werden daher die wichtigsten Komponenten vor der Hauptinstallation aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="3daa9-317">Therefore, in later steps below we will be updating Core Components prior to the main install.</span></span>
      - <span data-ttu-id="3daa9-318">Download: https://www.microsoft.com/download/details.aspx?id=55167.</span><span class="sxs-lookup"><span data-stu-id="3daa9-318">Download: https://www.microsoft.com/download/details.aspx?id=55167.</span></span> 
      - <span data-ttu-id="3daa9-319">Referenz: [Software, die vor einer Skype for Business Server 2015-Bereitstellung installiert werden sollte](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span><span class="sxs-lookup"><span data-stu-id="3daa9-319">Reference: [Software that should be installed before a Skype for Business Server 2015 deployment](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span></span>
3. <span data-ttu-id="3daa9-320">Kopieren von ISO-Dateien/Ordnern:</span><span class="sxs-lookup"><span data-stu-id="3daa9-320">Copy ISO Files/Folders:</span></span> 
    - <span data-ttu-id="3daa9-321">Wenn die Skype for Business Server 2015 ISO angefügt ist, öffnen Sie das Stammverzeichnis des Laufwerks, dem es angefügt ist (ex\) : D: im Datei-Explorer.</span><span class="sxs-lookup"><span data-stu-id="3daa9-321">With the Skype for Business Server 2015 ISO attached, open the root directory of the drive it is attached as (Ex: D:\) in File Explorer.</span></span>
    - <span data-ttu-id="3daa9-322">Kopieren Sie alle Ordner und Dateien in einen Ordner auf einem lokalen Datenträger (z. b.: C:\SkypeForBusiness2015ISO).</span><span class="sxs-lookup"><span data-stu-id="3daa9-322">Copy all folders and files to a folder on a local disk (Ex: C:\SkypeForBusiness2015ISO).</span></span>
    - <span data-ttu-id="3daa9-323">**Hinweis:** Vor dem Installieren von Komponenten müssen einige Dateien für die Unterstützung von TLS 1,2 aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="3daa9-323">**Note:** Prior to installing components, some files will need to be updated for support of TLS 1.2.</span></span>
4. <span data-ttu-id="3daa9-324">Ersetzen Sie MSI/exe-Pakete:</span><span class="sxs-lookup"><span data-stu-id="3daa9-324">Replace MSI/EXE Packages:</span></span> 
    - <span data-ttu-id="3daa9-325">Ersetzen Sie die vorhandenen MSI-und exe-Pakete im Ordner/Setup/amd64/des Installationsmediums auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="3daa9-325">Replace the existing MSI and EXE packages in the /Setup/amd64/ folder of the installation media on the local machine.</span></span>
    - <span data-ttu-id="3daa9-326">SQL 2014 SP2 Express:https://www.microsoft.com/download/details.aspx?id=53167</span><span class="sxs-lookup"><span data-stu-id="3daa9-326">SQL 2014 SP2 Express: https://www.microsoft.com/download/details.aspx?id=53167</span></span> 
        - <span data-ttu-id="3daa9-327">Benennen Sie den SQLEXPR_x64 auf dem lokalen Computer um, und ersetzen Sie die vorhandene Datei im Setup/amd64/Ordner des Installationsmediums.</span><span class="sxs-lookup"><span data-stu-id="3daa9-327">Rename to SQLEXPR_x64 on the local machine, and replace the existing file in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="3daa9-328">SQL Native Client:https://www.microsoft.com/download/details.aspx?id=50402</span><span class="sxs-lookup"><span data-stu-id="3daa9-328">SQL Native Client: https://www.microsoft.com/download/details.aspx?id=50402</span></span> 
        - <span data-ttu-id="3daa9-329">**Hinweis:** Benennen Sie diese bei Bedarf in sqlncli. msi um, und ersetzen Sie dann die vorhandene Datei, die im Setup/amd64/Ordner des Installationsmediums vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="3daa9-329">**Note:** Rename this if necessary to sqlncli.msi, and then replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="3daa9-330">SQL-Verwaltungsobjekte:https://www.microsoft.com/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="3daa9-330">SQL Management Objects: https://www.microsoft.com/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="3daa9-331">**Hinweis:** Das Feature Pack enthält eine Vielzahl von Elementen, die heruntergeladen werden können.</span><span class="sxs-lookup"><span data-stu-id="3daa9-331">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="3daa9-332">Wählen Sie diese Option aus, um nur SharedManagementObjects. msi herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="3daa9-332">Select to download SharedManagementObjects.msi only.</span></span>
        - <span data-ttu-id="3daa9-333">**Hinweis:** Ersetzen Sie die vorhandene Datei, die im Setup/amd64/Ordner des Installationsmediums vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="3daa9-333">**Note:** Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="3daa9-334">SQL CLR-Typen:https://www.microsoft.com/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="3daa9-334">SQL CLR Types: https://www.microsoft.com/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="3daa9-335">**Hinweis:** Das Feature Pack enthält eine Vielzahl von Elementen, die heruntergeladen werden können.</span><span class="sxs-lookup"><span data-stu-id="3daa9-335">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="3daa9-336">Auswählen, um nur CQLSysClrTypes. msi herunterzuladen</span><span class="sxs-lookup"><span data-stu-id="3daa9-336">Select to download CQLSysClrTypes.msi only</span></span>
        - <span data-ttu-id="3daa9-337">**Hinweis**: Ersetzen Sie die vorhandene Datei, die im Setup/amd64/Ordner des Installationsmediums vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="3daa9-337">**Note**: Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
5. <span data-ttu-id="3daa9-338">Installieren von Hauptkomponenten:</span><span class="sxs-lookup"><span data-stu-id="3daa9-338">Install Core Components:</span></span> 
    - <span data-ttu-id="3daa9-339">Führen Sie Setup. exe aus dem Setup/amd64/Ordner des Installationsmediums aus.</span><span class="sxs-lookup"><span data-stu-id="3daa9-339">Run Setup.exe from the Setup/amd64/ folder of the installation media.</span></span> <span data-ttu-id="3daa9-340">Befolgen Sie die Anweisungen zum Installieren von Hauptkomponenten.</span><span class="sxs-lookup"><span data-stu-id="3daa9-340">Follow the instructions to install Core Components</span></span>
    - <span data-ttu-id="3daa9-341">Schließen Sie die Kernkomponenten.</span><span class="sxs-lookup"><span data-stu-id="3daa9-341">Close Core Components.</span></span>
6. <span data-ttu-id="3daa9-342">Aktualisieren der Kernkomponenten:</span><span class="sxs-lookup"><span data-stu-id="3daa9-342">Update Core Components:</span></span> 
    - <span data-ttu-id="3daa9-343">Laden Sie das Installationsprogramm für Skype for Business Updates herunter.</span><span class="sxs-lookup"><span data-stu-id="3daa9-343">Download the Skype for Business Update Installer.</span></span>
    - <span data-ttu-id="3daa9-344">Führen Sie das Installationsprogramm aus, um die Hauptkomponenten zu aktualisieren und die Leistungsindikatoren zu installieren.</span><span class="sxs-lookup"><span data-stu-id="3daa9-344">Run the installer to update Core Components and install the performance counters.</span></span>
    - <span data-ttu-id="3daa9-345">**Hinweis:** Ab der Veröffentlichung von CU6HF2 wird die automatische Update Funktion derzeit nur bis zu CU6 installieren.</span><span class="sxs-lookup"><span data-stu-id="3daa9-345">**Note:** As of the release of CU6HF2, the auto-update feature currently only will install up to CU6.</span></span> <span data-ttu-id="3daa9-346">Daher muss der Updater separat ausgeführt werden, um die Hauptkomponenten auf 6.0.9319.516 zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="3daa9-346">Therefore, the updater must be run separately to update Core Components to 6.0.9319.516.</span></span>
    - <span data-ttu-id="3daa9-347">Referenzhttps://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015</span><span class="sxs-lookup"><span data-stu-id="3daa9-347">Reference: https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015</span></span>
7. <span data-ttu-id="3daa9-348">Installieren von Verwaltungs Tools (optional):</span><span class="sxs-lookup"><span data-stu-id="3daa9-348">Install Administrative Tools (Optional):</span></span> 
    - <span data-ttu-id="3daa9-349">Auf diese Weise werden die Microsoft SQL Server 2012 Native Client, SQL Server 2014 Management Objects (x64) und Microsoft System CLR-Typen für SQL Server 2014 (x64) unter Verwendung der aktualisierten Dateien installiert.</span><span class="sxs-lookup"><span data-stu-id="3daa9-349">This will install the Microsoft SQL Server 2012 Native Client, SQL Server 2014 Management Objects (x64), and Microsoft System CLR Types for SQL Server 2014 (x64) using the updated files.</span></span> <span data-ttu-id="3daa9-350">Darüber hinaus wird der Skype for Business Server 2015 Topologie-Generator und die Systemsteuerung auf dem lokalen Computer verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="3daa9-350">Additionally, the Skype for Business Server 2015 Topology Builder and Control Panel will be available on the local machine.</span></span>
8. <span data-ttu-id="3daa9-351">Installieren des lokalen Konfigurationsspeichers (Schritt 1):</span><span class="sxs-lookup"><span data-stu-id="3daa9-351">Install Local Configuration Store (Step 1):</span></span> 
     - <span data-ttu-id="3daa9-352">Öffnen Sie den Bereitstellungs-Assistenten, klicken Sie auf Installieren oder aktualisieren Sie Skype for Business Server System, und klicken Sie auf **Ausführen** unter Schritt 1: Installieren des lokalen Konfigurationsspeichers.</span><span class="sxs-lookup"><span data-stu-id="3daa9-352">Open the Deployment Wizard, click Install or Update Skype for Business Server System, and click on **Run** at Step 1: Install Local Configuration Store.</span></span>
     - <span data-ttu-id="3daa9-353">Klicken Sie im Dialogfeld **lokalen Konfigurationsspeicher installieren** auf **weiter** .</span><span class="sxs-lookup"><span data-stu-id="3daa9-353">Click **Next** in the **Install Local Configuration Store** dialog box.</span></span>
     <span data-ttu-id="3daa9-354">![Dialogfeld zum Installieren des lokalen Konfigurationsspeichers](../../media/local-configuration-store.png)</span><span class="sxs-lookup"><span data-stu-id="3daa9-354">![Install Local Configuration Store dialog box](../../media/local-configuration-store.png)</span></span>
     - <span data-ttu-id="3daa9-355">Überprüfen Sie die Ergebnisse, und stellen Sie sicher, dass der Aufgaben Status abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="3daa9-355">Review the results, and ensure that the Task Status is Completed.</span></span> <span data-ttu-id="3daa9-356">Überprüfen Sie die resultierende Protokolldatei, indem Sie auf **Protokoll anzeigen**klicken.</span><span class="sxs-lookup"><span data-stu-id="3daa9-356">Review the resulting log file by clicking **View Log**.</span></span>
     <span data-ttu-id="3daa9-357">![Vorgangsstatus wird als abgeschlossen angezeigt](../../media/local-configuration-task-completed.png)</span><span class="sxs-lookup"><span data-stu-id="3daa9-357">![Task status shows as Completed](../../media/local-configuration-task-completed.png)</span></span>
     - <span data-ttu-id="3daa9-358">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="3daa9-358">Click **Finish**.</span></span>
9. <span data-ttu-id="3daa9-359">Einrichten oder Entfernen von Skype for Business Server Komponenten (Schritt 2):</span><span class="sxs-lookup"><span data-stu-id="3daa9-359">Set up or remove Skype for Business Server Components (Step 2):</span></span>
    - <span data-ttu-id="3daa9-360">Öffnen Sie den Bereitstellungs-Assistenten, klicken Sie auf **Skype for Business Server System installieren oder aktualisieren**, und klicken Sie dann auf **Ausführen** von Schritt 2: Skype for Business Server Komponenten einrichten oder entfernen</span><span class="sxs-lookup"><span data-stu-id="3daa9-360">Open the Deployment Wizard, click **Install or Update Skype for Business Server System**, and click **Run** at Step 2: Set up or Remove Skype for Business Server Components</span></span>
    - <span data-ttu-id="3daa9-361">Klicken Sie im Dialogfeld Skype for Business Server Komponenten einrichten auf **weiter** .</span><span class="sxs-lookup"><span data-stu-id="3daa9-361">Click **Next** in the Set Up Skype for Business Server Components dialog box.</span></span>
    <span data-ttu-id="3daa9-362">![Das Fenster Skype for Business Server Komponenten einrichten](../../media/set-up-skype-for-business-server-components-window.png)</span><span class="sxs-lookup"><span data-stu-id="3daa9-362">![the Set Up Skype for Business Server Components window](../../media/set-up-skype-for-business-server-components-window.png)</span></span>
    - <span data-ttu-id="3daa9-363">Überprüfen Sie das Protokoll mit View Log, und überprüfen Sie, ob das Setup ohne Probleme abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="3daa9-363">Review the log using View Log, and validate that setup completed without issues.</span></span> 
    - <span data-ttu-id="3daa9-364">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="3daa9-364">Click **Finish**.</span></span>
10. <span data-ttu-id="3daa9-365">Fahren Sie bei Bedarf mit zusätzlicher Installation und Konfiguration fort (Sie können zu diesem Zeitpunkt die normalen Installationsverfahren fortsetzen).</span><span class="sxs-lookup"><span data-stu-id="3daa9-365">Proceed with additional installation and configuration as required (you can resume normal installation procedures at this point).</span></span>
