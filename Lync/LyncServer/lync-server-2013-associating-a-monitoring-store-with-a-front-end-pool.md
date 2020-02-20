---
title: 'Lync Server 2013: Zuordnen eines überwachungsspeichers zu einem Front-End-Pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associating a monitoring store with a Front End pool
ms:assetid: d3a20d5e-3f24-4cff-bc9b-4f84fea30e6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205271(v=OCS.15)
ms:contentKeyID: 48185439
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f889179c5302a0ff8d59b5cf438c7ba0ab3c489f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149174"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="associating-a-monitoring-store-with-a-front-end-pool-in-lync-server-2013"></a>Zuordnen eines überwachungsspeichers zu einem Front-End-Pool in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-04-22_

In Microsoft lync Server 2013 Überwachungsdaten nur in Front-End-Pools gesammelt werden können, die einem Überwachungsspeicher zugeordnet wurden, wird in der Regel eine Aufgabe definiert, die Sie im Topologie-Generator ein Front-End-Pool definieren. Wenn Sie einen Überwachungsspeicher einer neuen Front-End-Pool zuordnen möchten, stellen Sie sicher, dass Sie auf der Seite **Features auswählen** des Assistenten zum Definieren eines neuen Front-End-Pools die Option **Überwachung (Aufzeichnung von Kommunikationsdatensätzen und Protokollierung der Metriken für die Qualität der Erfahrung)** auswählen. Beachten Sie, dass Sie bei Auswahl dieser Option auch einen SQL-Speicher angeben müssen, um den Assistenten abzuschließen. Dieser Speicher muss jedoch nicht zum Zeitpunkt der Ausführung des Assistenten vorhanden sein. Das bedeutet, dass Sie zuerst einen Pool einem Überwachungsspeicher zuordnen können, dann später Setup und diesen Speicher konfigurieren.

Alternativ können Sie einem vorhandenen Front-End-Pool anhand des folgenden Verfahrens einen neuen oder anderen Überwachungsspeicher zuordnen:

1.  Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topologie-Generator**.

2.  Wählen Sie im Dialogfeld **Topologie-Generator** die Option **Topologie aus vorhandener Bereitstellung herunterladen** aus, und klicken Sie dann auf **OK**.

3.  Geben Sie im Dialogfeld **Speichern unter** einen Dateinamen für Ihre aktuelle Topologie ein, und klicken Sie dann auf **Speichern**. Die gespeicherte Topologie kann später abgerufen und erneut veröffentlicht werden, falls es Probleme mit der neuen Topologie gibt.

4.  Erweitern Sie im Topologie-Generator **lync Server 2013**, erweitern Sie den Namen des Standorts, der den Front-End-Pool enthält, und klicken Sie dann auf **Enterprise Edition-Front-End-Pools**erweitern.

5.  Klicken Sie mit der rechten Maustaste auf den Namen des Pools, dem der Überwachungsspeicher zugeordnet werden soll, und klicken Sie dann auf **Eigenschaften bearbeiten**.

6.  Wählen Sie im Dialogfeld **Eigenschaften bearbeiten** auf der Registerkarte **Allgemein** die Option **Überwachung (CDR- und QoE-Metriken)** aus, und wählen Sie dann in der Dropdownliste **SQL Server-Speicher für Überwachung** eine vorhandene SQL Server-Datenbank aus. (Oder klicken Sie auf **Neu**, um dem Pool einen neuen Datenbankspeicher zuzuordnen.) Wenn Sie einen neuen Datenbankspeicher verwenden möchten, geben Sie im Dialogfeld **Neuen SQL-Speicher definieren** den vollqualifizierten Domänenname des SQL Server-Computers im Feld **SQL Server-FQDN** ein. Wenn Sie die SQL Server-Standardinstanz für diesen Speicher verwenden möchten, wählen Sie **Standardinstanz** aus. Andernfalls wählen Sie **Benannte Instanz** aus und geben den Namen der Instanz im Feld **Benannte Instanz** ein.
    
    Im Dialogfeld **Eigenschaften bearbeiten** haben Sie auch die Möglichkeit, einen SQL-Spiegel für Ihre Überwachungsdatenbank zu erstellen (mit einem SQL-Spiegel können Sie zwei Kopien Ihrer Überwachungsdatenbank verwalten, wobei eine Kopie auf dem Überwachungsspeichercomputer und die andere Kopie auf dem SQL-Spiegelcomputer verwaltet wird). Zum Aktivieren der Spiegelung wählen Sie **Diese SQL-Instanz befindet sich in einer Spiegelungsbeziehung** aus und geben die Portnummer für den Spiegelserver im Feld **Spiegelportnummer** ein.

7.  Klicken Sie im Dialogfeld **Eigenschaften bearbeiten** auf **OK**.

Nachdem Sie den Überwachungsspeicher einem Front-End-Pool zugeordnet haben, müssen Sie die neue Topologie veröffentlichen, damit die Änderungen wirksam werden. Zum Veröffentlichen der neuen Topologie führen Sie die folgenden Schritte im Topologie-Generator aus:

1.  Klicken Sie auf **Aktion**, zeigen Sie auf **Topologie**, und klicken Sie dann auf **Veröffentlichen**.

2.  Klicken Sie im Assistenten zum Veröffentlichen der Topologie auf der Seite **Topologie veröffentlichen** auf **Weiter**.

3.  Klicken Sie auf der Seite **Assistent für die Veröffentlichung abgeschlossen** auf **Fertig stellen**.

Nachdem die Topologie veröffentlicht wurde, können Sie die Überwachungsdatenbank auf dem Computer installieren, auf dem der Überwachungsspeicher gehostet wird. Die Überwachungsdatenbank kann mithilfe der lync Server-Verwaltungsshell und Windows PowerShell installiert werden. Um die Datenbank lokal zu installieren (um die Datenbank auf demselben Computer zu installieren, auf dem Sie die lync Server-Verwaltungsshell ausführen), starten Sie die Verwaltungsshell auf dem entsprechenden Computer, geben Sie dann den folgenden Befehl ein, und drücken Sie die EINGABETASTE:

    Install-CsDatabase -LocalDatabases

Wenn Sie den obigen Befehl ausführen, liest install-CsDatabase die aktuelle lync Server-Topologie, ermittelt, welche Datenbanken auf dem lokalen Computer installiert werden müssen, und installiert und konfiguriert dann automatisch jede dieser Datenbanken.

Zum Installieren der Datenbank auf einem Remotecomputer (also einem anderen Computer als dem Computer, auf dem die Verwaltungsshell läuft) müssen Sie mindestens zwei Parameter einschließen: den ConfiguredDatabases-Parameter und den sqlserverfqdn "nicht-Parameter. Mit diesen Parametern wird das Cmdlet Install-CsDatabase dazu aufgefordert, die lync Server Topologie abzurufen und anschließend die erforderlichen Datenbanken auf dem durch den Parameter sqlserverfqdn "nicht angegebenen Computer zu installieren und zu konfigurieren. Der Parameter sqlserverfqdn "nicht muss einen Parameterwert verwenden, der den vollqualifizierten Domänennamen des Computers darstellt, auf dem die Datenbanken installiert werden sollen.

Beispielsweise wird mit dem folgenden Befehl die Überwachungsdatenbank auf dem Computer atl-sql-001.litwareinc.com installiert:

    Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn atl-sql-001.litwareinc.com

Alternativ können Sie die Überwachungsdatenbank installieren, indem Sie den lync Server-Bereitstellungs-Assistenten auf dem Computer ausführen, auf dem der Überwachungsspeicher gehostet wird. Dazu melden Sie sich am entsprechenden Computer an und führen das folgende Verfahren aus:

1.  Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Bereitstellungs-Assistent**.

2.  Klicken Sie im Bereitstellungs-Assistenten auf **Lync Server-System installieren oder aktualisieren**.

3.  Klicken Sie auf der Seite **Bereitstellen** unter **Schritt  2: Lync Server-Komponenten einrichten oder entfernen** auf **Erneut ausführen**.

4.  Klicken Sie im Assistenten zum Einrichten von Lync Server-Komponenten auf der Seite **Lync Server-Komponenten einrichten** auf **Weiter**.

5.  Geben Sie auf der Seite **Pfad zu MSIs angeben** den Pfad zur Datei OCSCore. msi ein (eine Datei, die im lync Server Installationsmedium enthalten ist), und klicken Sie dann auf **weiter**.

6.  Klicken Sie auf der Seite **Befehle ausführen** auf **Fertig stellen**.

Um sicherzustellen, dass alle erforderlichen lync Server Dienste gestartet wurden, klicken Sie unter der Überschrift **Schritt 4: Starten von Diensten** auf der Seite **Bereitstellen** auf **Ausführen** .

</div>

<span> </span>

</div>

</div>

</div>

