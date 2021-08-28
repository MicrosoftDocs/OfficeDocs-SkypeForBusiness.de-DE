---
title: Migrieren von Telefonen in öffentlichen Bereichen
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Telefone für gemeinsame Bereiche sind IP-Telefone, die sich am häufigsten in einem freigegebenen Arbeitsbereich oder öffentlichen Bereich befinden, z. B. in einer Lobby, in einer Kita oder in einer Fabrik. Telefone für gemeinsame Bereiche müssen nicht mit einem Computer verbunden werden, um Skype for Business Server Unified Communications (UC)-Funktionalität bereitzustellen. Nach der Migration einer Bereitstellung zu Skype for Business Server 2019 müssen Sie auch die Kontaktobjekte migrieren, die dem älteren common Area Telefon zugeordnet sind. Mithilfe Skype for Business Server Verwaltungsshell rufen Sie zunächst alle Kontaktobjekte ab, die den älteren Telefonen für gemeinsame Bereiche zugeordnet sind, und verschieben diese Objekte dann in den Skype for Business Server 2019-Pool.
ms.openlocfilehash: dabb91925b2d5271ba2760f62dd962ed7fa7a24c
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58579529"
---
# <a name="migrate-common-area-phones"></a>Migrieren von Telefonen in öffentlichen Bereichen

Telefone für gemeinsame Bereiche sind IP-Telefone, die sich am häufigsten in einem freigegebenen Arbeitsbereich oder öffentlichen Bereich befinden, z. B. in einer Lobby, in einer Kita oder in einer Fabrik. Telefone für gemeinsame Bereiche müssen nicht mit einem Computer verbunden werden, um Skype for Business Server Unified Communications (UC)-Funktionalität bereitzustellen. Nach der Migration einer Bereitstellung zu Skype for Business Server 2019 müssen Sie auch die Kontaktobjekte migrieren, die dem älteren common Area Telefon zugeordnet sind. Mithilfe Skype for Business Server Verwaltungsshell rufen Sie zunächst alle Kontaktobjekte ab, die den älteren Telefonen für gemeinsame Bereiche zugeordnet sind, und verschieben diese Objekte dann in den Skype for Business Server 2019-Pool.
  
### <a name="migrate-common-area-phones"></a>Migrieren von Telefonen in öffentlichen Bereichen

1. Öffnen Sie auf dem Front-End-Server Skype for Business Server 2019 Skype for Business Server Verwaltungsshell.
    
2. Geben Sie an der Befehlszeile Folgendes ein:
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
   ```

3. Geben Sie aus der Skype for Business Server Verwaltungsshell Folgendes ein, um zu überprüfen, ob alle Kontaktobjekte in den Skype for Business Server 2019-Pool verschoben wurden:
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

    Stellen Sie sicher, dass alle Kontaktobjekte jetzt dem pool Skype for Business Server 2019 zugeordnet sind.
    

