---
title: 'Lync Server 2013: Konfigurieren von Webveröffentlichungsregeln für einen einzelnen internen Pool'
description: 'Lync Server 2013: Konfigurieren von Webveröffentlichungsregeln für einen einzelnen internen Pool.'
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
ms.openlocfilehash: 45015c90fdac92fb488affc871f2cfaf9d7506a2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560511"
---
# <a name="configure-web-publishing-rules-for-a-single-internal-pool-in-lync-server-2013"></a>Konfigurieren von Webveröffentlichungsregeln für einen einzelnen internen Pool in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-07-07_

Microsoft Forefront Threat Management Gateway 2010 und IIS ARR (Internet Information Server Application Request Routing) verwendet Webveröffentlichungsregeln zum Veröffentlichen interner Ressourcen wie eine Besprechungs-URL für Benutzer im Internet.

Zusätzlich zu den Webdienste-URLs für die virtuellen Verzeichnisse müssen Sie auch Veröffentlichungsregeln für einfache URLs, die LyncDiscover-URL und den Office-webapps-Server erstellen. Für jede einfache URL müssen Sie eine einzelne Regel für den Reverseproxy erstellen, die auf diese einfache URL verweist.

Wenn Sie Mobilität bereitstellen und die automatische Ermittlung verwenden, müssen Sie eine Veröffentlichungsregel für die externe AutoErmittlungsdienst-URL erstellen. Für die automatische Ermittlung sind auch Veröffentlichungsregeln für die externe lync Server Webdienste-URL für Ihre Directorpool und Front-End-Pool erforderlich. Ausführliche Informationen zum Erstellen der Webveröffentlichungsregeln für die automatische Ermittlung finden Sie unter [Configuring the Reverse Proxy for Mobility in lync Server 2013](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md).

Verwenden Sie die folgenden Verfahren, um Webveröffentlichungsregeln zu erstellen.

<div>


> [!NOTE]  
> Bei diesen Verfahren wird davon ausgegangen, dass Sie die Standard Edition von Forefront Threat Management Gateway (TMG) 2010 installiert haben oder Internet Information Server mit der Erweiterung Application Request Routing (IIS arr) installiert und konfiguriert haben. Sie verwenden entweder TMG oder IIS arr.



</div>

<div>

## <a name="to-create-a-web-server-publishing-rule-on-the-computer-running-tmg-2010"></a>So erstellen Sie eine Webserver-Veröffentlichungsregel auf dem Computer mit TMG 2010

1.  Klicken Sie im **Startmenü**auf **Programme**, wählen Sie **Microsoft Forefront TMG**aus, und klicken Sie dann auf **Forefront TMG-Verwaltung**.

2.  Erweitern Sie im linken Bereich **Servername**, klicken Sie mit der rechten Maustaste auf **Firewall-Richtlinie**, wählen Sie **neu**aus, und klicken Sie dann auf **Website-Veröffentlichungsregel**.

3.  Geben Sie auf der Seite **Willkommen bei der neuen Webveröffentlichungsregel** einen Anzeigenamen für die Veröffentlichungsregel ein (beispielsweise LyncServerWebDownloadsRule).

4.  Wählen Sie auf der Seite **Regelaktion auswählen** die Option **Zulassen** aus.

5.  Wählen Sie auf der Seite **Veröffentlichungstyp** die Option **Einzelne Website oder Lastenausgleich veröffentlichen** aus.

6.  Klicken Sie auf der Seite **Sicherheit der Serververbindung** auf **SSL verwenden, um eine Verbindung zum veröffentlichten Webserver oder zur Serverfarm herzustellen**.

7.  Geben Sie auf der Seite **interne Veröffentlichungs Details** den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) der internen Webfarm ein, die den Inhalt des Besprechungsinhalts und des Adressbuchs im Feld **interner Websitename** hostet.
    
    <div>
    

    > [!NOTE]  
    > Wenn es sich bei dem internen Server um eine Standard Edition-Server handelt, handelt es sich bei diesem FQDN um den Standard Edition-Server-FQDN. Wenn es sich bei dem internen Server um eine Front-End-Pool handelt, handelt es sich bei diesem FQDN um eine virtuelle IP-Adresse für den Hardwarelastenausgleich (VIP), die die internen Webfarmserver mit Lastenausgleich abgleicht. Der TMG-Server muss in der Lage sein, den FQDN in die IP-Adresse des internen Webservers aufzulösen. Wenn der TMG-Server den FQDN nicht in die richtige IP-Adresse auflösen kann, können Sie <STRONG>einen Computernamen oder eine IP-Adresse verwenden, um eine Verbindung mit dem veröffentlichten Server herzustellen</STRONG>, und geben Sie dann in das Feld <STRONG>Computername oder</STRONG> <STRONG>IP-Adresse</STRONG> die IP-Adresse des internen Webservers ein. In diesem Fall müssen Sie sicherstellen, dass Port 53 auf dem TMG-Server geöffnet ist und einen DNS-Server erreichen kann, der sich im Umkreisnetzwerk befindet. Sie können auch Einträge in der lokalen Hostdatei verwenden, um die Namensauflösung bereitzustellen.

    
    </div>

8.  Geben Sie auf der Seite **interne Veröffentlichungs Details** im Feld **Pfad (optional)** **/\*** als Pfad zu dem zu veröffentlichenden Ordner ein.
    
    <div>
    

    > [!NOTE]  
    > Im Assistenten für die Website Veröffentlichung können Sie nur einen Pfad angeben. Durch Ändern der Eigenschaften der Regel können zusätzliche Pfade hinzugefügt werden.

    
    </div>

9.  Bestätigen Sie auf der Seite **Details des öffentlichen namens** , dass **dieser Domänenname** unter **Anforderungen annehmen für**aktiviert ist, geben Sie den externen Webdienste FQDN in das Feld **Öffentlicher Name** ein.

10. Klicken Sie auf der Seite **Weblistener auswählen** auf **neu** , um den Assistenten für neue Weblistener-Definition zu öffnen.

11. Geben Sie auf der Seite **Willkommen beim Assistenten für neue Weblistener** in das Feld **Weblistener-Name** einen Namen für den Weblistener ein (beispielsweise LyncServerWebServers).

12. Wählen Sie auf der Seite **Client Verbindungssicherheit** die Option **SSL-gesicherte Verbindungen mit Clients erforderlich**aus.

13. Wählen Sie auf der Seite **Weblistener-IP-Adresse** die Option **extern**aus, und klicken Sie dann auf **IP-Adressen auswählen**.

14. Wählen Sie auf der Seite **externe Listener-IP-Auswahl** die Option **angegebene IP-Adresse auf dem Forefront TMG-Computer im ausgewählten Netzwerk**aus, wählen Sie die entsprechende IP-Adresse aus, und klicken Sie auf **Hinzufügen**.

15. Wählen Sie auf der Seite **Listener-SSL-Zertifikate** die Option **Zertifikat für jede IP-Adresse zuweisen**aus, wählen Sie die IP-Adresse aus, die dem externen webfqdn zugeordnet ist, und klicken Sie dann auf **Zertifikat auswählen**.

16. Wählen Sie auf der Seite **Zertifikat auswählen** das Zertifikat aus, das mit den in Schritt 9 angegebenen öffentlichen Namen übereinstimmt, und klicken Sie dann auf **auswählen**.

17. Wählen Sie auf der Seite **Authentifizierungseinstellung** die Option **keine Authentifizierung**aus.

18. Klicken Sie auf der Seite **SSO-Einstellung** auf **weiter**.

19. Überprüfen Sie auf der Seite **Fertig stellen des Weblistener-Assistenten** , ob die **Weblistener-** Einstellungen korrekt sind, und klicken Sie dann auf **Fertig stellen**.

20. Klicken Sie auf der Seite **Authentifizierungsdelegierung** auf **Keine Delegierung, aber direkte Authentifizierung des Clients**.

21. Klicken Sie auf der Seite **Benutzergruppe** auf **weiter**.

22. Überprüfen Sie auf der Seite **Fertigstellen des Assistenten** die Einstellungen für die Webveröffentlichungsregel, und klicken Sie dann auf **Fertig stellen**.

23. Klicken Sie im Detailbereich auf **Übernehmen**, um die Änderungen zu speichern und die Konfiguration zu aktualisieren.

</div>

<div>

## <a name="to-create-a-web-server-publishing-rule-on-the-computer-running-iis-arr"></a>So erstellen Sie eine Webserver-Veröffentlichungsregel auf dem Computer mit IIS Arr

1.  Binden Sie das Zertifikat, das Sie für den Reverseproxy verwenden werden, an das HTTPS-Protokoll. Klicken Sie im **Startmenü**auf **Programme**, wählen Sie **Verwaltung**aus, und klicken Sie dann auf **Internet Information Services (IIS)-Manager**.
    
    <div>
    

    > [!NOTE]  
    > Weitere Hilfe, Screenshots und Anleitungen zur Bereitstellung und Konfiguration von IIS arr finden Sie im NextHop-Artikel <A href="https://go.microsoft.com/fwlink/?linkid=293391">using IIS arr as a Reverse Proxy for lync Server 2013</A>.

    
    </div>

2.  Falls noch nicht geschehen, importieren Sie das Zertifikat, das Sie für den Reverseproxy verwenden werden. Klicken Sie in **Internet Information Services (IIS)-Manager**auf den Namen des Reverse Proxyservers in der linken Größe der Konsole. In der Mitte der Konsole unter **IIS** locate **Server Certificates**. Klicken Sie mit der rechten Maustaste auf **Server Zertifikate** , und wählen Sie **Funktion öffnen**aus.

3.  Klicken Sie auf der rechten Seite der Konsole auf **importieren...**. Geben Sie den Pfad und den Dateinamen des Zertifikats mit der Erweiterung ein, oder klicken Sie auf **...** , um nach dem Zertifikat zu suchen. Wählen Sie das Zertifikat aus, und klicken Sie auf **Öffnen**. Geben Sie das zum Schutz des privaten Schlüssels verwendete Kennwort an (wenn Sie beim Exportieren des Zertifikats und des privaten Schlüssels ein Kennwort zugewiesen haben). Klicken Sie auf **OK**. Wenn der Zertifikatimport erfolgreich war, wird das Zertifikat als Eintrag in der Mitte der Konsole als Eintrag in **Server Zertifikaten**angezeigt.

4.  Weisen Sie das Zertifikat für die Verwendung durch HTTPS zu. Wählen Sie auf der linken Seite der Konsole die **Standard** Website des IIS-Servers aus. Klicken Sie auf der rechten Seite auf **Bindungen...**. Klicken Sie im Dialogfeld **Websitebindungen** auf **hinzufügen.**... Wählen Sie im Dialogfeld **Websitebindung hinzufügen** unter **Typ:** die Option **https**aus. Wenn Sie HTTPS auswählen, können Sie das Zertifikat auswählen, das für HTTPS verwendet werden soll. Wählen Sie unter **SSL-Zertifikat:** das Zertifikat aus, das Sie für den Reverseproxy importiert haben. Klicken Sie auf **OK**. Klicken Sie dann auf **Schließen**. Das Zertifikat ist nun an den Reverseproxy für SSL (Secure Socket Layer) und TLS (Transport Layer Security) gebunden.
    
    <div>
    

    > [!IMPORTANT]  
    > Wenn beim Schließen der Bindungs Dialogfelder, die Zwischenzertifikate fehlen, eine Warnung angezeigt wird, müssen Sie das Zertifikat der öffentlichen Zertifizierungsstellen-Stammzertifizierungsstelle und alle Zwischenzertifizierungsstellen Zertifikate suchen und importieren. Lesen Sie die Anweisungen in der öffentlichen Zertifizierungsstelle, von der Sie Ihr Zertifikat angefordert haben, und befolgen Sie die Anweisungen, um eine Zertifikatkette anzufordern und zu importieren. Wenn Sie das Zertifikat aus Ihrem Edgeserver exportiert haben, können Sie das Zertifikat der Stammzertifizierungsstelle sowie alle Zertifikate der Zwischenzertifizierungsstelle, die dem Edgeserver zugeordnet sind, exportieren. Importieren Sie das Zertifikat der Stammzertifizierungsstelle in den Speicher der vertrauenswürdigen Stammzertifizierungsstellen (nicht mit dem Benutzerspeicher verwechselt) und Zwischenzertifikate in den Speicher der Zwischenzertifizierungsstellen des Computers.

    
    </div>

5.  Klicken Sie auf der linken Seite der Konsole unter dem Namen des IIS-Servers mit der rechten Maustaste auf **Server** Farmen, und klicken Sie dann auf **Serverfarm erstellen...**.
    
    <div>
    

    > [!NOTE]  
    > Wenn der Knoten <STRONG>Server Farmen</STRONG> nicht angezeigt wird, müssen Sie das Routing von Anwendungsanforderungen installieren. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Einrichten von Reverse-Proxyservern für lync Server 2013</A>.

    
    </div>
    
    Geben Sie im Dialogfeld **Serverfarm erstellen** in **Serverfarm Name**den Namen a ein (Dies kann ein Anzeigename zu Identifikationszwecken sein) für die erste URL. Klicken Sie auf **Weiter**.

6.  Geben Sie im Dialogfeld **Server hinzufügen** unter **Serveradresse**den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) der externen Webdienste in Ihrer Front-End-Server ein. Die Namen, die hier zum Beispiel verwendet werden, sind dieselben, die im Planungsabschnitt für den Reverseproxy, die [Zertifikatzusammenfassung-Reverseproxy in lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md)verwendet werden. In Bezug auf die Planung für Reverse-Proxys geben Sie den FQDN ein `webext.contoso.com` . Stellen Sie sicher, dass das Kontrollkästchen neben **Online** aktiviert ist. Klicken Sie auf **Hinzufügen** , um den Server dem Pool von Webservern für diese Konfiguration hinzuzufügen.
    
    <div>
    

    > [!WARNING]  
    > Lync Server verwendet Hardwarelastenausgleichs für die Pool Director-und Front-End-Server für den HTTP-und HTTPS-Datenverkehr. Sie geben nur einen FQDN an, wenn Sie der IIS arr-Server Farm einen Server hinzufügen. Der FQDN ist der Front-End-Server oder Director in Konfigurationen ohne Pool Server oder der vollqualifizierte Domänenname des konfigurierten Hardware Lastenausgleichs für Server Pools. Die einzige unterstützte Methode zum Lastenausgleich von http-und HTTPS-Datenverkehr ist die Verwendung von Hardware-Lastenausgleichsmodulen.

    
    </div>

7.  Klicken Sie im Dialogfeld **Server hinzufügen** auf **Erweiterte Einstellungen...**. Dadurch wird ein Dialogfeld zum Definieren des Anwendungs Anforderungs Routings für Anforderungen an den konfigurierten FQDN geöffnet. Der Zweck besteht darin, den Port, der verwendet wird, wenn die Anforderung von IIS arr verarbeitet wird, neu zu definieren.
    
    Standardmäßig muss der http-Ziel Port als 8080 definiert werden. Klicken Sie auf neben dem aktuellen **Wert von HTTPPort 80** , und legen Sie den Wert auf **8080**fest. Klicken Sie auf neben dem aktuellen **httpsPort 443** , und legen Sie den Wert auf **4443**fest. Lassen Sie den Parameter **Weight** bei 100. Bei Bedarf können Sie Gewichte für eine bestimmte Regel neu definieren, wenn Sie über eine Baseline-Statistik verfügen. Klicken Sie auf **Fertig stellen** , um diesen Teil der Regelkonfiguration abzuschließen.

8.  Möglicherweise werden die Regeln für das Umschreiben von Dialogfeldern angezeigt, die Sie darüber informieren, dass der IIS-Manager eine URL-umschreibungs Regel erstellen kann, um alle eingehenden Anforderungen automatisch an die Serverfarm weiterzuleiten. Klicken Sie auf **Ja**. Sie passen die Regeln manuell an, aber mit Ja wird die Erstkonfiguration festgelegt..

9.  Klicken Sie auf den Namen der Serverfarm, die Sie soeben erstellt haben. Doppelklicken Sie in der Ansicht IIS-Manager-Features unter **Server Farm** auf **Zwischenspeicherung**. Deaktivieren Sie **Datenträgercache aktivieren**. Klicken Sie auf der rechten Seite auf **Apply** .

10. Klicken Sie auf den Namen der Serverfarm. Doppelklicken Sie in der Ansicht IIS-Manager-Features unter **Server Farm** auf **Proxy**. Ändern Sie auf der Seite Proxy Einstellungen den Wert für **Timeout (Sekunden)** in einen Wert, der für Ihre Bereitstellung geeignet ist. Klicken Sie auf über **nehmen** , um die Änderung zu speichern.
    
    <div>
    

    > [!IMPORTANT]  
    > Bei dem Proxy Timeoutwert handelt es sich um eine Zahl, die von der Bereitstellung bis zur Bereitstellung variieren kann. Sie sollten Ihre Bereitstellung überwachen und den Wert für die beste Benutzerfreundlichkeit für Clients ändern. Möglicherweise können Sie den Wert so niedrig wie 200 festlegen. Wenn Sie lync Mobile-Clients in Ihrer Umgebung unterstützen, sollten Sie den Wert auf 960 festlegen, um das Timeout für Push-Benachrichtigungen von Office 365 zu ermöglichen, die einen Timeoutwert von 900 haben. Es ist sehr wahrscheinlich, dass Sie den Timeoutwert verbessern müssen, um zu vermeiden, dass der Client die Verbindung trennt, wenn der Wert zu niedrig ist oder die Zahl verringert, wenn Verbindungen über den Proxy nicht getrennt werden und lange nach dem Trennen des Clients gelöscht werden. Überwachung und Base-Lining Was ist normal für Ihre Umgebung ist das einzig genaue Mittel, um zu bestimmen, wo die richtige Einstellung für diesen Wert ist.

    
    </div>

11. Klicken Sie auf den Namen der Serverfarm. Doppelklicken Sie in der Ansicht IIS-Manager-Features unter **Server Farm** auf **Weiterleitungsregeln**. Deaktivieren Sie im Dialogfeld Routingregeln unter Routing das Kontrollkästchen neben SSL-Verschiebung aktivieren. Wenn die Möglichkeit zum Deaktivieren des Kontrollkästchens nicht verfügbar ist, aktivieren Sie das Kontrollkästchen für **URL-Umschreibung verwenden, um eingehende Anforderungen zu überprüfen**. Klicken Sie auf über **nehmen** , um die Änderungen zu speichern.
    
    <div>
    

    > [!WARNING]  
    > Die SSL-Abladung durch den Reverseproxy wird nicht unterstützt.

    
    </div>

12. Wiederholen Sie die Schritte 5-11 für jede URL, die den Reverseproxy passieren muss. Eine allgemeine Liste wäre Folgendes:
    
      - Externe Front-End-Server-Webdienste: Webext.contoso.com (bereits durch erste Schritte konfiguriert)
    
      - Director-Webdienste extern für Director: webdirext.contoso.com (optional, wenn ein Director bereitgestellt wird)
    
      - Einfache URL Meet: Meet.contoso.com
    
      - Einfache URL Dialin: dialin.contoso.com
    
      - URL für lync AutoErmittlung: lyncdiscover.contoso.com
    
      - Office-webapps-Server-URL: officewebapps01.contoso.com
        
        <div>
        

        > [!IMPORTANT]  
        > Für die URL des Office-webapps-Servers wird eine andere httpsPort-Adresse verwendet. In Schritt 7 definieren Sie die <STRONG>httpsPort</STRONG> als <STRONG>443</STRONG> und <STRONG>Wert von HTTPPort</STRONG> als Port <STRONG>80</STRONG>. Alle anderen Konfigurationseinstellungen sind identisch.

        
        </div>

13. Klicken Sie auf der linken Seite der Konsole auf den Namen des IIS-Servers. Suchen Sie in der Mitte der Konsole unter **IIS**nach **URL-Umschreibung** . Doppelklicken Sie auf URL umschreiben, um die Konfiguration der URL-umschreibungs Regeln zu öffnen. Es sollten Regeln für jede Server Farm angezeigt werden, die Sie in den vorherigen Schritten erstellt haben. Wenn Sie dies nicht tun, vergewissern Sie sich, dass Sie direkt unter dem Knoten **Start Seite** in der Konsole von Internet Informationsserver-Manager auf den Namen des **IIS-Servers** geklickt haben.

14. Im Dialogfeld **URL-Umschreibung** mit Webext.contoso.com als Beispiel ist der vollständige Name der Regel, wie angezeigt wird, **arr \_ Webext.contoso.com \_ Loadbalance \_ SSL**.
    
      - Doppelklicken Sie auf die Regel, um das Dialogfeld **Eingehende Regel bearbeiten** zu öffnen.
    
      - Klicken Sie auf **hinzufügen...** im Dialogfeld **Bedingungen** .
    
      - Geben Sie in der Bedingung **Hinzufügen Bedingung** **Input:** **{http \_ Host}** ein. (Während der Eingabe wird ein Dialogfeld angezeigt, in dem Sie die Bedingung auswählen können). Wählen Sie unter **überprüfen, ob Eingabezeichenfolge:** SELECT mit **dem Muster übereinstimmt**. Geben Sie im **Muster Eingabetyp** ein **\*** . **Fall ignorieren** sollte ausgewählt sein. Klicken Sie auf **OK**.
    
      - Scrollen Sie im Dialogfeld **Eingehende Regel bearbeiten** , um das Dialogfeld **Aktion** zu suchen. **Aktionstyp:** sollte auf **Route zur Server Farm**, **Schema:** auf **https://**, **Serverfarm:** auf die URL festgelegt werden, auf die diese Regel angewendet wird. In diesem Beispiel sollte dies auf **Webext.contoso.com**festgelegt werden. **Path:** ist auf/{R festgelegt **: 0}**
    
      - Klicken Sie auf über **nehmen** , um die Änderungen zu speichern. Klicken Sie auf **Back to Rules** , um zu den Regeln zum Umschreiben von URLs zurückzukehren.

15. Wiederholen Sie das in Schritt 14 definierte Verfahren für alle definierten SSL-umschreibungs Regeln, eine pro Server Farm-URL.
    
    <div>
    

    > [!WARNING]  
    > Standardmäßig werden http-Regeln ebenfalls erstellt und durch die ähnliche Benennung der SSL-Regeln gekennzeichnet. Für unser aktuelles Beispiel würde die HTTP-Regel den Namen <STRONG>ARR_webext. contoso. com _loadbalance</STRONG>. Für diese Regeln sind keine Änderungen erforderlich, und Sie können sicher ignoriert werden.

    
    </div>

</div>

<div>

## <a name="to-modify-the-properties-of-the-web-publishing-rule-in-tmg-2010"></a>So ändern Sie die Eigenschaften der Webveröffentlichungsregel in TMG 2010

1.  Klicken Sie auf **Start**, zeigt auf **Programme**, wählen Sie **Microsoft Forefront TMG**aus, und klicken Sie dann auf **Forefront TMG-Verwaltung**.

2.  Erweitern Sie im linken Bereich **Servername**, und klicken Sie dann auf **Firewall-Richtlinie**.

3.  Klicken Sie im Detailbereich mit der rechten Maustaste auf die Webserververöffentlichungsregel, die Sie im vorherigen Verfahren erstellt haben (beispielsweise LyncServerExternalRule), und klicken Sie dann auf **Eigenschaften**.

4.  Führen Sie auf der Seite **Eigenschaften** auf der Registerkarte von die folgenden Aktionen **aus** :
    
      - Klicken Sie in der Liste **diese Regel gilt für Datenverkehr von diesen Quellen** auf **Anywhere**, und klicken Sie dann auf **Entfernen**.
    
      - Klicken Sie auf **Hinzufügen**.
    
      - Erweitern Sie unter **Netzwerkentitäten hinzufügen**den Knoten **Netzwerke**, klicken Sie auf **extern**, dann auf **Hinzufügen**, und klicken Sie dann auf **Schließen**.

5.  Stellen Sie auf der Registerkarte **an** sicher, dass das Kontrollkästchen **ursprünglichen Hostheader weiterleiten anstelle des tatsächliches** aktiviert ist.

6.  Aktivieren Sie auf der Registerkarte **Überbrückung** das Kontrollkästchen **Anforderung an SSL-Port umleiten** , und geben Sie dann Port **4443**an.

7.  Fügen Sie auf der Registerkarte **Öffentlicher Name** die einfachen URLs hinzu (beispielsweise Meet.contoso.com und dialin.contoso.com).

8.  Klicken Sie auf über **nehmen** , um die Änderungen zu speichern, und klicken Sie dann auf **OK**.

9.  Klicken Sie im Detailbereich auf **Übernehmen**, um die Änderungen zu speichern und die Konfiguration zu aktualisieren.

</div>

<div>

## <a name="to-modify-the-properties-of-the-web-publishing-rule-in-iis-arr"></a>So ändern Sie die Eigenschaften der Webveröffentlichungsregel in IIS-Arr

1.  Klicken Sie im **Startmenü**auf **Programme**, wählen Sie **Verwaltung**aus, und klicken Sie dann auf **Internet Information Services (IIS)-Manager**.

2.  Klicken Sie auf der linken Seite der Konsole auf den Namen des IIS-Servers.

3.  Suchen Sie in der Mitte der Konsole unter **IIS**nach **URL-Umschreibung** . Doppelklicken Sie auf URL umschreiben, um die Konfiguration der URL-umschreibungs Regeln zu öffnen.

4.  Doppelklicken Sie auf die Regel, die Sie ändern müssen. Nehmen Sie Ihre Änderungen bei Bedarf in **übereinstimmender URL**, **Bedingungen**, **Server Variablen** oder **Aktion**vor.

5.  Klicken Sie auf über **nehmen** , um die Änderungen zu bestätigen. Klicken Sie auf **Back to Rules** , um andere Regeln zu ändern, oder schließen Sie die **IIS-Manager-** Konsole, wenn Sie die Änderungen vorgenommen haben.

</div>

</div>

<span> </span>

</div>

</div>

</div>

