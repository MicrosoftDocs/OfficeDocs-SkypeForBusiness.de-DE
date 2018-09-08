---
title: Referenztopologien für Skype für Business Server
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0453aeee-c41f-44e6-a6e0-aaace526ca08
description: Referenztopologien für Skype für Business Server, einschließlich Diagramme und Entscheidungen für große, mittlerer und kleine Unternehmen.
ms.openlocfilehash: 0e59b1461b30435f77726e38bd5599cac0922c9f
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23887619"
---
# <a name="reference-topologies-for-skype-for-business-server"></a>Referenztopologien für Skype für Business Server

Referenztopologien für Skype für Business Server, einschließlich Diagramme und Entscheidungen für große, mittlerer und kleine Unternehmen.

Die beste Skype für Business-Servertopologie für Sie hängt von der Größe Ihrer Organisation, den arbeitsauslastungen, die Sie bereitstellen möchten und die Anforderungen in Bezug auf hohe Verfügbarkeit und die Investitionskosten.

In diesem Abschnitt werden drei Beispiele für Referenztopologien sowie die Gründe beleuchtet, die hinter den Entscheidungen für die jeweilige Topologie standen.

## <a name="reference-topology-for-a-small-organization"></a>Referenztopologie für kleine Organisationen

Die Referenztopologie für kleine Organisationen zeigt, wie Sie eine robuste, hochverfügbare Lösung bereitstellen können, durch die Bereitstellung von lediglich drei Servern mit Skype für Business Server.

**Referenztopologie für kleine Organisationen**

![Referenztopologie mit drei Servern (Diagramm)](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology1.jpg)

- **Paar von Standard Edition-Server bereitgestellt** Diese Organisation umfasst 4.000 Benutzer an ihrem zentralen Standort. Sie haben zwei Standard Edition-Server bereitgestellt und miteinander zusammen, um hohe Verfügbarkeit und notfallwiederherstellung zu aktivieren. Jeder Server hostet 2.000 Benutzer, die Informationen zu allen Benutzern werden aber zwischen den beiden Servern synchronisiert. Fällt ein Server aus, kann ein Administrator ein Failover für die entsprechenden Benutzer ausführen, sodass sie mit minimaler Unterbrechung vom anderen Server gehostet werden. Weitere Informationen zu hoher Verfügbarkeit und Disaster Recovery-Funktionen in Skype für Business Server finden Sie unter [Planen für hohe Verfügbarkeit und notfallwiederherstellung in Skype für Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).

- **Empfehlung der Bereitstellung eines Edgeservers.** Auch wenn die Bereitstellung eines Edgeservers für interne Chats, für Anwesenheitsinformationen und für Konferenzen nicht erforderlich ist, wird sie selbst für kleine Bereitstellungen empfohlen. Sie können Ihre Skype für Business Server Investition durch Bereitstellen eines Edgeservers zum Bereitstellen von Service für Benutzer außerhalb der Firewalls der Organisation derzeit maximieren. Dies bietet folgende Vorteile:

  - Die organisationseigenen Benutzer können Skype für Business-Funktionen verwenden, wenn sie sich auf Reisen sind oder von zu Hause arbeiten.

  - Ihre Benutzer können externe Benutzer zur Teilnahme an Besprechungen einladen.

  - Wenn Sie ein Partner, Lieferanten oder Kundenorganisation, die auch Skype für Business Server verwendet wird, können Sie eine verbundbeziehung dieser Organisation bilden. Ihre Skype für Business Server-Bereitstellung würde dann Erkennung von Benutzern aus dieser verbundorganisations führt eine bessere Zusammenarbeit.

  - Ihre Benutzer können Chatnachrichten mit Benutzern von bestimmten öffentlichen Chatdiensten austauschen.

- **Ausfallsicherheit für Zweigstellen.** Diese Organisation ist ein Pilotprogramm des Enterprise-VoIP-Features von Skype für Business Server ausgeführt. Einige Benutzer verwenden Skype für Business Server als die alleinige VoIP-Lösung. Einige dieser pilot Enterprise-VoIP-Benutzer befinden sich am Zweigstellenstandort. Zweigstellenstandort hat keinen die Verbindung eine zuverlässige wide Area Network (WAN) am zentralen Standort, sodass es eine Survivable Branch Appliance bereitgestellt wird. Dank der Survivable Branch-Anwendung können die Benutzer in der Zweigstelle bei Ausfall der WAN-Verbindung weiterhin Anrufe tätigen und entgegennehmen (sowohl innerhalb der Organisation als auch über das Festnetz), die Voicemailfunktion nutzen und per Chat kommunizieren. Benutzer können darüber hinaus auch dann authentifiziert werden, wenn die WAN-Verbindung nicht verfügbar ist. Weitere Informationen finden Sie unter [Planen für Enterprise Voice Resiliency in Skype für Business Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md).

- **Exchange UM-Bereitstellung.** Dieser Referenztopologie enthält einen Exchange Unified Messaging (UM)-Server, der Microsoft Exchange Server nicht Skype für Business Server ausgeführt wird.

- **Office Web Apps Server.** Es wird empfohlen, in jeder Organisation, in der der Webkonferenzdienst verwendet wird, einen Office Web Apps Server oder eine Office Web Apps-Serverfarm bereitzustellen. Der Office Web Apps Server ermöglicht die Präsentation von PowerPoint-Folien in Webkonferenzen.

## <a name="reference-topology-for-a-medium-organization"></a>Referenztopologie für mittelständische Organisationen

Die Referenztopologie mit hoher Verfügbarkeit und einem einzelnen Rechenzentrum ist auf kleine bis mittelständische Organisationen mit einem zentralen Standort zugeschnitten. Die im folgenden Diagramm gezeigte exakte Topologie ist auf 20.000 Benutzer ausgelegt.

**Referenztopologie für mittelständige Organisationen**

![Referenztopologie für ein einziges Rechenzentrum (Diagramm)](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology2.jpg)

- **Möglichkeit, durch Hinzufügen zusätzlicher Front-End-Server weitere Benutzer zu unterstützen.** Die im Diagramm gezeigte Topologie umfasst drei Front-End-Server und kann daher bis zu 20.000 Benutzer unterstützen. Wenn Sie über einen einzelnen zentralen Standort und mehr Benutzer verfügen, können Sie dem Pool einfach weitere Front-End-Server hinzufügen. Die maximale Anzahl von Benutzern pro Pool beträgt 80.000 mit zwölf Front-End-Servern.

    Die Topologie mit einem einzelnen Standort kann jedoch noch mehr Benutzer unterstützen, wenn dem Standort ein weiterer Front-End-Pool hinzugefügt wird.

- **Möglichkeit, eine Notfallwiederherstellung hinzuzufügen.** Für diese Organisation hohe Verfügbarkeit für ihre Skype für Business Server-Dienste ist ein Feature erforderlich, Disaster Recovery ist jedoch nicht. Bietet eine hohe Verfügbarkeit der Pool Front-End-Servern, die sie bereitgestellt haben.

    Wenn die Fähigkeit zur Notfallwiederherstellung hinzugefügt werden soll, könnte die Organisation ein weiteres Rechenzentrum einrichten und dort einen weiteren Front-End-Pool hinzufügen, der dann mit dem Front-End-Pool im aktuellen Rechenzentrum kombiniert wird. Dadurch könnten die Administratoren bei einem Notfall, der den primären Pool betrifft, einen Failover der Benutzer auf den Sicherungspool durchführen.

- **Back-End-Servern werden gespiegelt.** Um weitere hohe Verfügbarkeit für Standardbenutzer Features bereitzustellen, hat die Organisation zwei gespiegelten Back-End-Servern für jeden Front-End-Pool bereitgestellt.

- **Optionen für die Monitoring Server-Datenbank.** Diese Organisation bereitgestellt hat, Überwachung, um sicherzustellen, dass die Qualität der Enterprise-VoIP-Anrufe und A / V-Konferenzen. Die Überwachung wird auf jedem Front-End-Server bereitgestellt und die Überwachungsdatenbank wird mit den Back-End-Servern verbunden. Außerdem werden Topologien unterstützt, in denen sich die Überwachungsdatenbank auf einem separaten Server befindet.

- **Hohe Verfügbarkeit für Edge-Server** In diesem Beispiel-Organisation mit 20.000 Benutzern wäre nur ein Edge-Server für die Leistung ausreichend. Es wird aber ein Pool mit zwei Edgeservern bereitgestellt, um hohe Verfügbarkeit sicherzustellen.

- **Optionen für Bereitstellungen an Zweigstellen.** Die Organisation in dieser Topologie verfügt über Enterprise-VoIP, die als ihre VoIP-Lösung bereitgestellt. Zweigniederlassung 1 hat keinen Link eine ausfallsichere WAN-Netzwerk (WAN) am zentralen Standort, dies ist eine Survivable Branch Appliance bereitgestellt, um zu gewährleisten, dass viele Skype für Business Server-Features für den Fall, dass die WAN-Verbindung zum zentralen Standort ausfällt. Zweigstelle 2 verfügt über eine ausfallsichere WAN-Verbindung, daher wird nur ein PSTN-Gateway benötigt. Das bereitgestellte PSTN-Gateway unterstützt die Medienumgehung, deshalb wird in Zweigstelle 2 kein Vermittlungsserver benötigt. Weitere Informationen finden Sie unter [Planen für Enterprise Voice Resiliency in Skype für Business Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md).

- **DNS-Lastenausgleich.** Der Front-End-Pool und der Edgeserver-Pool wurden zum DNS-Lastenausgleich für SIP-Datenverkehr konfiguriert. Auf diese Weise sind keine Hardwaregeräte zum Lastenausgleich für die Edgeserver erforderlich und Setup und Wartung der Hardwaregeräte zum Lastenausgleich für die weiteren Pools werden erheblich vereinfacht, da die Hardwaregeräte zum Lastenausgleich nur für HTTP-Datenverkehr benötigt werden. Weitere Informationen finden Sie unter (... /.. / plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing).

- **Exchange UM-Bereitstellung.** Dieser Referenztopologie enthält einen Exchange Unified Messaging (UM)-Server, der Microsoft Exchange Server nicht Skype für Business Server ausgeführt wird.

- **Office Web Apps Server.** Es wird empfohlen, in jeder Organisation, in der der Webkonferenzdienst verwendet wird, einen Office Web Apps Server oder eine Office Web Apps-Serverfarm bereitzustellen. Der Office Web Apps Server ermöglicht die Präsentation von PowerPoint-Folien in Webkonferenzen.

- **Möglichkeit, Directors hinzuzufügen.** Wenn diese Organisation die Sicherheit gegenüber Denial-of-Service-Angriffen erhöhen möchte, kann auch ein Director-Pool bereitgestellt werden. Ein Director ist eine separate, optionale Serverrolle in Skype für Business Server, der nicht privat Benutzerkonten, oder Anwesenheit oder Live Meeting-Dienste bereitstellen. Es dient als einen internen nächsten Hopservers, der ein Edge-Server eingehenden SIP-Datenverkehr für interne Server leitet. Der Director authentifiziert eingehende Anforderungen und leitet ihn zur home-Pool oder Server des Benutzers. Die Vorabauthentifizierung durch den Director ermöglicht das Verwerfen von Anfragen von Benutzerkonten, die der Bereitstellung nicht bekannt sind. Ein Director hilft bei Front-End-Servern wie Denial-of-Service (DoS) Angriffe bösartigem Datenverkehr zu isolieren. Wenn das Netzwerk mit ungültigen externen Datenverkehr in einem solchen Angriff übertragen wird, beendet der Datenverkehr des Directors.

- **System Center Operations Manager wird empfohlen.** Es wird empfohlen, dass Sie die Integrität Ihrer Skype für Business Server-Bereitstellung zur Sicherstellung der Verfügbarkeit für die Endbenutzer überwachen. Sie können das System Center Operations Manager Management Pack für Skype für Unternehmen verwenden, die als kostenloser Download von Microsoft verfügbar ist. Mit dem Skype for Business Management Pack können Sie unter anderem bei auftretenden Problemen proaktiv Echtzeitwarnungen empfangen, synthetische Transaktionen zum Testen der End-to-End-Funktionalität von Skype for Business ausführen und Berichte über die Dienstverfügbarkeit erhalten. Dadurch können Sie proaktiv auf Probleme mit Ihrer Bereitstellung reagieren, bevor Endbenutzer davon betroffen sind.

## <a name="reference-topology-for-a-large-organization"></a>Referenztopologie für große Organisationen

Die Referenztopologie für eine große Organisation mit mehreren Rechenzentren gilt für jede Organisationsgröße mit mehr als einem zentralen Standort. Die genaue Topologie im folgenden Diagramm bezieht sich auf eine Organisation mit 50.000 Benutzern, von denen sich 20.000 Benutzer am zentralen Standort A, 20.000 Benutzer am zentralen Standort B und insgesamt 10.000 Benutzer am zentralen Standort C und an Zweigstellen befinden. Der in diesem Diagramm gezeigte Topologietyp kann Organisationen mit einer beliebigen Benutzeranzahl umfassen.

Zusätzlich zu den hohe Verfügbarkeit von Pools von Front-End-Servern bereitgestellt fügt diese Topologie Unterstützung von Disaster Recovery. Der Front-End-Pools an zentralen Standorten A und B sind miteinander verbunden. Wenn einer dieser Pools ausfällt, kann der Administrator die Dienste für die betroffenen Benutzer in den kombinierten Pool des nicht betroffenen Standorts verlagern.

Diese Topologie wird in mehreren Diagrammen gezeigt. Zunächst sehen Sie einen Überblick, gefolgt von detaillierten Ansichten der zentralen Standorte.

**Überblick über die Referenztopologie für große Organisationen mit mehreren Rechenzentren**

![Referenztopologie für mehrere Rechenzentren](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-1-new.jpg)

**Referenztopologie für große Organisationen: Detaillierte Ansicht des zentralen Standorts A**

![Topologie 3-2](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-2.jpg)

**Referenztopologie für große Organisationen: Detaillierte Ansicht des zentralen Standorts B**

![Topologie 3-3](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-3.jpg)

**Referenztopologie für große Organisationen: Detaillierte Ansicht des zentralen Standorts C**

![Topologie 3-4](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-4.jpg)

- **Front-End-Pools sind zum Aktivieren von Disaster Recovery verbunden.** Der Front-End-Pools an Standort A und Standort B sind miteinander, Disaster Recovery in der Unterstützung von verbunden. Wenn der Pool an einem Standort ein Fehler auftritt, kann die Benutzer von dieser Site auf den paired Front-End-Pool am anderen Standort mit mindestens Unterbrechung des Dienstes für Benutzer der Administrator Failover. Jeder dieser beiden Front-End-Pools hat sechs Server, was ausreicht, um alle 40.000 Benutzer beider Pools im Fall eines Failovers zu unterstützen. Weitere Informationen finden Sie unter [Planen für hohe Verfügbarkeit und notfallwiederherstellung in Skype für Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).

- **Back-End-Servern werden gespiegelt.** Um weitere hohe Verfügbarkeit für Standardbenutzer Features bereitzustellen, hat die Organisation zwei gespiegelten Back-End-Servern für jeden Front-End-Pool bereitgestellt. Dies ist eine optionale Topologie und können Sie festlegen, stattdessen einen einzelnen Back End-Server bereitstellen. SQL-clustering und AlwaysOn Availability Groups werden ebenfalls unterstützt. Weitere Informationen finden Sie unter [hohe Verfügbarkeit von Back-End-Server in Skype für Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md).

- **Verwenden von Standard Edition-Server an einem Zweigstellenstandort.** Diese Organisation stuft Standort C als Zweigstelle ein, da er nur 600 Mitarbeiter umfasst. Die dortigen Benutzer halten aber untereinander viele A/V-Konferenzen ab. Wenn es in Skype für Business Server als Branch-Website bereitgestellt wurde, führen die Medien für diesen Konferenzen über das WAN-Netzwerk (WAN) zu und von einem zentralen Standort, der einem Front-End-Server bereitgestellt wurde. Um diese potenziellen Auslastung der Bandbreite zu vermeiden, haben sie ein Paar von Standard Edition-Servern an diesem Standort installiert, die diese Konferenzen gehostet wird. Und da Standard Edition-Server installiert sind, Skype für Business Server per Definition hält es einem zentralen Standort und als solche in Topologie-Generator und Planungstool behandelt wird.

    Nur einen einzelnen Standard Edition-Server ausreichen hier aus Leistungsgründen ist, aber die Organisation hat zwei bereitgestellt und miteinander zusammen, um hohe Verfügbarkeit für den Fall, dass ein Server ausfällt.

    Auch wenn Standort C als zentraler Standort betrachtet wird, müssen Sie dort keine Edgeserver bereitstellen. In diesem Beispiel verwendet Standort C die an Standort A bereitgestellten Edgeserver.

- **Überwachung und Archivierung** Diese Organisation hat die Überwachung und Archivierung bereitgestellt. Wenn Sie die Überwachung und den Archivierungsserver bereitstellen, wird es auf jedem Front-End-Server ausgeführt. Die Datenbanken für diese Features können mit der Back-End-Datenbank verbunden, oder auf einem separaten Server befinden. Diese Organisation hat diese Datenbanken auf einem Server, der getrennt von den Back End-Servern im zentralen Standort b befindet. Hier die Datenbanken erhalten Überwachung und Archivierung Daten von den Front-End-Servern auf allen Websites.

- **Optionen für Bereitstellungen an Zweigstellen.** Diese Organisation hat tatsächlich über 50 Zweigniederlassungen, von denen nur, die zwei in die detaillierte Diagramme angezeigt werden. Zweigniederlassung 1 verfügt nicht über eine ausfallsichere WAN am zentralen Standort, zu verknüpfen, damit sie die Survivable Branch Appliances um bereitzustellen, dass Telefondienst für den Fall, dass die WAN-Verbindung zum zentralen Standort ausfällt bereitgestellt haben. Zweigniederlassung 2 verfügt jedoch über eine ausfallsichere WAN-Verbindung, damit nur vom Gateway eine public switched Telephone Network, (PSTN) benötigt. Das bereitgestellte PSTN-Gateway unterstützt die Medienumgehung, deshalb wird in Zweigstelle 2 kein Vermittlungsserver benötigt. Ausführliche Informationen zu entscheiden, was am Zweigstellenstandort installiert werden finden Sie unter [Planen für Enterprise Voice Resiliency in Skype für Business Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md).

- **SIP-Trunking und Vermittlungsserver.** Beachten Sie, dass am zentralen Standort B der Vermittlungsserver nicht gemeinsam mit den Front-End-Servern ausgeführt wird. Der Grund dafür ist, dass für Standorte mit SIP-Trunking ein eigenständiger Vermittlungsserver empfohlen wird. In den meisten anderen Fällen empfiehlt sich die gemeinsame Ausführung des Vermittlungsservers mit dem Front-End-Server. Ausführliche Informationen zu Mediation Server-Topologien finden Sie unter [Komponenten und Topologien für den Vermittlungsserver](https://technet.microsoft.com/library/71397168-36c3-4d21-b8ef-db6a751634ee.aspx) in der Planungsdokumentation.

- **Beständiger Chat bereitgestellt wird.** Diese Organisation hat die notwendig, den beständigen Chat aktivieren Server bereitgestellt. Es hat mehrere Persistent Chat-Front-End-Server auf beide Handle die Auslastung für die Anzahl der Benutzer im Pool, und hohen Verfügbarkeit bereitzustellen bereitgestellt. Es ist Kompatibilität für beständigen Chat bereitgestellt, und der Persistent-Chat-Speicher und dem Persistent Chat Compliance-Store auf separaten Servern befinden. Diese Informationsspeicher ausgeführt werden konnte, und können auch mit der Back-End-Server zusammengestellt werden, aber diese Organisation hat sich entschieden, um eine bessere Leistung bieten zu trennen.

    > [!NOTE]
    > Beständiger Chat wird steht in Skype für Business Server 2015 jedoch nicht mehr unterstützt in Skype Business Server 2019. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter [Weg von Skype für Unternehmen, die Microsoft-Teams](/microsoftteams/journey-skypeforbusiness-teams). Wenn Sie Persistent Chat verwenden müssen, sind Ihrer Auswahl an Benutzer, die diese Funktionalität Teams migrieren oder weiterhin Skype für Business Server 2015 verwenden.

- **DNS-Lastenausgleich.** Der Front-End-Pool und der Edgeserverpool nutzen den DNS-Lastenausgleich. Dadurch sind keine Hardwaregeräte zum Lastenausgleich für die interne Schnittstelle der Edgeserver erforderlich und der für Setup und Wartung der Hardwaregeräte zum Lastenausgleich für die weiteren Pools erforderliche Zeitraum wird erheblich verringert, da die Hardwaregeräte zum Lastenausgleich nur für HTTP-Datenverkehr benötigt werden. Weitere Informationen finden Sie unter (... /.. / plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing).

- **Exchange UM-Bereitstellung.** Skype für Business Server arbeitet mit beiden lokalen Bereitstellungen von Exchange Unified Messaging (UM) und gehostete Exchange UM. Zentraler Standort A enthält einen Exchange Unified Messaging (UM)-Server, der Microsoft Exchange Server nicht Skype für Business Server ausgeführt wird. Die Exchange UM-Funktionalität für Skype für Business Server auf den Front-End-Pool ausgeführt wird.

    Am zentralen Standort B wird gehostetes Exchange eingesetzt, daher wird die Exchange UM-Serverfunktionalität ebenfalls gehostet.

    Ausführliche Informationen zu Exchange UM finden Sie unter [On-Premises Exchange Unified Messaging Integration](https://technet.microsoft.com/library/e7c63a71-2d99-4aa9-b649-36c1a431bdf1.aspx) und [Hosted Exchange Unified Messaging Integration](https://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx) in der Planungsdokumentation.

- **Office Web Apps Server.** Es wird empfohlen, in jeder Organisation, in der der Webkonferenzdienst verwendet wird, einen Office Web Apps Server oder eine Office Web Apps-Serverfarm bereitzustellen. Sie könnten Bereitstellen einer einzelne Office Web Apps Server-Farm an einem Standort der Datenverkehr von allen Websites dient oder an jedem Standort bereitstellen. Der Office Web Apps Server ermöglicht die Präsentation von PowerPoint-Folien in Webkonferenzen.

- **Möglichkeit, Directors hinzuzufügen.** Wenn diese Organisation die Sicherheit im Hinblick auf Denial-of-Service-Angriffe erhöhen möchte, könnte sie auch einen Pool von Directors bereitstellen. Ein Director ist eine separate, optionale Serverrolle in Skype für Business Server, der nicht privat Benutzerkonten, oder Anwesenheit oder Live Meeting-Dienste bereitstellen. Es dient als einen internen nächsten Hopservers, der ein Edge-Server eingehenden SIP-Datenverkehr für interne Server leitet. Der Director authentifiziert eingehende Anforderungen und leitet ihn zur home-Pool oder Server des Benutzers. Die Vorabauthentifizierung durch den Director ermöglicht das Verwerfen von Anfragen von Benutzerkonten, die der Bereitstellung nicht bekannt sind. Ein Director hilft bei Front-End-Servern wie Denial-of-Service (DoS) Angriffe bösartigem Datenverkehr zu isolieren. Wenn das Netzwerk mit ungültigen externen Datenverkehr in einem solchen Angriff übertragen wird, beendet der Datenverkehr des Directors.

- **System Center Operations Manager wird empfohlen.** Es wird empfohlen, dass Sie die Integrität Ihrer Skype für Business Server-Bereitstellung zur Sicherstellung der Verfügbarkeit für die Endbenutzer überwachen. Sie können das System Center Operations Manager Management Pack für Skype für Unternehmen verwenden, die als kostenloser Download von Microsoft verfügbar ist. Mit dem Skype for Business Management Pack können Sie unter anderem bei auftretenden Problemen proaktiv Echtzeitwarnungen empfangen, synthetische Transaktionen zum Testen der End-to-End-Funktionalität von Skype for Business ausführen und Berichte über die Dienstverfügbarkeit erhalten. Dadurch können Sie proaktiv auf Probleme mit Ihrer Bereitstellung reagieren, bevor Endbenutzer davon betroffen sind.


