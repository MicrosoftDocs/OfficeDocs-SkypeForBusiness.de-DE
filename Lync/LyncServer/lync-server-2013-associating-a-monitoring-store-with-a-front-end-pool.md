---
title: Zuordnen eines Überwachungsspeichers zu einem Front-End-Pool
TOCTitle: Zuordnen eines Überwachungsspeichers zu einem Front-End-Pool
ms:assetid: d3a20d5e-3f24-4cff-bc9b-4f84fea30e6b
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205271(v=OCS.15)
ms:contentKeyID: 49295506
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Zuordnen eines Überwachungsspeichers zu einem Front-End-Pool

 

_**Letztes Änderungsdatum des Themas:** 2013-04-22_

In Microsoft Lync Server 2013 können Überwachungsdaten nur in Front-End-Pools gesammelt werden, denen ein Überwachungsspeicher zugeordnet wurde. Diese Aufgabe wird in der Regel ausgeführt, wenn Sie einen Front-End-Pool im Topologie-Generator definieren. Zum Zuordnen eines Überwachungsspeichers zu einem neuen Front-End-Pool müssen Sie auf der Seite **Funktionen auswählen** des Assistenten zum Definieren eines neuen Front-End-Pools die Option **Überwachung (Aufzeichnung von Kommunikationsdatensätzen und Quality of Experience-Metriken) aktivieren** auswählen. Wenn Sie diese Option auswählen, müssen Sie auch einen SQL-Speicher angeben, um den Assistenten abzuschließen. Dieser Speicher muss jedoch zum Zeitpunkt der Ausführung des Assistenten nicht vorhanden sein. Dies bedeutet, dass Sie zuerst einem Pool einen Überwachungsspeicher zuordnen und diesen Speicher später einrichten und konfigurieren können.

Alternativ können Sie einem vorhandenen Front-End-Pool anhand des folgenden Verfahrens einen neuen oder anderen Überwachungsspeicher zuordnen:

1.  Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft Lync Server 2013** und anschließend auf **Lync Server-Topologie-Generator**.

2.  Wählen Sie im Dialogfeld **Topologie-Generator** die Option **Topologie aus vorhandener Bereitstellung herunterladen** aus, und klicken Sie dann auf **OK**.

3.  Geben Sie im Dialogfeld **Speichern unter** einen Dateinamen für Ihre aktuelle Topologie ein, und klicken Sie dann auf **Speichern**. Die gespeicherte Topologie kann später abgerufen und erneut veröffentlicht werden, falls es Probleme mit der neuen Topologie gibt.

4.  Erweitern Sie im Topologie-Generator die Option **Lync Server 2013**, erweitern Sie den Namen des Standorts, der den Front-End-Pool enthält, und klicken Sie dann auf **Enterprise Edition-Front-End-Pools**.

5.  Klicken Sie mit der rechten Maustaste auf den Namen des Pools, dem der Überwachungsspeicher zugeordnet werden soll, und klicken Sie dann auf **Eigenschaften bearbeiten**.

6.  Wählen Sie im Dialogfeld **Eigenschaften bearbeiten** auf der Registerkarte **Allgemein** die Option **Überwachung (CDR- und QoE-Metriken)** aus, und wählen Sie dann in der Dropdownliste **SQL Server-Speicher für Überwachung** eine vorhandene SQL Server-Datenbank aus. (Oder klicken Sie auf **Neu**, um dem Pool einen neuen Datenbankspeicher zuzuordnen.) Wenn Sie einen neuen Datenbankspeicher verwenden möchten, geben Sie im Dialogfeld **Neuen SQL-Speicher definieren** den vollqualifizierten Domänenname des SQL Server-Computers im Feld **SQL Server-FQDN** ein. Wenn Sie die SQL Server-Standardinstanz für diesen Speicher verwenden möchten, wählen Sie **Standardinstanz** aus. Andernfalls wählen Sie **Benannte Instanz** aus und geben den Namen der Instanz im Feld **Benannte Instanz** ein.
    
    Im Dialogfeld **Eigenschaften bearbeiten** haben Sie auch die Möglichkeit, einen SQL-Spiegel für Ihre Überwachungsdatenbank zu erstellen (mit einem SQL-Spiegel können Sie zwei Kopien Ihrer Überwachungsdatenbank verwalten, wobei eine Kopie auf dem Überwachungsspeichercomputer und die andere Kopie auf dem SQL-Spiegelcomputer verwaltet wird). Zum Aktivieren der Spiegelung wählen Sie **Diese SQL-Instanz befindet sich in einer Spiegelungsbeziehung** aus und geben die Portnummer für den Spiegelserver im Feld **Spiegelportnummer** ein.

7.  Klicken Sie im Dialogfeld **Eigenschaften bearbeiten** auf **OK**.

Nachdem Sie den Überwachungsspeicher einem Front-End-Pool zugeordnet haben, müssen Sie die neue Topologie veröffentlichen, damit die Änderungen wirksam werden. Zum Veröffentlichen der neuen Topologie führen Sie die folgenden Schritte im Topologie-Generator aus:

1.  Klicken Sie auf **Aktion**, zeigen Sie auf **Topologie**, und klicken Sie dann auf **Veröffentlichen**.

2.  Klicken Sie im Assistenten zum Veröffentlichen der Topologie auf der Seite **Topologie veröffentlichen** auf **Weiter**.

3.  Klicken Sie auf der Seite **Assistent für die Veröffentlichung abgeschlossen** auf **Fertig stellen**.

Nachdem die Topologie veröffentlicht wurde, können Sie die Überwachungsdatenbank auf dem Computer installieren, von dem der Überwachungsspeicher gehostet wird. Die Überwachungsdatenbank kann mit der Lync Server-Verwaltungsshell und mit Windows PowerShell installiert werden. Um die Datenbank lokal zu installieren (d. h., auf demselben Computer, auf dem Sie die Lync Server-Verwaltungsshell ausführen), starten Sie die Verwaltungsshell auf dem entsprechenden Computer, geben Sie den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE:

    Install-CsDatabase -LocalDatabases

Wenn Sie den vorherigen Befehl ausführen, liest Install-CsDatabase die aktuelle Lync Server-Topologie, ermittelt die Datenbanken, die auf dem lokalen Computer installiert werden müssen, und installiert und konfiguriert dann automatisch jede dieser Datenbanken.

Wenn Sie die Datenbank auf einem Remotecomputer installieren möchten (d. h., auf einem anderen Computer als dem Computer, auf dem die Verwaltungsshell ausgeführt wird, müssen Sie mindestens zwei Parameter eingeben: den ConfiguredDatabases-Parameter und den SqlServerFqdn-Parameter. Mit diesen Parametern wird das Install-CsDatabase-Cmdlet angewiesen, die Lync Server-Topologie abzurufen und anschließend die erforderlichen Datenbanken auf dem durch den SqlServerFqdn-Parameter angegebenen Computer zu installieren und zu konfigurieren. Der SqlServerFqdn-Parameter muss einen Parameterwert verwenden, der den vollqualifizierten Domänennamen des Computers repräsentiert, auf dem die Datenbank installiert werden sollen.

Beispielsweise wird mit dem folgenden Befehl die Überwachungsdatenbank auf dem Computer atl-sql-001.litwareinc.com installiert:

    Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn atl-sql-001.litwareinc.com

Alternativ können Sie die Überwachungsdatenbank installieren, indem Sie den Lync Server-Bereitstellungs-Assistenten auf dem Computer ausführen, von dem der Überwachungsspeicher gehostet wird. Dazu melden Sie sich am entsprechenden Computer an und führen das folgende Verfahren aus:

1.  Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft Lync Server 2013** und anschließend auf **Lync Server-Bereitstellungs-Assistent**.

2.  Klicken Sie im Bereitstellungs-Assistenten auf **Lync Server-System installieren oder aktualisieren**.

3.  Klicken Sie auf der Seite **Bereitstellen** unter **Schritt  2: Lync Server-Komponenten einrichten oder entfernen** auf **Erneut ausführen**.

4.  Klicken Sie im Assistenten zum Einrichten von Lync Server-Komponenten auf der Seite **Lync Server-Komponenten einrichten** auf **Weiter**.

5.  Geben Sie auf der Seite **Pfad zu MSIs angeben** den Pfad zur Datei Ocscore.msi ein (diese Datei ist auf den Installationsmedien für Lync Server vorhanden), und klicken Sie dann auf **Weiter**.

6.  Klicken Sie auf der Seite **Befehle werden ausgeführt** auf **Fertig stellen**.

Um sicherzustellen, dass alle erforderlichen Lync Server-Dienste gestartet wurden, klicken Sie auf der Seite **Bereitstellen** unter **Schritt 4: Dienste starten** auf **Ausführen**.

