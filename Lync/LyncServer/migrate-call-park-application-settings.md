---
title: Migrieren von Einstellungen für die Anwendung zum Parken von Anrufen
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Call Park application settings
ms:assetid: 23b192d2-93ec-42a8-b175-b6ed502a2c35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687993(v=OCS.15)
ms:contentKeyID: 49733583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2789a8a83c8f3ee831fb91c85999d936ea54dd8b
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757006"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-call-park-application-settings"></a>Migrieren von Einstellungen für die Anwendung zum Parken von Anrufen

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-19_

Die Migration der Anwendung zum Parken von Anrufen von lync Server 2010 zu lync Server 2013 umfasst die Bereitstellung des lync Server 2013 Pools mit beliebigen benutzerdefinierten Musikdateien, die in lync Server 2010 hochgeladen wurden, wobei die Einstellungen für den Service Level wiederhergestellt und alle Orbits für das Parken von Anrufen an den lync Server 2013 Pool umgeplant werden. Wenn benutzerdefinierte Musikdateien im lync Server 2010 Pool konfiguriert wurden, müssen diese Dateien in den neuen lync Server 2013-Pool kopiert werden. Darüber hinaus wird empfohlen, dass Sie alle benutzerdefinierten Music-on-Hold-Dateien vom lync Server 2010 auf ein anderes Ziel sichern, um eine separate Sicherungskopie aller benutzerdefinierten Musikarchiv Dateien zu behalten, die für das Parken von Anrufen hochgeladen wurden. Die angepassten Music-on-Hold-Dateien für die Anwendung zum Parken von Anrufen werden im Dateispeicher des Pools gespeichert. Wenn Sie die Audiodateien aus einem lync Server 2010 Pool-Dateispeicher in einen lync Server 2013 Dateispeicher kopieren möchten, verwenden Sie den Befehl **xcopy** mit den folgenden Parametern:

   ```console
    Xcopy <Source: Lync Server 2010 Pool CPS File Store Path> <Destination: Lync Server 2013 Pool CPS File Store Path>
   ```

   ```console
    Example usage:  Xcopy "<Lync Server 2010 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Lync Server 2013 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
   ```

Wenn alle angepassten Audiodateien in den lync Server 2013 Dateispeicher kopiert wurden, müssen die Anwendung zum Parken von Anrufen Einstellungen des lync Server 2013 Pools konfiguriert werden, und die dem lync Server 2010 Pool zugeordneten orbitbereiche zum Parken von anrufen müssen dem lync Server 2013 Pool neu zugewiesen werden.

Zu den Einstellungen der Anwendung zum Parken von Anrufen gehören die Auswahl des Timeoutschwellenwerts für die Anrufannahme, das Aktivieren oder Deaktivieren der Wartemusik, die maximale Anzahl von Versuchen der Anrufannahme und die Timeoutanforderung. Sie müssen Anwendung zum Parken von Anrufen Einstellungen verwalten, indem Sie das Cmdlet " **CsCpsConfiguration** " mithilfe der lync Server-Verwaltungsshell ausführen. Die Anwendung zum Parken von Anrufen Einstellungen können nicht mithilfe der lync Server-Systemsteuerung verwaltet werden.

**Erneutes Konfigurieren der Einstellungen für den Dienst zum Parken von Anrufen**

1.  Öffnen Sie im lync Server 2013 Front-End-Server die lync Server-Verwaltungsshell.

2.  Geben Sie an der Befehlszeile Folgendes ein:
    
    <div>
    

    > [!NOTE]  
    > Wenn Ihre lync Server 2013 Anwendung zum Parken von Anrufen Einstellungen mit den lync Server 2010 Einstellungen für Legacy identisch sind, können Sie diesen Schritt überspringen. Wenn Anwendung zum Parken von Anrufen Einstellungen für die lync Server 2013-und lync Server 2010-Umgebungen unterschiedlich sind, verwenden Sie das unten aufgeführte Cmdlet als Vorlage, um diese Änderungen zu aktualisieren.

    
    </div>
    ```powershell
        Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>"-CallPickupTimeoutThreshold" <LS2010 CPS TimeSpan> "-" enablemusiconhold "" <LS2010 CPS value> "-" maxcallpickupattempts "" <LS2010 CPS pickup attempts> "-OnTimeoutURI" <LS2010 CPS timeout URI> "```

Um alle orbitbereiche für das Parken von Anrufen von lync Server 2010 Pool zum lync Server 2013-Pool neu zuzuweisen, können Sie entweder den lync Server-Systemsteuerung oder den lync Server-Verwaltungsshell verwenden.

**Neuzuordnen aller Bereiche für den Anrufparkorbit mit der Lync Server-Systemsteuerung**

1.  Öffnen Sie die Lync Server-Systemsteuerung.

2.  Wählen Sie im linken Bereich **VoIP-Funktionen** aus.

3.  Wählen Sie die Registerkarte **Parken von Anrufen** aus.

4.  Bearbeiten Sie für jeden orbitbereich für das Parken von anrufen, der einem lync Server 2010 Pool zugewiesen ist, die Einstellung **FQDN des Zielservers** , und wählen Sie den lync Server 2013 Pool aus, in dem die Anforderungen für das Parken von Anrufen verarbeitet werden.

5.  Klicken Sie auf **Commit ausführen**, um Ihre Änderungen zu speichern.

**Neuzuordnen aller Bereiche für den Anrufparkorbit mit der Lync Server-Verwaltungsshell**

1.  Öffnen Sie lync Server-Verwaltungsshell.

2.  Geben Sie an der Befehlszeile Folgendes ein:
    ```powershell
    Get-CsCallParkOrbit
    ```
    
    Dieses Cmdlet listet alle Bereiche für den Anrufparkorbit in der Bereitstellung auf. Alle Orbits für das Parken von anrufen, bei denen die Parameter **CallParkServiceId** und **CallParkServerFqdn** als lync Server 2010 Pool festgelegt sind, müssen neu zugewiesen werden.
    
    Geben Sie an der Befehlszeile Folgendes ein, um die lync Server 2010 orbitbereiche für das Parken von Anrufen dem lync Server 2013-Pool zuzuweisen:
    
    ```powershell
    Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Lync Server 2013 Pool FQDN>"
    ```

Nachdem Sie alle orbitbereiche für das Parken von Anrufen an den lync Server 2013 Pool neu zugewiesen haben, wird der Migrationsprozess für die Anwendung zum Parken von Anrufen abgeschlossen, und der lync Server 2013 Pool verarbeitet alle zukünftigen Anforderungen für das Parken von anrufen.

</div>

<span> </span>

</div>

</div>

</div>

