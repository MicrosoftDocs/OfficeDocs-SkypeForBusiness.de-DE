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
localization_priority: Normal
description: Telefone für gemeinsame Bereiche sind IP-Telefone, die sich am häufigsten in einem freigegebenen Arbeitsbereich oder einem gemeinsamen Bereich befinden, z. B. in einer Lobby, in einer Kita oder in einer Fabrik. Telefone für gemeinsame Bereiche müssen nicht mit einem Computer verbunden werden, um Skype for Business Server Unified Communications (UC)-Funktionalität bereitzustellen. Nach der Migration einer Bereitstellung zu Skype for Business Server 2019 müssen Sie auch die Kontaktobjekte migrieren, die dem älteren Common Area Telefon zugeordnet sind. Mit Skype for Business Server Verwaltungsshell rufen Sie zunächst alle Kontaktobjekte ab, die den älteren Telefonen für gemeinsame Bereiche zugeordnet sind, und verschieben diese Objekte dann in den Skype for Business Server 2019-Pool.
ms.openlocfilehash: 808e874216fac97b01face6efa7aae00e269b74ee0f009b106f872a33a6d6261
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54340431"
---
# <a name="migrate-common-area-phones"></a>Migrieren von Telefonen in öffentlichen Bereichen

Telefone für gemeinsame Bereiche sind IP-Telefone, die sich am häufigsten in einem freigegebenen Arbeitsbereich oder einem gemeinsamen Bereich befinden, z. B. in einer Lobby, in einer Kita oder in einer Fabrik. Telefone für gemeinsame Bereiche müssen nicht mit einem Computer verbunden werden, um Skype for Business Server Unified Communications (UC)-Funktionalität bereitzustellen. Nach der Migration einer Bereitstellung zu Skype for Business Server 2019 müssen Sie auch die Kontaktobjekte migrieren, die dem älteren Common Area Telefon zugeordnet sind. Mithilfe Skype for Business Server Verwaltungsshell rufen Sie zunächst alle Kontaktobjekte ab, die den älteren Telefonen für gemeinsame Bereiche zugeordnet sind, und verschieben diese Objekte dann in den Skype for Business Server 2019-Pool.
  
### <a name="migrate-common-area-phones"></a>Migrieren von Telefonen in öffentlichen Bereichen

1. Öffnen Sie auf dem Skype for Business Server 2019-Front-End-Server Skype for Business Server Verwaltungsshell.
    
2. Geben Sie an der Befehlszeile Folgendes ein:
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
   ```

3. Um zu überprüfen, ob alle Kontaktobjekte in den Skype for Business Server 2019-Pool verschoben wurden, geben Sie von der Skype for Business Server Verwaltungsshell Folgendes ein:
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

    Stellen Sie sicher, dass alle Kontaktobjekte jetzt dem Skype for Business Server 2019-Pool zugeordnet sind.
    

