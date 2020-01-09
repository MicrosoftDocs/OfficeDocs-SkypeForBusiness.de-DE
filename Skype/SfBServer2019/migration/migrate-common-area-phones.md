---
title: Migrieren von Telefonen für gemeinsame Bereiche
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Telefone im öffentlichen Bereich sind IP-Telefone, die sich am häufigsten in einem freigegebenen Arbeitsbereich oder in einem gemeinsamen Bereich befinden, beispielsweise in einer Lobby, einer Küche oder einem Factory-Stockwerk. Telefone im öffentlichen Bereich müssen nicht mit einem Computer verbunden sein, um die Funktionalität von Skype for Business Server Unified Communications (UC) bereitstellen zu können. Nachdem Sie eine Bereitstellung auf Skype for Business Server 2019 migriert haben, müssen Sie auch die Kontaktobjekte migrieren, die mit dem Legacy-Telefon des öffentlichen Bereichs verknüpft sind. Mit der Skype for Business Server-Verwaltungsshell rufen Sie zunächst alle Kontaktobjekte ab, die mit den Legacy-Telefonen im öffentlichen Bereich verknüpft sind, und verschieben diese Objekte dann in den Skype for Business Server 2019-Pool.
ms.openlocfilehash: f268c22f1d1132b3b5b8c1c1676e5b3a0182cf3f
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991150"
---
# <a name="migrate-common-area-phones"></a>Migrieren von Telefonen für gemeinsame Bereiche

Telefone im öffentlichen Bereich sind IP-Telefone, die sich am häufigsten in einem freigegebenen Arbeitsbereich oder in einem gemeinsamen Bereich befinden, beispielsweise in einer Lobby, einer Küche oder einem Factory-Stockwerk. Telefone im öffentlichen Bereich müssen nicht mit einem Computer verbunden sein, um die Funktionalität von Skype for Business Server Unified Communications (UC) bereitstellen zu können. Nachdem Sie eine Bereitstellung auf Skype for Business Server 2019 migriert haben, müssen Sie auch die Kontaktobjekte migrieren, die mit dem Legacy-Telefon des öffentlichen Bereichs verknüpft sind. Wenn Sie die Skype for Business Server-Verwaltungsshell verwenden, rufen Sie zunächst alle Kontaktobjekte ab, die mit den Legacy-Telefonen im allgemeinen Bereich verknüpft sind, und verschieben diese Objekte dann in den Skype for Business Server 2019-Pool.
  
### <a name="migrate-common-area-phones"></a>Migrieren von Telefonen für gemeinsame Bereiche

1. Öffnen Sie auf dem Skype for Business Server 2019-Front-End-Server die Skype for Business Server-Verwaltungsshell.
    
2. Geben Sie in der Befehlszeile Folgendes ein:
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
   ```

3. Um zu überprüfen, ob alle Kontaktobjekte in den Skype for Business Server 2019-Pool verschoben wurden, geben Sie in der Skype for Business Server-Verwaltungsshell Folgendes ein:
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

    Überprüfen Sie, ob alle Kontaktobjekte jetzt dem Skype for Business Server 2019-Pool zugeordnet sind.
    

