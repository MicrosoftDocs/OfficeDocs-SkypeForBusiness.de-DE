---
title: Konfigurieren von Partnerverbundrouten und Mediendatenverkehr
TOCTitle: Konfigurieren von Partnerverbundrouten und Mediendatenverkehr
ms:assetid: 8b2f5f81-a955-4ad1-ad74-397322ff9521
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688121(v=OCS.15)
ms:contentKeyID: 49890828
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von Partnerverbundrouten und Mediendatenverkehr

 

_**Letztes Änderungsdatum des Themas:** 2012-10-15_

Ein Partnerverbund ist eine Vertrauensstellung zwischen zwei oder mehr SIP-Domänen, die Benutzern in unterschiedlichen Organisationen die Kommunikation über Netzwerkgrenzen hinweg ermöglicht. Nach der Migration zum Lync Server 2013-Pilotpool müssen Sie von der Partnerverbundroute Ihrer Lync Server 2010-Edgeserver auf die Partnerverbundroute Ihrer Lync Server 2013-Edgeserver umstellen.

Verwenden Sie die nachfolgenden Verfahren, um die Partnerverbundroute und die Mediendatenverkehrsroute für eine Bereitstellung mit einem einzelnen Standort vom Lync Server 2010-Edgeserver und -Director auf den Lync Server 2013\>-Edgeserver umzustellen.


> [!IMPORTANT]
> Zum Ändern der Partnerverbundroute und der Mediendatenverkehrsroute müssen Sie Wartungsdowntime für die Lync Server 2013- und Lync Server 2010-Edgeserver einplanen. Der gesamte Umstellungsprozess bedeutet auch, dass der Verbundzugriff für die Dauer der Downtime nicht verfügbar ist. Sie sollten die Downtime für einen Zeitraum einplanen, in dem Sie minimale Benutzeraktivität erwarten. Darüber hinaus sollten Sie die Endbenutzer rechtzeitig informieren. Planen Sie diese Downtime sorgfältig, und stellen Sie innerhalb Ihrer Organisation entsprechende Ziele auf.




> [!IMPORTANT]
> Falls für Ihren Lync Server 2010-Edgeserver der Vorversion die Verwendung desselben vollqualifizierten Domänennamens (Fully Qualified Domain Name, FQDN) für den Zugriffs-Edgedienst, den Webkonferenz-Edgedienst und den A/V-Edgedienst konfiguriert ist, werden die in diesem Abschnitt beschriebenen Verfahren nicht unterstützt. Falls für die Edgedienste der Vorversion die Verwendung desselben vollqualifizierten Domänennamens konfiguriert ist, müssen Sie zuerst alle Ihre Benutzer von Lync Server 2010 zu Lync Server 2013 migrieren und anschließend den Lync Server 2010-Edgeserver deaktivieren, bevor Sie den Partnerverbund auf dem Lync Server 2013 -Edgeserver aktivieren.




> [!IMPORTANT]
> Wenn Ihr XMPP-Partnerverbund (Extensible Messaging and Presence Protocol) über einen Lync Server 2013-Edgeserver weitergeleitet wird, können Lync Server 2010-Legacybenutzer erst dann mit dem XMPP-Verbundpartner kommunizieren, nachdem alle Benutzer zu Lync Server 2013 verschoben und die XMPP-Richtlinien und -Zertifikate konfiguriert worden sind, der XMPP-Verbundpartner in Lync Server 2013 konfiguriert worden ist und schließlich die DNS-Einträge aktualisiert worden sind.



## So Entfernen Sie die Partnerverbundzuordnung der Vorversion für Lync Server 2013-Standorte

1.  Öffnen Sie auf dem Lync Server 2013-Front-End-Server die bestehende Topologie im Topologie-Generator.

2.  Navigieren Sie im linken Bereich zum Knoten "Standort", der sich direkt unter dem **Lync Server** befindet.

3.  Klicken Sie mit der rechten Maustaste auf den Standort, und klicken Sie auf **Eigenschaften bearbeiten** .

4.  Wählen Sie im linken Bereich die Option **Partnerverbundroute** aus.

5.  Deaktivieren Sie unter **Zuweisung der Partnerverbundroute des Standorts** das Kontrollkästchen **SIP-Partnerverbund aktivieren** , um die Partnerverbundroute über die alte Lync Server 2010-Umgebung zu deaktivieren.
    
    ![Eigenschaften bearbeiten (Dialogfeld), Partnerverbundroute (Seite)](images/JJ688121.8d755ae0-fc7d-4253-b0db-0cf31b863c55(OCS.15).jpg "Eigenschaften bearbeiten (Dialogfeld), Partnerverbundroute (Seite)")

6.  Klicken Sie auf **OK** , um die Seite **Eigenschaften bearbeiten** zu schließen.

7.  Wählen Sie im **Topologie-Generator** den obersten Knoten aus, **Lync Server** .

8.  Klicken Sie im Menü **Aktion** auf **Topologie veröffentlichen** .

9.  Klicken Sie auf **Weiter**, um den Veröffentlichungsvorgang zu beenden, und klicken Sie dann auf **Fertig stellen**, wenn der Veröffentlichungsvorgang abgeschlossen ist.

## So konfigurieren Sie den Edgeserver der Vorversion als Nicht-Partnerverbund-Edgeserver

1.  Navigieren Sie im linken Bereich zum Knoten **Lync Server 2010** und dann zum Knoten **Edgepools**.

2.  Klicken Sie mit der rechten Maustaste auf den Edgeserver und anschließend auf **Eigenschaften bearbeiten** .

3.  Wählen Sie im linken Bereich **Allgemein** aus.

4.  Deaktivieren Sie das Kontrollkästchen **Partnerverbund für diesen Edgepool aktivieren (Port 5061)** , und wählen Sie **OK** aus, um die Seite zu schließen.
    
    ![Eigenschaften bearbeiten, Allgemein, Aktivierung von Partnerverbund aufheben](images/JJ688121.3be2c8c0-9ed9-4544-bafd-b7694271fafc(OCS.15).jpg "Eigenschaften bearbeiten, Allgemein, Aktivierung von Partnerverbund aufheben")

5.  Wählen Sie im Menü **Aktionen** die Option **Topologie veröffentlichen** aus, und klicken Sie dann auf **Weiter** .

6.  Wenn der **Veröffentlichungs-Assistent** abgeschlossen ist, klicken Sie auf **Fertig stellen**, um den Assistenten zu schließen.

7.  Stellen Sie sicher, dass der Partnerverbund für die Edgeserver der Vorversion deaktiviert ist.
    
    ![Topologie-Generator, Edgepool, Partnerverbund deaktiviert](images/JJ688121.a2948438-d51a-4aeb-9eaa-d899ca950758(OCS.15).jpg "Topologie-Generator, Edgepool, Partnerverbund deaktiviert")

## So konfigurieren Sie Zertifikate auf dem Lync Server 2013-Edgeserver

1.  Exportieren Sie das externe Zugriffsproxyzertifikat mit dem privaten Schlüssel aus dem Lync Server 2010-Edgeserver der Vorversion.

2.  Importieren Sie auf dem Lync Server 2013-Edgeserver das externe Zugriffsproxyzertifikat aus dem vorherigen Schritt.

3.  Weisen Sie das externe Zugriffsproxyzertifikat der externen Lync Server 2013-Schnittstelle des Edgeservers zu.

4.  Das Zertifikat für die interne Schnittstelle des Lync Server 2013-Edgeservers sollte von einer vertrauenswürdigen Zertifizierungsstelle angefordert und zugewiesen werden.

## So legen Sie für die Lync Server 2010-Partnerverbundroute die Verwendung des Lync Server 2013-Edgeservers fest

1.  Navigieren Sie im Topologie-Generator im linken Bereich zum Knoten **Lync Server 2013** und dann zum Knoten **Edgepools**.

2.  Klicken Sie mit der rechten Maustaste auf den Edgeserver und anschließend auf **Eigenschaften bearbeiten** .

3.  Wählen Sie im linken Bereich **Allgemein** aus.

4.  Aktivieren Sie das Kontrollkästchen **Partnerverbund für diesen Edgepool aktivieren (Port 5061)** , und klicken Sie dann auf **OK**, um die Seite zu schließen.
    
    ![Eigenschaften bearbeiten (Dialogfeld), Allgemein (Seite)](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Eigenschaften bearbeiten (Dialogfeld), Allgemein (Seite)")

5.  Wählen Sie im Menü **Aktionen** die Option **Topologie veröffentlichen** aus, und klicken Sie dann auf **Weiter** .

6.  Wenn der **Veröffentlichungs-Assistent** abgeschlossen ist, klicken Sie auf **Fertig stellen**, um den Assistenten zu schließen.

7.  Stellen Sie sicher, dass die Option **Partnerverbund (Port 5061)** auf **Aktiviert** festgelegt wurde.
    
    ![Topologie-Generator, Edgepool, Partnerverbund aktiviert](images/JJ688121.e8ccdada-23f4-47e5-a99d-5bf795fefc48(OCS.15).jpg "Topologie-Generator, Edgepool, Partnerverbund aktiviert")

## So aktualisieren Sie den nächsten Partnerverbundhop für den Lync Server 2013-Edgeserver

1.  Navigieren Sie im Topologie-Generator im linken Bereich zum Knoten **Lync Server 2013** und dann zum Knoten **Edgepools**.

2.  Erweitern Sie den Knoten, klicken Sie mit der rechten Maustaste auf den aufgelisteten Edgeserver, und klicken Sie anschließend auf **Eigenschaften bearbeiten** .

3.  Wählen Sie auf der Seite **Allgemein** unter **Auswahl für nächsten Hop** in der Dropdownliste den Lync Server 2013-Pool aus.
    
    ![Dialogfeld zum Bearbeiten von Eigenschaften, Nächster Hop (Seite)](images/JJ688121.5741b9a8-e729-4457-9f62-38f08a2c5b02(OCS.15).jpg "Dialogfeld zum Bearbeiten von Eigenschaften, Nächster Hop (Seite)")

4.  Klicken Sie auf **OK** , um die Seite **Eigenschaften bearbeiten** zu schließen.

5.  Wählen Sie im **Topologie-Generator** den obersten Knoten aus, **Lync Server** .

6.  Klicken Sie im Menü **Aktionen** auf **Topologie veröffentlichen** , und schließen Sie den Assistenten ab.

## So konfigurieren Sie den ausgehenden Medienpfad für den Lync Server 2013-Edgeserver

1.  Navigieren Sie im Topologie-Generator im linken Bereich zum Knoten **Lync Server 2013** und dann zum Pool unter **Standard Edition-Front-End-Server** oder **Enterprise Edition-Front-End-Pools** .

2.  Klicken Sie mit der rechten Maustaste auf den Pool, und klicken Sie auf **Eigenschaften bearbeiten** .

3.  Aktivieren Sie im Abschnitt **Zuordnungen** das Kontrollkästchen **Edgepool zuordnen (für Medienkomponenten)** .
    
    ![Eigenschaften bearbeiten, Allgemein, Edgepool zuordnen](images/JJ688121.fd9b18ca-fda2-4764-9bf0-726bf39f6a12(OCS.15).jpg "Eigenschaften bearbeiten, Allgemein, Edgepool zuordnen")

4.  Wählen Sie in der Dropdownliste den Lync Server 2013-Edgeserver aus.

5.  Klicken Sie auf **OK** , um die Seite **Eigenschaften bearbeiten** zu schließen.

## So aktivieren Sie den Partnerverbund für den Lync Server 2013-Edgeserver

1.  Navigieren Sie im Topologie-Generator im linken Bereich zum Knoten **Lync Server 2013** und dann zum Knoten **Edgepools**.

2.  Erweitern Sie den Knoten, klicken Sie mit der rechten Maustaste auf den aufgelisteten Edgeserver, und klicken Sie anschließend auf **Eigenschaften bearbeiten** .
    

    > [!NOTE]
    > Der Partnerverbund kann nur für einen einzelnen Edgepool aktiviert werden. Wählen Sie bei mehreren Edgepools den Edgepool aus, den Sie als Partnerverbund- Edgepool verwenden möchten.



3.  Stellen Sie auf der Seite **Allgemein** sicher, dass die Einstellung **Partnerverbund für diesen Edgepool aktivieren (Port 5061)** aktiviert wurde.
    
    ![Eigenschaften bearbeiten (Dialogfeld), Allgemein (Seite)](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Eigenschaften bearbeiten (Dialogfeld), Allgemein (Seite)")

4.  Klicken Sie auf **OK** , um die Seite **Eigenschaften bearbeiten** zu schließen.

5.  Navigieren Sie anschließend zum Knoten **Standort** .

6.  Klicken Sie mit der rechten Maustaste auf den Standort, und klicken Sie auf **Eigenschaften bearbeiten** .

7.  Klicken Sie im linken Bereich auf **Partnerverbundroute** .

8.  Wählen Sie unter **Zuweisung der Partnerverbundroute des Standorts** die Option **SIP-Partnerverbund aktivieren** aus, und wählen Sie dann in der Liste den aufgeführten Lync Server 2013- Edgeserver aus.
    
    ![Eigenschaften bearbeiten, Partnerverbundroute (Seite)](images/JJ688121.c50c13b8-0859-4e3e-8793-45c431a5b4b5(OCS.15).jpg "Eigenschaften bearbeiten, Partnerverbundroute (Seite)")

9.  Klicken Sie auf **OK** , um die Seite **Eigenschaften bearbeiten** zu schließen.
    
    Für Bereitstellungen mit mehreren Standorten führen Sie dieses Verfahren an jedem Standort aus.

## So veröffentlichen Sie Edgeserver-Konfigurationsänderungen

1.  Wählen Sie im **Topologie-Generator** den obersten Knoten aus, **Lync Server** .

2.  Klicken Sie im Menü **Aktionen** auf **Topologie veröffentlichen** , und schließen Sie den Assistenten ab.

3.  Warten Sie, bis die Active Directory-Replikation für alle Pools in der Bereitstellung ausgeführt worden ist.
    

    > [!NOTE]
    > Möglicherweise wird die folgende Meldung angezeigt:<BR><STRONG>Warnung: Die Topologie enthält mehrere Partner-Edgeserver. Dies kann während der Migration zu einer höheren Version des Produkts geschehen. In diesem Fall wird nur ein Edgeserver aktiv für den Partnerverbund verwendet. Stellen Sie sicher, dass der externe DNS-SRV-Eintrag auf den richtigen Edgeserver verweist. Wenn Sie mehrere Partnerverbund-Edgeserver bereitstellen möchten, die gleichzeitig aktiv sind (kein Migrationsszenario), stellen Sie sicher, dass alle Verbundpartner Lync Server verwenden. Stellen Sie außerdem sicher, dass der externe DNS-SRV-Eintrag alle partnerverbundfähigen Edgeserver auflistet.</STRONG><BR>Diese Warnung entspricht der Erwartung und kann problemlos ignoriert werden.



## So konfigurieren Sie den Lync Server 2013-Edgeserver

1.  Schalten Sie alle Lync Server 2013-Edgeserver online.

2.  Aktualisieren Sie die externen Firewall-Routingregeln oder die Einstellungen für das Hardwaregerät zum Lastenausgleich, sodass SIP-Datenverkehr für den externen Zugriff (meist Port 443) und den Partnerverbund (meist Port 5061) nicht an den Edgeserver der Vorversion, sondern an den Lync Server 2013- Edgeserver gesendet wird.
    

    > [!NOTE]
    > Wenn Sie kein Hardwaregerät zum Lastenausgleich zur Verfügung haben, müssen Sie den DNS-A-Eintrag für den Partnerverbund aktualisieren, um das Problem für den neuen Lync Server-Zugriffs-Edgeserver zu lösen. Damit es mit geringstmöglicher Störung abgeschlossen werden kann, sollte Sie den TLL-Wert für den externen FQDN des Lync Server-Zugriffsedge reduzieren, sodass der Partnerverbund und der Remotezugriff schnell aktualisiert werden können, wenn die DNS aktualisiert wird, damit auf den neuen Lync Server-Zugriffsedge verwiesen werden kann.



3.  Beenden Sie anschließend den **Lync Server-Zugriffsedge** auf jedem Computer mit Edgeserver.

4.  Öffnen Sie auf jedem Edgeserver-Computer der Vorversion das Applet **Dienste** in **Verwaltung** .

5.  Suchen Sie in der Liste mit den Diensten nach **Lync Server-Zugriffsedge** .

6.  Klicken Sie mit der rechten Maustaste auf den Namen des Diensts, und klicken Sie dann auf **Beenden** , um den Dienst zu beenden.

7.  Legen Sie als Starttyp **Deaktiviert** fest.

8.  Klicken Sie auf **OK** , um das Fenster **Eigenschaften** zu schließen.

