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
localization_priority: Normal
description: 'Die Migration der Anwendung zum Parken von Anrufen umfasst die Bereitstellung des Skype for Business Server 2019-Pools mit beliebigen benutzerdefinierten Archivdateien, die in der Legacy Installation hochgeladen wurden, wobei die Einstellungen für den Service Level wiederhergestellt und alle Orbits für das Parken von Anrufen an den Skype for Business Server 2019-Pool neu ausgerichtet wurden. Wenn benutzerdefinierte Musikdateien im Pool konfiguriert wurden, müssen diese Dateien in den neuen Pool Skype for Business Server 2019 kopiert werden. Außerdem wird empfohlen, dass Sie alle benutzerdefinierten Music-on-Hold-Dateien für das Parken von Anrufen von einem anderen Ziel aus sichern, um eine separate Sicherungskopie aller benutzerdefinierten Musikarchiv Dateien aufzubewahren, die für das Parken von Anrufen hochgeladen wurden. Die angepassten Music-on-Hold-Dateien für die Anwendung zum Parken von Anrufen werden im Dateispeicher des Pools gespeichert. Wenn Sie die Audiodateien aus einem Pool Dateispeicher in einen Skype for Business Server 2019-Dateispeicher kopieren möchten, verwenden Sie den Befehl xcopy mit den folgenden Parametern:'
ms.openlocfilehash: ded38ab600da4b277b1cdc83218833c26df081aa
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752817"
---
# <a name="migrate-call-park-application-settings"></a>Migrieren von Einstellungen für die Anwendung zum Parken von Anrufen

Die Migration der Anwendung zum Parken von Anrufen umfasst die Bereitstellung des Skype for Business Server 2019-Pools mit beliebigen benutzerdefinierten Musikarchiv Dateien, die in die Legacy Installation hochgeladen wurden, wobei die Einstellungen auf Serviceebene wiederhergestellt und alle Orbits für das Parken von Anrufen auf den Skype for Business Server 2019-Pool neu ausgerichtet werden. Wenn benutzerdefinierte Musikdateien im Pool konfiguriert wurden, müssen diese Dateien in den neuen Pool Skype for Business Server 2019 kopiert werden. Darüber hinaus wird empfohlen, dass Sie alle benutzerdefinierten Music-on-Hold-Dateien für das Parken von Anrufen an ein anderes Ziel sichern, um eine separate Sicherungskopie aller benutzerdefinierten Musikarchiv Dateien aufzubewahren, die für das Parken von Anrufen hochgeladen wurden. Die angepassten Music-on-Hold-Dateien für die Anwendung zum Parken von Anrufen werden im Dateispeicher des Pools gespeichert. Wenn Sie die Audiodateien aus einem Pool Dateispeicher in einen Skype for Business Server 2019-Dateispeicher kopieren möchten, verwenden Sie den Befehl **xcopy** mit den folgenden Parametern: 

```console
Xcopy <Source: legacy Pool CPS File Store Path> <Destination: Skype for Business Server 2019 Pool CPS File Store Path>
```

```console
Example usage:  Xcopy "<legacy File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Skype for Business Server 2019 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

Wenn alle benutzerdefinierten Audiodateien in den Dateispeicher Skype for Business Server 2019 kopiert wurden, müssen die Anwendung zum Parken von Anrufen Einstellungen des Skype for Business Server 2019-Pools konfiguriert werden, und die dem Legacy Pool zugeordneten orbitbereiche für das Parken von anrufen müssen dem Skype for Business Server 2019-Pool neu zugewiesen werden.

Die Anwendung zum Parken von Anrufen Einstellungen umfassen den Schwellenwert für das Pickup-Timeout, das Aktivieren oder Deaktivieren von Wartemusik, die maximale Anzahl von Anruf Angriffen und die Timeout Anforderung. Sie müssen Anwendung zum Parken von Anrufen Einstellungen verwalten, indem Sie das Cmdlet "CsCpsConfiguration" mithilfe der Skype for Business Server **-** Verwaltungsshell ausführen. Die Anwendung zum Parken von Anrufen Einstellungen können nicht mithilfe der Skype for Business Server-Systemsteuerung verwaltet werden. 

## <a name="reconfigure-the-call-park-service-settings"></a>Erneutes Konfigurieren der Einstellungen für den Dienst zum Parken von Anrufen

1. Öffnen Sie im Skype for Business Server 2019 Front-End-Server die Skype for Business Server Verwaltungsshell.

2. Geben Sie an der Befehlszeile Folgendes ein:

    > [!NOTE]
    > Wenn Ihre Skype for Business Server 2019-Anwendung zum Parken von Anrufen Einstellungen mit den Legacy Einstellungen identisch sind, können Sie diesen Schritt überspringen. Wenn Anwendung zum Parken von Anrufen Einstellungen für die Skype for Business Server 2019-und Legacy Umgebungen unterschiedlich sind, verwenden Sie das unten aufgeführte Cmdlet als Vorlage, um diese Änderungen zu aktualisieren. 

   ```PowerShell
   Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"
   ```

Zum erneuten Zuweisen aller orbitbereiche zum Parken von Anrufen vom Legacy Pool zum Pool Skype for Business Server 2019 können Sie entweder die Skype for Business Server-Systemsteuerung oder die Skype for Business Server Verwaltungsshell verwenden. 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-control-panel"></a>Neuzuweisen aller Umlaufbahn Bereiche für das Parken von Anrufen mithilfe Skype for Business Server Systemsteuerung

1. Öffnen Sie Skype for Business Server Systemsteuerung.

2. Wählen Sie im linken Bereich **VoIP-Funktionen** aus.

3. Wählen Sie die Registerkarte **Parken von Anrufen** aus. 

4. Bearbeiten Sie für jeden orbitbereich für das Parken von anrufen, der einem Legacy Pool zugewiesen ist, die Einstellung **FQDN of Destination Server** , und wählen Sie den Pool Skype for Business Server 2019 aus, der die Anforderungen für das Parken von Anrufen verarbeiten soll. 

5. Klicken Sie auf **Commit ausführen**, um Ihre Änderungen zu speichern. 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-management-shell"></a>Alle Bereiche des Orbits für das Parken von Anrufen mit Skype for Business Server Verwaltungsshell neu zuweisen

1. Öffnen Sie Skype for Business Server Management Shell.

2. Geben Sie an der Befehlszeile Folgendes ein:

   ```PowerShell
   Get-CsCallParkOrbit
   ```

    Dieses Cmdlet listet alle Bereiche für den Anrufparkorbit in der Bereitstellung auf. Alle Orbits für das Parken von anrufen, bei denen die Parameter **CallParkServiceId** und **CallParkServerFqdn** als Legacy Pool festgelegt sind, müssen neu zugewiesen werden. 

    Geben Sie an der Befehlszeile Folgendes ein, um den Legacy Orbit für das Parken von Anrufen im Skype for Business Server 2019-Pool neu zuzuweisen:

   ```PowerShell
   Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Skype for Business Server 2019 Pool FQDN>"
   ```

Nach dem erneuten Zuweisen aller orbitbereiche für das Parken von Anrufen zum Pool Skype for Business Server 2019 wird der Migrationsprozess für die Anwendung zum Parken von Anrufen abgeschlossen, und der Skype for Business Server 2019-Pool verarbeitet alle zukünftigen Anforderungen für das Parken von anrufen.


