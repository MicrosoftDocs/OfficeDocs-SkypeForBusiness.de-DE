---
title: Migrieren von Telefonen für gemeinsame Bereiche
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
description: Telefone im öffentlichen Bereich sind IP-Telefone, die sich am häufigsten in einem freigegebenen Arbeitsbereich oder in einem gemeinsamen Bereich befinden, beispielsweise in einer Lobby, einer Küche oder einem Factory-Stockwerk. Telefone im öffentlichen Bereich müssen nicht mit einem Computer verbunden sein, um die Funktionalität von Skype for Business Server Unified Communications (UC) bereitstellen zu können. Nachdem Sie eine Bereitstellung auf Skype for Business Server 2019 migriert haben, müssen Sie auch die Kontaktobjekte migrieren, die mit dem Legacy-Telefon des öffentlichen Bereichs verknüpft sind. Mit der Skype for Business Server-Verwaltungsshell rufen Sie zunächst alle Kontaktobjekte ab, die mit den Legacy-Telefonen im öffentlichen Bereich verknüpft sind, und verschieben diese Objekte dann in den Skype for Business Server 2019-Pool.
ms.openlocfilehash: 5110f91788d09f644e20680f91f1cbafe146bdd6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813563"
---
# <a name="migrate-common-area-phones"></a><span data-ttu-id="f6426-106">Migrieren von Telefonen für gemeinsame Bereiche</span><span class="sxs-lookup"><span data-stu-id="f6426-106">Migrate Common Area Phones</span></span>

<span data-ttu-id="f6426-107">Telefone im öffentlichen Bereich sind IP-Telefone, die sich am häufigsten in einem freigegebenen Arbeitsbereich oder in einem gemeinsamen Bereich befinden, beispielsweise in einer Lobby, einer Küche oder einem Factory-Stockwerk.</span><span class="sxs-lookup"><span data-stu-id="f6426-107">Common Area Phones are IP phones that most often reside in a shared workspace or common area, like a lobby, kitchen, or factory floor.</span></span> <span data-ttu-id="f6426-108">Telefone im öffentlichen Bereich müssen nicht mit einem Computer verbunden sein, um die Funktionalität von Skype for Business Server Unified Communications (UC) bereitstellen zu können.</span><span class="sxs-lookup"><span data-stu-id="f6426-108">Common Area Phones do not need to be connected to a computer to provide Skype for Business Server unified communications (UC) functionality.</span></span> <span data-ttu-id="f6426-109">Nachdem Sie eine Bereitstellung auf Skype for Business Server 2019 migriert haben, müssen Sie auch die Kontaktobjekte migrieren, die mit dem Legacy-Telefon des öffentlichen Bereichs verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="f6426-109">After migrating a deployment to Skype for Business Server 2019, you must also migrate the contact objects associated with the legacy Common Area Phone.</span></span> <span data-ttu-id="f6426-110">Wenn Sie die Skype for Business Server-Verwaltungsshell verwenden, rufen Sie zunächst alle Kontaktobjekte ab, die mit den Legacy-Telefonen im allgemeinen Bereich verknüpft sind, und verschieben diese Objekte dann in den Skype for Business Server 2019-Pool.</span><span class="sxs-lookup"><span data-stu-id="f6426-110">Using Skype for Business Server Management Shell, you will first retrieve all contact objects associated with the legacy Common Area Phones, and then move those objects to the Skype for Business Server 2019 pool.</span></span>
  
### <a name="migrate-common-area-phones"></a><span data-ttu-id="f6426-111">Migrieren von Telefonen für gemeinsame Bereiche</span><span class="sxs-lookup"><span data-stu-id="f6426-111">Migrate Common Area Phones</span></span>

1. <span data-ttu-id="f6426-112">Öffnen Sie auf dem Skype for Business Server 2019-Front-End-Server die Skype for Business Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="f6426-112">From the Skype for Business Server 2019 Front End server, open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="f6426-113">Geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="f6426-113">From the command line, type the following:</span></span>
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
   ```

3. <span data-ttu-id="f6426-114">Um zu überprüfen, ob alle Kontaktobjekte in den Skype for Business Server 2019-Pool verschoben wurden, geben Sie in der Skype for Business Server-Verwaltungsshell Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="f6426-114">To verify that all contact objects have been moved to the Skype for Business Server 2019 pool, from the Skype for Business Server Management Shell type the following:</span></span>
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

    <span data-ttu-id="f6426-115">Überprüfen Sie, ob alle Kontaktobjekte jetzt dem Skype for Business Server 2019-Pool zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="f6426-115">Verify that all contact objects are now associated with the Skype for Business Server 2019 pool.</span></span>
    

