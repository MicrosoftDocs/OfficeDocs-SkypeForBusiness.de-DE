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
description: In diesem Artikel wird beschrieben, wie Sie das Wiederherstellungstool für Microsoft Teams-Räume verwenden, mit dem Sie ein veraltetes System in einen unterstützten Zustand bringen.
ms.openlocfilehash: 9a856312229ae326b4adbfd039ee0553213ca09c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117493"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a>Verwenden Sie das Wiederherstellungstools für Microsoft Teams Rooms

In diesem Artikel wird beschrieben, wie Sie das Wiederherstellungstool für Microsoft Teams-Räume verwenden, mit dem Sie ein veraltetes System in einen unterstützten Zustand bringen. Dieses Tool sollte angewendet werden, wenn entweder in der Microsoft Teams-Räume-Konsole der Fehler "systemconfig out of date" angezeigt wird, oder bevor eine Zurücksetzungs-Factory für Push-Schaltflächen ausgeführt [wird.](./rooms-operations.md#microsoft-teams-rooms-reset-factory-restore)

## <a name="prerequisites"></a>Voraussetzungen

Laden Sie das neueste [Microsoft Teams-Räume herunter,](https://go.microsoft.com/fwlink/?linkid=851168) und extrahieren Sie es auf einen USB-Speicherstick oder eine Netzwerkfreigabe, auf den das Gerät Microsoft Teams-Räume kann.

> [!NOTE]
> Das Extrahieren der Dateien aus der MSI kann auf viele verschiedene Mittel durchgeführt werden. Jeder Mechanismus, mit dem alle Dateien extrahiert und die Verzeichnisstruktur erhalten wird, ist akzeptabel. So können Sie beispielsweise den Befehl verwenden, der den vollständigen Pfad zum Microsoft Teams Room-Installationspaket darstellt und den vollständigen Pfad zu dem Ordner darstellt, in dem die Dateien `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` `PathToMsi` extrahiert werden `PathToTarget` sollen.

## <a name="running-the-tool"></a>Ausführen des Tools

1) Melden Sie sich bei dem Administratorkonto auf Ihrem Microsoft Teams-Räume an, und starten Sie eine Eingabeaufforderung mit erhöhten Rechten.
2) Vergewissern Sie sich Microsoft Teams-Räume-Gerät, dass Sie auf den zugreifen können, der in den Dateien enthalten ist, die aus dem `RecoveryTool.ps1 file` Microsoft Teams-Räume-Installationspaket extrahiert werden. Das Kit finden Sie auf der Netzwerkfreigabe oder auf dem USB-Laufwerk, das bei der Vorbereitung der Voraussetzungen verwendet wird.
3) Führen Sie `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"` aus.
4) So führen Sie eine Factorywiederherstellung durch:
   1. Wenn Sie vom Skript dazu aufgefordert werden, wählen Sie Option 2: **Zurücksetzen aus.**
   2. Wenn BitLocker aktiviert ist, folgen Sie den Anweisungen am Ende der Skriptausgabe, um die Skriptausgabe zu deaktivieren.
   3. Führen Sie die Factorywiederherstellung aus.
      1. Öffnen  Sie die Einstellungen-App, und wählen **Sie Update & Security aus.**
      2. Navigieren Sie zur **Registerkarte Wiederherstellung.**
      3. Wählen **Sie unter Diesen PC zurücksetzen** die Option Erste Schritte **aus.**
      4. Wählen **Sie Alles entfernen**, dann **Weiter** und **Zurücksetzen aus.**
        > [!WARNING]
        > Das Microsoft Teams-Räume kann unbrauchbar **werden,** wenn die Option Meine Dateien behalten – Apps und Einstellungen entfernen, aber Ihre persönlichen Dateien behalten während des Vorgangs zum Zurücksetzen Windows aktiviert ist. Aktivieren Sie diese Option nicht.
      5. Das System wird mehrmals neu gestartet. Nach Abschluss des Reset-Vorgangs befindet sich das System Windows OOBE-Bildschirm (Out-of-Box Experience).



## <a name="see-also"></a>Siehe auch

[Microsoft Teams Rooms-Hilfe](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Microsoft Teams Rooms verwalten](rooms-manage.md)