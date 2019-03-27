---
title: Migrieren von Telefonen für gemeinsame Bereiche
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Telefone in öffentlichen Bereichen sind-IP-Telefone, dass die meisten häufig in einem freigegebenen Arbeitsbereich oder gemeinsamen Bereich befinden sich wie ein Floor Lobby, Küche oder Factory. Telefone in öffentlichen Bereichen müssen nicht mit einem Computer schafft Skype für Business Server Communications (UC)-Funktionalität unified verbunden sein. Nach der Migration von einer Bereitstellung zu Skype für Business Server 2019, müssen Sie auch die Kontaktobjekte der Vorversion Common Area Phone zugeordnet migrieren. Skype für Business Server-Verwaltungsshell verwenden Sie zuerst alle Kontaktobjekte zugeordnete der Vorversion Telefone in öffentlichen Bereichen abrufen, und anschließend diese Objekte in der Skype für Business Server 2019 Pool verschieben.
ms.openlocfilehash: d17e15224a9124eaf3e9fd6696e6ecd9265044eb
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30887267"
---
# <a name="migrate-common-area-phones"></a><span data-ttu-id="52fa2-106">Migrieren von Telefonen für gemeinsame Bereiche</span><span class="sxs-lookup"><span data-stu-id="52fa2-106">Migrate Common Area Phones</span></span>

<span data-ttu-id="52fa2-107">Telefone in öffentlichen Bereichen sind-IP-Telefone, dass die meisten häufig in einem freigegebenen Arbeitsbereich oder gemeinsamen Bereich befinden sich wie ein Floor Lobby, Küche oder Factory.</span><span class="sxs-lookup"><span data-stu-id="52fa2-107">Common Area Phones are IP phones that most often reside in a shared workspace or common area, like a lobby, kitchen, or factory floor.</span></span> <span data-ttu-id="52fa2-108">Telefone in öffentlichen Bereichen müssen nicht mit einem Computer schafft Skype für Business Server Communications (UC)-Funktionalität unified verbunden sein.</span><span class="sxs-lookup"><span data-stu-id="52fa2-108">Common Area Phones do not need to be connected to a computer to provide Skype for Business Server unified communications (UC) functionality.</span></span> <span data-ttu-id="52fa2-109">Nach der Migration von einer Bereitstellung zu Skype für Business Server 2019, müssen Sie auch die Kontaktobjekte der Vorversion Common Area Phone zugeordnet migrieren.</span><span class="sxs-lookup"><span data-stu-id="52fa2-109">After migrating a deployment to Skype for Business Server 2019, you must also migrate the contact objects associated with the legacy Common Area Phone.</span></span> <span data-ttu-id="52fa2-110">Skype für Business Server-Verwaltungsshell verwenden, werden Sie zuerst alle Kontaktobjekte zugeordnete der Vorversion Telefone in öffentlichen Bereichen abrufen und anschließend diese Objekte in der Skype für Business Server 2019 Pool verschieben.</span><span class="sxs-lookup"><span data-stu-id="52fa2-110">Using Skype for Business Server Management Shell, you will first retrieve all contact objects associated with the legacy Common Area Phones, and then move those objects to the Skype for Business Server 2019 pool.</span></span>
  
### <a name="migrate-common-area-phones"></a><span data-ttu-id="52fa2-111">Migrieren von Telefonen für gemeinsame Bereiche</span><span class="sxs-lookup"><span data-stu-id="52fa2-111">Migrate Common Area Phones</span></span>

1. <span data-ttu-id="52fa2-112">Öffnen Sie in der Skype für Business Server 2019 Front-End-Server Skype für Business Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="52fa2-112">From the Skype for Business Server 2019 Front End server, open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="52fa2-113">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="52fa2-113">From the command line, type the following:</span></span>
    
   ```
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
   ```

3. <span data-ttu-id="52fa2-114">Um zu überprüfen, ob alle Kontaktobjekte in der Skype für Business Server 2019 Pool verschoben wurden, aus der Skype für Business Server-Verwaltungsshell Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="52fa2-114">To verify that all contact objects have been moved to the Skype for Business Server 2019 pool, from the Skype for Business Server Management Shell type the following:</span></span>
    
   ```
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

    <span data-ttu-id="52fa2-115">Stellen Sie sicher, dass alle Kontaktobjekte jetzt sind die Skype für Business Server 2019 Pool zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="52fa2-115">Verify that all contact objects are now associated with the Skype for Business Server 2019 pool.</span></span>
    

