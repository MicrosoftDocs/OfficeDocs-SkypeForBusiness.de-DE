---
title: Legen Sie den lync Server 2010 zentralen Verwaltungs Server auf lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move the Lync Server 2010 Central Management Server to Lync Server 2013
ms:assetid: 30cc98f2-1916-4dbe-99d0-8df5368ed3ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688013(v=OCS.15)
ms:contentKeyID: 49733602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90af32fce28d87b211a0829c5c863c9277129c86
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209731"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-the-lync-server-2010-central-management-server-to-lync-server-2013"></a>Legen Sie den lync Server 2010 zentralen Verwaltungs Server auf lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-11-25_

Nachdem Sie von lync Server 2010 zu lync Server 2013 migriert haben, müssen Sie den lync Server 2010 zentralen Verwaltungsserver in den lync Server 2013 Front-End-Server oder-Pool verschieben, bevor Sie den Legacy lync Server 2010 Server entfernen können.

Bei dem zentralen Verwaltungsserver handelt es sich um ein einzelnes Master/Multiple-Replikat System, bei dem die Lese-/Schreibzugriff-Kopie der Datenbank von der Front-End-Server gespeichert wird, die den zentralen Verwaltungsserver enthält. Jeder Computer in der Topologie, einschließlich der Front-End-Server, die den zentralen Verwaltungs Server enthält, verfügt über eine schreibgeschützte Kopie der Daten des zentralen Verwaltungsspeichers in der SQL Server-Datenbank (standardmäßig auf dem Computer RTCLOCAL), die während des Setups auf dem Computer installiert ist, und Bereitstellung. Die lokale Datenbank erhält Replikat Aktualisierungen über den lync Server Replikat Replikationsdienst-Agent, der auf allen Computern als Dienst ausgeführt wird. Der Name der tatsächlichen Datenbank auf dem zentralen Verwaltungs Server und das lokale Replikat ist XDS, das aus den Dateien XDS. mdf und XDS. ldf besteht. Auf den Speicherort der Master Datenbank wird in Active Directory-Domänendienste von einem Dienststeuerungspunkt (Service Control Points, SCP) verwiesen. Alle Tools, die den zentralen Verwaltungs Server zum Verwalten und konfigurieren lync Server verwenden den SCP zum Auffinden des zentralen Verwaltungsspeichers.

Nachdem Sie den zentralen Verwaltungsserver erfolgreich verschoben haben, sollten Sie die Datenbanken des zentralen Verwaltungsservers aus dem ursprünglichen Front-End-Server entfernen. Informationen zum Entfernen der Datenbanken des zentralen Verwaltungsservers finden Sie unter [Entfernen der SQL Server Datenbank für ein Front-End-Pool](remove-the-sql-server-database-for-a-front-end-pool.md).

Verwenden Sie das Windows PowerShell-Cmdlet " **CsManagementServer** " im lync Server-Verwaltungsshell, um die Datenbank aus der lync Server 2010 SQL Server-Datenbank in die lync Server 2013 SQL Server-Datenbank zu versetzen, und aktualisieren Sie dann den SCP so, dass er auf den Standort des lync Server 2013 zentralen Verwaltungsservers verweist.

<div>

## <a name="preparing-lync-server-2013front-end-servers-before-moving-the-central-management-server"></a>Vorbereiten lync Server 2013 Front-End-Server vor dem Verschieben des zentralen Verwaltungsservers

Verwenden Sie die Verfahren in diesem Abschnitt, um die lync Server 2013-Front-End-Server vorzubereiten, bevor Sie den lync Server 2010 zentralen Verwaltungs Server migrieren.

<div>

## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a>So bereiten Sie eine Enterprise Edition-Front-End-Pool vor

1.  Klicken Sie auf der lync Server 2013 Enterprise Edition-Front-End-Pool, an der Sie den zentralen Verwaltungs Server verschieben möchten: Melden Sie sich bei dem Computer an, auf dem der lync Server-Verwaltungsshell als Mitglied der **RTCUniversalServerAdmins** -Gruppe installiert ist. Sie müssen auch SQL Server Datenbank-sysadmin-Benutzerrechte und-Berechtigungen für die Datenbank haben, in der Sie den zentralen Verwaltungsspeicher installieren möchten.

2.  Öffnen Sie die Lync Server-Verwaltungsshell.

3.  Geben Sie zum Erstellen des neuen zentralen Verwaltungsspeichers in der lync Server 2013 SQL Server Datenbank im lync Server-Verwaltungsshell Folgendes ein:
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>

4.  Bestätigen Sie, dass der Dienst **Lync Server-Front-End** den Status **Gestartet** aufweist.

</div>

<div>

## <a name="to-prepare-a-standard-edition-front-end-server"></a>So bereiten Sie eine Standard Edition vor Front-End-Server

1.  Auf der lync Server 2013 Standard Edition-Front-End-Server, in der Sie den zentralen Verwaltungs Server verschieben möchten: Melden Sie sich bei dem Computer an, auf dem die lync Server-Verwaltungsshell installiert ist, als Mitglied der **RTCUniversalServerAdmins** -Gruppe.

2.  Öffnen Sie denLync Server-Bereitstellungs-Assistenten.

3.  Klicken Sie im lync Server-Bereitstellungs-Assistenten auf **erste Standard Edition-Server vorbereiten**.

4.  Auf der Seite **Befehle werden ausgeführt** wird SQL Server Express als zentraler Verwaltungs Server installiert. Die erforderlichen Firewallregeln werden erstellt. Klicken Sie auf **Fertig stellen**, wenn die Installation der Datenbank und der erforderlichen Software abgeschlossen ist.
    
    <div>
    

    > [!NOTE]  
    > Die Erstinstallation kann einige Zeit in Anspruch nehmen, und auf dem Zusammenfassungsbildschirm zur Befehlsausgabe werden keine Aktualisierungen angezeigt. Dies ist auf die Installation des SQL Server Express zurückzuführen. Sie können den Fortschritt der Datenbankinstallation im Task-Manager überwachen.

    
    </div>

5.  Geben Sie zum Erstellen des neuen zentralen Verwaltungsspeichers auf dem lync Server 2013 Standard Edition-Front-End-Server im lync Server-Verwaltungsshell Folgendes ein:
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>

6.  Bestätigen Sie, dass der Dienst **Lync Server-Front-End** den Status **Gestartet** aufweist.

</div>

</div>

<div>

## <a name="to-move-the-lync-server-2010central-management-server-to-lync-server-2013"></a>So legen Sie den lync Server 2010 zentralen Verwaltungs Server in lync Server 2013

1.  Auf dem lync Server 2013 Server, der als zentraler Verwaltungsserver verwendet wird: Melden Sie sich bei dem Computer an, auf dem der lync Server-Verwaltungsshell als Mitglied der **RTCUniversalServerAdmins** -Gruppe installiert ist. Darüber hinaus benötigen Sie Administratorrechte und -berechtigungen für die SQL Server-Datenbank.

2.  Öffnen Sie lync Server-Verwaltungsshell.

3.  Geben Sie im lync Server-Verwaltungsshell Folgendes ein:
    
        Enable-CsTopology
    
    <div>
    

    > [!WARNING]  
    > Wenn <CODE>Enable-CsTopology</CODE> nicht erfolgreich ist, lösen Sie das Problem, dass der Befehl nicht abgeschlossen ist, bevor Sie fortfahren. Wenn <STRONG>enable-CsTopology</STRONG> nicht erfolgreich ist, tritt bei der Migration ein Fehler auf, und Ihre Topologie kann in einem Zustand bleiben, in dem kein zentraler Verwaltungsspeicher vorhanden ist.

    
    </div>

4.  Geben Sie im lync Server 2013 Front-End-Server oder Front-End-Pool im lync Server-Verwaltungsshell Folgendes ein:
    
        Move-CsManagementServer

5.  Lync Server-Verwaltungsshell zeigt die Server, Dateispeicher, Datenbankspeicher und Dienstverbindungspunkte des aktuellen Status und des Status vorgeschlagen an. Lesen Sie die Informationen sorgfältig, und bestätigen Sie, dass dies die vorgesehene Quelle und das Ziel ist. Geben Sie **Y** ein, um fortzufahren, oder **N** , um die Bewegung zu beenden.

6.  Überprüfen Sie etwaige Warnungen oder Fehler, die durch den Befehl **Move-CsManagementServer** generiert wurden, und beheben Sie diese.

7.  Öffnen Sie auf dem lync Server 2013 Server den Assistenten für die lync Server-Bereitstellung.

8.  Klicken Sie im lync Server-Bereitstellungs-Assistenten auf **lync Server System installieren oder aktualisieren**, klicken Sie auf **Schritt 2: lync Server Komponenten einrichten oder entfernen**, klicken Sie auf **weiter**, überprüfen Sie die Zusammenfassung, und klicken Sie dann auf **Fertig stellen**.

9.  Öffnen Sie auf dem lync Server 2010 Server den Assistenten für die lync Server-Bereitstellung.

10. Klicken Sie im lync Server-Bereitstellungs-Assistenten auf **lync Server System installieren oder aktualisieren**, klicken Sie auf **Schritt 2: lync Server Komponenten einrichten oder entfernen**, klicken Sie auf **weiter**, überprüfen Sie die Zusammenfassung, und klicken Sie dann auf **Fertig stellen**.

11. Starten Sie den lync Server 2013 Server neu. Dies ist aufgrund einer Gruppen Mitgliedschaftsänderung für den Zugriff auf die Datenbank des zentralen Verwaltungsservers erforderlich.

12. Um zu bestätigen, dass die Replikation mit dem neuen zentralen Verwaltungsspeicher ausgeführt wird, geben Sie im lync Server-Verwaltungsshell Folgendes ein:
    
        Get-CsManagementStoreReplicationStatus
    
    <div>
    

    > [!NOTE]  
    > Bei der Replikation kann es eine Weile dauern, bis alle aktuellen Replikate aktualisiert wurden.

    
    </div>

</div>

<div>

## <a name="to-remove-lync-server-2010central-management-store-files-after-a-move"></a>So entfernen Sie nach einer Migration lync Server 2010 zentralen Verwaltungsspeicher Dateien

1.  Auf dem lync Server 2010 Server: Melden Sie sich bei dem Computer an, auf dem der lync Server-Verwaltungsshell als Mitglied der **RTCUniversalServerAdmins** -Gruppe installiert ist. Darüber hinaus benötigen Sie Administratorrechte und -berechtigungen für die SQL Server-Datenbank.

2.  Lync Server-Verwaltungsshell öffnen
    
    <div>
    

    > [!WARNING]  
    > Fahren Sie nicht mit dem Entfernen der vorherigen Datenbankdateien fort, bis die Replikation abgeschlossen und stabil ist. Wenn Sie die Dateien vor der Fertigstellung der Replikation entfernen, unterbrechen Sie den Replikationsprozess und lassen den neu verschobenen zentralen Verwaltungs Server in einem unbekannten Zustand wieder. Verwenden Sie das Cmdlet <STRONG>Get-CsManagementStoreReplicationStatus</STRONG> , um den Replikationsstatus zu bestätigen.

    
    </div>

3.  Geben Sie Folgendes ein, um die Datenbankdateien des zentralen Verwaltungsspeichers vom lync Server 2010 zentralen Verwaltungs Server zu entfernen:
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
    
    Zum Beispiel:
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
    
    Dabei ist \<der FQDN von\> SQL Server entweder der lync Server 2010-Back-End-Server in einer Enterprise Edition-Bereitstellung oder der FQDN des Standard Edition-Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

