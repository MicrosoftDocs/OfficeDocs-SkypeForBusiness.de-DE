---
title: 'Lync Server 2013: Integrieren von lync Server und Outlook Web App 2013'
description: 'Lync Server 2013: Integrieren von lync Server und Outlook Web App 2013.'
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
ms.openlocfilehash: 0d9c7e91dba22f78325eaddc5b5d7469ccf4cc92
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567391"
---
# <a name="integrating-microsoft-lync-server-2013-and-microsoft-outlook-web-app-2013"></a>Integrieren von Microsoft lync Server 2013 und Microsoft Outlook Web App 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-03_

Zusätzlich zur Integration mit Microsoft Outlook 2013 kann Microsoft lync Server 2013 vollständig in Microsoft Outlook Web App 2013 integriert werden; Dadurch werden Outlook Web App unter anderem Sofortnachrichten und Anwesenheitsinformationen hinzugefügt, und es ist möglich, dass ihre einheitliche Kontaktliste zwischen Outlook Web App und Microsoft lync 2013 freigegeben wird. Um lync Server 2013 und Outlook Web App zu integrieren, müssen Sie zunächst sicherstellen, dass die Unified Communications verwaltete API 4,0-Laufzeit auf dem Microsoft Exchange Server 2013-Back-End-Server installiert wurde. Sie können dies tun, indem Sie nach dem vorhanden sein des folgenden Registrierungswerts suchen:

HKEY \_ local \_ Machine \\ System \\ CurrentControlSet \\ Services \\ MSExchange OWA \\ instantmessaging \\ ImplementationDLLPath

Das ImplementationDLLPath-Argument sollte auf den Speicherort des Ordners für die Datei Microsoft.Rtc.Internal.Ucweb.dll. Wenn dies nicht der Fall ist, oder wenn der Registrierungswert nicht vorhanden ist, sollten Sie das Setupprogramm für die UCMA-Laufzeit im Microsoft Download Center unter herunterladen und installieren <https://www.microsoft.com/download/details.aspx?id=34992> . Informationen zum Installieren der UCMA-Laufzeit finden Sie auf derselben Webseite.

**Abwärtskompatibilität**

Lync Server 2013 können in die Microsoft Exchange Server 2010 Versionen von Unified Messaging und Outlook Web App integriert werden. Weitere Informationen finden Sie im Artikel Deploying on-premises Exchange um to bereitstellen lync Server 2010 Voice Mail at [https://technet.microsoft.com/library/gg398768.aspx](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md) . Wenn Sie in Exchange 2010 integrieren, verfügen Sie nicht über lync Server spezifische Features wie den einheitlichen Kontaktspeicher und die lync-zu-Exchange-Archivierung.

Microsoft lync 2013 kann auch in Verbindung mit Exchange 2010 und Outlook 2010 verwendet werden. Allerdings sind neue Funktionen wie der einheitliche Kontaktspeicher und Fotos mit hoher Auflösung für lync 2013 Benutzer nicht verfügbar. Diese neuen Funktionen erfordern sowohl lync Server 2013 als auch Exchange 2013.

**Erstellen eines vertrauenswürdigen Anwendungspools für Outlook Web App**

Wenn Sie den Microsoft Exchange Unified Messaging-Anruf Routerdienst und den Microsoft Exchange Unified Messaging-Dienst auf demselben Computer installiert haben, ist es nicht erforderlich, einen vertrauenswürdigen Anwendungspool für Outlook Web App zu erstellen. (Dies setzt voraus, dass der fragliche Server einen SipName um-Wählplan hostet.) Wenn Sie einen einzelnen Computer verwenden, um beide Dienste zu hosten, können Sie zum Abschnitt mit dem Titel **Aktivieren von Chat in Outlook Web App**springen.

Lync Server 2013 können alle Exchange-Server AutoErmittlung, die einen SipName-um-Wählplan hosten; Diese Server werden automatisch der Liste lync Server bekannte Server hinzugefügt. Es ist nicht erforderlich, einen vertrauenswürdigen Anwendungspool zu erstellen und diese Server der Liste der bekannten Server hinzuzufügen. Dies führt dazu, dass Outlook Web App Integration nicht mehr funktioniert.

<div>


> [!NOTE]  
> Dies liegt daran, dass die lync Server Topologie nun über zwei Einträge für denselben Computer verfügt: den automatisch entdeckten Eintrag und den manuell hinzugefügten Eintrag. Um das Problem zu beheben und Outlook Web App wieder funktionsfähig zu machen, verwenden Sie Windows PowerShell, um den vertrauenswürdigen Pool und die Einträge der vertrauenswürdigen Anwendung für den Server zu entfernen. Weitere Informationen finden Sie in den Hilfethemen zu den Cmdlets <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplicationPool">Remove-CsTrustedApplicationPool</A> und <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplication">Remove-CsTrustedApplication</A> .



</div>

Wenn diese beiden Dienste auf separaten Computern ausgeführt werden, müssen Sie, nachdem Sie überprüft haben, dass die Unified Communications verwaltete API 4,0-Laufzeit installiert wurde, einen lync Server vertrauenswürdigen Anwendungspool und eine vertrauenswürdige Anwendung erstellen, die Outlook Web App zugeordnet ist. Dadurch wird der Server der Liste der bekannten Server hinzugefügt. Führen Sie dazu zunächst einen Befehl aus dem lync Server-Verwaltungsshell aus, der dem folgenden ähnelt:

    New-CsTrustedApplicationPool -Identity atl-owa-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -Site Redmond -RequiresReplication $False

Im vorherigen Befehl ist ATL-OWA-001.litwareinc.com der vollqualifizierte Domänenname des Outlook Web App Pools; Dies muss derselbe Name sein, der in den Feldern Antragstellername und alternativer Antragstellername (San) des Zertifikats angezeigt wird, das den Zugriff auf Outlook Web App ermöglicht. Ebenso ist ATL-CS-001.litwareinc.com der vollqualifizierte Domänenname des lync Server 2013 Pools, der den neuen vertrauenswürdigen Anwendungspool hosten wird. Beachten Sie auch, dass die angegebene Website, Redmond, die Website-Nr der lync Server Website darstellt. Die Website-Nr ist nicht unbedingt identisch mit dem DisplayName der Website; Sie können SiteIDs für Ihre lync Server Websites abrufen, indem Sie den folgenden Befehl aus dem lync Server-Verwaltungsshell ausführen:

    Get-CsSite | Select-Object DisplayName, SiteID

Verwenden Sie nach dem Erstellen des vertrauenswürdigen Anwendungspools einen Befehl wie den folgenden, um eine Anwendungsidentität und einen Port für Outlook Web App zu konfigurieren:

    New-CsTrustedApplication -ApplicationId OutlookWebApp -TrustedApplicationPoolFqdn atl-owa-001.litwareinc.com  -Port 5199

Bei der ApplicationID im vorangehenden Befehl handelt es sich lediglich um einen Anzeigebezeichner zur Unterscheidung vertrauenswürdiger Anwendungen. Die ApplicationID kann eine beliebige Textzeichenfolge ohne Leerzeichen oder andere unzulässige Leerzeichen sein. (Es wird empfohlen, nur Buchstaben und Ziffern für eine ApplicationID zu verwenden, um Problemen mit der Gültigkeit vorzubeugen.) Die Angabe des Werts für den Portparameter obliegt dem Administrator: Jeder verfügbare Netzwerkport kann verwendet werden.

Nachdem Sie die vertrauenswürdige Anwendung erstellt haben, müssen Sie den folgenden Befehl ausführen, um die Änderungen an ihrer lync Server Topologie zu aktivieren:

    Enable-CsTopology

Beachten Sie, dass Sie auch Ihren Exchange-Clientzugriffs-und Postfachserver zu allen SIP-URI-Wählplänen hinzufügen müssen. Auf diese Weise werden die Server wiederum als vertrauenswürdige SIP-Peers mit der ExUmRouting-Topologie für lync Server konfiguriert.

**Aktivieren von Chatnachrichten auf Outlook Web App**

Wenn lync Server ordnungsgemäß konfiguriert ist, können Sie mit der Konfiguration von Outlook Web App beginnen. Der erste Schritt in diesem Prozess besteht darin, Chatnachrichten auf allen virtuellen Outlook Web App-Verzeichnissen auf Ihren Front-End-Servern zu aktivieren. (Es ist nicht erforderlich, Chatnachrichten für die virtuellen Verzeichnisse auf ihren Back-End-Servern zu aktivieren. Es wird daher empfohlen, dass Sie keine Chatnachrichten auf ihren Back-End-Servern aktivieren.) Chatnachrichten können auf den Clientzugriffsservern aktiviert werden, indem Sie den folgenden Befehl in der Exchange-Verwaltungsshell ausführen:

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $True -InstantMessagingType OCS

<div>


> [!NOTE]  
> Standardmäßig ist Instant Messaging bei der Installation von Outlook Web App aktiviert. Das heißt, die InstantMessagingEnabled-Eigenschaft ist auf true festgelegt. Sie müssen jedoch weiterhin den vorherigen Befehl ausführen, um den Instant Messaging-Typ auf OCS festzulegen. Standardmäßig ist InstantMessagingType auf None festgelegt.



</div>

Als nächstes müssen Sie die folgenden zwei Zeilen zu Outlook Web App Web.config Datei hinzufügen (diese Datei befindet sich in der Regel im Ordner C: \\ Programmdateien \\ Microsoft \\ Exchange Server \\ V15 \\ Client Access \\ OWA). Diese beiden Zeilen sollten unter dem \<AppSettings\> Knoten in der Web.config Datei hinzugefügt werden, und dieses Verfahren sollte nur auf den Back-End-Servern ausgeführt werden, auf denen Outlook Web App installiert wurde:

    <add key="IMCertificateThumbprint" value="EA5A332496CC05DA69B75B66111C0F78A110D22d"/>
    <add key="IMServerName" value="atl-cs-001.litwareinc.com"/>

Im vorherigen Beispiel muss der Wert für IMCertificateThumbprint der Fingerabdruck für das Exchange 2013 Zertifikat sein, das auf den Back-End-Servern installiert ist. Sie können diese Informationen abrufen, indem Sie den folgenden Befehl aus dem Exchange-Verwaltungsshell ausführen:

    Get-ExchangeCertificate

Beachten Sie auch, dass der dem imservername zugewiesene Wert der vollqualifizierte Domänenname des lync Server Pools ist, in dem Sie den vertrauenswürdigen Anwendungspool für Outlook Web App erstellt haben.

Das Zertifikat, das Sie für Outlook Web App verwenden, muss ein Zertifikat sein, das von lync Server als vertrauenswürdig eingestuft wird. Eine Möglichkeit, sicherzustellen, dass das Zertifikat sowohl von lync Server als auch von Exchange als vertrauenswürdig eingestuft wird, ist die Verwendung der internen Zertifizierungsstelle, um ein Zertifikat auf dem Postfachserver zu erstellen, damit sichergestellt ist, dass der Server-FQDN für den Antragstellernamen verwendet wird und dass dieser FQDN im Feld Alternativer Zertifikatsname angezeigt wird. Nachdem das Zertifikat erstellt wurde, kann es auf die Back-End-Server importiert werden. Das Ergebnis ist, dass das gleiche Zertifikat für zwei Zwecke verwendet wird: 1) Kommunikation zwischen Exchange Unified Messaging und lync Server; und 2) die Integration zwischen Outlook Web App und lync Server.

Nachdem Sie die Web.config Datei aktualisiert haben, sollten Sie den folgenden Befehl auf dem Exchange-Back-End-Server ausführen, um den Outlook Web App-Pool wiederzuverwenden:

    C:\Windows\System32\Inetsrv\Appcmd.exe recycle apppool /apppool.name:"MSExchangeOWAAppPool"

Wenn der Wiederverwendungsvorgang erfolgreich ist, wird die folgende Meldung im Exchange-Verwaltungsshell angezeigt:

    "MSExchangeOWAAppPool" successfully recycled

**Konfigurieren Outlook Web App Postfachrichtlinien**

An dieser Position können Sie den folgenden Befehl verwenden, um Chatnachrichten für die entsprechende Outlook Web App Postfachrichtlinie (oder Richtlinien) zu konfigurieren. Dieser Befehl, der beispielsweise auf einem ihrer Postfachserver ausgeführt wird, aktiviert Chatnachrichten in der Standardrichtlinie:

    Set-OwaMailboxPolicy -Identity "Default" -InstantMessagingEnabled $True -InstantMessagingType "OCS"

Mit diesem Befehl wird Instant Messaging für alle Outlook Web App Postfachrichtlinien aktiviert:

    Get-OwaMailboxPolicy | Set-OwaMailboxPolicy -InstantMessagingEnabled $True -InstantMessagingType "OCS"

Nachdem die Postfachrichtlinie aktiviert wurde, haben alle Benutzer, die mit dieser Richtlinie verwaltet werden, eine vollständige Integration zwischen lync Server und Outlook Web App, vorausgesetzt:

  - Der Benutzer verfügt über ein Postfach auf Exchange 2013.

  - Der Benutzer wurde für lync Server 2013 aktiviert.

  - Der Benutzer verfügt über eine gültige SIP-Proxyadresse.

**Deaktivieren von Chatnachrichten in Outlook Web App**

Wie bereits erwähnt, ist Instant Messaging in Outlook Web App standardmäßig aktiviert. Das heißt, wenn Sie Outlook Web App nicht mit lync Server integrieren, werden Benutzern bei jeder Anmeldung bei Outlook Web App leere anwesenheitssymbole und eine Fehlermeldung angezeigt. Um dieses Problem zu vermeiden, verwenden Sie den folgenden Exchange-Verwaltungsshell Befehl, um Chatnachrichten in Outlook-webapp zu deaktivieren:

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $False

**Überprüfen der Integration in Outlook Web App**

Um zu überprüfen, ob Chatnachrichten und Anwesenheitsinformationen in Outlook Web App integriert wurden, melden Sie sich bei Outlook Web App 2013 an. Oben rechts im Bildschirm wird Ihr Exchange-Anzeigename dargestellt. Wenn neben Ihrem Namen ein Anwesenheitssymbol vorhanden ist (beispielsweise ein grünes Symbol, das angibt, dass Ihr aktueller Status verfügbar ist), der angibt, dass Sie lync Server und Outlook Web App erfolgreich integriert haben.

Überprüfen Sie nach der anfänglichen Anmeldung bei Outlook Web App, ob ein Ereignis mit der Ereignis-ID 112 (und der Quelle MSExchange OWA) in das Ereignisprotokoll auf dem Postfachserver geschrieben wurde. Dieses Ereignis weist darauf hin, dass der Instant Messaging-Endpunkt-Manager erfolgreich initialisiert wurde. Wenn Chatnachrichten nicht zu funktionieren scheinen, suchen Sie auf dem Postfachserver nach Protokolldateien im Ordner C: \\ Programmdateien \\ Microsoft \\ Exchange Server \\ V15 \\ Logging \\ OWA \\ instantmessaging. Wenn die Protokollierung oder die instantmessaging Ordner nicht vorhanden sind, gibt an, dass die Integration fehlgeschlagen ist. In diesem Fall können Sie die SIPStack-Ablaufverfolgung für lync Server (alle Ebenen und alle Flags) verwenden, um zu versuchen, zu ermitteln, warum die Integration fehlgeschlagen ist.

</div>

<span> </span>

</div>

</div>

</div>

