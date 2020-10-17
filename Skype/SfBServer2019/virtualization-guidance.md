---
title: 'Unterstützung der Virtualisierung für Skype for Business Server 2019 '
ms.reviewer: corbinm
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 06/04/2020
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Zusammenfassung: erfahren Sie mehr über die Unterstützung der Virtualisierung für Skype for Business Server 2019.'
ms.openlocfilehash: edced9b0f884cbf76b224c9049cf3498c8f8b45c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509032"
---
# <a name="virtualization-support-for-skype-for-business-server-2019"></a><span data-ttu-id="d37e8-103">Unterstützung der Virtualisierung für Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="d37e8-103">Virtualization support for Skype for Business Server 2019</span></span>

<span data-ttu-id="d37e8-104">Skype for Business Server 2019 wird für die Virtualisierung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d37e8-104">Skype for Business Server 2019 is supported on virtualization.</span></span>

<span data-ttu-id="d37e8-105">Während die Virtualisierung unterstützt wird, gibt es einige wichtige Punkte, die Sie beachten sollten:</span><span class="sxs-lookup"><span data-stu-id="d37e8-105">While virtualization is supported, there are some key points to remember:</span></span>

- <span data-ttu-id="d37e8-106">Halten Sie ein 1:1-Verhältnis der virtuellen CPU mit der physischen CPU aufrecht.</span><span class="sxs-lookup"><span data-stu-id="d37e8-106">Maintain a 1:1 ratio of virtual CPU to physical CPU.</span></span>
- <span data-ttu-id="d37e8-107">Bewegen Sie einen gastserver nicht, während er in Betrieb ist.</span><span class="sxs-lookup"><span data-stu-id="d37e8-107">Don't move a guest server while it's operating.</span></span>
- <span data-ttu-id="d37e8-108">Die Migration eines Live-Systems und die Portabilität eines virtuellen Computers werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d37e8-108">Migration of a live system and portability of a virtual machine aren't supported.</span></span>
- <span data-ttu-id="d37e8-109">Deaktivieren Sie Hyper-Threading auf allen Hosts.</span><span class="sxs-lookup"><span data-stu-id="d37e8-109">Disable hyper-threading on all hosts.</span></span>
- <span data-ttu-id="d37e8-110">Konfigurieren Sie keinen dynamischen Arbeitsspeicher auf Hostservern.</span><span class="sxs-lookup"><span data-stu-id="d37e8-110">Don't configure dynamic memory on host servers.</span></span>
- <span data-ttu-id="d37e8-111">Verwenden Sie feste oder Pass-Through-Datenträger anstelle von dynamischen Datenträgern.</span><span class="sxs-lookup"><span data-stu-id="d37e8-111">Use fixed or pass-through disks rather than dynamic disks.</span></span>
- <span data-ttu-id="d37e8-112">Ermöglichen Sie den Overhead von 6-10 Prozent für Hypervisoren über das hinaus, was der virtuelle Gast benötigt.</span><span class="sxs-lookup"><span data-stu-id="d37e8-112">Allow for 6-10 percent overhead for hypervisors beyond what the virtual guest requires.</span></span>

## <a name="supported-hypervisors"></a><span data-ttu-id="d37e8-113">Unterstützte Hypervisoren</span><span class="sxs-lookup"><span data-stu-id="d37e8-113">Supported hypervisors</span></span>

<span data-ttu-id="d37e8-114">SFB Server 2019 wird unter Windows Server 2016 und Windows Server 2019 unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d37e8-114">SfB Server 2019 is supported on Windows Server 2016 and Windows Server 2019.</span></span>

<span data-ttu-id="d37e8-115">Für Hypervisoren von Drittanbietern benötigen Sie einen Hypervisor, der das Server Virtualization Validation Program (SVVP)-Test für das entsprechende Betriebssystem bestanden hat.</span><span class="sxs-lookup"><span data-stu-id="d37e8-115">For third-party hypervisors, you need a hypervisor that has passed the Server Virtualization Validation Program (SVVP) testing for the relevant OS.</span></span>

- <span data-ttu-id="d37e8-116">Siehe die [Versionen von Windows Server 2016](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25) in der SVVP-Liste.</span><span class="sxs-lookup"><span data-stu-id="d37e8-116">See the [Windows Server 2016 versions](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25) in the SVVP list.</span></span>
- <span data-ttu-id="d37e8-117">Siehe die [Versionen von Windows Server 2019](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25) in der SVVP-Liste.</span><span class="sxs-lookup"><span data-stu-id="d37e8-117">See the [Windows Server 2019 versions](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25) in the SVVP list.</span></span>

## <a name="stress-and-performance-tool"></a><span data-ttu-id="d37e8-118">Belastungs-und Leistungstool</span><span class="sxs-lookup"><span data-stu-id="d37e8-118">Stress and performance tool</span></span>

<span data-ttu-id="d37e8-119">Das Skype for Business Server 2019 Stress and Performance Tool enthält Tools, die die Kapazitätsplanung für Skype for Business Server 2019 vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="d37e8-119">The Skype for Business Server 2019 Stress and Performance Tool includes tools that simplify capacity planning for Skype for Business Server 2019.</span></span> <span data-ttu-id="d37e8-120">Das Skype for Business Server 2019 Stress and Performance Tool hilft Ihnen:</span><span class="sxs-lookup"><span data-stu-id="d37e8-120">The Skype for Business Server 2019 Stress and Performance Tool will help you to:</span></span>

- <span data-ttu-id="d37e8-121">Vereinfachung der Hardwareplanung für Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="d37e8-121">Simplify your hardware planning for Skype for Business Server 2019</span></span>
- <span data-ttu-id="d37e8-122">Vermehrte Kenntnisse und bewährte Methoden für die Leistungsoptimierung</span><span class="sxs-lookup"><span data-stu-id="d37e8-122">Provide you with increased knowledge and best practices for performance tuning</span></span>
- <span data-ttu-id="d37e8-123">Messen der Leistung Ihrer geplanten Skype for Business Server 2019-Bereitstellungen</span><span class="sxs-lookup"><span data-stu-id="d37e8-123">Measure the performance of your intended Skype for Business Server 2019 deployments</span></span>
 
<span data-ttu-id="d37e8-124">Sie können das Tool [hier](https://www.microsoft.com/download/details.aspx?id=101447)herunterladen.</span><span class="sxs-lookup"><span data-stu-id="d37e8-124">You can download the tool from [here](https://www.microsoft.com/download/details.aspx?id=101447).</span></span>
