---
title: 'Lync Server 2013: Remote Anrufsteuerung und Telefonnummernnormalisierung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remote call control and phone number normalization
ms:assetid: 291d9e87-4c65-4ea2-888f-517741391de5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558630(v=OCS.15)
ms:contentKeyID: 48183696
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 76d7ffb386f6b565fc00b866072bfab6390bc8d9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048736"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remote-call-control-and-phone-number-normalization-in-lync-server-2013"></a>Remote Anrufsteuerung und Telefonnummernnormalisierung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-22_

Lync-Clients laden die Normalisierungsregeln für Telefonnummern als Teil des Adressbuchdienst-Dateidownloads (Address Book Service, ABS) herunter. In Szenarien mit Remoteanrufsteuerung werden die vom Adressbuchdienst verwendeten Normalisierungsregeln für Rufnummern sowohl auf eingehende als auch auf ausgehende Anrufe mit Remoteanrufsteuerung angewendet. Für eingehende Anrufe bei einem Benutzer, der für die Remoteanrufsteuerung aktiviert ist, wird die Rufnummer des Anrufers zunächst über das SIP/CSTA-Gateway oder eine Nebenstellenanlage (Private Branch Exchange, PBX) in das E.164-Format normalisiert. Wenn lync Server 2013 den Anruf vom Gateway erhält, führt er eine umgekehrte Nummernsuche (können) für die Telefonnummer des Anrufers anhand der normalisierten Nummer in der Microsoft Office Outlook-Kontaktliste des angerufenen oder der globalen Adressliste (GAL) durch, die in gespeichert wird. der Adressbuchdienst. Wenn die umgekehrte Nummernsuche zu einem Treffer führt, wird der Anrufer in der Benachrichtigung über einen eingehenden Anruf mit seinem Namen identifiziert.

Für ausgehende Anrufe mit Remoteanrufsteuerung wendet lync die Normalisierungsregeln für den Adressbuchdienst auf die gewählte Nummer an, bevor der Anruf an das SIP/CSTA-Gateway weitergeleitet wird.

Ausführliche Informationen zum Erstellen von Normalisierungsregeln für Telefonnummern für die Remoteanrufsteuerung finden Sie unter [Wählpläne und Normalisierungsregeln in lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in der Planungsdokumentation.

<div>

## <a name="migrating-phone-number-normalization-rules"></a>Migrieren von Normalisierungsregeln für Rufnummern

Wenn Sie Benutzer migrieren, die zuvor für die Remoteanrufsteuerung aktiviert waren, finden Sie weitere Informationen in den folgenden Themen der Migrationsdokumentation:

  - Informationen zu lync Server 2010 finden Sie unter [Migrieren des Adressbuchs](migrate-address-book.md) in der Migrationsdokumentation.

  - Informationen zu Communications Server 2007 R2 finden Sie unter [Migrieren des Adressbuchs](migrate-address-book_1.md) in der Migrationsdokumentation.

</div>

</div>

<span> </span>

</div>

</div>

</div>

