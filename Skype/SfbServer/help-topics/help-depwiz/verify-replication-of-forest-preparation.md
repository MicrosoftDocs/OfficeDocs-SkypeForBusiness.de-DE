---
title: Überprüfen der Replikation der Gesamtstrukturvorbereitung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifyForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 94e87632-7c28-43df-9238-f5a47c1c43c0
description: 'Gehen Sie wie folgt vor, um zu bestätigen, dass die Replikation des globalen Katalogs und das Erstellen von Objekten während der Gesamtstrukturvorbereitung erfolgreich war:'
ms.openlocfilehash: ae6d068521f7b2e6038d05545da16be11c51cf18
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34289505"
---
# <a name="verify-replication-of-forest-preparation"></a>Überprüfen der Replikation der Gesamtstrukturvorbereitung
 
Gehen Sie wie folgt vor, um zu bestätigen, dass die Replikation des globalen Katalogs und das Erstellen von Objekten während der Gesamtstrukturvorbereitung erfolgreich war:
  
1. Öffnen Sie **Active Directory-Benutzer und -Computer** auf einem Domänencontroller (vorzugsweise an einem Remotestandort gegenüber den anderen Domänencontrollern) in der Gesamtstruktur, in der die Gesamtstrukturvorbereitung durchgeführt wurde.
    
2. Erweitern Sie in **Active Directory-Benutzer und -Computer** den Domänennamen Ihrer Gesamtstruktur oder einer untergeordneten Domäne.
    
3. Klicken Sie im linken Bereich auf den Container **Benutzer** , und suchen Sie im rechten Bereich nach der universellen Gruppe CsAdministrator. Wenn CsAdministrator (unter acht anderen neuen universellen Gruppen, die mit CS beginnen) vorhanden ist, wurde die Replikation der Gesamtstrukturvorbereitung erfolgreich ausgeführt.
    
4. Wenn die Gruppe (n) noch nicht vorhanden ist, können Sie die Replikation erzwingen oder 15 Minuten warten und den rechten Seitenbereich aktualisieren. Die Replikation ist abgeschlossen, wenn die Gruppen vorhanden sind.
    
> [!TIP]
> Wenn Sie die Protokolldateien überprüfen möchten, die vom Bereitstellungs-Assistenten für Skype for Business Server erstellt wurden, können Sie diese auf dem Computer finden, auf dem der Bereitstellungs-Assistent ausgeführt wurde, und zwar im Verzeichnis Benutzer des Active Directory-Domänendienste-Benutzers, der den Schritt ausgeführt hat. Wenn sich der Benutzer beispielsweise als Domänenadministrator im Domänen contoso.net angemeldet hat, befinden sich die Protokolldateien in: C:\users\administrator.Contoso\AppData\Local\Temp 
  

