---
title: 'Lync Server 2013: integrieren in Microsoft Exchange Server 2013'
description: 'Lync Server 2013: Integration in Microsoft Exchange Server 2013.'
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
ms.openlocfilehash: 54ab4a81e5455bc0a44677b1509876f39ff4d985
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543981"
---
# <a name="integrating-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a>Integrieren von Microsoft Lync Server 2013 und Microsoft Exchange Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-07-09_

Exchange und lync Server haben eine lange Geschichte der Integration und Kompatibilität. Diese Integration ist in der jeweiligen Clientanwendung am deutlichsten spürbar. Beispielsweise können lync-Anwesenheitsinformationen in Microsoft Outlook gemeldet werden; Ebenso kann lync Outlook-Kalender verwenden, um diese Anwesenheitsinformationen automatisch zu aktualisieren. (Beispielsweise kann lync ihren Status in "beschäftigt" ändern, wenn Ihr Kalender zeigt, dass Sie eine Besprechung geplant haben.) Obwohl Sie Exchange nicht ausführen müssen, um lync Server auszuführen (oder umgekehrt), gibt es kaum einen Zweifel daran, dass die Verwendung der beiden Produkte zusammen die Definition des Begriffs "besser zusammen" verkörpert.

Dies gilt insbesondere für die Veröffentlichung von Microsoft lync Server 2013 und Microsoft Exchange Server 2013. Neben Features wie Unified Messaging und Sofortnachrichten und Anwesenheitsinformationen, die sich in Microsoft Exchange Server 2010 und Microsoft lync Server 2010 befinden, enthalten die 2013-Versionen der Server Produkte eine Reihe neuer Funktionen. Dazu zählen beispielsweise folgende:

  - **Lync-Archivierungs Integration**. In lync Server 2013 Administratoren weiterhin die Möglichkeit haben, Chatnachrichten und Webkonferenz-Transkripte in SQL Server zu archivieren (genauso wie diese Transkripte in lync Server 2010 archiviert wurden). Alternativ können Administratoren auch die Archivierung von Transkripten in Exchange 2013 auswählen, wobei diese Transkripte in den einzelnen Benutzerpostfächern auf dieselbe Weise gespeichert werden, in der Exchange die Kommunikation archiviert. Das bedeutet ein einzelnes Repository für Ihre gesamte elektronische Kommunikation (sowohl in Exchange als auch in lync Server), wodurch es viel einfacher wird, diese Archivierte Kommunikation zu suchen und abzurufen, falls dies erforderlich ist.

  - **Einheitlicher Kontaktspeicher**. In lync Server 2010 mussten Benutzer getrennte Kontaktlisten in Outlook und lync verwalten; um sicherzustellen, dass in beiden Produkten dieselben Kontakte verfügbar waren, mussten Sie doppelte Kontaktlisten verwalten, eine für Outlook und eine für lync. Mit lync Server 2013 können Benutzer Kontakte jedoch in Exchange 2013 und im einheitlichen Kontaktspeicher gespeichert werden. Durch die Verwendung eines einzelnen Kontaktspeichers können Benutzer nur eine Gruppe von Kontakten verwalten, wobei dieselbe Gruppe von Kontakten in lync 2013, Outlook 2013 und Outlook Web Access 2013 zur Verfügung steht.

  - **Lync-Besprechungsplanung von OWA**. Mit lync Server 2013-und Exchange 2013-Integration können Benutzer lync-Besprechungen von Outlook Web Access 2013 aus planen.

  - **Fotos mit hoher Auflösung**. Lync 2010 konnten nur kleine Fotos Ihrer Kontakte anzeigen; Das liegt daran, dass diese Fotos in Active Directory gespeichert wurden und Active Directory eine 48 Pixelgrößen Beschränkung von 48 Pixeln auf gespeicherte Fotos auferlegt. Mit lync Server 2013 können Fotos jedoch in Microsoft Exchange gespeichert werden; Dies ermöglicht hochauflösende Fotos mit einer Größe von 648 Pixeln von 648 Pixel. Wie Sie vielleicht erwarten, wurde lync 2013 aktualisiert, um die Anzeige dieser hochauflösenden Fotos zu ermöglichen.

Beachten Sie, dass diese neuen Features sowohl lync Server 2013 als auch Exchange 2013 erfordern. Darüber hinaus müssen Benutzer, die diese neuen Funktionen in vollem Umfang nutzen möchten, über Konten für lync Server 2013 und Exchange 2013 verfügen und die neuesten Versionen der Client Software verwenden (beispielsweise lync 2013). Beispielsweise steht der einheitliche Kontaktspeicher nicht für Benutzer zur Verfügung, die in lync Server 2010 verwaltet wurden. Ebenso können hochauflösende Fotos nicht in lync 2010 angezeigt werden.

Diese Dokumentation enthält Informationen zur Integration von lync Server 2013 und Exchange 2013. einschließlich Schritt-für-Schritt-Informationen zur Aktivierung neuer Features wie die Archivierungs Integration und den einheitlichen Kontaktspeicher. In dieser Dokumentation werden die anfänglichen Einstellungen und Konfigurationen dieser beiden Produkte erläutert. Ausführliche Informationen zum Bereitstellen von lync Server 2013 finden Sie im lync Server 2013 Tech Center unter [https://go.microsoft.com/fwlink/p/?LinkId=246127](https://go.microsoft.com/fwlink/p/?linkid=246127) . Ausführliche Informationen zum Bereitstellen von Exchange 2013 finden Sie im Exchange 2013 Tech Center unter [https://go.microsoft.com/fwlink/p/?LinkId=268528](https://go.microsoft.com/fwlink/p/?linkid=268528) .

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

[Voraussetzungen für die Integration von Microsoft lync Server 2013 und Microsoft Exchange Server 2013](lync-server-2013-prerequisites-for-integrating-with-exchange-server-2013.md)

[Konfigurieren von Partneranwendungen in Microsoft lync Server 2013 und Microsoft Exchange Server 2013](lync-server-2013-configuring-partner-applications-in-lync-server-2013-and-exchange-server-2013.md)

[Konfigurieren Microsoft lync Server 2013 für die Verwendung Microsoft Exchange Server 2013 Archivierung](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md)

[Konfigurieren Microsoft SharePoint Server 2013 für die Suche nach archivierten Microsoft lync Server 2013 Daten](lync-server-2013-configuring-microsoft-sharepoint-server-2013-to-search-for-archived-lync-server-2013-data.md)

[Konfigurieren Microsoft lync Server 2013 für die Verwendung des einheitlichen Kontaktspeichers](lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md)

[Konfigurieren der Verwendung von hochauflösenden Fotos in Microsoft lync Server 2013](lync-server-2013-configuring-the-use-of-high-resolution-photos.md)

[Konfigurieren Microsoft Exchange Server 2013 Unified Messaging für Microsoft lync Server 2013-Voicemail](lync-server-2013-configuring-microsoft-exchange-server-2013-unified-messaging-for-lync-server-2013-voice-mail.md)

[Integrieren von Microsoft lync Server 2013 und Microsoft Outlook Web App 2013](lync-server-2013-integrating-lync-server-and-outlook-web-app-2013.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

