---
title: Konfigurieren von Partnerverbundrouten und Mediendatenverkehr
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
ms.openlocfilehash: 7af8228a7537f1bbef4e92af852834459281a817
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728175"
---
# <a name="configure-federation-routes-and-media-traffic"></a>Konfigurieren von Partnerverbundrouten und Mediendatenverkehr

 


Föderation ist eine Vertrauensstellung zwischen zwei oder mehr SIP-Domänen, die es Benutzern in separaten Organisationen ermöglicht, über Netzwerkgrenzen hinweg zu kommunizieren. Nachdem Sie die Migration zu Ihrem lync Server 2013-Pilot Pool durchgeführt haben, müssen Sie von der Verbund Route Ihrer Microsoft Office Communications Server 2007 R2-Edgeserver zur Föderations Route ihrer lync Server 2013-Edgeserver wechseln.

Führen Sie die folgenden Verfahren aus, um die Föderations Route und die Medien Verkehrsroute von Ihrem Office Communications Server 2007 R2-Edgeserver und-Director auf Ihren lync Server 2013-Edgeserver für eine Bereitstellung mit einem einzelnen Standort umzustellen.


> [!IMPORTANT]  
> Für das Ändern der Route für die Verbund Route und den Mediendatenverkehr müssen Sie Wartungs Ausfälle für die Edgeserver lync Server 2013 und Office Communications Server 2007 R2 planen. Dieser gesamte Übergangsprozess bedeutet auch, dass der Verbundzugriff für die Dauer des Ausfalls nicht verfügbar ist. Sie sollten die Downtime für eine Zeit planen, wenn Sie eine minimale Benutzeraktivität erwarten. Darüber hinaus sollten Sie den Endbenutzern eine ausreichende Benachrichtigung senden. Planen Sie für diesen Ausfall entsprechend, und setzen Sie in Ihrer Organisation angemessene Erwartungen.




> [!IMPORTANT]  
> Wenn Ihr Legacy Office Communications Server 2007 R2-Edgeserver so konfiguriert ist, dass derselbe FQDN für den Access-Edgedienst, den Webkonferenz-Edgedienst und den A/V-Edgedienst verwendet wird, werden die Verfahren in diesem Abschnitt zum Übergang der Verbund Einstellung zu einem lync Server 2013-Edgeserver nicht unterstützt. Wenn die Legacy-Edge-Dienste für die Verwendung desselben FQDN konfiguriert sind, müssen Sie zunächst alle Ihre Benutzer von Office Communications Server 2007 R2 auf lync Server 2013 migrieren und dann den Office Communications Server 2007 R2-Edgeserver außer Betrieb setzen, bevor Sie die Föderation aktivieren. der lync Server 2013-Edgeserver Ausführliche Informationen finden Sie in den folgenden Themen: 
> <UL>
> <LI>
> <P><A href="move-remaining-users-to-lync-server-2013_1.md">Verschieben der verbleibenden Benutzer zu Lync Server 2013</A></P>
> <LI>
> <P>"Entfernen von Servern und Serverrollen" unter<A href="http://go.microsoft.com/fwlink/p/?linkid=268790">http://go.microsoft.com/fwlink/p/?LinkId=268790</A></P></LI></UL>




> [!IMPORTANT]  
> Wenn Ihr XMPP-Verbund über einen lync Server 2013-Edgeserver weitergeleitet wird, können Legacy Office Communications Server 2007 R2-Benutzer nicht mit dem XMPP-Verbundpartner kommunizieren, bis alle Benutzer in lync Server 2013, XMPP-Richtlinien und Es wurden Zertifikate konfiguriert, der XMPP-Verbundpartner wurde auf lync Server 2013 konfiguriert, und zuletzt wurden die DNS-Einträge aktualisiert.



Um eine Topologie beim Hinzufügen oder Entfernen einer Serverrolle erfolgreich zu veröffentlichen, zu aktivieren oder zu deaktivieren, sollten Sie als Benutzer angemeldet sein, der Mitglied der Gruppen RTCUniversalServerAdmins und Domänenadministratoren ist. Es ist auch möglich, die richtigen Benutzerrechte und Berechtigungen für das Hinzufügen von Serverrollen zu delegieren. Ausführliche Informationen finden Sie unter [Delegieren von Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in der Dokumentation zur Standard Edition-Server-oder Enterprise Edition-Server Bereitstellung. Bei anderen Konfigurationsänderungen ist nur die Mitgliedschaft in der RTCUniversalServerAdmins-Gruppe erforderlich.

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a>So entfernen Sie die Legacy Verbund Zuordnung von lync Server 2013-Websites

1.  Öffnen Sie die Topologie des pilotpools mithilfe des Topologie-Generators.

2.  Navigieren Sie im linken Bereich zum Websiteknoten.

3.  Klicken Sie mit der rechten Maustaste auf die Website, und klicken Sie dann auf **Eigenschaften bearbeiten**.

4.  Wählen Sie im linken Bereich die Option **Föderations Route** aus.

5.  Deaktivieren Sie Unterwebsite Verbund-Routenzuordnung das Kontrollkästchen neben **SIP-Verbund aktivieren** , um die Föderations Route über die **BackCompatSite**zu deaktivieren.
    
    ![Dialogfeld ' Eigenschaften bearbeiten ', Verbund Route](images/JJ721925.2a80c103-c0cc-43ed-ba00-420f9add006a(OCS.15).jpg "Dialogfeld ' Eigenschaften bearbeiten ', Verbund Route")

6.  Klicken Sie auf **OK** , um die Seite Eigenschaften bearbeiten zu schließen.

7.  Wählen Sie im **Topologie-Generator**den **lync-Server**mit dem obersten Knoten aus.

8.  Klicken Sie im Menü **Aktion** auf **Topologie veröffentlichen** , und schließen Sie den Assistenten ab.

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a>So konfigurieren Sie den Legacy-Edgeserver als nicht-Föderations-Edgeserver

1.  Klicken Sie im Menü " **Aktion** " auf der Seite " **Topologie-Generator**" auf **Office Communications Server 2007 R2-Topologie zusammenführen**.

2.  Klicken Sie auf **Weiter**, um fortzufahren.

3.  Wählen Sie auf der **Seite Edge-Setup angeben**den **internen FQDN des Edge-Servers** aus, der derzeit für den Verbund konfiguriert ist, und klicken Sie dann auf **ändern**.
    
    ![Zusammenführen der OCS 2007 R2-Topologie, angeben des Edge-Setups](images/JJ721925.42c15aaf-c1ac-4fb1-a086-665835c57b23(OCS.15).jpg "Zusammenführen der OCS 2007 R2-Topologie, angeben des Edge-Setups")

4.  Klicken Sie auf **weiter** , und übernehmen Sie die Standardeinstellungen, bis Sie zur Seite **externen Edge angeben** gelangen:
    
    ![Topologie-Generator, Seite ' externe Kante angeben '](images/JJ721925.e36f3a1f-3655-456e-9e6d-4814c37da0bf(OCS.15).jpg "Topologie-Generator, Seite ' externe Kante angeben '")

5.  Deaktivieren Sie im Feld **externen Rand angeben**das Kontrollkästchen **dieser Edge-Pool wird für Verbund-und öffentliche Chat Verbindungen verwendet** . Dadurch wird die Verbund Zuordnung mit dem BackCompatSite entfernt.
    

    > [!IMPORTANT]  
    > Dieser Schritt ist wichtig. Sie müssen diese Option deaktivieren, um die Legacy Federation Association zu entfernen.



6.  Klicken Sie auf **weiter** , und übernehmen Sie die Standardeinstellungen der restlichen Seiten des Assistenten.

7.  Klicken Sie in **Zusammenfassung**auf **weiter** , um mit dem Zusammenführen der Topologien zu beginnen.

8.  Überprüfen Sie in der Spalte **Status** , ob der Wert **erfolgreich**ist, und klicken Sie dann auf **Fertig stellen** , um den Assistenten zu schließen.

9.  Wählen Sie im Menü **Aktion** die Option **Topologie veröffentlichen**aus, und klicken Sie dann auf **weiter**.

10. Klicken Sie nach Abschluss des **Veröffentlichungs-Assistenten** auf **Fertig stellen** , um den Assistenten zu schließen.
    
    ![Topologie-Generator mit Website, die nach dem Zusammenführen angezeigt wird](images/JJ721925.92b679ad-332f-49aa-b4e2-19f939b711ca(OCS.15).jpg "Topologie-Generator mit Website, die nach dem Zusammenführen angezeigt wird")
    
    Wie in der vorherigen Abbildung zu sehen ist, ist der **SIP-Verbund** , der sich unter **Website Verbund-Routenzuordnung** befindet, auf **deaktiviert**festgesetzt.

## <a name="to-configure-certificates-on-the-lync-server-2013-edge-server"></a>So konfigurieren Sie Zertifikate auf dem lync Server 2013-Edgeserver

1.  Exportieren Sie das Proxy Zertifikat für den externen Zugriff mit dem privaten Schlüssel aus dem Legacy Office Communications Server 2007 R2 Edge-Server.

2.  Importieren Sie auf dem lync Server 2013-Edgeserver das externe Zugriffs Proxy Zertifikat aus dem vorherigen Schritt.

3.  Weisen Sie das externe Zertifikat des Zugriffsproxys zur externen lync Server 2013-Schnittstelle des Edgeserver zu.

4.  Das interne Schnittstellen Zertifikat des lync Server 2013-Edge-Servers sollte nicht geändert werden.

## <a name="to-change-office-communications-server-2007-r2-federation-route-to-use-lync-server-2013-edge-server"></a>So ändern Sie die Office Communications Server 2007 R2-Verbund Route zur Verwendung des lync Server 2013 Edge-Servers

1.  Öffnen Sie auf dem Office Communications Server 2007 R2 Standard Edition-Server oder-Front-End-Server das Office Communications Server 2007 R2-Verwaltungstool.

2.  Erweitern Sie im linken Bereich den obersten Knoten, und klicken Sie dann mit der rechten Maustaste auf den Knoten **Gesamtstruktur** . Wählen Sie **Eigenschaften**aus, und klicken Sie dann auf **globale Eigenschaften**.

3.  Klicken Sie auf die Registerkarte **Föderation** .

4.  Aktivieren Sie das Kontrollkästchen, um Verbund-und öffentliche Chat Verbindungen zu aktivieren.

5.  Geben Sie den FQDN des lync Server 2013-Edge-Servers ein, und klicken Sie dann auf **OK**.
    
    ![Globale OCS-Eigenschaften, Registerkarte "Föderation"](images/JJ721925.da633f72-43c6-4dac-8d37-ccd0dcde79c9(OCS.15).jpg "Globale OCS-Eigenschaften, Registerkarte "Föderation"")

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a>So aktivieren Sie den lync Server 2013-Edgeserver-Verbund

1.  Navigieren Sie im linken Bereich des Topologie-Generators zum Knoten lync Server 2013- **Edge-Pools** .

2.  Erweitern Sie den Knoten, klicken Sie mit der rechten Maustaste auf den aufgelisteten Edgeserver, und klicken Sie dann auf **Eigenschaften bearbeiten**.
    

    > [!NOTE]  
    > Der Verbund kann nur für einen einzelnen Edge-Pool aktiviert werden. Wenn Sie über mehrere Edge-Pools verfügen, wählen Sie eine aus, die Sie als Föderations-Edge-Pool verwenden möchten.



3.  Aktivieren Sie auf der Seite **Allgemein** das Kontrollkästchen **Föderation für diesen Edge-Pool aktivieren (Port 5061)** .
    
    ![Eigenschaften bearbeiten, allgemein, Edge-Verbund aktivieren](images/JJ721925.2aeb5958-da55-4910-b3d7-2124e144a2f0(OCS.15).jpg "Eigenschaften bearbeiten, allgemein, Edge-Verbund aktivieren")

4.  Klicken Sie auf **OK** , um die Seite Eigenschaften bearbeiten zu schließen.

5.  Navigieren Sie als nächstes zum Websiteknoten.

6.  Klicken Sie mit der rechten Maustaste auf die Website, und klicken Sie dann auf **Eigenschaften bearbeiten**.

7.  Klicken Sie im linken Bereich auf **Föderations Route**.

8.  Wählen Sie unter **Website Verbund-Routenzuordnung**die Option **SIP-Verbund aktivieren**aus, und wählen Sie dann in der Liste den Eintrag lync Server 2013 Edge Server aus.

9.  Klicken Sie auf **OK** , um die Seite **Eigenschaften bearbeiten** zu schließen.
    
    ![Bearbeiten von Eigenschaften, allgemein, Verknüpfen des Edge-Pools](images/JJ721925.33d43297-10cd-412e-bf4a-a1d9a84b9009(OCS.15).jpg "Bearbeiten von Eigenschaften, allgemein, Verknüpfen des Edge-Pools")
    
    Führen Sie für die Bereitstellung mehrerer Websites dieses Verfahren an jedem Standort aus.

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a>So konfigurieren Sie den ausgehenden Medienpfad von lync Server 2013 Edge Server

1.  Navigieren Sie im **Topologie-Generator**zum lync Server 2013-Pool unter **Standard Edition-Front-End-Server** oder **Enterprise Edition-Front-End-Pools**.

2.  Klicken Sie mit der rechten Maustaste auf den Pool, und klicken Sie dann auf **Eigenschaften bearbeiten**.

3.  Aktivieren Sie im Abschnitt **Zuordnungen** das Kontrollkästchen **Edge-Pool zuordnen (für Medienkomponenten)** .

4.  Wählen Sie im Dropdownfeld den lync Server 2013-Edgeserver aus.
    
    ![Dialogfeld ' Eigenschaften bearbeiten ', Verknüpfung des Edge-Pools](images/JJ721925.0cb76b08-5923-4972-8d7a-a829cb77136b(OCS.15).jpg "Dialogfeld ' Eigenschaften bearbeiten ', Verknüpfung des Edge-Pools")

5.  Klicken Sie auf **OK** , um die Seite **Eigenschaften bearbeiten** zu schließen.

## <a name="to-publish-edge-server-configuration-changes"></a>So veröffentlichen Sie Änderungen an Edge-Server-Konfigurationen

1.  Wählen Sie im **Topologie-Generator**den **lync-Server**mit dem obersten Knoten aus.

2.  Wählen Sie im Menü **Aktion** die Option **Topologie veröffentlichen** aus, und schließen Sie den Assistenten ab.

3.  Warten Sie, bis die Active Directory-Replikation für alle Pools in der Bereitstellung erfolgt.
    

    > [!NOTE]  
    > Möglicherweise wird die folgende Meldung angezeigt:<BR><STRONG>Warnung: die Topologie enthält mehr als einen Federated-Edgeserver. Dies kann während der Migration zu einer neueren Version des Produkts auftreten. In diesem Fall würde nur ein Edgeserver für den Verbund aktiv verwendet. Überprüfen Sie, ob der externe DNS-SRV-Eintrag auf den richtigen Edgeserver verweist. Wenn Sie mehrere Verbund-Edgeserver bereitstellen möchten, um gleichzeitig aktiv zu sein (also kein Migrationsszenario), stellen Sie sicher, dass alle Verbundpartner Office Communications Server 2007 R2 oder lync Server verwenden. Überprüfen Sie, ob der externe DNS-SRV-Eintrag alle Verbund fähigen Edgeserver auflistet.</STRONG><BR>Diese Warnung wird erwartet und kann bedenkenlos ignoriert werden.



## <a name="to-verify-federation-and-remote-access-for-external-users"></a>So überprüfen Sie den Verbund und den Remotezugriff für externe Benutzer

1.  Öffnen Sie auf dem lync Server 2013-Front-End-Server die lync Server-Verwaltungsshell.

2.  Wenn Sie den Status von Föderation und RAS überprüfen möchten, geben Sie in der Befehlszeile Folgendes ein:
    
        Get-CsAccessEdgeConfiguration

3.  Um Föderation und RAS zu aktivieren, geben Sie in der Befehlszeile Folgendes ein:
    
        Set-CsAccessEdgeConfiguration
    
    Weitere Informationen zu diesen Cmdlets finden Sie unter den folgenden Themen: [Get-csaccessedgeconfiguration nicht angeben](https://technet.microsoft.com/en-us/library/gg398574\(v=ocs.15\)) und [csaccessedgeconfiguration nicht angeben](https://technet.microsoft.com/en-us/library/gg413017\(v=ocs.15\)).

4.  Warten Sie, bis die Replikation abgeschlossen ist, bevor Sie die lync Server 2013-Edgeserver online schalten und den Verbund und externen Zugriff testen.

## <a name="to-configure-lync-server-2013-edge-server"></a>So konfigurieren Sie den lync Server 2013-Edgeserver

1.  Bringen Sie alle lync Server 2013-Edgeserver online.

2.  Aktualisieren Sie die Routingregeln für externe Firewalls oder die Einstellungen für das Hardwarelastenausgleich, um SIP-Datenverkehr für externen Zugriff (normalerweise Port 443) und Föderation (in der Regel Port 5061) an den lync Server 2013-Edgeserver anstelle des Legacy-Edgeserver zu senden.
    

    > [!NOTE]  
    > Wenn Sie nicht über ein Hardware-Lastenausgleichsmodul verfügen, müssen Sie den DNS-a-Eintrag für Federation aktualisieren, um den neuen lync Server Access-Edgeserver zu beheben. Um dies bei minimaler Unterbrechung zu erreichen, verringern Sie den TTL-Wert für den externen lync Server Access-Edge-FQDN, sodass beim Aktualisieren von DNS auf den neuen lync Server Access-Edgeserver die Föderation und der Remotezugriff schnell aktualisiert werden.



3.  Beenden Sie als nächstes den **lync Server Access-Edge** von jedem Edgeserver-Computer.

4.  Öffnen Sie auf jedem Legacy-Edgeserver-Computer das Applet **Dienste** in den **Verwaltungs Tools**.

5.  Suchen Sie in der Liste Dienste nach **Office Communications Server Access Edge**.

6.  Klicken Sie mit der rechten Maustaste auf den Namen der Dienste, und wählen Sie dann **Beenden** aus, um den Dienst zu beenden.

7.  Setzen Sie den Starttyp auf **disabled**.

8.  Klicken Sie auf **OK** , um das **Eigenschaften** Fenster zu schließen.

## <a name="to-test-connectivity-of-external-users-and-external-access"></a>So testen Sie die Konnektivität externer Benutzer und des externen Zugriffs

  - Benutzer aus mindestens einer Verbunddomäne, einem internen Benutzer in lync Server 2013 und einem Benutzer in Office Communications Server 2007 R2 Testen Sie Instant Messaging (im), Anwesenheitsinformationen, Audio/Video (A/V) und Desktopfreigabe.

  - Benutzer jedes öffentlichen Chat Dienstanbieters, die von Ihrer Organisation unterstützt werden (und für die Bereitstellung abgeschlossen wurde), die mit einem Benutzer in lync Server 2013 und einem Benutzer in Office Communications Server 2007 R2 kommunizieren.

  - Überprüfen Sie, ob anonyme Benutzer an Konferenzen teilnehmen können.

  - Ein Benutzer, der auf Office Communications Server 2007 R2 mithilfe des Remotebenutzerzugriffs (Anmelden bei Office Communications Server 2007 R2 von außerhalb des Intranets, aber ohne VPN) mit einem Benutzer in lync Server 2013 und einem Benutzer auf Office Communications Server 2007 R2 gehostet wird. Testen Sie Chat, Anwesenheit, A/V und Desktopfreigabe.

  - Ein Benutzer, der auf lync Server 2013 mithilfe des Remotebenutzerzugriffs (Anmeldung bei lync Server 2013 von außerhalb des Intranets, aber ohne VPN) mit einem Benutzer in lync Server 2013 und einem Benutzer auf Office Communications Server 2007 R2 gehostet wird. Testen Sie Chat, Anwesenheit, A/V und Desktopfreigabe.

