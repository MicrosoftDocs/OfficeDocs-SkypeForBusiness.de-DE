---
title: Deaktivieren von TLS 1.0/1.1 in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Zusammenfassung: Vorbereiten und Implementieren der Deaktivierung von TLS 1,0 und 1,1 in Ihrer Umgebung.'
ms.openlocfilehash: 3f12642a5abf944ddbcddfdca0745998a8b634ec
ms.sourcegitcommit: a49caec01ff724475d6670b303d851ddd8266c2c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2019
ms.locfileid: "34275241"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a><span data-ttu-id="59800-103">Deaktivieren von TLS 1.0/1.1 in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="59800-103">Disable TLS 1.0/1.1 in Skype for Business Server 2015</span></span>

<span data-ttu-id="59800-104">In diesem Artikel werden die erforderlichen Anleitungen bereitgestellt, mit denen Sie die Deaktivierung von TLS 1,0 und 1,1 in ihren Umgebungen vorbereiten und implementieren können.</span><span class="sxs-lookup"><span data-stu-id="59800-104">The purpose of this article is to provide the necessary guidance for you to prepare for and implement disabling TLS 1.0 and 1.1 in your environments.</span></span> <span data-ttu-id="59800-105">Dieser Vorgang erfordert eine umfassende Planung und Vorbereitung.</span><span class="sxs-lookup"><span data-stu-id="59800-105">This process requires extensive planning and preparation.</span></span> <span data-ttu-id="59800-106">Bitte überprüfen Sie sorgfältig alle Informationen in diesem Artikel, während Sie Ihren Plan zur Deaktivierung von TLS 1,0 und 1,1 für Ihre Organisation festlegen.</span><span class="sxs-lookup"><span data-stu-id="59800-106">Please carefully review all of the information in this article as you make your plan to disable TLS 1.0 and 1.1 for your organization.</span></span> <span data-ttu-id="59800-107">Beachten Sie, dass es viele externe Abhängigkeiten und Verbindungsbedingungen gibt, die durch das Deaktivieren von TLS 1.0/1.1 beeinträchtigt werden können, daher ist eine umfassende Planung und Prüfung gewährleistet.</span><span class="sxs-lookup"><span data-stu-id="59800-107">Note that there are many external dependencies and connectivity conditions that could be impacted by disabling TLS 1.0/1.1, so extensive planning and testing is warranted.</span></span>

## <a name="in-this-article"></a><span data-ttu-id="59800-108">In diesem Artikel</span><span class="sxs-lookup"><span data-stu-id="59800-108">In this article</span></span>

- [<span data-ttu-id="59800-109">Hintergrund und Bereich</span><span class="sxs-lookup"><span data-stu-id="59800-109">Background and scope</span></span>](#background)
- [<span data-ttu-id="59800-110">Voraussetzungen und Prozesse</span><span class="sxs-lookup"><span data-stu-id="59800-110">Prerequisites and process</span></span>](#prerequisites-and-process)
- [<span data-ttu-id="59800-111">Erweiterte Bereitstellungsszenarien</span><span class="sxs-lookup"><span data-stu-id="59800-111">Advanced deployment scenarios</span></span>](#advanced-deployment-scenarios)

## <a name="background"></a><span data-ttu-id="59800-112">Hintergrund</span><span class="sxs-lookup"><span data-stu-id="59800-112">Background</span></span>

<span data-ttu-id="59800-113">Die primären Treiber für die Bereitstellung von TLS 1,0 und 1,1 für die Unterstützung von Skype for Business Server lokal sind die Standards für die Datenverarbeitung in der Zahlungskartenbranche (PCI) Security Standards Council und Federal Information Processing Standards.</span><span class="sxs-lookup"><span data-stu-id="59800-113">The primary drivers for providing TLS 1.0 and 1.1 disable support for Skype for Business Server On-Premises are Payment Card Industry (PCI) Security Standards Council and Federal Information Processing Standards requirements.</span></span> <span data-ttu-id="59800-114">Weitere Informationen zu PCI-Anforderungen finden Sie [hier](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).</span><span class="sxs-lookup"><span data-stu-id="59800-114">More information for PCI requirements can be found [here](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).</span></span>  <span data-ttu-id="59800-115">Microsoft kann keine Anleitungen dazu liefern, ob Ihre Organisation diese oder andere Anforderungen erfüllen muss.</span><span class="sxs-lookup"><span data-stu-id="59800-115">Microsoft cannot provide guidance on whether or not your organization is required to adhere to these or other requirements.</span></span> <span data-ttu-id="59800-116">Sie müssen feststellen, ob es für Sie erforderlich ist, TLS 1,0 und/oder 1,1 in ihren Umgebungen zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="59800-116">You must determine if it is required for you to disable TLS 1.0 and/or 1.1 in your environments.</span></span>

<span data-ttu-id="59800-117">Microsoft hat [hier](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)ein Whitepaper zu TLS erstellt, und wir empfehlen auch die Hintergrund Lektüre, die in diesem [Exchange-Blog](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="59800-117">Microsoft has produced a white paper on TLS available [here](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/), and we also recommend the background reading available in this [Exchange blog](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).</span></span>

## <a name="supportability-scope"></a><span data-ttu-id="59800-118">Unterstützungsbereich</span><span class="sxs-lookup"><span data-stu-id="59800-118">Supportability Scope</span></span>

<span data-ttu-id="59800-119">Der *Bereich* bezieht sich auf Unterstützungs Begrenzungen.</span><span class="sxs-lookup"><span data-stu-id="59800-119">*Scope* refers to supportability boundaries.</span></span> <span data-ttu-id="59800-120">Für Skype for Business Server lokal *im Bereich* bedeutet, dass wir die Deaktivierung von TLS 1,0 und 1,1 für die aufgelisteten Produktversionen vollständig unterstützen und getestet haben.</span><span class="sxs-lookup"><span data-stu-id="59800-120">For Skype for Business Server On-Premises, *in scope* means we fully support and have tested disabling of TLS 1.0 and 1.1 for the listed product versions.</span></span> <span data-ttu-id="59800-121">*Derzeit untersucht wird* , bedeutet genau dies; Wir untersuchen aktiv, wie diese Produkte in den Anwendungsbereich der TLS-Deaktivierung gebracht werden.</span><span class="sxs-lookup"><span data-stu-id="59800-121">*Currently being investigated* means just that; we are actively investigating bringing these products into scope for TLS disable support.</span></span> <span data-ttu-id="59800-122">*Außerhalb des gültigen Bereichs* bedeutet, dass diese Produktversionen die Deaktivierung von TLS 1,0 oder 1,1 nicht unterstützen und mit bekannten Ausnahmen nicht funktionieren.</span><span class="sxs-lookup"><span data-stu-id="59800-122">*Out of scope* means these product versions do not support disabling TLS 1.0 or 1.1 and will not work, with noted exceptions.</span></span>

### <a name="fully-tested-and-supported-servers"></a><span data-ttu-id="59800-123">Vollständig getestete und unterstützte Server</span><span class="sxs-lookup"><span data-stu-id="59800-123">Fully tested and supported servers</span></span>

- <span data-ttu-id="59800-124">Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="59800-124">Skype for Business Server 2019</span></span>
- <span data-ttu-id="59800-125">Skype for Business Server 2015 CU6 HF2 6.0.9319.516 ([März 2018 Update](https://support.microsoft.com/en-us/help/4086059/march-2018-cumulative-update-6-0-9319-516-for-skype-for-business)) und höher:</span><span class="sxs-lookup"><span data-stu-id="59800-125">Skype for Business Server 2015 CU6 HF2 6.0.9319.516 ([March 2018 update](https://support.microsoft.com/en-us/help/4086059/march-2018-cumulative-update-6-0-9319-516-for-skype-for-business)) and higher on:</span></span> 
    - <span data-ttu-id="59800-126">Windows Server 2012 (mit KB 3140245 oder Ersetzen von Update), 2012 R2 oder 2016</span><span class="sxs-lookup"><span data-stu-id="59800-126">Windows Server 2012 (with KB 3140245 or superseding update), 2012 R2 or 2016</span></span>
- <span data-ttu-id="59800-127">In-Place-Upgrade von Skype for Business Server 2015, mit CU6 HF2 und höher</span><span class="sxs-lookup"><span data-stu-id="59800-127">In-place Upgraded Skype for Business Server 2015, with CU6 HF2 and higher on</span></span> 
    - <span data-ttu-id="59800-128">Windows Server 2008 R2, 2012 (mit KB [3140245](https://support.microsoft.com/en-us/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) oder Ersetzen von Update) oder 2012 R2</span><span class="sxs-lookup"><span data-stu-id="59800-128">Windows Server 2008 R2, 2012 (with KB [3140245](https://support.microsoft.com/en-us/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), or 2012 R2</span></span>
- <span data-ttu-id="59800-129">Exchange-Konnektivität und Outlook Web App mit Exchange Server 2010 SP3 RU19 oder höher, Anleitung [hier](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span><span class="sxs-lookup"><span data-stu-id="59800-129">Exchange Connectivity and Outlook Web App with Exchange Server 2010 SP3 RU19 or higher, guidance [here](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span></span>
- <span data-ttu-id="59800-130">Überlebensfähige Branch Appliance (SBA) mit Skype for Business Server 2015 CU6 HF2 oder höher (bestätigen Sie bei Ihrem Anbieter, dass Sie die entsprechenden Updates verpackt haben und für Ihre Appliance zur Verfügung gestellt wurden)</span><span class="sxs-lookup"><span data-stu-id="59800-130">Survivable Branch Appliance (SBA) with Skype for Business Server 2015 CU6 HF2 or higher (confirm with your vendor that they packaged the appropiate updates and have been made available for your appliance)</span></span>
- <span data-ttu-id="59800-131">Survivor Branch Server (SBS) mit Skype for Business Server 2015 CU6 HF2 oder höher</span><span class="sxs-lookup"><span data-stu-id="59800-131">Survivable Branch Server (SBS) with Skype for Business Server 2015 CU6 HF2 or higher</span></span>
- <span data-ttu-id="59800-132">Nur lync Server 2013- **Edge-Rolle**, das liegt daran, dass die Edge-Rolle keine Abhängigkeit von Windows Fabric 1,0 aufweist.</span><span class="sxs-lookup"><span data-stu-id="59800-132">Lync Server 2013 **Edge Role Only**, this is because Edge role does not have a dependency on Windows Fabric 1.0.</span></span>


### <a name="fully-tested-and-supported-clients"></a><span data-ttu-id="59800-133">Vollständig getestete und unterstützte Clients</span><span class="sxs-lookup"><span data-stu-id="59800-133">Fully tested and supported clients</span></span>

- <span data-ttu-id="59800-134">Lync 2013 (Skype for Business)-Desktop Client, MSI und C2R, einschließlich grundlegender [15.0.5023.1000 und höher](https://support.microsoft.com/en-us/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span><span class="sxs-lookup"><span data-stu-id="59800-134">Lync 2013 (Skype for Business) Desktop Client, MSI and C2R, including Basic [15.0.5023.1000 and higher](https://support.microsoft.com/en-us/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span></span>
- <span data-ttu-id="59800-135">Skype for Business 2016-Desktop Client, MSI [16.0.4678.1000 und höher](https://support.microsoft.com/en-us/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), einschließlich Basic</span><span class="sxs-lookup"><span data-stu-id="59800-135">Skype for Business 2016 Desktop Client, MSI [16.0.4678.1000 and higher](https://support.microsoft.com/en-us/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), including Basic</span></span>
- <span data-ttu-id="59800-136">Für Skype for Business 2016-Click-to-Run sind die Updates vom [April 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) erforderlich:</span><span class="sxs-lookup"><span data-stu-id="59800-136">Skype for Business 2016 Click to Run Require the [April 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) Updates:</span></span> 
    - <span data-ttu-id="59800-137">Monatlich und halbjährlich ausgerichtet, 16\.0\.9126\.2152 und höher</span><span class="sxs-lookup"><span data-stu-id="59800-137">Monthly and Semi-Annual Targeted, 16\.0\.9126\.2152 and higher</span></span>
    - <span data-ttu-id="59800-138">Halbjährlicher und verzögerter Kanal, 16\.0\.8431\.2242 und höher</span><span class="sxs-lookup"><span data-stu-id="59800-138">Semi-Annual and Deferred Channel, 16\.0\.8431\.2242 and higher</span></span>
- <span data-ttu-id="59800-139">Skype for Business für Mac 16,15 und höher</span><span class="sxs-lookup"><span data-stu-id="59800-139">Skype for Business on Mac 16.15 and higher</span></span>
- <span data-ttu-id="59800-140">Skype for Business für IOS und Android 6,19 und höher</span><span class="sxs-lookup"><span data-stu-id="59800-140">Skype for Business for iOS and Android 6.19 and higher</span></span>
- <span data-ttu-id="59800-141">Skype Web App 2015 CU6 HF2 und höher (ausgeliefert mit Server)</span><span class="sxs-lookup"><span data-stu-id="59800-141">Skype Web App 2015 CU6 HF2 and higher (ships with Server)</span></span>

### <a name="currently-being-investigated"></a><span data-ttu-id="59800-142">Derzeit untersucht</span><span class="sxs-lookup"><span data-stu-id="59800-142">Currently being investigated</span></span>

#### <a name="devices"></a><span data-ttu-id="59800-143">Geräte</span><span class="sxs-lookup"><span data-stu-id="59800-143">Devices</span></span>

- <span data-ttu-id="59800-144">Lync Room System (aka</span><span class="sxs-lookup"><span data-stu-id="59800-144">Lync Room System (a.k.a.</span></span> <span data-ttu-id="59800-145">SRSv1)</span><span class="sxs-lookup"><span data-stu-id="59800-145">SRSv1)</span></span>
- <span data-ttu-id="59800-146">Microsoft Teams-Räume</span><span class="sxs-lookup"><span data-stu-id="59800-146">Microsoft Teams Rooms</span></span>
- <span data-ttu-id="59800-147">Surface Hub</span><span class="sxs-lookup"><span data-stu-id="59800-147">Surface Hub</span></span>
- <span data-ttu-id="59800-148">2015-basierte, überlebensfähige Branch Appliance (SBA) oder Survivable Branch Server (SBS)</span><span class="sxs-lookup"><span data-stu-id="59800-148">2015 based Survivable Branch Appliance (SBA) or Survivable Branch Server (SBS)</span></span>

#### <a name="other"></a><span data-ttu-id="59800-149">Andere</span><span class="sxs-lookup"><span data-stu-id="59800-149">Other</span></span>

- <span data-ttu-id="59800-150">Dashboard für die Anrufqualität (neue Installation nach TLS 1,0, 1,1 wurden deaktiviert, siehe unten) \*</span><span class="sxs-lookup"><span data-stu-id="59800-150">Call Quality Dashboard (new install after TLS 1.0, 1.1 have been disabled, see below)\*</span></span>
 
### <a name="out-of-scope"></a><span data-ttu-id="59800-151">Außerhalb des Bereichs</span><span class="sxs-lookup"><span data-stu-id="59800-151">Out of scope</span></span>

<span data-ttu-id="59800-152">Sofern nicht anders angegeben, sind die folgenden Produkte nicht im Bereich für die TLS 1.0/1.1-Unterstützung deaktiviert und funktionieren in einer Umgebung, in der TLS 1,0 und 1,1 deaktiviert wurden.</span><span class="sxs-lookup"><span data-stu-id="59800-152">Except where noted, the following products are not in scope for TLS 1.0/1.1 disable support and will not function in an environment where TLS 1.0 and 1.1 have been disabled.</span></span>  <span data-ttu-id="59800-153">Was dies bedeutet: Wenn Sie weiterhin Server oder Clients außerhalb des Geltungsbereichs verwenden, müssen Sie diese aktualisieren oder entfernen, wenn Sie TLS 1.0/1.1 an einer beliebigen Stelle in Ihrer lokalen Skype for Business Server-Bereitstellung deaktivieren müssen.</span><span class="sxs-lookup"><span data-stu-id="59800-153">What this means: if you still utilize out-of-scope servers or clients, you must update or remove these if you need to disable TLS 1.0/1.1 anywhere in your Skype for Business Server on-premises deployment.</span></span>

- <span data-ttu-id="59800-154">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="59800-154">Lync Server 2013</span></span>
- <span data-ttu-id="59800-155">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="59800-155">Lync Server 2010</span></span>
- <span data-ttu-id="59800-156">Windows Server 2008 und niedriger</span><span class="sxs-lookup"><span data-stu-id="59800-156">Windows Server 2008 and lower</span></span>
- <span data-ttu-id="59800-157">Lync für Mac 2011</span><span class="sxs-lookup"><span data-stu-id="59800-157">Lync for Mac 2011</span></span>
- <span data-ttu-id="59800-158">Lync 2013 für Handys – IOS, iPad, Android oder Windows Phone</span><span class="sxs-lookup"><span data-stu-id="59800-158">Lync 2013 for Mobile - iOS, iPad, Android or Windows Phone</span></span>
- <span data-ttu-id="59800-159">Lync "MX" Windows Store-Client</span><span class="sxs-lookup"><span data-stu-id="59800-159">Lync "MX" Windows Store client</span></span>
- <span data-ttu-id="59800-160">Alle lync 2010-Clients</span><span class="sxs-lookup"><span data-stu-id="59800-160">All Lync 2010 clients</span></span>
- <span data-ttu-id="59800-161">Lync Phone Edition – aktualisierte Anleitungen [finden Sie hier](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).</span><span class="sxs-lookup"><span data-stu-id="59800-161">Lync Phone Edition - updated guidance [here](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).</span></span>
- <span data-ttu-id="59800-162">2013-basierte, überlebensfähige Branch Appliance (SBA) oder Survivable Branch Server (SBS)</span><span class="sxs-lookup"><span data-stu-id="59800-162">2013 based Survivable Branch Appliance (SBA) or Survivable Branch Server (SBS)</span></span>
- <span data-ttu-id="59800-163">Cloud Connector Edition (CCE)</span><span class="sxs-lookup"><span data-stu-id="59800-163">Cloud Connector Edition (CCE)</span></span>
- <span data-ttu-id="59800-164">Microsoft Skype for Business für Windows Phone</span><span class="sxs-lookup"><span data-stu-id="59800-164">Skype for Business for Windows Phone</span></span>

### <a name="exceptions"></a><span data-ttu-id="59800-165">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="59800-165">Exceptions</span></span>

#### <a name="lync-server-2013"></a><span data-ttu-id="59800-166">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="59800-166">Lync Server 2013</span></span>

<span data-ttu-id="59800-167">Lync Server 2013 übernimmt eine Abhängigkeit von Windows Fabric, Version 1,0.</span><span class="sxs-lookup"><span data-stu-id="59800-167">Lync Server 2013 takes a dependency on Windows Fabric version 1.0.</span></span>  <span data-ttu-id="59800-168">In der Entwurfsphase von lync Server 2013 wurde Windows Fabric 1,0 für seine überzeugende und neue verteilte Architektur ausgewählt, um Replikation, höchste Verfügbarkeit und Fehlertoleranz bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="59800-168">In the design phase for Lync Server 2013, Windows Fabric 1.0 was chosen for its compelling and new distributed architecture to provide replication, high availability, and fault tolerance.</span></span>  <span data-ttu-id="59800-169">Im Laufe der Zeit haben sowohl Skype for Business Server als auch Windows Fabric diese gemeinsame Architektur erheblich verbessert, wobei in späteren Versionen ein erhebliches Re-Design zu finden ist.</span><span class="sxs-lookup"><span data-stu-id="59800-169">Over time, both Skype for Business Server and Windows Fabric have greatly improved this joint architecture with significant re-design in subsequent versions.</span></span>  <span data-ttu-id="59800-170">Der aktuelle Skype for Business 2015-Server verwendet beispielsweise Windows Fabric 3,0.</span><span class="sxs-lookup"><span data-stu-id="59800-170">Current Skype for Business 2015 Server uses Windows Fabric 3.0, for example.</span></span>

<span data-ttu-id="59800-171">Leider unterstützt Windows Fabric 1,0 **TLS 1,2 nicht.  Wir werden jedoch lync Server 2013 aktualisieren, um mit TLS 1,2 zu arbeiten**.</span><span class="sxs-lookup"><span data-stu-id="59800-171">Unfortunately, Windows Fabric 1.0 **does not support TLS 1.2.  However, we will be updating Lync Server 2013 to work with TLS 1.2**.</span></span> <span data-ttu-id="59800-172">Dies wird im nächsten kumulativen Update für lync Server 2013 erfolgen.</span><span class="sxs-lookup"><span data-stu-id="59800-172">This will be coming in the next Cumulative Update for Lync Server 2013.</span></span>  <span data-ttu-id="59800-173">Wir bieten TLS 1,2-Unterstützung, um Koexistenz-, Migrations-, Föderations-und Hybrid Szenarien zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="59800-173">We're providing TLS 1.2 support to enable co-existence, migration, federation, and hybrid scenarios.</span></span>

<span data-ttu-id="59800-174">Wenn Ihre Organisation TLS 1,0 und 1,1 deaktivieren muss und Sie zurzeit lync Server 2013 verwenden, empfehlen wir, dass Sie den Planungsprozess beginnen, mit der Möglichkeit, dass Sie möglicherweise ein direktes Upgrade oder eine parallele Migration (neue Pools, Verschieben von Benutzern) zu Skype für Business Server 2015 oder höher</span><span class="sxs-lookup"><span data-stu-id="59800-174">If your organization is required to disable TLS 1.0 and 1.1, and you currently use Lync Server 2013, we recommend you begin your planning process, with the possibility you may have to In-place upgrade or Side-by-Side migrate (new pools, move users) to Skype for Business Server 2015 or higher.</span></span>  <span data-ttu-id="59800-175">Oder Sie möchten vielleicht die Migration zu Skype for Business Online beschleunigen.</span><span class="sxs-lookup"><span data-stu-id="59800-175">Or you may want to accelerate migration to Skype for Business Online.</span></span>

#### <a name="call-quality-dashboard"></a><span data-ttu-id="59800-176">Anrufqualitäts-Dashboard</span><span class="sxs-lookup"><span data-stu-id="59800-176">Call Quality Dashboard</span></span>

<span data-ttu-id="59800-177">Das lokale Anruf Qualitäts Dashboard hat derzeit eine Abhängigkeit von TLS 1,0 bei der Neuinstallation (erstmalige Installation in Ihrer lokalen Umgebung).</span><span class="sxs-lookup"><span data-stu-id="59800-177">On-Premises Call Quality Dashboard currently has a dependency on TLS 1.0 during new install (first time installing into your On-Premises environments).</span></span>  <span data-ttu-id="59800-178">Wir untersuchen derzeit dieses Problem und planen, in naher Zukunft eine Lösung zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="59800-178">We are currently investigating this issue and plan to release a fix in the near future.</span></span>  <span data-ttu-id="59800-179">Wenn Sie beabsichtigen, CQD zu installieren und auch TLS 1,0 zu deaktivieren, empfehlen wir, zuerst die CQD-Installation abzuschließen und dann mit der Deaktivierung von TLS 1,0 fortzufahren.</span><span class="sxs-lookup"><span data-stu-id="59800-179">If you are planning to install CQD and also disable TLS 1.0, we recommend that you complete CQD installation first, and then proceed with TLS 1.0 disabling.</span></span>

#### <a name="third-party-devices"></a><span data-ttu-id="59800-180">Geräte von Drittanbietern</span><span class="sxs-lookup"><span data-stu-id="59800-180">Third-party devices</span></span>

<span data-ttu-id="59800-181">Achten Sie bei Geräten von Drittanbietern wie 3PIP-Telefonen, Video Konferenzen, Reverse-Proxys und Last-Balancern darauf, dass Sie die TLS 1,2-Unterstützung überprüfen, sorgfältig testen und bei Bedarf mit dem Anbieter in Verbindung treten.</span><span class="sxs-lookup"><span data-stu-id="59800-181">On third-party devices such as 3PIP phones, Video conferencing, Reverse Proxies and Load Balancers, be sure to validate TLS 1.2 supportability, test carefully, and contact the vendor if needed.</span></span>

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a><span data-ttu-id="59800-182">Überlegungen zur Föderation beim Deaktivieren von TLS 1.0/1.1 auf Edge-Servern</span><span class="sxs-lookup"><span data-stu-id="59800-182">Federation considerations when disabling TLS 1.0/1.1 on Edge servers</span></span>

<span data-ttu-id="59800-183">Sie müssen die Auswirkungen der Deaktivierung von TLS 1.0/1.1 auf Ihren Edge-Servern sorgfältig planen und berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="59800-183">You must carefully plan for and consider the impact of disabling TLS 1.0/1.1 on your Edge servers.</span></span>  <span data-ttu-id="59800-184">Wenn TLS 1,0 und 1,1 deaktiviert sind, stellen Sie möglicherweise fest, dass andere Organisationen nicht mehr mit Ihrer Organisation zusammenarbeiten können.</span><span class="sxs-lookup"><span data-stu-id="59800-184">Once TLS 1.0 and 1.1 are disabled, you may find that other organizations are no longer be able to federate with your organization.</span></span>

<span data-ttu-id="59800-185">Sie können festlegen, dass TLS 1.0/1.1 auf Ihren Edge-Servern aktiviert bleibt, damit die Abwärtskompatibilität mit nicht gepatchten (SFB 2015, lync 2013) oder älteren (2010) externen Systemen gewährleistet ist.</span><span class="sxs-lookup"><span data-stu-id="59800-185">You may opt to keep TLS 1.0/1.1 enabled on your Edge servers to maintain backward compatibility with non-patched (SfB 2015, Lync 2013) or older (2010) external systems.</span></span>

<span data-ttu-id="59800-186">Microsoft kann keine Ratschläge oder Empfehlungen liefern, ob Ihr Edge-Netzwerk (oder irgendein Netzwerk) unter den PCI-Standard fällt. Dies muss vom jeweiligen Unternehmen festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="59800-186">Microsoft cannot provide advice or recommendations on whether or not your Edge network (or any network) falls under PCI standard; that must be determined by the individual company.</span></span>

<span data-ttu-id="59800-187">Skype for Business Online ist heute in der Lage, TLS 1,2 zu nutzen, sodass keine Auswirkungen auf Hybrid/Federation mit Online erwartet werden.</span><span class="sxs-lookup"><span data-stu-id="59800-187">Skype for Business Online is capable of TLS 1.2 today, so no impact to Hybrid/Federation with Online is expected.</span></span>

<span data-ttu-id="59800-188">PIC (Public-Chat-Konnektivität) zum Skype-Verbraucher Dienst: Wir erwarten nicht, dass die Deaktivierung von TLS 1.0/1.1 Auswirkungen auf die [Skype-Konnektivität](../../deploy/deploy-skype-connectivity.md)hat. Microsoft PIC-Gateways sind bereits TLS 1,2-fähig.</span><span class="sxs-lookup"><span data-stu-id="59800-188">PIC (Public IM Connectivity) to Skype Consumer service: We do not expect disabling TLS 1.0/1.1 to impact [Skype Connectivity](../../deploy/deploy-skype-connectivity.md); Microsoft PIC Gateways are already TLS 1.2 capable.</span></span>

## <a name="prerequisites-and-process"></a><span data-ttu-id="59800-189">Voraussetzungen und Prozesse</span><span class="sxs-lookup"><span data-stu-id="59800-189">Prerequisites and process</span></span>

<span data-ttu-id="59800-190">Sofern oben nicht erwähnt, funktionieren Clients und Geräte nach der Deaktivierung von TLS 1,0 und 1,1 außerhalb des Bereichs nicht mehr ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="59800-190">Except where noted above, once TLS 1.0 and 1.1 are disabled out-of-scope servers, clients and devices will longer function properly, or at all.</span></span> <span data-ttu-id="59800-191">Dies bedeutet möglicherweise, dass Sie die Aktualisierung unterbrechen und auf aktualisierte Anleitungen von Microsoft warten müssen.</span><span class="sxs-lookup"><span data-stu-id="59800-191">This may mean you need to pause and wait for updated guidance from Microsoft.</span></span> <span data-ttu-id="59800-192">Wenn Sie davon überzeugt sind, dass Sie alle Anforderungen erfüllen und einen Plan zur Behebung von Lücken haben, fahren Sie fort.</span><span class="sxs-lookup"><span data-stu-id="59800-192">Once you are satisfied that you meet all requirements and have a plan to address gaps, proceed.</span></span>

<span data-ttu-id="59800-193">Auf einem hohen Niveau, während Skype for Business Server 2019 bei der Installation einsatzbereit ist, erfordert Skype for Business Server 2015, dass Sie CU6 HF2 installieren, Voraussetzungen für .net und SQL installieren, erforderliche Registrierungsschlüssel bereitstellen und schließlich eine separate Runde der Betriebssystem-Konfigurationsupdates (d. h. das Deaktivieren von TLS 1,0 und 1,1 über den Import von Registrierungsdateien).</span><span class="sxs-lookup"><span data-stu-id="59800-193">At a high level, while Skype for Business Server 2019 is ready for procedure at install, Skype for Business Server 2015 will require that you install CU6 HF2, applying pre-requisite updates to .NET and SQL, deploying prerequisite registry keys, and finally a separate round of OS configuration updates (i.e. disabling TLS 1.0 and 1.1 via registry file import).</span></span> <span data-ttu-id="59800-194">Es ist äußerst wichtig, dass Sie die Installation aller Voraussetzungen, einschließlich Skype for Business Server 2015 CU6 HF2, abschließen, bevor Sie TLS 1,0 und 1,1 auf einem beliebigen Server in Ihrer Umgebung deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="59800-194">It is critically important that you complete installation of all prerequisites, including Skype for Business Server 2015 CU6 HF2, prior to disabling TLS 1.0 and 1.1 on any server in your environment.</span></span> <span data-ttu-id="59800-195">Für jeden Skype for Business-Server, einschließlich Edge-Rolle und SQL-Backends, sind die Updates erforderlich.</span><span class="sxs-lookup"><span data-stu-id="59800-195">Every Skype for Business server, including Edge role and SQL Backends, requires the updates.</span></span> <span data-ttu-id="59800-196">Stellen Sie außerdem sicher, dass alle unterstützten (in-Scope-) Clients auf die erforderlichen Mindestversionen aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="59800-196">Also ensure that all supported (in-scope) clients have been updated to the required minimum versions.</span></span> <span data-ttu-id="59800-197">Vergessen Sie nicht, Management-Workstations auch zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="59800-197">Don’t forget to update management workstations as well.</span></span>

<span data-ttu-id="59800-198">Wir möchten die übliche Reihenfolge der Vorgänge von "Inside Out" für das Upgrade von Skype for Business-Servern befolgen.</span><span class="sxs-lookup"><span data-stu-id="59800-198">We want to follow the usual order of operations of "inside out" for upgrading Skype for Business servers.</span></span> <span data-ttu-id="59800-199">Behandeln Sie Director-Pools, beständigen Chat und gekoppelte Pools auf die gleiche Weise wie normalerweise.</span><span class="sxs-lookup"><span data-stu-id="59800-199">Treat Director pools, Persistent chat, and Paired Pools in the same manner you normally would.</span></span> <span data-ttu-id="59800-200">Reihenfolge und Methoden für das Upgrade werden [hier](topology.md) und [hier](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)behandelt.</span><span class="sxs-lookup"><span data-stu-id="59800-200">Order and methods for upgrade are covered [here](topology.md) and [here](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span></span>

### <a name="high-level-process"></a><span data-ttu-id="59800-201">Prozess auf höherer Ebene</span><span class="sxs-lookup"><span data-stu-id="59800-201">High-level process</span></span>

1. <span data-ttu-id="59800-202">Testen Sie alle Schritte in Ihrer Testumgebung, bevor Sie Produktionsserver konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="59800-202">Test all steps in your lab prior to configuring production servers.</span></span>
2. <span data-ttu-id="59800-203">Sichern Sie eine Kopie der exportierten Registrierung auf jedem einzelnen Server, der aktualisiert werden soll, und bewahren Sie Sie auf.</span><span class="sxs-lookup"><span data-stu-id="59800-203">Back up and preserve a copy of exported registry on each and every individual server to be updated.</span></span> <span data-ttu-id="59800-204">Sie können keine Registrierungen zwischen Servern freigeben. Sie enthalten eindeutige, auf Computern basierende Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="59800-204">You cannot share registries between servers; they contain unique machine-based keys.</span></span>
3. <span data-ttu-id="59800-205">Aktualisieren Sie alle Skype for Business 2015-Server auf CU6 HF2 oder höher.</span><span class="sxs-lookup"><span data-stu-id="59800-205">Upgrade all Skype for Business 2015 servers to CU6 HF2 or higher.</span></span> <span data-ttu-id="59800-206">(Für Skype for Business Server 2019 ist keine Cu erforderlich)</span><span class="sxs-lookup"><span data-stu-id="59800-206">(For Skype for Business Server 2019, no CU is needed)</span></span>
4. <span data-ttu-id="59800-207">Installieren Sie alle Voraussetzungen für alle Server.</span><span class="sxs-lookup"><span data-stu-id="59800-207">Install all prerequisites to all servers.</span></span>
5. <span data-ttu-id="59800-208">Bereitstellen von erforderlichen Registrierungsschlüsseln</span><span class="sxs-lookup"><span data-stu-id="59800-208">Deploy prerequisite registry keys.</span></span>
6. <span data-ttu-id="59800-209">Stellen Sie sicher, dass alle in-Scope-Clients aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="59800-209">Ensure that all in-scope clients are updated.</span></span>
7. <span data-ttu-id="59800-210">Deaktivieren Sie TLS 1,0 und 1,1 mithilfe des Registrierungs Imports.</span><span class="sxs-lookup"><span data-stu-id="59800-210">Disable TLS 1.0 and 1.1 via registry import.</span></span>
8. <span data-ttu-id="59800-211">Überprüfen Sie, ob Arbeitslasten wie erwartet funktionieren.</span><span class="sxs-lookup"><span data-stu-id="59800-211">Validate that workloads are functioning as expected.</span></span>
    - <span data-ttu-id="59800-212">Wenn Probleme aufgetreten sind, beheben und beheben oder</span><span class="sxs-lookup"><span data-stu-id="59800-212">If problems are encountered, troubleshoot and resolve, or</span></span>
    - <span data-ttu-id="59800-213">Wiederherstellen der Registrierung aus Schritt 2 zum erneuten Aktivieren von TLS 1,0 und 1,1</span><span class="sxs-lookup"><span data-stu-id="59800-213">Restore registry from step 2 to re-enable TLS 1.0 and 1.1</span></span>
9. <span data-ttu-id="59800-214">Überprüfen Sie, ob nur TLS 1,2 verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="59800-214">Validate that only TLS 1.2 is being used.</span></span>

### <a name="install-prerequisites-to-all-servers"></a><span data-ttu-id="59800-215">Installieren von Voraussetzungen für alle Server</span><span class="sxs-lookup"><span data-stu-id="59800-215">Install prerequisites to all servers</span></span>

<span data-ttu-id="59800-216">Umfassende Abhängigkeits Updates sind erforderlich, bevor Sie mit der Deaktivierung von TLS 1,0 und 1,1 auf Betriebssystemebene in Ihren Skype for Business Server 2015-Bereitstellungen beginnen.</span><span class="sxs-lookup"><span data-stu-id="59800-216">Extensive dependency updating is required before you begin to disable TLS 1.0 and 1.1 at the operating system level in your Skype for Business Server 2015 deployments.</span></span> <span data-ttu-id="59800-217">Im folgenden sind die Mindestversionen aufgeführt, die TLS 1,2 unterstützen können.</span><span class="sxs-lookup"><span data-stu-id="59800-217">The following are the minimum versions that can support TLS 1.2.</span></span> <span data-ttu-id="59800-218">Stellen Sie alle erforderlichen Updates für alle Skype for Business-Server in Ihrer Umgebung bereit, bevor Sie mit der Deaktivierung von TLS 1,0 und 1,1 beginnen.</span><span class="sxs-lookup"><span data-stu-id="59800-218">Deploy all prerequisite updates across every Skype for Business server in your environment before you begin disabling TLS 1.0 and 1.1.</span></span>

- <span data-ttu-id="59800-219">Skype for Business Server 2015 CU6 HF2 6.0.9319.516 ([März 2018 Update](https://support.microsoft.com/en-us/help/4086059/march-2018-cumulative-update-6-0-9319-516-for-skype-for-business)) oder höher</span><span class="sxs-lookup"><span data-stu-id="59800-219">Skype for Business Server 2015 CU6 HF2 6.0.9319.516 ([March 2018 update](https://support.microsoft.com/en-us/help/4086059/march-2018-cumulative-update-6-0-9319-516-for-skype-for-business)) or higher</span></span>
- <span data-ttu-id="59800-220">[.NET Framework 4,7](https://www.microsoft.com/en-us/download/details.aspx?id=55167) oder höher mit aktiviertem SchUseStrongCrypto in der Registrierung (siehe unten)</span><span class="sxs-lookup"><span data-stu-id="59800-220">[.NET Framework 4.7](https://www.microsoft.com/en-us/download/details.aspx?id=55167) or higher with SchUseStrongCrypto enabled in the registry (provided below)</span></span>
- <span data-ttu-id="59800-221">SQL muss auf allen Skype for Business 2015-Servern und-Backends aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="59800-221">SQL must be updated on all Skype for Business 2015 servers and backends.</span></span> <span data-ttu-id="59800-222">Aktualisieren Sie den Enterprise Edition-Pool SQL-Backends zuerst und dann den jeweiligen Fes.</span><span class="sxs-lookup"><span data-stu-id="59800-222">Update Enterprise Edition Pool SQL Backends first, then their respective FEs.</span></span> 
    - <span data-ttu-id="59800-223">SQL Server 2014 SP1 + CU5 ([Link](https://support.microsoft.com/help/3130926)) oder höher/SQL Server 2012 SP2 + CU16 oder höher/SQL Server 2014 RTM + CU12 ([Link](https://support.microsoft.com/en-us/help/3130923/cumulative-update-12-for-sql-server-2014)) oder höher/SQL Server 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="59800-223">SQL Server 2014 SP1 + CU5 ([link](https://support.microsoft.com/help/3130926)), or higher / SQL Server 2012 SP2 + CU16 or higher/ SQL Server 2014 RTM + CU12 ([link](https://support.microsoft.com/en-us/help/3130923/cumulative-update-12-for-sql-server-2014)) or higher / SQL Server 2014 SP2</span></span>
    - <span data-ttu-id="59800-224">SQL Server Native Client für SQL Server 2012 ([Link](https://www.microsoft.com/en-us/download/details.aspx?id=50402))</span><span class="sxs-lookup"><span data-stu-id="59800-224">SQL Server Native Client for SQL Server 2012 ([link](https://www.microsoft.com/en-us/download/details.aspx?id=50402))</span></span>
    - <span data-ttu-id="59800-225">Microsoft ODBC-Treiber 11 für SQL Server ([Link](https://www.microsoft.com/en-us/download/details.aspx?id=36434)) oder höher</span><span class="sxs-lookup"><span data-stu-id="59800-225">Microsoft ODBC Driver 11 for SQL Server ([link](https://www.microsoft.com/en-us/download/details.aspx?id=36434)), or higher</span></span>
    - <span data-ttu-id="59800-226">Freigegebene Verwaltungsobjekte für SQL Server 2014 SP2 ([Link](https://www.microsoft.com/en-in/download/details.aspx?id=42295))</span><span class="sxs-lookup"><span data-stu-id="59800-226">Shared Management Objects for SQL Server 2014 SP2 ([link](https://www.microsoft.com/en-in/download/details.aspx?id=42295))</span></span>
    - <span data-ttu-id="59800-227">SQLSysClrTypes für SQL Server 2014 SP2 ([Link](https://www.microsoft.com/en-in/download/details.aspx?id=42295))</span><span class="sxs-lookup"><span data-stu-id="59800-227">SQLSysClrTypes for SQL server 2014 SP2 ([link](https://www.microsoft.com/en-in/download/details.aspx?id=42295))</span></span>

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a><span data-ttu-id="59800-228">Grundlegende Schritte zum Installieren von Voraussetzungen in der empfohlenen Reihenfolge von Vorgängen</span><span class="sxs-lookup"><span data-stu-id="59800-228">Basic steps to install pre-requisites, in recommended order of operations</span></span>

1. <span data-ttu-id="59800-229">Installieren Sie das Skype for Business Server CU6HF2 (6.0.9319.516)-Update auf allen Servern.</span><span class="sxs-lookup"><span data-stu-id="59800-229">Install the Skype for Business Server CU6HF2 (6.0.9319.516) update to all servers.</span></span> 
    1. <span data-ttu-id="59800-230">Installieren Sie das Update auf Komponenten mithilfe des Updates.</span><span class="sxs-lookup"><span data-stu-id="59800-230">Install the update to components using the updater.</span></span>
    2. <span data-ttu-id="59800-231">Aktualisieren Sie Datenbankennach dokumentierten Verfahren.</span><span class="sxs-lookup"><span data-stu-id="59800-231">Update databases according to documented procedures.</span></span> <span data-ttu-id="59800-232">Anweisungen sind unter [https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="59800-232">Instructions are documented at [https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span></span>
    3. <span data-ttu-id="59800-233">Überprüfen Sie die Produktfunktionalität in der Bereitstellung, bevor Sie weitere Änderungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="59800-233">Validate product functionality in the deployment prior to moving forward with any other changes.</span></span>
2. <span data-ttu-id="59800-234">.NET 4,7 Offline-Installationsprogramm herunterladen.</span><span class="sxs-lookup"><span data-stu-id="59800-234">Download .NET 4.7 Offline Installer.</span></span> 
    1. <span data-ttu-id="59800-235">Referenz[https://www.microsoft.com/en-us/download/details.aspx?id=55167](https://www.microsoft.com/en-us/download/details.aspx?id=55167)</span><span class="sxs-lookup"><span data-stu-id="59800-235">Reference: [https://www.microsoft.com/en-us/download/details.aspx?id=55167](https://www.microsoft.com/en-us/download/details.aspx?id=55167)</span></span>
    2. <span data-ttu-id="59800-236">Stellen Sie sicher, dass Skype for Business Server 2015-Dienste auf dem Front-End-Server angehalten werden.</span><span class="sxs-lookup"><span data-stu-id="59800-236">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
    3. <span data-ttu-id="59800-237">Referenz[https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="59800-237">Reference: [https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)</span></span>
    4. <span data-ttu-id="59800-238">Ex (Standard Edition): Stop-CsWindowsServices</span><span class="sxs-lookup"><span data-stu-id="59800-238">Ex (Standard Edition): Stop-CsWindowsServices</span></span>
    5. <span data-ttu-id="59800-239">Ex (Enterprise Edition): Invoke-CsComputerFailover</span><span class="sxs-lookup"><span data-stu-id="59800-239">Ex (Enterprise Edition): Invoke-CsComputerFailover</span></span>
    6. <span data-ttu-id="59800-240">Führen Sie das Installationspaket aus.</span><span class="sxs-lookup"><span data-stu-id="59800-240">Run the installer package.</span></span>
    7. <span data-ttu-id="59800-241">Starten Sie den Server neu.</span><span class="sxs-lookup"><span data-stu-id="59800-241">Reboot the server.</span></span>
3. <span data-ttu-id="59800-242">Aktualisieren Sie SQL Express 2014 auf allen Servern.</span><span class="sxs-lookup"><span data-stu-id="59800-242">Update SQL Express 2014 on all servers.</span></span> 
    1. <span data-ttu-id="59800-243">Referenz[https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span><span class="sxs-lookup"><span data-stu-id="59800-243">Reference: [https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span></span>
    2. <span data-ttu-id="59800-244">Herunterladen von SQL 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="59800-244">Download SQL 2014 SP2</span></span> 
        - <span data-ttu-id="59800-245">Referenz[https://www.microsoft.com/en-us/download/details.aspx?id=53168](https://www.microsoft.com/en-us/download/details.aspx?id=53168)</span><span class="sxs-lookup"><span data-stu-id="59800-245">Reference: [https://www.microsoft.com/en-us/download/details.aspx?id=53168](https://www.microsoft.com/en-us/download/details.aspx?id=53168)</span></span>
    3. <span data-ttu-id="59800-246">Kopieren Sie das Installationsmedium in einen Ordner auf dem Server (z. b.: C:\01_2014SqlSp2).</span><span class="sxs-lookup"><span data-stu-id="59800-246">Copy the installation media to a folder on the server (Ex: C:\01_2014SqlSp2)</span></span>
    4. <span data-ttu-id="59800-247">Sicherstellen, dass die Dienste von Skype for Business Server 2015 auf dem Front-End-Server angehalten werden</span><span class="sxs-lookup"><span data-stu-id="59800-247">Ensure Skype for Business Server 2015 services are stopped on the Front End server</span></span> 
        - <span data-ttu-id="59800-248">Ex (Standard Edition): Stop-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="59800-248">Ex (Standard Edition): Stop-CsWindowsService</span></span>
        - <span data-ttu-id="59800-249">Ex (Enterprise Edition): Invoke-CsComputerFailove</span><span class="sxs-lookup"><span data-stu-id="59800-249">Ex (Enterprise Edition): Invoke-CsComputerFailove</span></span>
    5. <span data-ttu-id="59800-250">Öffnen Sie eine Administratoreingabeaufforderung, und aktualisieren Sie alle installierten Komponenten und Instanzen.</span><span class="sxs-lookup"><span data-stu-id="59800-250">Open an Admin Command Prompt, and upgrade all installed components and instances</span></span> 
        - <span data-ttu-id="59800-251">Beispiel: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe/QS-Parameter/IAcceptSQLServerLicenseTerms/Action = Patch/AllInstances</span><span class="sxs-lookup"><span data-stu-id="59800-251">Example: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances</span></span>
4. <span data-ttu-id="59800-252">Aktualisieren Sie SQL Native Client.</span><span class="sxs-lookup"><span data-stu-id="59800-252">Update SQL Native Client.</span></span> 
    1. <span data-ttu-id="59800-253">Referenz: [https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span><span class="sxs-lookup"><span data-stu-id="59800-253">Reference: [https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span></span>
    2. <span data-ttu-id="59800-254">Herunterladen von[https://www.microsoft.com/en-us/download/details.aspx?id=50402](https://www.microsoft.com/en-us/download/details.aspx?id=50402)</span><span class="sxs-lookup"><span data-stu-id="59800-254">Download from [https://www.microsoft.com/en-us/download/details.aspx?id=50402](https://www.microsoft.com/en-us/download/details.aspx?id=50402)</span></span>
    3. <span data-ttu-id="59800-255">Stellen Sie sicher, dass Skype for Business Server 2015-Dienste auf dem Front-End-Server angehalten werden.</span><span class="sxs-lookup"><span data-stu-id="59800-255">Ensure Skype for Business Server 2015 services are stopped on the Front End server.</span></span> 
        - <span data-ttu-id="59800-256">Ex (Standard Edition): Stop-CsWindowsServices</span><span class="sxs-lookup"><span data-stu-id="59800-256">Ex (Standard Edition): Stop-CsWindowsServices</span></span>
        - <span data-ttu-id="59800-257">Ex (Enterprise Edition): Invoke-CsComputerFailove</span><span class="sxs-lookup"><span data-stu-id="59800-257">Ex (Enterprise Edition): Invoke-CsComputerFailove</span></span>
    4. <span data-ttu-id="59800-258">Beenden der ausgeführten SQL-Instanzen</span><span class="sxs-lookup"><span data-stu-id="59800-258">Stop the SQL instances installed from running</span></span> 
        - <span data-ttu-id="59800-259">Ex: Get-Service "MSSQL $ RTCLOCAL" | Stop-Service</span><span class="sxs-lookup"><span data-stu-id="59800-259">Ex: Get-Service 'MSSQL$RTCLOCAL' | Stop-Servic</span></span>
        - <span data-ttu-id="59800-260">Ex: Get-Service "MSSQL $ LYNCLOCAL" | Stop-Service</span><span class="sxs-lookup"><span data-stu-id="59800-260">Ex: Get-Service 'MSSQL$LYNCLOCAL' | Stop-Servic</span></span>
        - <span data-ttu-id="59800-261">Ex (nur Standard Edition): Get-Service "MSSQL $ RTC" | Stop-Service</span><span class="sxs-lookup"><span data-stu-id="59800-261">Ex (Standard Edition Only): Get-Service 'MSSQL$RTC' | Stop-Servic</span></span>
    5. <span data-ttu-id="59800-262">Installieren Sie das Update.</span><span class="sxs-lookup"><span data-stu-id="59800-262">Install the update.</span></span>
5. <span data-ttu-id="59800-263">Aktualisieren Sie den ODBC-Treiber 11 für SQL Server.</span><span class="sxs-lookup"><span data-stu-id="59800-263">Update ODBC Driver 11 for SQL Server.</span></span> 
    1. <span data-ttu-id="59800-264">Referenz: [https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span><span class="sxs-lookup"><span data-stu-id="59800-264">Reference: [https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span></span>
    2. <span data-ttu-id="59800-265">Herunterladen von[https://www.microsoft.com/en-us/download/confirmation.aspx?id=36434](https://www.microsoft.com/en-us/download/confirmation.aspx?id=36434)</span><span class="sxs-lookup"><span data-stu-id="59800-265">Download from [https://www.microsoft.com/en-us/download/confirmation.aspx?id=36434](https://www.microsoft.com/en-us/download/confirmation.aspx?id=36434)</span></span>
    3. <span data-ttu-id="59800-266">Sicherstellen, dass die Dienste von Skype for Business Server 2015 auf dem Front-End-Server angehalten werden</span><span class="sxs-lookup"><span data-stu-id="59800-266">Ensure that Skype for Business Server 2015 services are stopped on the Front End server</span></span> 
        - <span data-ttu-id="59800-267">Ex (Standard Edition): Stop-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="59800-267">Ex (Standard Edition): Stop-CsWindowsService</span></span>
        - <span data-ttu-id="59800-268">Ex (Enterprise Edition): Invoke-CsComputerFailove</span><span class="sxs-lookup"><span data-stu-id="59800-268">Ex (Enterprise Edition): Invoke-CsComputerFailove</span></span>
    4. <span data-ttu-id="59800-269">Installieren Sie das Update.</span><span class="sxs-lookup"><span data-stu-id="59800-269">Install the update.</span></span>
6. <span data-ttu-id="59800-270">Bereitstellen von erforderlichen Registrierungsschlüsseln</span><span class="sxs-lookup"><span data-stu-id="59800-270">Deploy prerequisite registry keys.</span></span>

### <a name="pre-requisite-registry-keys"></a><span data-ttu-id="59800-271">Voraussetzungen für Registrierungsschlüssel</span><span class="sxs-lookup"><span data-stu-id="59800-271">Pre-requisite registry keys</span></span>

<span data-ttu-id="59800-272">Kopieren/fügen Sie den folgenden Test in den Editor ein, und benennen Sie TLSPreReq. reg oder einen Namen Ihrer Wahl um, und importieren Sie dann:</span><span class="sxs-lookup"><span data-stu-id="59800-272">Copy/paste the following test into Notepad and rename TLSPreReq.reg or a name of your choice, then import:</span></span>

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

<span data-ttu-id="59800-273">Für SQL-Back-Ends für Enterprise Edition-Pools sollten Voraussetzungen und TLS-Deaktivierung als SQL-oder Betriebssystemupdates behandelt werden. Weitere Informationen finden Sie unter:[https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span><span class="sxs-lookup"><span data-stu-id="59800-273">For SQL back ends for Enterprise Edition Pools, prerequisites and TLS disable should be treated as any SQL or OS updates would; refer to: [https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span></span>

<span data-ttu-id="59800-274">Während die Schritte für die Voraussetzungen für die Anwendungs-und TLS-Deaktivierung kombiniert werden können, empfehlen wir dringend, alle Voraussetzungen anzuwenden, bevor Sie mit der Deaktivierung von TLS 1,0 und 1,1 auf Betriebssystemebene fortfahren.</span><span class="sxs-lookup"><span data-stu-id="59800-274">While both the prerequisite application and TLS disabling steps can be combined, we strongly recommend all prerequisites be applied before proceeding with disabling of TLS 1.0 and 1.1 at the operating system level.</span></span> <span data-ttu-id="59800-275">Der bewährte Methodenansatz besteht darin, die Umgebung vorzubereiten, indem alle Voraussetzungen bereitgestellt werden, die Überprüfung, ob Arbeitsauslastungen ordnungsgemäß und wie erwartet funktionieren, und dann zu einem späteren Zeitpunkt die Deaktivierung von TLS 1.0/1.1 fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="59800-275">The best practice approach would be to prepare the environment by deploying all prerequisites, validating that workloads all function correctly and as expected, and then proceeding with TLS 1.0/1.1 disable at a later time.</span></span>

### <a name="disable-tls-10-and-11-via-registry-import"></a><span data-ttu-id="59800-276">Deaktivieren von TLS 1,0 und 1,1 über den Registrierungs Import</span><span class="sxs-lookup"><span data-stu-id="59800-276">Disable TLS 1.0 and 1.1 via registry import</span></span>

<span data-ttu-id="59800-277">Bevor Sie mit den nächsten Schritten fortfahren, *Stellen Sie sicher, dass Sie alle Voraussetzungen und aktualisierten Skype for Business-Server abgeschlossen haben*.</span><span class="sxs-lookup"><span data-stu-id="59800-277">Before you proceed with the next steps, *make sure you have completed all prerequisites and updated Skype for Business Servers*.</span></span>

<span data-ttu-id="59800-278">Kopieren Sie den folgenden Text in eine Notepad-Datei, und benennen Sie ihn **TLSDisable. reg**um:</span><span class="sxs-lookup"><span data-stu-id="59800-278">Copy the following text into a Notepad file and rename it **TLSDisable.reg**:</span></span>

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

<span data-ttu-id="59800-279">Importieren Sie die reg-Datei auf jedem Server, auf dem Sie TLS 1,0 und 1,1 deaktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="59800-279">Import the .reg file on each server you wish to disable TLS 1.0 and 1.1.</span></span> <span data-ttu-id="59800-280">Starten Sie den Server neu.</span><span class="sxs-lookup"><span data-stu-id="59800-280">Reboot the server.</span></span> <span data-ttu-id="59800-281">Wenn die Dienste wieder online sind, wechseln Sie zum nächsten Server.</span><span class="sxs-lookup"><span data-stu-id="59800-281">Once the services have come back online, move to the next server.</span></span> <span data-ttu-id="59800-282">Der Ansatz für Enterprise Edition-Pools ist für jedes Betriebssystemupdate identisch.</span><span class="sxs-lookup"><span data-stu-id="59800-282">The approach for Enterprise Edition Pools is the same you would take for any OS update.</span></span>

<span data-ttu-id="59800-283">Sie haben vielleicht bemerkt, dass wir hier mehr tun, als nur TLS 1,0 und 1,1 zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="59800-283">You may have noticed we are doing more than just disabling TLS 1.0 and 1.1 here.</span></span> <span data-ttu-id="59800-284">Wir unterstützen die erneute Reihenfolge der Verschlüsselungs Suite (wie oben dargestellt) und die Deaktivierung einiger älterer schwacher Chiffren.</span><span class="sxs-lookup"><span data-stu-id="59800-284">We are supporting Cipher Suite re-order (as shown above) and the disabling of some older weak ciphers.</span></span> <span data-ttu-id="59800-285">Dies ist das erste Mal, dass wir diese Änderungen an der Schannel-und Krypto-API in Skype for Business Server offiziell unterstützt haben, und es ist wichtig zu beachten, dass diese Änderungen die einzigen sind, die wir zurzeit unterstützen und getestet haben.</span><span class="sxs-lookup"><span data-stu-id="59800-285">This is the first time we have officially supported these changes to SCHANNEL and Crypto API on Skype for Business Server, and it is important to note that these changes are the only ones we support and have tested at this time.</span></span> <span data-ttu-id="59800-286">Wir können in Zukunft zusätzliche Konfigurationen in Erwägung gezogen, aber im Moment sollten Sie die Registrierungs Importdatei in ihrer Implementierung nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="59800-286">We may consider additional configurations in the future, but for now, please do not modify the registry import file in your implementation.</span></span>

### <a name="validate-that-workloads-are-functioning-as-expected"></a><span data-ttu-id="59800-287">Überprüfen, ob Arbeitslasten wie erwartet funktionieren</span><span class="sxs-lookup"><span data-stu-id="59800-287">Validate that workloads are functioning as expected</span></span>

<span data-ttu-id="59800-288">Nachdem TLS 1,0 und 1,1 in Ihrer Umgebung deaktiviert wurden, stellen Sie sicher, dass alle Ihre Haupt Arbeitsauslastungen wie erwartet funktionieren, beispielsweise Chat #a0 Anwesenheit, P2P-Anrufe, Enterprise-VoIP usw.</span><span class="sxs-lookup"><span data-stu-id="59800-288">Once TLS 1.0 and 1.1 have been disabled in your environment, ensure that all your main workloads are functioning as expected, such as IM & Presence, P2P calls, Enterprise Voice, etc.</span></span>

<span data-ttu-id="59800-289">**Nur überprüfen, ob TLS 1,2 verwendet wird**</span><span class="sxs-lookup"><span data-stu-id="59800-289">**Validate only TLS 1.2 is being used**</span></span>

<span data-ttu-id="59800-290">Lassen Sie Ihr Sicherheits Team eine neue Prüfung des Skype for Business-Datenverkehrs durchführen, um sicherzustellen, dass die älteren Protokolle TLS 1,0 und 1,1 nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="59800-290">Have your Security Team perform a new audit of Skype for Business traffic to ensure that the older protocols TLS 1.0 and 1.1 are no longer in use.</span></span>

<span data-ttu-id="59800-291">Alternativ können Sie Internet Explorer verwenden, um TLS-Verbindungen mit Webdiensten von Skype for Business Server 2015 zu testen, nachdem TLS 1,0 und TLS 1,1 deaktiviert wurden.</span><span class="sxs-lookup"><span data-stu-id="59800-291">Alternatively, you can use Internet Explorer to test TLS connections to web services from Skype for Business Server 2015 after TLS 1.0 and TLS 1.1 have been disabled.</span></span>

1. <span data-ttu-id="59800-292">Starten Sie Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="59800-292">Launch Internet Explorer.</span></span>
2. <span data-ttu-id="59800-293">Wählen Sie **Extras** > **Internet Optionen**aus.</span><span class="sxs-lookup"><span data-stu-id="59800-293">Select **Tools** > **Internet Options**.</span></span>
3. <span data-ttu-id="59800-294">Wählen Sie die Registerkarte **erweitert** aus.</span><span class="sxs-lookup"><span data-stu-id="59800-294">Select the **Advanced** tab.</span></span>
4. <span data-ttu-id="59800-295">Scrollen Sie unter **Einstellungen**nach unten.</span><span class="sxs-lookup"><span data-stu-id="59800-295">Under **Settings**, scroll to the bottom.</span></span>
5. <span data-ttu-id="59800-296">Überprüfen Sie, ob TLS 1,0, TLS 1,1 und TLS 1,2 aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="59800-296">Verify that TLS 1.0, TLS 1.1, and TLS 1.2 are enabled.</span></span>
6. <span data-ttu-id="59800-297">Durchsuchen Sie die interne Web Service-URL Ihres SFB 2015-Pools (sollte eine Verbindung erfolgreich hergestellt werden).</span><span class="sxs-lookup"><span data-stu-id="59800-297">Browse the Internal Web Service URL of your SfB 2015 pool (should connect successfully).</span></span>
7. <span data-ttu-id="59800-298">Wechseln Sie zurück in Internet Explorer, und deaktivieren Sie die Option nur für **TLS 1,2** .</span><span class="sxs-lookup"><span data-stu-id="59800-298">Go back into Internet Explorer and disable the option to **Use TLS 1.2** only.</span></span>
8. <span data-ttu-id="59800-299">Durchsuchen Sie die interne Web Service-URL Ihres SFB 2015-Pools erneut (Verbindungsfehler).</span><span class="sxs-lookup"><span data-stu-id="59800-299">Browse the Internal Web Service URL of your SfB 2015 pool again (should fail to connect).</span></span>

![Internet Optionen](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a><span data-ttu-id="59800-301">Erweiterte Bereitstellungsszenarien</span><span class="sxs-lookup"><span data-stu-id="59800-301">Advanced deployment scenarios</span></span>

<span data-ttu-id="59800-302">Da einige Abhängigkeits Voraussetzungen zur Unterstützung von TLS 1,2 in Skype for Business ser 2015 erforderlich sind, schlägt die Installation von RTM-Medien auf jedem System fehl, auf dem TLS 1,0 und 1,1 deaktiviert wurden.</span><span class="sxs-lookup"><span data-stu-id="59800-302">Because some dependency prerequisites are required to support TLS 1.2 in Skype for Business Ser 2015, installing from RTM media will fail on any system where TLS 1.0 and 1.1 have been disabled.</span></span>

<span data-ttu-id="59800-303">**Bereitstellen von neuen Standard Edition-Servern oder Enterprise Edition-Pools, sobald TLS 1,0 und 1,1 in Ihrer Umgebung deaktiviert wurden.**</span><span class="sxs-lookup"><span data-stu-id="59800-303">**Deploying New Standard Edition Servers or Enterprise Edition Pools once TLS 1.0 and 1.1 have been disabled in your environment.**</span></span>

<span data-ttu-id="59800-304">**Option 1:** Verwenden Sie [SmartSetup](../../deploy/install/install-skype-for-business-server.md).</span><span class="sxs-lookup"><span data-stu-id="59800-304">**Option 1:** Use [SmartSetup](../../deploy/install/install-skype-for-business-server.md).</span></span> <span data-ttu-id="59800-305">Beachten Sie, dass wir SmartSetup aktualisieren, um die aktualisierten SQL-Binärdateien in einem zukünftigen Cu-Daten Satz aufnehmen zu können, und diesen Artikel in Zukunft aktualisieren werden.</span><span class="sxs-lookup"><span data-stu-id="59800-305">Note that we are updating SmartSetup to accommodate the updated SQL binaries in a future CU, and will update this article in the future.</span></span>

<span data-ttu-id="59800-306">**Option 2:** Lokale SQL-Instanzen (RTCLOCAL und LYNCLOCAL) vor der Installation</span><span class="sxs-lookup"><span data-stu-id="59800-306">**Option 2:** Pre-install local SQL instances (RTCLOCAL and LYNCLOCAL)</span></span>

1. <span data-ttu-id="59800-307">Laden Sie SQL Express 2014 SP2 (SQLEXPR_x64. exe) in den lokalen Ordner auf FE herunter, und kopieren Sie Sie.</span><span class="sxs-lookup"><span data-stu-id="59800-307">Download and copy SQL Express 2014 SP2 (SQLEXPR_x64.exe) to local folder on FE.</span></span> <span data-ttu-id="59800-308">Angenommen, der Ordnerpfad <SQL_FOLDER_PATH>.</span><span class="sxs-lookup"><span data-stu-id="59800-308">Let’s say folder path <SQL_FOLDER_PATH>.</span></span>
2. <span data-ttu-id="59800-309">Starten Sie PowerShell oder Eingabeaufforderung, und navigieren Sie zu <SQL_FOLDER_PATH>.</span><span class="sxs-lookup"><span data-stu-id="59800-309">Launch PowerShell or Command Prompt and navigate to <SQL_FOLDER_PATH>.</span></span>
3. <span data-ttu-id="59800-310">Erstellen Sie die RTCLOCAL-SQL-Instanz, indem Sie den folgenden Befehl ausführen.</span><span class="sxs-lookup"><span data-stu-id="59800-310">Create the RTCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="59800-311">Warten Sie, bis "SQLEXPR_x64. exe" abgeschlossen ist, bevor Sie fortfahren:</span><span class="sxs-lookup"><span data-stu-id="59800-311">Wait until SQLEXPR_x64.exe finishes before proceeding:</span></span>

    <span data-ttu-id="59800-312">SQLEXPR_x64. exe/q/IACCEPTSQLSERVERLICENSETERMS/UPDATEENABLED = 0/HIDECONSOLE/Action = install/Features = SQLEngine, Tools/instanceName = RTCLOCAL/TCPENABLED = 1/SQLSVCACCOUNT = "NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "Builtin \ Administratoren "/BROWSERSVCSTARTUPTYPE =" Automatic "/AGTSVCACCOUNT =" NTAUTHORITY\NetworkService "/SQLSVCSTARTUPTYPE = automati</span><span class="sxs-lookup"><span data-stu-id="59800-312">SQLEXPR_x64.exe  /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=RTCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automati</span></span>
1. <span data-ttu-id="59800-313">Erstellen Sie die LYNCLOCAL-SQL-Instanz, indem Sie den folgenden Befehl ausführen.</span><span class="sxs-lookup"><span data-stu-id="59800-313">Create the LYNCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="59800-314">Warten Sie, bis SQLEXPR_x64. exe beendet ist, bevor Sie mit dem nächsten Schritt fortfahren:</span><span class="sxs-lookup"><span data-stu-id="59800-314">Wait until SQLEXPR_x64.exe finishes before proceeding to the next step:</span></span>

    <span data-ttu-id="59800-315">SQLEXPR_x64. exe/q/IACCEPTSQLSERVERLICENSETERMS/UPDATEENABLED = 0/HIDECONSOLE/Action = install/Features = SQLEngine, Tools/instanceName = LYNCLOCAL/TCPENABLED = 1/SQLSVCACCOUNT = "NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "Builtin \ Administratoren "/BROWSERSVCSTARTUPTYPE =" Automatic "/AGTSVCACCOUNT =" NTAUTHORITY\NetworkService "/SQLSVCSTARTUPTYPE = Automatic</span><span class="sxs-lookup"><span data-stu-id="59800-315">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=LYNCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automatic</span></span>
1. <span data-ttu-id="59800-316">Führen Sie das Setup von Skype for Business Server 2015 RTM aus.</span><span class="sxs-lookup"><span data-stu-id="59800-316">Run Skype for Business Server 2015 RTM setup.</span></span>
2. <span data-ttu-id="59800-317">Führen Sie die restlichen Schritte aus dem Abschnitt Voraussetzungen oben aus.</span><span class="sxs-lookup"><span data-stu-id="59800-317">Follow the remaining steps from the prerequisites section above.</span></span>

<span data-ttu-id="59800-318">**Option 3:** Sie können Binärdateien in einem lokalen Installationsmedien Verzeichnis auch manuell wie folgt ersetzen:</span><span class="sxs-lookup"><span data-stu-id="59800-318">**Option 3:** You may also manually replace binaries in a local installation media directory as follows:</span></span>

1. [<span data-ttu-id="59800-319">Installieren von Voraussetzungen für Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="59800-319">Install prerequisites for Skype for Business Server</span></span>](../../deploy/install/install-prerequisites.md)  
2. 2. <span data-ttu-id="59800-320">Installieren Sie .NET 4,7:</span><span class="sxs-lookup"><span data-stu-id="59800-320">Install .NET 4.7:</span></span> 
      - <span data-ttu-id="59800-321">**Hinweis:** Wir haben zunächst die Unterstützung für .NET 4,7 in Skype for Business Server 2015 CU5 + (6.0.9319.281) eingeführt.</span><span class="sxs-lookup"><span data-stu-id="59800-321">**Note:** We first introduced support for .NET 4.7 in Skype for Business Server 2015 CU5+ (6.0.9319.281).</span></span> <span data-ttu-id="59800-322">Aus diesem Grund werden wir in den nachfolgenden Schritten die wichtigsten Komponenten vor der Hauptinstallation aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="59800-322">Therefore, in later steps below we will be updating Core Components prior to the main install.</span></span>
      - <span data-ttu-id="59800-323">Download: https://www.microsoft.com/en-us/download/details.aspx?id=55167.</span><span class="sxs-lookup"><span data-stu-id="59800-323">Download: https://www.microsoft.com/en-us/download/details.aspx?id=55167.</span></span>
      - <span data-ttu-id="59800-324">Referenz: [Software, die vor der Bereitstellung von Skype for Business Server 2015 installiert werden soll](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span><span class="sxs-lookup"><span data-stu-id="59800-324">Reference: [Software that should be installed before a Skype for Business Server 2015 deployment](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span></span>
3. <span data-ttu-id="59800-325">Kopieren von ISO-Dateien/-Ordnern:</span><span class="sxs-lookup"><span data-stu-id="59800-325">Copy ISO Files/Folders:</span></span> 
    - <span data-ttu-id="59800-326">Wenn der Skype for Business Server 2015 ISO angeschlossen ist, öffnen Sie das Stammverzeichnis des Laufwerks, dem es angefügt ist (ex\) : D: im Datei-Explorer.</span><span class="sxs-lookup"><span data-stu-id="59800-326">With the Skype for Business Server 2015 ISO attached, open the root directory of the drive it is attached as (Ex: D:\) in File Explorer.</span></span>
    - <span data-ttu-id="59800-327">Kopieren Sie alle Ordner und Dateien in einen Ordner auf einem lokalen Datenträger (z. b.: C:\SkypeForBusiness2015ISO).</span><span class="sxs-lookup"><span data-stu-id="59800-327">Copy all folders and files to a folder on a local disk (Ex: C:\SkypeForBusiness2015ISO).</span></span>
    - <span data-ttu-id="59800-328">**Hinweis:** Vor der Installation von Komponenten müssen einige Dateien für die Unterstützung von TLS 1,2 aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="59800-328">**Note:** Prior to installing components, some files will need to be updated for support of TLS 1.2.</span></span>
4. <span data-ttu-id="59800-329">Ersetzen Sie MSI/exe-Pakete:</span><span class="sxs-lookup"><span data-stu-id="59800-329">Replace MSI/EXE Packages:</span></span> 
    - <span data-ttu-id="59800-330">Ersetzen Sie die vorhandenen MSI-und exe-Pakete im Ordner/Setup/amd64/des Installationsmediums auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="59800-330">Replace the existing MSI and EXE packages in the /Setup/amd64/ folder of the installation media on the local machine.</span></span>
    - <span data-ttu-id="59800-331">SQL 2014 SP2 Express:https://www.microsoft.com/en-us/download/details.aspx?id=53167</span><span class="sxs-lookup"><span data-stu-id="59800-331">SQL 2014 SP2 Express: https://www.microsoft.com/en-us/download/details.aspx?id=53167</span></span> 
        - <span data-ttu-id="59800-332">Benennen Sie SQLEXPR_x64 auf dem lokalen Computer um, und ersetzen Sie die vorhandene Datei im Setup/amd64/-Ordner des Installationsmediums.</span><span class="sxs-lookup"><span data-stu-id="59800-332">Rename to SQLEXPR_x64 on the local machine, and replace the existing file in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="59800-333">SQL Native Client:https://www.microsoft.com/en-us/download/details.aspx?id=50402</span><span class="sxs-lookup"><span data-stu-id="59800-333">SQL Native Client: https://www.microsoft.com/en-us/download/details.aspx?id=50402</span></span> 
        - <span data-ttu-id="59800-334">**Hinweis:** Benennen Sie diese bei Bedarf in sqlncli. msi um, und ersetzen Sie dann die vorhandene Datei, die im Setup/amd64/-Ordner des Installationsmediums vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="59800-334">**Note:** Rename this if necessary to sqlncli.msi, and then replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="59800-335">SQL-Verwaltungsobjekte:https://www.microsoft.com/en-us/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="59800-335">SQL Management Objects: https://www.microsoft.com/en-us/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="59800-336">**Hinweis:** Das Feature Pack enthält viele Elemente, die heruntergeladen werden können.</span><span class="sxs-lookup"><span data-stu-id="59800-336">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="59800-337">Wählen Sie diese Option aus, um nur SharedManagementObjects. msi herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="59800-337">Select to download SharedManagementObjects.msi only.</span></span>
        - <span data-ttu-id="59800-338">**Hinweis:** Ersetzen Sie die vorhandene Datei, die im Setup/amd64/-Ordner des Installationsmediums vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="59800-338">**Note:** Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="59800-339">SQL CLR-Typen:https://www.microsoft.com/en-us/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="59800-339">SQL CLR Types: https://www.microsoft.com/en-us/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="59800-340">**Hinweis:** Das Feature Pack enthält viele Elemente, die heruntergeladen werden können.</span><span class="sxs-lookup"><span data-stu-id="59800-340">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="59800-341">Zum Herunterladen von CQLSysClrTypes. msi auswählen</span><span class="sxs-lookup"><span data-stu-id="59800-341">Select to download CQLSysClrTypes.msi only</span></span>
        - <span data-ttu-id="59800-342">**Hinweis**: Ersetzen Sie die vorhandene Datei, die im Setup/amd64/-Ordner des Installationsmediums vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="59800-342">**Note**: Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
5. <span data-ttu-id="59800-343">Installieren von Kernkomponenten:</span><span class="sxs-lookup"><span data-stu-id="59800-343">Install Core Components:</span></span> 
    - <span data-ttu-id="59800-344">Führen Sie Setup. exe aus dem Setup/amd64/Ordner des Installationsmediums aus.</span><span class="sxs-lookup"><span data-stu-id="59800-344">Run Setup.exe from the Setup/amd64/ folder of the installation media.</span></span> <span data-ttu-id="59800-345">Befolgen Sie die Anweisungen zum Installieren der Kernkomponenten.</span><span class="sxs-lookup"><span data-stu-id="59800-345">Follow the instructions to install Core Components</span></span>
    - <span data-ttu-id="59800-346">Schließen Sie Kernkomponenten.</span><span class="sxs-lookup"><span data-stu-id="59800-346">Close Core Components.</span></span>
6. <span data-ttu-id="59800-347">Aktualisieren von Kernkomponenten:</span><span class="sxs-lookup"><span data-stu-id="59800-347">Update Core Components:</span></span> 
    - <span data-ttu-id="59800-348">Laden Sie das Skype for Business Update-Installationsprogramm herunter.</span><span class="sxs-lookup"><span data-stu-id="59800-348">Download the Skype for Business Update Installer.</span></span>
    - <span data-ttu-id="59800-349">Führen Sie das Installationsprogramm aus, um die Kernkomponenten zu aktualisieren und die Leistungsindikatoren zu installieren.</span><span class="sxs-lookup"><span data-stu-id="59800-349">Run the installer to update Core Components and install the performance counters.</span></span>
    - <span data-ttu-id="59800-350">**Hinweis:** Ab der Veröffentlichung von CU6HF2 wird das Feature für die automatische Aktualisierung zurzeit nur bis zu CU6 installiert.</span><span class="sxs-lookup"><span data-stu-id="59800-350">**Note:** As of the release of CU6HF2, the auto-update feature currently only will install up to CU6.</span></span> <span data-ttu-id="59800-351">Daher muss der Updater separat ausgeführt werden, um Kernkomponenten auf 6.0.9319.516 zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="59800-351">Therefore, the updater must be run separately to update Core Components to 6.0.9319.516.</span></span>
    - <span data-ttu-id="59800-352">Referenzhttps://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015</span><span class="sxs-lookup"><span data-stu-id="59800-352">Reference: https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015</span></span>
7. <span data-ttu-id="59800-353">Installieren von Verwaltungs Tools (optional):</span><span class="sxs-lookup"><span data-stu-id="59800-353">Install Administrative Tools (Optional):</span></span> 
    - <span data-ttu-id="59800-354">Damit werden die Microsoft SQL Server 2012 Native Client-, SQL Server 2014 Management Objects (x64)-und Microsoft System CLR-Typen für SQL Server 2014 (x64) unter Verwendung der aktualisierten Dateien installiert.</span><span class="sxs-lookup"><span data-stu-id="59800-354">This will install the Microsoft SQL Server 2012 Native Client, SQL Server 2014 Management Objects (x64), and Microsoft System CLR Types for SQL Server 2014 (x64) using the updated files.</span></span> <span data-ttu-id="59800-355">Darüber hinaus steht der Skype for Business Server 2015-Topologie-Generator und die Systemsteuerung auf dem lokalen Computer zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="59800-355">Additionally, the Skype for Business Server 2015 Topology Builder and Control Panel will be available on the local machine.</span></span>
8. <span data-ttu-id="59800-356">Installieren des lokalen Konfigurationsspeichers (Schritt 1):</span><span class="sxs-lookup"><span data-stu-id="59800-356">Install Local Configuration Store (Step 1):</span></span> 
     - <span data-ttu-id="59800-357">Öffnen Sie den Bereitstellungs-Assistenten, klicken Sie auf Installieren oder aktualisieren Sie das Skype for Business Server-System, und klicken Sie auf **Ausführen** unter Schritt 1: Installieren des lokalen Konfigurationsspeichers.</span><span class="sxs-lookup"><span data-stu-id="59800-357">Open the Deployment Wizard, click Install or Update Skype for Business Server System, and click on **Run** at Step 1: Install Local Configuration Store.</span></span>
     - <span data-ttu-id="59800-358">Klicken Sie im Dialogfeld **lokalen Konfigurationsspeicher installieren** auf **weiter** .</span><span class="sxs-lookup"><span data-stu-id="59800-358">Click **Next** in the **Install Local Configuration Store** dialog box.</span></span>
     <span data-ttu-id="59800-359">![Dialogfeld ' lokalen Konfigurationsspeicher installieren '](../../media/local-configuration-store.png)</span><span class="sxs-lookup"><span data-stu-id="59800-359">![Install Local Configuration Store dialog box](../../media/local-configuration-store.png)</span></span>
     - <span data-ttu-id="59800-360">Überprüfen Sie die Ergebnisse, und stellen Sie sicher, dass der Vorgangs Status abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="59800-360">Review the results, and ensure that the Task Status is Completed.</span></span> <span data-ttu-id="59800-361">Überprüfen Sie die resultierende Protokolldatei, indem Sie auf **Protokoll anzeigen**klicken.</span><span class="sxs-lookup"><span data-stu-id="59800-361">Review the resulting log file by clicking **View Log**.</span></span>
     <span data-ttu-id="59800-362">![Vorgangsstatus wird als abgeschlossen angezeigt](../../media/local-configuration-task-completed.png)</span><span class="sxs-lookup"><span data-stu-id="59800-362">![Task status shows as Completed](../../media/local-configuration-task-completed.png)</span></span>
     - <span data-ttu-id="59800-363">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="59800-363">Click **Finish**.</span></span>
9. <span data-ttu-id="59800-364">Einrichten oder Entfernen von Skype for Business Server-Komponenten (Schritt 2):</span><span class="sxs-lookup"><span data-stu-id="59800-364">Set up or remove Skype for Business Server Components (Step 2):</span></span>
    - <span data-ttu-id="59800-365">Öffnen Sie den Bereitstellungs-Assistenten, klicken Sie auf **installieren oder aktualisieren Sie das Skype for Business Server-System**, und klicken Sie auf **Ausführen** bei Schritt 2: Einrichten oder Entfernen von Skype for Business Server-Komponenten</span><span class="sxs-lookup"><span data-stu-id="59800-365">Open the Deployment Wizard, click **Install or Update Skype for Business Server System**, and click **Run** at Step 2: Set up or Remove Skype for Business Server Components</span></span>
    - <span data-ttu-id="59800-366">Klicken Sie im Dialogfeld Skype for Business Server-Komponenten einrichten auf **weiter** .</span><span class="sxs-lookup"><span data-stu-id="59800-366">Click **Next** in the Set Up Skype for Business Server Components dialog box.</span></span>
    <span data-ttu-id="59800-367">![Das Fenster "Skype for Business Server-Komponenten einrichten"](../../media/set-up-skype-for-business-server-components-window.png)</span><span class="sxs-lookup"><span data-stu-id="59800-367">![the Set Up Skype for Business Server Components window](../../media/set-up-skype-for-business-server-components-window.png)</span></span>
    - <span data-ttu-id="59800-368">Überprüfen Sie das Protokoll mithilfe von View Log, und überprüfen Sie, ob Setup ohne Probleme abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="59800-368">Review the log using View Log, and validate that setup completed without issues.</span></span> 
    - <span data-ttu-id="59800-369">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="59800-369">Click **Finish**.</span></span>
10. <span data-ttu-id="59800-370">Fahren Sie nach Bedarf mit zusätzlicher Installation und Konfiguration fort (Sie können an dieser Stelle die normalen Installationsverfahren fortsetzen).</span><span class="sxs-lookup"><span data-stu-id="59800-370">Proceed with additional installation and configuration as required (you can resume normal installation procedures at this point).</span></span>
