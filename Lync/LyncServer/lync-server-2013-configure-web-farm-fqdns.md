---
title: 'Lync Server 2013: Konfigurieren von Webfarm-FQDNs'
TOCTitle: Konfigurieren von Webfarm-FQDNs
ms:assetid: cb25dbbd-dcea-4997-8e14-e5007dd7d3ca
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg429722(v=OCS.15)
ms:contentKeyID: 49295415
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von Webfarm-FQDNs für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-03-29_

Beim Definieren der Konfiguration des Standard Edition-Servers, des Front-End-Pools, des Directors oder des Directorpools in Topologie-Generator konfigurieren Sie einen externen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN). Bei der Anmeldung eines auf dem Standard Edition-Server oder im Front-End-Pool verwalteten Clients werden die konfigurierten Webdienste-FQDNs über die In-Band-Bereitstellung gesendet. Falls Sie die externe Webdienste-URL hinzufügen oder ändern müssen, verwenden Sie Topologie-Generator zum Konfigurieren oder Umkonfigurieren der Webdienstekonfiguration mithilfe des in diesem Thema beschriebenen Verfahrens.

## So konfigurieren Sie einen externen Pool-FQDN für Webdienste

1.  Starten des Topologie-Generators: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Topologie-Generator**.

2.  Klicken Sie im Topologie-Generator in der Konsolenstruktur unter **Standard Edition-Front-Ends** , **Enterprise Edition-Front-Ends** und **Directors** mit der rechten Maustaste auf den Namen des Pools, den Sie bearbeiten möchten, und klicken Sie anschließend auf **Eigenschaften bearbeiten** .

3.  Fügen Sie im Abschnitt **Webdienste** unter **Externer FQDN für Webdienste** den FQDN hinzu, oder bearbeiten Sie diesen.

4.  Überprüfen Sie die **Überwachungsports** , und passen Sie sie für HTTP und HTTPS an. Dies sind die Standardwerte:
    
      - **Überwachungsports:** HTTP 8080, HTTPS 4443
    
      - **Veröffentlichte Ports:** HTTP 80, HTTPS 443
    
    Dabei bezeichnen die **Überwachungsports** die Ports, über die die externen Webdienste vom Reverseproxy Anforderungen erhalten. **Veröffentlichte Ports** sind jene Ports, die vom Reverseproxy extern veröffentlicht werden und während der In-Band-Bereitstellung an die Clients übertragen werden.

5.  Wenn Sie alle Eingaben und Änderungen vorgenommen haben, klicken Sie auf **OK** , um den Vorgang fortzusetzen.

6.  Klicken Sie mit der rechten Maustaste auf **Lync Server 2013**, und klicken Sie dann auf **Veröffentlichen** .
    

    > [!IMPORTANT]
    > Nachdem die Veröffentlichung erfolgreich abgeschlossen wurde, wird möglicherweise ein Link angezeigt, mit dem Sie darüber informiert werden, dass zusätzliche Schritte ausgeführt werden müssen. Wenn Sie auf diesen Link klicken, wird eine Liste mit Servern geöffnet, die von den im Topologie-Generator vorgenommenen Änderungen betroffen sind. In diesem Fall müssen Sie den Lync Server-Bereitstellungs-Assistenten auf jedem aufgeführten Server erneut ausführen, um die Konfiguration für hinzugefügte, entfernte oder geänderte Komponenten zu aktualisieren.



7.  Wiederholen Sie diese Schritte für jeden Standard Edition-Server, Front-End-Pool, Director oder Directorpool in der Organisation.

