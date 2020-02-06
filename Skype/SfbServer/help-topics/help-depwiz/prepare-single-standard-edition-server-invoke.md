---
title: Vorbereiten eines einzelnen Standard Edition-Servers (Aufruf)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Auf der Seite "Befehle ausführen" können die Aufgaben der Installation von SQL Server Express und der Konfiguration als zentraler Verwaltungsspeicher im Aufgabenbereich angezeigt werden. Standardmäßig wird eine Instanz einer SQL Server-basierten Datenbank mit dem Namen RTC erstellt. Außerdem werden Firewallregeln erstellt, um den ein-und ausgehenden Zugriff für Server und Clients für die Kommunikation mit der Datenbank und Instanz zu ermöglichen. Nach Abschluss der Aufgabe können Sie die Protokolldatei aus der Dropdownliste auswählen. Die Protokolldatei hat den Namen Bootstrap Local Machine. Nachdem Sie die Protokolldatei ausgewählt haben, klicken Sie auf Protokoll anzeigen. Überprüfen Sie die Protokolldatei auf Fehler und Warnungen. Wenn Sie den Vorgang fortsetzen möchten, klicken Sie auf Fertig stellen. Wenn Sie dies noch nicht getan haben, sollten Sie jetzt Ihre Topologie mit dem Topology Builder definieren.
ms.openlocfilehash: 16cc6ada75ae90da4da2cb269aed26adbf472a33
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823439"
---
# <a name="prepare-single-standard-edition-server-invoke"></a>Vorbereiten eines einzelnen Standard Edition-Servers (Aufruf)
 
Auf der Seite " **Befehle ausführen** " können die Aufgaben der Installation von SQL Server Express und der Konfiguration als zentraler Verwaltungsspeicher im Aufgabenbereich angezeigt werden. Standardmäßig wird eine Instanz einer SQL Server-basierten Datenbank mit dem Namen RTC erstellt. Außerdem werden Firewallregeln erstellt, um den ein-und ausgehenden Zugriff für Server und Clients für die Kommunikation mit der Datenbank und Instanz zu ermöglichen. Nach Abschluss der Aufgabe können Sie die Protokolldatei aus der Dropdownliste auswählen. Die Protokolldatei hat den Namen **Bootstrap Local Machine**. Nachdem Sie die Protokolldatei ausgewählt haben, klicken Sie auf **Protokoll anzeigen**. Überprüfen Sie die Protokolldatei auf Fehler und Warnungen. Wenn Sie den Vorgang fortsetzen möchten, klicken Sie auf **Fertig stellen.** Wenn Sie dies noch nicht getan haben, sollten Sie jetzt Ihre Topologie mit dem Topology Builder definieren.
  
> [!IMPORTANT]
> Die Installation von SQL Server Express kann einige Zeit in Anspruch nehmen. Während der Installation wird kein Status auf dem Bildschirm oder im Aufgabenbereich angezeigt. Um die Installation zu überwachen, sollten Sie den Windows Task-Manager verwenden und nach den msiexec-Prozessen und den Setup Dateien für SQL Server suchen. Auf diese Weise können Sie den Status der Installation anzeigen und sicherstellen, dass die Installation fortgesetzt wird. In Abhängigkeit von Faktoren, die den Rahmen dieses Hilfethemas sprengen, kann es bis zu 15 Minuten dauern, bis die SQL Server-Instanz installiert wird. 
  

