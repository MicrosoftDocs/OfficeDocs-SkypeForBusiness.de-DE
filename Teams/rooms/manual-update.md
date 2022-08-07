---
title: Manuelles Aktualisieren eines Microsoft Teams-Räume Geräts
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
- Teams_ITAdmin_Rooms
description: Erfahren Sie, wie Sie Ihr Microsoft Teams-Räume Gerät manuell auf eine bestimmte Version aktualisieren.
ms.openlocfilehash: c3128f5b909901da0eb5578f1586aaad785b49a6
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2022
ms.locfileid: "67267640"
---
# <a name="manually-update-a-microsoft-teams-rooms-device"></a>Manuelles Aktualisieren eines Microsoft Teams-Räume Geräts

Die Microsoft Teams-Räume-App wird über den Microsoft Store verteilt. Aktualisierungen der App werden während der nachts durchgeführten Wartung automatisch aus dem Microsoft Store installiert. Dies ist die empfohlene Methode zum Abrufen von Updates. Es gibt jedoch einige Situationen, in denen ein Teams-Räume Gerät keine Updates aus dem Microsoft Store empfangen kann. Beispielsweise erlauben Sicherheitsrichtlinien möglicherweise nicht, dass Geräte eine Verbindung mit dem Internet herstellen oder dass Apps nicht aus dem Microsoft Store heruntergeladen werden können. Oder Sie möchten ein Gerät aktualisieren, bevor Sie das Setup ausführen, während dessen der Microsoft Store nicht verfügbar ist.

Wenn Sie keine Updates aus dem Microsoft Store erhalten können, können Sie ein PowerShell-Skript für das Offline-App-Update verwenden, um Ihre Teams-Räume Geräte manuell auf eine neuere Version der Teams-Räume-App zu aktualisieren. Führen Sie die Schritte in diesem Artikel aus, um Ihre Teams-Räume Geräte manuell zu aktualisieren.

> [!NOTE]
> Bei diesem Vorgang kann nur ein Teams-Räume Gerät aktualisiert werden, auf dem die Teams-Räume App bereits installiert ist. Es kann nicht zum Ausführen einer neu installierten Installation verwendet werden. Es kann auch nicht verwendet werden, um die App auf eine ältere Version herabzustufen. Wenn Sie eine neu installierte Teams-Räume-App ausführen möchten, wenden Sie sich an den Hersteller Ihres Geräts, um spezifische Medien zu erfahren.

## <a name="step-1-download-the-offline-app-update-script"></a>Schritt 1: Herunterladen des Offline-App-Updateskripts

Laden Sie zunächst die neueste Version des Offline-App-Updateskripts herunter. Klicken Sie auf , um <https://go.microsoft.com/fwlink/?linkid=2151817>das Skript herunterzuladen. Das Skript wird in den Standarddownloadordner auf Ihrem Gerät heruntergeladen.

Heruntergeladene Dateien können von Windows als blockiert markiert werden. Wenn Sie das Skript ohne Interaktion ausführen müssen, müssen Sie die Blockierung des Skripts aufheben. Gehen Sie wie folgt vor, um die Blockierung des Skripts aufzuheben:

1. Klicken Sie mit der rechten Maustaste auf die Datei in Explorer
2. Klicken Sie auf **"Eigenschaften".**
3. "**Blockierung aufheben**" auswählen
4. Klicken Sie auf **"OK".**

Informationen zum Aufheben der Blockierung des Skripts mithilfe von PowerShell finden Sie [unter "Blockierung aufheben"](/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1).

Nachdem das Skript für das Update der Offline-App heruntergeladen wurde, übertragen Sie die Datei auf das Teams-Räume Gerät. Sie können eine Datei auf das Gerät übertragen, indem Sie ein USB-Laufwerk verwenden oder von einer Netzwerkdateifreigabe aus auf die Datei zugreifen, während Sie sich im Admin-Modus auf dem Gerät befinden. Achten Sie darauf, zu beachten, wo Sie die Datei auf dem Gerät speichern.

## <a name="step-2-run-the-script-to-update-the-teams-rooms-app"></a>Schritt 2: Ausführen des Skripts zum Aktualisieren der Teams-Räume-App

Das Skript für das Update der Offline-App muss über eine Eingabeaufforderung mit erhöhten Rechten ausgeführt werden, während der Skype-Benutzer (der Benutzer, unter dem die App ausgeführt wird) weiterhin angemeldet ist. Weitere Informationen dazu, wie Sie sich bei einem Administratorkonto anmelden, um die Eingabeaufforderung mit erhöhten Rechten zu verwenden, während der Skype-Benutzer noch angemeldet ist, finden Sie unter [Wechseln zum Admin-Modus und zurück, wenn die Microsoft Teams-Räume-App abstürzt](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes).

Führen Sie die folgenden Schritte aus, um das Skript an einer Eingabeaufforderung mit erhöhten Rechten auszuführen:

1. Wechseln zum Admin Modus
2. Klicken Sie auf das Symbol "Start", geben **Sie "Eingabeaufforderung"** ein, und wählen Sie dann "**Als Administrator ausführen" aus**.
3. Führen Sie den folgenden Befehl aus, der `<path to script>` den vollständigen Pfad zum Skript und den Namen der Skriptdatei enthält:

    ```console
    PowerShell -ExecutionPolicy Unrestricted "<path to script>"
    ```

Wenn sich die Skriptdatei beispielsweise in `C:\Users\Admin\Downloads`und der Name `MTR-Update-4.5.6.7.ps1`der Skriptdatei befindet, führen Sie den folgenden Befehl aus:

```console
PowerShell -ExecutionPolicy Unrestricted "C:\Users\Admin\Downloads\MTR-Update-4.5.6.7.ps1"
```

Zulassen, dass das Skript ausgeführt wird. Wenn der Vorgang abgeschlossen ist, startet das Skript das Teams-Räume Gerät neu.

Sie können das Skript auch mithilfe von Remote PowerShell ausführen. Weitere Informationen zur Verwendung von Remote PowerShell mit Teams-Räume Geräten finden Sie unter [Remoteverwaltung mithilfe von PowerShell](rooms-operations.md#remote-management-using-powershell).

## <a name="step-3-verify-the-app-has-been-updated-successfully"></a>Schritt 3: Überprüfen, ob die App erfolgreich aktualisiert wurde

Wenn das Skript erfolgreich ausgeführt wird, wird das Gerät in die Teams-Räume-App neu gestartet.

Wenn beim Skript ein Problem auftritt, gibt es an, was das Problem in der Befehlszeile ist, und zeichnet seine Ausgabe in einer Datei auf. Befolgen Sie alle Anweisungen, die das Skript bereitstellt. Wenn Sie sich an Microsoft-Support wenden müssen, schließen Sie die Protokolldatei zusammen mit der Supportanfrage ein. Das Skript stellt Ihnen den Pfad zur Protokolldatei bereit.
