---
title: 'Lync Server 2013: Wiederherstellen eines Enterprise Edition-Back-End-Servers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring an Enterprise Edition Back End Server
ms:assetid: 1450eb4e-3315-4d02-8f02-6e1791fb1550
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202163(v=OCS.15)
ms:contentKeyID: 51541446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9780963614a1d0f5049fdc5226391e2ee2b6d59c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511542"
---
# <a name="restoring-an-enterprise-edition-back-end-server-in-lync-server-2013"></a>Wiederherstellen eines Enterprise Edition-Back-End-Servers in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-18_

Verwenden Sie das in diesem Thema beschriebene Verfahren in den folgenden beiden Fällen:

  - Sowohl die primäre als auch die Spiegeldatenbank eines gespiegelten Enterprise Edition-Back-End-Servers schlagen fehl.

  - Ein nicht gespiegelter Enterprise Edition-Back-End-Server schlägt fehl.

Wenn Sie ein gespiegeltes Enterprise Edition-Back-End haben und nur die Spiegelung oder primäre Datenbank ausfällt, finden Sie weitere Informationen unter [Wiederherstellen eines gespiegelten Enterprise Edition-Back-End-Servers in lync Server 2013-Primary](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md) zum Wiederherstellen der primären Datenbank und [Wiederherstellen eines gespiegelten Enterprise Edition-Back-End-Servers in lync Server 2013-Mirror](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md)

Wenn der zentrale Verwaltungsspeicher fehlschlägt, finden Sie weitere Informationen unter [Wiederherstellen des Servers, der den zentralen Verwaltungsspeicher in lync Server 2013 hostet](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md). Wenn ein Enterprise Edition-Mitgliedsserver, lync Server 2013 bei dem es sich nicht um den Back-End-Server handelt, fehlerhaft ist, finden Sie unter [Wiederherstellen eines Enterprise Edition](lync-server-2013-restoring-an-enterprise-edition-member-server.md)

<div>


> [!TIP]  
> Es wird empfohlen, eine Abbild Kopie des Systems zu erstellen, bevor Sie mit der Wiederherstellung beginnen. Sie können dieses Bild als Rollback-Argument verwenden, falls während der Wiederherstellung etwas schief geht. Möglicherweise möchten Sie das Abbild kopieren, nachdem Sie das Betriebssystem installiert und SQL Server und die Zertifikate wiederhergestellt oder erneut registriert haben.



</div>

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server"></a>So stellen Sie einen Back-End-Server der Enterprise Edition wieder her

1.  Beginnen Sie mit einem sauberen oder neuen Server mit dem gleichen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) wie der fehlerhafte Computer, installieren Sie das Betriebssystem, und stellen Sie dann die Zertifikate wieder her oder registrieren Sie Sie erneut.
    
    <div>
    

    > [!NOTE]  
    > Gehen Sie nach den in Ihrer Organisation gültigen Verfahren für die Serverbereitstellung vor, um diesen Schritt durchzuführen.

    
    </div>

2.  Melden Sie sich von einem Benutzerkonto, das Mitglied der Gruppe RTCUniversalServerAdmins ist, bei dem Server an, den Sie wiederherstellen.

3.  Installieren Sie SQL Server 2012 oder SQL Server 2008 R2, und halten Sie die Namen der Instanz so wie vor dem Fehler.
    
    <div>
    

    > [!NOTE]  
    > Je nach vorhandener Bereitstellung umfasst der Back-End-Server möglicherweise mehrere verbundene oder separate Datenbanken. Führen Sie das gleiche Verfahren zum Installieren von SQL Server durch, mit dem Sie auch ursprünglich den Server bereitgestellt haben, einschließlich SQL Server-Berechtigungen und -Anmeldungen.

    
    </div>

4.  Führen Sie nach dem Installieren von SQL Server folgende Schritte aus:
    
    1.  Starten Sie den Topologie-Generator: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topologie-Generator**.
    
    2.  Klicken Sie auf **Topologie aus einer vorhandenen Bereitstellung herunterladen**, und klicken Sie dann auf **OK**.
    
    3.  Wählen Sie die Topologie aus, und klicken Sie auf **Speichern**. Klicken Sie auf **Ja**, um die Auswahl zu bestätigen.
    
    4.  Klicken Sie mit der rechten Maustaste auf den Knoten **lync Server 2013** , und klicken Sie dann auf **Topologie veröffentlichen**.
    
    5.  Folgen Sie den Anweisungen im Assistenten zum Veröffentlichen der Topologie****. Wählen Sie auf der Seite **Datenbankenerstellen** die Datenbanken aus, die Sie neu erstellen möchten.
        
        <div>
        

        > [!NOTE]  
        > Auf der Seite <STRONG>Erstellen von Datenbanken</STRONG> werden nur eigenständige Datenbanken angezeigt.

        
        </div>
    
    6.  Wenn Sie ein gespiegeltes Back-End wiederherstellen, fahren Sie mit dem Rest des Assistenten fort, bis die Aufforderung zum **Erstellen einer Spiegeldatenbank** angezeigt wird. Wählen Sie die Datenbank aus, die Sie installieren möchten, und führen Sie den Vorgang aus.
    
    7.  Folgen Sie den Anweisungen auf den weiteren Seiten des Assistenten, und klicken Sie dann auf **Fertig stellen**.
    
    <div>
    

    > [!TIP]  
    > Anstatt den Topologie-Generator auszuführen, können Sie das Cmdlet <STRONG>install-CsDatabase</STRONG> verwenden, um die einzelnen Datenbanken zu erstellen, und das Cmdlet <STRONG>install-CsMirrorDatabase</STRONG> , um die Spiegelung zu konfigurieren. Einzelheiten finden Sie in der Dokumentation zur Lync Server-Verwaltungsshell.

    
    </div>

5.  Stellen Sie die Benutzerdaten wieder her, indem Sie die folgenden Schritte ausführen:
    
    1.  Kopieren Sie ExportedUserData.zip aus $Backup \\ in ein lokales Verzeichnis.
    
    2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.
    
    3.  Bevor Sie die Benutzerdaten wiederherstellen, müssen Sie lync-Dienste beenden. Geben Sie dazu Folgendes ein:
        
            Stop-CsWindowsService
    
    4.  Geben Sie in die Befehlszeile Folgendes ein, um die Benutzerdaten wiederherzustellen:
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        Beispiel:
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    5.  Starten Sie lync Services neu, indem Sie Folgendes eingeben:
        
            Start-CsWindowsService

6.  Wenn Sie die Reaktionsgruppe in diesem Pool bereitgestellt haben, stellen Sie die Konfigurationsdaten der Reaktionsgruppe wieder her. Ausführliche Informationen finden Sie unter [Wiederherstellen von Reaktionsgruppeneinstellungen in lync Server 2013](lync-server-2013-restoring-response-group-settings.md).

7.  Wenn Sie einen Back-End-Server wiederherstellen, auf dem sich Archivierungs- oder Überwachungsdatenbanken befanden, stellen Sie die Archivierungs- oder Überwachungsdaten mithilfe eines SQL Server-Tools wie etwa SQL Server Management Studio wieder her. Ausführliche Informationen finden Sie unter [Wiederherstellen von Überwachungs-oder Archivierungsdaten in lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

