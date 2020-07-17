---
title: Migrieren analoger Geräte
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype for Business Server bietet Unterstützung für analoge Geräte. Zu den unterstützten analogen Geräten gehören insbesondere analoge Telefone und Faxgeräte. Sie können die qualifizierten Gateways so konfigurieren, dass die Verwendung von analogen Geräten in Ihrer Skype for Business Server Umgebung unterstützt wird. Nachdem Sie zu Skype for Business Server 2019 migriert haben, müssen Sie auch die Kontaktobjekte migrieren, die den analogen Geräten zugeordnet sind. Verwenden Sie Skype for Business Server Verwaltungsshell, um zuerst alle Contact-Objekte abzurufen, die den älteren analogen Geräten zugeordnet sind, und dann diese Objekte in den Skype for Business Server 2019-Pool zu migrieren.
ms.openlocfilehash: 7b90a52486725c2cf30856dc643660d569d698e2
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752827"
---
# <a name="migrate-analog-devices"></a><span data-ttu-id="2e80f-107">Migrieren analoger Geräte</span><span class="sxs-lookup"><span data-stu-id="2e80f-107">Migrate analog devices</span></span>

<span data-ttu-id="2e80f-108">Skype for Business Server bietet Unterstützung für analoge Geräte.</span><span class="sxs-lookup"><span data-stu-id="2e80f-108">Skype for Business Server provides support for analog devices.</span></span> <span data-ttu-id="2e80f-109">Zu den unterstützten analogen Geräten gehören insbesondere analoge Telefone und Faxgeräte.</span><span class="sxs-lookup"><span data-stu-id="2e80f-109">Specifically, the supported analog devices are analog audio phones and analog fax machines.</span></span> <span data-ttu-id="2e80f-110">Sie können die qualifizierten Gateways so konfigurieren, dass die Verwendung von analogen Geräten in Ihrer Skype for Business Server Umgebung unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="2e80f-110">You can configure the qualified gateways to support the use of analog devices in your Skype for Business Server environment.</span></span> <span data-ttu-id="2e80f-111">Nachdem Sie zu Skype for Business Server 2019 migriert haben, müssen Sie auch die Kontaktobjekte migrieren, die den analogen Geräten zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="2e80f-111">After you migrate to Skype for Business Server 2019, you must also migrate the contact objects associated with the analog devices.</span></span> <span data-ttu-id="2e80f-112">Verwenden Sie Skype for Business Server Verwaltungsshell, um zuerst alle Contact-Objekte abzurufen, die den älteren analogen Geräten zugeordnet sind, und dann diese Objekte in den Skype for Business Server 2019-Pool zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="2e80f-112">Use Skype for Business Server Management Shell to first retrieve all contact objects associated with the legacy analog devices, and then move those objects to the Skype for Business Server 2019 pool.</span></span>

### <a name="to-migrate-analog-devices"></a><span data-ttu-id="2e80f-113">So migrieren Sie analoge Geräte</span><span class="sxs-lookup"><span data-stu-id="2e80f-113">To migrate analog devices</span></span>

1. <span data-ttu-id="2e80f-114">Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft Skype for Business Server 2019**, und klicken Sie dann auf **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="2e80f-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="2e80f-115">Geben Sie in die Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="2e80f-115">At the command line, type:</span></span>

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. <span data-ttu-id="2e80f-116">Stellen Sie sicher, dass alle Kontaktobjekte in den Pool Skype for Business Server 2019 verschoben wurden.</span><span class="sxs-lookup"><span data-stu-id="2e80f-116">Verify that all contact objects have been moved to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="2e80f-117">Geben Sie in die Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="2e80f-117">At the command line, type:</span></span>

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. <span data-ttu-id="2e80f-118">Stellen Sie sicher, dass alle Contact-Objekte nun dem Pool Skype for Business Server 2019 zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="2e80f-118">Verify that all the contact objects are now associated with the Skype for Business Server 2019 pool.</span></span>


