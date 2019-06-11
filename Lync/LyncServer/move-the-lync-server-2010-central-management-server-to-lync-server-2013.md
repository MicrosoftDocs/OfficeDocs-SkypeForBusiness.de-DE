---
title: Verschieben des zentralen Verwaltungsservers mit lync Server 2010 auf lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Move the Lync Server 2010 Central Management Server to Lync Server 2013
ms:assetid: 30cc98f2-1916-4dbe-99d0-8df5368ed3ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688013(v=OCS.15)
ms:contentKeyID: 49733602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: abcb361beb82b98cd765b3797b63b22c280fdf70
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847078"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-the-lync-server-2010-central-management-server-to-lync-server-2013"></a>Verschieben des zentralen Verwaltungsservers mit lync Server 2010 auf lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-11-25_

Nachdem Sie die Migration von lync Server 2010 zu lync Server 2013 durchlaufen haben, müssen Sie den zentralen Verwaltungsserver von lync Server 2010 auf den lync Server 2013-Front-End-Server oder-Pool verschieben, bevor Sie den Legacy-lync Server 2010-Server entfernen können.

Bei dem zentralen Verwaltungsserver handelt es sich um ein einzelnes Master/Multiple-Replikat System, bei dem die Kopie der Datenbank vom Front-End-Server, auf dem sich der zentrale Verwaltungsserver befindet, gelesen/geschrieben wird. Jeder Computer in der Topologie, einschließlich des Front-End-Servers, der den zentralen Verwaltungsserver enthält, verfügt über eine schreibgeschützte Kopie der zentralen Verwaltungsspeicher Daten in der SQL Server-Datenbank (standardmäßig mit dem Namen RTCLOCAL), die während des Setups auf dem Computer installiert sind, und Bereitstellungs. Die lokale Datenbank erhält Replikat Updates über den lync Server Replica Replicator-Agent, der auf allen Computern als Dienst ausgeführt wird. Der Name der tatsächlichen Datenbank auf dem zentralen Verwaltungs Server und das lokale Replikat ist XDS, das aus den Dateien XDS. mdf und XDS. ldf besteht. Auf den Speicherort der Master Datenbank wird in den Active Directory-Domänendiensten von einem Dienst Kontrollpunkt (Service Control Point, SCP) verwiesen. Alle Tools, die den zentralen Verwaltungs Server zum Verwalten und Konfigurieren von lync Server verwenden, verwenden den SCP, um den zentralen Verwaltungsspeicher zu finden.

Nachdem Sie den zentralen Verwaltungsserver erfolgreich verschoben haben, sollten Sie die zentralen Verwaltungsserver Datenbanken vom ursprünglichen Front-End-Server entfernen. Informationen zum Entfernen der zentralen Verwaltungs Server-Datenbanken finden Sie unter [Entfernen der SQL Server-Datenbank für einen Front-End-Pool](remove-the-sql-server-database-for-a-front-end-pool.md).

Sie verwenden das Windows PowerShell **-Cmdlet Move-CsManagementServer** in der lync Server-Verwaltungsshell, um die Datenbank aus der lync Server 2010 SQL Server-Datenbank in die lync Server 2013 SQL Server-Datenbank zu verschieben und dann den SCP so zu aktualisieren, dass er auf das lync verweist. Server 2013 Central Management Server-Standort.

<div>

## <a name="preparing-lync-server-2013front-end-servers-before-moving-the-central-management-server"></a>Vorbereiten der lync Server 2013-Front-End-Server vor dem Verschieben des zentralen Verwaltungsservers

Führen Sie die Verfahren in diesem Abschnitt aus, um die lync Server 2013-Front-End-Server vorzubereiten, bevor Sie den zentralen Verwaltungs Server für lync Server 2010 verschieben.

<div>

## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a>Vorbereiten eines Enterprise Edition-Front-End-Pools

1.  Klicken Sie im Front-End-Pool von lync Server 2013 Enterprise Edition, in dem Sie den zentralen Verwaltungs Server umsiedeln möchten: Melden Sie sich bei dem Computer an, auf dem die lync Server-Verwaltungsshell als Mitglied der **RTCUniversalServerAdmins** -Gruppe installiert ist. Sie müssen auch über die SQL Server-Datenbank sysadmin-Benutzerrechte und-Berechtigungen für die Datenbank verfügen, in der Sie den zentralen Verwaltungsspeicher installieren möchten.

2.  Öffnen Sie die lync Server-Verwaltungsshell.

3.  Zum Erstellen des neuen zentralen Verwaltungsspeichers in der lync Server 2013 SQL Server-Datenbank geben Sie in der lync Server-Verwaltungsshell Folgendes ein:
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>

4.  Vergewissern Sie sich, dass der Status des **lync Server-Front-End-** Diensts **gestartet**wurde.

</div>

<div>

## <a name="to-prepare-a-standard-edition-front-end-server"></a>Vorbereiten eines Standard Edition-Front-End-Servers

1.  Auf dem lync Server 2013 Standard Edition-Front-End-Server, auf dem Sie den zentralen Verwaltungsserver verschieben möchten: Melden Sie sich bei dem Computer an, auf dem die lync Server-Verwaltungsshell als Mitglied der **RTCUniversalServerAdmins** -Gruppe installiert ist.

2.  Öffnen Sie den lync Server-Bereitstellungs-Assistenten.

3.  Klicken Sie im lync Server-Bereitstellungs-Assistenten auf **First Standard Edition-Server vorbereiten**.

4.  Auf der Seite **Ausführungsbefehle** wird SQL Server Express als zentraler Verwaltungs Server installiert. Es werden erforderliche Firewallregeln erstellt. Wenn die Installation der Datenbank und der erforderlichen Software abgeschlossen ist, klicken Sie auf **Fertig stellen**.
    
    <div>
    

    > [!NOTE]  
    > Die anfängliche Installation kann einige Zeit in Anspruch nehmen, ohne dass die Anzeige des Befehlsausgabe Zusammenfassungsbildschirms sichtbar wird. Dies ist auf die Installation von SQL Server Express zurückzuführen. Wenn Sie die Installation der Datenbank überwachen müssen, verwenden Sie den Task-Manager, um das Setup zu überwachen.

    
    </div>

5.  Zum Erstellen des neuen zentralen Verwaltungsspeichers auf dem lync Server 2013 Standard Edition-Front-End-Server geben Sie in der lync Server-Verwaltungsshell Folgendes ein:
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>

6.  Vergewissern Sie sich, dass der Status des **lync Server-Front-End-** Diensts **gestartet**wurde.

</div>

</div>

<div>

## <a name="to-move-the-lync-server-2010central-management-server-to-lync-server-2013"></a>So verschieben Sie den lync Server 2010 Central-Verwaltungs Server nach lync Server 2013

1.  Auf dem lync Server 2013-Server, der der zentrale Verwaltungsserver sein soll: Melden Sie sich bei dem Computer an, auf dem die lync Server-Verwaltungsshell als Mitglied der **RTCUniversalServerAdmins** -Gruppe installiert ist. Sie müssen auch über die Benutzerrechte und-Berechtigungen des SQL Server-Datenbankadministrators verfügen.

2.  Öffnen Sie die Lync Server-Verwaltungsshell.

3.  Geben Sie in der lync Server-Verwaltungsshell Folgendes ein:
    
        Enable-CsTopology
    
    <div>
    

    > [!WARNING]  
    > Wenn <CODE>Enable-CsTopology</CODE> dies nicht der Fall ist, beheben Sie das Problem, das verhindert, dass der Befehl abgeschlossen wird, bevor Sie fortfahren. Wenn <STRONG>enable-CsTopology</STRONG> nicht erfolgreich ist, schlägt die Verschiebung fehl, und Sie verlässt Ihre Topologie möglicherweise in einem Zustand, in dem kein zentraler Verwaltungsspeicher vorhanden ist.

    
    </div>

4.  Geben Sie auf dem lync Server 2013-Front-End-Server oder-Front-End-Pool in der lync Server-Verwaltungsshell Folgendes ein:
    
        Move-CsManagementServer

5.  In der lync Server-Verwaltungsshell werden die Server, Dateispeicher, Datenbankspeicher und die Dienstverbindungspunkte des aktuellen Zustands und des vorgeschlagenen Zustands angezeigt. Lesen Sie die Informationen sorgfältig durch, und bestätigen Sie, dass dies die beabsichtigte Quelle und das Ziel ist. Geben Sie **Y** ein, um fortzufahren, oder **N** , um die Verschiebung zu beenden.

6.  Überprüfen Sie alle Warnungen oder Fehler, die durch den Befehl **Move-CsManagementServer** generiert wurden, und beheben Sie Sie.

7.  Öffnen Sie auf dem lync Server 2013-Server den lync Server-Bereitstellungs-Assistenten.

8.  Klicken Sie im lync Server-Bereitstellungs-Assistenten auf **lync Server System installieren oder aktualisieren**, klicken Sie auf **Schritt 2: Einrichten oder Entfernen von lync Server-Komponenten**, klicken Sie auf **weiter**, überprüfen Sie die Zusammenfassung, und klicken Sie dann auf **Fertig stellen**.

9.  Öffnen Sie auf dem lync Server 2010-Server den lync Server-Bereitstellungs-Assistenten.

10. Klicken Sie im lync Server-Bereitstellungs-Assistenten auf **lync Server System installieren oder aktualisieren**, klicken Sie auf **Schritt 2: Einrichten oder Entfernen von lync Server-Komponenten**, klicken Sie auf **weiter**, überprüfen Sie die Zusammenfassung, und klicken Sie dann auf **Fertig stellen**.

11. Starten Sie den lync Server 2013-Server neu. Dies ist aufgrund einer Änderung der Gruppenmitgliedschaft für den Zugriff auf die zentrale Verwaltungs Server-Datenbank erforderlich.

12. Um zu bestätigen, dass die Replikation mit dem neuen zentralen Verwaltungsspeicher erfolgt, geben Sie in der lync Server-Verwaltungsshell Folgendes ein:
    
        Get-CsManagementStoreReplicationStatus
    
    <div>
    

    > [!NOTE]  
    > Die Replikation kann einige Zeit dauern, bis alle aktuellen Replikate aktualisiert wurden.

    
    </div>

</div>

<div>

## <a name="to-remove-lync-server-2010central-management-store-files-after-a-move"></a>So entfernen Sie nach einem Umzug lync Server 2010 Central Management Store-Dateien

1.  Auf dem lync Server 2010-Server: Melden Sie sich bei dem Computer an, auf dem die lync Server-Verwaltungsshell als Mitglied der **RTCUniversalServerAdmins** -Gruppe installiert ist. Sie müssen auch über die Benutzerrechte und-Berechtigungen des SQL Server-Datenbankadministrators verfügen.

2.  Öffnen der lync Server-Verwaltungsshell
    
    <div>
    

    > [!WARNING]  
    > Gehen Sie nicht mit dem Entfernen der vorherigen Datenbankdateien fort, bis die Replikation abgeschlossen und stabil ist. Wenn Sie die Dateien vor dem Abschließen der Replikation entfernen, werden Sie den Replikationsprozess unterbrechen und den neu verschobenen zentralen Verwaltungs Server in einem unbekannten Zustand belässt. Verwenden Sie das Cmdlet <STRONG>Get-CsManagementStoreReplicationStatus</STRONG> , um den Replikationsstatus zu bestätigen.

    
    </div>

3.  Wenn Sie die zentralen Verwaltungsspeicher-Datenbankdateien vom lync Server 2010 Central-Verwaltungs Server entfernen möchten, geben Sie Folgendes ein:
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
    
    Beispiel:
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
    
    Hierbei handelt \<es sich bei dem\> FQDN von SQL Server entweder um den lync Server 2010-Back-End-Server in einer Enterprise Edition-Bereitstellung oder um den FQDN des Standard Edition-Servers.

</div>

</div>

<span> </span>

</div>

</div>

</div>

