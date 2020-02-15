---
title: 'Lync Server 2013: neue Reaktionsgruppenanwendung-Features'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Response Group application features
ms:assetid: 569544b4-fa97-429b-97e6-568afab6c19b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398373(v=OCS.15)
ms:contentKeyID: 48184196
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f98261aaf40413c52598465338c9c198aca435f9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048309"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-response-group-application-features-in-lync-server-2013"></a>Neue Reaktionsgruppenanwendung Features in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-29_

Mithilfe der Reaktionsgruppenanwendung können Sie eingehende Anrufe an benannte Personen mit speziellen Aufgabenbereichen weiterleiten – z. B. an den Kundendienst, ein internes Helpdesk oder die allgemeine Telefonunterstützung für eine Abteilung – oder den Anruf in der Warteschleife platzieren.

Die folgenden Reaktionsgruppenanwendung Features sind in lync Server 2013 neu:

  - **Manager-Rolle**
    
    Lync Server 2013 stellt eine neue Rolle für Reaktionsgruppen-Manager vor. Nun gibt es zwei Verwaltungsrollen für Reaktionsgruppen: Reaktionsgruppen-Manager und Reaktionsgruppen Administrator. Während Reaktionsgruppen Administratoren immer noch ein beliebiges Element für eine beliebige Reaktionsgruppe konfigurieren können, können Manager nur bestimmte Elemente konfigurieren, nur für Ihre eigenen Reaktionsgruppen.
    
    Dies stellt – insbesondere mit Blick auf umfangreiche Bereitstellungsszenarien – eine Verbesserung im Verwaltungsmodell bezüglich der Skalierbarkeit von Reaktionsgruppen dar.

  - **Hochverfügbarkeit**
    
    Die Unterstützung für hohe Verfügbarkeit für den Reaktionsgruppenanwendung in Form von SQL Server Spiegelung wird als Teil der Gesamtkonfiguration und der Bereitstellung der hohen Verfügbarkeit für lync Server 2013 aktiviert. Wenn Sie Ihre Konfiguration auf hohe Verfügbarkeit auslegen und es zu einer Unterbrechung der Verbindung zum primären Back-End-Server kommt, ist die Reaktionsgruppenfunktion davon nicht beeinträchtigt, weil auf einen gespiegelten Back-End-Server zugegriffen werden kann.
    
    Unterstützung für SQL Server Spiegelung für das Reaktionsgruppenanwendung kann nicht einzeln aktiviert oder konfiguriert werden, außerhalb der gesamten lync Server 2013 Konfiguration für hohe Verfügbarkeit.

  - **Notfallwiederherstellung**
    
    Die Unterstützung für die Notfallwiederherstellung für den Reaktionsgruppenanwendung wird als Teil der Konfiguration und Bereitstellung der gekoppelten Front-End-Pools aktiviert, die Teil der gesamten lync Server 2013 Notfall Wiederherstellungskonfiguration sind. Darüber hinaus unterstützen die Cmdlets der Reaktionsgruppe den Failoverprozess zum Sicherungspool sowie den Failbackprozess zum primären oder zu einem neuen Pool. Bei einem Ausfall des primären Pools kann für die Reaktionsgruppen ein Failover zum Sicherungspool durchgeführt werden, und nach der Wiederherstellung kann ein Failback zum primären oder zu einem neuen Pool durchgeführt werden.

<div id="sectionSection0" class="section">

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Planen von Reaktionsgruppen in lync Server 2013](lync-server-2013-planning-for-response-groups.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

