---
title: 'Lync Server 2013: Konfigurieren von Webveröffentlichungsregeln für einen einzelnen internen Pool'
TOCTitle: Konfigurieren von Webveröffentlichungsregeln für einen einzelnen internen Pool
ms:assetid: 86ff4b2a-1ba9-46a2-a175-8b19e00a49dd
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg429712(v=OCS.15)
ms:contentKeyID: 49294644
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von Webveröffentlichungsregeln für einen einzelnen internen Pool in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Microsoft Forefront Threat Management Gateway 2010 und Internet Information Server Application Request Routing (IIS ARR) verwenden zur Webveröffentlichungsregeln, um interne Ressourcen, z. B. eine Besprechungs-URL, für Benutzer im Internet zu veröffentlichen.

Zusätzlich zu den Webdienste-URLs für die virtuellen Verzeichnisse müssen Sie Veröffentlichungsregeln für einfache URLs, die LyncDiscover-URL und Office Web Apps-Server erstellen. Für jede einfache URL muss eine einzelne Regel für den Reverseproxy erstellt werden, die auf diese einfache URL zeigt.

Wenn Sie Mobilität bereitstellen und die automatische Ermittlung verwenden, müssen Sie eine Veröffentlichungsregel für die externe AutoErmittlungsdienst-URL erstellen. Zudem erfordert die automatische Ermittlung auch das Veröffentlichen von Regeln für die externe Lync Server-Webdienste-URL für den Directorpool und Front-End-Pool. Ausführliche Informationen zum Erstellen der Webveröffentlichungsregeln für die automatische Ermittlung finden Sie unter [Konfigurieren des Reverseproxys für Mobilität in Lync Server 2013](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md).

Verwenden Sie die folgenden Verfahren, um Webveröffentlichungsregeln zu erstellen.


> [!NOTE]
> Bei diesen Vorgehensweisen wird vorausgesetzt, dass die Standard Edition von Forefront Threat Management Gateway (TMG) 2010 installiert oder Internetinformationsdienste mit der Routingerweiterung für Anwendungsanforderungen (IIS ARR) installiert und konfiguriert ist. Sie verwenden entweder TMG oder IIS ARR. .



## So erstellen Sie eine Webveröffentlichungsregel auf dem Computer, auf dem TMG 2010 ausgeführt wird

1.  Klicken Sie auf **Start** , wählen Sie **Programme** und dann **Microsoft Forefront TMG** aus, und klicken Sie auf **Forefront TMG-Verwaltung** .

2.  Erweitern Sie im linken Bereich **ServerName** , klicken Sie mit der rechten Maustaste auf **Firewallrichtlinie** , wählen Sie **Neu** aus, und klicken Sie dann auf **Website-Veröffentlichungsregel** .

3.  Geben Sie auf der Seite **Willkommen** einen Anzeigenamen für die Veröffentlichungsregel ein (z. B. "LyncServerWebDownloadsRule").

4.  Wählen Sie auf der Seite **Regelaktion auswählen** die Option **Zulassen** aus.

5.  Wählen Sie auf der Seite **Veröffentlichungstyp** die Option **Einzelne Website oder Lastenausgleich veröffentlichen** aus.

6.  Klicken Sie auf der Seite **Sicherheit der Serververbindung** auf **SSL verwenden, um eine Verbindung zum veröffentlichten Webserver oder zur Serverfarm herzustellen** .

7.  Geben Sie auf der Seite **Interne Veröffentlichungsdetails** im Feld **Interner Sitename** den FQDN der internen Webfarm ein, auf der Besprechungsinhalte und Adressbuchdateien gehostet werden.
    

    > [!NOTE]
    > Wenn der interne Server ein Standard Edition-Server ist, entspricht dieser FQDN dem vollqualifizierten Domänennamen des Standard Edition-Servers. Handelt es sich bei Ihrem internen Server um einen Front-End-Pool, entspricht dieser FQDN einer virtuellen IP (VIP) für das Hardwaregerät zum Lastenausgleich, das den Lastenausgleich für die internen Webfarmserver durchführt. Der TMG-Server muss in der Lage sein, den FQDN für die IP-Adresse des internen Webservers aufzulösen. Wenn der TMG-Server den FQDN nicht in eine ordnungsgemäße IP-Adresse auflösen kann, können Sie <STRONG>Name oder IP-Adresse eines Computers verwenden, um eine Verbindung zum veröffentlichten Server herzustellen</STRONG> auswählen und dann die IP-Adresse des internen Webservers in das Feld <STRONG>Computername</STRONG> oder <STRONG>IP-Adresse</STRONG> eingeben. In diesem Fall müssen Sie sicherstellen, dass der Port&nbsp;53 auf dem TMG-Server geöffnet ist und der Server mit einem DNS-Server im Umkreisnetzwerk kommunizieren kann. Sie können für die Namensauflösung auch Einträge in der Datei lokaler Hosts verwenden.



8.  Geben Sie auf der Seite **Interne Veröffentlichungsdetails** im Feld **Pfad (optional)** als Pfad zum Ordner, der veröffentlicht werden soll, **/\*** ein.
    

    > [!NOTE]
    > Sie können im Assistenten zum Veröffentlichen von Websites nur einen Pfad angeben. Weitere Pfade können Sie hinzufügen, indem Sie die Eigenschaften der Regel ändern.



9.  Stellen Sie auf der Seite **Details des öffentlichen Namens** sicher, dass unter **Anforderungen annehmen für** die Option **Diesen Domänennamen** ausgewählt ist, und geben Sie den externen FQDN der Webdienste in das Feld **Öffentlicher Name** ein.

10. Klicken Sie auf der Seite **Weblistener auswählen** auf **Neu** , um den Assistenten für neue Weblistenerdefinition zu öffnen.

11. Geben Sie auf der Seite **Willkommen** im Feld **Weblistenername** einen Namen für den Weblistener ein (z. B. "LyncServerWebServers").

12. Wählen Sie auf der Seite **Sicherheit der Clientverbindung** die Einstellung **Sichere SSL-Verbindungen mit Clients erforderlich** aus.

13. Wählen Sie auf der Seite **Weblistener-IP-Adressen** die Option **Extern** aus, und klicken Sie dann auf **IP-Adressen auswählen** .

14. Wählen Sie auf der Seite zur Auswahl von externen Listener-IP-Adressen die Option **Angegebene IP-Adressen auf dem Forefront TMG-Computer im ausgewählten Netzwerk** aus, wählen Sie die passende IP-Adresse aus und klicken Sie auf **Hinzufügen** .

15. Klicken Sie auf der Seite **Listener-SSL-Zertifikate** auf **Jeder IP-Adresse ein Zertifikat zuweisen** , wählen Sie die IP-Adresse aus, die dem externen Web-FQDN zugeordnet ist, und klicken Sie dann auf **Zertifikat auswählen** .

16. Wählen Sie auf der Seite **Zertifikat auswählen** das Zertifikat aus, das den in Schritt 9 angegebenen öffentlichen Namen entspricht, und klicken Sie auf **Auswählen** .

17. Wählen Sie auf der Seite **Authentifizierungseinstellungen** die Option **Keine Authentifizierung** aus.

18. Klicken Sie auf der Seite **Einstellungen für einmaliges Anmelden (SSO)** auf **Weiter** .

19. Überprüfen Sie auf der Seite **Fertigstellen des Assistenten** die Einstellungen unter **Weblistener** , und klicken Sie dann auf **Fertig stellen** .

20. Klicken Sie auf der Seite **Authentifizierungsdelegierung** auf **Keine Delegierung, aber direkte Authentifizierung des Clients** .

21. Klicken Sie auf der Seite **Benutzersatz** auf **Weiter** .

22. Überprüfen Sie auf der Seite **Fertigstellen des Assistenten** die Einstellungen für die Webveröffentlichungsregel und klicken Sie dann auf **Fertig stellen** .

23. Klicken Sie im Detailbereich auf **Übernehmen** , um die Änderungen zu speichern und die Konfiguration zu aktualisieren.

## So erstellen Sie eine Webserververöffentlichungsregel auf dem Computer, auf dem IIS ARR ausgeführt wird

1.  Binden Sie das Zertifikat, das Sie für den Reverseproxy verwenden möchten, an das HTTPS-Protokoll. Klicken Sie auf **Start** , wählen Sie **Programme** aus, wählen Sie **Verwaltungstools** aus, und klicken Sie dann auf **Internetinformationsdienste-Manager** .
    

    > [!NOTE]
    > Weitere Hilfe, Screenshots und Hilfestellung zum Bereitstellen und Konfigurieren von IIS ARR finden Sie im NextHop-Artikel <A href="http://go.microsoft.com/fwlink/?linkid=293391">Using IIS ARR as a Reverse Proxy for Lync Server 2013</A>.



2.  Wenn dies noch nicht geschehen ist, importieren Sie das Zertifikat, das Sie für den Reverseproxy verwenden möchten. Klicken Sie im **Internetinformationsdienste-Manager** auf der linken Seite der Konsole auf den Namen des Reverseproxyservers. Suchen Sie in der Mitte der Konsole unter **IIS** den Eintrag **Serverzertifikate** . Klicken Sie mit der rechten Maustaste auf **Serverzertifikate** , und wählen Sie **Feature öffnen** aus.

3.  Klicken Sie auf der rechten Seite der Konsole auf **Importieren…** . Geben Sie den Pfad und den Dateinamen mit der Erweiterung ein, oder klicken Sie auf **…** , um nach dem Zertifikat zu suchen. Wählen Sie das Zertifikat aus, und klicken Sie auf **Öffnen** . Geben Sie das Kennwort ein, das zum Schützen des privaten Schlüssels verwendet wird (falls Sie beim Exportieren von Zertifikat und privatem Schlüssel ein Kennwort zugewiesen haben). Klicken Sie auf **OK** . Wenn der Import des Zertifikats erfolgreich war, wird das Zertifikat als Eintrag in der Mitte der Konsole als Eintrag in **Serverzertifikate** angezeigt.

4.  Weisen Sie das Zertifikat für die Verwendung durch HTTPS zu. Wählen Sie auf der linken Seite der Konsole die **Standardwebsite** des IIS-Servers aus. Klicken Sie auf der rechten Seite auf **Bindungen…** . Klicken Sie im Dialogfeld **Sitebindungen** auf **Hinzufügen…** . Wählen Sie im Dialogfeld **Sitebindung hinzufügen** unter **Typ:** den Wert **https** aus. Nach dem Auswählen von "https" können Sie das Zertifikat auswählen, das für HTTPS verwendet werden soll. Wählen Sie unter **SSL-Zertifikat:** das Zertifikat aus, das Sie für den Reverseproxy importiert haben. Klicken Sie auf **OK** . Klicken Sie dann auf **Schließen** . Das Zertifikat ist jetzt an den Reverseproxy für SSL (Secure Socket Layer) und TLS (Transport Layer Security) gebunden.
    

    > [!IMPORTANT]
    > Wenn beim Schließen des Dialogfelds "Bindungen" eine Warnung angezeigt wird, dass Zwischenzertifikate fehlen, müssen Sie das Zertifikat der öffentliche Stammzertifizierungsstelle und alle Zwischenzertifikate der Zertifizierungsstelle importieren. Schlagen Sie in den Anweisungen der öffentlichen Zertifizierungsstelle, bei der Sie ihr Zertifikat angefordert haben, nach, und befolgen Sie die Anweisungen zum Anfordern und Importieren einer Zertifikatkette. Wenn Sie das Zertifikat von Ihrem Edgeserver exportiert haben, können Sie das Stammzertifikat der Zertifizierungsstelle und alle Zwischenzertifikate der Zertifizierungsstelle, die Edgeserver zugewiesen sind, exportieren. Importieren Sie das Stammzertifikat der Zertifizierungsstelle in den Speicher für vertrauenswürdige Stammzertifizierungsstellen des Computers (nicht zu verwechseln mit dem Benutzerspeicher) und Zwischenzertifikate in den Speicher für Zwischenzertifizierungsstellen des Computers.



5.  Klicken Sie auf der linken Seite der Konsole unterhalb des IIS-Servernamens mit der rechten Maustaste auf **Serverfarmen** , und klicken Sie dann auf **Serverfarm erstellen…** .
    

    > [!NOTE]
    > Wenn der Knoten <STRONG>Serverfarmen</STRONG> nicht angezeigt wird, müssen Sie Routing von Anwendungsanforderungen installieren. Details finden Sie unter <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Einrichten von Reverseproxyservern für Lync Server 2013</A>.

    
    Geben Sie im Dialogfeld **Serverfarm erstellen** unter **Serverfarmname** den Namen (dies kann ein Anzeigename zur Identifizierung sein) für die erste URL ein. Klicken Sie auf **Weiter** .

6.  Geben Sie im Dialogfeld **Server hinzufügen** unter **Serveradresse** den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) der externen Webdienste für Ihren Front-End-Server ein. Die Namen, die hier zu Beispielzwecken verwendet werden, sind die gleichen, die im Planungsabschnitt für den Reverseproxy, [Zertifikatzusammenfassung für Reverseproxy in Lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md), verwendet werden. Mit Bezug auf die Planung des Reverseproxys geben wir den FQDN `webext.contoso.com` ein. Bestätigen Sie, dass das Kontrollkästchen neben **Online** aktiviert ist. Klicken Sie auf **Hinzufügen** , um den Server zum Pool der Webserver für diese Konfiguration hinzuzufügen.
    

    > [!WARNING]
    > Lync Server verwendet Hardwarelastenausgleich, um Director und Front-End-Server für HTTP- und HTTPS-Verkehr zu poolen. Beim Hinzufügen eines Servers zur IIS ARR-Serverfarm geben Sie nur einen FQDN an. Der FQDN entspricht dem Front-End-Server oder Director in nicht gepoolten Serverkonfigurationen oder dem FQDN des konfigurieren Hardware-Lastenausgleichsmoduls bei Serverpools. Das einzige unterstützte Verfahren für den Lastenausgleich von HTTP- und HTTPS-Verkehr besteht in der Verwendung von Hardwarelastenausgleich.



7.  Klicken Sie im Dialogfeld **Server hinzufügen** auf **Erweiterte Einstellungen…** . Dadurch wird ein Dialogfeld zum Definieren des Routings von Anwendungsanforderungen zum konfigurierten FQDN geöffnet. Der Zweck besteht in der Neudefinition des verwendeten Ports, wenn die Anforderung von IIS ARR verarbeitet wird.
    
    Standardmäßig muss der HTTP-Zielport als 8080 definiert werden. Klicken Sie neben dem aktuellen **httpPort 80** , und legen Sie den Wert auf **8080** fest. Klicken Sie neben dem aktuellen **httpsPort 443** , und legen Sie den Wert auf **4443** fest. Belassen Sie den Parameter **Stärke** bei 100. Erforderlichenfalls können Sie die Gewichtungen für eine bestehende Regel neu definieren, sobald Sie über grundlegende Statistiken verfügen. Klicken Sie auf **Fertig stellen** , um diesen Teil der Regelkonfiguration abzuschließen.

8.  Möglicherweise wird ein Dialogfeld "Rewriteregeln" angezeigt, das Ihnen mitteilt, dass der IIS-Manager eine URL-Rewriteregel erstellen kann, um alle eingehenden Anforderungen an die Serverfarm automatisch zu routen. Klicken Sie auf **Ja** . Sie müssen die Regeln manuell anpassen, aber indem Sie "Ja" auswählen, wird die Grundkonfiguration festgelegt.

9.  Klicken Sie auf den Namen der Serverfarm, die Sie soeben erstellt haben. In der Featureansicht von IIS-Manager doppelklicken Sie unter **Serverfarm** auf **Zwischenspeicherung** . Deaktivieren Sie **Datenträgercache aktivieren** . Klicken Sie auf der rechten Seite auf **Übernehmen** .

10. Klicken Sie auf den Namen der Serverfarm. In der Featureansicht von IIS-Manager doppelklicken Sie unter **Serverfarm** auf **Proxy** . Ändern Sie auf der Seite für Proxyeinstellungen den Wert für **Timeout (Sekunden):** in einen Wert, der für Ihre Bereitstellung geeignet ist. Klicken Sie auf **Übernehmen** , um die Änderung zu speichern.
    

    > [!IMPORTANT]
    > Der Timeoutwert des Proxys ist eine Zahl, die sich von Bereitstellung zu Bereitstellung unterscheiden wird. Sie sollten Ihre Bereitstellung beobachten und den Wert entsprechend anpassen, um eine optimale Benutzererfahrung für die Clients zu garantieren. Möglicherweise können Sie den Wert sogar nur auf 200 einstellen. Wenn Sie mobile Clients in Ihrer Lync-Umgebung unterstützen, sollten Sie den Wert auf 960 einstellen, um Pushbenachrichtigungen von Office 365 zu ermöglichen. Diese haben einen Timeoutwert von 900. Wahrscheinlich werden Sie den Timeoutwert heraufsetzen müssen, um die Trennung von Clients zu vermeiden, weil der Wert zu niedrig ist, oder ihn herabsetzen müssen, weil Verbindungen über den Proxy auch lange nach dem Trennen des Clients nicht getrennt werden. Nur durch Beobachtung und Ermittlung der für Ihre Umgebung geeigneten Grundwerte lässt sich die korrekte Einstellung für diesen Wert zuverlässig bestimmen.



11. Klicken Sie auf den Namen der Serverfarm. In der Featureansicht von IIS-Manager doppelklicken Sie unter **Serverfarm** auf **Routingregeln** . Deaktivieren Sie im Dialogfeld "Routingregeln" unter "Routing" das Kontrollkästchen neben "SSL-Verschiebung zulassen". Wenn die Möglichkeit zum Deaktivieren dieses Kontrollkästchens nicht besteht, aktivieren Sie das Kontrollkästchen für **URL-Rewrite zur Untersuchung eingehender Anforderungen verwenden** . Klicken Sie auf **Übernehmen** , um Ihre Änderungen zu speichern.
    
    > [!CAUTION]  
	> SSL-Verschiebung über den Reverseproxy wird nicht unterstützt.


12. Wiederholen Sie die Schritte 5-11 für jede URL, die durch den Reverseproxy übergeben werden muss. Eine allgemeine Liste wäre z. B. die folgende:
    
      - Front-End-Server Externe Webdienste: "webext.contoso.com" (bereits im ersten Durchgang konfiguriert)
    
      - Director Externe Webdienste für Director: "webdirext.contoso.com" (Optional, wenn ein Director bereitgestellt wurde)
    
      - Einfache URL für Besprechungen: "meet.contoso.com"
    
      - Einfache URL für Einwahl: "dialin.contoso.com"
    
      - URL für Lync-Autodiscover: "lyncdiscover.contoso.com"
    
      - URL des Office Web Apps-Servers: "officewebapps01.contoso.com"
        

        > [!IMPORTANT]
        > Die URL für den Office Web Apps-Server verwendet eine andere httpsPort-Adresse. In Schritt 7 definieren Sie den <STRONG>httpsPort</STRONG> als <STRONG>443</STRONG> und den <STRONG>httpPort</STRONG> als Port <STRONG>80</STRONG> . Alle anderen Konfigurationseinstellungen sind gleich.



13. Klicken Sie auf der linken Seite der Konsole auf den IIS-Servernamen. Suchen Sie in der Mitte der Konsole unter **IIS** den Eintrag **URL-Rewrite** . Doppelklicken Sie auf "URL-Rewrite", um die Regelkonfiguration für URL-Rewrite zu öffnen. Es sollten Regeln für jede in den vorhergehenden Schritten erstellte Serverfarm angezeigt werden. Ist das nicht der Fall, überprüfen Sie, ob Sie in der Konsole des Internetinformationsdienste-Managers auf den Namen von **IIS-Server** unmittelbar unterhalb des Knotens **Startseite** geklickt haben.

14. Im Dialogfeld **URL-Rewrite** wird der vollständige Name der Regel als **ARR\_webext.contoso.com\_loadbalance\_SSL** angezeigt, wenn "webext.contoso.com" als Beispiel zugrunde gelegt wird.
    
      - Doppelklicken Sie auf die Regel, um das Dialogfeld **Eingangsregel bearbeiten** zu öffnen.
    
      - Klicken Sie im Dialogfeld **Bedingungen** auf **Hinzufügen...** .
    
      - Geben Sie unter **Bedingung hinzufügen** in **Bedingungseingabe:** den Wert **{HTTP\_HOST}** ein. (Während der Eingabe wird ein Dialogfeld angezeigt, in dem Sie die Bedingung auswählen können). Wählen Sie unter **Überprüfen, ob die Eingabezeichenfolge:** den Wert **mit dem Muster übereinstimmt** aus. Geben Sie unter **Mustereingabe** den Wert **\*** ein. **Groß-/Kleinschreibung ignorieren** sollte aktiviert sein. Klicken Sie auf **OK** .
    
      - Führen Sie im Dialogfeld **Eingangsregel bearbeiten** einen Bildlauf nach unten durch, um das Dialogfeld **Aktion** zu finden. **Aktionsart:** sollte auf **An Serverfarm weiterleiten** , **Schema:** auf **https://** und **Serverfarm:** auf die URL festgelegt sein, für die diese Regel gilt. In diesem Beispiel sollte das der Wert **webext.contoso.com** sein. **Pfad:** ist auf **/{R:0}** festgelegt.
    
      - Klicken Sie auf **Übernehmen** , um Ihre Änderungen zu speichern. Klicken Sie auf **Zurück zu den Regeln** , um zu den URL-Rewriteregeln zurückzukehren.

15. Wiederholen Sie die in Schritt 14 definierte Vorgehensweise für jede der SSL-Rewriteregeln, die Sie definiert haben, eine pro Serverfarm-URL.
    

    > [!WARNING]
    > Standardmäßig werden auch HTTP-Regeln erstellt und durch eine den SSL-Regeln ähnliche Benennung gekennzeichnet. Für unser aktuelles Beispiel wäre der Name der HTTP-Regel dann <STRONG>ARR_webext.contoso.com_loadbalance</STRONG> . An diesen Regeln müssen keine Änderungen vorgenommen werden, und sie können ohne Risiko ignoriert werden.



## So ändern Sie die Eigenschaften der Webveröffentlichungsregel in TMG 2010

1.  Klicken Sie auf **Start** , zeigen Sie auf **Programme** , wählen Sie dann **Microsoft Forefront TMG** aus, und klicken Sie auf **Forefront TMG-Verwaltung** .

2.  Erweitern Sie im linken Bereich **ServerName** , und klicken Sie dann auf **Firewallrichtlinie** .

3.  Klicken Sie im Detailbereich mit der rechten Maustaste auf die Webserververöffentlichungsregel, die Sie im vorhergehenden Verfahren erstellt haben (z. B. "LyncServerExternalRule"), und klicken Sie dann auf **Eigenschaften** .

4.  Führen Sie auf der Seite **Eigenschaften** auf der Registerkarte **Von** folgende Schritte aus:
    
      - Klicken Sie in der Liste **Diese Regel betrifft Datenverkehr von diesen Quellen** auf **Beliebig** , und klicken Sie dann auf **Entfernen** .
    
      - Klicken Sie auf **Hinzufügen** .
    
      - Erweitern Sie in **Netzwerkidentitäten hinzufügen** den Eintrag **Netzwerke** , klicken Sie auf **Extern** , dann auf **Hinzufügen** und zuletzt auf **Schließen** .

5.  Stellen Sie auf der Registerkarte **An** sicher, dass das Kontrollkästchen **Ursprünglichen Hostheader anstelle des aktuellen Headers weiterleiten** aktiviert ist.

6.  Aktivieren Sie auf der Registerkarte **Bridging** das Kontrollkästchen **Anforderung an SSL-Port umleiten** , und geben Sie anschließend Port 4443 an.

7.  Fügen Sie auf der Registerkarte **Öffentlicher Name** die einfachen URLs hinzu (z. B. "meet.contoso.com" und "dialin.contoso.com").

8.  Klicken Sie auf **Übernehmen** , um die Änderungen zu speichern, und klicken Sie dann auf **OK** .

9.  Klicken Sie im Detailbereich auf **Übernehmen** , um die Änderungen zu speichern und die Konfiguration zu aktualisieren.

## So ändern Sie die Eigenschaften der Webveröffentlichungsregel in ISS ARR

1.  Klicken Sie auf **Start** , wählen Sie **Programme** aus, wählen Sie **Verwaltungstools** aus, und klicken Sie dann auf **Internetinformationsdienste-Manager** .

2.  Klicken Sie auf der linken Seite der Konsole auf den IIS-Servernamen.

3.  Suchen Sie in der Mitte der Konsole unter **IIS** den Eintrag **URL-Rewrite** . Doppelklicken Sie auf "URL-Rewrite", um die Regelkonfiguration für URL-Rewrite zu öffnen.

4.  Doppelklicken Sie auf die Regel, die Sie ändern müssen. Nehmen Sie Ihre Änderungen nach Bedarf in **URL abgleichen** , **Bedingungen** , **Servervariablen** oder **Aktion** vor.

5.  Klicken Sie auf **Übernehmen** , um Ihre Änderungen festzuschreiben. Klicken Sie auf **Zurück zu den Regeln** , um weitere Regeln zu ändern, oder schließen Sie die **IIS-Manager** -Konsole, wenn Sie Ihre Änderungen abgeschlossen haben.

