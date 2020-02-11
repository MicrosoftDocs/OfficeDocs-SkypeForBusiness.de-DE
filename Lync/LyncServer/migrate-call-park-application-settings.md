---
title: Migrieren von Einstellungen für die Anwendung zum Parken von Anrufen
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate Call Park application settings
ms:assetid: 23b192d2-93ec-42a8-b175-b6ed502a2c35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687993(v=OCS.15)
ms:contentKeyID: 49733583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee1afd2e53bd29571818b9194fe77d3d350386f1
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888764"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-call-park-application-settings"></a>Migrieren von Einstellungen für die Anwendung zum Parken von Anrufen

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-19_

Die Migration der Anruf Park Anwendung von lync Server 2010 zu lync Server 2013 umfasst die Bereitstellung des lync Server 2013-Pools mit beliebigen benutzerdefinierten Musikdateien, die in lync Server 2010 hochgeladen wurden, die Einstellungen für den Service Level wiederherstellen und eine erneute Zielausrichtung durchführen. alle Anruf parken umkreist den lync Server 2013-Pool. Wenn benutzerdefinierte Music-on-halten-Dateien im lync Server 2010-Pool konfiguriert wurden, müssen diese Dateien in den neuen lync Server 2013-Pool kopiert werden. Darüber hinaus empfiehlt es sich, dass Sie alle angefügten Music-on-Keep-Dateien von lync Server 2010 zu einem anderen Ziel sichern, um eine separate Sicherungskopie aller angepassten Music-on-halten-Dateien zu erhalten, die für den Anruf Park hochgeladen wurden. Die angepassten Music-on-halten-Dateien für die Anwendung "Parken" werden im Dateispeicher des Pools gespeichert. Wenn Sie die Audiodateien aus einem lync Server 2010-Pool Dateispeicher in einen lync Server 2013-Dateispeicher kopieren möchten, verwenden Sie den Befehl **xcopy** mit den folgenden Parametern:

   ```console
    Xcopy <Source: Lync Server 2010 Pool CPS File Store Path> <Destination: Lync Server 2013 Pool CPS File Store Path>
   ```

   ```console
    Example usage:  Xcopy "<Lync Server 2010 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Lync Server 2013 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
   ```

Wenn alle angepassten Audiodateien in den lync Server 2013-Dateispeicher kopiert wurden, müssen die Einstellungen für den Anruf Park des lync Server 2013-Pools konfiguriert sein, und die orbitbereiche für den Anruf Park, die dem lync Server 2010-Pool zugeordnet sind, müssen erneut zugewiesen werden. der lync Server 2013-Pool.

Die Anwendungseinstellungen des Anruf Parks beinhalten den Schwellenwert für das Pickup-Zeitlimit, das Aktivieren oder Deaktivieren von Musik in Wartestellung, die maximale Anzahl von Anruf Angriffen und die Timeout-Anforderung. Sie müssen die Einstellungen für die Anruf Park Anwendung verwalten, indem Sie die lync Server-Verwaltungsshell verwenden, um das Cmdlet " **Satz-CsCpsConfiguration** " auszuführen. Mit der lync Server-Systemsteuerung können Sie die Anwendungseinstellungen für den Anruf Park nicht verwalten.

**Neukonfigurieren der Einstellungen für den Anruf Park Dienst**

1.  Öffnen Sie auf dem lync Server 2013-Front-End-Server die lync Server-Verwaltungsshell.

2.  Geben Sie an der Befehlszeile Folgendes ein:
    
    <div>
    

    > [!NOTE]  
    > Wenn die Anwendungseinstellungen Ihres lync Server 2013-Anrufs mit den Legacy Einstellungen von lync Server 2010 identisch sind, können Sie diesen Schritt überspringen. Wenn sich die Einstellungen für den Anruf Park für die lync Server 2013-und lync Server 2010-Umgebungen unterscheiden, verwenden Sie das unten aufgeführte Cmdlet als Vorlage, um diese Änderungen zu aktualisieren.

    
    </div>
    ```powershell
        Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>"-CallPickupTimeoutThreshold"<LS2010 CPS TimeSpan>"-" enablemusiconhold ""<LS2010 CPS value>"-" maxcallpickupattempts ""<LS2010 CPS pickup attempts>"-OnTimeoutURI"<LS2010 CPS timeout URI>"```

Wenn Sie alle orbitbereiche des Anruf Parks vom lync Server 2010-Pool zum lync Server 2013-Pool neu zuweisen möchten, können Sie entweder die lync Server-Systemsteuerung oder die lync Server-Verwaltungsshell verwenden.

**Erneutes Zuweisen aller orbitbereiche für den Anruf Bereich mithilfe der lync Server-Systemsteuerung**

1.  Öffnen Sie die Lync Server-Systemsteuerung.

2.  Wählen Sie im linken Bereich **sprach Features**aus.

3.  Wählen Sie die Registerkarte **Anruf parken** aus.

4.  Bearbeiten Sie für jeden Anruf Park-orbitbereich, der einem lync Server 2010-Pool zugewiesen ist, den **FQDN der Ziel Server** Einstellung, und wählen Sie den lync Server 2013-Pool aus, der die Anforderungen des Anruf Parks verarbeitet.

5.  Wählen Sie **Commit** aus, um die Änderungen zu speichern.

**Erneutes Zuweisen aller orbitbereiche für den Anruf Bereich mithilfe der lync Server-Verwaltungsshell**

1.  Öffnen Sie die Lync Server-Verwaltungsshell.

2.  Geben Sie an der Befehlszeile Folgendes ein:
    ```powershell
    Get-CsCallParkOrbit
    ```
    
    Mit diesem Cmdlet werden alle orbitbereiche des Anruf Parks in der Bereitstellung aufgelistet. Alle Orbits des Anruf Parks, deren **CallParkServiceId** -und **CallParkServerFqdn** -Parameter als lync Server 2010-Pool festgelegt sind, müssen neu zugewiesen werden.
    
    Geben Sie in der Befehlszeile Folgendes ein, um den lync Server 2010-Orbit für den Anruf Bereich zum lync Server 2013-Pool erneut zuzuweisen:
    
    ```powershell
    Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Lync Server 2013 Pool FQDN>"
    ```

Nach dem erneuten Zuweisen aller orbitbereiche für den Anruf Bereich zum lync Server 2013-Pool wird der Migrationsprozess für die Anwendung "Parken" abgeschlossen, und der lync Server 2013-Pool verarbeitet alle zukünftigen Anruf Park Anfragen.

</div>

<span> </span>

</div>

</div>

</div>

