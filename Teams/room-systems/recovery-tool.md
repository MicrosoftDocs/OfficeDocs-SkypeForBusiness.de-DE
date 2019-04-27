---
title: Verwenden Sie das Wiederherstellungstools für Microsoft Teams Rooms
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: davgroom
ms.date: 4/17/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
ms.collection: M365-voice
localization_priority: Normal
description: In diesem Artikel wird erläutert, wie mit dem Recovery Tool für Microsoft-Teams Chatrooms, die Sie verwenden würden, um ein veraltet System in einem unterstützten Zustand bringen.
ms.openlocfilehash: 9580a94c96b7982a3030ccc0435be8e05f7c4a25
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2019
ms.locfileid: "33362815"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a>Verwenden Sie das Wiederherstellungstools für Microsoft Teams Rooms
 
In diesem Artikel wird erläutert, wie mit dem Recovery Tool für Microsoft-Teams Chatrooms, die Sie verwenden würden, um ein veraltet System in einem unterstützten Zustand bringen. Verwenden Sie dieses Tool, wenn die Microsoft-Teams Räume-Konsole einen "veraltet System Config" Fehler angezeigt wird.
  

<a name="Prerequisites"> </a>  
## <a name="prerequisites"></a>Voraussetzungen

Laden Sie das neueste [Installationspaket für den Microsoft-Teams Chatrooms](https://go.microsoft.com/fwlink/?linkid=851168) und Entpacken Sie es auf ein USB-Speicher Stick oder eine Netzwerkfreigabe für das Microsoft-Teams Chatrooms Gerät zugänglich ist.

Sie müssen auch [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu)installieren.

<a name="Windows-ver"> </a>
## <a name="verify-windows-version"></a>Überprüfen der Windows-Version 

1. Melden Sie sich an ein Administratorkonto, indem Sie auf **Settings> Setting> Admin Anmeldung im Windows** vom Microsoft-Teams Chatrooms Gerät. Diese Option bietet Ihnen zum Anmeldebildschirm.
2. Melden Sie sich bei einer Administratorkonto der Standard-Administrator berücksichtigt wird `admin` mit dem Kennwort `sfb`.
3. Klicken Sie auf das Startmenü und Typ `winver.exe` in das Suchfeld, und klicken Sie auf * das Ergebnis der*Befehl ausführen* .
4. Notieren Sie die Nummer nach "Version" in der zweiten Zeile im Infobereich.

>[!NOTE]
>Wenn die Version dargestellt 1607 oder früher ist, führen Sie die Schritte in den Schritten <a href="#Windows-up">Update Windows vor der Wiederherstellung</a> vor Proceding zu den Schritten zum <a href="#Perform">Ausführen einer Wiederherstellung</a> . Wenn die Version dargestellt 1607 größer ist, führen Sie nur die Schritte unter <a href="#Perform">Perform Wiederherstellung</a>.

<a name="Windows-up"> </a>
## <a name="update-windows-before-recovery-if-needed"></a>Aktualisieren von Windows vor der Wiederherstellung (falls erforderlich)

1. Zwar weiterhin als Benutzer mit Administratorberechtigung angemeldet haben, starten Sie ein Powershell-Eingabeaufforderung mit erhöhten Rechten.
2. Führen Sie den Befehl `Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`.
3. Führen Sie Windows Update, und installieren Sie das Update für Windows 1709.
4. Nachdem die Aktualisierung auf 1709 ist vollständige Anmeldung wieder in den Administratorkonto und [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu)installieren. Das Update kann über den Link durchgeführt werden, oder über Windows Update.
5. Als optionalen Schritt installieren Sie zusätzliche verfügbare Updates von Windows Update.

<a name="Perform"> </a>
## <a name="perform-a-recovery"></a>Führen Sie eine Wiederherstellung

1. Melden Sie sich an das Administratorkonto auf dem Gerät Microsoft Teams Chatrooms, und starten Sie eine Eingabeaufforderung mit erhöhten Rechten.
2. Vergewissern Sie sich vom Microsoft-Teams Chatrooms Gerät, dass Sie Zugriff auf sind die `RecoveryTool.ps1` -Datei, die in die Dateien extrahiert haben, aus dem Microsoft-Teams Räume-Installationspaket enthalten ist. Das Kit finden Sie auf der Netzwerkfreigabe oder USB-Laufwerk beim Vorbereiten der erforderlichen Komponenten verwendet.
3. Führen Sie den Befehl Powershell.exe `-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.
4. Bei Aufforderung durch die Option "Skript auswählen" `1:"Repair System"`.
5. Starten Sie nach dem Abschluss das Microsoft-Teams Chatrooms Gerät neu. Es wird erneut automatisch neu gestartet und könnten vollständig wiederhergestellte zweites Mal.



<a name="See"> </a>  
## <a name="see-also"></a>Siehe auch
 
[Microsoft Teams Rooms-Hilfe](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Microsoft Teams Rooms verwalten](skype-room-systems-v2.md)