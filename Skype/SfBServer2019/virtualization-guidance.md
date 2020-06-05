---
title: 'Unterstützung der Virtualisierung für Skype for Business Server 2019 '
ms.reviewer: corbinm
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 06/04/20
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Zusammenfassung: erfahren Sie mehr über die Unterstützung der Virtualisierung für Skype for Business Server 2019.'
ms.openlocfilehash: a01f529d80e84df3f7ca844696738b079f78df26
ms.sourcegitcommit: f9db7effbb1e56484686afe4724cc3b73380166d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "44565954"
---
# <a name="virtualization-support-for-skype-for-business-server-2019"></a><span data-ttu-id="cd83c-103">Unterstützung der Virtualisierung für Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="cd83c-103">Virtualization support for Skype for Business Server 2019</span></span>

<span data-ttu-id="cd83c-104">Skype for Business Server 2019 wird für die Virtualisierung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="cd83c-104">Skype for Business Server 2019 is supported on virtualization.</span></span>

<span data-ttu-id="cd83c-105">Während die Virtualisierung unterstützt wird, gibt es einige wichtige Punkte, die Sie beachten sollten:</span><span class="sxs-lookup"><span data-stu-id="cd83c-105">While virtualization is supported, there are some key points to remember:</span></span>

- <span data-ttu-id="cd83c-106">Halten Sie ein 1:1-Verhältnis der virtuellen CPU mit der physischen CPU aufrecht.</span><span class="sxs-lookup"><span data-stu-id="cd83c-106">Maintain a 1:1 ratio of virtual CPU to physical CPU.</span></span>
- <span data-ttu-id="cd83c-107">Bewegen Sie einen gastserver nicht, während er in Betrieb ist.</span><span class="sxs-lookup"><span data-stu-id="cd83c-107">Don't move a guest server while it's operating.</span></span>
- <span data-ttu-id="cd83c-108">Die Migration eines Live-Systems und die Portabilität eines virtuellen Computers werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="cd83c-108">Migration of a live system and portability of a virtual machine aren't supported.</span></span>
- <span data-ttu-id="cd83c-109">Deaktivieren Sie Hyper-Threading auf allen Hosts.</span><span class="sxs-lookup"><span data-stu-id="cd83c-109">Disable hyper-threading on all hosts.</span></span>
- <span data-ttu-id="cd83c-110">Konfigurieren Sie keinen dynamischen Arbeitsspeicher auf Hostservern.</span><span class="sxs-lookup"><span data-stu-id="cd83c-110">Don't configure dynamic memory on host servers.</span></span>
- <span data-ttu-id="cd83c-111">Verwenden Sie feste oder Pass-Through-Datenträger anstelle von dynamischen Datenträgern.</span><span class="sxs-lookup"><span data-stu-id="cd83c-111">Use fixed or pass-through disks rather than dynamic disks.</span></span>
- <span data-ttu-id="cd83c-112">Ermöglichen Sie den Overhead von 6-10 Prozent für Hypervisoren über das hinaus, was der virtuelle Gast benötigt.</span><span class="sxs-lookup"><span data-stu-id="cd83c-112">Allow for 6-10 percent overhead for hypervisors beyond what the virtual guest requires.</span></span>

## <a name="supported-hypervisors"></a><span data-ttu-id="cd83c-113">Unterstützte Hypervisoren</span><span class="sxs-lookup"><span data-stu-id="cd83c-113">Supported hypervisors</span></span>

<span data-ttu-id="cd83c-114">SFB Server 2019 wird unter Windows Server 2016 und Windows Server 2019 unterstützt.</span><span class="sxs-lookup"><span data-stu-id="cd83c-114">SfB Server 2019 is supported on Windows Server 2016 and Windows Server 2019.</span></span>

<span data-ttu-id="cd83c-115">Für Hypervisoren von Drittanbietern benötigen Sie einen Hypervisor, der das Server Virtualization Validation Program (SVVP)-Test für das entsprechende Betriebssystem bestanden hat.</span><span class="sxs-lookup"><span data-stu-id="cd83c-115">For third-party hypervisors, you need a hypervisor that has passed the Server Virtualization Validation Program (SVVP) testing for the relevant OS.</span></span>

- <span data-ttu-id="cd83c-116">Siehe die [Versionen von Windows Server 2016](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25) in der SVVP-Liste.</span><span class="sxs-lookup"><span data-stu-id="cd83c-116">See the [Windows Server 2016 versions](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25) in the SVVP list.</span></span>
- <span data-ttu-id="cd83c-117">Siehe die [Versionen von Windows Server 2019](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25) in der SVVP-Liste.</span><span class="sxs-lookup"><span data-stu-id="cd83c-117">See the [Windows Server 2019 versions](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25) in the SVVP list.</span></span>
