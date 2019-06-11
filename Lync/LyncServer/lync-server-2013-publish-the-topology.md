---
title: 'Lync Server 2013: Veröffentlichen der Topologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Publish the topology
ms:assetid: 3b5a744b-b3a8-4538-a55e-e2e4f72dff47
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425880(v=OCS.15)
ms:contentKeyID: 48183866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fee3b14776c6cdf6ddd52ada724d3d4a6d6a245a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823966"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-the-topology-in-lync-server-2013"></a>Veröffentlichen der Topologie in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-10-01_

Um eine Topologie beim Hinzufügen oder Entfernen einer Serverrolle erfolgreich zu veröffentlichen, zu aktivieren oder zu deaktivieren, sollten Sie als Benutzer angemeldet sein, der Mitglied der Gruppen RTCUniversalServerAdmins und Domänenadministratoren ist. Es ist auch möglich, die richtigen Administratorrechte und-Berechtigungen zu delegieren. Ausführliche Informationen finden Sie unter Delegieren von [Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md). Bei anderen Konfigurationsänderungen ist nur die Mitgliedschaft in der RTCUniversalServerAdmins-Gruppe erforderlich.

Nachdem Sie Ihre Topologie im Topologie-Generator definiert haben, müssen Sie die Topologie im zentralen Verwaltungsspeicher veröffentlichen. Der zentrale Verwaltungsspeicher bietet eine robuste, schematisierten Speicherung der Daten, die zum definieren, einrichten, verwalten, verwalten, beschreiben und betreiben einer lync Server 2013-Bereitstellung erforderlich sind. Außerdem werden die Daten überprüft, um die Konsistenz der Konfiguration zu gewährleisten. Alle Änderungen an diesen Konfigurationsdaten erfolgen im zentralen Verwaltungsspeicher, wodurch Synchronisierungsprobleme beseitigt werden. Schreibgeschützte Kopien der Daten werden auf alle Server in der Topologie repliziert, einschließlich Edgeserver.

<div>


> [!NOTE]  
> SQL Server benötigt eine Mindestmenge von 20 GB freien Speicherplatz, um die ursprüngliche Topologie erfolgreich zu veröffentlichen und den zentralen Verwaltungs Server zu erstellen.



</div>

<div>


> [!NOTE]  
> Nur für Enterprise Edition: um die Topologie zu veröffentlichen, muss der auf SQL Server basierende Back-End-Server online sein und über Firewall-Ausnahmen zugänglich sein. Details zum Angeben von Firewall-Ausnahmen finden Sie unter <A href="lync-server-2013-understanding-firewall-requirements-for-sql-server.md">Grundlegendes zu Firewall-Anforderungen für SQL Server mit lync Server 2013</A>. Details zum Konfigurieren von SQL Server finden Sie unter <A href="lync-server-2013-configure-sql-server-for-lync-server.md">Konfigurieren von SQL Server für lync Server 2013</A>.



</div>

<div>

## <a name="to-publish-a-topology"></a>So veröffentlichen Sie eine Topologie

1.  Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topology Builder**.

2.  Wählen Sie aus, um die Topologie aus einer lokalen Datei zu öffnen. Wenn Sie sich auf dem Computer befinden, auf dem Sie die Topologie definiert haben, befindet sich diese an dem Speicherort, an dem Sie Sie in früheren Schritten gespeichert haben. In der Regel handelt es sich hierbei um den Ordner "Dokumente" des Benutzers, der die Topologie konfiguriert hat.

3.  Klicken Sie mit der rechten Maustaste auf den **lync Server 2013** -Knoten, und klicken Sie dann auf **Topologie veröffentlichen**.

4.  Klicken Sie auf der Seite **Topologie veröffentlichen** auf **Weiter**.

5.  Wählen Sie auf der Seite **Create** Databases die Datenbanken aus, die Sie veröffentlichen möchten.
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie nicht über die erforderlichen Rechte zum Erstellen der Datenbanken verfügen, können Sie die Kontrollkästchen neben diesen Datenbanken deaktivieren, und ein Benutzer mit den entsprechenden Rechten kann später die Datenbankenerstellen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Bereitstellungsberechtigungen für SQL Server in lync Server 2013</A>.

    
    </div>

6.  Klicken Sie optional auf **Erweitert**. Mit den erweiterten Optionen für SQL Server-Datendatei Platzierungen können Sie zwischen den folgenden Optionen auswählen:
    
      - **Speicherort für Datenbankdateien automatisch ermitteln** – mit dieser Option wird die optimale Betriebsleistung basierend auf der Datenträgerkonfiguration auf dem SQL Server-basierten Server ermittelt, indem die Protokoll-und Datendateien an den besten Speicherort verteilt werden.
    
      - **Standardpfade der SQL Server-Instanz verwenden**: Bei Auswahl dieser Option werden die Protokoll- und Datendateien gemäß den Instanzeneinstellungen auf dem SQL Server-basierten Server platziert. Diese Option macht keinen Gebrauch von der Funktion des SQL Server-basierten Servers zum Ermitteln der optimalen Speicherorte für Protokolle und Daten. Der SQL Server-Administrator verschiebt die Protokoll- und Datendateien in der Regel an Speicherorte, die für den SQL Server-basierten Server geeignet sind und den Verwaltungsverfahren für die Organisation entsprechen.
    
    Klicken Sie auf **OK** und dann auf **Weiter**.

7.  Wählen Sie auf der Seite **Central Management Server auswählen** einen Front-End-Pool aus.

8.  Klicken Sie optional auf **Erweitert**. Mit den erweiterten Optionen für die SQL Server-Datendatei Platzierung können Sie zwischen den folgenden Optionen auswählen:
    
      - **Speicherort für Datenbankdateien automatisch ermitteln** – mit dieser Option wird die optimale Betriebsleistung basierend auf der Datenträgerkonfiguration auf dem SQL Server-basierten Server ermittelt, indem die Protokoll-und Datendateien an den besten Speicherort verteilt werden.
    
      - **Standardpfade der SQL Server-Instanz verwenden**: Bei Auswahl dieser Option werden die Protokoll- und Datendateien gemäß den Instanzeneinstellungen auf dem SQL Server-basierten Server platziert. Diese Option macht keinen Gebrauch von der Funktion des SQL Server-basierten Servers zum Ermitteln der optimalen Speicherorte für Protokolle und Daten. Der SQL Server-Administrator verschiebt die Protokoll- und Datendateien in der Regel an Speicherorte, die für den SQL Server-basierten Server geeignet sind und den Verwaltungsverfahren für die Organisation entsprechen.
    
    Klicken Sie anschließend auf **OK**.

9.  Klicken Sie auf **Weiter**, um die Veröffentlichung abzuschließen.

10. Wenn der Veröffentlichungsprozess abgeschlossen ist, klicken Sie auf **Fertig stellen**.
    
    Wenn die Topologie erfolgreich veröffentlicht wurde, können Sie mit der Installation eines lokalen Replikats des zentralen Verwaltungsspeichers auf jedem Server mit lync Server 2013 in Ihrer Topologie beginnen. Es wird empfohlen, mit dem ersten Front-End-Pool zu beginnen.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Einrichten von Front-End-Servern und Front-End-Pools für Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

