---
title: 'Lync Server 2013: Veröffentlichen der Topologie'
description: 'Lync Server 2013: veröffentlichen Sie die Topologie.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish the topology
ms:assetid: 3b5a744b-b3a8-4538-a55e-e2e4f72dff47
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425880(v=OCS.15)
ms:contentKeyID: 48183866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 453fe186a02c88a5dcd7308096b661058fc04aa6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547721"
---
# <a name="publish-the-topology-in-lync-server-2013"></a>Veröffentlichen der Topologie in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-10-01_

Für eine erfolgreiche Veröffentlichung, Aktivierung oder Deaktivierung einer Topologie beim Hinzufügen oder Entfernen einer Serverrolle müssen Sie als Mitglied der Gruppen "RTCUniversalServerAdmins" und "Domänen-Admins" angemeldet sein. Es ist auch möglich, die geeigneten Administratorrechte und -berechtigungen zu delegieren. Ausführliche Informationen finden Sie unter [Delegate Setup Permissions in lync Server 2013](lync-server-2013-delegate-setup-permissions.md). Für andere Konfigurationsänderungen müssen Sie lediglich Mitglied der Gruppe "RTCUniversalServerAdmins" sein.

Nachdem Sie Ihre Topologie im Topologie-Generator definiert haben, müssen Sie die Topologie im zentralen Verwaltungsspeicher veröffentlichen. Der zentrale Verwaltungsspeicher bietet eine robuste, schematisierten Speicherung der Daten, die für die Definition, Einrichtung, Verwaltung, Verwaltung, Beschreibung und den Betrieb einer lync Server 2013-Bereitstellung benötigt werden. Außerdem werden die Daten überprüft, um die Konsistenz der Konfiguration zu gewährleisten. Alle Änderungen an diesen Konfigurationsdaten erfolgen im zentralen Verwaltungsspeicher, wodurch nicht mehr synchrone Probleme auftreten. Schreibgeschützte Kopien der Daten werden auf alle Server in der Topologie repliziert, Edgeserver eingeschlossen.

<div>


> [!NOTE]  
> SQL Server benötigt mindestens 20 GB freien Speicherplatz, um die anfängliche Topologie erfolgreich zu veröffentlichen und den zentralen Verwaltungs Server zu erstellen.



</div>

<div>


> [!NOTE]  
> Nur Enterprise Edition: Zum Veröffentlichen der Topologie muss der SQL Server-basierte Back-End-Server online und über die eingerichteten Firewallausnahmen erreichbar sein. Ausführliche Informationen zum Angeben von Firewall-Ausnahmen finden Sie unter <A href="lync-server-2013-understanding-firewall-requirements-for-sql-server.md">Understanding Firewall Requirements for SQL Server with lync Server 2013</A>. Ausführliche Informationen zum Konfigurieren von SQL Server finden Sie unter <A href="lync-server-2013-configure-sql-server-for-lync-server.md">configure SQL Server for lync Server 2013</A>.



</div>

<div>

## <a name="to-publish-a-topology"></a>So veröffentlichen Sie eine Topologie

1.  Starten Sie den Topologie-Generator: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topologie-Generator**.

2.  Öffnen Sie die Topologie aus einer lokalen Datei. Wenn Sie an dem Computer arbeiten, an dem Sie die Topologie definiert haben, ist dies der Speicherort, an dem Sie die Datei zuvor gespeichert haben. In der Regel ist dies der Ordner "Dokumente" des Benutzers, der die Topologie konfiguriert hat.

3.  Klicken Sie mit der rechten Maustaste auf den Knoten **lync Server 2013** , und klicken Sie dann auf **Topologie veröffentlichen**.

4.  Klicken Sie auf der Seite **Topologie veröffentlichen** auf **Weiter**.

5.  Wählen Sie auf der Seite **Datenbanken erstellen** die Datenbanken, die Sie veröffentlichen möchten.
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie nicht über die erforderlichen Rechte zum Erstellen der Datenbanken verfügen, können Sie die Kontrollkästchen neben diesen Datenbanken deaktivieren, und ein Benutzer mit den entsprechenden Berechtigungen kann später die Datenbankenerstellen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment Permissions for SQL Server in lync Server 2013</A>.

    
    </div>

6.  Klicken Sie optional auf **Erweitert**. Mit den Optionen für erweiterte SQL Server-Platzierung von Datendateien können Sie zwischen den folgenden Optionen auswählen:
    
      - **Speicherort für Datenbankdateien automatisch bestimmen** – Bei Auswahl dieser Option wird optimale Leistung basierend auf der Festplattenkonfiguration für Ihren SQL Server-basierten Server gewährleistet, indem die Protokoll- und Datendateien verteilt platziert werden.
    
      - **Standardpfade der SQL Server-Instanz verwenden** – Bei Auswahl dieser Option werden die Protokoll- und Datendateien gemäß den Instanzeneinstellungen auf dem SQL Server-basierten Server platziert. Diese Option macht keinen Gebrauch von der Funktion des SQL Server-basierten Servers zum Ermitteln der optimalen Speicherorte für Protokolle und Daten. Der SQL Server-Administrator verschiebt die Protokoll- und Datendateien in der Regel an Speicherorte, die für den SQL Server-basierten Server geeignet sind und den Verwaltungsverfahren für die Organisation entsprechen.
    
    Klicken Sie auf **OK** und dann auf **Weiter**.

7.  Wählen Sie auf der Seite **zentralen Verwaltungs Server auswählen** eine Front-End-Pool aus.

8.  Klicken Sie optional auf **Erweitert**. Mit den Optionen für erweiterte SQL Server-Platzierung von Datendateien können Sie zwischen den folgenden Optionen auswählen:
    
      - **Speicherort für Datenbankdateien automatisch bestimmen** – Bei Auswahl dieser Option wird optimale Leistung basierend auf der Festplattenkonfiguration für Ihren SQL Server-basierten Server gewährleistet, indem die Protokoll- und Datendateien verteilt platziert werden.
    
      - **Standardpfade der SQL Server-Instanz verwenden** – Bei Auswahl dieser Option werden die Protokoll- und Datendateien gemäß den Instanzeneinstellungen auf dem SQL Server-basierten Server platziert. Diese Option macht keinen Gebrauch von der Funktion des SQL Server-basierten Servers zum Ermitteln der optimalen Speicherorte für Protokolle und Daten. Der SQL Server-Administrator verschiebt die Protokoll- und Datendateien in der Regel an Speicherorte, die für den SQL Server-basierten Server geeignet sind und den Verwaltungsverfahren für die Organisation entsprechen.
    
    Klicken Sie auf **OK**.

9.  Klicken Sie auf **Weiter**, um die Veröffentlichung abzuschließen.

10. Klicken Sie nach Abschluss der Veröffentlichung auf **Fertig stellen**.
    
    Wenn die Topologie erfolgreich veröffentlicht wurde, können Sie mit der Installation eines lokalen Replikats des zentralen Verwaltungsspeichers auf jedem Server beginnen, auf dem lync Server 2013 in Ihrer Topologie ausgeführt wird. Es wird empfohlen, mit dem ersten Front-End-Pool zu beginnen.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Einrichten von Front-End-Servern und Front-End-Pools für lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

