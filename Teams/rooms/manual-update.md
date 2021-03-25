---
title: Manuelles Aktualisieren eines Microsoft Teams Rooms-Geräts
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
appliesto:
- Microsoft Teams
ms.reviewer: sohailta
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: Erfahren Sie, wie Sie Ihr Microsoft Teams Rooms-Gerät manuell auf eine bestimmte Version aktualisieren.
ms.openlocfilehash: 3353758fa36534994336fc81e0a759c8b9f3c678
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117513"
---
# <a name="manually-update-a-microsoft-teams-rooms-device"></a>Manuelles Aktualisieren eines Microsoft Teams Rooms-Geräts

Die Microsoft Teams Rooms-App wird über den Microsoft Store verteilt. Updates für die App werden während der nächtlichen Wartung automatisch aus dem Microsoft Store installiert. Dies ist die empfohlene Methode, um Updates zu erhalten. Es gibt jedoch situationen, in denen ein Team Rooms-Gerät keine Updates aus dem Microsoft Store erhalten kann. Sicherheitsrichtlinien ermöglichen z. B. nicht, dass Geräte eine Verbindung mit dem Internet herstellen oder apps aus dem Microsoft Store heruntergeladen werden. Oder Sie möchten ein Gerät aktualisieren, bevor Sie das Setup durchführen, während dessen der Microsoft Store nicht verfügbar ist.

Wenn Sie keine Updates aus dem Microsoft Store erhalten können, können Sie ein PowerShell-Skript für das Offline-App-Update verwenden, um Ihre Teams Rooms-Geräte manuell auf eine neuere Version der Teams Rooms-App zu aktualisieren. Führen Sie die Schritte in diesem Artikel aus, um Ihre Teams Rooms-Geräte manuell zu aktualisieren.

> [!NOTE]
> Bei diesem Vorgang kann ein Team Rooms-Gerät nur aktualisiert werden, wenn die Teams Rooms-App bereits installiert ist. Es kann nicht verwendet werden, um eine neue Installation durchzuführen. Sie kann auch nicht zum Herunterstufen der App auf eine ältere Version verwendet werden. Wenn Sie eine neue Installation der Teams Rooms-App durchführen möchten, wenden Sie sich an den Hersteller Ihres Geräts, um spezifische Medien zu erhalten, oder lesen Sie Vorbereiten [der Installationsmedien.](console.md#prepare-the-installation-media)

## <a name="step-1-download-the-offline-app-update-script"></a>Schritt 1: Herunterladen des Updateskripts für Offline-Apps

Laden Sie zuerst die neueste Version des Updateskripts für Offline-Apps herunter. Zum Herunterladen des Skripts klicken Sie auf <https://go.microsoft.com/fwlink/?linkid=2151817> . Das Skript wird in den Standardordner für Downloads auf Ihrem Gerät heruntergeladen.

Heruntergeladene Dateien werden möglicherweise von Windows als blockiert gekennzeichnet. Wenn Sie das Skript ohne Interaktion ausführen müssen, müssen Sie die Blockierung des Skripts aufheben. Zum Aufheben der Blockierung des Skripts gehen Sie wie folgt vor:

1. Klicken Sie mit der rechten Maustaste auf die Datei im Datei-Explorer.
2. Klicken Sie **auf Eigenschaften**
3. Wählen Sie **Blockierung aufheben aus.**
4. Klicken Sie **auf OK**

Informationen zum Aufheben der Blockierung des Skripts mit PowerShell finden Sie unter [Aufheben der Blockierungsdatei](/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1).

Nachdem das Updateskript der Offline-App heruntergeladen wurde, übertragen Sie die Datei auf das Gerät Teams Rooms. Sie können eine Datei auf das Gerät übertragen, indem Sie ein USB-Laufwerk verwenden oder über eine Netzwerkdateifreigabe auf die Datei zugreifen, während Sie sich im Administratormodus auf dem Gerät befinden. Beachten Sie unbedingt, wo Sie die Datei auf dem Gerät speichern.

## <a name="step-2-run-the-script-to-update-the-teams-rooms-app"></a>Schritt 2: Ausführen des Skripts zum Aktualisieren der Teams Rooms-App

Das Updateskript der Offline-App muss über eine Eingabeaufforderung mit erhöhten Rechten ausgeführt werden, während der Skype-Benutzer (der Benutzer, unter dem die App ausgeführt wird) noch angemeldet ist. Weitere Informationen dazu, wie Sie sich bei einem Administratorkonto anmelden, um die Eingabeaufforderung mit erhöhter Eingabeaufforderung zu verwenden, während der Skype-Benutzer noch angemeldet ist, finden Sie unter Wechseln in den Administratormodus und zurück, wenn die [Microsoft Teams Rooms-App ausgeführt wird.](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)

Führen Sie die folgenden Schritte aus, um das Skript über eine Eingabeaufforderung mit erhöhten Rechten auszuführen:

1. Wechseln in den Administratormodus
2. Klicken Sie auf das Symbol Start, geben Sie **Eingabeaufforderung** ein, und wählen Sie **dann Als Administrator ausführen aus.**
3. Führen Sie den folgenden Befehl aus, der den vollständigen Pfad `<path to script>` zum Skript und den Namen der Skriptdatei enthält:

    ```console
    PowerShell -ExecutionPolicy Unrestricted "<path to script>"
    ```

Wenn sich die Skriptdatei beispielsweise in befindet und der Skriptdateiname `C:\Users\Admin\Downloads` `MTR-Update-4.5.6.7.ps1` der ist, führen Sie den folgenden Befehl aus:

```console
PowerShell -ExecutionPolicy Unrestricted "C:\Users\Admin\Downloads\MTR-Update-4.5.6.7.ps1"
```

Ausführen des Skripts zulassen Nach Abschluss des Skripts wird das Gerät "Teams Rooms" neu gestartet.

Sie können das Skript auch mithilfe von Remote PowerShell ausführen. Weitere Informationen zur Verwendung von Remote PowerShell mit Teams Rooms-Geräten finden Sie unter [Remoteverwaltung mit PowerShell.](rooms-operations.md#remote-management-using-powershell)

## <a name="step-3-verify-the-app-has-been-updated-successfully"></a>Schritt 3: Überprüfen, ob die App erfolgreich aktualisiert wurde

Wenn das Skript erfolgreich ausgeführt wird, wird das Gerät in der Teams Rooms-App neu gestartet.

Wenn beim Skript ein Problem vor liegt, gibt es an, was das Problem in der Befehlszeile ist, und notiert die Ausgabe in einer Datei. Folgen Sie den Anweisungen, die das Skript bietet. Wenn Sie den Microsoft-Support kontaktieren müssen, stellen Sie sicher, dass Sie die Protokolldatei zusammen mit der Supportanfrage aufnehmen. Das Skript stellt Ihnen den Pfad zur Protokolldatei zur Verfügung.