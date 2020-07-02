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
f1.keywords:
- NOCSH
localization_priority: Normal
description: In diesem Artikel wird erläutert, wie Sie das Wiederherstellungstool für Microsoft Teams-Räume verwenden, mit denen Sie ein veraltetes System in einen unterstützten Zustand bringen.
ms.openlocfilehash: 47e9bed4377a111a1c1284684bbc40517dbb42d8
ms.sourcegitcommit: 4099da7b1db7663e63ef5bece16e3090c33ea207
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2020
ms.locfileid: "45021723"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a>Verwenden Sie das Wiederherstellungstools für Microsoft Teams Rooms

In diesem Artikel wird erläutert, wie Sie das Wiederherstellungstool für Microsoft Teams-Räume verwenden, mit denen Sie ein veraltetes System in einen unterstützten Zustand bringen. Dieses Tool sollte angewendet werden, wenn die Microsoft Teams rooms-Konsole einen Fehler vom Typ "Systemkonfiguration veraltet" oder vor dem Durchführen einer [Wiederherstellung](https://docs.microsoft.com/microsoftteams/rooms/rooms-operations#microsoft-teams-rooms-reset-factory-restore)des Zurücksetzens einer Drucktaste zeigt.

## <a name="prerequisites"></a>Voraussetzungen

Laden Sie das neueste [Microsoft Teams rooms-Installationspaket](https://go.microsoft.com/fwlink/?linkid=851168) herunter, und extrahieren Sie es auf einen USB-Speicherstick oder eine Netzwerkfreigabe, auf die das Microsoft Teams rooms-Gerät zugreifen kann.

> [!NOTE]
> Das Extrahieren der Dateien aus der MSI-Datei kann mit vielen Mitteln erfolgen. Jeder Mechanismus, der alle Dateien extrahiert und die Verzeichnisstruktur erhält, ist akzeptabel. Eine Möglichkeit besteht darin, den Befehl zu `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` verwenden `PathToMsi` , der den vollständigen Pfad zum Microsoft Teams Room-Installationspaket darstellt, und `PathToTarget` stellt den vollständigen Pfad zu dem Ordner dar, in den die Dateien extrahiert werden sollen.

## <a name="running-the-tool"></a>Ausführen des Tools

1) Registrieren Sie sich auf Ihrem Microsoft Teams rooms-Gerät beim Administratorkonto, und starten Sie eine Eingabeaufforderung mit erhöhten Rechten.
2) Überprüfen Sie im Microsoft Teams rooms-Gerät, auf das Sie zugreifen können `RecoveryTool.ps1 file` , das in den Dateien enthalten ist, die aus dem Installationspaket für Microsoft Teams rooms extrahiert wurden. Das Kit befindet sich auf der Netzwerkfreigabe oder dem USB-Laufwerk, das bei der Vorbereitung von Voraussetzungen verwendet wird.
3) Ausführen `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"` .
4) So führen Sie eine Factory-Wiederherstellung aus:
   1. Wenn Sie vom Skript dazu aufgefordert werden, wählen Sie Option 2: **Zurücksetzen**aus.
   2. Wenn BitLocker aktiviert ist, folgen Sie den Anweisungen am Ende der Skriptausgabe, um Sie zu deaktivieren.
   3. Durchführen der Factory-Wiederherstellung
      1. Öffnen Sie die app " **Einstellungen** ", und wählen Sie **& Sicherheit aktualisieren** aus.
      2. Navigieren Sie zur Registerkarte **Wiederherstellen** .
      3. Wählen Sie unter **diesen PC zurücksetzen die**Option **Erste Schritte** aus.
      4. Wählen Sie **alles entfernen**und dann **weiter** und **Zurücksetzen** aus.
        > [!WARNING]
        > Das Gerät "Microsoft Teams Rooms" kann unbrauchbar werden, wenn die Option " **meine Dateien beibehalten-apps und Einstellungen entfernt, aber Ihre persönlichen Dateien** beibehalten" während des Windows-Reset-Vorgangs aktiviert ist. Wählen Sie diese Option nicht aus.
      5. Das System wird mehrmals neu gestartet. Wenn der Reset abgeschlossen ist, befindet sich das System auf dem Windows-Bildschirm "Out-of-Box-Experience" (OOBE).



## <a name="see-also"></a>Siehe auch

[Microsoft Teams Rooms-Hilfe](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Microsoft Teams Rooms verwalten](rooms-manage.md)
