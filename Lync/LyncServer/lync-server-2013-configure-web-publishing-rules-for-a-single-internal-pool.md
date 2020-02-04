---
title: 'Lync Server 2013: Konfigurieren von Webveröffentlichungsregeln für einen einzelnen internen Pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure web publishing rules for a single internal pool
ms:assetid: 86ff4b2a-1ba9-46a2-a175-8b19e00a49dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429712(v=OCS.15)
ms:contentKeyID: 48184725
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ea798f3d5cefa3b65194eb8afcb6e9b35aaa9c1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741315"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-web-publishing-rules-for-a-single-internal-pool-in-lync-server-2013"></a>Konfigurieren von Webveröffentlichungsregeln für einen einzelnen internen Pool in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-07-07_

Microsoft Forefront Threat Management Gateway 2010 und Internet Information Server Application Request Routing (IIS arr) verwendet Webveröffentlichungsregeln zum Veröffentlichen interner Ressourcen, beispielsweise einer Besprechungs-URL, für Benutzer im Internet.

Zusätzlich zu den Webdienste-URLs für die virtuellen Verzeichnisse müssen Sie auch Veröffentlichungsregeln für einfache URLs, die LyncDiscover-URL und den Office Web Apps-Server erstellen. Für jede einfache URL müssen Sie eine einzelne Regel auf dem Reverseproxy erstellen, die auf diese einfache URL verweist.

Wenn Sie Mobilität bereitstellen und die automatische Ermittlung verwenden, müssen Sie eine Veröffentlichungsregel für die URL des externen AutoErmittlungsdiensts erstellen. Für die automatische Ermittlung sind auch Veröffentlichungsregeln für die externe lync Server-Webdienste-URL für den Director-Pool und den Front-End-Pool erforderlich. Details zum Erstellen der Webveröffentlichungsregeln für die automatische Erkennung finden Sie unter [Konfigurieren des Reverse-Proxys für Mobilität in lync Server 2013](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md).

Führen Sie die folgenden Verfahren aus, um Webveröffentlichungsregeln zu erstellen.

<div>


> [!NOTE]  
> Bei diesen Verfahren wird davon ausgegangen, dass Sie die Standard Edition von Forefront Threat Management Gateway (TMG) 2010 installiert haben oder Internet Information Server mit der Erweiterung Application Request Routing (IIS arr) installiert und konfiguriert haben. Sie verwenden entweder TMG oder IIS arr.



</div>

<div>

## <a name="to-create-a-web-server-publishing-rule-on-the-computer-running-tmg-2010"></a>So erstellen Sie eine Web Server-Veröffentlichungsregel auf dem Computer mit TMG 2010

1.  Klicken Sie auf **Start**, wählen Sie **Programme**aus, wählen Sie **Microsoft Forefront TMG**aus, und klicken Sie dann auf **Forefront TMG-Verwaltung**.

2.  Erweitern Sie im linken Bereich **Servername**, klicken Sie mit der rechten Maustaste auf **Firewall-Richtlinie**, wählen Sie **neu**aus, und klicken Sie dann auf **Website Veröffentlichungsregel**.

3.  Geben Sie auf der Seite **Willkommen bei der neuen Webveröffentlichungsregel** einen Anzeigenamen für die Veröffentlichungsregel ein (beispielsweise LyncServerWebDownloadsRule).

4.  Wählen Sie auf der Seite **Regelaktion auswählen** die Option **zulassen**aus.

5.  Wählen Sie auf der Seite **Veröffentlichungs** **eine einzelne Website oder ein Lastenausgleichsmodul veröffentlichen**aus.

6.  Wählen Sie auf der Seite **Server Verbindungssicherheit** die Option **SSL verwenden aus, um eine Verbindung mit dem veröffentlichten Webserver oder der Serverfarm herzustellen**.

7.  Geben Sie auf der Seite **interne Veröffentlichungs Details** den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) der internen Webfarm ein, die den Inhalt der Besprechungsinhalte und des Adressbuchs im Feld **interner Websitename** hostet.
    
    <div>
    

    > [!NOTE]  
    > Wenn es sich bei dem internen Server um einen Standard Edition-Server handelt, handelt es sich um den FQDN des Standard Edition-Servers. Wenn es sich bei dem internen Server um einen Front-End-Pool handelt, handelt es sich bei diesem FQDN um einen Hardware-Lastenausgleichsmodul (Virtual IP, VIP), mit dem die internen Webfarmserver ausgeglichen werden. Der TMG-Server muss den FQDN in die IP-Adresse des internen Webservers auflösen können. Wenn der TMG-Server den FQDN nicht in die richtige IP-Adresse auflösen kann, können Sie <STRONG>einen Computernamen oder eine IP-Adresse verwenden, um eine Verbindung mit dem veröffentlichten Server herzustellen</STRONG>, und geben Sie dann im Feld <STRONG>Computername oder</STRONG> <STRONG>IP-Adresse</STRONG> die IP-Adresse des internen Webservers ein. In diesem Fall müssen Sie sicherstellen, dass Port 53 auf dem TMG-Server geöffnet ist und einen DNS-Server erreicht, der sich im Umkreisnetzwerk befindet. Sie können auch Einträge in der lokalen Hosts-Datei verwenden, um die Namensauflösung bereitzustellen.

    
    </div>

8.  **Geben / ** Sie auf der Seite **interne Veröffentlichungs Details** im Feld **Pfad (optional)** den Pfad des zu veröffentlichenden Ordners ein.
    
    <div>
    

    > [!NOTE]  
    > Im Website-Veröffentlichungs-Assistenten können Sie nur einen Pfad angeben. Zusätzliche Pfade können durch Ändern der Eigenschaften der Regel hinzugefügt werden.

    
    </div>

9.  Überprüfen Sie auf der Seite Details für den **öffentlichen Namen** , ob **dieser Domänenname** unter **Anforderungen annehmen für**ausgewählt ist, geben Sie im Feld **Öffentlicher Name** den FQDN der externen Webdienste ein.

10. Klicken Sie auf der Seite **Weblistener auswählen** auf **neu** , um den Assistenten für neue Weblistener-Definition zu öffnen.

11. Geben Sie auf der Seite **Willkommen beim neuen Weblistener-Assistenten** im Feld **Weblistener-Name** einen Namen für den Weblistener ein (beispielsweise LyncServerWebServers).

12. Wählen Sie auf der Seite **Client Verbindungssicherheit** die Option **SSL-gesicherte Verbindungen mit Clients anfordern**aus.

13. Wählen Sie auf der Seite **Weblistener-IP-Adresse** die Option **extern**aus, und klicken Sie dann auf **IP-Adressen auswählen**.

14. Wählen Sie auf der Seite **externe Listener-IP-Auswahl** die Option **angegebene IP-Adresse auf dem Forefront TMG-Computer im ausgewählten Netzwerk**aus, wählen Sie die entsprechende IP-Adresse aus, und klicken Sie auf **Hinzufügen**.

15. Wählen Sie auf der Seite **Listener SSL-Zertifikate** die Option **Zertifikat für jede IP-Adresse zuweisen**aus, wählen Sie die IP-Adresse aus, die dem externen Web-FQDN zugeordnet ist, und klicken Sie dann auf **Zertifikat auswählen**.

16. Wählen Sie auf der Seite **Zertifikat auswählen** das Zertifikat aus, das mit den in Schritt 9 angegebenen öffentlichen Namen übereinstimmt, und klicken Sie auf **auswählen**.

17. Wählen Sie auf der Seite **Authentifizierungseinstellung** **keine Authentifizierung**aus.

18. Klicken Sie auf der Seite **SSO-Einstellungen** auf **weiter**.

19. Überprüfen Sie auf der Seite **abschließen des Weblistener-Assistenten** , ob die **Weblistener-** Einstellungen korrekt sind, und klicken Sie dann auf **Fertig stellen**.

20. Wählen Sie auf der Seite **Authentifizierungsdelegierung** **keine Delegierung aus, aber der Client kann sich direkt authentifizieren**.

21. Klicken Sie auf der Seite **Benutzersatz** auf **weiter**.

22. Überprüfen Sie auf der Seite zum **Abschließen der neuen Webveröffentlichungsregel** , ob die Einstellungen für die Webveröffentlichungsregel richtig sind, und klicken Sie dann auf **Fertig stellen**.

23. Klicken Sie im Detailbereich auf über **nehmen** , um die Änderungen zu speichern und die Konfiguration zu aktualisieren.

</div>

<div>

## <a name="to-create-a-web-server-publishing-rule-on-the-computer-running-iis-arr"></a>So erstellen Sie eine Web Server-Veröffentlichungsregel auf dem Computer, auf dem IIS arr ausgeführt wird

1.  Binden Sie das Zertifikat, das Sie für den Reverse-Proxy verwenden, an das HTTPS-Protokoll. Klicken Sie auf **Start**, wählen Sie **Programme**aus, wählen Sie **Verwaltung**aus, und klicken Sie dann auf **Internet Informationsdienste (IIS)-Manager**.
    
    <div>
    

    > [!NOTE]  
    > Weitere Hilfe, Screenshots und Anleitungen zum Bereitstellen und Konfigurieren von IIS arr finden Sie im NextHop-Artikel <A href="http://go.microsoft.com/fwlink/?linkid=293391">Verwenden von IIS arr als Reverse-Proxy für lync Server 2013</A>.

    
    </div>

2.  Wenn dies noch nicht geschehen ist, importieren Sie das Zertifikat, das Sie für den Reverse-Proxy verwenden werden. Klicken Sie im **Internet Informationsdienste (IIS)-Manager**auf den Namen des Reverse Proxyservers auf der linken Seite der Konsole. Klicken Sie in der Mitte der Konsole unter **IIS** auf **Server Zertifikate**. Klicken Sie mit der rechten Maustaste auf **Server Zertifikate** , und wählen Sie **Funktion öffnen**aus.

3.  Klicken Sie auf der rechten Seite der Konsole auf **importieren.**... Geben Sie den Pfad und den Dateinamen des Zertifikats mit der Erweiterung ein, oder klicken Sie auf **...** , um nach dem Zertifikat zu suchen. Wählen Sie das Zertifikat aus, und klicken Sie auf **Öffnen**. Geben Sie das Kennwort ein, mit dem der private Schlüssel geschützt wird (wenn Sie beim Exportieren des Zertifikats und des privaten Schlüssels ein Kennwort zugewiesen haben). Klicken Sie auf **OK**. Wenn der Zertifikatimport erfolgreich war, wird das Zertifikat als Eintrag in der Mitte der Konsole als Eintrag in **Server Zertifikate**angezeigt.

4.  Weisen Sie das Zertifikat zur Verwendung durch HTTPS zu. Wählen Sie auf der linken Seite der Konsole die **Standardwebsite** des IIS-Servers aus. Klicken Sie auf der rechten Seite auf **Bindungen...**. Klicken Sie im Dialogfeld **Websitebindungen** auf **hinzufügen.**... Wählen Sie im Dialogfeld **Websitebindung hinzufügen** unter **Typ:** die Option **https**aus. Wenn Sie HTTPS auswählen, können Sie das Zertifikat auswählen, das für HTTPS verwendet werden soll. Wählen Sie unter **SSL-Zertifikat:** das Zertifikat aus, das Sie für den Reverse-Proxy importiert haben. Klicken Sie auf **OK**. Klicken Sie dann auf **Schließen**. Das Zertifikat ist nun an den Reverse-Proxy für Secure Socket Layer (SSL) und Transport Layer Security (TLS) gebunden.
    
    <div>
    

    > [!IMPORTANT]  
    > Wenn beim Schließen der Bindungen Dialogfelder, die Zwischenzertifikate fehlen, eine Warnung angezeigt wird, müssen Sie das Zertifikat der öffentlichen Zertifizierungsstelle für die Stammzertifizierungsstelle und alle Zwischenzertifizierungsstellen Zertifikate suchen und importieren. Lesen Sie die Anweisungen in der öffentlichen Zertifizierungsstelle, von der Sie Ihr Zertifikat angefordert haben, und folgen Sie den Anweisungen zum Anfordern und Importieren einer Zertifikatkette. Wenn Sie das Zertifikat von Ihrem Edge-Server exportiert haben, können Sie das Stammzertifizierungsstellenzertifikat und alle dem Edgeserver zugeordneten Zwischenzertifizierungsstellen Zertifikate exportieren. Importieren Sie das Zertifikat der Stammzertifizierungsstelle auf dem Computer (nicht zu verwechseln mit dem Benutzerspeicher) vertrauenswürdige Stammzertifizierungsstellen und Zwischenzertifikate in den Zwischenspeicher des Computers Zwischenzertifizierungsstellen.

    
    </div>

5.  Klicken Sie auf der linken Seite der Konsole unter dem Namen des IIS-Servers mit der rechten Maustaste auf **Server** Farmen, und klicken Sie dann auf **Serverfarm erstellen...**.
    
    <div>
    

    > [!NOTE]  
    > Wenn der Knoten <STRONG>Server Farms</STRONG> nicht angezeigt wird, müssen Sie den Anwendungs Anforderungs Routing installieren. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Einrichten von Reverse-Proxyservern für lync Server 2013</A>.

    
    </div>
    
    Geben Sie im Dialogfeld **Serverfarm erstellen** in **Serverfarm Name**den Namen (Dies kann ein Anzeigename für die Identifizierung sein) für die erste URL ein. Klicken Sie auf **Weiter**.

6.  Geben Sie im Dialogfeld **Server hinzufügen** unter **Serveradresse**den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) der externen Webdienste auf dem Front-End-Server ein. Die Namen, die hier zum Beispiel verwendet werden, sind dieselben, die im Planungsabschnitt für den Reverse Proxy, [Certificate Summary-Reverse Proxy in lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md), verwendet werden. In Bezug auf die Reverse-Proxy-Planung geben wir `webext.contoso.com`den FQDN ein. Vergewissern Sie sich, dass das Kontrollkästchen neben **Online** aktiviert ist. Klicken Sie auf **Hinzufügen** , um den Server zum Pool von Webservern für diese Konfiguration hinzuzufügen.
    
    <div>
    

    > [!WARNING]  
    > Lync Server verwendet Hardwarelastenausgleichs, um die Pool Director-und Front-End-Server für http-und HTTPS-Datenverkehr zu verwenden. Beim Hinzufügen eines Servers zur IIS arr-Server Farm wird nur ein FQDN bereitgestellt. Der FQDN ist der Front-End-Server oder-Director in nicht gepoolten Serverkonfigurationen oder der FQDN des konfigurierten Hardware Lastenausgleichs für Server Pools. Die einzige unterstützte Methode zum Lastenausgleich von http-und HTTPS-Datenverkehr ist die Verwendung von Hardwarelastenausgleichs.

    
    </div>

7.  Klicken Sie im Dialogfeld **Server hinzufügen** auf **Erweiterte Einstellungen.**... Dadurch wird ein Dialogfeld zum Definieren des Anwendungs Anforderungs Routings für Anforderungen an den konfigurierten FQDN geöffnet. Das Ziel besteht darin, den Port neu zu definieren, der verwendet wird, wenn die Anforderung von IIS arr verarbeitet wird.
    
    Standardmäßig muss der http-Ziel-Port als 8080 definiert werden. Klicken Sie neben dem aktuellen **Wert von HTTPPort 80** , und setzen Sie den Wert auf **8080**. Klicken Sie neben dem aktuellen **httpsPort 443** , und setzen Sie den Wert auf **4443**. Belasse den **Gewichtungs** Parameter bei 100. Falls erforderlich, können Sie die Gewichtung für eine bestimmte Regel neu definieren, sobald Sie eine Baseline-Statistik haben. Klicken Sie auf **Fertig stellen** , um diesen Teil der Regelkonfiguration abzuschließen.

8.  Möglicherweise wird ein Dialogfeld zum Umschreiben von Regeln angezeigt, in dem Sie darüber informiert werden, dass IIS-Manager eine URL-umschreibungs Regel erstellen kann, um alle eingehenden Anforderungen automatisch an die Serverfarm weiterzuleiten. Klicken Sie auf **Ja**. Sie werden die Regeln manuell anpassen, aber durch Auswählen von Ja wird die ursprüngliche Konfiguration festgelegt.

9.  Klicken Sie auf den Namen der Serverfarm, die Sie soeben erstellt haben. Doppelklicken Sie in der Ansicht IIS-Manager-Features unter **Server Farm** auf **Zwischenspeicherung**. Deaktivieren Sie den **Datenträgercache aktivieren**. Klicken Sie auf der rechten Seite auf über **nehmen** .

10. Klicken Sie auf den Namen der Serverfarm. Doppelklicken Sie in der Ansicht IIS-Manager-Features unter **Server Farm** auf **Proxy**. Ändern Sie auf der Seite Proxy Einstellungen den Wert für **Timeout (Sekunden)** auf einen Wert, der für Ihre Bereitstellung angemessen ist. Klicken Sie auf über **nehmen** , um die Änderung zu speichern.
    
    <div>
    

    > [!IMPORTANT]  
    > Der Proxy-Timeoutwert ist eine Zahl, die von der Bereitstellung bis zur Bereitstellung variieren kann. Überwachen Sie Ihre Bereitstellung, und ändern Sie den Wert für die optimale Benutzerfreundlichkeit für Clients. Möglicherweise können Sie den Wert so einstellen, dass er so gering wie 200 ist. Wenn Sie lync Mobile-Clients in Ihrer Umgebung unterstützen, sollten Sie den Wert auf 960 setzen, um das Timeout von Push-Benachrichtigungen von Office 365 zu ermöglichen, die einen Timeoutwert von 900 aufweisen. Es ist sehr wahrscheinlich, dass Sie den Timeoutwert erhöhen müssen, um zu verhindern, dass der Client die Verbindung trennt, wenn der Wert zu gering ist, oder die Zahl verkleinern, wenn Verbindungen über den Proxy nicht getrennt werden, und löschen, nachdem der Client die Verbindung getrennt hat. Überwachen und Base-Lining was für Ihre Umgebung normal ist, ist die einzige genaue Methode, um festzustellen, wo die richtige Einstellung für diesen Wert ist.

    
    </div>

11. Klicken Sie auf den Namen der Serverfarm. Doppelklicken Sie in der Ansicht IIS-Manager-Features unter **Server Farm** auf **Routing Regeln**. Deaktivieren Sie im Dialogfeld Routingregeln unter Routing das Kontrollkästchen neben SSL-Verschiebung aktivieren. Wenn die Möglichkeit zum Deaktivieren des Kontrollkästchens nicht verfügbar ist, aktivieren Sie das Kontrollkästchen **URL-umschreiben verwenden, um eingehende Anforderungen zu überprüfen**. Klicken Sie auf über **nehmen** , um die Änderungen zu speichern.
    
    <div>
    

    > [!WARNING]  
    > Die SSL-Verschiebung durch den Reverse-Proxy wird nicht unterstützt.

    
    </div>

12. Wiederholen Sie die Schritte 5-11 für jede URL, die den Reverse-Proxy durchlaufen muss. Eine gemeinsame Liste ist wie folgt:
    
      - Front-End-Server-Webdienste extern: Webext.contoso.com (bereits durch Initiale durchlaufen konfiguriert)
    
      - Director-Webdienste extern für Director: webdirext.contoso.com (optional, wenn ein Director bereitgestellt wird)
    
      - Einfache URL-Besprechung: Meet.contoso.com
    
      - Einfache URL Dialin: dialin.contoso.com
    
      - Lync-Auto Ermittlungs-URL: lyncdiscover.contoso.com
    
      - Office Web Apps-Server-URL: officewebapps01.contoso.com
        
        <div>
        

        > [!IMPORTANT]  
        > Die URL für den Office Web Apps-Server verwendet eine andere httpsPort-Adresse. In Schritt 7 definieren Sie die <STRONG>httpsPort</STRONG> als <STRONG>443</STRONG> und <STRONG>Wert von HTTPPort</STRONG> als Port <STRONG>80</STRONG>. Alle anderen Konfigurationseinstellungen sind identisch.

        
        </div>

13. Klicken Sie auf der linken Seite der Konsole auf den Namen des IIS-Servers. Suchen Sie in der Mitte der Konsole unter **IIS**nach **URL-Umschreibung** . Doppelklicken Sie auf URL-umschreiben, um die Konfiguration der Regeln für die URL-Umschreibung zu öffnen. Es sollten Regeln für jede Server Farm angezeigt werden, die Sie in den vorherigen Schritten erstellt haben. Wenn dies nicht der Fall ist, vergewissern Sie sich, dass Sie auf den **IIS-Server** Namen direkt unter dem Knoten **Start Seite** in der Internet Information Server-Manager-Konsole geklickt haben.

14. Im Dialogfeld **URL-umschreiben** unter Verwendung von Webext.contoso.com als Beispiel ist der vollständige Name der angezeigten Regel **arr\_Webext.contoso.com\_Loadbalance\_SSL**.
    
      - Doppelklicken Sie auf die Regel, um das Dialogfeld " **Eingehende Regel bearbeiten** " zu öffnen.
    
      - Klicken Sie auf **hinzufügen...** im Dialogfeld " **Bedingungen** ".
    
      - Geben **Sie** unter **Bedingungs Eingabe:** **{\_HTTP-Host}** ein. (Während der Eingabe wird ein Dialogfeld eingeblendet, in dem Sie die Bedingung auswählen können). Wählen Sie unter **überprüfen, ob Eingabezeichenfolge:** **die Option entspricht dem Muster**aus. Geben **\*** Sie im **Muster Eingabetyp** an. **Fall ignorieren** sollte ausgewählt sein. Klicken Sie auf **OK**.
    
      - Scrollen Sie im Dialogfeld " **Eingehende Regel bearbeiten** " nach unten, um das Dialogfeld **Aktion** zu finden. **Aktionstyp:** sollte auf **Route to Server Farm**festzulegen, **Schema:** auf **https://**, **Serverfarm:** auf die URL festzulegen, auf die diese Regel angewendet wird. Für dieses Beispiel sollte dies auf **Webext.contoso.com**festzulegen sein. **Path:** ist auf **/{R: 0}** eingestellt
    
      - Klicken Sie auf über **nehmen** , um die Änderungen zu speichern. Klicken Sie auf **zurück zu Regeln** , um zu den Regeln zum Umschreiben von URLs zurückzukehren.

15. Wiederholen Sie das in Schritt 14 definierte Verfahren für jede der definierten SSL-umschreibungs Regeln, eine pro Server Farm-URL.
    
    <div>
    

    > [!WARNING]  
    > Standardmäßig werden http-Regeln ebenfalls erstellt und durch die ähnliche Namensgebung für die SSL-Regeln bezeichnet. Für das aktuelle Beispiel wird die HTTP-Regel mit dem Namen <STRONG>ARR_webext. contoso. com_loadbalance</STRONG>. Für diese Regeln sind keine Änderungen erforderlich, und Sie können bedenkenlos ignoriert werden.

    
    </div>

</div>

<div>

## <a name="to-modify-the-properties-of-the-web-publishing-rule-in-tmg-2010"></a>So ändern Sie die Eigenschaften der Web-Veröffentlichungsregel in TMG 2010

1.  Klicken Sie auf **Start**, zeigen Sie auf **Programme**, wählen Sie **Microsoft Forefront TMG**aus, und klicken Sie dann auf **Forefront TMG-Verwaltung**.

2.  Erweitern Sie im linken Bereich **Servername**, und klicken Sie dann auf **Firewall-Richtlinie**.

3.  Klicken Sie im Detailbereich mit der rechten Maustaste auf die Webserver-Veröffentlichungsregel, die Sie im vorherigen Verfahren erstellt haben (beispielsweise LyncServerExternalRule), und klicken Sie dann auf **Eigenschaften**.

4.  Führen Sie auf der Seite " **Eigenschaften** " auf der Registerkarte von die folgenden Aktionen **aus** :
    
      - Klicken Sie in der Liste **diese Regel gilt für Datenverkehr aus dieser Quelle** auf **eine beliebige Stelle**, und klicken Sie dann auf **Entfernen**.
    
      - Klicken Sie auf **Hinzufügen**.
    
      - Erweitern Sie unter **Netzwerkentitäten hinzufügen**den Knoten **Netzwerke**, klicken Sie auf **extern**, klicken Sie auf **Hinzufügen**und dann auf **Schließen**.

5.  Stellen Sie auf der Registerkarte **an** sicher, dass das Kontrollkästchen **ursprünglicher Host-Header weiterleiten anstelle des eigentlichen** Kontrollkästchens aktiviert ist.

6.  Aktivieren Sie auf der Registerkarte **Bridging** das Kontrollkästchen **Anforderung an SSL-Port umleiten** , und geben Sie dann Port **4443**an.

7.  Fügen Sie auf der Registerkarte **Öffentlicher Name** die einfachen URLs hinzu (beispielsweise Meet.contoso.com und dialin.contoso.com).

8.  Klicken Sie auf über **nehmen** , um die Änderungen zu speichern, und klicken Sie dann auf **OK**.

9.  Klicken Sie im Detailbereich auf über **nehmen** , um die Änderungen zu speichern und die Konfiguration zu aktualisieren.

</div>

<div>

## <a name="to-modify-the-properties-of-the-web-publishing-rule-in-iis-arr"></a>So ändern Sie die Eigenschaften der Webveröffentlichungsregel in IIS Arr

1.  Klicken Sie auf **Start**, wählen Sie **Programme**aus, wählen Sie **Verwaltung**aus, und klicken Sie dann auf **Internet Informationsdienste (IIS)-Manager**.

2.  Klicken Sie auf der linken Seite der Konsole auf den Namen des IIS-Servers.

3.  Suchen Sie in der Mitte der Konsole unter **IIS**nach **URL-Umschreibung** . Doppelklicken Sie auf URL-umschreiben, um die Konfiguration der Regeln für die URL-Umschreibung zu öffnen.

4.  Doppelklicken Sie auf die Regel, die Sie ändern müssen. Nehmen Sie die gewünschten Änderungen in **Übereinstimmung mit URL**, **Bedingungen**, **Server Variablen** oder **Aktion**vor.

5.  Klicken Sie auf über **nehmen** , um Ihre Änderungen zu bestätigen. Klicken Sie auf **zurück zu Regeln** , um andere Regeln zu ändern, oder schließen Sie die **IIS-Manager-** Konsole, wenn Sie die Änderungen vorgenommen haben.

</div>

</div>

<span> </span>

</div>

</div>

</div>

