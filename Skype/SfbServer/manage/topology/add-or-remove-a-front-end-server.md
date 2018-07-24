---
title: Hinzufügen oder Entfernen eines Front-End-Servers in Skype für Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Zusammenfassung: Informationen Sie zum Hinzufügen oder Entfernen von Front-End-Servern in Skype für Business Server.'
ms.openlocfilehash: 07f23f3dfb913a353a72ac855915d4001ed02f24
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "21018783"
---
# <a name="add-or-remove-a-front-end-server-in-skype-for-business-server"></a>Hinzufügen oder Entfernen eines Front-End-Servers in Skype für Business Server
 
**Zusammenfassung:** Informationen Sie zum Hinzufügen oder Entfernen von Front-End-Servern in Skype für Business Server.
  
Wenn Sie einen Front-End-Server zu einem Pool hinzufügen oder eines Front-End-Servers aus einem Pool entfernen, müssen Sie dann den Pool neu starten. 
  
> [!IMPORTANT]
> Wenn Sie einen Server zum Pool in Ihrer Topologie hinzufügen oder daraus entfernen und dann die aktualisierte Topologie veröffentlichen, werden alle Server im Pool gleichzeitig gestartet. Während die Server neu gestartet werden, ist der Pool offline, wodurch der Dienst für die mit diesem Pool verbundenen Benutzer unterbrochen wird. Um Dienstunterbrechungen zu vermeiden, planen Sie die Veröffentlichung der Topologie mit dem neuen Server im Pool außerhalb der Geschäftszeiten. 
  
Sie können das folgende Verfahren beim Hinzufügen oder Entfernen eines Front-End-Servers.
  
> [!NOTE]
> Wenn Sie neue Server zum Pool hinzufügen, aktualisieren Sie Ihre neuen Poolserver, sodass diese im Hinblick auf das kumulative Update auf demselben Stand sind wie die bereits bestehenden Server in dem Pool. 
  
### <a name="to-add-or-remove-front-end-servers"></a>Zum Hinzufügen oder Entfernen von Front-End-Servern

1. Wenn Sie alle Front-End-Server entfernen, beenden Sie zuerst neue Verbindungen mit diesen Servern. Dazu können Sie das folgende Cmdlet verwenden:
    
   ```
   Stop-CsWindowsService -Graceful
   ```

2. Öffnen Sie den Topologie-Generator und fügen Sie hinzu oder entfernen Sie die benötigten Server. 
    
3. Veröffentlichen Sie die Topologie.
    
    > [!IMPORTANT]
    > Wenn Sie einen Server zum Pool in Ihrer Topologie hinzufügen oder daraus entfernen und dann die aktualisierte Topologie veröffentlichen, werden alle Server im Pool gleichzeitig gestartet. Während die Server neu gestartet werden, ist der Pool offline, wodurch der Dienst für die mit diesem Pool verbundenen Benutzer unterbrochen wird. Um Dienstunterbrechungen zu vermeiden, planen Sie die Veröffentlichung der Topologie mit dem neuen Server im Pool außerhalb der Geschäftszeiten. 
  
4. Wenn Sie die Anzahl der Server im Front-End-Pool in einer der folgenden Methoden geändert haben, müssen Sie den Pool mit dann zurücksetzen, indem Sie das folgende Cmdlet eingeben: Reset-CsPoolRegistrarState - ResetType FullReset - PoolFqdn 
    
   ```
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - 2 bis beliebig
    
     - Beliebig bis 2
    
     - 3 bis beliebig
    
     - Beliebig bis 3
    
5. Starten Sie den Pool neu, indem Sie das folgende Cmdlet eingeben
    
   ```
   Start-CsPool
   ```