---
title: Migrieren von Telefonen in öffentlichen Bereichen
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Telefone in öffentlichen Bereichen sind-IP-Telefone, dass die meisten häufig in einem freigegebenen Arbeitsbereich oder gemeinsamen Bereich befinden sich wie ein Floor Lobby, Küche oder Factory. Telefone in öffentlichen Bereichen müssen nicht mit einem Computer schafft Skype für Business Server Communications (UC)-Funktionalität unified verbunden sein. Nach der Migration von einer Bereitstellung zu Skype für Business Server 2019, müssen Sie auch die Kontaktobjekte der Vorversion Common Area Phone zugeordnet migrieren. Skype für Business Server-Verwaltungsshell verwenden Sie zuerst alle Kontaktobjekte zugeordnete der Vorversion Telefone in öffentlichen Bereichen abrufen, und anschließend diese Objekte in der Skype für Business Server 2019 Pool verschieben.
ms.openlocfilehash: d2d30e087d44973379d5f57dd85d137482762e5e
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25371574"
---
# <a name="migrate-common-area-phones"></a>Migrieren von Telefonen in öffentlichen Bereichen

Telefone in öffentlichen Bereichen sind-IP-Telefone, dass die meisten häufig in einem freigegebenen Arbeitsbereich oder gemeinsamen Bereich befinden sich wie ein Floor Lobby, Küche oder Factory. Telefone in öffentlichen Bereichen müssen nicht mit einem Computer schafft Skype für Business Server Communications (UC)-Funktionalität unified verbunden sein. Nach der Migration von einer Bereitstellung zu Skype für Business Server 2019, müssen Sie auch die Kontaktobjekte der Vorversion Common Area Phone zugeordnet migrieren. Skype für Business Server-Verwaltungsshell verwenden, werden Sie zuerst alle Kontaktobjekte zugeordnete der Vorversion Telefone in öffentlichen Bereichen abrufen und anschließend diese Objekte in der Skype für Business Server 2019 Pool verschieben.
  
### <a name="migrate-common-area-phones"></a>Migrieren von Telefonen in öffentlichen Bereichen

1. Öffnen Sie in der Skype für Business Server 2019 Front-End-Server Skype für Business Server-Verwaltungsshell.
    
2. Geben Sie an der Befehlszeile Folgendes ein:
    
   ```
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
   ```

3. Um zu überprüfen, ob alle Kontaktobjekte in der Skype für Business Server 2019 Pool verschoben wurden, aus der Skype für Business Server-Verwaltungsshell Folgendes ein:
    
   ```
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

    Stellen Sie sicher, dass alle Kontaktobjekte jetzt sind die Skype für Business Server 2019 Pool zugeordnet.
    

