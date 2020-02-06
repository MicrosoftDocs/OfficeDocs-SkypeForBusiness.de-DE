---
title: Migrieren analoger Geräte
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype for Business Server bietet Unterstützung für analoge Geräte. Die unterstützten analogen Geräte sind analoge Audio-Telefone und analoge Faxgeräte. Sie können die qualifizierten Gateways so konfigurieren, dass die Verwendung von analogen Geräten in Ihrer Skype for Business Server-Umgebung unterstützt wird. Nachdem Sie zu Skype for Business Server 2019 migriert haben, müssen Sie auch die Kontaktobjekte migrieren, die den analogen Geräten zugeordnet sind. Verwenden Sie die Skype for Business Server-Verwaltungsshell, um zunächst alle Kontaktobjekte abzurufen, die mit den Legacy-Analoggeräten verknüpft sind, und verschieben Sie diese Objekte dann in den Skype for Business Server 2019-Pool.
ms.openlocfilehash: b3b3cc1ebafa468a43043b202a01957c1cc06e87
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813593"
---
# <a name="migrate-analog-devices"></a><span data-ttu-id="86833-107">Migrieren analoger Geräte</span><span class="sxs-lookup"><span data-stu-id="86833-107">Migrate analog devices</span></span>

<span data-ttu-id="86833-108">Skype for Business Server bietet Unterstützung für analoge Geräte.</span><span class="sxs-lookup"><span data-stu-id="86833-108">Skype for Business Server provides support for analog devices.</span></span> <span data-ttu-id="86833-109">Die unterstützten analogen Geräte sind analoge Audio-Telefone und analoge Faxgeräte.</span><span class="sxs-lookup"><span data-stu-id="86833-109">Specifically, the supported analog devices are analog audio phones and analog fax machines.</span></span> <span data-ttu-id="86833-110">Sie können die qualifizierten Gateways so konfigurieren, dass die Verwendung von analogen Geräten in Ihrer Skype for Business Server-Umgebung unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="86833-110">You can configure the qualified gateways to support the use of analog devices in your Skype for Business Server environment.</span></span> <span data-ttu-id="86833-111">Nachdem Sie zu Skype for Business Server 2019 migriert haben, müssen Sie auch die Kontaktobjekte migrieren, die den analogen Geräten zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="86833-111">After you migrate to Skype for Business Server 2019, you must also migrate the contact objects associated with the analog devices.</span></span> <span data-ttu-id="86833-112">Verwenden Sie die Skype for Business Server-Verwaltungsshell, um zunächst alle Kontaktobjekte abzurufen, die mit den Legacy-Analoggeräten verknüpft sind, und verschieben Sie diese Objekte dann in den Skype for Business Server 2019-Pool.</span><span class="sxs-lookup"><span data-stu-id="86833-112">Use Skype for Business Server Management Shell to first retrieve all contact objects associated with the legacy analog devices, and then move those objects to the Skype for Business Server 2019 pool.</span></span>

### <a name="to-migrate-analog-devices"></a><span data-ttu-id="86833-113">So migrieren Sie analoge Geräte</span><span class="sxs-lookup"><span data-stu-id="86833-113">To migrate analog devices</span></span>

1. <span data-ttu-id="86833-114">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft Skype for Business Server 2019**, und klicken Sie dann auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="86833-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="86833-115">Geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="86833-115">At the command line, type:</span></span>

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. <span data-ttu-id="86833-116">Überprüfen Sie, ob alle Kontaktobjekte in den Skype for Business Server 2019-Pool verschoben wurden.</span><span class="sxs-lookup"><span data-stu-id="86833-116">Verify that all contact objects have been moved to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="86833-117">Geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="86833-117">At the command line, type:</span></span>

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. <span data-ttu-id="86833-118">Überprüfen Sie, ob alle Kontaktobjekte jetzt dem Skype for Business Server 2019-Pool zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="86833-118">Verify that all the contact objects are now associated with the Skype for Business Server 2019 pool.</span></span>


