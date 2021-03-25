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
description: In diesem Artikel wird erläutert, wie Sie das Wiederherstellungstool für Microsoft Teams Rooms verwenden, mit dem Sie ein veraltetes System in einen unterstützten Zustand bringen.
ms.openlocfilehash: 9a856312229ae326b4adbfd039ee0553213ca09c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117493"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a>Verwenden Sie das Wiederherstellungstools für Microsoft Teams Rooms

In diesem Artikel wird erläutert, wie Sie das Wiederherstellungstool für Microsoft Teams Rooms verwenden, mit dem Sie ein veraltetes System in einen unterstützten Zustand bringen. Dieses Tool sollte angewendet werden, wenn entweder auf der Microsoft Teams Rooms-Konsole ein Fehler "Systemkonfiguration veraltet" angezeigt wird, oder wenn vor dem Zurücksetzen der Pushschaltfläche die Factorywiederherstellung [ausgeführt wird.](./rooms-operations.md#microsoft-teams-rooms-reset-factory-restore)

## <a name="prerequisites"></a>Voraussetzungen

Laden Sie das neueste [Microsoft Teams Rooms-Installationspaket](https://go.microsoft.com/fwlink/?linkid=851168) herunter, und extrahieren Sie es auf einen USB-Speicherstick oder eine Netzwerkfreigabe, auf den das Microsoft Teams Rooms-Gerät zugreifen kann.

> [!NOTE]
> Das Extrahieren der Dateien aus dem MSI kann auf viele Verschiedenes durchgeführt werden. Alle Mechanismen, die alle Dateien extrahieren und deren Verzeichnisstruktur beibehalten, sind akzeptabel. Eine solche Möglichkeit besteht in der Verwendung des Befehls, der den vollständigen Pfad zum Microsoft Teams Room-Installationspaket darstellt, und stellt den vollständigen Pfad zu dem Ordner dar, in den die Dateien `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` `PathToMsi` extrahiert werden `PathToTarget` sollen.

## <a name="running-the-tool"></a>Ausführen des Tools

1) Melden Sie sich auf Ihrem Microsoft Teams Rooms-Gerät beim Administratorkonto an, und starten Sie eine Eingabeaufforderung mit erhöhten Eingabeaufforderungen.
2) Überprüfen Sie auf dem Microsoft Teams Rooms-Gerät, ob Sie auf das zugreifen können, das in den Dateien enthalten ist, die aus dem Microsoft Teams Rooms-Installationspaket `RecoveryTool.ps1 file` extrahiert wurden. Das Kit kann auf der Netzwerkfreigabe oder dem USB-Laufwerk gefunden werden, das zum Vorbereiten von Voraussetzungen verwendet wird.
3) Führen Sie `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"` aus.
4) So führen Sie eine Werkswiederherstellung aus:
   1. Wenn Sie vom Skript aufgefordert werden, wählen Sie Option 2: **Zurücksetzen aus.**
   2. Wenn BitLocker aktiviert ist, folgen Sie den Anweisungen am Ende der Skriptausgabe, um sie zu deaktivieren.
   3. Führen Sie die Werkswiederherstellung aus.
      1. Öffnen Sie die **App** "Einstellungen", und wählen **Sie & Sicherheit aktualisieren aus.**
      2. Navigieren Sie zur **Registerkarte Wiederherstellung.**
      3. Wählen **Sie unter Diesen PC zurücksetzen** die Option Erste Schritte **aus.**
      4. Wählen **Sie Alles entfernen** und dann **Weiter** und **Zurücksetzen aus.**
        > [!WARNING]
        > Das Microsoft Teams Rooms-Gerät kann unbrauchbar werden, wenn die Option Meine Dateien behalten – Apps und Einstellungen **entfernt,** aber Ihre persönlichen Dateien während des Windows-Reset-Vorgangs aktiviert bleibt. Wählen Sie diese Option nicht aus.
      5. Das System wird mehrmals neu gestartet. Nach Abschluss des Zurücksetzens befindet sich das System auf dem Windows-Bildschirm "out-of-box experience" (OOBE).



## <a name="see-also"></a>Siehe auch

[Microsoft Teams Rooms-Hilfe](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Microsoft Teams Rooms verwalten](rooms-manage.md)