---
title: Wiederherstellen eines gespiegelten Enterprise Edition-Back-End-Servers – Spiegelung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring a mirrored Enterprise Edition Back End Server - mirror
ms:assetid: 4b3c8eae-6f1f-4377-b39b-6699e725c517
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945626(v=OCS.15)
ms:contentKeyID: 51541471
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 113d69d7aa39673686ff870c36a64bd1a8fe90f2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823077"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---mirror"></a>Wiederherstellen eines gespiegelten Enterprise Edition-Back-End-Servers in lync Server 2013 – Spiegelung

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-19_

Wenn Sie über einen Enterprise Edition-Back-End-Server in einer gespiegelten Konfiguration verfügen und nur die Spiegelung fehlschlägt, führen Sie die Verfahren in diesem Abschnitt aus. Wenn sowohl die primäre Datenbank als auch die Spiegelung fehlerhaft sind, lesen Sie [Wiederherstellen eines Enterprise Edition-Back-End-Servers in lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md). Wenn nur der primäre Fehler auftritt, lesen Sie [Wiederherstellen eines gespiegelten Enterprise Edition-Back-End-Servers in lync Server 2013 – primär](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md). Wenn die Datenbank, die den zentralen Verwaltungsspeicher hostet, fehlschlägt, lesen Sie [Wiederherstellen des Servers, auf dem der zentrale Verwaltungsspeicher in lync Server 2013 gehostet](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)wird. Wenn ein Enterprise Edition-Mitgliedsserver, der nicht der Back-End-Server ist, fehlschlägt, lesen Sie [Wiederherstellen eines Enterprise Edition-Mitgliedsservers in lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md)

Wir empfehlen, dass Sie eine Image-Kopie des Systems erstellen, bevor Sie mit der Wiederherstellung beginnen. Sie können dieses Bild als Rollback-Punkt verwenden, falls während der Wiederherstellung etwas schief geht. Möglicherweise möchten Sie das Abbild kopieren, nachdem Sie das Betriebssystem und SQL Server installiert haben, und die Zertifikate wiederherstellen oder erneut registrieren.

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-mirror-database"></a>So stellen Sie eine Spiegeldatenbank für den Back-End-Server eines Enterprise Edition

1.  Melden Sie sich bei einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist, bei einem Front-End-Server an.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Deinstallieren Sie die Spiegelung. Geben Sie zuerst das folgende Cmdlet ein:
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn <PrimaryServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    Beispiel:
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn server4.contoso.com -SqlInstanceName archinst -verbose
    
    Führen Sie diese Schritte für alle Datenbanktypen auf diesem Server aus.

4.  Erstellen Sie einen sauberen oder neuen Server mit dem gleichen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) (db1.contoso.com) wie der fehlerhafte Computer, installieren Sie das Betriebssystem, und stellen Sie die Zertifikate dann wieder her oder registrieren Sie Sie erneut. Dieser Server wird als neue Spiegelungsfunktion verwendet.

5.  Melden Sie sich bei einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist, beim neuen Server an.

6.  Installieren Sie SQL Server 2012 oder SQL Server 2008 R2, und halten Sie die Namen der Instanz wie vor dem Fehler.

7.  Melden Sie sich bei einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist, bei einem Front-End-Server an.

8.  Verwenden Sie den Topologie-Generator, um die Spiegeldatenbank zu installieren. Führen Sie die folgenden Aktionen aus:
    
      - Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topology Builder**.
    
      - Klicken Sie mit der rechten Maustaste auf den lync Server 2013-Knoten, klicken Sie auf **Topologie**, und klicken Sie dann auf **Datenbank installieren**.
    
      - Folgen Sie dem Assistenten zum **Installieren der Datenbank** . Wählen Sie auf der Seite **Create** Databases die Datenbanken aus, die Sie neu erstellen möchten.
    
      - Folgen Sie dem Assistenten, bis eine Aufforderung zum **Erstellen einer Spiegeldatenbank** angezeigt wird. Wählen Sie die Datenbank aus, die Sie installieren möchten, und führen Sie diesen Vorgang aus.
        
        <div>
        

        > [!TIP]
        > Anstelle des Topologie-Generators können Sie das Cmdlet <STRONG>install-CsMirrorDatabase</STRONG> verwenden, um die Spiegelung zu konfigurieren. Ausführliche Informationen finden Sie in der Dokumentation zur lync Server-Verwaltungsshell.

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

