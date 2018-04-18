---
title: Verwenden Sie das Skype Raum Systemen v2 Recovery-tool
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 4/17/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df418e25-81fd-474d-be16-5cd1ac8145cc
description: In diesem Artikel wird erläutert, wie das Wiederherstellungstool verwenden für Skype Raum Systemen v2, Sie verwenden würden, um ein veraltet System in einem unterstützten Zustand bringen.
ms.openlocfilehash: 5972f38370227e93cb0154771a35f3c5b0458052
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2018
---
# <a name="use-the-skype-room-systems-v2-recovery-tool"></a>Verwenden Sie das Skype Raum Systemen v2 Recovery-tool
 
In diesem Artikel wird erläutert, wie das Wiederherstellungstool verwenden für Skype Raum Systemen v2, Sie verwenden würden, um ein veraltet System in einem unterstützten Zustand bringen. Verwenden Sie dieses Tool, wenn die Skype Raum Systemen v2-Konsole einen "veraltet System Config" Fehler angezeigt wird.
  

<a name="Prerequisites"> </a>  
## <a name="prerequisites"></a>Voraussetzungen

Laden Sie das neueste [Skype Raum Systemen v2 Installationspaket](https://go.microsoft.com/fwlink/?linkid=851168) und Entpacken Sie es auf einem USB-Speicher Stick oder einer Netzwerkressource Skype Raum Systemen v2 Gerät zugegriffen werden.

Sie müssen auch [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu)installieren.

<a name="Windows-ver"> </a>
## <a name="verify-windows-version"></a>Überprüfen der Windows-Version 

1. Melden Sie sich ein Administratorkonto, indem Sie auf **Einstellungen > Windows-Einstellung > Admin anmelden** vom Gerät v2 Skype Raum Systeme. Diese Option bietet Ihnen zum Anmeldebildschirm.
2. Melden Sie sich bei einer Administratorkonto der Standard-Administrator berücksichtigt wird `admin` mit dem Kennwort `sfb`.
3. Klicken Sie auf das Startmenü und Typ `winver.exe` in das Suchfeld, und klicken Sie auf * das Ergebnis der*Befehl ausführen* .
4. Notieren Sie die Nummer nach "Version" in der zweiten Zeile im Infobereich.

> [HINWEIS] Wenn die Version dargestellt 1607 oder früher ist, führen Sie die Schritte in den Schritten <a href="#Windows-up">Update Windows vor der Wiederherstellung</a> vor Proceding zu den Schritten zum <a href="#Perform">Ausführen einer Wiederherstellung</a> . Wenn die Version dargestellt 1607 größer ist, führen Sie nur die Schritte unter <a href="#Perform">Perform Wiederherstellung</a>.

<a name="Windows-up"> </a>
## <a name="update-windows-before-recovery-if-needed"></a>Aktualisieren von Windows vor der Wiederherstellung (falls erforderlich)

1. Zwar weiterhin als Benutzer mit Administratorberechtigung angemeldet haben, starten Sie ein Powershell-Eingabeaufforderung mit erhöhten Rechten.
2. Führen Sie den Befehl `Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`.
3. Führen Sie Windows Update, und installieren Sie das Update für Windows 1709.
4. Nachdem die Aktualisierung auf 1709 ist vollständige Anmeldung wieder in den Administratorkonto und [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu)installieren. Das Update kann über den Link durchgeführt werden, oder über Windows Update.
5. Installieren Sie zusätzliche verfügbare Updates von Windows Update.

<a name="Perform"> </a>
## <a name="perform-a-recovery"></a>Führen Sie eine Wiederherstellung

1. Melden Sie sich an das Administratorkonto auf dem mobilen Gerät Skype Raum Systeme-v2, und starten Sie eine Eingabeaufforderung mit erhöhten Rechten.
2. Vergewissern Sie sich vom Gerät v2 Skype Raum Systeme, dass Sie Zugriff auf sind die `RecoveryTool.ps1` -Datei, die in die Dateien extrahiert haben, aus dem Skype Raum Systemen v2-Installationspaket enthalten ist. Das Kit finden Sie auf der Netzwerkfreigabe oder USB-Laufwerk beim Vorbereiten der erforderlichen Komponenten verwendet.
3. Führen Sie den Befehl Powershell.exe `-file "<path to RecoveryTool.ps1>" -ExecutionPolicy Unrestricted`.
4. Bei Aufforderung durch die Option "Skript auswählen" `1:"Repair System"`.
5. Starten Sie nach dem Abschluss das Skype Raum Systemen v2 Gerät neu. Es wird erneut automatisch neu gestartet und könnten vollständig wiederhergestellte zweites Mal.



<a name="See"> </a>  
## <a name="see-also"></a>Waren diese Schritte hilfreich? Wenn ja, teilen Sie uns dies bitte unterhalb des Artikels mit. Wenn nicht, schreiben Sie uns, was für Sie unklar war, und wir verwenden Ihr Feedback, um unsere Schritte zu überprüfen.


#### 

[Verwalten von Skype Raum Systemen v2](skype-room-systems-v2.md)
#### 