---
title: Manuelles Aktualisieren eines Microsoft Teams rooms-Geräts
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
description: Erfahren Sie, wie Sie Ihr Microsoft Teams rooms-Gerät manuell auf eine bestimmte Version aktualisieren.
ms.openlocfilehash: fc5602aad6ffdb52ddd9f58c458b0fd6d2a625fd
ms.sourcegitcommit: 67782296062528bbeade5cb9074143fee0536646
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/24/2020
ms.locfileid: "49731393"
---
# <a name="manually-update-a-microsoft-teams-rooms-device"></a>Manuelles Aktualisieren eines Microsoft Teams rooms-Geräts

Die Microsoft Teams rooms-APP wird über den Microsoft Store verteilt. Updates für die APP werden während der nächtlichen Wartung automatisch aus dem Microsoft Store installiert. Dies ist die empfohlene Methode zum Abrufen von Updates. Es gibt jedoch einige Situationen, in denen das Gerät "Teams Rooms" keine Updates vom Microsoft Store erhalten kann. Beispielsweise können mit Sicherheitsrichtlinien keine Geräte eine Verbindung mit dem Internet herstellen oder zulassen, dass apps nicht aus dem Microsoft Store heruntergeladen werden können. Oder Sie können ein Gerät aktualisieren, bevor Sie das Setup durchführen, in dem der Microsoft Store nicht verfügbar ist.

Wenn Sie keine Updates aus dem Microsoft Store erhalten können, können Sie ein PowerShell-Skript für Offline-App-Updates verwenden, um Ihre Teams rooms-Geräte manuell auf eine neuere Version der APP Teams Rooms zu aktualisieren. Führen Sie die Schritte in diesem Artikel aus, um Ihre Teams rooms-Geräte manuell zu aktualisieren.

> [!NOTE]
> Dieser Vorgang kann nur ein Gerät für Teams-Chatrooms aktualisieren, wenn die Teams rooms-App bereits installiert ist. Sie kann nicht verwendet werden, um eine neue Installation durchzuführen. Sie kann auch nicht verwendet werden, um die APP auf eine ältere Version zu downgraden. Wenn Sie eine neue Installation der Teams rooms-App durchführen möchten, wenden Sie sich an den Hersteller Ihres Geräts, um entsprechende Medien zu erhalten, oder lesen Sie [Vorbereiten der Installationsmedien](console.md#prepare-the-installation-media).

## <a name="step-1-download-the-offline-app-update-script"></a>Schritt 1: Herunterladen des Offline-App-Updateskripts

Laden Sie zunächst die neueste Version des Offline-App-Updateskripts herunter. Klicken Sie zum Herunterladen des Skripts auf <https://go.microsoft.com/fwlink/?linkid=2151817> . Das Skript wird in den Standardordner "Downloads" auf Ihrem Gerät heruntergeladen.

Heruntergeladene Dateien werden möglicherweise von Windows als blockiert markiert. Wenn Sie das Skript ohne Interaktion ausführen müssen, müssen Sie das Skript freigeben. Gehen Sie wie folgt vor, um die Blockierung des Skripts aufzuheben:

1. Klicken Sie mit der rechten Maustaste auf die Datei im Datei-Explorer.
2. Klicken Sie auf **Eigenschaften** .
3. Auswählen der **Blockierung**
4. Klicken Sie auf **OK** .

Informationen zum Aufheben der Blockierung des Skripts mithilfe von PowerShell finden Sie unter [entsperren-Datei](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1).

Nachdem das Offline-App-Updateskript heruntergeladen wurde, übertragen Sie die Datei auf das Gerät "Teams Rooms". Sie können eine Datei auf das Gerät übertragen, indem Sie ein USB-Laufwerk verwenden oder auf die Datei über eine Netzwerkdateifreigabe zugreifen, während Sie sich im Administratormodus auf dem Gerät befinden. Achten Sie darauf, zu beachten, wo Sie die Datei auf dem Gerät speichern.

## <a name="step-2-run-the-script-to-update-the-teams-rooms-app"></a>Schritt 2: Ausführen des Skripts zum Aktualisieren der App "Teams Rooms"

Das Offline-App-Updateskript muss über eine Eingabeaufforderung mit erhöhten Rechten ausgeführt werden, während der Skype-Benutzer (der Benutzer, unter dem die app ausgeführt wird) noch angemeldet ist. Weitere Informationen zum Anmelden bei einem Administratorkonto, um die Eingabeaufforderung mit erhöhten Rechten zu verwenden, während der Skype-Benutzer noch angemeldet ist, finden Sie unter [Wechseln zum Administratormodus und zurück, wenn die Microsoft Teams rooms-app ausgeführt wird](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running).

Führen Sie die folgenden Schritte aus, um das Skript über eine Eingabeaufforderung mit erhöhten Rechten auszuführen:

1. Wechseln zum Administratormodus
2. Klicken Sie auf das Start Symbol, geben Sie **Eingabeaufforderung** ein, und wählen Sie dann **als Administrator ausführen** aus.
3. Führen Sie den folgenden Befehl `<path to script>` aus, wobei der vollständige Pfad zum Skript und der Name der Skriptdatei enthalten sind:

    ```console
    PowerShell -ExecutionPolicy Unrestricted "<path to script>"
    ```

Wenn sich die Skriptdatei beispielsweise in befindet `C:\Users\Admin\Downloads` und der Name der Skriptdatei lautet `MTR-Update-4.5.6.7.ps1` , führen Sie den folgenden Befehl aus:

```console
PowerShell -ExecutionPolicy Unrestricted "C:\Users\Admin\Downloads\MTR-Update-4.5.6.7.ps1"
```

Lassen Sie das Skript ausführen. Nach Abschluss des Skripts wird das Gerät des Teams rooms neu gestartet.

Sie können das Skript auch mithilfe der Remote-PowerShell ausführen. Weitere Informationen zum Verwenden von Remote-PowerShell mit Teams rooms-Geräten finden Sie unter [Remoteverwaltung mithilfe von PowerShell](rooms-operations.md#remote-management-using-powershell).

## <a name="step-3-verify-the-app-has-been-updated-successfully"></a>Schritt 3: überprüfen, ob die APP erfolgreich aktualisiert wurde

Wenn das Skript erfolgreich ausgeführt wird, wird das Gerät in die APP Teams rooms neu gestartet.

Wenn das Skript auf ein Problem stößt, zeigt es an, was das Problem in der Befehlszeile ist, und zeichnet die Ausgabe in einer Datei auf. Befolgen Sie alle Anweisungen, die vom Skript bereitgestellt werden. Wenn Sie sich an den Microsoft-Support wenden müssen, stellen Sie sicher, dass Sie die Protokolldatei zusammen mit der Supportanfrage angeben. Das Skript stellt Ihnen den Pfad zur Protokolldatei zur Verfügung.
