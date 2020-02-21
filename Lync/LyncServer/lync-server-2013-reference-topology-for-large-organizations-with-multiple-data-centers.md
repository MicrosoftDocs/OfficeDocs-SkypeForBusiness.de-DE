---
title: Lync Server 2013 Referenztopologie für große Organisationen mit mehreren Rechenzentren
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reference topology for large organizations with multiple data centers
ms:assetid: 9a6aeae6-629b-49e6-9804-7ef369d7c3dc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398797(v=OCS.15)
ms:contentKeyID: 48184887
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a596276361183bc31b2503aceacb064f1f45ec1f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215151"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="reference-topology-for-lync-server-2013-in-large-organizations-with-multiple-data-centers"></a>Referenztopologie für lync Server 2013 in großen Organisationen mit mehreren Rechenzentren

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-22_

Die Referenztopologie für eine große Organisation mit mehreren Rechenzentren gilt für jede Organisationsgröße mit mehr als einem zentralen Standort. Die genaue Topologie in dem folgenden Diagramm bezieht sich auf eine Organisation mit 50.000 Benutzern, von denen sich 20.000 Benutzer am zentralen Standort A, 20.000 Benutzer am zentralen Standort B und insgesamt 10.000 Benutzer am zentralen Standort C und an Zweigstellenstandorten befinden. Der in diesem Diagramm gezeigte Topologietyp kann Organisationen mit einer beliebigen Benutzeranzahl umfassen.

Zusätzlich zur hohen Verfügbarkeit, die von Pools von Front-End-Servern bereitgestellt wird, bietet diese Topologie Unterstützung für die Notfallwiederherstellung. Die Front-End-Pools an den zentralen Standorten A und B sind zusammen gekoppelt. Wenn einer dieser Pools ausfällt, kann der Administrator die Dienste für die betroffenen Benutzer in den kombinierten Pool des nicht betroffenen Standorts verlagern.

Diese Topologie wird in mehreren Diagrammen gezeigt. Zunächst sehen Sie einen Überblick, gefolgt von detaillierten Ansichten der zentralen Standorte.

**Überblick über die Referenztopologie für große Organisationen mit mehreren Rechenzentren**

![Referenztopologie für mehrere Rechenzentren](images/Gg398797.471e1ce9-be11-44b9-9f4a-59e0551b7b30(OCS.15).jpg "Referenztopologie für mehrere Rechenzentren")

**Referenztopologie für große Organisationen: Detaillierte Ansicht des zentralen Standorts A**

![dab33f19-e77b-42da-9047-858fb9851264](images/Gg398797.dab33f19-e77b-42da-9047-858fb9851264(OCS.15).jpg "dab33f19-e77b-42da-9047-858fb9851264")

**Referenztopologie für große Organisationen: Detaillierte Ansicht des zentralen Standorts B**

![5ccaf1d4-bd53-4cb7-96fe-723147334e7f](images/Gg398797.5ccaf1d4-bd53-4cb7-96fe-723147334e7f(OCS.15).jpg "5ccaf1d4-bd53-4cb7-96fe-723147334e7f")

**Referenztopologie für große Organisationen: Detaillierte Ansicht des zentralen Standorts C**

![7238ca40-340c-491f-b497-ddc2665dadb6](images/Gg398797.7238ca40-340c-491f-b497-ddc2665dadb6(OCS.15).jpg "7238ca40-340c-491f-b497-ddc2665dadb6")

  - **Front-End-Pools sind gekoppelt, um eine Notfallwiederherstellung zu ermöglichen.**    Die Front-End-Pools an Standort a und Standort B sind miteinander gekoppelt, um Unterstützung für die Notfallwiederherstellung bereitzustellen. Wenn der Pool an einem Standort ausfällt, kann der Administrator die Benutzer von dieser Website an den gepaarten Front-End-Pool am anderen Standort, mit mindestens einer Dienstunterbrechung für Benutzer, ein Failover durchführen. Jeder dieser beiden Front-End-Pools hat sechs Server, was ausreicht, um alle 40.000 Benutzer beider Pools im Fall eines Failovers zu unterstützen. Weitere Informationen finden Sie unter [Planung für hohe Verfügbarkeit und Notfallwiederherstellung in lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

  - **Back-End-Server werden gespiegelt**   , um eine höhere Verfügbarkeit für grundlegende Benutzerfunktionen bereitzustellen, hat die Organisation ein gespiegeltes paar von Back-End-Servern für jede Front-End-Pool bereitgestellt. Hierbei handelt es sich um eine optionale Topologie, die Sie stattdessen für die Bereitstellungeines einzelnen Back-End-Servers auswählen können.

  - **Verwenden von Standard Edition-Server an einem Zweigstellenstandort.**    Diese Organisation betrachtet Standort C als Zweigstelle, da es nur 600 Mitarbeiter hat. Die dortigen Benutzer halten jedoch untereinander viele A/V-Konferenzen ab. Wenn er in lync Server als Zweigstellenstandort bereitgestellt wurde, würden die Medien für diese Konferenzen über das WAN (Wide Area Network) an einen zentralen Standort und von einem zentralen Standort aus ausgeführt, auf dem ein Front-End-Server bereitgestellt wurde. Um diese mögliche Bandbreitenlast zu vermeiden, haben Sie ein paar Standard Edition-Server auf dieser Website installiert, in dem diese Konferenzen gehostet werden. Da Standard Edition-Server dort installiert sind, wird lync Server per Definition als zentraler Standort betrachtet und im Topologie-Generator und im Planungs Tool als solche behandelt.
    
    Für die Leistung wäre hier nur eine Standard Edition-Server ausreichen, aber die Organisation hat zwei bereitgestellt und kombiniert, um eine hohe Verfügbarkeit sicherzustellen, wenn ein Server ausfällt.
    
    Auch wenn Standort C als zentraler Standort betrachtet wird, müssen Sie dort keine Edgeserver bereitstellen. In diesem Beispiel verwendet Standort C die an Standort A bereitgestellten Edgeserver.

  - **Überwachung und Archivierung**   diese Organisation hat sowohl Überwachung als auch Archivierung bereitgestellt. Wenn Sie die Überwachung oder Archivierung bereitstellen, wird Sie auf jeder Front-End-Server ausgeführt. Die Datenbanken für diese Features können mit der Back-End-Datenbank oder auf einem separaten Server zusammengefasst werden. Diese Organisation hat sich diese Datenbanken auf einem Server getrennt von den Back-End-Servern am zentralen Standort B befinden. Die Datenbanken erhalten hier Überwachungs-und Archivierungsdaten von den Front-End-Servern an allen Standorten.

  - **Bereitstellungsoptionen für Zweigstellenstandorte.**    Diese Organisation verfügt tatsächlich über 50 Zweigstellen, von denen nur drei in den detaillierten Diagrammen angezeigt werden. Zweigstellenstandorte 1 und 3 verfügen nicht über eine belastbare WAN-Verbindung mit dem zentralen Standort, sodass Survivable Branch Appliances bereitgestellt werden, um den Telefondienst bereitzustellen, falls die WAN-Verbindung zum zentralen Standort ausfällt. Zweigstelle 2 verfügt jedoch über eine stabile WAN-Verbindung, daher benötigen Sie nur ein PSTN-Gateway (Public Switched Telephone Network). Das dort bereitgestellte PSTN-Gateway unterstützt die medienumgehung, daher ist am Zweigstellenstandort B keine Vermittlungsserver erforderlich. Ausführliche Informationen zur Entscheidung, was Sie an einem Zweigstellenstandort installieren sollten, finden Sie unter [Planning for Enterprise Voice Resilienz in lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md) in der Planungsdokumentation.

  - **SIP-Trunking und Vermittlungsserver.**    Beachten Sie, dass Vermittlungsserver an der zentralen Stelle B nicht mit den Front-End-Servern zusammengestellt ist. Der Grund hierfür liegt darin, dass für Standorte mit SIP-Trunking ein eigenständiger Vermittlungsserver empfohlen wird. In den meisten anderen Fällen empfiehlt sich die gemeinsame Ausführung des Vermittlungsservers mit dem Front-End-Server. Ausführliche Informationen zu Vermittlungsserver Topologien finden Sie unter [Components and Topologies for Vermittlungsserver in lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) in der Planungsdokumentation.

  - **Beständiger Chat wird bereitgestellt.**    Diese Organisation hat die erforderlichen Server bereitgestellt, um den beständigen Chat zu aktivieren. Es wurden mehrere Front-End-Server für beständigen Chat bereitgestellt, um die Last für die Anzahl der Benutzer im Pool zu verarbeiten und hohe Verfügbarkeit bereitzustellen. Sie hat auch die Compliance für den beständigen Chat und den Speicher für beständigen Chat und den Kompatibilitäts Speicher für beständigen Chat auf separaten Servern bereitgestellt. Diese Speicher können zusammengestellt werden und sogar mit dem Back-End-Server verbunden sein, aber diese Organisation hat sich entschieden, diese zu trennen, um eine bessere Leistung zu erzielen.

  - **DNS-Lastenausgleich.**    Die Front-End-Pool und Edgeserver Pool,. Auf diese Weise sind keine Hardwaregeräte zum Lastenausgleich für die interne Schnittstelle der Edgeserver erforderlich, und der für Setup und Wartung der Hardwaregeräte zum Lastenausgleich für die weiteren Pools erforderliche Zeitraum wird erheblich verringert, da die Hardwaregeräte zum Lastenausgleich nur für HTTP-Datenverkehr benötigt werden. Ausführliche Informationen zum DNS-Lastenausgleich finden Sie unter [DNS-Lastenausgleich in lync Server 2013](lync-server-2013-dns-load-balancing.md) in der Planungsdokumentation.

  - **Exchange um Bereitstellung.**   Lync Server funktioniert sowohl mit *lokalen* Bereitstellungen von Exchange Unified Messaging (um) als auch mit *gehosteten* Exchange um. Der zentrale Standort A enthält einen Exchange Unified Messaging (um) Server, der Exchange Server und nicht lync Server ausführt. Die Exchange um Funktionalität für lync Server wird im Front-End-Pool ausgeführt.
    
    Am zentralen Standort B wird gehostetes Exchange eingesetzt, daher wird die Exchange UM-Serverfunktionalität ebenfalls gehostet.
    
    Ausführliche Informationen zu Exchange um finden Sie unter [Planning for Exchange Unified Messagingintegration in lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) and [Hosted Exchange Unified Messagingintegration in lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) in der Planungsdokumentation.

  - **Office Web Apps Server.**   Wir empfehlen die Bereitstellung eines Office Web Apps Servers oder einer Office Web Apps Server-Farm in allen Organisation, die Webkonferenzen unterstützen. Sie können eine einzelne Office Web Apps Server-Farm an einem Standort bereitstellen, die den Datenverkehr von allen Standorten abwickelt, oder diese an allen Standorten bereitstellen. Mit Office Web Apps Server können Powerpoint-Folien in Webkonferenzen präsentiert werden. Weitere Informationen finden Sie unter [Konfigurieren der Integration mit Office-webapps Server und lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

  - **Directors konnten hinzugefügt werden.**   Wenn diese Organisation die Sicherheit vor Denial-of-Service-Angriffen verbessern wollte, könnte Sie auch einen Pool von Directors bereitstellen. Ein Director ist eine separate, optionale Serverrolle in lync Server, die keine Benutzerkonten aufweist, oder Anwesenheits-oder Konferenzdienste bereitstellen. Er dient als interner nächster Hop-Server, an den ein Edgeserver eingehenden SIP-Datenverkehr für interne Server weiterleitet. Der Director authentifiziert eingehende Anforderungen vorab und leitet Sie an den privaten Pool oder Server des Benutzers weiter. Die Vorabauthenitifizierung in Director ermöglicht das Aussortieren von Anfragen, die von Benutzerkonten stammen, die in der Bereitstellung nicht bekannt sind. Ein Director unterstützt das Isolieren von Front-End-Servern vor bösartigem Datenverkehr wie Denial-of-Service-Angriffen (DOS). Wenn das Netzwerk bei einem solchen Angriff mit ungültigem externem Datenverkehr überflutet wird, endet der Datenverkehr beim Director.

  - **System Center Operations Manager wird bereitgestellt.**   Es wird empfohlen, die Integrität ihrer lync Server-Bereitstellung zu überwachen, um die Verfügbarkeit von Diensten für Endbenutzer sicherzustellen. Sie können lync mit dem System Center Operations Manager Management Pack für lync überwachen, das als kostenloser Download von Microsoft zur Verfügung steht. Mit dem Lync Management Pack erhalten Sie proaktiv Echtzeitwarnungen, sobald Probleme auftreten, können synthetische Transaktionen ausführen, um die Lync-Funktionalität von Ende zu Ende zu testen, Berichte zur Dienstverfügbarkeit erhalten usw. Dies hilft Ihnen bei der proaktiven Behandlung von Problemen mit Ihrer Bereitstellung, bevor diese für Endbenutzer spürbar werden.
    
    Diese Organisation hat einen System Center Operations Manager-Server an jedem zentralen Standort bereitgestellt.

</div>

<span> </span>

</div>

</div>

</div>

