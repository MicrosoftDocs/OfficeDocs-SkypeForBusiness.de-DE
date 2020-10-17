---
title: 'Lync Server 2013: Datenbankschema für beständigen Chat'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Persistent Chat database schema
ms:assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558653(v=OCS.15)
ms:contentKeyID: 48184228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b393f9281c1bb1fc1072a541b33bbab2656dafb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524252"
---
# <a name="persistent-chat-database-schema-in-lync-server-2013"></a>Datenbankschema für beständigen Chat in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-18_

In diesem Dokument wird das Schema der Datenbank für beständigen Chat in lync Server 2013 Kommunikationssoftware dokumentiert.

Die Datenbank für beständigen Chat bezieht sich auf die Datenbank, die den lync Server 2013 Back-End-Server Rollen **PersistentChatStore** (entsprechend der MGC-Datenbank) und **PersistentChatComplianceStore** (entsprechend der mgccomp-Datenbank) entspricht. Durch die Veröffentlichung dieses Schemas können Sie Abfragen erstellen und erhalten Einblick in das Erstellen hilfreicher Berichte zur Verwendung der Chatfunktion, zu aktiven Räumen, Benutzern mit den meisten Beiträgen usw.

<div>


> [!IMPORTANT]  
> Wir behalten uns das Recht zur Weiterentwicklung dieses Schemas vor. Microsoft übernimmt keinerlei Garantie für eine dauerhafte vollständige Abwärtskompatibilität mit diesem veröffentlichten Schema.



</div>

Halten Sie sich an folgende bewährte Methoden:

  - Keine SELECT \* //wird unterstützt, da die Spaltenliste wachsen kann.

  - Es werden keine benutzergenerierten Schemaänderungen unterstützt.

  - Auch Schreibvorgänge werden nicht unterstützt.

  - Testen Sie alle Abfragen, die Sie erstellen, mit Datenbanken ähnlicher Größe, um sicherzustellen, dass die Leistung der Abfragen Ihren Anforderungen entspricht.

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Liste der Server Tabellen für beständigen Chat in lync Server 2013](lync-server-2013-list-of-persistent-chat-server-tables.md)

  - [Liste der Kompatibilitätstabellen für den Server für beständigen Chat in lync Server 2013](lync-server-2013-list-of-persistent-chat-server-compliance-tables.md)

  - [Tabellendetails für persistent Chat Server in lync Server 2013](lync-server-2013-persistent-chat-server-table-details.md)

  - [Beispiel für Datenbankabfragen für beständigen Chat für lync Server 2013](lync-server-2013-sample-persistent-chat-database-queries.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

