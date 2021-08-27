---
title: Manuelles Aktualisieren Microsoft Teams-Räume Geräts
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
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
description: Erfahren Sie, wie Sie Ihr Microsoft Teams-Räume auf eine bestimmte Version aktualisieren.
ms.openlocfilehash: 36d5477ef84eb97971727314aa39ab19e4139488
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58578249"
---
# <a name="manually-update-a-microsoft-teams-rooms-device"></a>Manuelles Aktualisieren Microsoft Teams-Räume Geräts

Die Microsoft Teams-Räume-App wird über die App Microsoft Store. Updates für die App werden während der nächtlichen Wartung automatisch Microsoft Store installiert. dies ist die empfohlene Methode, um Updates zu erhalten. Es gibt jedoch einige Situationen, in denen ein Teams-Räume keine Updates vom Gerät empfangen Microsoft Store. Sicherheitsrichtlinien lassen beispielsweise möglicherweise nicht zu, dass Geräte eine Verbindung mit dem Internet herstellen, oder sie gestatten das Herunterladen von Apps aus Microsoft Store. Oder Sie möchten ein Gerät aktualisieren, bevor Sie das Setup durchführen, während dessen Microsoft Store nicht verfügbar ist.

Wenn Sie keine Updates aus dem Microsoft Store erhalten können, können Sie ein PowerShell-Skript für offline-App-Updates verwenden, um Ihre Teams-Räume-Geräte manuell auf eine neuere Version der Teams-Räume-App zu aktualisieren. Führen Sie die Schritte in diesem Artikel aus, um Ihre Teams-Räume zu aktualisieren.

> [!NOTE]
> Mit diesem Vorgang kann nur ein Teams-Räume aktualisiert werden, auf dem die Teams-Räume-App bereits installiert ist. Er kann nicht zum Ausführen einer neuen Installation verwendet werden. Sie kann auch nicht verwendet werden, um die App auf eine ältere Version herunterstufen. Wenn Sie eine neue Installation der Teams-Räume-App ausführen möchten, wenden Sie sich an den Gerätehersteller, um spezifische Medien zu erhalten, oder lesen Sie Vorbereiten [der Installationsmedien.](console.md#prepare-the-installation-media)

## <a name="step-1-download-the-offline-app-update-script"></a>Schritt 1: Herunterladen des Aktualisierungsskripts für die Offline-App

Laden Sie zuerst die neueste Version des Aktualisierungsskripts für Offline-Apps herunter. Um das Skript herunterzuladen, klicken Sie auf <https://go.microsoft.com/fwlink/?linkid=2151817> . Das Skript wird in den Standardordner für Downloads auf Ihrem Gerät heruntergeladen.

Heruntergeladene Dateien werden möglicherweise von anderen als blockiert Windows. Wenn Sie das Skript ohne Interaktion ausführen müssen, müssen Sie die Blockierung des Skripts aufheben. Gehen Sie zum Aufheben der Blockierung des Skripts wie folgt vor:

1. Klicken Sie im Datei-Explorer mit der rechten Maustaste auf die Datei.
2. Klicken Sie **auf "Eigenschaften".**
3. Wählen Sie **Blockierung aufheben aus.**
4. Klicken Sie **auf OK.**

Informationen zum Aufheben der Blockierung des Skripts mithilfe von PowerShell finden Sie unter [Aufheben der Blockierung von -Datei.](/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1)

Nachdem das Updateskript für die Offline-App heruntergeladen wurde, übertragen Sie die Datei auf das Teams-Räume Gerät. Sie können eine Datei auf das Gerät übertragen, indem Sie ein USB-Laufwerk verwenden oder über eine Netzwerkdateifreigabe auf die Datei zugreifen, während Sie sich auf dem Gerät im Administratormodus befinden. Notieren Sie sich unbedingt, wo Sie die Datei auf dem Gerät speichern.

## <a name="step-2-run-the-script-to-update-the-teams-rooms-app"></a>Schritt 2: Ausführen des Skripts zum Aktualisieren der Teams-Räume App

Das Skript für die Offline-App-Aktualisierung muss über eine Eingabeaufforderung mit erhöhten Rechten ausgeführt werden, während der Skype-Benutzer (der Benutzer, unter dem die App ausgeführt wird) noch angemeldet ist. Weitere Informationen dazu, wie Sie sich bei einem Administratorkonto anmelden, um die Eingabeaufforderung mit erhöhten Rechten zu verwenden, während der Skype-Benutzer noch angemeldet ist, finden Sie unter Wechseln in den Administratormodus und zurück, wenn die Microsoft Teams-Räume-App ausgeführt [wird.](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)

Führen Sie die folgenden Schritte aus, um das Skript über eine Eingabeaufforderung mit erhöhten Rechten auszuführen:

1. Wechseln in den Administratormodus
2. Klicken Sie auf das Symbol "Start", geben **Sie Eingabeaufforderung** ein, und wählen Sie **dann Als Administrator ausführen aus.**
3. Führen Sie den folgenden Befehl aus, der den vollständigen `<path to script>` Pfad zum Skript und den Namen der Skriptdatei enthält:

    ```console
    PowerShell -ExecutionPolicy Unrestricted "<path to script>"
    ```

Wenn sich die Skriptdatei beispielsweise in befindet und der Skriptdateiname `C:\Users\Admin\Downloads` `MTR-Update-4.5.6.7.ps1` der ist, führen Sie den folgenden Befehl aus:

```console
PowerShell -ExecutionPolicy Unrestricted "C:\Users\Admin\Downloads\MTR-Update-4.5.6.7.ps1"
```

Ausführen des Skripts zulassen Wenn das Skript fertig ist, wird das Skript neu gestartet, Teams-Räume gerät.

Sie können das Skript auch mithilfe der Remote-PowerShell ausführen. Weitere Informationen zur Verwendung von Remote-PowerShell mit Teams-Räume-Geräten finden Sie unter [Remoteverwaltung mithilfe von PowerShell.](rooms-operations.md#remote-management-using-powershell)

## <a name="step-3-verify-the-app-has-been-updated-successfully"></a>Schritt 3: Überprüfen, ob die App erfolgreich aktualisiert wurde

Wenn das Skript erfolgreich ausgeführt wird, führt das Gerät einen Neustart in der Teams-Räume aus.

Wenn das Skript ein Problem findet, wird das Problem in der Befehlszeile angegeben und seine Ausgabe in einer Datei aufgezeichnet. Folgen Sie den Anweisungen des Skripts. Wenn Sie sich an den Microsoft-Support wenden müssen, müssen Sie die Protokolldatei zusammen mit der Supportanfrage aufnehmen. Das Skript stellt Ihnen den Pfad zur Protokolldatei zur Verfügung.