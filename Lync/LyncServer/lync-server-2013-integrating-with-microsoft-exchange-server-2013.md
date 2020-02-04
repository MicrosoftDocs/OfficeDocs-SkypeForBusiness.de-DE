---
title: 'Lync Server 2013: Integration in Microsoft Exchange Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Integrating Lync Server 2013 and Exchange Server 2013
ms:assetid: 795dc1c6-524f-4012-8b66-103b55198044
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688098(v=OCS.15)
ms:contentKeyID: 49733697
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1467f6a570f83908eb5809f9493303bdc91c169
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725855"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="integrating-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a>Integration von Microsoft lync Server 2013 und Microsoft Exchange Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-07-09_

Exchange und lync Server verfügen über ein langes Integrations-und Kompatibilitäts Protokoll. Diese Integration ist in der jeweiligen Clientanwendung besonders auffällig. Lync-Anwesenheitsinformationen können beispielsweise in Microsoft Outlook gemeldet werden. Lync kann auch Outlook-Kalender verwenden, um diese Anwesenheitsinformationen automatisch zu aktualisieren. (Beispielsweise kann lync ihren Status in "beschäftigt" ändern, wenn Ihr Kalender zeigt, dass eine Besprechung geplant ist.) Obwohl Sie Exchange nicht ausführen müssen, um lync Server auszuführen (oder umgekehrt), besteht kaum Zweifel daran, dass die Verwendung der beiden Produkte zusammen die Definition des Ausdrucks "besser zusammen" verkörpert.

Dies gilt insbesondere für die Veröffentlichung von Microsoft lync Server 2013 und Microsoft Exchange Server 2013. Neben Features wie Unified Messaging und Chat und Anwesenheit, die in Microsoft Exchange Server 2010 und Microsoft lync Server 2010 zu finden sind, enthalten die 2013-Versionen der Server Produkte eine Reihe neuer Funktionen. Zu diesen Funktionen gehören unter anderem:

  - **Integration der lync-Archivierung** In lync Server 2013 können Administratoren weiterhin Instant Messaging-und Webkonferenz Protokolle in SQL Server archivieren (auf die gleiche Weise, wie diese Transkripte in lync Server 2010 archiviert wurden). Sie können aber auch festlegen, dass die Protokolle in Exchange 2013 archiviert werden sollen, wobei die Protokolle in den einzelnen Benutzerpostfächern auf die gleiche Weise gespeichert werden, in der die Kommunikation in Exchange archiviert wird. Das bedeutet ein einzelnes Repository für alle Ihre elektronischen Kommunikationen (sowohl von Exchange als auch von lync Server), wodurch es viel einfacher ist, diese archivierten Kommunikationen zu suchen und abzurufen, falls dies erforderlich ist.

  - **Einheitlicher Kontaktspeicher** In lync Server 2010 mussten Benutzer getrennte Kontaktlisten in Outlook und lync verwalten. um sicherzustellen, dass Sie über dieselben Kontakte in beiden Produkten verfügen, mussten Sie doppelte Kontaktlisten verwalten, eine für Outlook und eine für lync. Bei lync Server 2013 können Benutzer Kontakte jedoch in Exchange 2013 und im Unified Contact Store gespeichert werden. Mit einem einzelnen Kontaktspeicher können Benutzer nur einen Satz Kontakte verwalten, wobei die gleichen Kontakte in lync 2013, Outlook 2013 und Outlook Web Access 2013 zur Verfügung stehen.

  - **Lync-Besprechungsplanung von OWA**. Mit lync Server 2013 und Exchange 2013-Integration können Benutzer lync-Besprechungen aus Outlook Web Access 2013 planen.

  - **Fotos mit höherer Auflösung**. Lync 2010 konnte nur kleine Fotos Ihrer Kontakte anzeigen. Das liegt daran, dass diese Fotos in Active Directory gespeichert wurden und Active Directory eine 48 Pixelgröße von 48 Pixeln für gespeicherte Fotos vorschreibt. Mit lync Server 2013 können Fotos jedoch in Microsoft Exchange gespeichert werden. Damit können Fotos mit hoher Auflösung so groß wie 648 Pixel von 648 Pixeln sein. Wie Sie vielleicht erwarten, wurde lync 2013 aktualisiert, um die Anzeige dieser Fotos mit hoher Auflösung zu ermöglichen.

Beachten Sie, dass diese neuen Features die Verwendung von lync Server 2013 und Exchange 2013 erfordern. Darüber hinaus müssen Benutzer, die diese neuen Funktionen in vollem Umfang nutzen möchten, über Konten in lync Server 2013 und Exchange 2013 verfügen und die neuesten Versionen der Client Software verwenden (beispielsweise lync 2013). Beispielsweise steht der Unified Contact Store nicht für Benutzer zur Verfügung, die sich in lync Server 2010 befanden. Ebenso können Fotos mit hoher Auflösung in lync 2010 nicht angezeigt werden.

Diese Dokumentation enthält Informationen zur Integration von lync Server 2013 und Exchange 2013. einschließlich Schritt-für-Schritt-Informationen zur Aktivierung neuer Funktionen wie Archivierungs Integration und einheitlicher Kontaktspeicher. In dieser Dokumentation wird die Ersteinrichtung und Konfiguration dieser beiden Produkte erläutert. Details zum Bereitstellen von lync Server 2013 finden Sie im lync Server 2013 Tech [http://go.microsoft.com/fwlink/p/?LinkId=246127](http://go.microsoft.com/fwlink/p/?linkid=246127)Center unter. Details zum Bereitstellen von Exchange 2013 finden Sie im Exchange 2013 Tech [http://go.microsoft.com/fwlink/p/?LinkId=268528](http://go.microsoft.com/fwlink/p/?linkid=268528)Center unter.

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

[Voraussetzungen für die Integration von Microsoft lync Server 2013 und Microsoft Exchange Server 2013](lync-server-2013-prerequisites-for-integrating-with-exchange-server-2013.md)

[Konfigurieren von Partneranwendungen in Microsoft lync Server 2013 und Microsoft Exchange Server 2013](lync-server-2013-configuring-partner-applications-in-lync-server-2013-and-exchange-server-2013.md)

[Konfigurieren von Microsoft lync Server 2013 für die Verwendung von Microsoft Exchange Server 2013-Archivierung](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md)

[Konfigurieren von Microsoft SharePoint Server 2013 zum Suchen nach archivierten Microsoft lync Server 2013-Daten](lync-server-2013-configuring-microsoft-sharepoint-server-2013-to-search-for-archived-lync-server-2013-data.md)

[Konfigurieren von Microsoft lync Server 2013 für die Verwendung des einheitlichen Kontaktspeichers](lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md)

[Konfigurieren der Verwendung von Fotos mit hoher Auflösung in Microsoft lync Server 2013](lync-server-2013-configuring-the-use-of-high-resolution-photos.md)

[Konfigurieren von Microsoft Exchange Server 2013 Unified Messaging für Microsoft lync Server 2013-Voicemail](lync-server-2013-configuring-microsoft-exchange-server-2013-unified-messaging-for-lync-server-2013-voice-mail.md)

[Integrieren von Microsoft lync Server 2013 und Microsoft Outlook Web App 2013](lync-server-2013-integrating-lync-server-and-outlook-web-app-2013.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

