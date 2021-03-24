---
title: Beheben von Problemen bei Installation und Update von Microsoft Teams unter Windows
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: lenatarhun
ms.topic: article
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Hier erfahren Sie, wie Sie Probleme mit Installation und Update der Teams-Desktopclient-App unter Windows beheben.
ms.openlocfilehash: 283b1818789624428aa772a4d71360a07eed6f00
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097551"
---
# <a name="troubleshoot-microsoft-teams-installation-and-update-issues-on-windows"></a>Beheben von Problemen bei Installation und Update von Microsoft Teams unter Windows

Dieser Artikel enthält Anleitungen zu Diagnose und Problembehandlung bei Installations- und Updateproblemen für die Teams-Desktopclient-App unter Windows.

## <a name="check-whether-teams-is-updated-successfully"></a>Überprüfen, ob Teams erfolgreich aktualisiert wurde

Führen Sie die folgenden Schritte aus, um zu überprüfen, ob Teams erfolgreich installiert wurde.

1. Wählen Sie in Teams Ihr Profilbild aus, und klicken Sie auf **Info** > **Version**.
2. Klicken Sie im selben Menü auf **Nach Updates suchen**.
3. Warten Sie, bis oben in der App das Banner angezeigt wird, dass darauf hinweist, dass eine "Aktualisierung" von Teams erforderlich ist. Der Link sollte ungefähr eine Minute später angezeigt werden, während dieser Vorgang die neue Version von Teams herunterlädt. Das Banner informiert Sie auch darüber, ob Sie bereits die neueste Version ausführen. In diesem Fall ist keine Aktualisierung erforderlich.
4. Klicken Sie im Banner auf den Link "Aktualisieren".
5. Warten Sie, bis Teams neu gestartet wird, und wiederholen Sie dann Schritt 1, um zu überprüfen, ob die App aktualisiert wurde.

Wenn eine Fehlermeldung angezeigt wird oder die Versionsnummer mit der in Schritt 4 identisch ist, ist der Updatevorgang fehlgeschlagen.

## <a name="troubleshoot-installation-and-update-issues"></a>Problembehandlung bei Problemen mit Installation und Update

### <a name="troubleshoot-installation-issues"></a>Behandeln von Installationsproblemen

Bei der Installation von Teams protokolliert das Teams-Installationsprogramm die Abfolge von Ereignissen in "%LocalAppData%\SquirrelTemp\SquirrelSetup.log". Zuerst sollten Sie nach einer Fehlermeldung oder einer Anrufliste am Ende des Protokolls suchen. Beachten Sie, dass Aufruflisten am Anfang des Protokolls möglicherweise nicht bedeuten, dass ein Installationsproblem vorliegt. Es kann einfacher sein, Ihr Protokoll mit einem Protokoll einer erfolgreichen Installation (ggf. auf einem anderen Computer) zu vergleichen, um zu sehen, was zu erwarten ist.

Wenn die Ursache nicht in "SquirrelSetup.log " aufgeführt ist, oder wenn Sie weitere Informationen benötigen, um das Problem zu beheben, lesen Sie [Erfassen und Analysieren von Anwendungs- und Systemprotokollen](#collect-and-analyze-application-and-system-logs).

### <a name="troubleshoot-update-issues"></a>Behandeln von Problemen beim Update

Wenn Teams erfolgreich installiert wurde, wechselt der Protokollspeicherort von „%LocalAppData%\SquirrelTemp“ zu „%AppData%\Microsoft\Teams“. An diesem Speicherort befinden sich zwei interessante Protokolldateien: "SquirrelSetup.log" und "logs.txt".

- Die Datei "SquirrelSetup.log" an diesem Speicherort wurde von "Update.exe" geschrieben, einer ausführbaren Datei, die die Teams-App wartet.
- Die Datei "Logs.txt" wird von der Teams-App (speziell "Teams.exe") verwendet, um wichtige Anwendungsereignisse aufzuzeichnen. Sie enthält wahrscheinlich Fehlerinformationen.

Diese Protokolldateien enthalten personenbezogene Informationen (Personally Identifiable Information, PII) und werden daher nicht an Microsoft gesendet.

Teams kann (je nach Richtlinie) den Aktualisierungsvorgang automatisch starten, oder Benutzer können manuell nach Updates suchen, indem sie zu Ihrem Profilbild wechseln und **Nach Updates suchen** auswählen. Beide Methoden verwenden die folgende Ereignissequenz.

1. **Nach Updates suchen**. Teams erstellt eine Webanforderung und schließt die aktuelle App-Version sowie Informationen zum Bereitstellungsring ein. Das Ziel dieses Schritts besteht darin, den Downloadlink abzurufen. Fehler in diesem Schritt werden in "Logs.txt" protokolliert.
2. **Update herunterladen**. Teams lädt das Update mithilfe des in Schritt 1 abgerufenen Downloadlinks herunter. Nach Abschluss des Downloads ruft Teams "Update.exe" auf, um den Download bereitzustellen. Downloadfehler werden ebenfalls in "Logs.txt" protokolliert.
3. **Updates bereitstellen**. Die heruntergeladenen Inhalte werden überprüft und in einen temporären Ordner (%LocalAppData%\Microsoft\Teams\stage) entpackt. Dies wird durch "Update.exe" ausgeführt. Fehler in diesem Schritt werden in "SquirrelTemp.log" protokolliert.
4. **Update installieren**. Es gibt mehrere Möglichkeiten, Teams zu starten. Teams wird automatisch gestartet, wenn sich ein Benutzer anmeldet, oder Sie können Teams über eine Verknüpfung starten. In diesem Schritt überprüft "Update.exe" das Vorhandensein des Bereitstellungsordners, überprüft den Inhalt erneut und führt Dateivorgänge aus, um die Bereitstellung der App aufzuheben. Der alte Anwendungsordner in "%LocalAppData%\Microsoft\Teams\current" wird auf "%LocalAppData%\Microsoft\Teams\previous" gesichert, und der Bereitstellungsordner wird in "current" umbenannt. Fehler in diesem Schritt werden in "SquirrelTemp.log" protokolliert.

Wenn "SquirrelTemp.log" oder "Logs.txt" nicht genügend Informationen enthalten, um die zugrundeliegende Ursache zu ermitteln, und Sie weitere Informationen zur Behebung des Problems benötigen, gehen Sie zu [Erfassen und Analysieren von Anwendungs- und Systemprotokollen](#collect-and-analyze-application-and-system-logs).

## <a name="collect-and-analyze-application-and-system-logs"></a>Erfassen und Analysieren von Anwendungs- und Systemprotokollen

In diesem Abschnitt wird beschrieben, wie Anwendungs- und Systemprotokolle erfasst und analysiert werden, um umfassendere Informationen zur Problembehandlung zu erhalten. Sie verwenden die Sysinternals-Tools, um diese Schritte auszuführen. Weitere Informationen hierzu finden Sie unter [Windows Sysinternals](/sysinternals/).

### <a name="collect-logs"></a>Protokolle erfassen

1. Laden Sie die [Sysinternals-Tools](https://download.sysinternals.com/files/SysinternalsSuite.zip) herunter.
2. Extrahieren Sie die ZIP-Datei in den Ordner "%TEMP%" auf dem lokalen Laufwerk.
3. Öffnen Sie eine Eingabeaufforderung mit erhöhten Rechten, und gehen Sie dann folgendermaßen vor:

    1. Führen Sie die folgenden Schritte aus, um zu Ihrem Ordner "Temp" zu wechseln:

        ```console
        cd /d %TEMP%
        ```
    2. Kopieren Sie die Setup- und Anwendungsprotokolle. Je nachdem, wo der Fehlerauftritt, sind einige dieser Protokolle möglicherweise nicht vorhanden.

        ```console
        copy %LocalAppData%\SquirrelTemp\SquirrelSetup.log SquirrelSetup.log
        copy %AppData%\Microsoft\Teams\logs.txt logs.txt
        copy %LocalAppData%\Microsoft\Teams\SquirrelSetup.log SquirrelSetup_Teams.log
        ```
    3. Führen Sie die folgenden Schritte aus, um die geöffneten Handles aufzuzeichnen.

        ```console
        handle > handles.txt
        ```

    4. Führen Sie die folgenden Schritte aus, um die geöffneten DLLs aufzuzeichnen.

        ```console
        listdlls -v Teams > dlls.txt
        ```
    5. Führen Sie die folgenden Schritte aus, um die laufenden Treiber zu erfassen.

        ```console
        driverquery /v > driverquery.txt
        ```

    6. Führen Sie die folgenden Schritte aus, um die ACLs (Access Control Lists) des Ordners "Teams" zu erfassen.

        ```console 
        icacls %LOCALAPPDATA%\Microsoft\Teams /save icacls.txt /T
        ```

### <a name="analyze-logs-for-advanced-users"></a>Protokolle analysieren (für fortgeschrittene Benutzer)

Eine fehlgeschlagene Aktualisierung kann zu einem unvorhersehbaren App-Verhalten führen. So können Benutzer beispielsweise Teams nicht mehr beenden, verwenden weiter die veraltete Version von Teams oder können Teams nicht starten. Wenn während einer Aktualisierung ein Problem auftritt, suchen Sie die Ursache zunächst in "SquirrelTemp.log". Nachfolgend werden die verschiedenen Arten von Updatefehlern, vom häufigsten bis zum seltensten Fehler, aufgelistet, und es wird beschrieben, wie sie mithilfe von Protokollen analysiert und behandelt werden.

#### <a name="unable-to-exit-teams"></a>Teams kann nicht beendet werden

Wenn Teams feststellt, dass es auf eine neuere Version aktualisiert werden muss, wird die neue App heruntergeladen und bereitgestellt. Dann wird auf eine Möglichkeit zu einem Neustart gewartet, wenn der Computer im Leerlauf ist. Ein häufiges Problem während dieses Prozesses ist, wenn ein anderer Prozess oder ein Dateisystemtreiber den Teams.exe-Prozess sperrt und dadurch das Beenden von "Teams.exe" verhindert. Die Teams-App kann daher nicht durch die neu heruntergeladene und bereitgestellte App ersetzt werden.

Problembehebungstipps:

- Um sich zu vergewissern, dass dieses Problem bei Ihnen auftritt, beenden Sie die Teams. (Klicken Sie dazu in der Taskleiste mit der rechten Maustaste auf Teams, und klicken Sie dann auf **Beenden**.) Öffnen Sie dann den Task-Manager in Windows, um zu überprüfen, ob noch eine Instanz von Teams ausgeführt wird.  
- Wenn Sie sich nicht an dem Computer befinden, auf dem das Problem auftritt, untersuchen Sie die Datei "SquirrelTemp.log", die von dem Computer, auf dem das Problem auftritt, erfasst wurde, und suchen Sie im Protokoll nach einem Eintrag "Programm: Der Prozess kann nicht beendet werden".
- Um festzustellen, was das Beenden von "Teams.exe" verhindert, sehen Sie sich die Protokolle "Dlls.txt" und "Handles.txt" an. Anhand dieser Protokolle können Sie die Prozesse ermitteln, die das Beenden von Teams verhindert haben.
- Eine weitere Ursache, die das Beenden von Teams möglicherweise verhindert, ist der Kernelmodus-Dateisystemfilter-Treiber. Verwenden Sie das SysInternals-Tool, [ProcDump](/sysinternals/downloads/procdump), um die Kernelmodusprozess-Speicherabbilddatei durch Ausführen von ```procdump -mk <pid>``` zu erfassen, wobei <pid> die vom Task-Manager abgerufene Prozess-ID ist. Sie können auch die Protokolldatei "Driverquery.txt" untersuchen, um die aktiven Filtertreiber anzuzeigen, die sich störend auf Teams auswirken können.
- Um dieses Problem zu beheben, starten Sie den Computer neu.

#### <a name="file-permissions"></a>Dateiberechtigungen

Teams erstellt während des gesamten Installations- und Aktualisierungsprozesses eine Reihe von Unterordnern und Dateien im Profil des Benutzers. Da die App und der Updater als Benutzer ohne erhöhte Rechte ausgeführt werden, müssen Lese- und Schreibberechtigungen für die folgenden Ordner gewährt werden:

|Ordner  |Verwendet von  |
|---------|---------|
|%LocalAppData%\SquirrelTemp     | Team-Installationsprogramm (z. B. Teams_Windows_x64.exe) während der Installationsphase        |
|%LocalAppData%\Microsoft\Teams  | Team-Updater (Update.exe) zum Extrahieren und Bereitstellen des Anwendungspakets während des Updateprozesses        |
|%AppData%\Microsoft\Teams   |  Team-App (Teams.exe) zum Speichern von Einstellungen, App-Status und dem (vorinstallierten) heruntergeladenen Updatepaket       |

Wenn Teams der Zugriff verweigert wird, weil es nicht in eine Datei schreiben kann, wirkt sich eine andere Softwareanwendung möglicherweise störend aus, oder ein Sicherheitsbeschreibungseintrag schränkt den Schreibzugriff auf einen Ordner ein.

Problembehebungstipps:

- Suchen Sie nach Nachweisen für "Zugriff verweigert" in "SquirrelTemp.log" oder "Logs.txt". Überprüfen Sie diese Dateien, um zu sehen, ob ein Versuch, in eine Datei zu schreiben, fehlgeschlagen ist.
- Öffnen Sie "Icacls.txt", und suchen Sie nach dem effektiven Zugriffssteuerungseintrag (ACE, Access Control Entry), der Schreiboperationen eines Benutzers, der kein Administrator ist, blockiert. Typischerweise befindet sich dieser in einem der DACL-Einträge. Weitere Informationen finden Sie in der [Dokumentation zu icacls](/windows-server/administration/windows-commands/icacls).

#### <a name="file-corrupted"></a>Beschädigte Datei

In einigen Fällen ändert Verschlüsselungssoftware Dateien im Ordner "%LocalAppData%\Microsoft\Teams", und verhindert dadurch den Start von Teams. Dies kann jederzeit geschehen, auch wenn die App nicht aktualisiert wird. Wenn eine Datei beschädigt ist, besteht leider die einzige Möglichkeit, dieses Problem zu beheben, darin, Teams zu deinstallieren und neu zu installieren.

> [!NOTE]
> Wenn Sie die zugrundeliegende Ursache des Problems mit keinem dieser Schritte ermitteln können, können Sie es mit einer [Prozessmonitor](/sysinternals/downloads/procmon)-Sitzung versuchen. Der Prozessmonitor ist ein Sysinternals-Tool, das den Zugriff auf die Registrierung und das Dateisystem aufzeichnet.

## <a name="related-topics"></a>Verwandte Themen

- [Beziehen von Clients für Teams](get-clients.md)
- [Teams-Clientupdates](teams-client-update.md)
- [Teams-Problembehandlung](/MicrosoftTeams/troubleshoot/teams)