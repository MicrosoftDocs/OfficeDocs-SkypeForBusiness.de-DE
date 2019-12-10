---
title: Verwenden Sie das Wiederherstellungstools für Microsoft Teams Rooms
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
localization_priority: Normal
description: In diesem Artikel wird erläutert, wie Sie das Wiederherstellungstool für Microsoft Teams-Räume verwenden, mit denen Sie ein veraltetes System in einen unterstützten Zustand bringen.
ms.openlocfilehash: 79cdd7b2e3530570033083bdac7089e862f169ce
ms.sourcegitcommit: dc70fd277d9542d831741e14dba9ae22367210ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/09/2019
ms.locfileid: "39909461"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a>Verwenden Sie das Wiederherstellungstools für Microsoft Teams Rooms

In diesem Artikel wird erläutert, wie Sie das Wiederherstellungstool für Microsoft Teams-Räume verwenden, mit denen Sie ein veraltetes System in einen unterstützten Zustand bringen. Dieses Tool sollte angewendet werden, wenn die Microsoft Teams rooms-Konsole einen Fehler vom Typ "Systemkonfiguration veraltet" oder vor dem Durchführen einer [Wiederherstellung](https://docs.microsoft.com/microsoftteams/room-systems/room-systems-v2-operations#microsoft-teams-rooms-reset-factory-restore)des Zurücksetzens einer Drucktaste zeigt.

## <a name="prerequisites"></a>Voraussetzungen

Laden Sie das neueste [Microsoft Teams rooms-Installationspaket](https://go.microsoft.com/fwlink/?linkid=851168) herunter, und extrahieren Sie es auf einen USB-Speicherstick oder eine Netzwerkfreigabe, auf die das Microsoft Teams rooms-Gerät zugreifen kann.

> [!NOTE]
> Das Extrahieren der Dateien aus der MSI-Datei kann mit vielen Mitteln erfolgen. Jeder Mechanismus, der alle Dateien extrahiert und die Verzeichnisstruktur erhält, ist akzeptabel. Eine Möglichkeit besteht darin, den Befehl `msiexec /qn PathToMsi /qb TARGETDIR=PathToTarget` zu verwenden `PathToMsi` , der den vollständigen Pfad zum Microsoft Teams Room-Installationspaket `PathToTarget` darstellt, und stellt den vollständigen Pfad zu dem Ordner dar, in den die Dateien extrahiert werden sollen.

## <a name="running-the-tool"></a>Ausführen des Tools

1) Registrieren Sie sich auf Ihrem Microsoft Teams rooms-Gerät beim Administratorkonto, und starten Sie eine Eingabeaufforderung mit erhöhten Rechten.
2) Überprüfen Sie im Microsoft Teams rooms-Gerät, auf das `RecoveryTool.ps1 file`Sie zugreifen können, das in den Dateien enthalten ist, die aus dem Installationspaket für Microsoft Teams rooms extrahiert wurden. Das Kit befindet sich auf der Netzwerkfreigabe oder dem USB-Laufwerk, das bei der Vorbereitung von Voraussetzungen verwendet wird.
3) Ausführen `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.
4) Wenn Sie eine Factory-Wiederherstellung durchführen:
   - Wenn Sie vom Skript dazu aufgefordert werden, wählen Sie Option 2: **Zurücksetzen**aus.
   - Wenn BitLocker aktiviert ist, folgen Sie den Anweisungen am Ende der Skriptausgabe, um Sie zu deaktivieren.
   - Durchführen der Factory-Wiederherstellung
      - Öffnen Sie die app " **Einstellungen** ", und wählen Sie **#a0 Sicherheit aktualisieren** aus.
      - Navigieren Sie zur Registerkarte **Wiederherstellen** .
      - Wählen Sie unter **diesen PC zurücksetzen die**Option **Erste Schritte** aus.
      - Wählen Sie **alles entfernen**und dann **weiter** und **Zurücksetzen** aus.
      - Das System wird mehrmals neu gestartet. Wenn der Reset abgeschlossen ist, befindet sich das System auf dem Windows-OOBE-Bildschirm.
5) Wenn Sie ein veraltetes System reparieren:
    - Wenn Sie vom Skript dazu aufgefordert werden, wählen Sie Option 1: **Reparieren**aus.
    - Starten Sie nach Abschluss das Microsoft Teams rooms-Gerät neu. Sie wird automatisch neu gestartet und beim zweiten Mal wieder vollständig wiederhergestellt.

> [!NOTE]
> Es gibt ein bekanntes Problem, bei dem die Microsoft Teams-Räume unbrauchbar werden können, wenn die Option **meine Dateien beibehalten-apps und Einstellungen entfernt, aber Ihre persönlichen Dateien beibehalten** aktiviert ist, während des Windows-Reset-Vorgangs. Verwenden Sie diese Option *nicht* .

## <a name="see-also"></a>Siehe auch

[Microsoft Teams Rooms-Hilfe](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Microsoft Teams Rooms verwalten](skype-room-systems-v2.md)
