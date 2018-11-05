---
title: Integrieren von Microsoft Lync Server 2013 und Microsoft Outlook Web App 2013
TOCTitle: Integrieren von Microsoft Lync Server 2013 und Microsoft Outlook Web App 2013
ms:assetid: 513d4cc7-aa87-4f68-b99d-d58b63bdf242
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688055(v=OCS.15)
ms:contentKeyID: 49890747
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Integrieren von Microsoft Lync Server 2013 und Microsoft Outlook Web App 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Neben Microsoft Outlook 2013 kann Microsoft Lync Server 2013 auch vollständig in Microsoft Outlook Web App 2013 integriert werden. Dadurch werden Outlook Web App u. a. Chat- und Anwesenheitsfunktionen hinzugefügt, und Ihre einheitliche Kontaktliste kann in Outlook Web App und Microsoft Lync 2013 gemeinsam verwendet werden. Wenn Sie Lync Server 2013 in Outlook Web App integrieren möchten, müssen Sie zunächst sicherstellen, dass die Unified Communications Managed API 4.0 Runtime auf Ihrem Microsoft Exchange Server 2013-Back-End-Server installiert ist. Überprüfen Sie zu diesem Zweck, ob der folgende Registrierungswert vorhanden ist:

HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\MSExchange OWA\\InstantMessaging\\ImplementationDLLPath

ImplementationDLLPath sollte auf den Speicherort des Ordners für die Datei "Microsoft.Rtc.Internal.Ucweb.dll" zeigen. Andernfalls, oder wenn der Registrierungswert nicht vorhanden ist, sollten Sie das Setupprogramm für die UCMA Runtime aus dem Microsoft Download Center unter <http://www.microsoft.com/de-de/download/details.aspx?id=34992> herunterladen und installieren. Informationen zum Installieren der UCMA Runtime befinden sich auf derselben Webseite.

**Abwärtskompatibilität**

Lync Server 2013 kann in die Microsoft Exchange Server 2010-Versionen von Unified Messaging und Outlook Web App integriert werden. Weitere Informationen finden Sie im Artikel "Bereitstellen lokaler Exchange Unified Messaging-Dienste zur Unterstützung von Lync Server 2010-Voicemail" unter [http://technet.microsoft.com/de-de/library/gg398768.aspx](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md). Bei einer Integration in Exchange 2010 stehen Ihnen Lync Server-spezifische Features wie z. B. der einheitliche Kontaktspeicher und die Lync-zu-Exchange-Archivierung nicht zur Verfügung.

Microsoft Lync 2013 kann auch in Verbindung mit Exchange 2010 und Outlook 2010 verwendet werden. Auch in diesem Fall sind jedoch neue Funktionen wie der einheitliche Kontaktspeicher und hochauflösende Fotos für Lync 2013-Benutzer nicht verfügbar. Diese neuen Funktionen erfordern sowohl Lync Server 2013 als auch Exchange 2013.

**Erstellen eines vertrauenswürdigen Anwendungspools für Outlook Web App**

Wenn Sie den Microsoft Exchange Unified Messaging-Anrufrouterdiensts und den Microsoft Exchange Unified Messaging-Dienst auf demselben Computer installiert haben, muss für Outlook Web App kein vertrauenswürdiger Anwendungspool erstellt werden. (Dies setzt voraus, dass der betreffende Server einen SipName-UM-Wählplan hostet.) Wenn Sie diese beiden Dienste auf demselben Computer hosten, können Sie den Abschnitt **Aktivieren von Chatfunktionen in Outlook Web App** dieses Dokuments überspringen.

Lync Server 2013 ermittelt automatisch alle Exchange-Server, die einen SipName-UM-Wählplan hosten. Diese Server werden automatisch der Lync Server-Liste der bekannte Server hinzugefügt. Das Erstellen eines vertrauenswürdigen Anwendungspools und das Hinzufügen dieser Server zur Liste der bekannten Server ist nicht erforderlich. Im Gegenteil: Danach würde die Outlook Web App-Integration nicht mehr funktionieren.


> [!NOTE]
> Dies ist darauf zurückzuführen, dass die Lync Server-Topologie dann zwei Einträge für denselben Computer enthält: den automatisch ermittelten und den manuell hinzugefügten Eintrag. Um dieses Problem zu beheben und die Funktionsfähigkeit von Outlook Web App wiederherzustellen verwenden Sie die Windows PowerShell, um den vertrauenswürdigen Pool und die Einträge für vertrauenswürdige Anwendungen vom Server zu entfernen. Weitere Informationen finden Sie in den Hilfethemen zu den Cmdlets <A href="https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrustedApplicationPool">Remove-CsTrustedApplicationPool</A> und <A href="https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrustedApplication">Remove-CsTrustedApplication</A>.



Wenn diese beiden Dienste auf verschiedenen Computern ausgeführt werden und Sie sich vergewissert haben, dass die Unified Communications Managed API 4.0 Runtime installiert wurde, müssen Sie einen vertrauenswürdigen Lync Server-Anwendungspool sowie eine vertrauenswürdige Anwendung erstellen, die mit Outlook Web App verknüpft sind; dadurch wir der Server der Liste der bekannten Server hinzugefügt. Führen Sie dazu zuerst einen Befehl wie den folgenden in derLync Server-Verwaltungsshell aus:

    New-CsTrustedApplicationPool -Identity atl-owa-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -Site Redmond -RequiresReplication $False

"atl-owa-001.litwareinc.com" ist der vollqualifizierte Domänenname des Outlook Web App-Pools aus dem vorangehenden Befehl. Er muss mit dem Namen übereinstimmen, der in den Feldern "Antragstellername" und "Alternativer Antragstellername" des Zertifikats für den Zugriff auf Outlook Web App eingetragen ist. Analog dazu entspricht "atl-cs-001.litwareinc.com" dem vollqualifizierten Domänennamen des Lync Server 2013-Pools, in dem der neue vertrauenswürdige Anwendungspool gehostet wird. Beachten Sie außerdem, dass der angegebene Standort, Redmond, der Standort-ID von Lync Server entspricht. Diese Standort-ID stimmt nicht unbedingt mit dem Anzeigenamen des Standorts überein. Sie können die Standort-IDs für Ihre Lync Server-Standorte abrufen, indem Sie den folgenden Befehl in Lync Server-Verwaltungsshell ausführen:

    Get-CsSite | Select-Object DisplayName, SiteID

Nachdem Sie den vertrauenswürdigen Anwendungspool erstellt haben, konfigurieren Sie mit einem Befehl wie dem folgenden eine Anwendungs-ID sowie einen Port für Outlook Web App:

    New-CsTrustedApplication -ApplicationId OutlookWebApp -TrustedApplicationPoolFqdn atl-owa-001.litwareinc.com  -Port 5199

Bei der ApplicationID im vorangehenden Befehl handelt es sich lediglich um einen Anzeigebezeichner zur Unterscheidung vertrauenswürdiger Anwendungen. Die ApplicationID kann eine beliebige Textzeichenfolge ohne Leerzeichen oder andere unzulässige Leerzeichen sein. (Es wird empfohlen, nur Buchstaben und Ziffern für eine ApplicationID zu verwenden, um Problemen mit der Gültigkeit vorzubeugen.) Die Angabe des Werts für den Portparameter obliegt dem Administrator: Jeder verfügbare Netzwerkport kann verwendet werden.

Im Anschluss an das Erstellen der vertrauenswürdigen Anwendung müssen Sie den folgenden Befehl ausführen, damit die Änderungen an Ihrer Lync Server-Topologie wirksam werden:

    Enable-CsTopology

Beachten Sie, dass Sie allen SIP-URI-Wählplänen auch Ihren Exchange-Clientzugriff und den Postfachserver hinzufügen müssen. Dadurch wiederum werden die Server als vertrauenswürdige SIP-Peers mit der ExUmRouting-Topologie für Lync Server konfiguriert.

**Aktivieren von Chatfunktionen in Outlook Web App**

Lync Server ist nun ordnungsgemäß konfiguriert, und Sie können mit dem Konfigurieren von Outlook Web App beginnen. Dazu aktivieren Sie zunächst die Chatfunktion in allen virtuellen Verzeichnissen von Outlook Web App auf Ihren Front-End-Servern. (Auf den Back-End-Servern muss die Chatfunktion in virtuellen Verzeichnissen nicht aktiviert werden. Es wird sogar empfohlen, sie nicht zu aktivieren.) Die Chatfunktion kann auf den Clientzugriffsservern aktiviert werden, indem in der Exchange-Verwaltungsshell folgender Befehl ausgeführt wird:

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $True -InstantMessagingType OCS


> [!NOTE]
> Bei der Installation von Outlook Web App wird die Chatfunktion standardmäßig aktiviert, d.&nbsp;h. die Eigenschaft "InstantMessagingEnabled" wird auf "True" festgelegt. Sie müssen dennoch den vorstehenden Befehl ausführen, um den Chattyp auf OCS festzulegen. "InstantMessagingType" ist standardmäßig auf "None" festgelegt.



Als Nächstes müssen Sie der Web.config-Datei von Outlook Web App (die sich i. d. R. im Ordner "C:\\Programme\\Microsoft\\Exchange Server\\V15\\ClientAccess\\Owa" befindet) zwei Zeilen hinzufügen. Diese beiden Zeilen sollten unter dem Knoten "\<AppSettings\>" in der Datei "Web.config" hinzugefügt werden. Dieses Verfahren sollte nur auf den Back-End-Servern ausgeführt werden, auf denen Outlook Web App installiert ist:

    <add key="IMCertificateThumbprint" value="EA5A332496CC05DA69B75B66111C0F78A110D22d"/>
    <add key="IMServerName" value="atl-cs-001.litwareinc.com"/>

Im vorangehenden Beispiel muss der Wert von IMCertificateThumbprint dem Fingerabdruck des Exchange 2013-Zertifikats entsprechen, das auf Ihren Back-End-Servern installiert ist. Sie können diese Informationen abrufen, indem Sie den folgenden Befehl in der Exchange-Verwaltungsshell ausführen:

    Get-ExchangeCertificate

Darüber hinaus entspricht der IMServerName zugewiesene Wert dem vollqualifizierten Domänennamen des Lync Server-Pools, in dem Sie den vertrauenswürdigen Anwendungspool für Outlook Web App erstellt haben.

Lync Server muss dem Zertifikat vertrauen, das für Outlook Web App verwendet wird. Eine Möglichkeit zum Sicherstellen, dass sowohl Lync Server als auch Exchange dem Zertifikat vertrauen, ist das Verwenden der internen Zertifizierungsstelle zum Erstellen eines Zertifikats auf dem Postfachserver. Dabei muss der Server-FQDN als Antragstellernamen verwendet werden und auch im Feld "Alternativer Antragstellername" des Zertifikats angegeben werden. Nachdem das Zertifikat erstellt wurde, kann es auf Ihren Back-End-Servern importiert werden. Dies führt letztendlich dazu, das dasselbe Zertifikat für zwei Zwecke verwendet wird: 1) Kommunikation zwischen Exchange Unified Messaging und Lync Server; und, 2) die Integration von Outlook Web App in Lync Server.

Nachdem Sie die Web.config-Datei aktualisiert haben, müssen Sie den folgenden Befehl auf dem Exchange-Back-End-Server ausführen, um den Outlook Web App-Pool wiederzuverwenden:

    C:\Windows\System32\Inetsrv\Appcmd.exe recycle apppool /apppool.name:"MSExchangeOWAAppPool"

Wenn der Wiederherstellungsvorgang erfolgreich war, wird die folgende Meldung in der Exchange-Verwaltungsshell angezeigt:

    "MSExchangeOWAAppPool" successfully recycled

**Konfigurieren von Outlook Web App-Postfachrichtlinien**

Nun können Sie mit dem folgenden Befehl die Sofortnachrichtenfunktion in den entsprechenden Postfachrichtlinien von Outlook Web App konfigurieren. Beispielsweise aktiviert der folgende Befehl die Sofortnachrichtenfunktion in der Standardrichtlinie, wenn er auf einem Ihrer Postfachserver ausgeführt wird:

    Set-OwaMailboxPolicy -Identity "Default" -InstantMessagingEnabled $True -InstantMessagingType "OCS"

Und mit dem folgenden Befehl wird die Sofortnachrichtenfunktion für alle Outlook Web App-Postfachrichtlinien aktiviert:

    Get-OwaMailboxPolicy | Set-OwaMailboxPolicy -InstantMessagingEnabled $True -InstantMessagingType "OCS"

Sobald die Postfachrichtlinie aktiviert wurde, sind alle Benutzer, die durch diese Richtlinie verwaltet werden, vollständig in Lync Server und Outlook Web App integriert, wenn folgende Voraussetzungen erfüllt sind:

  - Der Benutzer verfügt über ein Postfach in Exchange 2013.

  - Der Benutzer wurde für Lync Server 2013 aktiviert.

  - Der Benutzer verfügt über eine gültige SIP-Proxyadresse.

**Deaktivieren der Chatfunktion in Outlook Web App**

Wie bereits erwähnt ist die Chatfunktion in Outlook Web App standardmäßig aktiviert. Das bedeutet, dass Benutzern bei jeder Anmeldung an Outlook Web App leere Anwesenheitssymbole und eine Fehlermeldung angezeigt werden, wenn Sie Outlook Web App nicht in Lync Server integrieren. Um dieses Problem zu vermeiden, verwenden Sie den folgenden Exchange.Verwaltungsshell-Befehl, um die Chatfunktion in Outlook Web App zu deaktivieren:

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $False

**Überprüfen der Integration in Outlook Web App**

Um die Integration der Chat- und Anwesenheitsfunktion in Outlook Web App zu überprüfen, melden Sie sich bei Outlook Web App 2013 an. Oben rechts im Bildschirm ist Ihr Exchange-Anzeigename zu sehen. Wenn neben Ihrem Namen ein Anwesenheitssymbol vorhanden ist (z. B. ein grünes Symbol, das Ihren aktuellen Status als "verfügbar" kennzeichnet) haben Sie Lync Server erfolgreich in Outlook Web App integriert.

Überprüfen Sie nach der ersten Anmeldung an Outlook Web App, ob ein Ereignis mit der ID 112 (und der Quelle "MSExchange OWA") in das Ereignisprotokoll auf dem Postfachserver geschrieben wurde. Das Ereignis zeigt an, dass der Instant Messaging Endpoint Manager wurde erfolgreich initialisiert wurde. Funktioniert der Chat dennoch nicht, suchen Sie auf dem Postfachserver nach Protokolldateien im Ordner "C:\\Program Files\\Microsoft\\Exchange server\\V15\\Logging\\OWA\\InstantMessaging". Wenn der Ordner "Logging" oder der Ordner "InstantMessaging" nicht vorhanden ist, deutet dies darauf hin, das die Integration fehlgeschlagen ist. In diesem Fall können Sie mithilfe der SIPStack-Verfolgung in Lync Server (alle Ebenen und alle Kennzeichen) versuchen, die Ursache für das Fehlschlagen der Integration zu ermitteln.

