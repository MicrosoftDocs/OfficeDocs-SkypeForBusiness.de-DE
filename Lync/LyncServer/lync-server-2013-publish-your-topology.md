---
title: 'Lync Server 2013: Veröffentlichen der Topologie'
TOCTitle: Veröffentlichen der Topologie
ms:assetid: bfed3829-7a54-4b5c-a7cb-28871acd35e7
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412935(v=OCS.15)
ms:contentKeyID: 49295282
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Veröffentlichen der Topologie in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-08_

Jedes Mal, wenn Sie den Topologie-Generator zum Erstellen einer Topologie verwenden, müssen Sie die Topologie in einer Datenbank im zentralen Verwaltungsspeicher veröffentlichen, sodass die Daten für die Bereitstellung von Lync Server 2013 verwendet werden können. Führen Sie die folgenden Schritte aus, um Ihre Topologie zu veröffentlichen.

## So veröffentlichen Sie die Topologie

1.  Starten des Topologie-Generators: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Topologie-Generator**.

2.  Klicken Sie im Topologie-Generator in der Konsolenstruktur mit der rechten Maustaste auf **Lync 2013**, und klicken Sie dann auf **Topologie veröffentlichen** .

3.  Klicken Sie auf der Seite **Willkommen** des Assistenten auf **Weiter** .

4.  Klicken Sie auf der Seite **Topologie-Generator hat einen zentralen Verwaltungsspeicher gefunden** auf **Weiter** .

5.  Klicken Sie auf der Seite **Weitere Datenbanken erstellen** auf **Weiter** .

6.  Wenn die erfolgreiche Erstellung der Datenbank angezeigt wird, führen Sie folgende Schritte aus:
    
      - Klicken Sie zum Anzeigen des Protokolls auf **Protokoll anzeigen** .
    
      - Klicken Sie auf **Fertig stellen** , um den Assistenten zu schließen.
        

        > [!IMPORTANT]
        > Falls es sich um eine neue Installation eines Edgeservers oder eines Edgepools handelt, müssen Sie die Edgeserver-Konfiguration von einem vorhandenen Front-End-Server, Front-End-Pool oder Standard Edition-Server exportieren. Informationen zum Exportieren der Konfiguration finden Sie unter <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">Exportieren der Lync Server 2013-Topologie und Kopieren auf externe Medien zur Edgeinstallation</A>. Während der Setup- und Bereitstellungsphase der Edgeserver importieren Sie mithilfe des Lync Server-Bereitstellungs-Assistenten die Konfigurationsdatei vom externen Medium oder der Netzwerkfreigabe.<BR>Wenn die Edgeserver betriebsbereit sind und die lokale Konfigurationsverwaltungsspeicher-Datenbank mit der internen Bereitstellung repliziert wird, werden nachfolgende Aktualisierungen an der Lync Server 2013-Konfiguration auf den Edgeservern veröffentlicht und repliziert.


