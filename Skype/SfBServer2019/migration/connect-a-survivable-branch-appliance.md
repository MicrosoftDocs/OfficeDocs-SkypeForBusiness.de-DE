---
title: Verbinden einer Survivable Branch Appliance
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
description: 'Jede Survivable Branch Appliance (SBA) ist einer Front-End-Pool zugeordnet, die als Sicherungs Registrierungsstelle für die SBVg dient. Wenn die Front-End-Pool zu Skype for Business Server 2019 migriert wird, muss die SBVg von der Front-End-Pool entfernt werden, während der Pool aktualisiert wird, nachdem der Pool zu Skype for Business Server 2019 migriert wurde, kann die SBVg erneut mit der aktualisierten Front-End-Pool verbunden werden. Dies umfasst das Löschen des SBA aus der Legacy Topologie im Topologie-Generator und das anschließende Hinzufügen des SBA zur Skype for Business Server 2019-Topologie. Benutzer, die in der Legacy-SBA verwaltet werden, müssen zuerst in eine andere Front-End-Pool verschoben werden, bevor Sie die SBA aus der Topologie entfernen. Sobald die SBVg der Skype for Business Server 2019-Topologie hinzugefügt wurde, können diese Benutzer wieder in die SBVg verschoben werden. Die dazu erforderlichen Schritte sind im Folgenden zusammengefasst:'
ms.openlocfilehash: 23fea7694a754b82ecad684d2ea02b603a6c7299
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751547"
---
# <a name="connect-a-survivable-branch-appliance"></a>Verbinden einer Survivable Branch Appliance

Jede Survivable Branch Appliance (SBA) ist einer Front-End-Pool zugeordnet, die als Sicherungs Registrierungsstelle für die SBVg dient. Wenn die Front-End-Pool zu Skype for Business Server 2019 migriert wird, muss die SBVg von der Front-End-Pool entfernt werden, während der Pool aktualisiert wird. Nachdem der Pool zu Skype for Business Server 2019 migriert wurde, kann die SBVg erneut mit der aktualisierten Front-End-Pool verknüpft werden. Dies umfasst das Löschen des SBA aus der Legacy Topologie im Topologie-Generator und das anschließende Hinzufügen des SBA zur Skype for Business Server 2019-Topologie. Benutzer, die in der Legacy-SBA verwaltet werden, müssen zuerst in eine andere Front-End-Pool verschoben werden, bevor Sie die SBA aus der Topologie entfernen. Nachdem die SBVg der Skype for Business Server 2019-Topologie hinzugefügt wurde, können diese Benutzer wieder in die SBVg verschoben werden. Die dazu erforderlichen Schritte sind im Folgenden zusammengefasst:
  
1. Verlagern von Zweigstellenbenutzern, die sich in der Legacy-SBA befinden, in eine andere Front-End-Pool
    
2. Entfernen Sie SBA aus der Legacy Topologie, um die vorhandene Front-End-Pool als Sicherungs Registrierungsstelle zu trennen.
    
3. Fügen Sie SBA zur Skype for Business Server 2019-Topologie hinzu, und konfigurieren Sie diese neue Front-End-Pool als Sicherungs Registrierungsstelle. 
    
4. Stellen Sie die Zweigstellenbenutzer in die neue Skype for Business Server 2019 SBA.
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a>Hinzufügen eines Legacy-SBA-Zweigstellen Standorts zu Ihrer Topologie

1. Öffnen Sie den **Topologie-Generator**.
    
2. Klicken Sie im linken Bereich mit der rechten Maustaste auf **Zweigstellenstandorte**, und klicken Sie dann auf **Neue Zweigstelle**.
    
3. Klicken Sie im Dialogfeld **Neuen Zweigstellenstandort definieren** auf **Name**, und geben Sie den Namen für den Zweigstellenstandort ein.
    
4. (Optional) Klicken Sie auf **Beschreibung**, und geben Sie eine aussagekräftige Beschreibung für den Zweigstellenstandort ein.
    
5. Klicken Sie auf **Weiter**.
    
6. (Optional) Führen Sie im nächsten Dialogfeld **Neuen Zweigstellenstandort definieren** einen der folgenden Schritte aus: 
    
    1. Klicken Sie auf **Ort**, und geben Sie den Namen der Stadt ein, in der sich der Zweigstellenstandort befindet.
    
    2. Klicken Sie auf **Bundesland/Kanton**, und geben Sie den Namen des Bundeslands bzw. Kantons ein, in dem sich der Zweigstellenstandort befindet.
    
    3. Klicken Sie auf **Ländercode**, und geben Sie den zweistelligen Ländercode für das Land ein, in dem sich der Zweigstellenstandort befindet.
    
7. Klicken Sie auf **weiter**, und wenn Sie eine Survivable Branch Appliance oder einen Server an dieser Website verwenden, müssen Sie den Assistenten zum **Öffnen des neuen überlebten Assistenten deaktivieren, wenn dieser Assistent geschlossen** wird. Klicken Sie auf **Fertig stellen**.
    
8. So ordnen Sie das Legacy-SBA dem Skype for Business Server 2019 Front-End-Pool zu:
    
    1. Erweitern Sie den Zweigstellenstandort, der erstellt wurde. 
    
    2. Klicken Sie mit der rechten Maustaste auf ältere Version, und klicken Sie dann auf **neu**.
    
    3. Klicken Sie auf **Survivable Branch Appliance**.
    
9. Befolgen Sie die Anweisungen im Assistenten, der geöffnet wird. Informationen zu Assistenten Elementen finden Sie unter    
   <!-- [Define a Survivable Branch Appliance or Server in Lync 2013](https://technet.microsoft.com/library/gg398280(v=ocs.15).aspx). -->
   <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > Ein Survivable Branch Appliance kann nur einem Überwachungsspeicher zugeordnet werden. 
  
10. Wenn Sie an diesem Standort keinen Survivable Branch Appliance oder Server verwenden, deaktivieren Sie das Kontrollkästchen **neuen überlebten Assistenten öffnen, wenn dieser Assistent geschlossen** wird, und klicken Sie dann auf **Fertig stellen**.
    
11. Wiederholen Sie die vorherigen Schritte für jeden Zweigstellenstandort, den Sie der Topologie hinzufügen möchten.
    

