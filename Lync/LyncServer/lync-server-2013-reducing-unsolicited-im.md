---
title: 'Lync Server 2013: Reduzieren von nicht angeforderten Chatnachrichten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Reducing unsolicited IM for Lync Server 2013
ms:assetid: d2998708-e699-4465-a918-e1d9ea4c49c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518335(v=OCS.15)
ms:contentKeyID: 62625493
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5042c4400cdf16be650a3c2c74ed756f01d93114
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823917"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reducing-unsolicited-im-for-lync-server-2013"></a>Reduzieren von nicht angeforderten Chatnachrichten für Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-12-05_

Die intelligente Chat Filter-Anwendung schützt Ihre Microsoft lync Server 2013-Bereitstellung vor den häufigsten Viren mit minimaler Beeinträchtigung der Benutzererfahrung. Der intelligente Chat-Filter bietet Folgendes:

  - Erweiterte URL-Filterung

  - Verbesserte Filter für die Dateiübertragung

Verwenden Sie den intelligenten Chatfilter, um Filter so zu konfigurieren, dass unerwünschte oder potenziell schädliche Sofortnachrichten von unbekannten Endpunkten außerhalb der Unternehmensfirewall blockiert werden. Sie konfigurieren Filter, indem Sie die Kriterien angeben, die verwendet werden sollen, um zu bestimmen, was blockiert werden soll, beispielsweise Sofortnachrichten mit Links und Dateien mit bestimmten Erweiterungen.

Bevor Sie die intelligente Chat-Nachrichten Filter Anwendung bereitstellen, sollten Sie wissen, wie Filteroptionen angewendet werden, wenn Nachrichten von einem lync Server 2013-Server an einen anderen weitergeleitet werden. Die Art und Weise, wie diese Filteroptionen angewendet werden, ist konsistent, unabhängig davon, ob sich die Server in einer einzelnen Organisation oder unternehmensübergreifend befinden. Diese Konsistenz bezieht sich auf die Art und Weise, in der benutzerdefinierte Hinweise und Warnungstexte in Nachrichten eingefügt und serverübergreifend gesendet werden.

Die empfohlene Filteroption besteht darin, Sofortnachrichten mit Hyperlinks zuzulassen, aber den intelligenten Chat-Filter zum Deaktivieren der Verknüpfung zu erzwingen, indem Sie einen Unterstrich davor einfügen. Wenn Sie diese Option auswählen, haben Sie die zusätzliche Möglichkeit, eine Benachrichtigung an Benutzer zu verfassen, die am Anfang jeder Chatnachricht angezeigt wird, die einen Link enthält.

Eine zweite Filteroption besteht darin, Sofortnachrichten mit nicht geänderten Hyperlinks zu ermöglichen. Wenn Sie diese Option auswählen, haben Sie die zusätzliche Option (empfohlen) zum Verfassen einer Warnung für Benutzer, die in jede Nachricht eingefügt wird.

Eine dritte Möglichkeit besteht darin, alle Sofortnachrichten, die Links enthalten, zu blockieren. Wenn Sie diese Option auswählen, sendet der Server eine Warnung an den Benutzer. Sie müssen diese Warnung schreiben.

</div>

<span> </span>

</div>

</div>

</div>

