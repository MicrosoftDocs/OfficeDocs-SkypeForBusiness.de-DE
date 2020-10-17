---
title: Wiederherstellen eines gespiegelten Enterprise Edition-Back-End-Servers-Primary
description: Wiederherstellen eines gespiegelten Enterprise Edition-Back-End-Servers-Primary.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a mirrored Enterprise Edition Back End Server - primary
ms:assetid: bc555b46-70c5-4eee-ae91-e195df238293
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945648(v=OCS.15)
ms:contentKeyID: 51541512
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f186bc304dccc363e5a7e0bf89a2276043e361e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542411"
---
# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---primary"></a>Wiederherstellen eines gespiegelten Enterprise Edition-Back-End-Servers in lync Server 2013-Primary

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-17_

Wenn Sie einen Enterprise Edition-Back-End-Server in einer gespiegelten Konfiguration haben und nur die primäre Datenbank ausfällt, befolgen Sie die Verfahren in diesem Abschnitt. Wenn sowohl die primäre Datenbank als auch die Spiegelung fehlerhaft sind, finden Sie unter [Wiederherstellen eines Enterprise Edition-Back-End-Servers in lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md). Wenn nur die Spiegelung fehlschlägt, lesen Sie [Wiederherstellen eines gespiegelten Enterprise Edition-Back-End-Servers in lync Server 2013-Mirror](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md). Wenn die Datenbank, die den zentralen Verwaltungsspeicher hostet, fehlschlägt, lesen Sie [Wiederherstellen des Servers, der den zentralen Verwaltungsspeicher in lync Server 2013 hostet](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md). Wenn ein Enterprise Edition-Mitgliedsserver, lync Server 2013 bei dem es sich nicht um den Back-End-Server handelt, fehlerhaft ist, finden Sie unter [Wiederherstellen eines Enterprise Edition](lync-server-2013-restoring-an-enterprise-edition-member-server.md)

Es wird empfohlen, eine Abbild Kopie des Systems zu erstellen, bevor Sie mit der Wiederherstellung beginnen. Sie können dieses Bild als Rollback-Argument verwenden, falls während der Wiederherstellung etwas schief geht. Möglicherweise möchten Sie das Abbild kopieren, nachdem Sie das Betriebssystem installiert und SQL Server und die Zertifikate wiederhergestellt oder erneut registriert haben.

In diesem Thema weist die Beispieldatenbank einen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) von BE1.contoso.com auf, und die Spiegeldatenbank verfügt über einen FQDN von BE2.contoso.com.

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-primary-database"></a>So stellen Sie eine primäre Datenbank einer Enterprise Edition-Back-End-Server

1.  Melden Sie sich von einem Benutzerkonto, das Mitglied der Gruppe RTCUniversalServerAdmins ist, bei einem Front-End-Server an.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Erzwingen Sie, dass für alle konfigurierten Datenbanken ein Failover auf die Spiegelung ausgeführt wird. Geben Sie für jeden der Datenbanktypen, die Sie auf diesem Server konfiguriert haben, das folgende Cmdlet ein:
    
        Invoke-CsDataBaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <Configured Database Type> -NewPrincipal Mirror -Force -Verbose
    
    Zum Beispiel:
    
        Invoke-CsDataBaseFailover -PoolFqdn pool0.vdomain.com -DatabaseType User -NewPrincipal Mirror -Force -Verbose
    
    <div>
    

    > [!WARNING]
    > Wenn Sie die Back-End-Datenbank so konfiguriert haben, dass die synchronisierte Spiegelung mit einem Zeugen verwendet wird, erfolgt das Failover automatisch.

    
    </div>

4.  Führen Sie nach Abschluss des Failovers die folgenden Schritte aus:
    
      - Starten Sie den Topologie-Generator: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topologie-Generator**.
    
      - Deaktivieren der Spiegelung auf dem Back-End-Server: Klicken Sie mit der rechten Maustaste auf den Pool unter **Enterprise Edition-Front-End-Pools** , und wählen Sie **Eigenschaften bearbeiten**aus. Deaktivieren Sie auf der Registerkarte **Allgemein** unter **Zuordnungen**das Kontrollkästchen **SQL Server Speicherspiegelung aktivieren** . Tun Sie dies für die Archivierung und Überwachung bei Bedarf. Klicken Sie anschließend auf **OK**.
    
      - Klicken Sie mit der rechten Maustaste auf den Knoten lync Server 2013, klicken Sie auf **Topologie**, und klicken Sie dann auf **veröffentlichen**.
    
      - Wählen Sie das noch funktionsfähige Back-End (BE2.contoso.com) als neuen SQL-Speicher aus. Klicken Sie dazu mit der rechten Maustaste auf den Pool unter **Enterprise Edition-Front-End-Pools** , und wählen Sie **Eigenschaften bearbeiten**aus. Geben Sie auf der Registerkarte **Allgemein** unter **Zuordnungen**den FQDN des funktionsfähigen Back-Ends in das Feld **SQL Server Speicher** ein (in unserem Beispiel BE2.contoso.com).
    
      - Klicken Sie mit der rechten Maustaste auf den Knoten lync Server 2013, klicken Sie auf **Topologie**, und klicken Sie dann auf **veröffentlichen**.
    
      - Starten Sie die Dienste neu, damit jeder Server die neue Topologie lesen kann. Führen Sie in einem lync Server-Verwaltungsshell die folgenden Cmdlets für jeden Front-End-Server aus, der zu diesem Pool gehört:
        
            Stop-CsWindowsService
            Start-CsWindowsService

5.  Deinstallieren Sie die Spiegelung. Führen Sie in einem lync Server-Verwaltungsshell das folgende Cmdlet aus:
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn <MirrorServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    Zum Beispiel:
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn DB2.contoso.com -SqlInstanceName rtc -verbose
    
    Tun Sie dies für alle Datenbanktypen auf diesem Server.

6.  Erstellen Sie einen sauberen oder neuen Server mit demselben FQDN (in diesem Beispiel db1.contoso.com) als ausgefallenen Computer, installieren Sie das Betriebssystem, und stellen Sie die Zertifikate dann wieder her oder registrieren Sie Sie erneut. Dieser Server wird als neue Spiegelungsfunktion fungieren.

7.  Melden Sie sich bei einem Benutzerkonto, das Mitglied der Gruppe RTCUniversalServerAdmins ist, am neuen Server an.

8.  Installieren Sie SQL Server 2012 oder SQL Server 2008 R2, und halten Sie die Namen der Instanz so wie vor dem Fehler.

9.  Melden Sie sich von einem Benutzerkonto, das Mitglied der Gruppe RTCUniversalServerAdmins ist, bei einem Front-End-Server an.

10. Verwenden Sie den Topologie-Generator zum Installieren der Spiegeldatenbank. Führen Sie die folgenden Schritte durch:
    
      - Starten Sie den Topologie-Generator: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topologie-Generator**.
    
      - Aktivieren Sie die Spiegelung auf dem Back-End-Server. Klicken Sie dazu mit der rechten Maustaste auf den Pool unter **Enterprise Edition-Front-End-Pools** , und wählen Sie **Eigenschaften bearbeiten**aus. Aktivieren Sie auf der Registerkarte **Allgemein** unter **Zuordnungen**das Kontrollkästchen **SQL Server Speicherspiegelung aktivieren** . Tun Sie dies auch für die Archivierung und Überwachung, falls erforderlich.
        
        Geben Sie dann im Feld **Spiegelungs SQL Server Speicher** den FQDN des neuen Servers ein (n in diesem Beispiel BE1.contoso.com). Klicken Sie anschließend auf **OK**.
    
      - Klicken Sie mit der rechten Maustaste auf den Knoten lync Server 2013, klicken Sie auf **Topologie**, und klicken Sie dann auf **Datenbank installieren**.
    
      - Führen Sie den Assistenten zum **Installieren einer Datenbank** aus. Wählen Sie auf der Seite **Datenbankenerstellen** die Datenbanken aus, die Sie neu erstellen möchten.
    
      - Folgen Sie dem Assistenten, bis Sie zur Eingabeaufforderung kommen, **Spiegeldatenbank erstellen**. Wählen Sie die Datenbank aus, die Sie installieren möchten, und führen Sie diesen Vorgang aus.

</div>

</div>

<span> </span>

</div>

</div>

</div>

