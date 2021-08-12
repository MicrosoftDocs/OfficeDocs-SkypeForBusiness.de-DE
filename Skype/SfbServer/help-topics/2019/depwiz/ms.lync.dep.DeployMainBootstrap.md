---
title: Einrichten oder Entfernen von Komponenten von Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainBootstrap
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: f8813f25-eafa-4006-a186-94e4ebcc5ac7
ROBOTS: NOINDEX, NOFOLLOW
description: 'Um Skype for Business Server Komponenten zu installieren und zu aktivieren oder zu deinstallieren, verwenden Sie Schritt 2: Einrichten oder Entfernen Skype Serverkomponenten. Sie müssen auf dem Computer, den Sie installieren oder ändern, als lokaler Administrator angemeldet sein und in der Lage sein, Active Directory Domain Services-Benutzer und -Gruppen in der aktuellen Domäne zu lesen. Klicken Sie zunächst auf "Ausführen". Wenn Sie dies tun, wird die auf dem zentralen Verwaltungsspeicher basierende Topologiedefinition gelesen. Erforderliche Softwarekomponenten werden entsprechend der rolle, die im zentralen Verwaltungsspeicher definiert ist, installiert und konfiguriert. Wenn die Installation abgeschlossen ist, überprüfen Sie die Zusammenfassung, und klicken Sie auf Fertig stellen.'
ms.openlocfilehash: 6bea150f7117fe30e1785d2494c7348171bba615ec884946c8e935b2475e9e25
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54282188"
---
# <a name="setup-or-remove-skype-for-business-server-components"></a>Einrichten oder Entfernen von Komponenten von Skype for Business Server
 
Um Skype for Business Server Komponenten zu installieren und zu aktivieren oder zu deaktivieren oder zu deinstallieren, verwenden Sie **Schritt 2: Einrichten oder Entfernen Skype Serverkomponenten.** Sie müssen auf dem Computer, den Sie installieren oder ändern, als lokaler Administrator angemeldet sein und in der Lage sein, Active Directory Domain Services-Benutzer und -Gruppen in der aktuellen Domäne zu lesen. Klicken Sie zunächst auf **"Ausführen".** Wenn Sie dies tun, wird die auf dem zentralen Verwaltungsspeicher basierende Topologiedefinition gelesen. Erforderliche Softwarekomponenten werden entsprechend der rolle, die im zentralen Verwaltungsspeicher definiert ist, installiert und konfiguriert. Überprüfen Sie nach Abschluss der Installation die Zusammenfassung, und klicken Sie auf **Fertig stellen.**
  
> [!TIP]
> Wenn Sie die vom Bereitstellungs-Assistenten erstellten Protokolldateien überprüfen müssen, finden Sie diese auf dem Computer, auf dem der Bereitstellungs-Assistent ausgeführt wurde, im Verzeichnis "Benutzer" des Active Directory-Benutzers, der den Schritt ausgeführt hat. Wenn sich der Benutzer beispielsweise als Domänenadministrator in der Domäne Contoso.net angemeldet hat, befinden sich die Protokolldateien in: > C:\Users\Administrator.Contoso\AppData\Local\Temp 
  
> [!NOTE]
> Wenn Sie zuvor Skype for Business Server Komponenten auf diesem Computer installiert haben, erkennt der Bereitstellungs-Assistent dies, und die Schaltfläche in Schritt 2 wird als **"Erneut ausführen"** angezeigt. Auf diese Weise können Sie den Schritt so oft wie nötig ausführen, um den Server ordnungsgemäß zu konfigurieren oder zu ändern. 
  

