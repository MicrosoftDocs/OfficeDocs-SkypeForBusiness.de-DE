---
title: Verwenden Sie das Wiederherstellungstools für Microsoft Teams Rooms
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: davgroom
ms.date: 4/17/2018
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection: M365-voice
localization_priority: Normal
description: In diesem Artikel wird erläutert, wie Sie das Wiederherstellungstool für Microsoft Teams-Räume verwenden, mit denen Sie ein veraltetes System in einen unterstützten Zustand bringen.
ms.openlocfilehash: 90e6db7739a4a95e3f1fbde62f5b8dd8bde9e237
ms.sourcegitcommit: 1401ee484a2bc8e72d96649b0571bb59198f9dab
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "36427987"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a>Verwenden Sie das Wiederherstellungstools für Microsoft Teams Rooms
 
In diesem Artikel wird erläutert, wie Sie das Wiederherstellungstool für Microsoft Teams-Räume verwenden, mit denen Sie ein veraltetes System in einen unterstützten Zustand bringen. Sie würden dieses Tool verwenden, wenn die Microsoft Teams rooms-Konsole einen Fehler "Systemkonfiguration veraltet" anzeigt.
  

<a name="Prerequisites"> </a>  
## <a name="prerequisites"></a>Voraussetzungen

Laden Sie das neueste [Microsoft Teams rooms-Installationspaket](https://go.microsoft.com/fwlink/?linkid=851168) herunter, und extrahieren Sie es auf einen USB-Speicherstick oder eine Netzwerkfreigabe, auf die das Microsoft Teams rooms-Gerät zugreifen kann.

Möglicherweise müssen Sie auch [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu)installieren.

<a name="Windows-ver"> </a>
## <a name="verify-windows-version"></a>Überprüfen der Windows-Version 

1. Melden Sie sich bei einem Administratorkonto an, indem Sie unter **Einstellungen> Windows-Einstellung> Administrator** beim Microsoft Teams rooms-Gerät anmelden. Mit dieser Option gelangen Sie zum Anmeldebildschirm.
2. Melden Sie sich `admin` bei einem Administratorkonto an, dem standardmäßigen Administrator `sfb`Konto, das das Kennwort hat.
3. Klicken Sie auf das Startmenü und geben `winver.exe` Sie in das Suchfeld ein und klicken Sie auf*Befehl "ausführen* " im Ergebnis.
4. Notieren Sie sich die Zahl nach "Version" in der zweiten Zeile des Infobereichs.

>[!NOTE]
>Wenn die angezeigte Version 1607 oder früher ist, führen Sie die Schritte in den Schritten unter <a href="#Windows-up">Aktualisieren von Windows vor der Wiederherstellung</a> vor vorgegangen, um die Schritte zum <a href="#Perform">Ausführen einer Wiederherstellung auszuführen</a> . Wenn die angezeigte Version größer als 1607 ist, führen Sie nur die Schritte unter <a href="#Perform">Durchführen einer Wiederherstellung</a>aus.

<a name="Windows-up"> </a>
## <a name="update-windows-before-recovery-if-needed"></a>Aktualisieren von Windows vor der Wiederherstellung (falls erforderlich)

1. Wenn Sie weiterhin als Administrator angemeldet sind, starten Sie eine Eingabeaufforderung mit erhöhten PowerShell.
2. Führen Sie den `Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`Befehl aus.
3. Führen Sie Windows Update aus, und installieren Sie das Update für Windows 1709.
4. Nachdem das Update auf 1709 abgeschlossen ist, melden Sie sich erneut beim Administratorkonto an, und installieren Sie [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu). Das Update kann über den Link oder die Verwendung von Windows Update erfolgen.
5. Als optionalen Schritt installieren Sie alle weiteren Updates, die über Windows Update zur Verfügung stehen.

<a name="Perform"> </a>
## <a name="perform-a-recovery"></a>Durchführen einer Wiederherstellung

1. Registrieren Sie sich auf Ihrem Microsoft Teams rooms-Gerät beim Administratorkonto, und starten Sie eine Eingabeaufforderung mit erhöhten Rechten.
2. Überprüfen Sie im Microsoft Teams rooms-Gerät, dass Sie auf die `RecoveryTool.ps1` Datei zugreifen können, die in den Dateien enthalten ist, die aus dem Installationspaket für Microsoft Teams rooms extrahiert wurden. Das Kit befindet sich auf der Netzwerkfreigabe oder dem USB-Laufwerk, das bei der Vorbereitung von Voraussetzungen verwendet wird.
3. Führen Sie den Befehl `-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`PowerShell. exe aus.
4. Wenn Sie von der Option `1:"Repair System"`Skript auswählen aufgefordert werden.
5. Starten Sie nach Abschluss das Microsoft Teams rooms-Gerät neu. Sie wird automatisch neu gestartet und beim zweiten Mal wieder vollständig wiederhergestellt.



<a name="See"> </a>  
## <a name="see-also"></a>Siehe auch
 
[Microsoft Teams Rooms-Hilfe](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Microsoft Teams Rooms verwalten](skype-room-systems-v2.md)
