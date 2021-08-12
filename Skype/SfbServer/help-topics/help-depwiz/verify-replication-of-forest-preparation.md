---
title: Überprüfen der Replikation der Gesamtstrukturvorbereitung
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainVerifyForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 94e87632-7c28-43df-9238-f5a47c1c43c0
description: 'Führen Sie die folgenden Aktionen aus, um die Replikation des globalen Katalogs und der bei der Vorbereitung der Gesamtstruktur erstellten Objekte zu überprüfen:'
ms.openlocfilehash: 304513bbae1e27224172c3efc638825c22a1f2d8f6ce2b4d83085d6b0b38a226
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54347031"
---
# <a name="verify-replication-of-forest-preparation"></a>Überprüfen der Replikation der Gesamtstrukturvorbereitung
 
Führen Sie die folgenden Aktionen aus, um die Replikation des globalen Katalogs und der bei der Vorbereitung der Gesamtstruktur erstellten Objekte zu überprüfen:
  
1. Öffnen Sie auf einem Domänencontroller (vorzugsweise an einem Remotestandort gegenüber den anderen Domänencontrollern) in der Gesamtstruktur, in der die Gesamtstrukturvorbereitung durchgeführt wurde, **Active Directory-Benutzer und -Computer**.
    
2. Erweitern Sie in **Active Directory-Benutzer und -Computer** den Domänennamen Ihrer Gesamtstruktur oder einer untergeordneten Domäne.
    
3. Klicken Sie im linken Bereich auf den Container **"Benutzer",** und suchen Sie im rechten Seitenbereich nach der universellen Gruppe "CsAdministrator". Wenn CsAdministrator (unter acht anderen neuen universellen Gruppen, die mit Cs beginnen) vorhanden ist, war die Replikation der Gesamtstrukturvorbereitung erfolgreich.
    
4. Wenn die Gruppe nicht vorhanden ist, können Sie die Replikation erzwingen oder 15 Minuten warten und den rechten Fensterbereich aktualisieren. Die Replikation ist abgeschlossen, wenn die Gruppen vorhanden sind.
    
> [!TIP]
> Wenn Sie die Vom Skype for Business Server Bereitstellungs-Assistenten erstellten Protokolldateien überprüfen möchten, finden Sie sie auf dem Computer, auf dem der Bereitstellungs-Assistent ausgeführt wurde, im Verzeichnis "Benutzer" des Active Directory Domain Services-Benutzers, der den Schritt ausgeführt hat. Wenn sich der Benutzer beispielsweise als Domänenadministrator in der Domäne Contoso.net angemeldet hat, befinden sich die Protokolldateien in: C:\Users\Administrator.Contoso\AppData\Local\Temp 
  

