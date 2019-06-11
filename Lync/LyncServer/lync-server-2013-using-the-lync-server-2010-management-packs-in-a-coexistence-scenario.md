---
title: Verwenden der lync Server 2010-Verwaltungspakete in einem Koexistenz-Szenario
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using the Lync Server 2010 management packs in a coexistence scenario
ms:assetid: 8b792503-bd88-47fe-9d97-b071e8d429a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205078(v=OCS.15)
ms:contentKeyID: 48184772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 159aaa55e61068356701abaed3c0a67a60265c75
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847316"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-lync-server-2010-management-packs-in-a-coexistence-scenario"></a>Verwenden der lync Server 2010-Verwaltungspakete in einem Koexistenz-Szenario

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-22_

Viele Kunden nehmen ein Rollout-Programm innerhalb ihrer Unternehmen an, in dem Benutzer schrittweise von Microsoft lync Server 2010 zu lync Server 2013 migriert werden. Die Administratoren in diesen Unternehmen kümmern sich um die Überwachung beider lync Server-Versionen, um sicherzustellen, dass alle Endbenutzer die bestmögliche Kommunikationserfahrung erhalten. In diesem Szenario unterstützt das lync Server 2013-Management Pack einen parallelen Migrationspfad mit dem lync Server 2010-Management Pack.

In lync Server 2010 wurden lync Server-Computer über das Topologie-Dokument ermittelt, das mit dem zentralen Verwaltungsspeicher gespeichert wurde. In dieser Konfiguration meldet ein einzelner Computer das vorhanden sein aller anderen lync Server-Computer.

Die Management Packs für lync Server 2013 verwenden jetzt die Ermittlung auf Computerebene anstelle des zentralen Ermittlungsmechanismus, der in lync Server 2010 verwendet wurde. Dies bedeutet, dass sich jeder System Center-Agent im wesentlichen selbst erkennt und seine Existenz an System Center Operations Manager meldet. Die Verwendung der Ermittlung auf Computerebene vereinfacht die Verwaltung ihrer System Center-Infrastruktur und ermöglicht auch die unterschiedlichen Versionen der lync Server-Verwaltungspakete (beispielsweise Management Packs für lync Server 2010 und Management Packs für lync Server 2013). , um einfacher koexistieren zu können.

Um diese Migration zu unterstützen, müssen Sie zunächst Ihre vorhandene lync Server 2010-Überwachung aktualisieren, um Lücken in der Berichterstattung zu vermeiden. Wählen Sie dazu einen vorhandenen lync Server 2010-Computer aus, um das zentrale Ermittlungsskript für den lync Server 2010 zu warten, bevor Sie den zentralen Verwaltungsspeicher auf lync Server 2013 aktualisieren. Hierbei handelt es sich um einen vierstufigen Prozess:

1.  Aktualisieren Sie die lync Server 2010-Verwaltungspakete auf Kumulatives Update 7.

2.  Weisen Sie einen lync Server 2010-Computer an, das zentrale Ermittlungsskript auszuführen.

3.  Überschreiben Sie den zentralen Ermittlungs Kandidaten im Microsoft lync Server 2010-Management Pack.

4.  Überprüfen Sie, ob der neue Central Discovery-Kandidat gefunden wurde.

<div>

## <a name="instructing-a-lync-server-2010-computer-to-run-the-central-discovery-script"></a>Anweisen eines lync Server 2010-Computers zum Ausführen des zentralen Ermittlungsskripts

Wenn Sie einen nicht zentralen Verwaltungsspeicher Computer benennen möchten (beispielsweise einen lync Server-Front-End-Server), der die zentrale Ermittlung behandeln soll, müssen Sie den folgenden Registrierungsschlüssel auf dem nicht zentralen Verwaltungsspeicher Server erstellen:

HKLM\\Software\\Microsoft\\Real-Time Communications\\Health\\CentralDiscoveryCandidate

Sie können diesen Registrierungsschlüssel erstellen, indem Sie die folgenden Schritte ausführen:

1.  Klicken Sie auf **Start** und dann auf **Ausführen**.

2.  Geben Sie im Dialogfeld **Ausführen** den **Befehl regedit** ein, und drücken Sie dann die EINGABETASTE.

3.  Erweitern Sie im Registrierungs- **Editor\_HKEY\_lokaler Computer**, erweitern Sie **Software**, erweitern Sie **Microsoft**, und erweitern Sie dann die **Echtzeitkommunikation**.

4.  Klicken Sie mit der rechten Maustaste auf **Status**, klicken Sie auf **neu**, und klicken Sie dann auf **Taste**. Wenn der **Integritäts** Schlüssel nicht vorhanden ist, klicken Sie mit der rechten Maustaste auf **Echtzeitkommunikation**, zeigen Sie auf **neu**, und klicken Sie dann auf **Taste**. Wenn Sie den neuen Schlüssel erstellen, geben Sie Gesundheit ein, und drücken Sie dann die EINGABETASTE.
    
    Nachdem der neue Schlüssel erstellt wurde, geben Sie **CentralDiscoveryCandidate** ein, und drücken Sie dann die EINGABETASTE, um den Schlüssel umzubenennen.

Es kann den Computer mehrere Stunden dauern, bis diese Änderung abgeholt wird. Damit die Änderung sofort wirksam wird, beenden Sie den Integritäts-Agent-Dienst, und starten Sie ihn dann erneut. Führen Sie die folgenden Schritte auf dem lync Server 2010-Computer aus, um den Integritäts-Agent-Dienst erneut zu starten:

1.  Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Zubehör**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und klicken Sie dann auf **als Administrator ausführen**.

2.  Geben Sie im Konsolenfenster den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE:
    
        Net stop HealthService

3.  Es wird eine Meldung angezeigt, die besagt, dass "der System Center-Verwaltungsdienst beendet wird", gefolgt von einer zweiten Meldung, die besagt, dass der Dienst angehalten wurde. Nachdem der Dienst beendet wurde, können Sie ihn erneut starten, indem Sie den folgenden Befehl eingeben und die EINGABETASTE drücken:
    
        Net start HealthService

</div>

<div>

## <a name="overriding-the-central-discovery-candidate-in-the-lync-server-2010-management-pack"></a>Überschreiben des zentralen Ermittlungs Kandidaten im lync Server 2010-Management Pack

Nachdem Sie einen lync Server 2010-Computer angewiesen haben, auf lync Server 2010-Computern zu berichten, müssen Sie das lync Server 2010-Management Pack auch über diese Änderung informieren. Dazu müssen Sie im Management Pack eine Außerkraftsetzung erstellen. Dazu können Sie die folgenden Schritte ausführen:

1.  Klicken Sie in der Operations Manager-Konsole auf **Dokumenterstellung**.

2.  Erweitern Sie auf der Registerkarte Dokumenterstellung den Knoten **Management Pack-Objekte**, klicken Sie auf **Objektermittlungen**, und klicken Sie dann auf **Bereich**.

3.  Wählen Sie im Dialogfeld **Scope Management Pack-Objekte** das Element mit dem Ziel **ls Discovery Candidate** aus, und klicken Sie dann auf **OK**. Beachten Sie, dass der ls-Ermittlungs Kandidat nur angezeigt wird, wenn Sie das lync Server 2010-Management Pack installiert haben.

4.  Klicken Sie in der Operations Manager-Konsole mit der rechten Maustaste auf **ls Discovery Candidate**, zeigen Sie auf **außer Kraft**setzungen, zeigen Sie auf **Objektermittlung außer Kraft setzen**, und klicken Sie dann auf **für alle Objekte der Klasse: ls Discovery Candidate**.

5.  Aktivieren Sie im Dialogfeld **Eigenschaften außer Kraft setzen** das Kontrollkästchen **außer Kraft setzen** neben dem FQDN des Parameters **Central Discovery WatcherNode**. Geben Sie den vollqualifizierten Domänennamen des lync Server 2010-Computers in die Felder **Außerkraftsetzungswert** und **effektiver Wert** ein. Aktivieren Sie das Kontrollkästchen **erzwungen** , und klicken Sie auf **OK**.

Nachdem Sie die Außerkraftsetzung erstellt haben, müssen Sie den Integritätsdienst auf dem Stamm Verwaltungs Server erneut starten. Führen Sie den folgenden Vorgang auf dem Stamm Verwaltungs Server aus, um den Integritätsdienst erneut zu starten:

1.  Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Zubehör**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und klicken Sie dann auf **als Administrator ausführen**.

2.  Geben Sie im Konsolenfenster den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE:
    
        Net stop HealthService

3.  Es wird eine Meldung angezeigt, die besagt, dass "der System Center-Verwaltungsdienst beendet wird", gefolgt von einer zweiten Meldung, die besagt, dass der Dienst angehalten wurde. Nachdem der Dienst beendet wurde, können Sie ihn erneut starten, indem Sie den folgenden Befehl eingeben und die EINGABETASTE drücken:
    
        Net start HealthService

</div>

<div>

## <a name="verifying-that-the-new-central-discovery-candidate-was-discovered"></a>Überprüfen, ob der neue zentrale Discovery Candidate erkannt wurde

Der letzte Schritt vor dem Upgrade des zentralen Verwaltungsspeichers besteht darin, sicherzustellen, dass der neue zentrale Discovery-Kandidat vom lync Server 2010-Management Pack erkannt wurde. Öffnen Sie dazu die Operations Manager-Konsole, und klicken Sie dann auf Überwachung. Erweitern Sie auf der Registerkarte Überwachung den **Status Microsoft lync Server 2010**, erweitern Sie **Topologie Discovery**, und klicken Sie dann auf **Ermittlungsstatus Ansicht**. Überprüfen Sie, ob eine Zeile in der Anzeige einen **Pfad** enthält, in dem der vollqualifizierte Domänenname des zentralen Ermittlungs Kandidaten aufgeführt ist. Sie sollten auch sicherstellen, dass der Computerzustand als **Fehler**freigemeldet wird.

</div>

</div>

<span> </span>

</div>

</div>

</div>

