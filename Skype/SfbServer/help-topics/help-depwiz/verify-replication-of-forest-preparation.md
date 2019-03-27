---
title: Überprüfen der Replikation der Gesamtstrukturvorbereitung
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifyForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 94e87632-7c28-43df-9238-f5a47c1c43c0
description: 'Um zu bestätigen, dass die Replikation des globalen Katalogs und die Erstellung von Objekten während der Vorbereitung der Gesamtstruktur verfügen erfolgreich war, gehen Sie folgendermaßen vor:'
ms.openlocfilehash: 113f3627f1d180ac8ccb63c97a606c5af6622767
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884020"
---
# <a name="verify-replication-of-forest-preparation"></a>Überprüfen der Replikation der Gesamtstrukturvorbereitung
 
Um zu bestätigen, dass die Replikation des globalen Katalogs und die Erstellung von Objekten während der Vorbereitung der Gesamtstruktur verfügen erfolgreich war, gehen Sie folgendermaßen vor:
  
1. Öffnen Sie **Active Directory-Benutzer und -Computer** auf einem Domänencontroller (vorzugsweise an einem Remotestandort gegenüber den anderen Domänencontrollern) in der Gesamtstruktur, in der die Gesamtstrukturvorbereitung durchgeführt wurde.
    
2. Erweitern Sie in **Active Directory-Benutzer und -Computer** den Domänennamen Ihrer Gesamtstruktur oder einer untergeordneten Domäne.
    
3. Klicken Sie auf den Container **Users** , klicken Sie im linken Bereich, und suchen Sie nach der universellen Gruppe CsAdministrator klicken Sie im rechten Bereich. Wenn CsAdministrator (zwischen acht andere neuen universellen Gruppen, die beginnen mit Cs) vorhanden ist, wurde die Replikation der Vorbereitung der Gesamtstruktur erfolgreich hergestellt.
    
4. Wenn die Gruppe noch nicht vorhanden ist, können Sie erzwingen, dass die Replikation oder warten Sie 15 Minuten und aktualisieren im rechten Bereich. Die Replikation ist abgeschlossen, wenn die Gruppen vorhanden sind.
    
> [!TIP]
> Wenn Sie die Protokolldateien, die durch die Skype für Business Server-Bereitstellungs-Assistenten erstellt werden, prüfen möchten, können Sie diese auf dem Computer finden, in dem Bereitstellungs-Assistenten ausgeführt wurde, in das Verzeichnis Benutzer des Benutzers Active Directory Domain Services, die im Schritt ausgeführt hat. Angenommen, wenn der Benutzer als Domänenadministrator in der Domäne Contoso.net angemeldet, die Protokolldateien befinden sich im: C:\Users\Administrator.Contoso\AppData\Local\Temp 
  

