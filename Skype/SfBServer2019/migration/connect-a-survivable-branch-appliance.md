---
title: Verbinden einer Survivable Branch Appliance
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Jede Survivable Branch Appliance (SBA) ist mit einem Front-End-Pool verbunden, der als Backup-Registrar für die SBA fungiert. Wenn der Front-End-Pool zu Skype for Business Server 2019 migriert wird, muss die SBA vom Front-End-Pool entfernt werden, während der Pool aktualisiert wird, nachdem der Pool zu Skype for Business Server 2019 migriert wurde, kann die SBA erneut mit dem aktualisierten Front-E verknüpft werden. ND-Pool. Dies umfasst das Löschen des SBA aus der Legacy Topologie im Topologie-Generator und das anschließende Hinzufügen des SBA zur Skype for Business Server 2019-Topologie. Benutzer, die in der Legacy-SBA verwaltet werden, müssen zunächst in einen anderen Front-End-Pool verschoben werden, bevor Sie die SBA aus der Topologie entfernen. Sobald die SBA zur Skype for Business Server 2019-Topologie hinzugefügt wurde, können diese Benutzer wieder in die SBA verschoben werden. Nachfolgend werden die folgenden Schritte zusammengefasst:'
ms.openlocfilehash: e5545a2de4eddd65790f425ab888b8fd07faf970
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239284"
---
# <a name="connect-a-survivable-branch-appliance"></a>Verbinden einer Survivable Branch Appliance

Jede Survivable Branch Appliance (SBA) ist mit einem Front-End-Pool verknüpft, der als Sicherungs Registrierungsstelle für die SBA fungiert. Wenn der Front-End-Pool zu Skype for Business Server 2019 migriert wird, muss der SBA beim Upgrade des Pools vom Front-End-Pool abgehoben werden. Nachdem der Pool zu Skype for Business Server 2019 migriert wurde, kann der SBA dem aktualisierten Front-End-Pool erneut zugeordnet werden. Dies umfasst das Löschen des SBA aus der Legacy Topologie im Topologie-Generator und das anschließende Hinzufügen des SBA zur Skype for Business Server 2019-Topologie. Benutzer, die in der Legacy-SBA verwaltet werden, müssen zunächst in einen anderen Front-End-Pool verschoben werden, bevor Sie die SBA aus der Topologie entfernen. Nachdem die SBA zur Skype for Business Server 2019-Topologie hinzugefügt wurde, können diese Benutzer wieder in die SBA verschoben werden. Nachfolgend werden die folgenden Schritte zusammengefasst:
  
1. Verschieben Sie Branch-Benutzer, die sich im Legacy-SBA befinden, in einen anderen Front-End-Pool.
    
2. Entfernen Sie SBA aus der Legacy Topologie, um den vorhandenen Front-End-Pool als Sicherungs Registrierungsstelle zu trennen.
    
3. Fügen Sie SBA zur Skype for Business Server 2019-Topologie hinzu, und konfigurieren Sie diesen neuen Front-End-Pool als Sicherungs Registrierungsstelle. 
    
4. Verschieben Sie die Benutzer der Verzweigung in den neuen Skype for Business Server 2019 SBA.
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a>Hinzufügen einer älteren SBA-Verzweigungs Website zu Ihrer Topologie

1. Öffnen Sie den **Topologie-Generator**.
    
2. Klicken Sie im linken Bereich mit der rechten Maustaste auf **Verzweigungs Websites**, und klicken Sie dann auf **neue Verzweigungs Website**.
    
3. Klicken Sie im Dialogfeld **neue Verzweigungs Website definieren** auf **Name**, und geben Sie dann den Namen der Verzweigungs Website ein.
    
4. Optional Klicken Sie auf **Beschreibung**, und geben Sie eine aussagekräftige Beschreibung für die Verzweigungs Website ein.
    
5. Klicken Sie auf **Weiter**.
    
6. Optional Führen Sie im nächsten Dialogfeld **neue Verzweigungs Website definieren** eine der folgenden Aktionen aus: 
    
    1. Klicken Sie auf **Stadt**, und geben Sie dann den Namen des Orts ein, in dem sich die Zweigstelle befindet.
    
    2. Klicken Sie auf **Bundesland/Region**, und geben Sie dann den Namen des Bundeslands oder der Region ein, in dem sich die Verzweigungs Website befindet.
    
    3. Klicken Sie auf **Landesvorwahl**, und geben Sie dann den zweistelligen anrufcode für das Land/die Region ein, in dem sich die Zweigstelle befindet.
    
7. Klicken Sie auf **weiter**, und wenn Sie eine überlebensfähige Branch-Appliance oder einen Server an dieser Website verwenden, müssen Sie das Kontrollkästchen **den neuen Überlebenden-Assistenten öffnen, wenn dieser Assistent geschlossen** wird, deaktivieren. Klicken Sie auf **Fertig stellen**.
    
8. So ordnen Sie das Legacy-SBA dem Skype for Business Server 2019-Front-End-Pool zu:
    
    1. Erweitern Sie die erstellte Verzweigungs Website. 
    
    2. Klicken Sie mit der rechten Maustaste auf Legacy Version, und klicken Sie dann auf **neu**.
    
    3. Klicken Sie auf **Survivable Branch Appliance**.
    
9. Folgen Sie den Anweisungen im Assistenten, der geöffnet wird. Informationen zu Assistenten Elementen finden Sie unter    
   <!-- [Define a Survivable Branch Appliance or Server in Lync 2013](https://technet.microsoft.com/en-us/library/gg398280(v=ocs.15).aspx). -->
   <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > Eine Survivable Branch-Appliance kann nur einem Überwachungsspeicher zugeordnet werden. 
  
10. Wenn Sie keine Survivable Branch-Appliance oder einen Server an dieser Website verwenden, deaktivieren Sie das Kontrollkästchen **neuen Überlebenden Assistenten öffnen, wenn dieser Assistent geschlossen** wird, und klicken Sie dann auf **Fertig stellen**.
    
11. Wiederholen Sie die vorherigen Schritte für jede Verzweigungs Website, die Sie der Topologie hinzufügen möchten.
    

