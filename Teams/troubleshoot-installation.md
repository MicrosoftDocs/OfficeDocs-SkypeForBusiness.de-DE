---
title: Beheben von Problemen mit der Installation und dem Update von Microsoft Teams unter Windows
author: lanachin
ms.author: v-lanac
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
description: Erfahren Sie, wie Sie Probleme mit der Installation und dem Update für die Desktop-Client-App für Teams unter Windows beheben können.
ms.openlocfilehash: f47edf351d6a55f57977fee823d670b749896049
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837625"
---
# <a name="troubleshoot-microsoft-teams-installation-and-update-issues-on-windows"></a>Beheben von Problemen mit der Installation und dem Update von Microsoft Teams unter Windows

Dieser Artikel enthält Anleitungen zum Diagnostizieren und behandeln von Problemen bei der Installation und dem Update für die Desktop Client-App für Teams, die unter Windows ausgeführt wird.

## <a name="check-whether-teams-is-updated-successfully"></a>Überprüfen, ob Teams erfolgreich aktualisiert wurden

Führen Sie die folgenden Schritte aus, um zu überprüfen, ob ein Team Update erfolgreich installiert wurde.

1. Wählen Sie in Teams Ihr Profilbild aus, und klicken Sie dann auf **über** > **Version**.
2. Klicken Sie im gleichen Menü auf auf **Updates überprüfen**.
3. Warten Sie auf das Banner oben in der APP, um anzugeben, dass eine "Aktualisierung" von Teams erforderlich ist. Der Link sollte etwa eine Minute später angezeigt werden, da dieser Vorgang die neue Version von Teams herunterlädt. Darüber hinaus können Sie über das Banner wissen, ob Sie bereits die neueste Version ausgeführt haben, aber es ist keine Aktualisierung erforderlich.
4. Klicken Sie im Banner auf den Link aktualisieren.
5. Warten Sie, bis Teams neu gestartet werden, und wiederholen Sie dann Schritt 1, um festzustellen, ob die APP aktualisiert wurde.

Wenn eine Fehlermeldung angezeigt wird oder die Versionsnummer mit der in Schritt 4 identisch ist, ist der Aktualisierungsvorgang fehlgeschlagen.

## <a name="troubleshoot-installation-and-update-issues"></a>Problembehandlung bei Problemen mit Installation und Update

### <a name="troubleshoot-installation-issues"></a>Behandeln von Problemen bei der Installation

Wenn Teams installiert ist, protokolliert das Team-Installationsprogramm die Abfolge von Ereignissen auf%LocalAppData%\SquirrelTemp\SquirrelSetup.log. Als erstes suchen Sie nach einer Fehlermeldung oder einem Aufruf Stapel am Ende des Protokolls. Beachten Sie, dass Aufruflisten am Anfang des Protokolls möglicherweise nicht bedeuten, dass ein Installationsproblem vorliegt. Es ist einfacher, das Protokoll von einer erfolgreichen Installation (sogar auf einem anderen Computer) mit dem Protokoll zu vergleichen, um zu sehen, was erwartet wird.

Wenn SquirrelSetup. log nicht die Ursache angibt oder wenn Sie weitere Informationen benötigen, um das Problem zu beheben, lesen Sie [sammeln und Analysieren von Anwendungs-und Systemprotokollen](#collect-and-analyze-application-and-system-logs).

### <a name="troubleshoot-update-issues"></a>Behandeln von Problemen mit Updates

Wenn Teams erfolgreich installiert wurden, wechselt der Protokollspeicherort von%LocalAppData%\SquirrelTemp zu%APPDATA%\Microsoft\Teams.. An diesem Speicherort gibt es zwei interessante Protokolldateien, SquirrelSetup. log und Logs. txt.

- Die Datei "SquirrelSetup. log" an diesem Speicherort wird von "Update. exe" geschrieben, die eine ausführbare Datei ist, die die Teams-App Dienstleistungen.
- Die Datei "Logs. txt" wird von der Teams-app (insbesondere "Teams. exe") zum Aufzeichnen von signifikanten Anwendungsereignissen verwendet. Sie enthält wahrscheinlich Fehlerinformationen.

Diese Protokolldateien enthalten personenbezogene Informationen (PII) und werden daher nicht an Microsoft gesendet.

Teams können den Updateprozess automatisch starten (je nach Richtlinie), oder Benutzer können manuell nach Updates suchen, indem Sie zu Ihrem Profilbild wechseln #a0 nach **Updates**suchen. Beide Methoden verwenden die folgende Abfolge von Ereignissen.

1. **Auf Updates überprüfen**. Teams erstellt eine Webanforderung und enthält die aktuelle App-Version und Informationen zum Bereitstellungs Ring. Das Ziel dieses Schritts besteht darin, den Download-Link zu erhalten. Ein Fehler bei diesem Schritt wird in "Logs. txt" protokolliert.
2. **Update herunterladen**. Teams downloadet das Update mithilfe des Download-Links, der in Schritt 1 abgerufen wurde. Wenn der Download abgeschlossen ist, ruft Teams Update. exe auf, um den Download zu inszenieren. Ein Downloadfehler wird auch in "Logs. txt" protokolliert.
3. **Stufen Sie das Update ein**. Der heruntergeladene Inhalt wird in einen zwischen Ordner,%LocalAppData%\Microsoft\Teams\stage), überprüft und entpackt, der von Update. exe ausgeführt wird. Fehler in diesem Schritt werden in SquirrelTemp. log protokolliert.
4. **Installieren Sie das Update**. Es gibt mehrere Möglichkeiten, um Teams zu starten. Das System startet automatisch Teams, wenn sich ein Benutzer anmeldet, oder Sie können Teams über eine Verknüpfung starten. In diesem Schritt überprüft Update. exe das vorhanden sein des Staging-Ordners, überprüft den Inhalt erneut und führt Dateivorgänge aus, um die APP zu deinstallieren. Der alte Anwendungsordner in%LocalAppData%\Microsoft\Teams\current wird auf%LocalAppData%\Microsoft\Teams\previous gesichert, und der Ordner "Stage" wird in "Current" umbenannt. Fehler in diesem Schritt werden in SquirrelTemp. log protokolliert.

Wenn SquirrelTemp. log oder Logs. txt nicht genügend Informationen enthält, um die zugrunde liegende Ursache zu ermitteln, und wenn Sie weitere Informationen benötigen, um das Problem zu beheben, gehen Sie zu [sammeln und Analysieren von Anwendungs-und Systemprotokollen](#collect-and-analyze-application-and-system-logs).

## <a name="collect-and-analyze-application-and-system-logs"></a>Sammeln und Analysieren von Anwendungs-und Systemprotokollen

In diesem Abschnitt wird beschrieben, wie Anwendungs-und Systemprotokolle gesammelt und analysiert werden, um umfassendere Informationen zur Problembehandlung zu erhalten. Sie verwenden Sysinternals-Tools, um diese Schritte auszuführen. Weitere Informationen finden Sie unter [Windows Sysinternals](https://docs.microsoft.com/sysinternals/).

### <a name="collect-logs"></a>Sammeln von Protokollen

1. Laden Sie die [Sysinternals-Tools](https://download.sysinternals.com/files/SysinternalsSuite.zip)herunter.
2. Extrahieren Sie die ZIP-Datei in den Ordner% Temp% auf dem lokalen Laufwerk.
3. Öffnen Sie eine Eingabeaufforderung mit erhöhten Rechten, und gehen Sie dann wie folgt vor:

    1. Führen Sie die folgenden Schritte aus, um zu Ihrem temporären Ordner zu wechseln:

        ```
        cd /d %TEMP%
        ```
    2. Kopieren Sie die Setup-und Anwendungsprotokolle. Beachten Sie, dass einige dieser Protokolle, abhängig vom Fehlerpunkt, möglicherweise nicht vorhanden sind.

        ```
        copy %LocalAppData%\SquirrelTemp\SquirrelSetup.log SquirrelSetup.log
        copy %AppData%\Microsoft\Teams\logs.txt logs.txt
        copy %LocalAppData%\Microsoft\Teams\SquirrelSetup.log SquirrelSetup_Teams.log
        ```
    3. Führen Sie die folgenden Schritte aus, um die geöffneten Handles zu erfassen.

        ```
        handle > handles.txt
        ```

    4. Führen Sie die folgenden Schritte aus, um die geöffneten DLLs zu erfassen.

        ```
        listdlls -v Teams > dlls.txt
        ```
    5. Führen Sie die folgenden Schritte aus, um die ausgeführten Treiber zu erfassen.

        ```
        driverquery /v > driverquery.txt
        ```

    6. Führen Sie die folgenden Schritte aus, um die Zugriffssteuerungslisten (Access Control Lists, ACLs) des Ordners "Teams" zu erfassen.

        ``` 
        icacls %LOCALAPPDATA%\Microsoft\Teams /save icacls.txt /T
        ```

### <a name="analyze-logs-for-advanced-users"></a>Analysieren von Protokollen (für erfahrene Benutzer)

Eine fehlgeschlagene Aktualisierung kann zu einem unvorhersehbaren App-Verhalten führen. Beispielsweise können Benutzer nicht in der Lage sein, Teams zu beenden, eine veraltete Version von Teams zu haben oder Teams zu starten. Wenn während eines Updates ein Problem auftritt, suchen Sie zuerst nach der Ursache, indem Sie SquirrelTemp. log finden. Nachfolgend finden Sie die verschiedenen Arten von Updatefehlern, die von den häufigsten bis zu den am wenigsten üblichen Typen aufgelistet sind, und wie Sie mithilfe von Protokollen analysiert und behoben werden können.

#### <a name="unable-to-exit-teams"></a>Teams können nicht beendet werden

Wenn Teams feststellt, dass Sie sich selbst auf eine neuere Version aktualisieren müssen, downloadet und inszeniert Sie die neue APP und wartet dann auf die Möglichkeit, sich bei der nächsten Leerlaufzeit des Computers neu zu starten. Ein häufiges Problem während dieses Vorgangs ist, wenn ein anderer Prozess oder ein Dateisystemtreiber den Prozess "Teams. exe" sperrt, wodurch "Teams. exe" nicht mehr beendet wird. Daher kann die app "Teams" nicht durch die neu heruntergeladene und inszenierte App ersetzt werden.

Tipps zur Problembehandlung:

- Um zu bestätigen, dass das Problem auftritt, beenden Sie Teams (Klicken Sie in der Taskleiste mit der rechten Maustaste auf Teams, und klicken Sie dann auf **Beenden**). Öffnen Sie dann den Task-Manager in Windows, um festzustellen, ob eine Instanz von Teams noch ausgeführt wird.  
- Wenn Sie sich nicht auf dem Computer befinden, auf dem dieses Problem auftritt, überprüfen Sie das SquirrelTemp. log auf dem Computer, auf dem dieses Problem auftritt, und suchen Sie nach einem "Programm: der Prozess kann im Protokoll nicht beendet werden".
- Um zu ermitteln, was verhindert, dass Teams. exe beendet wird, sehen Sie sich die DLLs. txt und Handles. txt-Protokolle an. Diese erläutern die Prozesse, die verhindern, dass Teams beendet werden.
- Ein weiterer Täter, der das Beenden von Teams verhindern kann, ist der Kernelmodus-Dateisystemfiltertreiber. Verwenden Sie das Sysinternals-Tool " [von procdump](https://docs.microsoft.com/sysinternals/downloads/procdump)", um den Kernelmodus-Prozess- ```procdump -mk <pid>```Dump zu <pid> sammeln, indem Sie ausführen, wobei die Prozess-ID im Task-Manager abgerufen wird. Sie können auch die driverquery. txt-Protokolldatei überprüfen, um die aktiven Filtertreiber anzuzeigen, die die Teams stören können.
- Wenn Sie diesen Zustand wiederherstellen möchten, starten Sie den Computer neu.

#### <a name="file-permissions"></a>Dateiberechtigungen

Teams erstellt während des Installations-und Aktualisierungsprozesses eine Reihe von Unterordnern und Dateien im Profil des Benutzers. Da die APP und der Updater als Benutzer ohne erhöhten Zugriff ausgeführt werden, müssen die Lese-und Schreibberechtigungen für die folgenden Ordner gewährt werden:

|Ordner  |Verwendet von  |
|---------|---------|
|%LocalAppData%\SquirrelTemp     | Teams-Installationsprogramm (beispielsweise Teams_Windows_x64. exe) während der Installationsphase        |
|%LocalAppData%\Microsoft\Teams  | Teams-Updater (Update. exe) zum Extrahieren und inszenieren des App-Pakets während des Updatevorgangs        |
|%AppData%\Microsoft\Teams   |  Teams-app (Teams. exe) zum Speichern von Einstellungen, App-Zuständen und des heruntergeladenen Updatepakets (Pre-Staging)       |

Wenn Teams der Zugriff verweigert wird, weil Sie nicht in eine Datei schreiben können, kann eine andere Softwareanwendung stören, oder ein Sicherheitsdeskriptor-Eintrag kann den Schreibzugriff auf einen Ordner einschränken.

Tipps zur Problembehandlung:

- Suchen Sie nach dem "Zugriff verweigert"-Beweis in SquirrelTemp. log oder Logs. txt. Überprüfen Sie diese Dateien, um festzustellen, ob versucht wurde, in eine Datei zu schreiben, die fehlgeschlagen ist.
- Öffnen Sie icacls. txt, und suchen Sie nach dem effektiven Zugriffssteuerungseintrag (Access Control Entry, ACE), der Schreibvorgänge durch einen Benutzer blockiert, der kein Administrator ist. In der Regel befindet sich dies in einem der DACL-Einträge. Weitere Informationen finden Sie in der [icacls-Dokumentation](https://docs.microsoft.com/windows-server/administration/windows-commands/icacls).

#### <a name="file-corrupted"></a>Datei beschädigt

In einigen Fällen kann die Verschlüsselungssoftware Dateien im Ordner "%LocalAppData%\Microsoft\Teams" ändern, wodurch verhindert wird, dass Teams gestartet werden. Dies kann zu einem beliebigen Zeitpunkt geschehen, auch wenn die APP nicht aktualisiert wird. Wenn eine Datei beschädigt ist, besteht die einzige Möglichkeit zur Wiederherstellung in diesem Zustand darin, Teams zu deinstallieren und erneut zu installieren.

> [!NOTE]
> Wenn Sie die zugrunde liegende Ursache des Problems mithilfe eines dieser Schritte nicht ermitteln können, sollten Sie eine [Prozess Monitor](https://docs.microsoft.com/sysinternals/downloads/procmon) Sitzung testen. Prozess Monitor ist ein Sysinternals-Tool, mit dem der Zugriff auf die Registrierung und das Dateisystem aufgezeichnet wird.

## <a name="related-topics"></a>Verwandte Themen

- [Beziehen von Clients für Teams](get-clients.md)
- [Teams-Clientupdates](teams-client-update.md)