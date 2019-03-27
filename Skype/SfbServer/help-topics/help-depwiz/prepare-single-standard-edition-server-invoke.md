---
title: Vorbereiten eines einzelnen Standard Edition-Servers (Aufruf)
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployAIOInvoke
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5da0aa73-8bf8-41f3-81e7-94f955cda541
description: Klicken Sie auf der Seite Befehle ausführen können die Aufgaben von SQL Server Express installieren und Konfigurieren von um als dem zentralen Verwaltungsspeicher fungieren im Aufgabenbereich angezeigt werden. Standardmäßig wird eine Instanz einer SQL Server-basierten ist RTC-Datenbank erstellt. Firewall-Regeln werden auch erstellt, um eingehende und ausgehende Zugriff für Server und Clients zur Kommunikation mit der Datenbank und eine Instanz zulässig. Nachdem der Vorgang abgeschlossen ist, können Sie die Protokolldatei aus der Dropdown-Liste auswählen. Die Protokolldatei heißt Bootstrap lokalen Computer. Klicken Sie nachdem Sie die Protokolldatei ausgewählt haben auf Protokoll anzeigen. Überprüfen Sie die Protokolldatei für alle Fehler und Warnungen. Wenn Sie zum Fortfahren bereit sind, klicken Sie auf Fertig stellen. Wenn Sie nicht bereits getan haben, sollten Sie jetzt Ihre Topologie mit Topology Builder definieren.
ms.openlocfilehash: 665075799794d94328e0a5a3d9e1f9c603813ed7
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30880063"
---
# <a name="prepare-single-standard-edition-server-invoke"></a>Vorbereiten eines einzelnen Standard Edition-Servers (Aufruf)
 
Auf der Seite **Befehle ausführen** können die Aufgaben von SQL Server Express installieren und Konfigurieren von um als dem zentralen Verwaltungsspeicher fungieren im Aufgabenbereich angezeigt werden. Standardmäßig wird eine Instanz einer SQL Server-basierten ist RTC-Datenbank erstellt. Firewall-Regeln werden auch erstellt, um eingehende und ausgehende Zugriff für Server und Clients zur Kommunikation mit der Datenbank und eine Instanz zulässig. Nachdem der Vorgang abgeschlossen ist, können Sie die Protokolldatei aus der Dropdown-Liste auswählen. Die Protokolldatei heißt **Bootstrap lokalen Computer**. Klicken Sie nachdem Sie die Protokolldatei ausgewählt haben auf **Protokoll anzeigen**. Überprüfen Sie die Protokolldatei für alle Fehler und Warnungen. Wenn Sie zum Fortfahren bereit sind, klicken Sie auf **Fertig stellen.** Wenn Sie nicht bereits getan haben, sollten Sie jetzt Ihre Topologie mit Topology Builder definieren.
  
> [!IMPORTANT]
> Die Installation von SQL Server Express kann einige Zeit in Anspruch nehmen. Während der Installation ist kein Fortschritt auf dem Bildschirm oder im Aufgabenbereich angezeigt. Um die Installation zu überwachen, sollten Sie Windows Task-Manager verwenden und suchen Sie nach der MSIExec-Prozesse und die Installationsdateien für SQL Server. Auf diese Weise können Sie den Status der Installation anzeigen und achten Sie darauf, dass die Installation fortfahren ist. Je nach Faktoren Gegenstand dieses Hilfethema kann es bis zu 15 Minuten dauern oder mehr für die Installation der SQL Server-Instanz um abzuschließen. 
  

