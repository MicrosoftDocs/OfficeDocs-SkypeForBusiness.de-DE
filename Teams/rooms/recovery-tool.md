---
title: Verwenden Sie das Wiederherstellungstools für Microsoft Teams Rooms
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: In diesem Artikel wird erläutert, wie Sie das Wiederherstellungstool für Microsoft Teams-Räume verwenden, das Sie verwenden würden, um ein veraltetes System in einen unterstützten Zustand zu versetzen.
ms.openlocfilehash: c50b59ff4ed1ee997b990b0776ef4a7ee0ac29c2
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271160"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a>Verwenden Sie das Wiederherstellungstools für Microsoft Teams Rooms

In diesem Artikel wird erläutert, wie Sie das Wiederherstellungstool für Microsoft Teams-Räume verwenden, das Sie verwenden würden, um ein veraltetes System in einen unterstützten Zustand zu versetzen. Dieses Tool sollte angewendet werden, wenn entweder in der Microsoft Teams-Räume Konsole der Fehler "Systemkonfiguration veraltet" angezeigt wird, oder bevor die [Werkswiederherstellung](./rooms-operations.md#microsoft-teams-rooms-reset-factory-restore) auf Knopfdruck zurückgesetzt wird.

## <a name="prerequisites"></a>Voraussetzungen

Laden Sie das neueste [Microsoft Teams-Räume Installationspaket](https://go.microsoft.com/fwlink/?linkid=851168) herunter, und extrahieren Sie es auf einen USB-Speicherstick oder eine Netzwerkfreigabe, auf die Microsoft Teams-Räume zugreifen kann.

> [!NOTE]
> Das Extrahieren der Dateien aus der MSI-Datei kann auf viele Verschiedenes erreicht werden. Jeder Mechanismus, mit dem alle Dateien extrahiert und ihre Verzeichnisstruktur beibehalten wird, ist akzeptabel. Eine solche Möglichkeit ist die Verwendung des Befehls `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` , der `PathToMsi` den vollständigen Pfad zum Microsoft Teams Room-Installationspaket darstellt und `PathToTarget` den vollständigen Pfad zu dem Ordner darstellt, in den die Dateien extrahiert werden sollen.

## <a name="running-the-tool"></a>Ausführen des Tools

1) Melden Sie sich auf Ihrem Microsoft Teams-Räume Gerät beim Administratorkonto an, und starten Sie eine Eingabeaufforderung mit erhöhten Rechten.
2) Überprüfen Sie vom Microsoft Teams-Räume Gerät, ob Sie auf die `RecoveryTool.ps1` Datei zugreifen können, die in den Dateien enthalten ist, die aus dem Microsoft Teams-Räume Installationspaket extrahiert wurden. Das Kit befindet sich auf der Netzwerkfreigabe oder dem USB-Laufwerk, das bei der Vorbereitung der Voraussetzungen verwendet wird.
3) Führen Sie `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.
4) So führen Sie eine Factorywiederherstellung durch:
   1. Wenn Sie vom Skript dazu aufgefordert werden, wählen Sie Option 2 aus: **Zurücksetzen**.
   2. Wenn BitLocker aktiviert ist, folgen Sie den Anweisungen am Ende der Skriptausgabe, um sie zu deaktivieren.
   3. Führen Sie die Werkswiederherstellung durch.
      1. Öffnen Sie die **Einstellungs-App**, und wählen Sie **"& Sicherheit aktualisieren**" aus.
      2. Navigieren Sie zur Registerkarte " **Wiederherstellung** ".
      3. Wählen **Sie unter "Diesen PC zurücksetzen**" die Option "**Erste Schritte**" aus.
      4. Wählen Sie **"Alles entfernen"** und dann "**Weiter**" und **"Zurücksetzen"** aus.
        > [!WARNING]
        > Das Microsoft Teams-Räume Gerät kann unbrauchbar werden, wenn die Option "**Meine Dateien behalten – Entfernt Apps und Einstellungen" aktiviert ist, während** des Windows-Zurücksetzens jedoch die Option "Persönliche Dateien" aktiviert bleibt. Wählen Sie diese Option nicht aus.
      5. Das System wird mehrmals neu gestartet. Wenn das Zurücksetzen abgeschlossen ist, wird das System auf dem Windows-Bildschirm "Out of Box Experience" (OOBE) angezeigt.



## <a name="see-also"></a>Siehe auch

[Microsoft Teams Rooms-Hilfe](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Microsoft Teams Rooms verwalten](rooms-manage.md)
