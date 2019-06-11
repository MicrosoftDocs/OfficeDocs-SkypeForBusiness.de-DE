---
title: Wiederherstellen eines gespiegelten Enterprise Edition-Back-End-Servers – primär
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring a mirrored Enterprise Edition Back End Server - primary
ms:assetid: bc555b46-70c5-4eee-ae91-e195df238293
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945648(v=OCS.15)
ms:contentKeyID: 51541512
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbf0c8562ed4180fb14bf0bda74a03dd4ee8f746
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823063"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---primary"></a>Wiederherstellen eines gespiegelten Enterprise Edition-Back-End-Servers in lync Server 2013 – primär

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-17_

Wenn Sie über einen Enterprise Edition-Back-End-Server in einer gespiegelten Konfiguration verfügen und nur die primäre Datenbank fehlschlägt, führen Sie die Verfahren in diesem Abschnitt aus. Wenn sowohl die primäre Datenbank als auch die Spiegelung fehlerhaft sind, lesen Sie [Wiederherstellen eines Enterprise Edition-Back-End-Servers in lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md). Wenn nur die Spiegelung fehlschlägt, lesen Sie [Wiederherstellen eines gespiegelten Enterprise Edition-Back-End-Servers in lync Server 2013-Mirror](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md). Wenn die Datenbank, die den zentralen Verwaltungsspeicher hostet, fehlschlägt, lesen Sie [Wiederherstellen des Servers, auf dem der zentrale Verwaltungsspeicher in lync Server 2013 gehostet](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)wird. Wenn ein Enterprise Edition-Mitgliedsserver, der nicht der Back-End-Server ist, fehlschlägt, lesen Sie [Wiederherstellen eines Enterprise Edition-Mitgliedsservers in lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md)

Wir empfehlen, dass Sie eine Image-Kopie des Systems erstellen, bevor Sie mit der Wiederherstellung beginnen. Sie können dieses Bild als Rollback-Punkt verwenden, falls während der Wiederherstellung etwas schief geht. Möglicherweise möchten Sie das Abbild kopieren, nachdem Sie das Betriebssystem und SQL Server installiert haben, und die Zertifikate wiederherstellen oder erneut registrieren.

In diesem Thema verfügt die primäre Beispieldatenbank über einen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) von BE1.contoso.com, und die Spiegeldatenbank verfügt über einen FQDN von BE2.contoso.com.

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-primary-database"></a>So stellen Sie eine primäre Datenbank für den Back-End-Server eines Enterprise Edition

1.  Melden Sie sich bei einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist, bei einem Front-End-Server an.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Erzwingen Sie, dass alle konfigurierten Datenbanken ein Failover zur Spiegelung durchführen. Geben Sie für jeden der Datenbanktypen, die Sie auf diesem Server konfiguriert haben, das folgende Cmdlet ein:
    
        Invoke-CsDataBaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <Configured Database Type> -NewPrincipal Mirror -Force -Verbose
    
    Beispiel:
    
        Invoke-CsDataBaseFailover -PoolFqdn pool0.vdomain.com -DatabaseType User -NewPrincipal Mirror -Force -Verbose
    
    <div>
    

    > [!WARNING]
    > Wenn Sie Ihre Back-End-Datenbank so konfiguriert haben, dass die synchronisierte Spiegelung mit einem Zeugen verwendet wird, ist das Failover automatisch.

    
    </div>

4.  Führen Sie nach Abschluss des Failovers die folgenden Aktionen aus:
    
      - Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topology Builder**.
    
      - Deaktivieren der Spiegelung auf dem Back-End-Server: Klicken Sie mit der rechten Maustaste auf den Pool unter **Enterprise Edition-Front-End-Pools** , und wählen Sie **Eigenschaften bearbeiten**aus. Deaktivieren Sie auf der Registerkarte **Allgemein** unter **Zuordnungen**das Kontrollkästchen **Spiegelung des SQL Server-Speichers aktivieren** . Führen Sie diese Schritte für die Archivierung und Überwachung nach Bedarf aus. Klicken Sie dann auf **OK**.
    
      - Klicken Sie mit der rechten Maustaste auf den Knoten lync Server 2013, klicken Sie auf **Topologie**, und klicken Sie dann auf **veröffentlichen**.
    
      - Wählen Sie das noch funktionierende Back-End (BE2.contoso.com) als neuen SQL Store aus. Klicken Sie dazu mit der rechten Maustaste auf den Pool unter **Enterprise Edition-Front-End-Pools** , und wählen Sie **Eigenschaften bearbeiten**aus. Geben Sie auf der Registerkarte **Allgemein** unter **Zuordnungen**den FQDN des funktionierenden Back-Ends im Feld **SQL Server Store** ein (in unserem Beispiel BE2.contoso.com).
    
      - Klicken Sie mit der rechten Maustaste auf den Knoten lync Server 2013, klicken Sie auf **Topologie**, und klicken Sie dann auf **veröffentlichen**.
    
      - Starten Sie Dienste neu, damit jeder Server die neue Topologie lesen kann. Führen Sie in einer lync Server-Verwaltungsshell die folgenden Cmdlets auf jedem Front-End-Server aus, der zu diesem Pool gehört:
        
            Stop-CsWindowsService
            Start-CsWindowsService

5.  Deinstallieren Sie die Spiegelung. Führen Sie in einer lync Server-Verwaltungsshell das folgende Cmdlet aus:
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn <MirrorServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    Beispiel:
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn DB2.contoso.com -SqlInstanceName rtc -verbose
    
    Führen Sie diese Schritte für alle Datenbanktypen auf diesem Server aus.

6.  Erstellen Sie einen sauberen oder neuen Server mit dem gleichen FQDN (in diesem Beispiel db1.contoso.com) wie der fehlerhafte Computer, installieren Sie das Betriebssystem, und stellen Sie die Zertifikate dann wieder her oder registrieren Sie Sie erneut. Dieser Server wird als neue Spiegelungsfunktion verwendet.

7.  Melden Sie sich bei einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist, beim neuen Server an.

8.  Installieren Sie SQL Server 2012 oder SQL Server 2008 R2, und halten Sie die Namen der Instanz wie vor dem Fehler.

9.  Melden Sie sich bei einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist, bei einem Front-End-Server an.

10. Verwenden Sie den Topologie-Generator zum Installieren der Spiegelungs-DB. Führen Sie die folgenden Schritte aus:
    
      - Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topology Builder**.
    
      - Aktivieren der Spiegelung auf dem Back-End-Server. Klicken Sie dazu mit der rechten Maustaste auf den Pool unter **Enterprise Edition-Front-End-Pools** , und wählen Sie **Eigenschaften bearbeiten**aus. Aktivieren Sie auf der Registerkarte **Allgemein** unter **Zuordnungen**das Kontrollkästchen **Spiegelung des SQL Server-Speichers aktivieren** . Dies gilt auch für die Archivierung und Überwachung, falls erforderlich.
        
        Geben Sie im Feld **Spiegelung des SQL Server** -Speichers den FQDN des neuen Servers ein (n diesem Beispiel BE1.contoso.com). Klicken Sie dann auf **OK**.
    
      - Klicken Sie mit der rechten Maustaste auf den lync Server 2013-Knoten, klicken Sie auf **Topologie**, und klicken Sie dann auf **Datenbank installieren**.
    
      - Folgen Sie dem Assistenten zum **Installieren der Datenbank** . Wählen Sie auf der Seite **Create** Databases die Datenbanken aus, die Sie neu erstellen möchten.
    
      - Folgen Sie dem Assistenten, bis Sie zur Eingabeaufforderung gelangen, **Spiegelungsdatenbank erstellen**. Wählen Sie die Datenbank aus, die Sie installieren möchten, und führen Sie diesen Vorgang aus.

</div>

</div>

<span> </span>

</div>

</div>

</div>

