---
title: Konfigurieren von Verbund Routen und Mediendatenverkehr
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Configure federation routes and media traffic
ms:assetid: ed6cb922-7863-453a-adce-2ce0ba761d74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721925(v=OCS.15)
ms:contentKeyID: 49733860
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6fc7359a21d60c0c77028491af9fccdf21991c58
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136092"
---
# <a name="configure-federation-routes-and-media-traffic"></a>Konfigurieren von Verbund Routen und Mediendatenverkehr

 


Ein Partnerverbund ist eine Vertrauensstellung zwischen zwei oder mehr SIP-Domänen, die Benutzern in unterschiedlichen Organisationen die Kommunikation über Netzwerkgrenzen hinweg ermöglicht. Nachdem Sie zu Ihrem lync Server 2013 Pilot-Pool migriert haben, müssen Sie von der Verbund Route Ihrer Microsoft Office Communications Server 2007 R2-Edgeserver zur Verbund Route ihrer lync Server 2013 Edgeserver wechseln.

Führen Sie die folgenden Verfahren aus, um die partnerverbundroute und die Mediendaten Verkehrsroute von Ihrem Office Communications Server 2007 R2 Edgeserver und Directors zu Ihrem lync Server 2013 Edgeserver für eine Bereitstellung mit einem einzelnen Standort umzuleiten.


> [!IMPORTANT]  
> Zum Ändern der Route für partnerverbundroute und Mediendatenverkehr müssen Sie Wartungs Ausfälle für die lync Server 2013-und Office Communications Server 2007 R2-Edgeserver planen. Der gesamte Umstellungsprozess bedeutet auch, dass der Verbundzugriff für die Dauer der Downtime nicht verfügbar ist. Sie sollten die Downtime für einen Zeitraum einplanen, in dem Sie minimale Benutzeraktivität erwarten. Darüber hinaus sollten Sie die Endbenutzer rechtzeitig informieren. Planen Sie diese Downtime sorgfältig, und stellen Sie innerhalb Ihrer Organisation entsprechende Ziele auf.




> [!IMPORTANT]  
> Wenn Ihr Legacy Office Communications Server 2007 R2 Edgeserver für die Verwendung desselben FQDN für die Zugriffs-Edgedienst, Webkonferenz-Edgedienst und den A/V-Edgedienst konfiguriert ist, werden die Verfahren in diesem Abschnitt zum Übergang der Verbund Einstellung zu einem lync Server 2013 Edgeserver nicht unterstützt. Wenn die Legacy-Edge-Dienste für die Verwendung desselben FQDN konfiguriert sind, müssen Sie zunächst alle Ihre Benutzer von Office Communications Server 2007 R2 zu lync Server 2013 migrieren und dann die Office Communications Server 2007 R2 Edgeserver vor dem Aktivieren der Partnerverbund Funktion außer Betrieb nehmen. die lync Server 2013 Edgeserver. Weitere Informationen finden Sie in den folgenden Themen: 
> <UL>
> <LI>
> <P><A href="move-remaining-users-to-lync-server-2013_1.md">Verbleibenden Benutzer in lync Server 2013 verlagern</A></P>
> <LI>
> <P>"Entfernen von Servern und Serverrollen" unter<A href="https://go.microsoft.com/fwlink/p/?linkid=268790">https://go.microsoft.com/fwlink/p/?LinkId=268790</A></P></LI></UL>




> [!IMPORTANT]  
> Wenn Ihr XMPP-Verbund über eine lync Server 2013 Edgeserver weitergeleitet wird, können Legacy Office Communications Server 2007 R2-Benutzer nicht mit dem XMPP-Verbundpartner kommunizieren, bis alle Benutzer zu lync Server 2013, XMPP-Richtlinien verschoben wurden und Zertifikate wurden konfiguriert, der XMPP-Verbundpartner wurde für lync Server 2013 konfiguriert, und schließlich wurden die DNS-Einträge aktualisiert.



Für eine erfolgreiche Veröffentlichung, Aktivierung oder Deaktivierung einer Topologie beim Hinzufügen oder Entfernen einer Serverrolle müssen Sie als Mitglied der Gruppen "RTCUniversalServerAdmins" und "Domänen-Admins" angemeldet sein. Es ist auch möglich, die geeigneten Benutzerrechte und -berechtigungen für das Hinzufügen von Serverrollen zu delegieren. Ausführliche Informationen finden Sie unter [Delegate Setup Permissions in lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in der Standard Edition-Server-oder Enterprise Edition-Server-Bereitstellungsdokumentation. Für andere Konfigurationsänderungen müssen Sie lediglich Mitglied der Gruppe "RTCUniversalServerAdmins" sein.

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a>So entfernen Sie die Partnerverbundzuordnung der Vorversion von Lync Server 2013-Standorten

1.  Öffnen Sie mithilfe des Topologie-Generators die Pilotpooltopologie.

2.  Navigieren Sie im linken Bereich zum Knoten Standort.

3.  Klicken Sie mit der rechten Maustaste auf den Standort, und klicken Sie auf **Eigenschaften bearbeiten**.

4.  Wählen Sie im linken Bereich die Option **Partnerverbundroute** aus.

5.  Deaktivieren Sie unter Standort Verbund Routen Zuweisung das Kontrollkästchen neben SIP-Partner **Verbund aktivieren** , um die partnerverbundroute über das **BackCompatSite**zu deaktivieren.
    
    ![Dialogfeld "Eigenschaften bearbeiten", Verbund Route](images/JJ721925.2a80c103-c0cc-43ed-ba00-420f9add006a(OCS.15).jpg "Dialogfeld "Eigenschaften bearbeiten", Verbund Route")

6.  Klicken Sie auf **OK**, um die Seite "Eigenschaften bearbeiten" zu schließen.

7.  Wählen Sie im Topologie-Generator**** den obersten Knoten **Lync Server** aus.

8.  Klicken Sie im Menü **Aktionen** auf **Topologie veröffentlichen**, und schließen Sie den Assistenten ab.

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a>So konfigurieren Sie den Edgeserver der Vorversion als Nicht-Partnerverbund-Edgeserver

1.  Klicken Sie im Topologie-Generator im Menü ******Aktionen** auf **Office Communications Server 2007 R2-Topologie zusammenführen**.

2.  Klicken Sie auf **Weiter**, um den Vorgang fortzusetzen.

3.  Wählen Sie auf der Seite **Edgesetup angeben** unter **Interner FQDN des Edgeservers** den vollqualifizierten Domänennamen (FQDN) aus, der aktuell für den Partnerverbund konfiguriert ist, und klicken Sie dann auf **Ändern**.
    
    ![Zusammenführen der OCS 2007 R2-Topologie, angeben des Edge-Setups](images/JJ721925.42c15aaf-c1ac-4fb1-a086-665835c57b23(OCS.15).jpg "Zusammenführen der OCS 2007 R2-Topologie, angeben des Edge-Setups")

4.  Klicken Sie auf **Weiter**, und akzeptieren Sie die Standardeinstellungen, bis Sie zur Seite **Externen Edge angeben** gelangen:
    
    ![Topologie-Generator: Seite "externer Edge" angeben](images/JJ721925.e36f3a1f-3655-456e-9e6d-4814c37da0bf(OCS.15).jpg "Topologie-Generator: Seite "externer Edge" angeben")

5.  Deaktivieren Sie unter **externer Edge angeben**das Kontrollkästchen **diese Edgepool wird für Verbund-und öffentliche Chat Verbindungen verwendet** . Dadurch wird die Verbund Zuordnung mit dem BackCompatSite entfernt.
    

    > [!IMPORTANT]  
    > Dieser Schritt ist wichtig. Sie müssen dieses Kontrollkästchen deaktivieren, um die Partnerverbundzuordnung der Vorversion zu entfernen.



6.  Klicken Sie auf **Weiter**, und akzeptieren Sie die Standardeinstellungen der restlichen Seiten des Assistenten.

7.  Klicken Sie auf der Seite **Zusammenfassung** auf **Weiter**, um mit dem Zusammenführen der Topologien zu beginnen.

8.  Überprüfen Sie in der Spalte **Status** , ob der Wert **Erfolg**lautet, und klicken Sie dann auf **Fertig stellen** , um den Assistenten zu schließen.

9.  Wählen Sie im Menü **Aktionen** die Option **Topologie veröffentlichen** aus, und klicken Sie dann auf **Weiter**.

10. Nach Abschluss des Veröffentlichungs-Assistenten**** klicken Sie auf **Fertig stellen**, um den Assistenten zu schließen.
    
    ![Topologie-Generator mit Website, die nach dem Zusammenführen angezeigt wird](images/JJ721925.92b679ad-332f-49aa-b4e2-19f939b711ca(OCS.15).jpg "Topologie-Generator mit Website, die nach dem Zusammenführen angezeigt wird")
    
    Wie in der vorherigen Abbildung gezeigt, ist der **SIP-Partnerverbund** unter **Zuweisung der Partnerverbundroute des Standorts** auf **Deaktiviert** festgelegt.

## <a name="to-configure-certificates-on-the-lync-server-2013-edge-server"></a>So konfigurieren Sie Zertifikate auf dem Lync Server 2013-Edgeserver

1.  Exportieren Sie das externe Zugriffs Proxy Zertifikat mit dem privaten Schlüssel aus dem Legacy Office Communications Server 2007 R2 Edgeserver.

2.  Importieren Sie im lync Server 2013 Edgeserver das externe Zugriffs Proxy Zertifikat aus dem vorherigen Schritt.

3.  Weisen Sie das externe Zertifikat des Zugriffsproxys der externen lync Server 2013-Schnittstelle des Edgeserver zu.

4.  Das interne Schnittstellen Zertifikat des lync Server 2013 Edgeserver sollte nicht geändert werden.

## <a name="to-change-office-communications-server-2007-r2-federation-route-to-use-lync-server-2013-edge-server"></a>So legen Sie für die Office Communications Server 2007 R2-Partnerverbundroute die Verwendung des Lync Server 2013-Edgeservers fest

1.  Öffnen Sie im Office Communications Server 2007 R2 Standard Edition-Server oder Front-End-Server das Office Communications Server 2007 R2 Verwaltungstool.

2.  Erweitern Sie im linken Bereich den obersten Knoten, und klicken Sie dann mit der rechten Maustaste auf den Knoten **Gesamtstruktur**. Wählen Sie **Eigenschaften** aus, und klicken Sie auf **Globale Eigenschaften**.

3.  Klicken Sie auf die Registerkarte **Partnerverbund**.

4.  Aktivieren Sie das Kontrollkästchen Verbund und Verbindung mit öffentlichen Instant Messaging-Diensten aktivieren.

5.  Geben Sie den FQDN des lync Server 2013 Edgeserver ein, und klicken Sie dann auf **OK**.
    
    ![Globale OCS-Eigenschaften, Registerkarte "Verbund"](images/JJ721925.da633f72-43c6-4dac-8d37-ccd0dcde79c9(OCS.15).jpg "Globale OCS-Eigenschaften, Registerkarte "Verbund"")

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a>So aktivieren Sie den Partnerverbund für den Lync Server 2013-Edgeserver

1.  Navigieren Sie im linken Bereich des Topologie-Generators zum Knoten lync Server 2013- **Edge-Pools** .

2.  Erweitern Sie den Knoten, klicken Sie mit der rechten Maustaste auf den aufgelisteten Edgeserver, und klicken Sie anschließend auf **Eigenschaften bearbeiten**.
    

    > [!NOTE]  
    > Der Partnerverbund kann nur für einen einzelnen Edgepool aktiviert werden. Wählen Sie bei mehreren Edgepools den Edgepool aus, den Sie als Partnerverbund-Edgepool verwenden möchten.



3.  Aktivieren Sie auf der Seite **Allgemein** das Kontrollkästchen **Partnerverbund für diesen Edgepool aktivieren (Port 5061)**.
    
    ![Eigenschaften bearbeiten, allgemein, Edge-Verbund aktivieren](images/JJ721925.2aeb5958-da55-4910-b3d7-2124e144a2f0(OCS.15).jpg "Eigenschaften bearbeiten, allgemein, Edge-Verbund aktivieren")

4.  Klicken Sie auf **OK**, um die Seite "Eigenschaften bearbeiten" zu schließen.

5.  Navigieren Sie anschließend zum Knoten Standort.

6.  Klicken Sie mit der rechten Maustaste auf den Standort, und klicken Sie auf **Eigenschaften bearbeiten**.

7.  Klicken Sie im linken Bereich auf **Partnerverbundroute**.

8.  Wählen Sie unter **Standort Verbund-Routen Zuweisung**die Option SIP-Partner **Verbund aktivieren**aus, und wählen Sie dann in der Liste den aufgelisteten lync Server 2013 Edgeserver aus.

9.  Klicken Sie auf **OK**, um die Seite **Eigenschaften bearbeiten** zu schließen.
    
    ![Eigenschaften bearbeiten, allgemein, zuordnen Edgepool](images/JJ721925.33d43297-10cd-412e-bf4a-a1d9a84b9009(OCS.15).jpg "Eigenschaften bearbeiten, allgemein, zuordnen Edgepool")
    
    Für Bereitstellungen mit mehreren Standorten führen Sie dieses Verfahren an jedem Standort aus.

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a>So konfigurieren Sie den ausgehenden Medienpfad für den Lync Server 2013-Edgeserver

1.  Navigieren Sie im **Topologie-Generator**zum lync Server 2013 Pool unter **Standard Edition-Front-End-Server** oder **Enterprise Edition-Front-End-Pools**.

2.  Klicken Sie mit der rechten Maustaste auf den Pool, und klicken Sie auf **Eigenschaften bearbeiten**.

3.  Aktivieren Sie im Abschnitt **Zuordnungen** das Kontrollkästchen **Edgepool zuordnen (für Medienkomponenten)**.

4.  Wählen Sie im Dropdownfeld die lync Server 2013 Edgeserver aus.
    
    ![Dialogfeld "Eigenschaften bearbeiten", "Edge-Pool zuordnen"](images/JJ721925.0cb76b08-5923-4972-8d7a-a829cb77136b(OCS.15).jpg "Dialogfeld "Eigenschaften bearbeiten", "Edge-Pool zuordnen"")

5.  Klicken Sie auf **OK**, um die Seite **Eigenschaften bearbeiten** zu schließen.

## <a name="to-publish-edge-server-configuration-changes"></a>So veröffentlichen Sie Edgeserver-Konfigurationsänderungen

1.  Wählen Sie im **** Topologie-Generator den obersten Knoten aus, **Lync Server**.

2.  Klicken Sie im Menü **Aktionen** auf **Topologie veröffentlichen**, und schließen Sie den Assistenten ab.

3.  Warten Sie, bis die Active Directory-Replikation für alle Pools in der Bereitstellung ausgeführt worden ist.
    

    > [!NOTE]  
    > Möglicherweise wird die folgende Meldung angezeigt:<BR><STRONG>Warnung: Die Topologie enthält mehrere Partner-Edgeserver. Dies kann während der Migration auf eine höhere Version des Produkts geschehen. In diesem Fall wird nur ein Edgeserver aktiv für den Partnerverbund verwendet. Stellen Sie sicher, dass der externe DNS-SRV-Eintrag auf den richtigen Edgeserver verweist. Wenn Sie mehrere Partnerverbund-Edgeserver bereitstellen möchten, die gleichzeitig aktiv sind (kein Migrationsszenario), stellen Sie sicher, dass alle Verbundpartner Office Communications Server 2007 R2 oder höher verwenden. Stellen Sie außerdem sicher, dass der externe DNS-SRV-Eintrag alle partnerverbundfähigen Edgeserver auflistet.</STRONG><BR>Diese Warnung entspricht der Erwartung und kann problemlos ignoriert werden.



## <a name="to-verify-federation-and-remote-access-for-external-users"></a>So überprüfen Sie den Partnerverbund und den Remotezugriff für externe Benutzer

1.  Öffnen Sie im lync Server 2013 Front-End-Server die lync Server-Verwaltungsshell.

2.  Zum Überprüfen des Status des Partnerverbunds und des Remotezugriffs geben Sie an der Befehlszeile folgenden Befehl ein:
    
        Get-CsAccessEdgeConfiguration

3.  Zum Aktivieren des Partnerverbunds und des Remotezugriffs geben Sie an der Befehlszeile folgenden Befehl ein:
    
        Set-CsAccessEdgeConfiguration
    
    Weitere Informationen zu diesen Cmdlets finden Sie in den folgenden Themen: [Get-csaccessedgeconfiguration nicht angeben](https://technet.microsoft.com/library/gg398574\(v=ocs.15\)) und [Sets-csaccessedgeconfiguration nicht angeben](https://technet.microsoft.com/library/gg413017\(v=ocs.15\)).

4.  Warten Sie, bis die Replikation abgeschlossen ist, bevor Sie die lync Server 2013-Edgeserver online schalten und den Partnerverbund und den externen Zugriff testen.

## <a name="to-configure-lync-server-2013-edge-server"></a>So konfigurieren Sie Lync Server 2013-Edgeserver

1.  Alle lync Server 2013-Edgeserver online schalten.

2.  Aktualisieren Sie die Routingregeln für externe Firewalls oder die Einstellungen für das Hardwaregerät zum Lastenausgleich, um den SIP-Datenverkehr für den externen Zugriff (in der Regel Port 443) und den Verbund (in der Regel Port 5061) an die lync Server 2013 Edgeserver anstelle des Legacy Edgeserver zu senden.
    

    > [!NOTE]  
    > Wenn Sie kein Hardwaregerät zum Lastenausgleich verwenden, müssen Sie den DNS-A-Eintrag für den Partnerverbund aktualisieren, sodass der neue Lync Server-Zugriffs-Edgeserver aufgelöst wird. Um dies mit minimaler Betriebsunterbrechung zu bewerkstelligen, reduzieren Sie den TTL-Wert für den externen vollqualifizierten Domänennamen (FQDN) des Lync Server-Zugriffs-Edgeservers. Dadurch werden, wenn das DNS aktualisiert wird, sodass es auf den neuen Lync Server-Zugriffs-Edgeserver zeigt, auch der Partnerverbund und der Remotezugriff rasch aktualisiert.



3.  Beenden Sie als nächstes die **lync Server Zugriffs Kante** für jeden Edgeserver Computer.

4.  Öffnen Sie auf jedem Computer mit Legacy Edgeserver das Applet **Dienste** über die **Verwaltungs Tools**.

5.  Suchen Sie in der Liste mit den Diensten nach **Office Communications Server-Zugriffsedge**.

6.  Klicken Sie mit der rechten Maustaste auf den Namen des Diensts, und klicken Sie dann auf **Beenden**, um den Dienst zu beenden.

7.  Legen Sie als Starttyp **Deaktiviert** fest.

8.  Klicken Sie auf **OK**, um das Fenster **Eigenschaften** zu schließen.

## <a name="to-test-connectivity-of-external-users-and-external-access"></a>So testen Sie die Anbindung externer Benutzer und den externen Zugriff

  - Benutzer aus mindestens einer Verbunddomäne, einem internen Benutzer auf lync Server 2013 und einem Benutzer in Office Communications Server 2007 R2. Testen von Chatnachrichten, Anwesenheit, Audio/Video (A/V) und Desktopfreigabe.

  - Benutzer aller öffentlichen Sofortnachrichten-Dienstanbieter, die von Ihrer Organisation unterstützt werden (und für die die Bereitstellung abgeschlossen ist), die mit einem Benutzer auf lync Server 2013 und einem Benutzer in Office Communications Server 2007 R2 kommunizieren.

  - Überprüfen Sie, ob anonyme Benutzer in der Lage sind, an Konferenzen teilzunehmen.

  - Ein Benutzer, der auf Office Communications Server 2007 R2 unter Verwendung des Remotebenutzerzugriffs (Anmeldung bei Office Communications Server 2007 R2 von außerhalb des Intranets, aber ohne VPN) mit einem Benutzer in lync Server 2013 und einem Benutzer auf Office Communications Server 2007 R2 gehostet wird. Testen Sie Sofortnachrichten, Anwesenheit, A/V und Desktopfreigabe.

  - Ein Benutzer, der auf lync Server 2013 unter Verwendung des Remotebenutzerzugriffs (Anmeldung bei lync Server 2013 von außerhalb des Intranets, aber ohne VPN) mit einem Benutzer in lync Server 2013 und einem Benutzer auf Office Communications Server 2007 R2 gehostet wird. Testen Sie Sofortnachrichten, Anwesenheit, A/V und Desktopfreigabe.

