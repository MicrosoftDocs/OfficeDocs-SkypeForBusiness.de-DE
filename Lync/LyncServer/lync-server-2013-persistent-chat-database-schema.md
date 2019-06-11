---
title: 'Lync Server 2013: Datenbankschema für beständigen Chat'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Persistent Chat database schema
ms:assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558653(v=OCS.15)
ms:contentKeyID: 48184228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f35b1551b1ef7f228c70cbb76e748eae5e7cf59
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825191"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="persistent-chat-database-schema-in-lync-server-2013"></a>Datenbankschema für beständigen Chat in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-18_

Dadurch wird das Schema der Datenbank für beständigen Chat in der lync Server 2013-Kommunikationssoftware dokumentiert.

Die Datenbank für beständigen Chat bezieht sich auf die Datenbank, die den lync Server 2013-Back-End-Serverrollen **PersistentChatStore** (entsprechend der MGC-Datenbank) und **PersistentChatComplianceStore** (entsprechend der mgccomp Datenbank). Das Ziel der Veröffentlichung dieses Schemas ist es, Ihnen zu ermöglichen, Abfragen zu erstellen und einige Einblicke in das Erstellen nützlicher Berichte rund um die Chat-Nutzung, in Active rooms, in Top-Poster usw. zu erhalten.

<div>


> [!IMPORTANT]  
> Wir behalten uns das Recht vor, dieses Schema weiterzuentwickeln. Microsoft übernimmt keine Garantien, um die vollständige Abwärtskompatibilität mit diesem veröffentlichten Schema zu gewährleisten.



</div>

Befolgen Sie diese bewährten Methoden:

  - Es wird\* keine SELECT//-Auswahl unterstützt, da die Spaltenliste vergrößert werden kann.

  - Es werden keine vom benutzergenerierten Schemaänderungen unterstützt.

  - Es werden keine Schreibvorgänge unterstützt.

  - Testen Sie alle Abfragen, die Sie auf repräsentativ sortierten Datenbankenerstellen, um sicherzustellen, dass die Abfragen auf einer Ebene ausgeführt werden können, um Ihre Anforderungen zu erfüllen.

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Liste der Tabellen für den Server für beständigen Chat in Lync Server 2013](lync-server-2013-list-of-persistent-chat-server-tables.md)

  - [Liste der Kompatibilitätstabellen für den Server für beständigen Chat in Lync Server 2013](lync-server-2013-list-of-persistent-chat-server-compliance-tables.md)

  - [Ausführliche Informationen zur Tabelle für den Server für beständigen Chat in Lync Server 2013](lync-server-2013-persistent-chat-server-table-details.md)

  - [Beispieldatenbankabfragen für beständigen Chat für Lync Server 2013](lync-server-2013-sample-persistent-chat-database-queries.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

