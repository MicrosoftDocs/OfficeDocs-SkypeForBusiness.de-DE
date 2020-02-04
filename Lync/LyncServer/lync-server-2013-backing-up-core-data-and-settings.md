---
title: 'Lync Server 2013: Sichern von Core-Daten und-Einstellungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up core data and settings
ms:assetid: 278bc95a-7b8d-4e01-a872-a844830459de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202170(v=OCS.15)
ms:contentKeyID: 51541452
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4185c02bc85077b0f68ca76d83fd48203e0e5fd9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727915"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-core-data-and-settings-in-lync-server-2013"></a>Sichern von Kern Daten und-Einstellungen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-04-23_

Die folgenden Verfahren verwenden Cmdlets der lync Server-Verwaltungsshell zum Erstellen von Sicherungsdateien für Einstellungen und Daten für Kerndienste. Details zu den in diesem Abschnitt verwendeten Tools, einschließlich ihrer Position, finden Sie unter [Sicherungs-und Wiederherstellungsanforderungen in lync Server 2013: Tools und Berechtigungen](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md). Details zum Sichern von Archivierungs-und Überwachungsdaten finden Sie unter [Sichern von Archivierungs-und Überwachungsdatenbanken in lync Server 2013](lync-server-2013-backing-up-archiving-and-monitoring-databases.md).

<div>


> [!NOTE]  
> Der Schritt in diesem Abschnitt zum Sichern des zentralen Verwaltungsspeichers umfasst die Einstellungen und die Konfiguration für die Archivierung und Überwachung.



</div>

Sie können die in diesem Abschnitt beschriebenen Cmdlets lokal oder Remote ausführen.

<div>

## <a name="to-back-up-core-data-and-settings"></a>So sichern Sie Core-Daten und-Einstellungen

1.  Melden Sie sich von einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist, bei einem beliebigen Computer in ihrer internen Bereitstellung an.

2.  Wenn Sie die in den folgenden Schritten erstellten Sicherungen speichern möchten, erstellen Sie einen neuen freigegebenen Ordner, und aktualisieren Sie den Pfad, auf den **$Backup** verweist, auf den neuen freigegebenen Ordner.

3.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

4.  Sichern Sie die Konfigurationsdatei des zentralen Verwaltungsspeichers. Geben Sie an der Befehlszeile Folgendes ein:
    
        Export-CsConfiguration -FileName <path and file name for backup>
    
    Beispiel:
    
        Export-CsConfiguration -FileName "C:\Config.zip"
    
    <div>
    

    > [!NOTE]  
    > Mit diesem Schritt werden Ihre lync Server-Topologie,-Richtlinien und-Konfigurationseinstellungen in eine Datei exportiert. Zum Sichern von Topologiedaten ist kein anderer Schritt erforderlich.

    
    </div>

5.  Kopieren Sie die gesicherte Konfigurationsdatei des zentralen Verwaltungsspeichers in $Backup\\.

6.  Sichern Sie die Daten des Standort Informationsdiensts. Geben Sie an der Befehlszeile Folgendes ein:
    
        Export-CsLisConfiguration -FileName <path and file name for backup>
    
    Beispiel:
    
        Export-CsLisConfiguration -FileName "C:\E911Config.zip"

7.  Kopieren Sie die Konfigurationsdatei des gesicherten Standort Informationsdiensts in\\$Backup.

8.  Sichern Sie die Benutzerdaten in jeder Back-End-Datenbank eines Front-End-Pools und jedes Standard Edition-Servers. Geben Sie an der Befehlszeile Folgendes ein:
    
        Export-CsUserData -PoolFQDN <Fqdn> -FileName <String>
    
    Beispiel:
    
        Export-CsUserData -PoolFQDN "atl-cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserData.zip"

9.  Kopieren Sie die gesicherte Benutzerdatei in $Backup\\.

10. Sichern Sie in jedem Pool, auf dem die reaktionsgruppenanwendung ausgeführt wird, die Konfiguration der Reaktionsgruppe. Gehen Sie wie folgt vor:
    
    1.  Geben Sie in der Befehlszeile Folgendes ein:
        
            Export-CsRgsConfiguration -Source "service:ApplicationServer:<pool FQDN>" -FileName <path and file name for backup>
        
        Beispiel:
        
            Export-CsRgsConfiguration -Source ApplicationServer:pool01.contoso.com -FileName C:\RgsConfiguration.zip

11. Kopieren Sie die gesicherte Antwortgruppen-Konfigurationsdatei in $Backup\\.

</div>

</div>

<span> </span>

</div>

</div>

</div>

