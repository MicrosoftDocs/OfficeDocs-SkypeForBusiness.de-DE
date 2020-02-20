---
title: Wiederherstellen eines gespiegelten Enterprise Edition-Back-End-Servers-Mirror
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a mirrored Enterprise Edition Back End Server - mirror
ms:assetid: 4b3c8eae-6f1f-4377-b39b-6699e725c517
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945626(v=OCS.15)
ms:contentKeyID: 51541471
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ba7b078df74b2ffde5c6da137b052b93d37d18b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144742"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---mirror"></a>Wiederherstellen eines gespiegelten Enterprise Edition-Back-End-Servers in lync Server 2013-Mirror

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-19_

Wenn Sie einen Enterprise Edition-Back-End-Server in einer gespiegelten Konfiguration haben und nur die Spiegelung fehlschlägt, befolgen Sie die Verfahren in diesem Abschnitt. Wenn sowohl die primäre Datenbank als auch die Spiegelung fehlerhaft sind, finden Sie unter [Wiederherstellen eines Enterprise Edition-Back-End-Servers in lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md). Wenn nur der primäre Fehler auftritt, lesen Sie [Wiederherstellen eines gespiegelten Enterprise Edition-Back-End-Servers in lync Server 2013-Primary](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md). Wenn die Datenbank, die den zentralen Verwaltungsspeicher hostet, fehlschlägt, lesen Sie [Wiederherstellen des Servers, der den zentralen Verwaltungsspeicher in lync Server 2013 hostet](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md). Wenn ein Enterprise Edition-Mitgliedsserver, lync Server 2013 bei dem es sich nicht um den Back-End-Server handelt, fehlerhaft ist, finden Sie unter [Wiederherstellen eines Enterprise Edition](lync-server-2013-restoring-an-enterprise-edition-member-server.md)

Es wird empfohlen, eine Abbild Kopie des Systems zu erstellen, bevor Sie mit der Wiederherstellung beginnen. Sie können dieses Bild als Rollback-Argument verwenden, falls während der Wiederherstellung etwas schief geht. Möglicherweise möchten Sie das Abbild kopieren, nachdem Sie das Betriebssystem installiert und SQL Server und die Zertifikate wiederhergestellt oder erneut registriert haben.

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-mirror-database"></a>So stellen Sie eine Spiegeldatenbank einer Enterprise Edition-Back-End-Server

1.  Melden Sie sich von einem Benutzerkonto, das Mitglied der Gruppe RTCUniversalServerAdmins ist, bei einem Front-End-Server an.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Deinstallieren Sie die Spiegelung. Geben Sie zuerst das folgende Cmdlet ein:
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn <PrimaryServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    Zum Beispiel:
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn server4.contoso.com -SqlInstanceName archinst -verbose
    
    Tun Sie dies für alle Datenbanktypen auf diesem Server.

4.  Erstellen Sie einen sauberen oder neuen Server mit dem gleichen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) (db1.contoso.com) als fehlerhaften Computer, installieren Sie das Betriebssystem, und stellen Sie die Zertifikate dann wieder her oder registrieren Sie Sie erneut. Dieser Server wird als neue Spiegelungsfunktion fungieren.

5.  Melden Sie sich bei einem Benutzerkonto, das Mitglied der Gruppe RTCUniversalServerAdmins ist, am neuen Server an.

6.  Installieren Sie SQL Server 2012 oder SQL Server 2008 R2, und halten Sie die Namen der Instanz so wie vor dem Fehler.

7.  Melden Sie sich von einem Benutzerkonto, das Mitglied der Gruppe RTCUniversalServerAdmins ist, bei einem Front-End-Server an.

8.  Verwenden Sie den Topologie-Generator, um die Spiegeldatenbank zu installieren. Führen Sie die folgenden Schritte aus:
    
      - Starten Sie den Topologie-Generator: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topologie-Generator**.
    
      - Klicken Sie mit der rechten Maustaste auf den Knoten lync Server 2013, klicken Sie auf **Topologie**, und klicken Sie dann auf **Datenbank installieren**.
    
      - Führen Sie den Assistenten zum **Installieren einer Datenbank** aus. Wählen Sie auf der Seite **Datenbankenerstellen** die Datenbanken aus, die Sie neu erstellen möchten.
    
      - Führen Sie den Assistenten aus, bis eine Aufforderung zum **Erstellen einer Spiegeldatenbank** angezeigt wird. Wählen Sie die Datenbank aus, die Sie installieren möchten, und führen Sie diesen Vorgang aus.
        
        <div>
        

        > [!TIP]
        > Anstatt den Topologie-Generator auszuführen, können Sie das Cmdlet <STRONG>install-CsMirrorDatabase</STRONG> verwenden, um die Spiegelung zu konfigurieren. Ausführliche Informationen finden Sie in der Dokumentation zur Lync Server-Verwaltungsshell.

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

