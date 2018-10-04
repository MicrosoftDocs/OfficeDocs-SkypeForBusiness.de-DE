---
title: Migrieren von Einstellungen für das Parken von Anrufen
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Die Migration von der Anwendung einschließlich der Bereitstellung der Skype für Business Server 2019 Pool mit eine beliebige benutzerdefinierte Musik in der Warteschleife-Dateien, die in der Vorversion Installation hochgeladen wurden parken, zum Wiederherstellen der Einstellungen auf Poolebene Service und alle Parken Neuzuweisen umkreist die Skype für Business Server 2019 Pool. Wenn benutzerdefinierte Musik halten Dateien im Pool konfiguriert wurden, müssen diese Dateien in die neue Skype für Business Server 2019 Pool kopiert werden. Darüber hinaus wird empfohlen, dass Sie alle Parken sichern Musik halten-Dateien an ein anderes Ziel angepasst beibehalten eine separate Sicherungskopie der angepassten Musik halten Dateien, die hochgeladen wurden für das Parken. Die angepassten Musik halten-Dateien für die Anwendung zum Parken von Anrufen werden in den Dateispeicher des Pools gespeichert. Um die Audiodateien aus einem Pool-Dateispeicher in einen Skype für Business Server 2019 Dateispeicher kopieren möchten, verwenden Sie den Befehl Xcopy mit den folgenden Parametern:'
ms.openlocfilehash: bcc2da8192f0c94f20d11073b1b18439ccc9df61
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25370994"
---
# <a name="migrate-call-park-application-settings"></a>Migrieren von Einstellungen für das Parken von Anrufen

Die Migration von der Anwendung zum Parken einschließlich der Bereitstellung der Skype für Business Server 2019 Pool mit den benutzerdefinierten Musik halten-Dateien, die in der Vorversion installieren, die Einstellungen Servicelevel wiederherstellen und Zielversion alle Orbits für das Parken von Anrufen hochgeladen wurden um die Skype für Business Server 2019 Pool. Wenn benutzerdefinierte Musik halten Dateien im Pool konfiguriert wurden, müssen diese Dateien in die neue Skype für Business Server 2019 Pool kopiert werden. Darüber hinaus wird empfohlen, dass alle zum Parken von Anrufen zu sichern Musik halten Dateien an ein anderes Ziel angepasst beibehalten eine separate Sicherungskopie der angepassten Musik halten Dateien, die hochgeladen wurden für das Parken. Die angepassten Musik halten-Dateien für die Anwendung zum Parken von Anrufen werden in den Dateispeicher des Pools gespeichert. Um die Audiodateien aus einem Pool-Dateispeicher in einen Skype für Business Server 2019 Dateispeicher kopieren möchten, verwenden Sie den Befehl **Xcopy** mit den folgenden Parametern: 

```
Xcopy <Source: legacy Pool CPS File Store Path> <Destination: Skype for Business Server 2019 Pool CPS File Store Path>
```

```
Example usage:  Xcopy "<legacy File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Skype for Business Server 2019 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

Wenn alle benutzerdefinierte Audiodateien in der Skype für Business Server 2019 Dateispeicher kopiert wurden, orbit die Einstellungen für den Anwendung zum Parken von Anrufen über die Skype für Business Server 2019 Pool konfiguriert werden muss, und die Parken Bereiche, die dem vorversionspool zugeordnet sind die Skype für Business Server 2019 Pool zugewiesen werden muss.

Einstellungen für die Parken enthalten den Timeoutschwellenwert pickup aktivieren oder Deaktivieren von wartemusik, die maximale pickup Anrufversuche, und die Timeout-Anforderung. Verwalten des Parkens von Anrufen Einstellungen müssen Sie mithilfe der Skype für Business Server-Verwaltungsshell das Cmdlet **Set-CsCpsConfiguration** ausführen. Sie können nicht zum Parken von Anrufen der Einstellungen für die Verwendung der Skype für Business Server-Systemsteuerung verwalten. 

## <a name="reconfigure-the-call-park-service-settings"></a>Konfigurieren von Einstellungen für das Parken von Anrufen

1. Öffnen Sie in der Skype für Business Server 2019 Front-End-Server der Skype für Business Server-Verwaltungsshell.

2. Geben Sie an der Befehlszeile Folgendes ein:

    > [!NOTE]
    > Wenn Ihre Skype für Business Server 2019 Call Park-Anwendungseinstellungen an den Einstellungen der Vorversionen identisch sind, können Sie diesen Schritt überspringen. Wenn Parken-Anwendungseinstellungen für die Skype für Business Server 2019 und legacy-Umgebungen unterschiedlich sind, verwenden Sie das Cmdlet unterhalb als Vorlage, um die Änderungen zu aktualisieren. 

   ```
   Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"
   ```

Um alle Anruf Bereiche für den anrufparkorbit aus dem vorversionspool, der Skype für Business Server 2019 Pool neu zuzuweisen, können Sie die Skype Business Server-Systemsteuerung oder die Skype für Business Server-Verwaltungsshell verwenden. 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-control-panel"></a>Neuzuordnen Sie aller Anruf Parken Orbit Bereiche mit Skype Business Server-Systemsteuerung

1. Öffnen von Skype Business Server-Systemsteuerung.

2. Wählen Sie im linken Bereich **VoIP-Funktionen**.

3. Wählen Sie die Registerkarte **Parken** . 

4. Bearbeiten Sie für jede Parken orbitbereichs ein, die einem legacypool zugewiesen sind die Einstellung **FQDN des Zielservers** , und wählen Sie die Skype für Business Server 2019-Pool, die die Anforderungen zum Parken von Anrufen verarbeitet. 

5. Wählen Sie auf **Commit** , um die Änderungen zu speichern. 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-management-shell"></a>Neuzuordnen Sie aller Anruf Parken Orbit Bereiche mit Skype für Business Server-Verwaltungsshell

1. Öffnen Sie Skype für Business Server-Verwaltungsshell.

2. Geben Sie an der Befehlszeile Folgendes ein:

   ```
   Get-CsCallParkOrbit
   ```

    Mit diesem Cmdlet werden alle orbitbereiche zum Parken von Anrufen in der Bereitstellung aufgelistet. Alle Orbits für das Parken von Anrufen, die die Parameter **CallParkServiceId** und **CallParkServerFqdn** als Pool der Vorgängerversion festgelegt haben, müssen neu zugewiesen werden. 

    Um die Vorversion anrufparkorbits geben Bereiche an der Skype für Business Server 2019 Pool, an der Befehlszeile Folgendes ein:

   ```
   Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Skype for Business Server 2019 Pool FQDN>"
   ```

Nach Neuzuweisen alle Anruf Bereiche für den anrufparkorbit, der Skype für Business Server 2019 Pool, der Migrationsprozess für die Anwendung zum Parken wird abgeschlossen, und die Skype für Business Server 2019 Pool alle zukünftige Parken-Anforderungen behandelt.


