---
title: 'Lync Server 2013: Anforderungen für den AutoErmittlungsdienst'
TOCTitle: Anforderungen für den AutoErmittlungsdienst
ms:assetid: 0ac5dbf7-9acd-4d25-b21a-932022b8b983
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Hh690012(v=OCS.15)
ms:contentKeyID: 49293127
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anforderungen für den AutoErmittlungsdienst für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-02-25_

Der Microsoft Lync Server 2013-AutoErmittlungsdienst wird auf Director- und Front-End-Poolservern ausgeführt. Ist der AutoErmittlungsdienst in DNS veröffentlicht, kann er von mobilen Geräten, auf denen Lync Mobile ausgeführt wird, zum Suchen von Mobilitätsdiensten verwendet werden. Bevor mobile Geräte, auf denen Lync Mobile ausgeführt wird, den AutoErmittlungsdienst nutzen können, müssen die Listen mit den alternativen Zertifikatantragstellernamen auf jedem Director und Front-End-Server geändert werden, auf dem der AutoErmittlungsdienst ausgeführt wird. Zudem kann es notwendig sein, die Liste der alternativen Antragstellernamen für Zertifikate zu ändern, die von Veröffentlichungsregeln für externe Webdienste auf Reverseproxys verwendet werden.

Ausführliche Informationen zu den Einträgen für alternative Antragstellernamen, die für Directors, Front-End-Server und Reverseproxys erforderlich sind, finden Sie unter [Technische Anforderungen für die Mobilität in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md) im Abschnitt zur Mobilitätsplanung.

Die Entscheidung, ob auf Reverseproxys alternative Antragstellernamen verwendet werden sollen, basiert darauf, ob Sie den AutoErmittlungsdienst an Port 80 oder an Port 443 veröffentlichen:

  - **Veröffentlicht an Port 80**   Es sind keine Zertifikatänderungen erforderlich, wenn die anfängliche Abfrage des AutoErmittlungsdiensts über den Port 80 erfolgt. Dies ist darauf zurückzuführen, dass mobile Geräte, auf denen Lync ausgeführt wird, extern auf den Reverseproxy an Port 80 zugreifen und dann intern an einen Director oder Front-End-Server an Port 8080 umgeleitet werden. Detaillierte Informationen finden Sie im Abschnitt "Anfänglicher AutoErmittlungsprozess über Port 80" weiter unten in diesem Thema.

  - **Veröffentlicht an Port 443**   Die Liste der alternativen Antragstellennamen für Zertifikate, die von der Veröffentlichungsregel für externe Webdienste verwendet werden, müssen einen *lyncdiscover.\<sipdomain\>* -Eintrag für jede SIP-Domäne in der Organisation enthalten.

Das erneute Ausstellen von Zertifikaten mit einer internen Zertifizierungsstelle ist normalerweise ein einfacher Vorgang. Aber bei öffentlichen Zertifikaten, die für die Webdienst-Veröffentlichungsregel verwendet werden, kann das Hinzufügen mehrerer alternativer Antragstellernamen aufwendig sein. Zur Umgehung dieses Problems wird die anfängliche Verbindung der automatischen Ermittlung über Port 80 unterstützt, die dann an Port 8080 für den Director oder Front-End-Server umgeleitet wird.

Angenommen, ein mobiler Client, auf dem Lync Mobile ausgeführt wird, ist für die Anmeldung an Lync Server 2013 mittels automatischer Ermittlung über HTTP für die erste Anforderung konfiguriert.

## Anfänglicher AutoErmittlungsprozess für mobile Geräte über Port 80

1.  Das mobile Gerät, auf dem Lync Mobile ausgeführt wird, schlägt "lyncdiscover.contoso.com" über DNS nach, wenn ein A-Eintrag vorhanden ist.

2.  Der externe DNS-Eintrag gibt die IP-Adresse für die externen Webdienste an den Client zurück.

3.  Das mobile Gerät, auf dem Lync Mobile ausgeführt wird, sendet die Anforderung "http://lyncdiscover.contoso.com?sipuri=lyncUser1@contoso.com" an den Reverseproxy.

4.  Die Webveröffentlichungsregel überbrückt die Anforderung von Port 80 (extern) an Port 8080 (intern), wodurch sie dann entweder an einen Director- oder Front-End-Server weitergeleitet wird.
    
    Da es sich um eine HTTP- und keine HTTPS-Anforderung handelt, sind keine Änderungen am Zertifikat der Veröffentlichungsregel für externe Webdienste erforderlich, damit der AutoErmittlungsdienst unterstützt wird.

5.  Der AutoErmittlungsdienst gibt die externen Webdienst-URLs (im HTTPS-Format) zurück.

6.  Das mobile Gerät, auf dem Lync Mobile ausgeführt wird, kann dann erneut eine Verbindung mit dem Reverseproxy an Port 443 herstellen und wird dann über Port 4443 an den Mobilitätsdienst umgeleitet, der im Home-Pool des Benutzers ausgeführt wird.
    
    Da die HTTPS-Abfrage an die externe Webdienste-URL und nicht an die AutoErmittlungsdienst-URL gerichtet ist, ist sie erfolgreich, da das Zertifikat bereits Einträge für alternative Antragstellernamen der externen Webdienste-FQDNs enthält.
    
    In diesem Szenario sind zur Unterstützung der Mobilität keine Zertifikatänderungen erforderlich.
    

    > [!NOTE]
    > Wenn der Zielwebserver über ein Zertifikat verfügt, das "lyncdiscover.contoso.com" als alternativen Antragstellernamen enthält:<BR>a.&nbsp;&nbsp;&nbsp;Der Webserver antwortet mit "Server Hello" und ohne Zertifikat.<BR>b.&nbsp;&nbsp;&nbsp;Das mobile Gerät, auf dem Lync Mobile ausgeführt wird, beendet die Sitzung umgehend.<BR>Wenn der Zielwebserver über ein Zertifikat verfügt, das "lyncdiscover.contoso.com" als alternativen Antragstellernamen enthält:<BR>a.&nbsp;&nbsp;&nbsp;Der Webserver antwortet mit "Server Hello" und einem Zertifikat.<BR>b.&nbsp;&nbsp;&nbsp;Das mobile Gerät, auf dem Lync Mobile ausgeführt wird, überprüft das Zertifikat und schließt den Handshake ab.



Zur Unterstützung einer anfänglichen Verbindung mit dem AutoErmittlungsdienst über Port 80 auf dem Reverseproxyserver können Sie eine HTTP-Veröffentlichungsregel erstellen, die dem folgenden Beispiel einer Webveröffentlichungsregel für einen Forefront Threat Management Gateway 2010-Reverseproxy ähnelt:

1.  Erstellen Sie eine neue Webveröffentlichungsregel (beispielsweise **Lync Server-AutoErmittlung (HTTP)** ).

2.  Geben Sie in **Öffentlicher Name** "lyncdiscover.contoso.com" ein.

3.  Wählen Sie auf der Registerkarte **Bridging** nur die Option zum Überbrücken von Anforderungen von Port 80 zu Port 8080 aus.

4.  Wählen Sie auf der Registerkarte **Authentifizierung** die Option **Keine Authentifizierung** und **Keine direkte Authentifizierung des Clients** aus.

5.  Übernehmen Sie die Änderungen, und verschieben Sie die Regel in der Liste der Lync-Regeln nach oben (erste Position in der Verarbeitungsreihenfolge).

## Mobilität für die Bereitstellung geteilter Domänen

Ein freigegebener SIP-Adressraum, auch als *geteilte Domäne* oder *Hybridbereitstellung* bezeichnet, ist eine Konfiguration, bei der Benutzer in einer lokalen Bereitstellung und einer Onlineumgebung bereitgestellt werden. Das Ziel besteht darin, dass ein Benutzer sich unabhängig davon, wo sich sein Homeserver befindet (lokal oder online) bei der Bereitstellung anmeldet und an den Speicherort ihres Homeservers weitergeleitet wird. Dazu wird die AutoErmittlungsfunktion von Microsoft Lync Server 2013 verwendet, um den Onlinebenutzer an die Onlinetopologie weiterzuleiten, indem die AutoErmittlungs-URL mithilfe der Lync Server-Verwaltungsshell und der Cmdlets **Get-CsHostingProvider** und **Set-CsHostingProvider** konfiguriert wird.

Sie müssen folgende bereitgestellte Attribute erfassen und aufzeichnen:

  - Geben Sie Folgendes in der Lync Server-Verwaltungsshell ein:
    
        Get-CsHostingProvider

  - Suchen Sie in den Ergebnissen nach dem Onlineanbieter mit dem Attribut **ProxyFQDN** , z. B. "sipfed.online.lync.com".

  - Zeichnen Sie den Wert von "ProxyFQDN" auf.

  - Aktivieren Sie in der lokalen Lync Server-Systemsteuerung den Partnerverbund, und lassen so einen Partnerverbund mit dem Onlineanbieter zu.

  - Aktivieren Sie den Partnerverbund für den Onlineanbieter. Standardmäßig sind alle Onlinebenutzer für den Domänenverbund aktiviert und können mit allen Domänen kommunizieren.

  - Wenn Sie gesperrte und zulässige Domänen definieren, legen Sie die Domänen fest, die Sie explizit zulassen oder sperren möchten.

  - Für den Onlineverbund müssen Sie Firewallausnahmen, Zertifikate und den DNS-Hosteinträge (A oder AAAA bei Verwendung von IPv6) planen. Außerdem müssen Sie Verbundrichtlinien konfigurieren. Nähere Informationen finden Sie unter [Planen von Lync Server- und Office Communications Server-Partnerverbünden](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)

