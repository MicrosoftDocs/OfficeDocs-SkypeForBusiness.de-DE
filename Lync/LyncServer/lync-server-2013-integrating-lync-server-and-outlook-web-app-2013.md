---
title: 'Lync Server 2013: Integrieren von lync Server und Outlook Web App 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Integrating Lync Server 2013 and Outlook Web App 2013
ms:assetid: 513d4cc7-aa87-4f68-b99d-d58b63bdf242
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688055(v=OCS.15)
ms:contentKeyID: 49733649
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: faa75694ecaac662a643d331a4efdf91b41223e5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725834"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="integrating-microsoft-lync-server-2013-and-microsoft-outlook-web-app-2013"></a>Integrieren von Microsoft lync Server 2013 und Microsoft Outlook Web App 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-03_

Neben der Integration in Microsoft Outlook 2013 kann Microsoft lync Server 2013 vollständig in Microsoft Outlook Web App 2013 integriert werden. Damit werden unter anderem Instant Messaging und Anwesenheitsinformationen zu Outlook Web App hinzugefügt, und Ihre Unified Contact-Liste kann zwischen Outlook Web App und Microsoft lync 2013 freigegeben werden. Um lync Server 2013 und Outlook Web App zu integrieren, müssen Sie zuerst überprüfen, ob die Unified Communications Managed API 4,0-Laufzeit auf dem Microsoft Exchange Server 2013-Back-End-Server installiert ist. Sie können dies tun, indem Sie nach dem vorhanden sein des folgenden Registrierungswerts suchen:

HKEY\_local\_Machine\\System\\CurrentControlSet\\Services\\MSExchange OWA\\instantmessaging\\ImplementationDLLPath

ImplementationDLLPath sollte auf den Speicherort des Ordners für die Datei „Microsoft.Rtc.Internal.Ucweb.dll“ zeigen. Wenn dies nicht der Fall ist, oder wenn der Registrierungswert nicht vorhanden ist, sollten Sie das UCMA-Runtime-Setup-Programm aus dem Microsoft Download Center <http://www.microsoft.com/en-us/download/details.aspx?id=34992>unter herunterladen und installieren. Informationen zum Installieren der UCMA Runtime finden Sie auf derselben Webseite.

**Abwärtskompatibilität**

Lync Server 2013 kann in die Microsoft Exchange Server 2010-Versionen von Unified Messaging und Outlook Web App integriert werden. Weitere Informationen finden Sie im Artikel Bereitstellen von lokalen Exchange um für die Bereitstellung von lync Server 2010- [http://technet.microsoft.com/en-us/library/gg398768.aspx](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)Voicemail. Wenn Sie sich in Exchange 2010 integrieren, verfügen Sie nicht über lync Server-spezifische Features wie den Unified Contact Store und die lync-zu-Exchange-Archivierung.

Microsoft lync 2013 kann auch in Verbindung mit Exchange 2010 und Outlook 2010 verwendet werden. Neue Funktionen wie der Unified Contact Store und Fotos mit hoher Auflösung sind jedoch nicht für lync 2013-Benutzer verfügbar. Diese neuen Funktionen erfordern sowohl lync Server 2013 als auch Exchange 2013.

**Erstellen eines vertrauenswürdigen Anwendungspools für Outlook Web App**

Wenn Sie den Microsoft Exchange Unified Messaging-Anruf Router-Dienst und den Microsoft Exchange Unified Messaging-Dienst auf demselben Computer installiert haben, müssen Sie keinen vertrauenswürdigen Anwendungspool für Outlook Web App erstellen. (Es wird davon ausgegangen, dass der fragliche Server einen SipName um-Wählplan hostet.) Wenn Sie einen einzelnen Computer zum Hosten dieser beiden Dienste verwenden, können Sie zum Abschnitt dieses Dokuments mit dem Titel **Aktivieren von Instant Messaging in Outlook Web App**springen.

Lync Server 2013 kann alle Exchange-Server, die einen SipName um-Wählplan hosten, AutoErmittlung durchführen. Diese Server werden automatisch der Liste der bekannten lync Server-Server hinzugefügt. Es ist nicht erforderlich, einen vertrauenswürdigen Anwendungspool zu erstellen und diese Server der Liste der bekannten Server hinzuzufügen. In der Tat führt dies dazu, dass die Integration von Outlook Web App nicht mehr funktioniert.

<div>


> [!NOTE]  
> Dies ist darauf zurückzuführen, dass die lync Server-Topologie nun über zwei Einträge für denselben Computer verfügt: den automatisch gefundenen Eintrag und den manuell hinzugefügten Eintrag. Sie können dieses Problem beheben und die Funktionsfähigkeit von Outlook Web App wiederherstellen, indem Sie mithilfe der Windows PowerShell den vertrauenswürdigen Pool und die Einträge für vertrauenswürdige Anwendungen vom Server entfernen. Weitere Informationen finden Sie in den Hilfethemen zu den Cmdlets <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplicationPool">Remove-CsTrustedApplicationPool</A> und <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplication">Remove-CsTrustedApplication</A>.



</div>

Wenn diese beiden Dienste auf separaten Computern ausgeführt werden, müssen Sie, nachdem Sie überprüft haben, dass die 4,0-Runtime der Unified Communications-API installiert ist, einen vertrauenswürdigen lync Server-Anwendungspool und eine vertrauenswürdige Anwendung erstellen, die mit Outlook Web App; Dadurch wird der Server der Liste der bekannten Server hinzugefügt. Führen Sie dazu zunächst in der lync Server-Verwaltungsshell einen ähnlichen Befehl wie den folgenden aus:

    New-CsTrustedApplicationPool -Identity atl-owa-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -Site Redmond -RequiresReplication $False

Im vorhergehenden Befehl ist ATL-OWA-001.litwareinc.com der vollqualifizierte Domänenname des Outlook Web App-Pools. Dies muss derselbe Name sein, der in den Feldern "Subject Name" und "Subject Alternative Name (San)" des Zertifikats angezeigt wird, das den Zugriff auf Outlook Web App ermöglicht. Ebenso ist ATL-CS-001.litwareinc.com der vollqualifizierte Domänenname des lync Server 2013-Pools, der den neuen vertrauenswürdigen Anwendungspool hosten soll. Beachten Sie auch, dass die angegebene Website, Redmond, die Website-Nr der lync Server-Website darstellt. Die Website-Nr ist nicht unbedingt mit dem DisplayName der Website identisch; Sie können SiteIDs für Ihre lync Server-Websites abrufen, indem Sie den folgenden Befehl in der lync Server-Verwaltungsshell ausführen:

    Get-CsSite | Select-Object DisplayName, SiteID

Nachdem Sie den vertrauenswürdigen Anwendungspool erstellt haben, konfigurieren Sie mit einem Befehl wie dem folgenden eine Anwendungs-ID sowie einen Port für Outlook Web App:

    New-CsTrustedApplication -ApplicationId OutlookWebApp -TrustedApplicationPoolFqdn atl-owa-001.litwareinc.com  -Port 5199

Bei der ApplicationID im vorherigen Befehl handelt es sich lediglich um einen Anzeigebezeichner zur Unterscheidung vertrauenswürdiger Anwendungen. Die ApplicationID kann eine beliebige Textzeichenfolge ohne Leerzeichen oder andere unzulässige Zeichen sein. (Es wird empfohlen, nur Buchstaben und Ziffern für eine ApplicationID zu verwenden, um Problemen mit der Gültigkeit vorzubeugen.) Die Angabe des Werts für den Portparameter obliegt dem Administrator: Jeder verfügbare Netzwerkport kann verwendet werden.

Nachdem Sie die vertrauenswürdige Anwendung erstellt haben, müssen Sie den folgenden Befehl ausführen, um die Änderungen an ihrer lync Server-Topologie zu aktivieren:

    Enable-CsTopology

Beachten Sie, dass Sie auch Ihren Exchange-Clientzugriffs-und Postfachserver zu allen SIP-URI-Wählplänen hinzufügen müssen. Auf diese Weise werden die Server wiederum als vertrauenswürdige SIP-Peers mit der ExUmRouting-Topologie für lync Server konfiguriert.

**Aktivieren von Chatfunktionen in Outlook Web App**

Wenn lync Server richtig konfiguriert ist, können Sie mit der Konfiguration von Outlook Web App beginnen. Aktivieren Sie dafür zunächst die Chatfunktion in allen virtuellen Verzeichnissen von Outlook Web App auf Ihren Front-End-Servern. (Auf den Back-End-Servern muss die Chatfunktion in virtuellen Verzeichnissen nicht aktiviert werden. In der Tat empfiehlt es sich, keine Chatnachrichten auf ihren Back-End-Servern zu aktivieren.) Sofortnachrichten können auf den Clientzugriffsservern aktiviert werden, indem Sie den folgenden Befehl in der Exchange-Verwaltungsshell ausführen:

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $True -InstantMessagingType OCS

<div>


> [!NOTE]  
> Bei der Installation von Outlook Web App wird die Chatfunktion standardmäßig aktiviert, d. h. die Eigenschaft „InstantMessagingEnabled“ wird auf „True“ festgelegt. Sie müssen dennoch den vorstehenden Befehl ausführen, um den Chattyp auf OCS festzulegen. „InstantMessagingType“ ist standardmäßig auf „None“ festgelegt.



</div>

Als nächstes müssen Sie die folgenden zwei Zeilen zur Outlook Web App Web. config-Datei hinzufügen (diese Datei befindet sich normalerweise\\im Ordner\\C\\: Programm\\Dateien\\Microsoft\\Exchange Server V15 ClientAccess OWA). Diese beiden Zeilen sollten unter dem \<appSettings\> -Knoten in der Datei Web. config hinzugefügt werden, und diese Vorgehensweisesollte nur auf den Back-End-Servern ausgeführt werden, auf denen Outlook Web App installiert wurde:

    <add key="IMCertificateThumbprint" value="EA5A332496CC05DA69B75B66111C0F78A110D22d"/>
    <add key="IMServerName" value="atl-cs-001.litwareinc.com"/>

Im vorhergehenden Beispiel muss der Wert für IMCertificateThumbprint der Fingerabdruck für das Exchange 2013-Zertifikat sein, das auf den Back-End-Servern installiert ist. Sie können diese Informationen abrufen, indem Sie den folgenden Befehl in der Exchange-Verwaltungsshell ausführen:

    Get-ExchangeCertificate

Beachten Sie auch, dass der dem imservername zugewiesene Wert der vollqualifizierte Domänenname des lync Server-Pools ist, in dem Sie den vertrauenswürdigen Anwendungspool für Outlook Web App erstellt haben.

Das Zertifikat, das Sie für Outlook Web App verwenden, muss ein Zertifikat sein, das von lync Server als vertrauenswürdig eingestuft wird. Eine Möglichkeit, um sicherzustellen, dass das Zertifikat sowohl von lync Server als auch von Exchange als vertrauenswürdig eingestuft wird, ist die Verwendung der internen Zertifizierungsstelle zum Erstellen eines Zertifikats auf dem Postfachserver, wobei sichergestellt wird, dass der Server-FQDN für den Antragstellernamen verwendet wird und dieser FQDN in t angezeigt wird. Feld ' alternativer Name ' des Zertifikats Nachdem das Zertifikat erstellt wurde, kann es in Ihre Back-End-Server importiert werden. Das Ergebnis ist, dass dasselbe Zertifikat für zwei Zwecke verwendet wird: 1) Kommunikation zwischen Exchange Unified Messaging und lync Server; und 2) die Integration von Outlook Web App und lync Server.

Nachdem Sie die Datei Web. config aktualisiert haben, sollten Sie den folgenden Befehl auf dem Exchange-Back-End-Server ausführen, um den Outlook Web App-Pool wieder zu verwenden:

    C:\Windows\System32\Inetsrv\Appcmd.exe recycle apppool /apppool.name:"MSExchangeOWAAppPool"

Wenn der Wiederverwendungsvorgang erfolgreich ausgeführt wird, wird in der Exchange-Verwaltungsshell die folgende Meldung angezeigt:

    "MSExchangeOWAAppPool" successfully recycled

**Konfigurieren von Outlook Web App-Postfachrichtlinien**

Nun können Sie mit dem folgenden Befehl die Sofortnachrichtenfunktion in den entsprechenden Postfachrichtlinien von Outlook Web App konfigurieren. Beispielsweise aktiviert der folgende Befehl die Sofortnachrichtenfunktion in der Standardrichtlinie, wenn er auf einem Ihrer Postfachserver ausgeführt wird:

    Set-OwaMailboxPolicy -Identity "Default" -InstantMessagingEnabled $True -InstantMessagingType "OCS"

Und mit dem folgenden Befehl wird die Sofortnachrichtenfunktion für alle Outlook Web App-Postfachrichtlinien aktiviert:

    Get-OwaMailboxPolicy | Set-OwaMailboxPolicy -InstantMessagingEnabled $True -InstantMessagingType "OCS"

Nachdem die Postfachrichtlinie aktiviert wurde, verfügen alle Benutzer, die von dieser Richtlinie verwaltet werden, über eine vollständige Integration zwischen lync Server und Outlook Web App, vorausgesetzt, dass:

  - Der Benutzer verfügt über ein Postfach in Exchange 2013.

  - Der Benutzer wurde für lync Server 2013 aktiviert.

  - Der Benutzer verfügt über eine gültige SIP-Proxyadresse.

**Deaktivieren der Chatfunktion in Outlook Web App**

Wie bereits erwähnt ist die Chatfunktion in Outlook Web App standardmäßig aktiviert. Wenn Sie Outlook Web App nicht in lync Server integrieren, werden Benutzern bei jeder Anmeldung bei Outlook Web App leere anwesenheitssymbole und eine Fehlermeldung angezeigt. Um dieses Problem zu vermeiden, verwenden Sie den folgenden Befehl der Exchange-Verwaltungsshell, um Chatnachrichten in Outlook Web App zu deaktivieren:

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $False

**Überprüfen der Integration in Outlook Web App**

Um die Integration der Chat- und Anwesenheitsfunktion in Outlook Web App zu überprüfen, melden Sie sich bei Outlook Web App 2013 an. Oben rechts im Bildschirm ist Ihr Exchange-Anzeigename zu sehen. Wenn neben Ihrem Namen ein Anwesenheitssymbol angezeigt wird (beispielsweise ein grünes Symbol, das angibt, dass Ihr aktueller Status verfügbar ist), der angibt, dass Sie lync Server und Outlook Web App erfolgreich integriert haben.

Überprüfen Sie nach der ersten Anmeldung an Outlook Web App, ob ein Ereignis mit der ID 112 (und der Quelle „MSExchange OWA“) in das Ereignisprotokoll auf dem Postfachserver geschrieben wurde. Das Ereignis zeigt an, dass der Instant Messaging Endpoint Manager erfolgreich initialisiert wurde. Wenn Instant Messaging nicht zu funktionieren scheint, suchen Sie auf dem Postfachserver nach Protokolldateien in dem Ordner\\C: Programmdateien\\Microsoft\\Exchange Server\\V15\\Protokollierung\\von OWA\\-instantmessaging. Wenn der Ordner „Logging“ oder der Ordner „InstantMessaging“ nicht vorhanden ist, deutet dies darauf hin, dass die Integration fehlgeschlagen ist. In diesem Fall können Sie die SIPStack-Ablaufverfolgung auf lync Server (alle Ebenen und alle Flags) verwenden, um zu versuchen, zu ermitteln, warum die Integration fehlgeschlagen ist.

</div>

<span> </span>

</div>

</div>

</div>

