---
title: Überprüfen der Replikation der Gesamtstrukturvorbereitung
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainVerifyForestPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 94e87632-7c28-43df-9238-f5a47c1c43c0
ROBOTS: NOINDEX, NOFOLLOW
description: 'Führen Sie die folgenden Aktionen aus, um die Replikation des globalen Katalogs und der bei der Vorbereitung der Gesamtstruktur erstellten Objekte zu überprüfen:'
ms.openlocfilehash: 31164e51cd3de60ce25313f726fc9c7ba086f299
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60738541"
---
# <a name="verify-replication-of-forest-preparation"></a>Überprüfen der Replikation der Gesamtstrukturvorbereitung
 
Führen Sie die folgenden Aktionen aus, um die Replikation des globalen Katalogs und der bei der Vorbereitung der Gesamtstruktur erstellten Objekte zu überprüfen:
  
1. Öffnen Sie auf einem Domänencontroller (vorzugsweise an einem Remotestandort gegenüber den anderen Domänencontrollern) in der Gesamtstruktur, in der die Gesamtstrukturvorbereitung durchgeführt wurde, **Active Directory-Benutzer und -Computer**.
    
2. Erweitern Sie in **Active Directory-Benutzer und -Computer** den Domänennamen Ihrer Gesamtstruktur oder einer untergeordneten Domäne.
    
3. Klicken Sie im linken Bereich auf den Container **"Benutzer",** und suchen Sie im rechten Seitenbereich nach der universellen Gruppe "CsAdministrator". Wenn CsAdministrator (unter acht anderen neuen universellen Gruppen, die mit Cs beginnen) vorhanden ist, war die Replikation der Gesamtstrukturvorbereitung erfolgreich.
    
4. Wenn die Gruppe nicht vorhanden ist, können Sie die Replikation erzwingen oder 15 Minuten warten und den rechten Fensterbereich aktualisieren. Die Replikation ist abgeschlossen, wenn die Gruppen vorhanden sind.
    
> [!TIP]
> Wenn Sie die Vom Skype for Business Server Bereitstellungs-Assistenten erstellten Protokolldateien überprüfen möchten, finden Sie diese auf dem Computer, auf dem der Bereitstellungs-Assistent ausgeführt wurde, im Verzeichnis "Benutzer" des Active Directory Domain Services-Benutzers, der den Schritt ausgeführt hat. Wenn sich der Benutzer beispielsweise als Domänenadministrator in der Domäne Contoso.net angemeldet hat, befinden sich die Protokolldateien in: C:\Users\Administrator.Contoso\AppData\Local\Temp 
  

