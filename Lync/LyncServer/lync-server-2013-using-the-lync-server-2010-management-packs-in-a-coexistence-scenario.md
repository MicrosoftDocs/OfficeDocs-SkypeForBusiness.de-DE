---
title: Verwenden der lync Server 2010 Management Packs in einem Szenario für die Koexistenz
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Lync Server 2010 management packs in a coexistence scenario
ms:assetid: 8b792503-bd88-47fe-9d97-b071e8d429a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205078(v=OCS.15)
ms:contentKeyID: 48184772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bb614726458f2cf9c77bdfe740ddb13d99d54f2f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529922"
---
# <a name="using-the-lync-server-2010-management-packs-in-a-coexistence-scenario"></a>Verwenden der lync Server 2010 Management Packs in einem Szenario für die Koexistenz

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-22_

Viele Kunden nehmen ein Einführungsprogramm innerhalb ihrer Unternehmen an, in dem Benutzer schrittweise von Microsoft lync Server 2010 zu lync Server 2013 migriert werden. Die Administratoren dieser Unternehmen kümmern sich um die Überwachung beider Versionen von lync Server, um sicherzustellen, dass alle Ihre Endbenutzer die bestmögliche Kommunikationserfahrung erhalten. In diesem Szenario unterstützt das lync Server 2013 Management Pack einen Side-by-Side-Migrationspfad mit dem lync Server 2010 Management Pack.

In der lync Server 2010 wurden lync Server Computer über das im zentralen Verwaltungsspeicher gespeicherte Topologie-Dokument ermittelt. In dieser Konfiguration würde ein einzelner Computer das vorhanden sein aller anderen lync Server Computer melden.

Die Management Packs für lync Server 2013 verwenden jetzt die Ermittlung auf Computerebene anstelle des zentralen Ermittlungsmechanismus, der in lync Server 2010 verwendet wurde. Das bedeutet, dass sich jeder System Center-Agent im Prinzip selbst ermittelt und sein Vorhandensein dem System Center Operations Manager berichtet. Das Verwenden der Ermittlung auf Computerebene vereinfacht die Verwaltung ihrer System Center-Infrastruktur und ermöglicht außerdem eine einfachere Koexistenz verschiedener Versionen der lync Server Management Packs (beispielsweise von Management Packs für lync Server 2010 und Management Packs für lync Server 2013).

Zur Unterstützung dieser Migration müssen Sie zunächst die vorhandene lync Server 2010 Überwachung aktualisieren, um Lücken bei der Berichterstattung zu vermeiden. Wählen Sie dazu einen vorhandenen lync Server 2010 Computer aus, um das zentrale Ermittlungsskript für die lync Server 2010 zu warten, bevor Sie den zentralen Verwaltungsspeicher auf lync Server 2013 aktualisieren. Dies ist ein Prozess in vier Schritten:

1.  Aktualisieren Sie die lync Server 2010 Management Packs auf das kumulative Update 7.

2.  Weisen Sie einen lync Server 2010 Computer an, das zentrale Ermittlungsskript auszuführen.

3.  Überschreiben Sie den zentralen Discovery Candidate im Microsoft lync Server 2010 Management Pack.

4.  Stellen Sie sicher, dass der neue zentrale Ermittlungskandidat ermittelt wurde.

<div>

## <a name="instructing-a-lync-server-2010-computer-to-run-the-central-discovery-script"></a>Anweisen eines Lync Server 2010-Computer zum Ausführen eines zentralen Ermittlungsskripts

Wenn Sie einen nicht-zentralen Verwaltungsspeicher Computer (beispielsweise einen lync Server-Front-End-Server) für die zentrale Ermittlung benennen möchten, müssen Sie den folgenden Registrierungsschlüssel auf dem nicht-zentralen Verwaltungsspeicher Server erstellen:

HKLM \\ Software \\ Microsoft \\ Real-Time Communications \\ Health \\ CentralDiscoveryCandidate

Sie können diesen Registrierungsschlüssel erstellen, indem Sie das folgende Verfahren durchführen:

1.  Klicken Sie auf **Start** und dann auf **Ausführen**.

2.  Geben Sie im Dialogfeld **Ausführen** den Befehl **reged** ein, und drücken Sie die EINGABETASTE.

3.  Erweitern Sie im Registrierungs- **Editor \_ HKEY lokaler \_ Computer**, erweitern Sie **Software**, erweitern Sie **Microsoft**, und erweitern Sie dann **Echtzeitkommunikation**.

4.  Klicken Sie mit der rechten Maustaste auf **Status**, klicken Sie dann auf **Neu**, und klicken Sie anschließend auf **Schlüssel**. Wenn der Schlüssel **Status** nicht vorhanden ist, klicken Sie mit der rechten Maustaste auf **Real-Time Communications**, zeigen auf **Neu**, und klicken Sie dann auf **Schlüssel**. Wenn der neue Schlüssel erstellt wurde, geben Sie "Status" ein, und drücken Sie dann die EINGABETASTE.
    
    Geben Sie **CentralDiscoveryCandidate** ein, nachdem der neue Schlüssel erstellt wurde, und drücken Sie die EINGABETASTE, um den Schlüssel umzubenennen.

Es kann einige Stunden dauern, bis diese Änderung vom Computer übernommen wurde. Damit die Änderungen sofort wirksam werden, sollte der Health Agent-Dienst beendet und dann erneut gestartet werden. Führen Sie auf dem lync Server 2010 Computer das folgende Verfahren aus, um den Integritäts-Agent-Dienst neu zu starten:

1.  Klicken Sie nacheinander auf **Start**, **Alle Programme** und **Zubehör**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und klicken Sie dann auf **Als Administrator ausführen**.

2.  Geben Sie im Konsolenfenster den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE:
    
        Net stop HealthService

3.  Es wird eine Meldung mit dem Text "Der System Center-Verwaltungsdienst wird beendet" gefolgt von einer zweiten Meldung angezeigt, in der mitgeteilt wird, dass der Dienst beendet wurde. Nachdem der Dienst gestoppt wurde, können Sie diesen erneut starten, indem Sie den folgenden Befehl eingeben und die EINGABETASTE drücken:
    
        Net start HealthService

</div>

<div>

## <a name="overriding-the-central-discovery-candidate-in-the-lync-server-2010-management-pack"></a>Außer Kraft setzen des zentralen Ermittlungskandidaten im Lync Server 2010 Management Pack

Nachdem Sie einen lync Server 2010 Computer angewiesen haben, auf lync Server 2010 Computern zu berichten, müssen Sie das lync Server 2010 Management Pack auch über diese Änderung informieren. Dafür müssen Sie im Management Pack eine Außerkraftsetzung erstellen. Führen Sie dafür die folgenden Schritte aus:

1.  Klicken Sie in der Operations Manager-Konsole auf **Konfiguration**.

2.  Erweitern Sie in der Registerkarte "Konfiguration" die Option **Management Pack-Objekte**, klicken Sie auf **Objektermittlungen** und anschließend auf **Bereiche**.

3.  Wählen Sie im Dialogfeld **Management Pack-Objekte in Bereiche einteilen** das Element mit dem Ziel-**LS-Ermittlungskandidat** aus, und klicken Sie dann auf **OK**. Beachten Sie, dass ls Discovery Candidate nur angezeigt wird, wenn Sie das lync Server 2010 Management Pack installiert haben.

4.  Klicken Sie mit der rechten Maustaste in der Operations Manager-Konsole auf **LS-Ermittlungskandidat**, zeigen Sie auf **Außerkraftsetzungen**, zeigen Sie auf **Objektermittlung außer Kraft setzen**, und klicken Sie anschließend auf **Für alle Objekte der Klasse: LS-Ermittlungskandidat**.

5.  Aktivieren Sie im Dialogfeld **Außerkraftsetzungseigenschaften** das Kontrollkästchen **Außerkraftsetzung** neben dem Parameter **Central Discovery WatcherNode Fqdn**. Geben Sie den vollqualifizierten Domänennamen des lync Server 2010 Computers in die Felder **Außerkraftsetzungswert** und **effektiver Wert** ein. Aktivieren Sie das Kontrollkästchen **Erzwungen**, und klicken Sie auf **OK**.

Nachdem die Außerkraftsetzung erstellt wurde, müssen Sie den Integritätsdienst auf dem Stammverwaltungsserver neu starten. Führen Sie die folgenden Schritte auf dem Stammverwaltungsserver aus, um den Integritätsdienst neu zu starten:

1.  Klicken Sie nacheinander auf **Start**, **Alle Programme** und **Zubehör**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und klicken Sie dann auf **Als Administrator ausführen**.

2.  Geben Sie im Konsolenfenster den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE:
    
        Net stop HealthService

3.  Es wird eine Meldung mit dem Text "Der System Center-Verwaltungsdienst wird beendet" gefolgt von einer zweiten Meldung angezeigt, in der mitgeteilt wird, dass der Dienst beendet wurde. Nachdem der Dienst gestoppt wurde, können Sie diesen erneut starten, indem Sie den folgenden Befehl eingeben und die EINGABETASTE drücken:
    
        Net start HealthService

</div>

<div>

## <a name="verifying-that-the-new-central-discovery-candidate-was-discovered"></a>So wird sichergestellt, dass der neue zentrale Ermittlungskandidat ermittelt wurde

Der letzte Schritt vor dem Upgrade des zentralen Verwaltungsspeichers besteht darin, sicherzustellen, dass der neue zentrale Ermittlungs Kandidat vom lync Server 2010 Management Pack erkannt wurde. Öffnen Sie dafür die Operations Manager-Konsole, und klicken Sie auf "Überwachung". Erweitern Sie in der Registerkarte "Überwachung" die Option **Microsoft Lync Server 2010 Health**, erweitern Sie dann **Topologieerkennung**, und klicken Sie dann auf **Ansicht Ermittlungsstatus**. Stellen Sie sicher, dass eine Zeile in der Anzeige über einen **Pfad** verfügt, der den vollqualifizierten Domänennamen des zentralen Ermittlungskandidaten auflistet. Es sollte auch sichergestellt werden, dass als Computerstatus **Fehlerfrei** angezeigt wird.

</div>

</div>

<span> </span>

</div>

</div>

</div>

