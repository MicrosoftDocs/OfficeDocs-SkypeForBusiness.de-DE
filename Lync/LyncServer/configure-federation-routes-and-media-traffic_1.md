---
title: Konfigurieren von Partnerverbundrouten und Mediendatenverkehr
TOCTitle: Konfigurieren von Partnerverbundrouten und Mediendatenverkehr
ms:assetid: ed6cb922-7863-453a-adce-2ce0ba761d74
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ721925(v=OCS.15)
ms:contentKeyID: 49891002
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von Partnerverbundrouten und Mediendatenverkehr

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Ein Partnerverbund ist eine Vertrauensstellung zwischen zwei oder mehr SIP-Domänen, die Benutzern in unterschiedlichen Organisationen die Kommunikation über Netzwerkgrenzen hinweg ermöglicht. Nach der Migration zum Lync Server 2013-Pilotpool müssen Sie von der Partnerverbundroute Ihrer Microsoft Office Communications Server 2007 R2-Edgeserver auf die Partnerverbundroute Ihrer Lync Server 2013-Edgeserver umstellen.

Verwenden Sie die nachfolgenden Verfahren, um die Partnerverbundroute und die Mediendatenverkehrsroute für eine Bereitstellung mit einem einzelnen Standort vom Office Communications Server 2007 R2-Edgeserver und -Director auf den Lync Server 2013-Edgeserver umzustellen.


> [!IMPORTANT]
> Zum Ändern der Partnerverbundroute und der Mediendatenverkehrsroute müssen Sie Wartungsdowntime für die Lync Server 2013- und Office Communications Server 2007 R2-Edgeserver einplanen. Der gesamte Umstellungsprozess bedeutet auch, dass der Verbundzugriff für die Dauer der Downtime nicht verfügbar ist. Sie sollten die Downtime für einen Zeitraum einplanen, in dem Sie minimale Benutzeraktivität erwarten. Darüber hinaus sollten Sie die Endbenutzer rechtzeitig informieren. Planen Sie diese Downtime sorgfältig, und stellen Sie innerhalb Ihrer Organisation entsprechende Ziele auf.




> [!IMPORTANT]
> Falls für Ihren Office Communications Server 2007 R2-Edgeserver der Vorversion die Verwendung desselben vollqualifizierten Domänennamens (Fully Qualified Domain Name, FQDN) für den Zugriffs-Edgedienst, den Webkonferenz-Edgedienst und den A/V-Edgedienst konfiguriert ist, werden die in diesem Abschnitt beschriebenen Verfahren für die Umstellung der Partnerverbundeinstellung auf einen Lync Server 2013-Edgeserver nicht unterstützt. Falls für die Edgedienste der Vorversion die Verwendung desselben vollqualifizierten Domänennamens konfiguriert ist, müssen Sie zuerst alle Ihre Benutzer von Office Communications Server 2007 R2 zu Lync Server 2013 migrieren und anschließend den Office Communications Server 2007 R2-Edgeserver deaktivieren, bevor Sie den Partnerverbund auf dem Lync Server 2013-Edgeserver aktivieren. Ausführliche Informationen finden Sie in den folgenden Themen: 
> <UL>
> <LI>
> <P><A href="move-remaining-users-to-lync-server-2013_1.md">Verschieben der verbleibenden Benutzer zu Lync Server 2013</A></P>
> <LI>
> <P>"Remove Servers and Server Roles" unter <A href="http://go.microsoft.com/fwlink/p/?linkid=268790">http://go.microsoft.com/fwlink/p/?LinkId=268790</A></P></LI></UL>




> [!IMPORTANT]
> Wenn Ihr XMPP-Partnerverbund (Extensible Messaging and Presence Protocol) über einen Lync Server 2013-Edgeserver weitergeleitet wird, können Office Communications Server 2007 R2-Legacybenutzer erst dann mit dem XMPP-Verbundpartner kommunizieren, nachdem alle Benutzer zu Lync Server 2013 verschoben und die XMPP-Richtlinien und -Zertifikate konfiguriert worden sind, der XMPP-Verbundpartner in Lync Server 2013 konfiguriert worden ist und schließlich die DNS-Einträge aktualisiert worden sind.



Für eine erfolgreiche Veröffentlichung, Aktivierung oder Deaktivierung einer Topologie beim Hinzufügen oder Entfernen einer Serverrolle müssen Sie als Mitglied der Gruppen "RTCUniversalServerAdmins" und "Domänen-Admins" angemeldet sein. Es ist auch möglich, die geeigneten Benutzerrechte und -berechtigungen für das Hinzufügen von Serverrollen zu delegieren. Ausführliche Informationen finden Sie unter [Delegieren von Setupberechtigungen in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in der Bereitstellungsdokumentation für Standard Edition-Server oder Enterprise Edition-Server. Für andere Konfigurationsänderungen müssen Sie lediglich Mitglied der Gruppe "RTCUniversalServerAdmins" sein.

## So entfernen Sie die Partnerverbundzuordnung der Vorversion von Lync Server 2013-Standorten

1.  Öffnen Sie mithilfe des Topologie-Generators die Pilotpooltopologie.

2.  Navigieren Sie im linken Bereich zum Knoten **Standort** .

3.  Klicken Sie mit der rechten Maustaste auf den Standort, und klicken Sie auf **Eigenschaften bearbeiten** .

4.  Wählen Sie im linken Bereich die Option **Partnerverbundroute** aus.

5.  Deaktivieren Sie unter **Zuweisung der Partnerverbundroute des Standorts** das Kontrollkästchen neben **SIP-Partnerverbund aktivieren** , um die Partnerverbundroute über **BackCompatSite** zu deaktivieren.
    
    ![Dialogfeld zum Bearbeiten von Eigenschaften, Partnerverbundroute](images/JJ721925.2a80c103-c0cc-43ed-ba00-420f9add006a(OCS.15).jpg "Dialogfeld zum Bearbeiten von Eigenschaften, Partnerverbundroute")

6.  Klicken Sie auf **OK** , um die Seite **Eigenschaften bearbeiten** zu schließen.

7.  Wählen Sie im **Topologie-Generator** den obersten Knoten aus, **Lync Server** .

8.  Klicken Sie im Menü **Aktionen** auf **Topologie veröffentlichen** , und schließen Sie den Assistenten ab.

## So konfigurieren Sie den Edgeserver der Vorversion als Nicht-Partnerverbund-Edgeserver

1.  Klicken Sie im Topologie-Generator im Menü **Aktionen** auf **Office Communications Server 2007 R2-Topologie zusammenführen** .

2.  Klicken Sie auf **Weiter** , um den Vorgang fortzusetzen.

3.  Wählen Sie auf der Seite **Edgesetup angeben** unter **Interner FQDN des Edgeservers** den vollqualifizierten Domänennamen (FQDN) aus, der aktuell für den Partnerverbund konfiguriert ist, und klicken Sie dann auf **Ändern** .
    
    ![OCS 2007 R2-Topologie zusammenführen, Edgesetup festlegen](images/JJ721925.42c15aaf-c1ac-4fb1-a086-665835c57b23(OCS.15).jpg "OCS 2007 R2-Topologie zusammenführen, Edgesetup festlegen")

4.  Klicken Sie auf **Weiter** , und akzeptieren Sie die Standardeinstellungen, bis Sie zur Seite **Externen Edge angeben** gelangen:
    
    ![Topologie-Generator: Externen Edge angeben (Seite)](images/JJ205243.32e97ce5-92f0-477e-8125-5d2ece237b13(OCS.15).jpg "Topologie-Generator: Externen Edge angeben (Seite)")

5.  Deaktivieren Sie auf der Seite **Externen Edge angeben** das Kontrollkästchen **Dieser Edgepool wird für den Partnerverbund und die Verbindung mit öffentlichen Sofortnachrichtendiensten verwendet** . Dadurch wird die Partnerverbundzuordnung mit **BackCompatSite** entfernt.
    

    > [!IMPORTANT]
    > Dieser Schritt ist wichtig. Sie müssen dieses Kontrollkästchen deaktivieren, um die Partnerverbundzuordnung der Vorversion zu entfernen.



6.  Klicken Sie auf **Weiter** , und akzeptieren Sie die Standardeinstellungen der restlichen Seiten des Assistenten.

7.  Klicken Sie auf der Seite **Zusammenfassung** auf **Weiter** , um mit dem Zusammenführen der Topologien zu beginnen.

8.  Überprüfen Sie in der Spalte **Status** , ob der Wert **Erfolg** lautet, und klicken Sie dann auf **Fertig stellen** , um den Assistenten zu schließen.

9.  Wählen Sie im Menü **Aktionen** die Option **Topologie veröffentlichen** aus, und klicken Sie dann auf **Weiter** .

10. Wenn der **Veröffentlichungs-Assistent** abgeschlossen ist, klicken Sie auf **Fertig stellen**, um den Assistenten zu schließen.
    
    ![Topologie-Generator mit Standort nach Zusammenführung](images/JJ721925.92b679ad-332f-49aa-b4e2-19f939b711ca(OCS.15).jpg "Topologie-Generator mit Standort nach Zusammenführung")
    
    Wie in der vorherigen Abbildung gezeigt, ist der **SIP-Partnerverbund** unter **Zuweisung der Partnerverbundroute des Standorts** auf **Deaktiviert** festgelegt.

## So konfigurieren Sie Zertifikate auf dem Lync Server 2013-Edgeserver

1.  Exportieren Sie das externe Zugriffsproxyzertifikat mit dem privaten Schlüssel aus dem Office Communications Server 2007 R2-Edgeserver der Vorversion.

2.  Importieren Sie auf dem Lync Server 2013-Edgeserver das externe Zugriffsproxyzertifikat aus dem vorherigen Schritt.

3.  Weisen Sie das externe Zugriffsproxyzertifikat der externen Lync Server 2013-Schnittstelle des Edgeservers zu.

4.  Das interne Schnittstellenzertifikat des Lync Server 2013-Edgeservers sollte nicht geändert werden.

## So legen Sie für die Office Communications Server 2007 R2-Partnerverbundroute die Verwendung des Lync Server 2013-Edgeservers fest

1.  Öffnen Sie auf dem Office Communications Server 2007 R2- Standard Edition-Server oder - Front-End-Server die Office Communications Server 2007 R2-Verwaltungstools.

2.  Erweitern Sie im linken Bereich den obersten Knoten, und klicken Sie dann mit der rechten Maustaste auf den Knoten **Gesamtstruktur** . Wählen Sie **Eigenschaften** aus, und klicken Sie auf **Globale Eigenschaften** .

3.  Klicken Sie auf die Registerkarte **Partnerverbund** .

4.  Aktivieren Sie das Kontrollkästchen **Verbund und Verbindung mit öffentlichen Instant Messaging-Diensten aktivieren** .

5.  Geben Sie den vollqualifizierten Domänennamen (FQDN) für den Lync Server 2013- Edgeserver ein, und klicken Sie dann auf **OK** .
    
    ![Globale OCS-Eigenschaften, Partnerverbund (Registerkarte)](images/JJ721925.da633f72-43c6-4dac-8d37-ccd0dcde79c9(OCS.15).jpg "Globale OCS-Eigenschaften, Partnerverbund (Registerkarte)")

## So aktivieren Sie den Partnerverbund für den Lync Server 2013-Edgeserver

1.  Navigieren Sie im Topologie-Generator im linken Bereich zum Knoten Lync Server 2013- **Edgepools** .

2.  Erweitern Sie den Knoten, klicken Sie mit der rechten Maustaste auf den aufgelisteten Edgeserver, und klicken Sie anschließend auf **Eigenschaften bearbeiten** .
    

    > [!NOTE]
    > Der Partnerverbund kann nur für einen einzelnen Edgepool aktiviert werden. Wählen Sie bei mehreren Edgepools den Edgepool aus, den Sie als Partnerverbund- Edgepool verwenden möchten.



3.  Aktivieren Sie auf der Seite **Allgemein** das Kontrollkästchen **Partnerverbund für diesen Edgepool aktivieren (Port 5061)** .
    
    ![Eigenschaften bearbeiten, Allgemein, Edgepartnerverbund aktivieren](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Eigenschaften bearbeiten, Allgemein, Edgepartnerverbund aktivieren")

4.  Klicken Sie auf **OK** , um die Seite **Eigenschaften bearbeiten** zu schließen.

5.  Navigieren Sie anschließend zum Knoten **Standort** .

6.  Klicken Sie mit der rechten Maustaste auf den Standort, und klicken Sie auf **Eigenschaften bearbeiten** .

7.  Klicken Sie im linken Bereich auf **Partnerverbundroute** .

8.  Wählen Sie unter **Zuweisung der Partnerverbundroute des Standorts** die Option **SIP-Partnerverbund aktivieren** aus, und wählen Sie dann in der Liste den aufgeführten Lync Server 2013- Edgeserver aus.

9.  Klicken Sie auf **OK** , um die Seite **Eigenschaften bearbeiten** zu schließen.
    
    ![Eigenschaften bearbeiten, Allgemein, Edgepool zuordnen](images/JJ721925.33d43297-10cd-412e-bf4a-a1d9a84b9009(OCS.15).jpg "Eigenschaften bearbeiten, Allgemein, Edgepool zuordnen")
    
    Für Bereitstellungen mit mehreren Standorten führen Sie dieses Verfahren an jedem Standort aus.

## So konfigurieren Sie den ausgehenden Medienpfad für den Lync Server 2013-Edgeserver

1.  Navigieren Sie im Topologie-Generator zum Lync Server 2013-Pool unter **Standard Edition-Front-End-Server** oder **Enterprise Edition-Front-End-Pools** .

2.  Klicken Sie mit der rechten Maustaste auf den Pool, und klicken Sie auf **Eigenschaften bearbeiten** .

3.  Aktivieren Sie im Abschnitt **Zuordnungen** das Kontrollkästchen **Edgepool zuordnen (für Medienkomponenten)** .

4.  Wählen Sie in der Dropdownliste den Lync Server 2013-Edgeserver aus.
    
    ![Dialogfeld zum Bearbeiten von Eigenschaften, Edgepool zuordnen](images/JJ721925.0cb76b08-5923-4972-8d7a-a829cb77136b(OCS.15).jpg "Dialogfeld zum Bearbeiten von Eigenschaften, Edgepool zuordnen")

5.  Klicken Sie auf **OK** , um die Seite **Eigenschaften bearbeiten** zu schließen.

## So veröffentlichen Sie Edgeserver-Konfigurationsänderungen

1.  Wählen Sie im **Topologie-Generator** den obersten Knoten aus, **Lync Server** .

2.  Klicken Sie im Menü **Aktionen** auf **Topologie veröffentlichen** , und schließen Sie den Assistenten ab.

3.  Warten Sie, bis die Active Directory-Replikation für alle Pools in der Bereitstellung ausgeführt worden ist.
    

    > [!NOTE]
    > Möglicherweise wird die folgende Meldung angezeigt:<BR><STRONG>Warnung: Die Topologie enthält mehrere Partner-Edgeserver. Dies kann während der Migration auf eine höhere Version des Produkts geschehen. In diesem Fall wird nur ein Edgeserver aktiv für den Partnerverbund verwendet. Stellen Sie sicher, dass der externe DNS-SRV-Eintrag auf den richtigen Edgeserver verweist. Wenn Sie mehrere Partnerverbund-Edgeserver bereitstellen möchten, die gleichzeitig aktiv sind (kein Migrationsszenario), stellen Sie sicher, dass alle Verbundpartner Office Communications Server&nbsp;2007&nbsp;R2 oder höher verwenden. Stellen Sie außerdem sicher, dass der externe DNS-SRV-Eintrag alle partnerverbundfähigen Edgeserver auflistet.</STRONG><BR>Diese Warnung entspricht der Erwartung und kann problemlos ignoriert werden.



## So überprüfen Sie den Partnerverbund und den Remotezugriff für externe Benutzer

1.  Öffnen Sie auf dem Lync Server 2013-Front-End-Server die Lync Server-Verwaltungsshell.

2.  Zum Überprüfen des Status des Partnerverbunds und des Remotezugriffs geben Sie an der Befehlszeile folgenden Befehl ein:
    
        Get-CsAccessEdgeConfiguration

3.  Zum Aktivieren des Partnerverbunds und des Remotezugriffs geben Sie an der Befehlszeile folgenden Befehl ein:
    
        Set-CsAccessEdgeConfiguration
    
    Weitere Informationen zu diesen Cmdlets finden Sie in folgenden Themen: [Get-CsAccessEdgeConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsAccessEdgeConfiguration) und [Set-CsAccessEdgeConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsAccessEdgeConfiguration).

4.  Warten Sie, bis die Replikation abgeschlossen ist, bevor Sie die Lync Server 2013-Edgeserver online schalten und den Partnerverbund und den externen Zugriff testen.

## So konfigurieren Sie Lync Server 2013-Edgeserver

1.  Schalten Sie alle Lync Server 2013-Edgeserver online.

2.  Aktualisieren Sie die externen Firewall-Routingregeln oder die Einstellungen für das Hardwaregerät zum Lastenausgleich, sodass SIP-Datenverkehr für den externen Zugriff (meist Port 443) und den Partnerverbund (meist Port 5061) nicht an den Edgeserver der Vorversion, sondern an den Lync Server 2013- Edgeserver gesendet wird.
    

    > [!NOTE]
    > Wenn Sie kein Hardwaregerät zum Lastenausgleich verwenden, müssen Sie den DNS-A-Eintrag für den Partnerverbund aktualisieren, sodass der neue Lync Server-Zugriffs-Edgeserver aufgelöst wird. Um dies mit minimaler Betriebsunterbrechung zu bewerkstelligen, reduzieren Sie den TTL-Wert für den externen vollqualifizierten Domänennamen (FQDN) des Lync Server-Zugriffs-Edgeservers. Dadurch werden, wenn das DNS aktualisiert wird, sodass es auf den neuen Lync Server-Zugriffs-Edgeserver zeigt, auch der Partnerverbund und der Remotezugriff rasch aktualisiert.



3.  Beenden Sie anschließend den **Lync Server-Zugriffsedge** auf jedem Edgeserver-Computer.

4.  Öffnen Sie auf jedem Edgeserver-Computer der Vorversion das Applet **Dienste** in **Verwaltung** .

5.  Suchen Sie in der Liste mit den Diensten nach **Office Communications Server-Zugriffsedge** .

6.  Klicken Sie mit der rechten Maustaste auf den Namen des Diensts, und klicken Sie dann auf **Beenden** , um den Dienst zu beenden.

7.  Legen Sie als Starttyp **Deaktiviert** fest.

8.  Klicken Sie auf **OK** , um das Fenster **Eigenschaften** zu schließen.

## So testen Sie die Anbindung externer Benutzer und den externen Zugriff

  - Benutzer aus mindestens einer Partnerdomäne, ein interner Benutzer von Lync Server 2013 sowie ein Benutzer von Office Communications Server 2007 R2. Testen Sie Sofortnachrichten, Anwesenheit. Audio/Video (A/V) und Desktopfreigabe.

  - Benutzer aller öffentlichen Sofortnachrichten-Dienstanbieter, die von Ihrer Organisation unterstützt werden (und für die die Bereitstellung abgeschlossen ist), die mit einem Benutzer von Lync Server 2013 und einem Benutzer von Office Communications Server 2007 R2 kommunizieren.

  - Überprüfen Sie, ob anonyme Benutzer in der Lage sind, an Konferenzen teilzunehmen.

  - Ein in Office Communications Server 2007 R2 verwalteter Benutzer unter Verwendung des Remotebenutzerzugriffs (Anmeldung an Office Communications Server 2007 R2 von außerhalb des Intranets, doch ohne VPN) mit einem Benutzer von Lync Server 2013 und einem Benutzer von Office Communications Server 2007 R2. Testen Sie Sofortnachrichten, Anwesenheit, A/V und Desktopfreigabe.

  - Ein in Lync Server 2013 verwalteter Benutzer unter Verwendung des Remotebenutzerzugriffs (Anmeldung an Lync Server 2013 von außerhalb des Intranets, doch ohne VPN) mit einem Benutzer von Lync Server 2013 und einem Benutzer von Office Communications Server 2007 R2. Testen Sie Sofortnachrichten, Anwesenheit, A/V und Desktopfreigabe.

