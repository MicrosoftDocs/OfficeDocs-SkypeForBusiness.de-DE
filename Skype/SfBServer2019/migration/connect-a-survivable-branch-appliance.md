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
ms.localizationpriority: medium
description: 'Jede Survivable Branch Appliance (SBA) ist einem Front-End-Pool zugeordnet, der als Sicherungsregistrierungsstelle für den SBA dient. Wenn der Front-End-Pool zu Skype for Business Server 2019 migriert wird, muss der SBA beim Upgrade des Pools vom Front-End-Pool getrennt werden. Nachdem der Pool zu Skype for Business Server 2019 migriert wurde, kann der SBA dem aktualisierten Front-End-Pool erneut zugeordnet werden. Dies umfasst das Löschen des SBA aus der älteren Topologie im Topologie-Generator und das anschließende Hinzufügen des SBA zur Skype for Business Server 2019-Topologie. Benutzer, die im älteren SBA verwaltet werden, müssen zuerst in einen anderen Front-End-Pool verschoben werden, bevor sie den SBA aus der Topologie entfernen. Sobald der SBA der Skype for Business Server 2019-Topologie hinzugefügt wurde, können diese Benutzer zurück zum SBA verschoben werden. Die dazu erforderlichen Schritte sind im Folgenden zusammengefasst:'
ms.openlocfilehash: c431451503efd23039b4c358488bfc5bce03ba65
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58588047"
---
# <a name="connect-a-survivable-branch-appliance"></a>Verbinden einer Survivable Branch Appliance

Jede Survivable Branch Appliance (SBA) ist einem Front-End-Pool zugeordnet, der als Sicherungsregistrierungsstelle für den SBA dient. Wenn der Front-End-Pool zu Skype for Business Server 2019 migriert wird, muss der SBA beim Upgrade des Pools vom Front-End-Pool getrennt werden. Nachdem der Pool zu Skype for Business Server 2019 migriert wurde, kann der SBA dem aktualisierten Front-End-Pool erneut zugeordnet werden. Dies umfasst das Löschen des SBA aus der älteren Topologie im Topologie-Generator und das anschließende Hinzufügen des SBA zur Skype for Business Server 2019-Topologie. Benutzer, die im älteren SBA verwaltet werden, müssen zuerst in einen anderen Front-End-Pool verschoben werden, bevor sie den SBA aus der Topologie entfernen. Nachdem der SBA der Skype for Business Server 2019-Topologie hinzugefügt wurde, können diese Benutzer zurück zum SBA verschoben werden. Die dazu erforderlichen Schritte sind im Folgenden zusammengefasst:
  
1. Verlagern Sie Zweigstellenbenutzer, die im älteren SBA verwaltet werden, in einen anderen Front-End-Pool.
    
2. Entfernen Sie SBA aus der Legacytopologie, um den vorhandenen Front-End-Pool als Sicherungsregistrierungsstelle zu trennen.
    
3. Fügen Sie SBA zur Topologie Skype for Business Server 2019 hinzu, und konfigurieren Sie diesen neuen Front-End-Pool als Sicherungsregistrierungsstelle. 
    
4. Verschieben Sie die Verzweigungsbenutzer in die neue Skype for Business Server 2019 SBA.
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a>Hinzufügen einer älteren SBA-Zweigstelle zu Ihrer Topologie

1. Öffnen Sie den **Topologie-Generator**.
    
2. Klicken Sie im linken Bereich mit der rechten Maustaste auf **"Zweigstellen",** und klicken Sie dann auf **"Neue Zweigstelle".**
    
3. Klicken Sie im Dialogfeld **Neuen Zweigstellenstandort definieren** auf **Name**, und geben Sie den Namen für den Zweigstellenstandort ein.
    
4. (Optional) Klicken Sie auf **Beschreibung**, und geben Sie eine aussagekräftige Beschreibung für den Zweigstellenstandort ein.
    
5. Klicken Sie auf **Weiter**.
    
6. (Optional) Führen Sie im nächsten Dialogfeld **Neuen Zweigstellenstandort definieren** einen der folgenden Schritte aus: 
    
    1. Klicken Sie auf **Ort**, und geben Sie den Namen der Stadt ein, in der sich der Zweigstellenstandort befindet.
    
    2. Klicken Sie auf **Bundesland/Kanton**, und geben Sie den Namen des Bundeslands bzw. Kantons ein, in dem sich der Zweigstellenstandort befindet.
    
    3. Klicken Sie auf **Ländercode**, und geben Sie den zweistelligen Ländercode für das Land ein, in dem sich der Zweigstellenstandort befindet.
    
7. Klicken Sie auf **"Weiter",** und deaktivieren Sie, wenn Sie an diesem Standort eine Survivable Branch Appliance oder einen Survivable Branch-Server verwenden, das Kontrollkästchen **"Neuen Survivable-Assistenten öffnen", wenn dieser Assistent geschlossen** wird. Klicken Sie auf **Fertig stellen**.
    
8. So ordnen Sie den Legacy-SBA dem Skype for Business Server 2019-Front-End-Pool zu:
    
    1. Erweitern Sie die Zweigstelle, die erstellt wurde. 
    
    2. Klicken Sie mit der rechten Maustaste auf die Legacyversion, und klicken Sie dann auf **"Neu".**
    
    3. Klicken Sie auf **Survivable Branch Appliance**.
    
9. Folgen Sie den Anweisungen im geöffneten Assistenten. Informationen zu Assistentenelementen finden Sie unter    
   <!-- [Define a Survivable Branch Appliance or Server in Lync 2013](/previous-versions/office/lync-server-2013/lync-server-2013-define-a-survivable-branch-appliance-or-server). -->
   <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > Eine Survivable Branch Appliance kann nur einer Überwachungs-Store zugeordnet werden. 
  
10. Wenn Sie an diesem Standort keine Survivable Branch Appliance oder keinen Survivable Branch Server verwenden, deaktivieren Sie das Kontrollkästchen **"Neuen Survivable-Assistenten öffnen", wenn dieser Assistent das** Kontrollkästchen schließt, und klicken Sie dann auf **"Fertig stellen".**
    
11. Wiederholen Sie die vorherigen Schritte für jeden Zweigstellenstandort, den Sie der Topologie hinzufügen möchten.
