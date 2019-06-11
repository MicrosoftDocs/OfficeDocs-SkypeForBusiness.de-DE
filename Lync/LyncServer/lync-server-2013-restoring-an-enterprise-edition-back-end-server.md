---
title: 'Lync Server 2013: Wiederherstellen eines Enterprise Edition-Back-End-Servers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring an Enterprise Edition Back End Server
ms:assetid: 1450eb4e-3315-4d02-8f02-6e1791fb1550
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202163(v=OCS.15)
ms:contentKeyID: 51541446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e0121ee654846bcb60acc6da6847995b967a880
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823049"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-an-enterprise-edition-back-end-server-in-lync-server-2013"></a>Wiederherstellen eines Enterprise Edition-Back-End-Servers in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-18_

Verwenden Sie das in diesem Thema beschriebene Verfahren in den beiden folgenden Fällen:

  - Sowohl die primäre als auch die Spiegeldatenbank eines gespiegelten Enterprise Edition-Back-End-Servers schlagen fehl.

  - Ein Enterprise Edition-Back-End-Server, der nicht gespiegelt wird, schlägt fehl.

Wenn Sie ein Back-End für eine gespiegelte Enterprise-Edition haben und nur die Spiegelungs-oder primäre Datenbank fehlschlägt, finden Sie Informationen dazu unter [Wiederherstellen eines gespiegelten Enterprise Edition-Back-End-Servers in lync Server 2013 – primär](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md) zum Wiederherstellen der primären Datenbank und [Wiederherstellen Enterprise Edition-Back-End-Server in lync Server 2013 – Spiegelung](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md) zum Wiederherstellen der Spiegelung.

Wenn der zentrale Verwaltungsspeicher fehlschlägt, lesen Sie [Wiederherstellen des Servers, auf dem der zentrale Verwaltungsspeicher in lync Server 2013 gehostet](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)wird. Wenn ein Enterprise Edition-Mitgliedsserver, der nicht der Back-End-Server ist, fehlschlägt, lesen Sie [Wiederherstellen eines Enterprise Edition-Mitgliedsservers in lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md)

<div>


> [!TIP]  
> Wir empfehlen, dass Sie eine Image-Kopie des Systems erstellen, bevor Sie mit der Wiederherstellung beginnen. Sie können dieses Bild als Rollback-Punkt verwenden, falls während der Wiederherstellung etwas schief geht. Möglicherweise möchten Sie das Abbild kopieren, nachdem Sie das Betriebssystem und SQL Server installiert haben, und die Zertifikate wiederherstellen oder erneut registrieren.



</div>

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server"></a>Wiederherstellen eines Enterprise Edition-Back-End-Servers

1.  Beginnen Sie mit einem sauberen oder neuen Server mit dem gleichen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) wie der fehlerhafte Computer, installieren Sie das Betriebssystem, und stellen Sie die Zertifikate dann wieder her oder registrieren Sie Sie erneut.
    
    <div>
    

    > [!NOTE]  
    > Befolgen Sie die Server Bereitstellungsverfahren Ihrer Organisation, um diesen Schritt ausführen zu können.

    
    </div>

2.  Melden Sie sich von einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist, bei dem Server an, den Sie wiederherstellen möchten.

3.  Installieren Sie SQL Server 2012 oder SQL Server 2008 R2, und halten Sie die Namen der Instanz wie vor dem Fehler.
    
    <div>
    

    > [!NOTE]  
    > Je nach Bereitstellung umfasst der Back-End-Server möglicherweise mehrere zusammengefasste oder getrennte Datenbanken. Führen Sie die gleichen Schritte aus, um SQL Server zu installieren, den Sie ursprünglich für die Bereitstellung des Servers verwendet haben, einschließlich SQL Server-Berechtigungen und-Anmeldungen.

    
    </div>

4.  Nachdem Sie SQL Server installiert haben, führen Sie die folgenden Aktionen aus:
    
    1.  Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topology Builder**.
    
    2.  Klicken Sie auf **Topologie aus vorhandener Bereitstellung herunterladen**, und klicken Sie dann auf **OK**.
    
    3.  Wählen Sie die Topologie aus, und klicken Sie dann auf **Speichern**. Klicken Sie auf **Ja** , um die Auswahl zu bestätigen.
    
    4.  Klicken Sie mit der rechten Maustaste auf den **lync Server 2013** -Knoten, und klicken Sie dann auf **Topologie veröffentlichen**.
    
    5.  Folgen Sie dem Assistenten zum **Veröffentlichen der Topologie** . Wählen Sie auf der Seite **Create** Databases die Datenbanken aus, die Sie neu erstellen möchten.
        
        <div>
        

        > [!NOTE]  
        > Auf der Seite " <STRONG>Datenbankenerstellen</STRONG> " werden nur eigenständige Datenbanken angezeigt.

        
        </div>
    
    6.  Wenn Sie ein zurück gespiegeltes Back-End wiederherstellen, folgen Sie weiterhin dem restlichen Assistenten, bis die Aufforderung zum **Erstellen einer Spiegeldatenbank** angezeigt wird. Wählen Sie die Datenbank aus, die Sie installieren möchten, und schließen Sie den Vorgang ab.
    
    7.  Führen Sie den restlichen Assistenten aus, und klicken Sie dann auf **Fertig stellen**.
    
    <div>
    

    > [!TIP]  
    > Anstelle des Topologie-Generators können Sie das Cmdlet " <STRONG>install-CsDatabase</STRONG> " verwenden, um jede Datenbank zu erstellen, und das Cmdlet " <STRONG>install-CsMirrorDatabase</STRONG> ", um die Spiegelung zu konfigurieren. Ausführliche Informationen finden Sie in der Dokumentation zur lync Server-Verwaltungsshell.

    
    </div>

5.  Wiederherstellen von Benutzerdaten durch Ausführen der folgenden Schritte:
    
    1.  Kopieren Sie ExportedUserData. zip aus\\ $Backup in ein lokales Verzeichnis.
    
    2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.
    
    3.  Bevor Sie die Benutzerdaten wiederherstellen, müssen Sie lync-Dienste beenden. Geben Sie dazu Folgendes ein:
        
            Stop-CsWindowsService
    
    4.  Geben Sie zum Wiederherstellen der Benutzerdaten in der Befehlszeile Folgendes ein:
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        Beispiel:
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    5.  Starten Sie lync Services neu, indem Sie Folgendes eingeben:
        
            Start-CsWindowsService

6.  Wenn Sie die Reaktionsgruppe in diesem Pool bereitgestellt haben, stellen Sie die Konfigurationsdaten der Reaktionsgruppe wieder her. Ausführliche Informationen finden Sie unter [Wiederherstellen von Einstellungen für die Reaktionsgruppe in lync Server 2013](lync-server-2013-restoring-response-group-settings.md).

7.  Wenn Sie einen Back-End-Server wiederherstellen, der Archivierungs-oder Überwachungsdatenbanken enthielt, stellen Sie die Archivierungs-oder Überwachungsdaten mithilfe eines SQL Server-Tools wie SQL Server Management Studio wieder her. Ausführliche Informationen finden Sie unter [Wiederherstellen von Überwachungs-oder Archivierungsdaten in lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

