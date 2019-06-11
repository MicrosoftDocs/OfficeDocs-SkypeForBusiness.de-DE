---
title: 'Lync Server 2013: Remoteanrufsteuerung und Normalisieren von Rufnummern'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Remote call control and phone number normalization
ms:assetid: 291d9e87-4c65-4ea2-888f-517741391de5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558630(v=OCS.15)
ms:contentKeyID: 48183696
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86de318cb1e72fce8fb6f42ff7698db5974034fe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823168"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remote-call-control-and-phone-number-normalization-in-lync-server-2013"></a>Remoteanrufsteuerung und Normalisieren von Rufnummern in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-22_

Lync-Clients laden Telefonnummern Normalisierungsregeln als Teil des Adressbuchdienst-Dateidownloads (ABS) herunter. In Szenarien für die Remoteanrufsteuerung werden die Normalisierungsregeln für den Adressbuchdienst für eingehende und ausgehende Anrufe in der Remoteanrufsteuerung angewendet. Für eingehende Anrufe an einen Benutzer mit Remoteanrufsteuerung wird die Telefonnummer des Anrufers zuerst vom SIP/CSTA-Gateway oder von der PBX (Private Branch Exchange) auf das E. 164-Format normiert. Wenn lync Server 2013 den Anruf vom Gateway empfängt, führt er Reverse Number Lookup (RNL) für die Telefonnummer des Anrufers anhand der normalisierten Nummer in der Microsoft Office Outlook-Kontaktliste des berufenen oder in der globalen Adressliste (GAL) durch, die in gespeichert ist. der Adressbuchdienst Wenn die Suche nach einer umgekehrten Zahl erfolgreich gefunden wird, wird der Anrufer in der Benachrichtigung über den eingehenden Anruf durch den Namen gekennzeichnet.

Bei ausgehenden Remote Anruf Steuerungs anrufen wendet lync die Normalisierungsregeln für den Adressbuchdienst auf die gewählte Nummer an, bevor der Anruf an das SIP/CSTA-Gateway weitergeleitet wird.

Details zum Erstellen von Regeln für die Normalisierung der Telefonnummern für die Remoteanrufsteuerung finden Sie unter [Wählpläne und Normalisierungsregeln in lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in der Planungsdokumentation.

<div>

## <a name="migrating-phone-number-normalization-rules"></a>Migrieren von Normalisierungsregeln für Telefonnummern

Wenn Sie Benutzer migrieren, die zuvor für die Remoteanrufsteuerung aktiviert wurden, lesen Sie die folgenden Themen in der Migrationsdokumentation:

  - Informationen zu lync Server 2010 finden Sie unter [Migrieren des Adressbuchs](migrate-address-book.md) in der Migrationsdokumentation.

  - Informationen zu Communications Server 2007 R2 finden Sie unter [Migrieren des Adressbuchs](migrate-address-book_1.md) in der Migrationsdokumentation.

</div>

</div>

<span> </span>

</div>

</div>

</div>

