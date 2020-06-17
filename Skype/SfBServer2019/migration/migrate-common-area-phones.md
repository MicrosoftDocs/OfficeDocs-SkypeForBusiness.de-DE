---
title: Migireren von Telefonen für gemeinsame Bereiche
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
description: Telefone in öffentlichen Bereichen sind IP-Telefone, die sich am häufigsten in einem gemeinsamen Arbeitsbereich oder in einem gemeinsamen Bereich befinden, wie beispielsweise eine Lobby, eine Küche oder ein Factory Floor. Telefone für gemeinsame Bereiche müssen nicht mit einem Computer verbunden sein, um eine Skype for Business Server Unified Communications (UC)-Funktionalität bereitzustellen. Nachdem Sie eine Bereitstellung auf Skype for Business Server 2019 migriert haben, müssen Sie auch die Kontaktobjekte migrieren, die dem Legacy-Telefon für gemeinsame Bereiche zugeordnet sind. Mit Skype for Business Server Verwaltungsshell rufen Sie zunächst alle Contact-Objekte ab, die den Legacy-Telefonen für gemeinsame Bereiche zugeordnet sind, und dann diese Objekte in den Skype for Business Server 2019-Pool zu migrieren.
ms.openlocfilehash: b9cf5a32614ac41ac3c82773af4f37907c16e6f2
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752707"
---
# <a name="migrate-common-area-phones"></a><span data-ttu-id="9fb58-106">Migireren von Telefonen für gemeinsame Bereiche</span><span class="sxs-lookup"><span data-stu-id="9fb58-106">Migrate Common Area Phones</span></span>

<span data-ttu-id="9fb58-107">Telefone in öffentlichen Bereichen sind IP-Telefone, die sich am häufigsten in einem gemeinsamen Arbeitsbereich oder in einem gemeinsamen Bereich befinden, wie beispielsweise eine Lobby, eine Küche oder ein Factory Floor.</span><span class="sxs-lookup"><span data-stu-id="9fb58-107">Common Area Phones are IP phones that most often reside in a shared workspace or common area, like a lobby, kitchen, or factory floor.</span></span> <span data-ttu-id="9fb58-108">Telefone für gemeinsame Bereiche müssen nicht mit einem Computer verbunden sein, um eine Skype for Business Server Unified Communications (UC)-Funktionalität bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="9fb58-108">Common Area Phones do not need to be connected to a computer to provide Skype for Business Server unified communications (UC) functionality.</span></span> <span data-ttu-id="9fb58-109">Nachdem Sie eine Bereitstellung auf Skype for Business Server 2019 migriert haben, müssen Sie auch die Kontaktobjekte migrieren, die dem Legacy-Telefon für gemeinsame Bereiche zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="9fb58-109">After migrating a deployment to Skype for Business Server 2019, you must also migrate the contact objects associated with the legacy Common Area Phone.</span></span> <span data-ttu-id="9fb58-110">Mit Skype for Business Server-Verwaltungsshell rufen Sie zunächst alle Kontaktobjekte ab, die den Legacy-Telefonen für gemeinsame Bereiche zugeordnet sind, und dann diese Objekte in den Skype for Business Server 2019-Pool zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="9fb58-110">Using Skype for Business Server Management Shell, you will first retrieve all contact objects associated with the legacy Common Area Phones, and then move those objects to the Skype for Business Server 2019 pool.</span></span>
  
### <a name="migrate-common-area-phones"></a><span data-ttu-id="9fb58-111">Migireren von Telefonen für gemeinsame Bereiche</span><span class="sxs-lookup"><span data-stu-id="9fb58-111">Migrate Common Area Phones</span></span>

1. <span data-ttu-id="9fb58-112">Öffnen Sie auf dem Skype for Business Server 2019-Front-End-Server Skype for Business Server Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="9fb58-112">From the Skype for Business Server 2019 Front End server, open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="9fb58-113">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="9fb58-113">From the command line, type the following:</span></span>
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
   ```

3. <span data-ttu-id="9fb58-114">Um zu überprüfen, ob alle Kontaktobjekte in den Pool Skype for Business Server 2019 verschoben wurden, geben Sie in der Skype for Business Server Verwaltungsshell Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="9fb58-114">To verify that all contact objects have been moved to the Skype for Business Server 2019 pool, from the Skype for Business Server Management Shell type the following:</span></span>
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

    <span data-ttu-id="9fb58-115">Stellen Sie sicher, dass alle Contact-Objekte nun dem Pool Skype for Business Server 2019 zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="9fb58-115">Verify that all contact objects are now associated with the Skype for Business Server 2019 pool.</span></span>
    

