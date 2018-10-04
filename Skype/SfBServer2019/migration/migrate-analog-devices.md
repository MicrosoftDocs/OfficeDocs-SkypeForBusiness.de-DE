---
title: Migrieren von analogen Geräten
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype für Business Server bietet Unterstützung für analoge Geräte. Sind vor allem die unterstützten analoge Geräte analoge audio Telefone und analoge Fax-. Sie können den qualifizierten Gateways zur Unterstützung der Verwendung von analogen Geräten in Ihrer Skype für Business Server-Umgebung konfigurieren. Nach der Migration zu Skype für Business Server 2019 müssen Sie auch die Kontaktobjekte analogen Geräten zugeordnet migrieren. Verwenden Sie Skype für Business Server-Verwaltungsshell, um alle mit der Vorversionen analogen Geräten verknüpften Objekte Kontakte abrufen, und anschließend verschieben Sie diese Objekte in der Skype für Business Server 2019 Pool.
ms.openlocfilehash: ea100f4e26cc38d5eb30f881de61bf415110ca36
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25374850"
---
# <a name="migrate-analog-devices"></a><span data-ttu-id="07a12-107">Migrieren von analogen Geräten</span><span class="sxs-lookup"><span data-stu-id="07a12-107">Migrate analog devices</span></span>

<span data-ttu-id="07a12-108">Skype für Business Server bietet Unterstützung für analoge Geräte.</span><span class="sxs-lookup"><span data-stu-id="07a12-108">Skype for Business Server provides support for analog devices.</span></span> <span data-ttu-id="07a12-109">Sind vor allem die unterstützten analoge Geräte analoge audio Telefone und analoge Fax-.</span><span class="sxs-lookup"><span data-stu-id="07a12-109">Specifically, the supported analog devices are analog audio phones and analog fax machines.</span></span> <span data-ttu-id="07a12-110">Sie können den qualifizierten Gateways zur Unterstützung der Verwendung von analogen Geräten in Ihrer Skype für Business Server-Umgebung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="07a12-110">You can configure the qualified gateways to support the use of analog devices in your Skype for Business Server environment.</span></span> <span data-ttu-id="07a12-111">Nach der Migration zu Skype für Business Server 2019 müssen Sie auch die Kontaktobjekte analogen Geräten zugeordnet migrieren.</span><span class="sxs-lookup"><span data-stu-id="07a12-111">After you migrate to Skype for Business Server 2019, you must also migrate the contact objects associated with the analog devices.</span></span> <span data-ttu-id="07a12-112">Verwenden Sie Skype für Business Server-Verwaltungsshell, um alle mit der Vorversionen analogen Geräten verknüpften Objekte Kontakte abrufen, und anschließend verschieben Sie diese Objekte in der Skype für Business Server 2019 Pool.</span><span class="sxs-lookup"><span data-stu-id="07a12-112">Use Skype for Business Server Management Shell to first retrieve all contact objects associated with the legacy analog devices, and then move those objects to the Skype for Business Server 2019 pool.</span></span>

### <a name="to-migrate-analog-devices"></a><span data-ttu-id="07a12-113">Migrieren von analogen Geräten</span><span class="sxs-lookup"><span data-stu-id="07a12-113">To migrate analog devices</span></span>

1. <span data-ttu-id="07a12-114">Starten Sie die Skype für Business Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft Skype für Business Server 2019**, und klicken Sie dann auf **Skype für Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="07a12-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="07a12-115">Geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="07a12-115">At the command line, type:</span></span>

   ```
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. <span data-ttu-id="07a12-116">Stellen Sie sicher, dass alle Kontaktobjekte in der Skype für Business Server 2019 Pool verschoben wurden.</span><span class="sxs-lookup"><span data-stu-id="07a12-116">Verify that all contact objects have been moved to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="07a12-117">Geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="07a12-117">At the command line, type:</span></span>

   ```
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. <span data-ttu-id="07a12-118">Stellen Sie sicher, dass die Kontaktobjekte jetzt sind die Skype für Business Server 2019 Pool zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="07a12-118">Verify that all the contact objects are now associated with the Skype for Business Server 2019 pool.</span></span>


