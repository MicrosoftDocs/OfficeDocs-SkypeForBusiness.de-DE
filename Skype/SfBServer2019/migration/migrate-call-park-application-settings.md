---
title: Migrieren von Einstellungen für die Anwendung zum Parken von Anrufen
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 'Die Migration der Anwendung zum Parken von Anrufen umfasst die Bereitstellung des Skype for Business Server 2019-Pools mit benutzerdefinierten Wartemusikdateien, die in der Legacyinstallation hochgeladen wurden, das Wiederherstellen der Einstellungen auf Dienstebene und das Retargeting aller Orbits für das Parken von Anrufen in den Pool Skype for Business Server 2019. Wenn angepasste Dateien für die Wartemusik im Pool konfiguriert wurden, müssen diese Dateien in den neuen Pool Skype for Business Server 2019 kopiert werden. Darüber hinaus wird empfohlen, dass Sie alle dateien für das Parken von "Wartemusik" für das Parken von Anrufen von einem anderen Ziel aus sichern, um eine separate Sicherungskopie aller angepassten Wartemusikdateien beizubehalten, die für das Parken von Anrufen hochgeladen wurden. Die angepassten Wartemusikdateien für die Anwendung zum Parken von Anrufen werden im Dateispeicher des Pools gespeichert. Um die Audiodateien aus einem Pooldateispeicher in einen Skype for Business Server 2019-Dateispeicher zu kopieren, verwenden Sie den Xcopy-Befehl mit den folgenden Parametern:'
ms.openlocfilehash: b8d2c5a898ca9ce4c2c1e8be4b9cbf3e7355a8cc
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58597539"
---
# <a name="migrate-call-park-application-settings"></a>Migrieren von Einstellungen für die Anwendung zum Parken von Anrufen

Die Migration der Anwendung zum Parken von Anrufen umfasst die Bereitstellung des Skype for Business Server 2019-Pools mit benutzerdefinierten Musik-on-Hold-Dateien, die in der Legacyinstallation hochgeladen wurden, das Wiederherstellen der Einstellungen auf Dienstebene und das erneute Ausrichten aller Orbits für das Parken von Anrufen in den Pool Skype for Business Server 2019. Wenn angepasste Dateien für die Wartemusik im Pool konfiguriert wurden, müssen diese Dateien in den neuen Pool Skype for Business Server 2019 kopiert werden. Darüber hinaus wird empfohlen, dass Sie alle benutzerdefinierten Wartemusikdateien für das Parken von Anrufen an ein anderes Ziel sichern, um eine separate Sicherungskopie aller angepassten Wartemusikdateien beizubehalten, die für das Parken von Anrufen hochgeladen wurden. Die angepassten Wartemusikdateien für die Anwendung zum Parken von Anrufen werden im Dateispeicher des Pools gespeichert. Um die Audiodateien aus einem Pooldateispeicher in einen Skype for Business Server 2019-Dateispeicher zu kopieren, verwenden Sie den **Xcopy-Befehl** mit den folgenden Parametern: 

```console
Xcopy <Source: legacy Pool CPS File Store Path> <Destination: Skype for Business Server 2019 Pool CPS File Store Path>
```

```console
Example usage:  Xcopy "<legacy File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Skype for Business Server 2019 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

Wenn alle angepassten Audiodateien in den Skype for Business Server 2019-Dateispeicher kopiert wurden, müssen die Einstellungen der Anwendung zum Parken von Anrufen des Skype for Business Server 2019-Pools konfiguriert werden, und die Orbitbereiche für das Parken von Anrufen, die dem Legacypool zugeordnet sind, müssen dem Pool Skype for Business Server 2019 neu zugewiesen werden.

Die Einstellungen der Anwendung zum Parken von Anrufen umfassen den Timeoutschwellenwert für die Annahme, das Aktivieren oder Deaktivieren von Wartemusik, die maximalen Anrufannahmeversuche und die Timeoutanforderung. Sie müssen die Einstellungen der Anwendung zum Parken von Anrufen mithilfe der Skype for Business Server Verwaltungsshell verwalten, um das Cmdlet **"Set-CsCpsConfiguration"** auszuführen. Sie können die Einstellungen der Anwendung zum Parken von Anrufen nicht über die Skype for Business Server Systemsteuerung verwalten. 

## <a name="reconfigure-the-call-park-service-settings"></a>Erneutes Konfigurieren der Einstellungen für den Dienst zum Parken von Anrufen

1. Öffnen Sie auf dem Front-End-Server Skype for Business Server 2019 die Skype for Business Server Verwaltungsshell.

2. Geben Sie an der Befehlszeile Folgendes ein:

    > [!NOTE]
    > Wenn Ihre Einstellungen für die Skype for Business Server 2019-Anwendung zum Parken von Anrufen mit den älteren Einstellungen identisch sind, können Sie diesen Schritt überspringen. Wenn sich die Einstellungen der Anwendung zum Parken von Anrufen für die Skype for Business Server 2019 und ältere Umgebungen unterscheiden, verwenden Sie das folgende Cmdlet als Vorlage, um diese Änderungen zu aktualisieren. 

   ```PowerShell
   Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"
   ```

Um alle Orbitbereiche für das Parken von Anrufen vom Legacypool zum Skype for Business Server 2019-Pool neu zuzuweisen, können Sie entweder die Skype for Business Server Systemsteuerung oder die Skype for Business Server-Verwaltungsshell verwenden. 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-control-panel"></a>Neuzuweisen aller Orbitbereiche für das Parken von Anrufen mit Skype for Business Server Systemsteuerung

1. Öffnen Sie Skype for Business Server Systemsteuerung.

2. Wählen Sie im linken Bereich **VoIP-Funktionen** aus.

3. Wählen Sie die Registerkarte **Parken von Anrufen** aus. 

4. Bearbeiten Sie für jeden Orbitbereich für das Parken von Anrufen, der einem Legacypool zugewiesen ist, den **FQDN des Zielservers,** und wählen Sie den Skype for Business Server 2019-Pool aus, der die Anforderungen für das Parken von Anrufen verarbeitet. 

5. Klicken Sie auf **Commit ausführen**, um Ihre Änderungen zu speichern. 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-management-shell"></a>Neuzuweisen aller Orbitbereiche für das Parken von Anrufen mit Skype for Business Server Verwaltungsshell

1. Öffnen Sie Skype for Business Server Verwaltungsshell.

2. Geben Sie an der Befehlszeile Folgendes ein:

   ```PowerShell
   Get-CsCallParkOrbit
   ```

    Dieses Cmdlet listet alle Bereiche für den Anrufparkorbit in der Bereitstellung auf. Alle Orbits zum Parken von Anrufen, für die die Parameter **CallParkServiceId** und **CallParkServerFqdn** als Legacypool festgelegt sind, müssen neu zugewiesen werden. 

    Geben Sie an der Befehlszeile Folgendes ein, um die Legacy-Orbitbereiche für das Parken von Anrufen dem Skype for Business Server 2019-Pool neu zuzuweisen:

   ```PowerShell
   Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Skype for Business Server 2019 Pool FQDN>"
   ```

Nachdem alle Orbitbereiche für das Parken von Anrufen dem Skype for Business Server 2019-Pool neu zugewiesen wurden, wird der Migrationsprozess für die Anwendung zum Parken von Anrufen abgeschlossen, und der Pool Skype for Business Server 2019 verarbeitet alle zukünftigen Anforderungen für das Parken von Anrufen.


