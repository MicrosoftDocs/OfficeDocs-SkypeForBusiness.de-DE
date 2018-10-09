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
ms.openlocfilehash: d97083b40c3a2baf926ecd61a5c9792ded6eddd5
ms.sourcegitcommit: baa4ecf69bdcf499b5b724246f3e9f45c6ca3b7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/08/2018
ms.locfileid: "25450518"
---
# <a name="migrate-lync-room-system-lrs-devices-to-skype-room-system-v2"></a><span data-ttu-id="f31b4-103">Migrieren von Lync Raum System (LRS) Geräte zu Skype Raum System v2</span><span class="sxs-lookup"><span data-stu-id="f31b4-103">Migrate Lync Room System (LRS) devices to Skype Room System v2</span></span> 
<span data-ttu-id="f31b4-104">Lync Raum System (LRS) Geräte mit Skype Raum System Version 1 (SRS v1) Software werden [Ablauf des Supports auf 9 Oktober 2018](https://support.microsoft.com/en-us/help/4043450/products-reaching-end-of-support-for-2018)erreichen.</span><span class="sxs-lookup"><span data-stu-id="f31b4-104">Lync Room System (LRS) devices with Skype Room System Version 1 (SRS v1) software will reach [end of support on October 9, 2018](https://support.microsoft.com/en-us/help/4043450/products-reaching-end-of-support-for-2018).</span></span> <span data-ttu-id="f31b4-105">Dies bedeutet, dass Skype Raum Systemsoftware v1 Produktupdates oder Hotfixes nach diesem Datum nicht abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="f31b4-105">This means Skype Room Systems v1 software will not get any product updates or fixes after this date.</span></span> <span data-ttu-id="f31b4-106">Kunden mit Lync Raum System im Geräte-Skype Raum Systemsoftware v1, sollten ihre Geräte auf Skype Raum System, Version 2 (SRS v2) zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="f31b4-106">Customers with Lync Room System devices using Skype Room System v1 software are advised to upgrade their devices to Skype Room System version 2 (SRS v2).</span></span>

<span data-ttu-id="f31b4-107">Skype Raum System Version 2 (SRS v2) Software arbeitet mit Microsoft-Teams, zusätzlich zu Skype Business Server und Online-Dienste für Besprechungen und Aufrufen von auf allen Geräten von SRS v2 unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f31b4-107">Skype Room System Version 2 (SRS v2) software works with Microsoft Teams in addition to Skype for Business Server and Online services for meetings and calling on all SRS v2 supported devices.</span></span>

<span data-ttu-id="f31b4-108">Ihre vorhandenen Geräte **können** weiterhin funktionsfähig, nach dem Ende des Skype Raum Systemsoftware v1 unterstützen.</span><span class="sxs-lookup"><span data-stu-id="f31b4-108">Your existing devices **may** continue to work after the end of Skype Room System v1 software support.</span></span> <span data-ttu-id="f31b4-109">Diese Software einen Software-Fehler, der ein Update freigeben Microsoft benötigt werden schließlich erreicht, oder Sie haben einen Fall, in dem eine vorhandene Kommunikationsprotokoll von Skype Raum System v1 Software Änderungen verwendet oder wird nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f31b4-109">This software will eventually hit a software bug that needs Microsoft to release a fix, or may have a case where an existing communication protocol used by Skype Room System v1 software changes or is no longer supported.</span></span> <span data-ttu-id="f31b4-110">Eine solche bekannte Änderung ist das Verwerfen von TLS 1.0 / 1.1 in Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="f31b4-110">One such known change is deprecation of TLS 1.0/ 1.1 in Microsoft Office 365.</span></span> <span data-ttu-id="f31b4-111">Erfahren Sie mehr über die [Vorbereitung auf das Verwerfen der TLS 1.0/1.1](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608).</span><span class="sxs-lookup"><span data-stu-id="f31b4-111">You can learn more about [Preparing for TLS 1.0/1.1 Deprecation](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608).</span></span>  

## <a name="which-devices-are-affected"></a><span data-ttu-id="f31b4-112">Welche Geräte betroffen sind?</span><span class="sxs-lookup"><span data-stu-id="f31b4-112">Which devices are affected?</span></span>
<span data-ttu-id="f31b4-113">Hier wird die Liste der Geräte, die von dieser Änderung betroffen sind:</span><span class="sxs-lookup"><span data-stu-id="f31b4-113">Here is the list of the devices that are affected by this change:</span></span>
- [<span data-ttu-id="f31b4-114">Intelligente Raum-Systeme</span><span class="sxs-lookup"><span data-stu-id="f31b4-114">SMART Room systems</span></span>](https://smartkapp.com/products/smart-room-systems)
- [<span data-ttu-id="f31b4-115">Crestron RL2</span><span class="sxs-lookup"><span data-stu-id="f31b4-115">Crestron RL2</span></span>](https://www.crestron.com/en-US/Products/Featured-Solutions/Crestron-RL-2)
- [<span data-ttu-id="f31b4-116">Polycom CX8000</span><span class="sxs-lookup"><span data-stu-id="f31b4-116">Polycom CX8000</span></span>](http://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)
- <span data-ttu-id="f31b4-117">Crestron RL</span><span class="sxs-lookup"><span data-stu-id="f31b4-117">Crestron RL</span></span>

## <a name="upgrade-options"></a><span data-ttu-id="f31b4-118">Upgrade-Optionen</span><span class="sxs-lookup"><span data-stu-id="f31b4-118">Upgrade options</span></span>
<span data-ttu-id="f31b4-119">Es gibt mehrere Optionen für das Upgrade von Lync Raum Systeme auf die nächste Generation von Skype Raum Systeme (SRS v2).</span><span class="sxs-lookup"><span data-stu-id="f31b4-119">There are multiple options for upgrading Lync Room Systems to the next generation of Skype Room Systems (SRS v2).</span></span>

### <a name="crestron-hardware-trade-in-program"></a><span data-ttu-id="f31b4-120">Crestron Hardware Rückkauf Programm</span><span class="sxs-lookup"><span data-stu-id="f31b4-120">Crestron hardware Trade-in program</span></span>
<span data-ttu-id="f31b4-121">Crestron wird ein Upgrade der [Crestron SR-System](https://www.crestron.com/en-us/products/featured-solutions/crestron-sr) oder einer gleichwertigen für alle nicht-Crestron Lync Raum System Kunden bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="f31b4-121">Crestron will provide an upgrade to the [Crestron SR system](https://www.crestron.com/en-us/products/featured-solutions/crestron-sr) or equivalent for all Non-Crestron Lync Room System customers.</span></span> <span data-ttu-id="f31b4-122">Finden Sie unter Details dieses Programms [hier](https://support.crestron.com/app/answers/answer_view/a_id/1000220) oder <!-- For details, --> [e-Mail](mailto:lrsupgrade@crestron.com) Crestron LRS Support.</span><span class="sxs-lookup"><span data-stu-id="f31b4-122">See details of this program [here](https://support.crestron.com/app/answers/answer_view/a_id/1000220) or <!-- For details, -->[email](mailto:lrsupgrade@crestron.com) Crestron LRS support.</span></span>  


### <a name="crestron-rl2-to-rl3"></a><span data-ttu-id="f31b4-123">Crestron RL2 auf RL3</span><span class="sxs-lookup"><span data-stu-id="f31b4-123">Crestron RL2 to RL3</span></span>
<span data-ttu-id="f31b4-124">Bestehende Crestron RL2 (auch als Crestron RL200 bezeichnet) Kunden können ein Aktualisierungspaket zum Aktualisieren des aktuellen RL2 RL3 Verwendung erwerben eine minimale Kosten pro Gerät.</span><span class="sxs-lookup"><span data-stu-id="f31b4-124">Existing Crestron RL2 (also referred to as Crestron RL200) customers can acquire an upgrade package to upgrade current RL2 to RL3 using a for a minimal cost per device.</span></span> <span data-ttu-id="f31b4-125">Finden Sie unter Details dieses Programms [hier](https://support.crestron.com/app/answers/answer_view/a_id/1000220) oder <!-- For details, --> [e-Mail](mailto:lrsupgrade@crestron.com) Crestron LRS Support.</span><span class="sxs-lookup"><span data-stu-id="f31b4-125">See details of this program [here](https://support.crestron.com/app/answers/answer_view/a_id/1000220) or <!-- For details, -->[email](mailto:lrsupgrade@crestron.com) Crestron LRS support.</span></span>  


### <a name="smart-room-systems-upgrade"></a><span data-ttu-id="f31b4-126">Intelligente Raum Systeme aktualisieren</span><span class="sxs-lookup"><span data-stu-id="f31b4-126">SMART Room Systems upgrade</span></span> 
<span data-ttu-id="f31b4-127">SMART LRS Kunden, ausreichend Abstand zu platzieren Crestron Hardware Rückkauf Programm arbeiten Microsoft und EFFIZIENT auch auf die Bereitstellung einer Lösung für das upgrade auf Skype Raum System v2.</span><span class="sxs-lookup"><span data-stu-id="f31b4-127">For SMART LRS customers, apart from Crestron hardware trade-in program, Microsoft and SMART are also working on providing a solution to upgrade to Skype Room System v2.</span></span> <span data-ttu-id="f31b4-128">Dieses Update wird für alle vorhandenen SMART LRS Kunden durch SMART angeboten.</span><span class="sxs-lookup"><span data-stu-id="f31b4-128">This upgrade will be offered by SMART to all existing SMART LRS customers.</span></span> <span data-ttu-id="f31b4-129">Weitere Informationen zu diesem Programm werden auf dieser Seite im Oktober 2018 bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="f31b4-129">More details of this program will be provided on this page in October 2018.</span></span> <span data-ttu-id="f31b4-130">Stellen Sie sicher, dass Sie wieder nach Updates suchen.</span><span class="sxs-lookup"><span data-stu-id="f31b4-130">Please make sure to check back for updates.</span></span>

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

## <a name="what-should-you-do"></a><span data-ttu-id="f31b4-131">Was sollten Sie tun?</span><span class="sxs-lookup"><span data-stu-id="f31b4-131">What should you do?</span></span>
<span data-ttu-id="f31b4-132">Es wird empfohlen, dass Sie Lync Raum Systemkomponenten Skype Raum Systemen V2 vor TLS 1.0/1.1 das Verwerfen von oben erwähnten Upgradeoptionen aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="f31b4-132">We recommend you plan to update Lync Room System devices to Skype Room Systems v2 before TLS 1.0/1.1 deprecation using upgrade options mentioned above.</span></span> <span data-ttu-id="f31b4-133">Darüber hinaus können Sie auch bedenken, Austauschen von vorhandenen Geräten mit neuer für SRS v2 zertifizierte Geräte.</span><span class="sxs-lookup"><span data-stu-id="f31b4-133">Additionally, you may also consider replacing existing devices with new devices certified for SRS v2.</span></span> <span data-ttu-id="f31b4-134">Einzelheiten finden Sie unter [Raum Geräte](https://aka.ms/roomdevices) und auch betrachten Sie [Skype Raum Systemen v2 Anforderungen](https://docs.microsoft.com/en-us/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).</span><span class="sxs-lookup"><span data-stu-id="f31b4-134">See [Room devices](https://aka.ms/roomdevices) for details and also take a look at [Skype Room Systems v2 requirements](https://docs.microsoft.com/en-us/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).</span></span>  

> [!NOTE]
> <span data-ttu-id="f31b4-135">Fingereingabe und Whiteboard-Funktionalität ist in Skype Raum System v2 noch nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f31b4-135">Touch and whiteboard functionality is not yet supported in Skype Room System v2.</span></span> <span data-ttu-id="f31b4-136">Unterstützung von Touch und Whiteboard ist noch nicht verarbeiteten für Skype Raum System v2 und H1 CY2019 hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="f31b4-136">Touch and whiteboard support is in the backlog for Skype Room System v2 and will be added in H1 CY2019.</span></span>

> [!NOTE]
> <span data-ttu-id="f31b4-137">Skype Raum System V2 Software unterstützt derzeit nicht 1.2 TLS-Protokoll.</span><span class="sxs-lookup"><span data-stu-id="f31b4-137">Skype Room System V2 software currently does not support TLS 1.2 protocol.</span></span> <span data-ttu-id="f31b4-138">Unterstützung für TLS 1.2 ist, die bearbeitet und wird vor dem 1/0/1.1 TLS abgeschlossen das verwerfen.</span><span class="sxs-lookup"><span data-stu-id="f31b4-138">TLS 1.2 support is being worked on and will be completed before TLS 1/0/1.1 deprecation.</span></span> <span data-ttu-id="f31b4-139">Kunden Upgradging SRS v2 wird Auswirkung von TLS 1.0/1.1 das verwerfen auf Raum-Geräten mit dem neuesten Version von SRS v2 app nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f31b4-139">Customers upgradging to SRS v2 will not see any impact of TLS 1.0/1.1 deprecation on Room devices running latest version of SRS v2 app.</span></span>
