---
title: Vorbereiten eines einzelnen Standard Edition-Servers (Aufruf)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployAIOInvoke
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5da0aa73-8bf8-41f3-81e7-94f955cda541
description: Auf der Seite "Befehle ausführen" können die Aufgaben zum Installieren der SQL Server Express und zum Konfigurieren der Rolle des zentralen Verwaltungsspeichers im Aufgabenbereich angezeigt werden. Standardmäßig wird eine Instanz einer SQL Server-basierten Datenbank mit dem Namen RTC erstellt. Außerdem werden auch Firewallregeln erstellt, um Servern und Clients für die Kommunikation mit der Datenbank und Instanz einen ein- und ausgehenden Zugriff zu erlauben. Nachdem die Aufgabe abgeschlossen wurde, können Sie die Protokolldatei in der Dropdownliste auswählen. Die Protokolldatei hat den Namen Bootstrap local machine. Klicken Sie nach Auswählen der Protokolldatei auf Protokoll anzeigen. Überprüfen Sie die Protokolldatei auf Fehler und Warnungen. Klicken Sie im Anschluss an die Überprüfung auf Fertig stellen. Sie sollten jetzt Ihre Topologie mit dem Topologie-Generator definieren, wenn Sie dies noch nicht getan haben.
ms.openlocfilehash: 6c6cd0062f5d8269b7cd19a1d3587f90e24b9d3e551b372907d593719ca89054
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54319308"
---
# <a name="prepare-single-standard-edition-server-invoke"></a>Vorbereiten eines einzelnen Standard Edition-Servers (Aufruf)
 
Auf der Seite **"Befehle ausführen"** können die Aufgaben zum Installieren der SQL Server Express und zum Konfigurieren der Rolle des zentralen Verwaltungsspeichers im Aufgabenbereich angezeigt werden. Standardmäßig wird eine Instanz einer SQL Server-basierten Datenbank mit dem Namen RTC erstellt. Außerdem werden auch Firewallregeln erstellt, um Servern und Clients für die Kommunikation mit der Datenbank und Instanz einen ein- und ausgehenden Zugriff zu erlauben. Nachdem die Aufgabe abgeschlossen wurde, können Sie die Protokolldatei in der Dropdownliste auswählen. Die Protokolldatei hat den Namen **Bootstrap local machine**. Klicken Sie nach Auswählen der Protokolldatei auf **Protokoll anzeigen**. Überprüfen Sie die Protokolldatei auf Fehler und Warnungen. Klicken Sie im Anschluss an die Überprüfung auf **Fertig stellen**. Sie sollten jetzt Ihre Topologie mit dem Topologie-Generator definieren, wenn Sie dies noch nicht getan haben.
  
> [!IMPORTANT]
> Die Installation des SQL Server Express kann einige Zeit in Anspruch nehmen. Während der Installation ist kein Fortschritt auf dem Bildschirm oder im Aufgabenbereich sichtbar. Um die Installation zu überwachen, sollten Sie Windows Task-Manager verwenden und nach den MSIExec-Prozessen und den Setupdateien für SQL Server suchen. Auf diese Weise können Sie den Status der Installation anzeigen und sicherstellen, dass die Installation fortgesetzt wird. Abhängig von Faktoren, die den Rahmen dieses Hilfethemas sprengen, kann es bis zu 15 Minuten oder mehr dauern, bis die Installation der SQL Server Instanz abgeschlossen ist. 
  

