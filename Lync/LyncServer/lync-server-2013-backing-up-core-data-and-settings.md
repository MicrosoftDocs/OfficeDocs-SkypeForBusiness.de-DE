---
title: 'Lync Server 2013: Sichern von Hauptdaten und-Einstellungen'
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
ms.openlocfilehash: 403a32798f84d2be6d045564e3a3e3803240f4a3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205861"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backing-up-core-data-and-settings-in-lync-server-2013"></a>Sichern von Hauptdaten und-Einstellungen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-04-23_

In den folgenden Verfahren werden lync Server-Verwaltungsshell-Cmdlets zum Erstellen von Sicherungsdateien für Einstellungen und Daten für Hauptdienste verwendet. Ausführliche Informationen zu den in diesem Abschnitt verwendeten Tools, einschließlich der Stelle, an der Sie sich befinden, finden Sie unter [Sicherungs-und Wiederherstellungsanforderungen in lync Server 2013: Tools and Permissions](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md). Ausführliche Informationen zum Sichern von Archivierungs-und Überwachungsdaten finden Sie unter [Sichern von Archivierungs-und Überwachungsdatenbanken in lync Server 2013](lync-server-2013-backing-up-archiving-and-monitoring-databases.md).

<div>


> [!NOTE]  
> Der Schritt in diesem Abschnitt zum Sichern des zentralen Verwaltungsspeichers umfasst die Einstellungen und die Konfiguration für die Archivierung und Überwachung.



</div>

Sie können die in diesem Abschnitt beschriebenen Cmdlets lokale oder remote ausführen.

<div>

## <a name="to-back-up-core-data-and-settings"></a>So sichern Sie wichtige Daten und Einstellungen

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe RTCUniversalServerAdmins ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Zum Speichern der Sicherungen, die Sie in den folgenden Schritten erstellen, legen Sie einen neuen freigegebenen Ordner an und aktualisieren Sie den Pfad, der von **$Backup** referenziert wid, auf den neuen freigegebenen Ordner.

3.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

4.  Sichern Sie die Konfigurationsdatei des zentralen Verwaltungsspeichers. Geben Sie an der Befehlszeile Folgendes ein:
    
        Export-CsConfiguration -FileName <path and file name for backup>
    
    Zum Beispiel:
    
        Export-CsConfiguration -FileName "C:\Config.zip"
    
    <div>
    

    > [!NOTE]  
    > In diesem Schritt werden die lync Server Topologie, die Richtlinien und Konfigurationseinstellungen in eine Datei exportiert. Weitere Schritte sind zum Sichern der Topologiedaten nicht erforderlich.

    
    </div>

5.  Kopieren Sie die gesicherte Konfigurationsdatei des zentralen Verwaltungsspeichers in $Backup\\.

6.  Sichern Sie die Standortinformationsdienst-Daten. Geben Sie an der Befehlszeile Folgendes ein:
    
        Export-CsLisConfiguration -FileName <path and file name for backup>
    
    Beispiel:
    
        Export-CsLisConfiguration -FileName "C:\E911Config.zip"

7.  Kopieren Sie die gesicherte Standortinformationsdienst Konfigurationsdatei in $Backup\\.

8.  Sichern von Benutzerdaten in jeder Back-End-Datenbank eines Front-End-Pool und jeder Standard Edition-Server. Geben Sie an der Befehlszeile Folgendes ein:
    
        Export-CsUserData -PoolFQDN <Fqdn> -FileName <String>
    
    Zum Beispiel:
    
        Export-CsUserData -PoolFQDN "atl-cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserData.zip"

9.  Kopieren Sie die gesicherte Benutzerdatei in $Backup\\.

10. Sichern Sie in jedem Pool, der das Reaktionsgruppenanwendung ausführt, die Konfiguration der Reaktionsgruppe. Gehen Sie wie folgt vor:
    
    1.  Geben Sie in die Befehlszeile Folgendes ein:
        
            Export-CsRgsConfiguration -Source "service:ApplicationServer:<pool FQDN>" -FileName <path and file name for backup>
        
        Zum Beispiel:
        
            Export-CsRgsConfiguration -Source ApplicationServer:pool01.contoso.com -FileName C:\RgsConfiguration.zip

11. Kopieren Sie die gesicherte Antwortgruppen-Konfigurationsdatei in $Backup\\.

</div>

</div>

<span> </span>

</div>

</div>

</div>

