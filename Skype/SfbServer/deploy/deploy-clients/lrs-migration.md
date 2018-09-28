---
title: Migrieren von Lync Raum System Geräte zu Skype Raum System, Version 2
ms.author: jambirk
author: jambirk
ms.reviewer: sohailta
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ''
description: Lesen Sie in diesem Thema erfahren, wie Lync Raum Systemkomponenten Verwendung die Systemsoftware Skype Raum v2 migrieren.
ms.openlocfilehash: e552f3979bf64a0fe1ebadebdf39a9a55da1e28c
ms.sourcegitcommit: 19fb0279985251c00cd507a8d13b8499b19e2808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2018
ms.locfileid: "25347537"
---
# <a name="migrate-lync-room-system-lrs-devices-to-skype-room-system-v2"></a><span data-ttu-id="15adb-103">Migrieren von Lync Raum System (LRS) Geräte zu Skype Raum System v2</span><span class="sxs-lookup"><span data-stu-id="15adb-103">Migrate Lync Room System (LRS) devices to Skype Room System v2</span></span> 
<span data-ttu-id="15adb-104">Lync Raum System (LRS) Geräte mit Skype Raum System Version 1 (SRS v1) Software werden Ablauf des Supports auf 9 Oktober 2018 erreichen.</span><span class="sxs-lookup"><span data-stu-id="15adb-104">Lync Room System (LRS) devices with Skype Room System Version 1 (SRS v1) software will reach end of support on October 9, 2018.</span></span> <span data-ttu-id="15adb-105">Dies bedeutet, dass Skype Raum Systemsoftware Produktupdates oder Hotfixes nach diesem Datum nicht abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="15adb-105">This means Skype Room Systems software will not get any product updates or fixes after this date.</span></span> <span data-ttu-id="15adb-106">Kunden mit Lync Raum System im Geräte-Skype Raum Systemsoftware v1, sollten ihre Geräte auf Skype Raum System, Version 2 (SRS v2) zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="15adb-106">Customers with Lync Room System devices using Skype Room System v1 software are advised to upgrade their devices to Skype Room System version 2 (SRS v2).</span></span>

<span data-ttu-id="15adb-107">Skype Raum System Version 2 (SRS v2) Software arbeitet mit Microsoft-Teams, zusätzlich zu Skype Business Server und Online-Dienste für Besprechungen und Aufrufen von auf allen Geräten von SRS v2 unterstützt.</span><span class="sxs-lookup"><span data-stu-id="15adb-107">Skype Room System Version 2 (SRS v2) software works with Microsoft Teams in addition to Skype for Business Server and Online services for meetings and calling on all SRS v2 supported devices.</span></span>

<span data-ttu-id="15adb-108">Ihre vorhandenen Geräte **können** weiterhin funktionsfähig, nach dem Ende des Skype Raum Systemsoftware v1 unterstützen.</span><span class="sxs-lookup"><span data-stu-id="15adb-108">Your existing devices **may** continue to work after the end of Skype Room System v1 software support.</span></span> <span data-ttu-id="15adb-109">Diese Software einen Software-Fehler, der ein Update freigeben Microsoft benötigt werden schließlich erreicht, oder Sie haben einen Fall, in dem eine vorhandene Kommunikationsprotokoll von Skype Raum System v1 Software Änderungen verwendet oder wird nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="15adb-109">This software will eventually hit a software bug that needs Microsoft to release a fix, or may have a case where an existing communication protocol used by Skype Room System v1 software changes or is no longer supported.</span></span> <span data-ttu-id="15adb-110">Eine solche bekannte Änderung ist das Verwerfen von TLS 1.0 / 1.1 in Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="15adb-110">One such known change is deprecation of TLS 1.0/ 1.1 in Microsoft Office 365.</span></span> <span data-ttu-id="15adb-111">Erfahren Sie mehr über die [Vorbereitung auf das Verwerfen der TLS 1.0/1.1](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608).</span><span class="sxs-lookup"><span data-stu-id="15adb-111">You can learn more about [Preparing for TLS 1.0/1.1 Deprecation](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608).</span></span>  

## <a name="which-devices-are-affected"></a><span data-ttu-id="15adb-112">Welche Geräte betroffen sind?</span><span class="sxs-lookup"><span data-stu-id="15adb-112">Which devices are affected?</span></span>
<span data-ttu-id="15adb-113">Hier wird die Liste der Geräte, die von dieser Änderung betroffen sind:</span><span class="sxs-lookup"><span data-stu-id="15adb-113">Here is the list of the devices that are affected by this change:</span></span>
- [<span data-ttu-id="15adb-114">Intelligente Raum-Systeme</span><span class="sxs-lookup"><span data-stu-id="15adb-114">SMART Room systems</span></span>](https://smartkapp.com/products/smart-room-systems)
- [<span data-ttu-id="15adb-115">Crestron RL2</span><span class="sxs-lookup"><span data-stu-id="15adb-115">Crestron RL2</span></span>](https://www.crestron.com/en-US/Products/Featured-Solutions/Crestron-RL-2)
- [<span data-ttu-id="15adb-116">Polycom CX8000</span><span class="sxs-lookup"><span data-stu-id="15adb-116">Polycom CX8000</span></span>](http://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)
- <span data-ttu-id="15adb-117">Crestron RL</span><span class="sxs-lookup"><span data-stu-id="15adb-117">Crestron RL</span></span>

## <a name="upgrade-options"></a><span data-ttu-id="15adb-118">Upgrade-Optionen</span><span class="sxs-lookup"><span data-stu-id="15adb-118">Upgrade options</span></span>
<span data-ttu-id="15adb-119">Es gibt mehrere Optionen für das Upgrade von Lync Raum Systeme auf die nächste Generation von Skype Raum Systeme (SRS v2).</span><span class="sxs-lookup"><span data-stu-id="15adb-119">There are multiple options for upgrading Lync Room Systems to the next generation of Skype Room Systems (SRS v2).</span></span>

### <a name="crestron-hardware-trade-in-program"></a><span data-ttu-id="15adb-120">Crestron Hardware Rückkauf Programm</span><span class="sxs-lookup"><span data-stu-id="15adb-120">Crestron hardware Trade-in program</span></span>
<span data-ttu-id="15adb-121">Crestron wird ein Upgrade der [Crestron SR-System](https://www.crestron.com/en-us/products/featured-solutions/crestron-sr) oder einer gleichwertigen für alle nicht-Crestron Lync Raum System Kunden bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="15adb-121">Crestron will provide an upgrade to the [Crestron SR system](https://www.crestron.com/en-us/products/featured-solutions/crestron-sr) or equivalent for all Non-Crestron Lync Room System customers.</span></span> <span data-ttu-id="15adb-122">Finden Sie unter Details dieses Programms [hier](https://support.crestron.com/app/answers/answer_view/a_id/1000220) oder <!-- For details, --> [e-Mail](mailto:lrsupgrade@crestron.com) Crestron LRS Support.</span><span class="sxs-lookup"><span data-stu-id="15adb-122">See details of this program [here](https://support.crestron.com/app/answers/answer_view/a_id/1000220) or <!-- For details, -->[email](mailto:lrsupgrade@crestron.com) Crestron LRS support.</span></span>  


### <a name="crestron-rl2-to-rl3"></a><span data-ttu-id="15adb-123">Crestron RL2 auf RL3</span><span class="sxs-lookup"><span data-stu-id="15adb-123">Crestron RL2 to RL3</span></span>
<span data-ttu-id="15adb-124">Bestehende Crestron RL2 (auch als Crestron RL200 bezeichnet) Kunden können ein Aktualisierungspaket zum Aktualisieren des aktuellen RL2 RL3 Verwendung erwerben eine minimale Kosten pro Gerät.</span><span class="sxs-lookup"><span data-stu-id="15adb-124">Existing Crestron RL2 (also referred to as Crestron RL200) customers can acquire an upgrade package to upgrade current RL2 to RL3 using a for a minimal cost per device.</span></span> <span data-ttu-id="15adb-125">Finden Sie unter Details dieses Programms [hier](https://support.crestron.com/app/answers/answer_view/a_id/1000220) oder <!-- For details, --> [e-Mail](mailto:lrsupgrade@crestron.com) Crestron LRS Support.</span><span class="sxs-lookup"><span data-stu-id="15adb-125">See details of this program [here](https://support.crestron.com/app/answers/answer_view/a_id/1000220) or <!-- For details, -->[email](mailto:lrsupgrade@crestron.com) Crestron LRS support.</span></span>  


### <a name="smart-room-systems-upgrade--diy-program"></a><span data-ttu-id="15adb-126">Intelligente Raum Systeme Upgrade & DIY Programm</span><span class="sxs-lookup"><span data-stu-id="15adb-126">SMART Room Systems upgrade & DIY program</span></span>
<span data-ttu-id="15adb-127">SMART LRS Kunden, ausreichend Abstand zu platzieren Crestron Hardware Rückkauf Programm arbeiten Microsoft und EFFIZIENT auch auf die Bereitstellung einer Lösung für das upgrade auf Skype Raum System v2.</span><span class="sxs-lookup"><span data-stu-id="15adb-127">For SMART LRS customers, apart from Crestron hardware trade-in program, Microsoft and SMART are also working on providing a solution to upgrade to Skype Room System v2.</span></span> <span data-ttu-id="15adb-128">Microsoft ist eine DIY Lösung auch für intelligente LRS Kunden testen.</span><span class="sxs-lookup"><span data-stu-id="15adb-128">Microsoft is also testing a DIY solution for SMART LRS customers.</span></span> <span data-ttu-id="15adb-129">Weitere Informationen zu dieser Programme werden auf dieser Seite in frühe Oktober 2018 bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="15adb-129">More details of these programs will be provided on this page in early October 2018.</span></span> <span data-ttu-id="15adb-130">Stellen Sie sicher, dass Sie für die Updates auf diese Upgradeoptionen zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="15adb-130">Please make sure to check back for updates on these upgrade options.</span></span>

<!--  
For later 
### Do-It-Yourself
A Do-It-Yourself option is also available for customers with upgrade to Windows 10 and Skype Room Systems v2 software. Windows 10 Enterprise Licenses are available through [approved resellers](https://www.microsoft.com/en-us/Licensing/how-to-buy/how-to-buy.aspx) and Skype Room System V2 software will be available through this guide. 
 
  
To use this option however, customers must additionaly buy a [Logitech Screen Share](https://www.logitech.com/en-us/product/screen-share) adapter. Microsoft will provide instructions on how to use this adapter with Skype Room System v2 software. 


Look for upgrade instructions on this page shortly. 
  
### Summary of upgrade options
This table lists summary of all available options for existing LRS devices:
<!--  For later 
| Upgrade Option | SMART Room Systems | Crestron RL2 | Polycom CX8000 | Crestron RL |
|:--- |:--- |:--- |:--- |:--- |
|**Crestron hardware </br>Trade-in program**|Available|Available|Available|Available|
|**Crestron RL3**|Not Available|Available|Not Available|Not Available|
|**Do-It-Yourself**|Available|Not Available|Not Available|Not Available|
| | | | | |
-->

## <a name="what-should-you-do"></a><span data-ttu-id="15adb-131">Was sollten Sie tun?</span><span class="sxs-lookup"><span data-stu-id="15adb-131">What should you do?</span></span>
<span data-ttu-id="15adb-132">Es wird empfohlen, dass Sie Lync Raum Systemkomponenten Skype Raum Systemen V2 vor TLS 1.0/1.1 das Verwerfen von oben erwähnten Upgradeoptionen aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="15adb-132">We recommend you plan to update Lync Room System devices to Skype Room Systems v2 before TLS 1.0/1.1 deprecation using upgrade options mentioned above.</span></span> <span data-ttu-id="15adb-133">Darüber hinaus können Sie auch bedenken, Austauschen von vorhandenen Geräten mit neuer für SRS v2 zertifizierte Geräte.</span><span class="sxs-lookup"><span data-stu-id="15adb-133">Additionally, you may also consider replacing existing devices with new devices certified for SRS v2.</span></span> <span data-ttu-id="15adb-134">Einzelheiten finden Sie unter [Raum Geräte](https://aka.ms/roomdevices) und auch betrachten Sie [Skype Raum Systemen v2 Anforderungen](https://docs.microsoft.com/en-us/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).</span><span class="sxs-lookup"><span data-stu-id="15adb-134">See [Room devices](https://aka.ms/roomdevices) for details and also take a look at [Skype Room Systems v2 requirements](https://docs.microsoft.com/en-us/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).</span></span>  

> [!NOTE]
> <span data-ttu-id="15adb-135">Fingereingabe und Whiteboard-Funktionalität ist in Skype Raum System v2 noch nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="15adb-135">Touch and whiteboard functionality is not yet supported in Skype Room System v2.</span></span> <span data-ttu-id="15adb-136">Unterstützung von Touch und Whiteboard ist noch nicht verarbeiteten für Skype Raum System v2 und H1 CY2019 hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="15adb-136">Touch and whiteboard support is in the backlog for Skype Room System v2 and will be added in H1 CY2019.</span></span>
