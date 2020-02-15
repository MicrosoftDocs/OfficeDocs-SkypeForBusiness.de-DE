---
title: 'Lync Server 2013: Installieren von lync für Windows Phone'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing Lync for Windows Phone
ms:assetid: bf502546-ff69-489f-a92e-a78b58803d53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690996(v=OCS.15)
ms:contentKeyID: 51541513
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 349a4b2609f3b810d0aa64c9e71786f309f21918
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045287"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-lync-for-windows-phone-in-lync-server-2013"></a>Installieren von lync für Windows phone in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-02-03_

Lync 2013 für Windows Phone ist eine Benutzer installierbare Anwendung, die auf dem Windows Phone Marketplace verfügbar ist.

<div>

## <a name="installing-lync-for-windows-mobile"></a>Installieren von Lync für Windows Mobile

Sie können Ihre Benutzer anweisen, lync 2013 für Windows Phone auf Ihren Geräten zu installieren, indem Sie Sie an den <http://go.microsoft.com/fwlink/p/?linkid=231901>Windows Phone Marketplace unterrichten.

</div>

<div>

## <a name="if-you-use-a-dns-srv-record-to-publish-exchange-web-services"></a>Wenn Sie einen DNS-SRV-Eintrag zum Veröffentlichen von Exchange Webdienste verwenden

Um die Exchange-Integration für lync-Clients zu aktivieren, veröffentlichen einige Organisationen die Exchange Webdienste-URL mithilfe eines DNS-SRV-Eintrags. Das Dokument "Understanding and Troubleshooting Exchange Integration", verfügbar im Microsoft Download Center [http://go.microsoft.com/fwlink/?LinkID=391095](http://go.microsoft.com/fwlink/?linkid=391095)unter, beschreibt Szenarien, in denen dies möglicherweise erforderlich ist. Die Exchange-Integration für Windows Phone Benutzer ist in diesem Szenario jedoch nicht funktionsfähig, da die Windows Phone-Plattform keine SRV-Lookups unterstützt. Sie müssen Windows Phone Benutzer anweisen, die Exchange Webdienste-URL anzugeben, anstatt dem Telefon die automatische Erkennung des Servers zu erlauben.

Weisen Sie die Benutzer an, die lync-Einstellungen auf Ihren Windows-Telefonen wie folgt zu konfigurieren:

1.  Wählen Sie in Windows phone in den lync-Einstellungen den Bildschirm **Exchange** aus.

2.  **Automatisches Erkennen von Servern** in **aus**.

3.  Tippen Sie auf das leere Feld, und geben Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) oder die URL für Exchange Webdienste ein.
    
    <div>
    

    > [!NOTE]  
    > Sie können entweder den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) oder die vollständige URL Ihres Exchange Webdienste-Servers angeben. Wenn Sie den FQDN angeben, werden das Protokoll (https://) und der Exchange Webdienste Pfad (/EWS/Exchange.asmx) automatisch hinzugefügt. Wenn Ihr Exchange Webdienste-Pfad unterschiedlich ist, können Sie die vollständige URL angeben.

    
    </div>

4.  Schließen Sie den Bildschirm.

</div>

<div>

## <a name="verifying-mobile-client-installation"></a>Überprüfen der Installation des mobilen Clients

Nachdem Sie den Client konfiguriert und sich erfolgreich angemeldet haben, können Sie anhand der folgenden Tests überprüfen, ob die Installation von lync 2013 auf Ihrem mobilen Gerät ordnungsgemäß funktioniert.

**Suchen nach einem Kontakt im Unternehmensverzeichnis**

1.  Tippen Sie in der Kontaktliste unten auf die Schaltfläche **Suchen**.

2.  Suchen Sie einen Kontakt, der nur in der globalen Adressliste vorhanden ist.

3.  Stellen Sie sicher, dass der Kontaktname in den Suchergebnissen angezeigt wird.

**Testen von Chatnachrichten und Anwesenheitsinformationen**

1.  Tippen Sie in der Kontaktliste auf einen Kontakt.

2.  Tippen Sie in der Visitenkarte auf das Symbol **IM**.

3.  Stellen Sie sicher, dass ein Chatfenster angezeigt wird und Sie ein Chatnachrichten eingeben und senden können.

**Testen der Dial-Out-Konferenz**

1.  Planen Sie in Outlook eine Lync-Besprechung.

2.  Öffnen Sie auf dem mobilen Gerät die Besprechungseinladung.

3.  Klicken Sie in der Besprechung auf den Link, um an der Besprechung teilzunehmen.

4.  Nehmen Sie den Anruf vom Konferenzdienst entgegen, und stellen Sie sicher, dass Sie mit dem Besprechungsaudio verbunden sind.

**Testen von Pushbenachrichtigungen**

1.  Melden Sie sich auf dem mobilen Gerät von Benutzer A bei Lync mit dem Konto des Benutzers A an.

2.  Öffnen Sie eine andere Anwendung auf dem mobilen Gerät.

3.  Melden Sie sich in einem anderen Client mit dem Konto von Benutzer B bei Lync an.

4.  Senden Sie eine Sofortnachricht von Benutzer B an Benutzer A.

5.  Stellen Sie sicher, dass die Sofortnachricht auf dem mobilen Gerät von Benutzer A erscheint.

</div>

</div>

<span> </span>

</div>

</div>

</div>

