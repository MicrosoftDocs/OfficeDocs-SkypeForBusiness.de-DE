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
ms.openlocfilehash: 75e42f9fd2b954e943050fc9877706ae53a1143c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726135"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-lync-for-windows-phone-in-lync-server-2013"></a>Installieren von lync für Windows phone in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-02-03_

Lync 2013 für Windows Phone ist eine vom Benutzer installierbare Anwendung, die auf dem Windows Phone Marketplace zur Verfügung steht.

<div>

## <a name="installing-lync-for-windows-mobile"></a>Installieren von lync für Windows Mobile

Sie können Ihre Benutzer anweisen, lync 2013 für Windows Phone auf Ihren Geräten zu installieren, indem Sie Sie an den Windows <http://go.microsoft.com/fwlink/p/?linkid=231901>Phone Marketplace unterrichten.

</div>

<div>

## <a name="if-you-use-a-dns-srv-record-to-publish-exchange-web-services"></a>Wenn Sie einen DNS-SRV-Eintrag zum Veröffentlichen von Exchange-Webdiensten verwenden

Um die Exchange-Integration für lync-Clients zu aktivieren, veröffentlichen einige Organisationen die Exchange-Webdienste-URL mithilfe eines DNS-SRV-Eintrags. Das Dokument "Understanding and Troubleshooting Exchange Integration", das im Microsoft Download Center [http://go.microsoft.com/fwlink/?LinkID=391095](http://go.microsoft.com/fwlink/?linkid=391095)verfügbar ist, beschreibt Szenarien, in denen dies erforderlich sein kann. Die Exchange-Integration für Windows Phone-Benutzer funktioniert in diesem Szenario jedoch nicht, da die Windows Phone-Plattform keine SRV-Lookups unterstützt. Sie müssen Windows Phone-Benutzer anweisen, die Exchange-Webdienste-URL anzugeben, anstatt dem Smartphone den automatischen Erkennen des Servers zu ermöglichen.

Weisen Sie die Benutzer an, die lync-Einstellungen auf Ihren Windows-Smartphones wie folgt zu konfigurieren:

1.  Wählen Sie in Windows phone in den lync-Einstellungen den Bildschirm **Exchange** aus.

2.  Verschieben Sie den **Server automatisch erkennen** auf **aus**.

3.  Tippen Sie auf das leere Feld, und geben Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) oder die URL für Exchange Web Services ein.
    
    <div>
    

    > [!NOTE]  
    > Sie können entweder den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) oder die vollständige URL Ihres Exchange-Webdienste-Servers angeben. Wenn Sie den FQDN angeben, werden das Protokoll (https://) und der Exchange-Webdienste Pfad (/EWS/Exchange.asmx) automatisch hinzugefügt. Wenn ihr Pfad für Exchange-Webdienste anders ist, können Sie die vollständige URL angeben.

    
    </div>

4.  Schließen Sie den Bildschirm.

</div>

<div>

## <a name="verifying-mobile-client-installation"></a>Überprüfen der Installation des mobilen Clients

Nachdem Sie den Client konfiguriert und sich erfolgreich angemeldet haben, verwenden Sie die folgenden Tests, um zu überprüfen, ob Ihre Installation von lync 2013 auf Ihrem mobilen Gerät ordnungsgemäß funktioniert.

**Suchen nach einem Kontakt im Unternehmensverzeichnis**

1.  Tippen Sie in der Kontaktliste unten auf **Suchen** .

2.  Suchen Sie einen Kontakt, der nur in der globalen Adressliste vorhanden ist.

3.  Stellen Sie sicher, dass der Kontaktname in den Suchergebnissen angezeigt wird.

**Testen der Chat- und Anwesenheitsfunktionen**

1.  Tippen Sie in der Kontaktliste auf einen Kontakt.

2.  Tippen Sie auf der Visitenkarte auf das Symbol **Chat** .

3.  Stellen Sie sicher, dass ein Chatfenster zum Eingeben und Senden einer Sofortnachricht angezeigt wird.

**Testen der Auswahlkonferenz**

1.  Planen Sie in Outlook eine lync-Besprechung.

2.  Öffnen Sie auf dem mobilen Gerät die Besprechungseinladung.

3.  Klicken Sie in der Besprechung auf den Link, um an der Besprechung teilzunehmen.

4.  Nehmen Sie den Anruf vom Konferenzdienst entgegen und stellen Sie sicher, dass Sie mit dem Besprechungsaudio verbunden sind.

**Testen von Pushbenachrichtigungen**

1.  Registrieren Sie sich auf dem mobilen Gerät von Benutzer a bei lync mit dem Konto von Benutzer a.

2.  Öffnen Sie eine andere Anwendung auf dem mobilen Gerät.

3.  Bei einem anderen Client können Sie sich mit dem Konto von Benutzer B bei lync anmelden.

4.  Senden Sie eine Sofortnachricht von Benutzer B an Benutzer A.

5.  Stellen Sie sicher, dass die Sofortnachricht auf dem mobilen Gerät von Benutzer A erscheint.

</div>

</div>

<span> </span>

</div>

</div>

</div>

