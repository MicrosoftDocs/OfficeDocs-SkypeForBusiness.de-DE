---
title: 'Lync Server 2013: Neue Funktionen der Reaktionsgruppenanwendung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New Response Group application features
ms:assetid: 569544b4-fa97-429b-97e6-568afab6c19b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398373(v=OCS.15)
ms:contentKeyID: 48184196
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33dd01cf7516f950e58dbc90ee09b06901bccf74
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826150"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-response-group-application-features-in-lync-server-2013"></a>Neue Funktionen der Reaktionsgruppenanwendung in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-29_

Mit der reaktionsgruppenanwendung können Sie eingehende Anrufe an bestimmte Personen zu speziellen Zwecken wie Kundendienst, internem Helpdesk oder allgemeinen Telefonsupport für eine Abteilung weiterleiten und in die Warteschlange einreihen.

Die folgenden Features der reaktionsgruppenanwendung sind in lync Server 2013 neu:

  - **Manager-Rolle**
    
    Lync Server 2013 führt eine neue Rolle des Antwortgruppen-Managers ein. Nun gibt es zwei Verwaltungsrollen für Antwortgruppen: Antwortgruppen-Manager und Antwortgruppen Administrator. Während Reaktionsgruppen Administratoren weiterhin ein beliebiges Element für eine Reaktionsgruppe konfigurieren können, können Manager nur bestimmte Elemente nur für Antwortgruppen konfigurieren, die Sie besitzen.
    
    Diese Verbesserungen im Verwaltungsmodell nutzen die Skalierbarkeit der Reaktionsgruppe, insbesondere bei umfangreichen Bereitstellungsszenarien.

  - **Hohe Verfügbarkeit**
    
    Die Unterstützung für die Reaktionsgruppe in Form einer SQL Server-Spiegelung ist als Teil der allgemeinen Konfiguration und Bereitstellung von Hochverfügbarkeits Funktionen für lync Server 2013 aktiviert. Wenn Sie für eine höhere Verfügbarkeit konfigurieren und die Verbindung mit dem primären Back-End-Server verlieren, ist die Funktion der Reaktionsgruppe nicht von der Nutzung des gespiegelten Back-End-Servers betroffen.
    
    Die Unterstützung für die SQL Server-Spiegelung für die reaktionsgruppenanwendung kann nicht einzeln aktiviert oder außerhalb der gesamten lync Server 2013-Konfiguration mit höherer Verfügbarkeit konfiguriert werden.

  - **Notfallwiederherstellung**
    
    Die Unterstützung für die Disaster Recovery für die reaktionsgruppenanwendung wird im Rahmen der Konfiguration und Bereitstellung der gekoppelten Front-End-Pools aktiviert, die Teil der gesamten lync Server 2013-Konfiguration für die Disaster Recovery sind. Darüber hinaus unterstützen Cmdlets für das Importieren und Exportieren von Reaktionsgruppen den Failoverprozess für den Sicherungspool und den Failback-Prozess im primären Pool oder in einem neuen Pool. Wenn ein Ausfall im primären Pool auftritt, können Reaktionsgruppen für den Sicherungspool Failover durchgeführt werden, und bei einem Ausfall ist der primäre Pool oder ein neuer Pool wieder fehlerhaft.

<div id="sectionSection0" class="section">

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Planen von Reaktionsgruppen in Lync Server 2013](lync-server-2013-planning-for-response-groups.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

