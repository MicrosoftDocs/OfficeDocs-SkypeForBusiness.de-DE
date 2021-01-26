---
title: Vorbereiten eines einzelnen Standard Edition-Servers (Aufruf)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployAIOInvoke
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 5da0aa73-8bf8-41f3-81e7-94f955cda541
ROBOTS: NOINDEX, NOFOLLOW
description: Auf der Seite "Befehle ausführen" können die Aufgaben der Installation von SQL Server Express und der Konfiguration als zentraler Verwaltungsspeicher im Aufgabenbereich angezeigt werden. Standardmäßig wird eine Instanz einer SQL Server Datenbank namens RTC erstellt. Außerdem werden auch Firewallregeln erstellt, um Servern und Clients für die Kommunikation mit der Datenbank und Instanz einen ein- und ausgehenden Zugriff zu erlauben. Nachdem die Aufgabe abgeschlossen wurde, können Sie die Protokolldatei in der Dropdownliste auswählen. Die Protokolldatei hat den Namen Bootstrap local machine. Klicken Sie nach Auswählen der Protokolldatei auf Protokoll anzeigen. Überprüfen Sie die Protokolldatei auf Fehler und Warnungen. Klicken Sie im Anschluss an die Überprüfung auf Fertig stellen. Wenn Sie dies noch nicht getan haben, sollten Sie ihre Topologie jetzt mit dem Topologie-Generator definieren.
ms.openlocfilehash: c3e6e01f7aed0471d8f1eed0ad79f8ef6320f86a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820615"
---
# <a name="prepare-single-standard-edition-server-invoke"></a>Vorbereiten eines einzelnen Standard Edition-Servers (Aufruf)
 
Auf der **Seite "Befehle** ausführen" können die Aufgaben der Installation von SQL Server Express und der Konfiguration als zentraler Verwaltungsspeicher im Aufgabenbereich angezeigt werden. Standardmäßig wird eine Instanz einer SQL Server Datenbank namens RTC erstellt. Außerdem werden auch Firewallregeln erstellt, um Servern und Clients für die Kommunikation mit der Datenbank und Instanz einen ein- und ausgehenden Zugriff zu erlauben. Nachdem die Aufgabe abgeschlossen wurde, können Sie die Protokolldatei in der Dropdownliste auswählen. Die Protokolldatei hat den Namen **Bootstrap local machine**. Klicken Sie nach Auswählen der Protokolldatei auf **Protokoll anzeigen**. Überprüfen Sie die Protokolldatei auf Fehler und Warnungen. Klicken Sie im Anschluss an die Überprüfung auf **Fertig stellen**. Wenn Sie dies noch nicht getan haben, sollten Sie ihre Topologie jetzt mit dem Topologie-Generator definieren.
  
> [!IMPORTANT]
> Die Installation von SQL Server Express kann einige Zeit dauern. Während der Installation ist kein Fortschritt auf dem Bildschirm oder im Aufgabenbereich sichtbar. Verwenden Sie zum Überwachen der Installation den Windows-Task-Manager, und suchen Sie nach den MSIExec-Prozessen und den Setupdateien für SQL Server. Auf diese Weise können Sie den Status der Installation anzeigen und sicherstellen, dass die Installation fortschreitet. Je nach faktoren, die den Rahmen dieses Hilfethemas über hinausgehen, kann es bis zu 15 Minuten oder mehr dauern, bis die Installation der SQL Server abgeschlossen ist. 
  

