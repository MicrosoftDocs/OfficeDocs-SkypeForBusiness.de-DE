---
title: Migrieren von Einstellungen für die Anwendung zum Parken von Anrufen
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Die Migration der Anwendung für den Anruf Park umfasst die Bereitstellung des Skype for Business Server 2019-Pools mit benutzerdefinierten Musikdateien, die in die Legacy Installation hochgeladen wurden, Wiederherstellen der Einstellungen für den Service Level und erneutes anvisieren aller Orbits des Anruf Parks an die Skype for Business Server 2019-Pool. Wenn benutzerdefinierte Musik-in-Warte-Dateien im Pool konfiguriert wurden, müssen diese Dateien in den neuen Skype for Business Server 2019-Pool kopiert werden. Darüber hinaus empfiehlt es sich, dass Sie alle für den Anruf Park angepassten Music-on-halten-Dateien von einem anderen Ziel aus sichern, um eine separate Sicherungskopie aller angepassten Music-on-halten-Dateien zu erhalten, die für den Anruf Park hochgeladen wurden. Die angepassten Music-on-halten-Dateien für die Anwendung "Parken" werden im Dateispeicher des Pools gespeichert. Wenn Sie die Audiodateien aus einem Pool Dateispeicher in einen Skype for Business Server 2019-Dateispeicher kopieren möchten, verwenden Sie den Befehl xcopy mit den folgenden Parametern:'
ms.openlocfilehash: b9e55bc76e718d499482fb21e029a0a74e8f207f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813583"
---
# <a name="migrate-call-park-application-settings"></a>Migrieren von Einstellungen für die Anwendung zum Parken von Anrufen

Die Migration der Anwendung "Parken des Anrufs" umfasst die Bereitstellung des Skype for Business Server 2019-Pools mit benutzerdefinierten Musik-in-situ-Dateien, die in die Legacy Installation hochgeladen wurden, Wiederherstellen der Einstellungen auf Dienstebene und erneutes Targeting für alle Orbits des Anruf Parks zum Skype for Business Server 2019-Pool. Wenn benutzerdefinierte Musik-in-Warte-Dateien im Pool konfiguriert wurden, müssen diese Dateien in den neuen Skype for Business Server 2019-Pool kopiert werden. Darüber hinaus empfiehlt es sich, dass Sie alle angefügten Music-on-Keep-Dateien auf einem anderen Ziel gesichert haben, um eine separate Sicherungskopie aller angepassten Music-on-halten-Dateien zu erhalten, die für den Anruf Park hochgeladen wurden. Die angepassten Music-on-halten-Dateien für die Anwendung "Parken" werden im Dateispeicher des Pools gespeichert. Wenn Sie die Audiodateien aus einem Pool Dateispeicher in einen Skype for Business Server 2019-Dateispeicher kopieren möchten, verwenden Sie den Befehl **xcopy** mit den folgenden Parametern: 

```
Xcopy <Source: legacy Pool CPS File Store Path> <Destination: Skype for Business Server 2019 Pool CPS File Store Path>
```

```
Example usage:  Xcopy "<legacy File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Skype for Business Server 2019 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

Wenn alle angepassten Audiodateien in den Skype for Business Server 2019-Dateispeicher kopiert wurden, müssen die Einstellungen für den Anruf Park des Skype for Business Server 2019-Pools konfiguriert und die Umlaufbahn Bereiche des Anruf Parks, die dem Legacy Pool zugeordnet sind, angegeben werden. muss dem Skype for Business Server 2019-Pool erneut zugewiesen werden.

Die Anwendungseinstellungen des Anruf Parks beinhalten den Schwellenwert für das Pickup-Zeitlimit, das Aktivieren oder Deaktivieren von Musik in Wartestellung, die maximale Anzahl von Anruf Angriffen und die Timeout Anforderung. Sie müssen die Einstellungen für die Anruf Park Anwendung verwalten, indem Sie die Skype for Business Server-Verwaltungsshell verwenden, um das Cmdlet " **Satz-CsCpsConfiguration** " auszuführen. Sie können die Einstellungen für den Anruf Park nicht über das Control Panel von Skype for Business Server verwalten. 

## <a name="reconfigure-the-call-park-service-settings"></a>Neukonfigurieren der Einstellungen für den Anruf Park Dienst

1. Öffnen Sie auf dem Front-End-Server von Skype for Business Server 2019 die Skype for Business Server-Verwaltungsshell.

2. Geben Sie an der Befehlszeile Folgendes ein:

    > [!NOTE]
    > Wenn die Anwendungseinstellungen Ihres Skype for Business Server 2019-Anrufs mit den Legacy-Einstellungen identisch sind, können Sie diesen Schritt überspringen. Wenn sich die Einstellungen für den Anruf Park für die Skype for Business Server 2019-und Legacy-Umgebungen unterscheiden, verwenden Sie das unten aufgeführte Cmdlet als Vorlage, um diese Änderungen zu aktualisieren. 

   ```PowerShell
   Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"
   ```

Wenn Sie alle orbitbereiche des Anruf Parks vom Legacy Pool zum Skype for Business Server 2019-Pool neu zuweisen möchten, können Sie entweder das Skype for Business Server Control Panel oder die Skype for Business Server-Verwaltungsshell verwenden. 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-control-panel"></a>Alle orbitbereiche für den Anruf Bereich über die Skype for Business Server-Systemsteuerung neu zuweisen

1. Öffnen Sie die Skype for Business Server-Systemsteuerung.

2. Wählen Sie im linken Bereich **sprach Features**aus.

3. Wählen Sie die Registerkarte **Anruf parken** aus. 

4. Bearbeiten Sie für jeden Orbit-Bereich, der einem Legacy Pool zugewiesen ist, den **FQDN der Zielserver** Einstellung, und wählen Sie den Skype for Business Server 2019-Pool aus, der die Anforderungen des Anruf Parks verarbeitet. 

5. Wählen Sie **Commit** aus, um die Änderungen zu speichern. 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-management-shell"></a>Erneutes Zuweisen aller orbitbereiche für den Anruf Bereich mithilfe der Skype for Business Server-Verwaltungsshell

1. Öffnen Sie die Skype for Business Server-Verwaltungsshell.

2. Geben Sie an der Befehlszeile Folgendes ein:

   ```PowerShell
   Get-CsCallParkOrbit
   ```

    Mit diesem Cmdlet werden alle orbitbereiche des Anruf Parks in der Bereitstellung aufgelistet. Alle Orbits des Anruf Parks, deren **CallParkServiceId** -und **CallParkServerFqdn** -Parameter als Legacy Pool festgelegt sind, müssen neu zugewiesen werden. 

    Geben Sie in der Befehlszeile Folgendes ein, um den Legacy-Anruf Park Orbit-Bereich dem Skype for Business Server 2019-Pool erneut zuzuweisen:

   ```PowerShell
   Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Skype for Business Server 2019 Pool FQDN>"
   ```

Nach der Neuzuweisung aller orbitbereiche für den Anruf Bereich zum Skype for Business Server 2019-Pool wird der Migrationsprozess für die Anwendung "Parken" abgeschlossen, und der Skype for Business Server 2019-Pool verarbeitet alle zukünftigen Anruf Park Anfragen.


