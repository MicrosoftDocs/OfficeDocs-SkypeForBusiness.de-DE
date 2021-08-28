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
ms.localizationpriority: medium
ms.assetid: 5da0aa73-8bf8-41f3-81e7-94f955cda541
ROBOTS: NOINDEX, NOFOLLOW
description: Auf der Seite "Befehle ausführen" können die Aufgaben zum Installieren der SQL Server Express und zum Konfigurieren als zentraler Verwaltungsspeicher im Aufgabenbereich angezeigt werden. Standardmäßig wird eine Instanz einer SQL Server-basierten Datenbank namens RTC erstellt. Außerdem werden auch Firewallregeln erstellt, um Servern und Clients für die Kommunikation mit der Datenbank und Instanz einen ein- und ausgehenden Zugriff zu erlauben. Nachdem die Aufgabe abgeschlossen wurde, können Sie die Protokolldatei in der Dropdownliste auswählen. Die Protokolldatei hat den Namen Bootstrap local machine. Klicken Sie nach Auswählen der Protokolldatei auf Protokoll anzeigen. Überprüfen Sie die Protokolldatei auf Fehler und Warnungen. Klicken Sie im Anschluss an die Überprüfung auf Fertig stellen. Sie sollten jetzt Ihre Topologie mit dem Topologie-Generator definieren, wenn Sie dies noch nicht getan haben.
ms.openlocfilehash: 9e51339e49d798b882d4395c27b7273a3ee9128d
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58590539"
---
# <a name="prepare-single-standard-edition-server-invoke"></a>Vorbereiten eines einzelnen Standard Edition-Servers (Aufruf)
 
Auf der Seite **"Befehle ausführen"** können die Aufgaben zum Installieren des SQL Server Express und zum Konfigurieren als zentraler Verwaltungsspeicher im Aufgabenbereich angezeigt werden. Standardmäßig wird eine Instanz einer SQL Server-basierten Datenbank namens RTC erstellt. Außerdem werden auch Firewallregeln erstellt, um Servern und Clients für die Kommunikation mit der Datenbank und Instanz einen ein- und ausgehenden Zugriff zu erlauben. Nachdem die Aufgabe abgeschlossen wurde, können Sie die Protokolldatei in der Dropdownliste auswählen. Die Protokolldatei hat den Namen **Bootstrap local machine**. Klicken Sie nach Auswählen der Protokolldatei auf **Protokoll anzeigen**. Überprüfen Sie die Protokolldatei auf Fehler und Warnungen. Klicken Sie im Anschluss an die Überprüfung auf **Fertig stellen**. Sie sollten jetzt Ihre Topologie mit dem Topologie-Generator definieren, wenn Sie dies noch nicht getan haben.
  
> [!IMPORTANT]
> Die Installation der SQL Server Express kann einige Zeit in Anspruch nehmen. Während der Installation ist kein Fortschritt auf dem Bildschirm oder im Aufgabenbereich sichtbar. Um die Installation zu überwachen, sollten Sie Windows Task-Manager verwenden und nach den MSIExec-Prozessen und den Setupdateien für SQL Server suchen. Auf diese Weise können Sie den Status der Installation anzeigen und sicherstellen, dass die Installation fortgesetzt wird. Abhängig von Faktoren, die den Rahmen dieses Hilfethemas sprengen, kann es bis zu 15 Minuten oder mehr dauern, bis die Installation der SQL Server Instanz abgeschlossen ist. 
  

