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
# <a name="migrate-common-area-phones"></a>Migireren von Telefonen für gemeinsame Bereiche

Telefone in öffentlichen Bereichen sind IP-Telefone, die sich am häufigsten in einem gemeinsamen Arbeitsbereich oder in einem gemeinsamen Bereich befinden, wie beispielsweise eine Lobby, eine Küche oder ein Factory Floor. Telefone für gemeinsame Bereiche müssen nicht mit einem Computer verbunden sein, um eine Skype for Business Server Unified Communications (UC)-Funktionalität bereitzustellen. Nachdem Sie eine Bereitstellung auf Skype for Business Server 2019 migriert haben, müssen Sie auch die Kontaktobjekte migrieren, die dem Legacy-Telefon für gemeinsame Bereiche zugeordnet sind. Mit Skype for Business Server-Verwaltungsshell rufen Sie zunächst alle Kontaktobjekte ab, die den Legacy-Telefonen für gemeinsame Bereiche zugeordnet sind, und dann diese Objekte in den Skype for Business Server 2019-Pool zu migrieren.
  
### <a name="migrate-common-area-phones"></a>Migireren von Telefonen für gemeinsame Bereiche

1. Öffnen Sie auf dem Skype for Business Server 2019-Front-End-Server Skype for Business Server Verwaltungsshell.
    
2. Geben Sie an der Befehlszeile Folgendes ein:
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
   ```

3. Um zu überprüfen, ob alle Kontaktobjekte in den Pool Skype for Business Server 2019 verschoben wurden, geben Sie in der Skype for Business Server Verwaltungsshell Folgendes ein:
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

    Stellen Sie sicher, dass alle Contact-Objekte nun dem Pool Skype for Business Server 2019 zugeordnet sind.
    

