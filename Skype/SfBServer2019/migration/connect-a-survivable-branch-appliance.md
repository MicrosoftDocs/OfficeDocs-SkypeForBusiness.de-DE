---
title: Verbinden einer Survivable Branch Appliance
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Jeder Survivable Branch Appliance (SBA) ist einem Front-End-Pool die dient als sicherungsregistrierung für die SBA zugeordnet. Wenn der Front-End Pool zu Skype für Business Server 2019, die SBA migriert wurde während der Pool aktualisiert wird, sobald der Pool zu Skype für Business Server 2019 migriert wurde, aus dem Front-End-Pool getrennt werden müssen, kann die SBA mit der aktualisierten Front-E erneut verknüpft werden. Nd-Pool. Dies umfasst die SBA aus der Vorversion Topologie im Topologie-Generator löschen und dann die Skype für Business Server 2019 Topologie die SBA hinzuzufügen. Benutzer, die sich in der Legacy-SBA zuerst in einen anderen Front-End-Pool verschoben werden muss vor dem Entfernen der SBA aus der Topologie. Nachdem die Skype für Business Server 2019 Topologie die SBA hinzugefügt wird, können diese Benutzer dann wieder auf die SBA verschoben werden. Diese Schritte werden im folgenden zusammengefasst:'
ms.openlocfilehash: e4917b20e9e680627e92935dcb10ebf06c2e3d2d
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32238654"
---
# <a name="connect-a-survivable-branch-appliance"></a>Verbinden einer Survivable Branch Appliance

Jeder Survivable Branch Appliance (SBA) ist einem Front-End-Pool, der als sicherungsregistrierung für die SBA fungiert zugeordnet. Wenn Sie der Front-End-Pool zu Skype für Business Server 2019 migriert wurde, muss die SBA aus dem Front-End-Pool aufgehoben werden soll, während der Pool aktualisiert wird. Nach der Pool zu Skype für Business Server 2019 migriert wurde, kann die SBA wieder mit dem aktualisierten Front-End-Pool zugeordnet werden. Dies umfasst die SBA aus der Vorversion Topologie im Topologie-Generator löschen und dann die Skype für Business Server 2019 Topologie die SBA hinzuzufügen. Benutzer, die sich in der Legacy-SBA zuerst in einen anderen Front-End-Pool verschoben werden muss vor dem Entfernen der SBA aus der Topologie. Nachdem die Skype für Business Server 2019 Topologie die SBA hinzugefügt wurde, können diese Benutzer wieder auf die SBA verschoben werden. Diese Schritte werden im folgenden zusammengefasst:
  
1. Verschieben Sie Benutzer an Zweigstellenstandorten in der Vorversion SBA in einen anderen Front-End-Pool verwaltet.
    
2. Entfernen der SBA aus der Vorversion Topologie der vorhandenen Front-End-Pools als sicherungsregistrierung zu trennen.
    
3. Fügen Sie der SBA zur die Skype für Business Server 2019 Topologie hinzu und konfigurieren Sie dieses neuen Front-End-Pools als sicherungsregistrierung. 
    
4. Verschieben der Zweigstellenbenutzer auf die neue Skype für Business Server 2019 SBA.
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a>Hinzufügen der Vorversion SBA-Zweigniederlassung zu einer Topologie

1. **Topologie-Generator**zu öffnen.
    
2. Klicken Sie im linken Bereich mit der rechten Maustaste **Zweigniederlassungen**, und klicken Sie dann auf **Neue Zweigniederlassung**.
    
3. Klicken Sie auf **Name**, und geben Sie den Namen des zweigstellenstandorts, klicken Sie im Dialogfeld **Neue Zweigniederlassung definieren** .
    
4. (Optional) Klicken Sie auf **Beschreibung**, und geben Sie eine aussagekräftige Beschreibung für den Zweigstellenstandort.
    
5. Klicken Sie auf **Weiter**.
    
6. (Optional) Klicken Sie im Dialogfeld **Neue Zweigniederlassung definieren** führen Sie eine der folgenden Aktionen aus: 
    
    1. Klicken Sie auf **Ort**, und geben Sie den Namen der Stadt ein, in dem sich die Zweigniederlassung befindet.
    
    2. Klicken Sie auf **Bundesland/Kanton**, und geben Sie den Namen der das Bundesland oder die Region, in dem sich die Zweigniederlassung befindet.
    
    3. Klicken Sie auf **Ländercode**, und geben Sie den zweistelligen aufrufenden Code für das Land/Region, in dem sich die Zweigniederlassung befindet.
    
7. Klicken Sie auf **Weiter**, und klicken Sie dann, wenn Sie eine Survivable Branch Appliance oder einen Server an diesem Standort arbeiten, werden Sie sicher, dass Sie das Kontrollkästchen **Öffnen Sie den neuen Survivable Assistenten Wenn dieser Assistent geschlossen** . Klicken Sie auf **Fertig stellen**.
    
8. So verknüpfen Sie die legacy-SBA der Skype für Business Server 2019 Front-End-Pool:
    
    1. Erweitern Sie den Zweigstellenstandort, der erstellt wurde. 
    
    2. Mit der rechten Maustaste auf die ältere Version, und klicken Sie dann auf **neu**.
    
    3. Klicken Sie auf **Survivable Branch Appliance**.
    
9. Führen Sie die Schritte des Assistenten, das geöffnet wird. Informationen zum Assistenten für Elemente finden Sie unter    
   <!-- [Define a Survivable Branch Appliance or Server in Lync 2013](https://technet.microsoft.com/en-us/library/gg398280(v=ocs.15).aspx). -->
   <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > Survivable Branch Appliance kann nur eine Überwachungsspeicher zugeordnet werden. 
  
10. Wenn Sie nicht über eine Survivable Branch Appliance oder einen Server an diesem Standort arbeiten, deaktivieren Sie das Kontrollkästchen **Öffnen Sie den neuen Survivable Assistenten Wenn dieser Assistent geschlossen** , und klicken Sie dann auf **Fertig stellen**.
    
11. Wiederholen Sie die vorherigen Schritte für jeden Zweigstellenstandort, der zur Topologie hinzugefügt werden soll.
    

