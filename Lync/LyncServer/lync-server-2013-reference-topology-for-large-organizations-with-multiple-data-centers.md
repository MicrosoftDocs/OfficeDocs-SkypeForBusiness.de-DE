---
title: 'Lync Server 2013: Referenztopologie für große Organisationen mit mehreren Rechenzentren'
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
ms.openlocfilehash: 56d9edde5ab097f3244919d6dd2c572b4a1dc112
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746885"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reference-topology-for-lync-server-2013-in-large-organizations-with-multiple-data-centers"></a>Referenztopologie für Lync Server 2013 für große Organisationen mit mehreren Rechenzentren

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-22_

Die Referenztopologie für eine große Organisation mit mehreren Rechenzentren gilt für jede Organisationsgröße mit mehr als einem zentralen Standort. Die genaue Topologie im folgenden Diagramm bezieht sich auf eine Organisation mit 50.000 Benutzern, von denen sich 20.000 Benutzer am zentralen Standort A, 20.000 Benutzer am zentralen Standort B und insgesamt 10.000 Benutzer am zentralen Standort C und an Zweigstellen befinden. Der in diesem Diagramm gezeigte Topologietyp kann Organisationen mit einer beliebigen Benutzeranzahl umfassen.

Neben der großen Verfügbarkeit, die von den Pools der Front-End-Server bereitgestellt wird, fügt diese Topologie Disaster Recovery-Unterstützung hinzu. Die Front-End-Pools an zentralen Standorten A und B sind zusammen gekoppelt. Wenn einer dieser Pools ausfällt, kann der Administrator die Dienste für die betroffenen Benutzer in den kombinierten Pool des nicht betroffenen Standorts verlagern.

Diese Topologie wird in mehreren Diagrammen gezeigt. Zunächst sehen Sie einen Überblick, gefolgt von detaillierten Ansichten der zentralen Standorte.

**Überblick über die Referenztopologie für große Organisationen mit mehreren Rechenzentren**

![Referenztopologie für mehrere Rechenzentren](images/Gg398797.471e1ce9-be11-44b9-9f4a-59e0551b7b30(OCS.15).jpg "Referenztopologie für mehrere Rechenzentren")

**Referenztopologie für große Organisationen: Detaillierte Ansicht des zentralen Standorts A**

![dab33f19-e77b-42da-9047-858fb9851264](images/Gg398797.dab33f19-e77b-42da-9047-858fb9851264(OCS.15).jpg "dab33f19-e77b-42da-9047-858fb9851264")

**Referenztopologie für große Organisationen: Detaillierte Ansicht des zentralen Standorts B**

![5ccaf1d4-bd53-4cb7-96fe-723147334e7f](images/Gg398797.5ccaf1d4-bd53-4cb7-96fe-723147334e7f(OCS.15).jpg "5ccaf1d4-bd53-4cb7-96fe-723147334e7f")

**Referenztopologie für große Organisationen: Detaillierte Ansicht des zentralen Standorts C**

![7238ca40-340c-491f-b497-ddc2665dadb6](images/Gg398797.7238ca40-340c-491f-b497-ddc2665dadb6(OCS.15).jpg "7238ca40-340c-491f-b497-ddc2665dadb6")

  - **Front-End-Pools sind gekoppelt, um eine Disaster Recovery zu ermöglichen.**    Die Front-End-Pools an Standort a und Standort B sind miteinander gekoppelt, um Disaster Recovery-Unterstützung bereitzustellen. Wenn der Pool an einer Website fehlschlägt, kann der Administrator für die Benutzer von dieser Website an den gekoppelten Front-End-Pool am anderen Standort ein Failover durchführen, wobei für die Benutzer mindestens eine Dienstunterbrechung erforderlich ist. Jeder dieser beiden Front-End-Pools verfügt über sechs Server, was für alle 40.000-Benutzer in beiden Pools ausreichend ist, wenn ein Failover durchgeführt wird. Weitere Informationen finden Sie unter [Planen von höchst Verfügbarkeit und Disaster Recovery in lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

  - **Back-End-Server werden gespiegelt**   , um eine höhere Verfügbarkeit für grundlegende Benutzer Features bereitzustellen, hat die Organisation ein gespiegeltes paar von Back-End-Servern für jeden Front-End-Pool bereitgestellt. Hierbei handelt es sich um eine optionale Topologie, und Sie können stattdessen einen einzelnen Back-End-Server bereitstellen.

  - **Verwenden des Standard Edition-Servers an einer Zweigstelle**    Diese Organisation berücksichtigt Website C als Zweigstellen Website, da Sie nur 600 Mitarbeiter hat. Allerdings haben die Benutzer dort viele A/V-Konferenzen unter sich. Wenn Sie in lync Server als Verzweigungs Website bereitgestellt wurde, würden die Medien für diese Konferenzen über das WAN (Wide Area Network) zu und von einem zentralen Standort aus ausgeführt werden, auf dem ein Front-End-Server bereitgestellt wurde. Um diese potenzielle Bandbreitenauslastung zu vermeiden, haben Sie auf dieser Website ein paar Standard Edition-Server installiert, auf denen diese Konferenzen gehostet werden. Da die Standard Edition-Server dort installiert sind, sieht lync Server per Definition eine zentrale Website und wird als solche im Topologie-Generator und im Planungs Tool behandelt.
    
    Nur ein Standard Edition-Server würde hier die Leistung ausreichen, aber die Organisation hat zwei bereitgestellt und zusammengefügt, um eine höhere Verfügbarkeit zu gewährleisten, wenn ein Server ausfällt.
    
    Auch wenn Standort C als zentraler Standort betrachtet wird, müssen Sie dort keine Edgeserver bereitstellen. In diesem Beispiel verwendet Standort C die an Standort A bereitgestellten Edgeserver.

  - **Überwachung und Archivierung**   diese Organisation hat sowohl die Überwachung als auch die Archivierung bereitgestellt. Wenn Sie die Überwachung oder Archivierung bereitstellen, wird Sie auf jedem Front-End-Server ausgeführt. Die Datenbanken für diese Features können mit der Back-End-Datenbank oder auf einem separaten Server gespeichert werden. Diese Organisation hat diese Datenbanken auf einem Server getrennt von den Back-End-Servern auf dem zentralen Standort B lokalisiert. Die Datenbanken hier empfangen Überwachungs-und Archivierungsdaten von den Front-End-Servern an allen Standorten.

  - **Bereitstellungsoptionen für Verzweigungs Websites**    Diese Organisation verfügt tatsächlich über mehr als 50 Zweigstellen, von denen nur drei in den detaillierten Diagrammen angezeigt werden. Die Zweigstellen 1 und 3 verfügen nicht über eine stabile WAN-Verbindung mit dem zentralen Standort, sodass Sie über Survivable Branch-Appliances bereitgestellt werden, um einen Telefondienst bereitzustellen, falls die WAN-Verbindung zum zentralen Standort ausfällt. Branch Site 2 hat jedoch eine stabile WAN-Verbindung, sodass Sie nur ein öffentliches Switched Telephone Network (PSTN)-Gateway benötigen. Das dort bereitgestellte PSTN-Gateway unterstützt die medienumgehung, sodass auf dem Zweigstellenstandort B kein Vermittlungs Server erforderlich ist. Details zur Entscheidung, was Sie an einer Zweigstelle installieren sollten, finden Sie unter [Planen der Enterprise-VoIP-Resilienz in lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md) in der Planungsdokumentation.

  - **SIP-Trunking-und Vermittlungs Server**    Beachten Sie, dass der Vermittlungs Server am zentralen Standort B nicht mit den Front-End-Servern bereit steht. Der Grund dafür ist, dass für Standorte mit SIP-Trunking ein eigenständiger Vermittlungsserver empfohlen wird. In den meisten anderen Fällen empfiehlt sich die gemeinsame Ausführung des Vermittlungsservers mit dem Front-End-Server. Details zu Mediation Server-Topologien finden Sie unter [Komponenten und Topologien für Mediation Server in lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) in der Planungsdokumentation.

  - **Beständiger Chat wird bereitgestellt.**    Diese Organisation hat die erforderlichen Server zum Aktivieren des beständigen Chats bereitgestellt. Es wurden mehrere beständige Chat-Front-End-Server bereitgestellt, um die Last für die Anzahl der Benutzer im Pool zu behandeln und eine hohe Verfügbarkeit bereitzustellen. Darüber hinaus wurde Compliance für beständigen Chat bereitgestellt und der beständige Chat Speicher und der Compliance-Speicher für beständigen Chat auf separaten Servern gespeichert. Diese Stores können mit dem Back-End-Server kombiniert werden, aber diese Organisation hat sich entschieden, diese zu trennen, um eine bessere Leistung zu gewährleisten.

  - **DNS-Lastenausgleich**    Der Front-End-Pool und der Edge-Server Pool. Dadurch sind keine Hardwaregeräte zum Lastenausgleich für die interne Schnittstelle der Edgeserver erforderlich und der für Setup und Wartung der Hardwaregeräte zum Lastenausgleich für die weiteren Pools erforderliche Zeitraum wird erheblich verringert, da die Hardwaregeräte zum Lastenausgleich nur für HTTP-Datenverkehr benötigt werden. Details zum DNS-Lastenausgleich finden Sie unter [DNS-Lastenausgleich in lync Server 2013](lync-server-2013-dns-load-balancing.md) in der Planungsdokumentation.

  - **Exchange um-Bereitstellung.**   Lync Server funktioniert sowohl mit *lokalen* Bereitstellungen von Exchange Unified Messaging (um) als auch mit *Hosted* Exchange um. Der zentrale Standort A umfasst einen Exchange Unified Messaging (um)-Server, auf dem Microsoft Exchange Server ausgeführt wird, nicht lync Server. Die Exchange um-Funktionalität für lync Server wird im Front-End-Pool ausgeführt.
    
    Am zentralen Standort B wird gehostetes Exchange eingesetzt, daher wird die Exchange UM-Serverfunktionalität ebenfalls gehostet.
    
    Ausführliche Informationen zu Exchange um finden Sie unter [Planen der Exchange Unified Messaging-Integration in lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) und [gehostete Exchange Unified Messaging-Integration in lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) in der Planning-Dokumentation.

  - **Office Web Apps-Server.**   Es wird empfohlen, in jeder Organisation, in der der Webkonferenzdienst verwendet wird, einen Office Web Apps Server oder eine Office Web Apps-Serverfarm bereitzustellen. Sie können eine einzelne Office Web Apps-Server Farm auf einer Website bereitstellen, die Datenverkehr von allen Websites dient, oder Sie auf jeder Website bereitstellen. Der Office Web Apps Server ermöglicht die Präsentation von PowerPoint-Folien in Webkonferenzen. Weitere Informationen finden Sie unter [Konfigurieren der Integration in Office Web Apps Server und lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

  - **Directors können hinzugefügt werden.**   Wenn diese Organisation die Sicherheit gegen Denial-of-Service-Angriffe erhöhen möchte, könnte Sie auch einen Pool von Directors bereitstellen. Bei einem Director handelt es sich um eine separate, optionale Serverrolle in lync Server, auf der keine Benutzerkonten zu Hause sind, oder Anwesenheits-oder Konferenzdienste bereitstellen. Sie fungiert als interner Server für den nächsten Hop, auf dem ein Edgeserver eingehenden SIP-Datenverkehr für interne Server weiterleitet. Der Director authentifiziert eingehende Anforderungen vorab und leitet Sie an den privaten Pool oder Server des Benutzers weiter. Die Vorabauthentifizierung durch den Director ermöglicht das Verwerfen von Anfragen von Benutzerkonten, die der Bereitstellung nicht bekannt sind. Ein Director hilft, Front-End-Server vor böswilligem Datenverkehr zu isolieren, wie DOS-Attacken (Denial-of-Service). Wenn das Netzwerk bei einem solchen Angriff mit einem ungültigen externen Datenverkehr überflutet wird, endet der Datenverkehr beim Director.

  - **System Center Operations Manager wird bereitgestellt.**   Wir empfehlen, dass Sie den Status Ihrer lync Server-Bereitstellung überwachen, um die Dienstverfügbarkeit für Endbenutzer zu gewährleisten. Sie können lync mit dem System Center Operations Manager-Management Pack für lync überwachen, das als kostenloser Download von Microsoft zur Verfügung steht. Mit dem lync-Management Pack können Sie proaktiv Echtzeitbenachrichtigungen erhalten, wenn Probleme auftreten, synthetische Transaktionen ausführen, um die End-to-End-lync-Funktionalität zu testen, Berichte für die Dienstverfügbarkeit abzurufen usw. Dadurch können Sie proaktiv auf Probleme mit Ihrer Bereitstellung reagieren, bevor Endbenutzer davon betroffen sind.
    
    Diese Organisation hat einen System Center Operations Manager-Server an jedem zentralen Standort bereitgestellt.

</div>

<span> </span>

</div>

</div>

</div>

