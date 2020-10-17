---
title: 'Lync Server 2013: Reduzieren von unerwünschten Sofortnachrichten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reducing unsolicited IM for Lync Server 2013
ms:assetid: d2998708-e699-4465-a918-e1d9ea4c49c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518335(v=OCS.15)
ms:contentKeyID: 62625493
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e6b3b720e5c05051cd556af7d32e8293e95c315
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512012"
---
# <a name="reducing-unsolicited-im-for-lync-server-2013"></a>Reduzieren von unerwünschten Sofortnachrichten für lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-12-05_

Die intelligente Sofortnachrichten-Filter Anwendung schützt Ihre Microsoft lync Server 2013-Bereitstellung vor den häufigsten Viren mit minimaler Beeinträchtigung der Benutzeroberfläche. Der intelligente Sofortnachrichtenfilter bietet folgende Funktionen:

  - Verbesserte URL-Filterung

  - Verbesserte Filterung von Dateiübertragungen

Konfigurieren Sie mit dem intelligenten Sofortnachrichtenfilter Filter zum Blockieren unerwünschter oder potenziell schädlicher Sofortnachrichten von unbekannten Endpunkten außerhalb der Unternehmensfirewall. Zum Konfigurieren von Filtern geben Sie die Kriterien an, anhand derer die zu blockierenden Elemente, z. B. Sofortnachrichten mit Links und Dateien mit bestimmten Erweiterungen, ermittelt werden sollen.

Bevor Sie die Filteranwendung für den intelligenten Chat Nachrichtendienst bereitstellen, sollten Sie wissen, wie Filteroptionen angewendet werden, wenn Nachrichten von einem lync Server 2013 Server an einen anderen weitergeleitet werden. Die Art der Anwendung von Filteroptionen ist konsistent, unabhängig davon, ob die Server sich in einer einzigen Organisation oder in mehreren Organisationen befinden. Diese Konsistenz betrifft die Art und Weise, wie benutzerdefinierte Hinweise und Warntexte in Nachrichten eingefügt und über Server übermittelt werden.

Es empfiehlt sich, die Filteroptionen so einzustellen, dass Sofortnachrichten mit Hyperlinks zugelassen sind, der intelligente Sofortnachrichtenfilter jedoch einen Unterstrich davor einfügen muss, damit der Link deaktiviert wird. Wenn Sie diese Option auswählen, können Sie zusätzlich einen Hinweis an die Benutzer verfassen, der am Anfang jeder Sofortnachricht angezeigt wird, die einen Hyperlink enthält.

Eine zweite Filteroption besteht darin, Sofortnachrichten mit nicht veränderten Hyperlinks zuzulassen. Wenn Sie diese Option auswählen, können Sie zusätzlich eine Warnung an die Benutzer verfassen (empfohlen), die in jede Nachricht eingefügt wird.

Eine dritte Option besteht darin, alle Sofortnachrichten mit Hyperlinks zu blockieren. Wenn Sie diese Option wählen, sendet der Server eine Warnung an den Benutzer. Diese Warnung müssen Sie selbst verfassen.

</div>

<span> </span>

</div>

</div>

</div>

