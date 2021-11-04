---
title: Referenztopologien für Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0453aeee-c41f-44e6-a6e0-aaace526ca08
description: Referenztopologien für Skype for Business Server, einschließlich Diagrammen und Entscheidungen für große, mittlere und kleine Organisationen.
ms.openlocfilehash: 270814a8a4dacccdec8919a0e31c9c6098603493
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60762103"
---
# <a name="reference-topologies-for-skype-for-business-server"></a>Referenztopologien für Skype for Business Server

Referenztopologien für Skype for Business Server, einschließlich Diagrammen und Entscheidungen für große, mittlere und kleine Organisationen.

Die beste Skype for Business Server Topologie für Sie hängt von der Größe Ihrer Organisation, den Workloads, die Sie bereitstellen möchten, und Ihren Einstellungen für hohe Verfügbarkeit im Vergleich zu den Kosten der Investition ab.

In diesem Abschnitt werden drei Beispielreferenztopologien beschrieben, einschließlich der Gründe für viele der Entscheidungen, die in jeder Topologie berücksichtigt wurden.

## <a name="reference-topology-for-a-small-organization"></a>Referenztopologie für eine kleine Organisation

Die Referenztopologie für kleine Organisationen zeigt, wie Sie eine stabile, hoch verfügbare Lösung bereitstellen können, indem Sie nur drei Server bereitstellen, auf denen Skype for Business Server ausgeführt wird.

**Referenztopologie für kleine Organisationen**

![Referenztopologie zur Bereitstellung von drei Servern ( Diagramm).](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology1.jpg)

- **Bereitgestelltes Standard Edition-Serverpaar** Diese Organisation hat 4.000 Benutzer an ihrem zentralen Standort. Sie haben zwei Standard Edition-Server bereitgestellt und kombiniert, um hohe Verfügbarkeit und Notfallwiederherstellung zu ermöglichen. Jeder Server verfügt über 2.000 Benutzer, informationen zu allen Benutzern werden jedoch zwischen den beiden Servern synchronisiert. Wenn einer ausfällt, kann ein Administrator diese Benutzer, die vom anderen Server bedient werden sollen, mit einem Minimum an Unterbrechungen für die Benutzer außer Kraft setzen. Weitere Informationen zu Features für hohe Verfügbarkeit und Notfallwiederherstellung in Skype for Business Server finden Sie unter [Plan for high availability and disaster recovery in Skype for Business Server.](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)

- **Empfehlung zur Bereitstellung eines Edgeservers.** Wenngleich die Bereitstellung eines Edgeservers für das interne Instant Messaging, für Anwesenheitsinformationen und Konferenzen nicht erforderlich ist, wird sie selbst für kleine Bereitstellung empfohlen. Sie können Ihre Skype for Business Server Investition maximieren, indem Sie einen Edgeserver bereitstellen, um Benutzern, die sich derzeit außerhalb der Firewalls Ihrer Organisation befinden, Dienste bereitzustellen. Hierdurch bieten sich folgende Vorteile:

  - Die eigenen Benutzer Ihrer Organisation können Skype for Business Server Funktionen verwenden, wenn sie von zu Hause aus arbeiten oder unterwegs sind.

  - Ihre Benutzer können externe Benutzer zur Teilnahme an Besprechungen einladen.

  - Wenn Sie über eine Partner-, Lieferanten- oder Kundenorganisation verfügen, die auch Skype for Business Server verwendet, können Sie eine Verbundbeziehung mit dieser Organisation bilden. Ihre Skype for Business Server Bereitstellung würde dann Benutzer aus dieser Verbundorganisation erkennen, was zu einer besseren Zusammenarbeit führt.

  - Ihre Benutzer können Chatnachrichten mit Benutzern einiger öffentlicher Chatdienste austauschen.

- **Ausfallsicherheit für Zweigstellen.** Diese Organisation führt ein Pilotprogramm des Enterprise-VoIP Features von Skype for Business Server aus. Einige Benutzer verwenden Skype for Business Server als einzige Sprachlösung. Einige dieser Enterprise-VoIP Pilotbenutzer befinden sich an der Zweigstelle. Der Zweigstellenstandort verfügt nicht über eine zuverlässige WAN-Verbindung (Wide Area Network) mit dem zentralen Standort, sodass dort eine Survivable Branch Appliance bereitgestellt wird. Wenn die WAN-Verbindung ausfällt, können Benutzer am Zweigstellenstandort weiterhin Anrufe tätigen und empfangen (sowohl Anrufe innerhalb der Organisation als auch PSTN-Anrufe), über Voicemailfunktionen verfügen und mit Chatnachrichten von zwei Teilnehmern kommunizieren. Benutzer können darüber hinaus auch dann authentifiziert werden, wenn die WAN-Verbindung nicht verfügbar ist. Weitere Informationen finden Sie unter [Plan for Enterprise-VoIP resiliency in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md).

- **Exchange UM-Bereitstellung.** Diese Referenztopologie enthält einen Exchange Unified Messaging (UM)-Server, der Microsoft Exchange Server und nicht Skype for Business Server ausgeführt wird.

- **Office Web Apps Server.** Wir empfehlen die Bereitstellung eines Office Web Apps Servers oder einer Office Web Apps Server-Farm in allen Organisation, die Webkonferenzen unterstützen. Office Web Apps Server ermöglicht die Präsentation PowerPoint Folien in Webkonferenzen.

## <a name="reference-topology-for-a-medium-organization"></a>Referenztopologie für eine mittlere Organisation

Die Referenztopologie mit hoher Verfügbarkeit und einem einzelnen Rechenzentrum ist auf kleine bis mittelständische Organisationen mit einem zentralen Standort zugeschnitten. Die genaue Topologie im folgenden Diagramm ist für eine Organisation mit 20.000 Benutzern vorgesehen.

**Referenztopologie für mittlere Organisationen**

![Referenztopologie für einzelnes Rechenzentrumsdiagramm.](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology2.jpg)

- **Möglichkeit zur Unterstützung weiterer Benutzer durch das Hinzufügen zusätzlicher Front-End-Server.** Die genaue Topologie in diesem Diagramm verfügt über drei Front-End-Server, um 20.000 Benutzer zu unterstützen. Wenn Sie über einen zentralen Standort und mehr Benutzer verfügen, können Sie dem Pool einfach weitere Front-End-Server hinzufügen. Die maximale Anzahl von Benutzern pro Pool beträgt 80.000 mit zwölf Front-End-Servern.

    Die Topologie mit einem einzelnen Standort kann jedoch noch mehr Benutzer unterstützen, wenn dem Standort ein weiterer Front-End-Pool hinzugefügt wird.

- **Die Notfallwiederherstellung kann hinzugefügt werden.** Für diese Organisation ist die hohe Verfügbarkeit für ihre Skype for Business Server Dienste ein erforderliches Feature, die Notfallwiederherstellung jedoch nicht. Der bereitgestellte Pool von Front-End-Servern bietet hohe Verfügbarkeit.

    Wenn sie eine Notfallwiederherstellungsmöglichkeit hinzufügen möchten, könnten sie erwägen, ein weiteres Rechenzentrum einzurichten und dort einen anderen Front-End-Pool hinzuzufügen und ihn mit dem Front-End-Pool in ihrem aktuellen Rechenzentrum zu koppeln. Wenn sich dann ein Notfall auf ihren primären Pool auswirkte, könnten die Administratoren Benutzer in den Sicherungspool übergehen.

- **Back-End-Server werden gespiegelt** Um eine höhere Verfügbarkeit für grundlegende Benutzerfeatures bereitzustellen, hat die Organisation ein gespiegeltes Back-End-Serverpaar für jeden Front-End-Pool bereitgestellt.

- **Optionen für die Monitoring Server-Datenbank.** Diese Organisation hat die Überwachung bereitgestellt, um die Qualität von Enterprise-VoIP Anrufen und A/V-Konferenzen sicherzustellen. Die Überwachung wird auf jedem Front-End-Server bereitgestellt, und die Überwachungsdatenbank wird mit den Back-End-Servern verbunden. Wir unterstützen auch Topologien, in denen sich die Überwachungsdatenbank auf einem separaten Server befindet.

- **Hohe Verfügbarkeit des Edgeservers** In dieser Beispielorganisation mit 20.000 Benutzern würde nur ein Edgeserver für die Leistung ausreichen. Sie haben jedoch einen Pool von zwei Edgeservern bereitgestellt, um hohe Verfügbarkeit zu gewährleisten.

- **Optionen für Bereitstellungen an Zweigstellenstandorten.** Die Organisation in dieser Topologie hat Enterprise-VoIP als ihre VoIP-Lösung bereitgestellt. Zweigstelle 1 verfügt nicht über eine ausfallsichere WAN-Verbindung (Wide Area Network) mit dem zentralen Standort, sodass eine Survivable Branch Appliance bereitgestellt wurde, um viele Skype for Business Server Features aufrechtzuerhalten, falls die WAN-Verbindung zum zentralen Standort unterbrochen wird. Zweigstellenstandort 2 verfügt über eine ausfallsichere WAN-Verbindung, daher wird nur ein PSTN-Gateway benötigt. Das bereitgestellte PSTN-Gateway unterstützt die Medienumgehung, deshalb wird an Zweigstellenstandort 2 kein Vermittlungsserver benötigt. Weitere Informationen finden Sie unter [Plan for Enterprise-VoIP resiliency in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md).

- **DNS-Lastenausgleich.** Der Front-End-Pool und der Edgeserverpool verfügen über einen DNS-Lastenausgleich für SIP-Datenverkehr. Auf diese Weise sind keine Hardwaregeräte zum Lastenausgleich für die Edgeserver erforderlich, und Setup und Wartung der Hardwaregeräte zum Lastenausgleich für die weiteren Pools werden erheblich vereinfacht, da die Hardwaregeräte zum Lastenausgleich nur für HTTP-Datenverkehr benötigt werden. Weitere Informationen finden Sie unter [DNS-Lastenausgleich.](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing)

- **Exchange UM-Bereitstellung.** Diese Referenztopologie enthält einen Exchange Unified Messaging (UM)-Server, der Microsoft Exchange Server und nicht Skype for Business Server ausgeführt wird.

- **Office Web Apps Server.** Wir empfehlen die Bereitstellung eines Office Web Apps Servers oder einer Office Web Apps Server-Farm in allen Organisation, die Webkonferenzen unterstützen. Mit Office Web Apps Server können Powerpoint-Folien in Webkonferenzen präsentiert werden.

- **Directors können hinzugefügt werden.** Wenn diese Organisation dazu beitragen möchte, die Sicherheit vor Denial-of-Service-Angriffen zu erhöhen, könnte sie auch einen Pool von Directors bereitstellen. Ein Director ist eine separate, optionale Serverrolle in Skype for Business Server, die keine Benutzerkonten verwaltet oder Anwesenheits- oder Konferenzdienste bereitstellt. Es dient als interner nächster Hopserver, an den ein Edgeserver eingehenden SIP-Datenverkehr weiterleitet, der für interne Server bestimmt ist. Der Director authentifiziert eingehende Anforderungen vorab und leitet sie an den Heimpool oder Server des Benutzers weiter. Die Vorabauthenitifizierung in Director ermöglicht das Aussortieren von Anfragen, die von Benutzerkonten stammen, die in der Bereitstellung nicht bekannt sind. Ein Director hilft dabei, Front-End-Server vor bösartigem Datenverkehr wie Denial-of-Service (DoS)-Angriffen zu schützen. Wenn das Netzwerk bei einem solchen Angriff mit ungültigen externen Datenverkehr überschwemmt wird, endet der Datenverkehr beim Director.

- **System Center Operations Manager wird empfohlen.** Es wird empfohlen, den Status Ihrer Skype for Business Server-Bereitstellung zu überwachen, um die Dienstverfügbarkeit für Endbenutzer sicherzustellen. Sie können das System Center Operations Manager Management Pack für Skype for Business verwenden, das als kostenloser Download von Microsoft zur Verfügung steht. Mit dem Skype for Business Management Pack können Sie proaktiv Echtzeitwarnungen erhalten, wenn Probleme auftreten, synthetische Transaktionen ausführen, um End-to-End-Skype for Business-Funktionen zu testen, Berichte zur Dienstverfügbarkeit zu erhalten usw. Dies hilft Ihnen bei der proaktiven Behandlung von Problemen mit Ihrer Bereitstellung, bevor diese für Endbenutzer spürbar werden.

## <a name="reference-topology-for-a-large-organization"></a>Referenztopologie für eine große Organisation

Die Referenztopologie für eine große Organisation mit mehreren Rechenzentren gilt für jede Organisationsgröße mit mehr als einem zentralen Standort. Die genaue Topologie in dem folgenden Diagramm bezieht sich auf eine Organisation mit 50.000 Benutzern, von denen sich 20.000 Benutzer am zentralen Standort A, 20.000 Benutzer am zentralen Standort B und insgesamt 10.000 Benutzer am zentralen Standort C und an Zweigstellenstandorten befinden. Der in diesem Diagramm gezeigte Topologietyp kann Organisationen mit einer beliebigen Benutzeranzahl umfassen.

Zusätzlich zur hohen Verfügbarkeit durch Pools von Front-End-Servern bietet diese Topologie Unterstützung für die Notfallwiederherstellung. Die Front-End-Pools an den zentralen Standorten A und B sind miteinander gekoppelt. Wenn einer dieser Pools ausfällt, kann der Administrator die Dienste für die betroffenen Benutzer in den kombinierten Pool des nicht betroffenen Standorts verlagern.

Diese Topologie wird in mehreren Diagrammen gezeigt. Zunächst sehen Sie einen Überblick, gefolgt von detaillierten Ansichten der zentralen Standorte.

**Überblick über die Referenztopologie für große Organisationen mit mehreren Rechenzentren**

![Referenztopologie für mehrere Rechenzentren.](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-1-new.jpg)

**Referenztopologie für große Organisationen: Detaillierte Ansicht des zentralen Standorts A**

![Topologie 3-2.](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-2.jpg)

**Referenztopologie für große Organisationen: Detaillierte Ansicht des zentralen Standorts B**

![Topologie 3-3.](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-3.jpg)

**Referenztopologie für große Organisationen: Detaillierte Ansicht des zentralen Standorts C**

![Topologie 3-4.](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-4.jpg)

- **Front-End-Pools werden gekoppelt, um die Notfallwiederherstellung zu aktivieren.** Die Front-End-Pools an Standort A und Standort B sind miteinander gekoppelt, um Unterstützung für die Notfallwiederherstellung bereitzustellen. Wenn der Pool an einem Standort fehlschlägt, kann der Administrator die Benutzer von diesem Standort in den gepaarten Front-End-Pool am anderen Standort mit einer minimalen Dienstunterbrechung für Benutzer übergehen. Jeder dieser beiden Front-End-Pools hat sechs Server, was ausreicht, um alle 40.000 Benutzer beider Pools im Fall eines Failovers zu unterstützen. Weitere Informationen finden Sie unter [Plan for high availability and disaster recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).

- **Back-End-Server werden gespiegelt** Um eine höhere Verfügbarkeit für grundlegende Benutzerfeatures bereitzustellen, hat die Organisation ein gespiegeltes Back-End-Serverpaar für jeden Front-End-Pool bereitgestellt. Dies ist eine optionale Topologie, und Sie können stattdessen einen einzelnen Back-End-Server bereitstellen. SQL Clustering- und AlwaysOn-Verfügbarkeitsgruppen werden ebenfalls unterstützt. Weitere Informationen finden Sie unter [Back-End-Server hohe Verfügbarkeit in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md).

- **Verwenden Standard Edition Servers an einem Zweigstellenstandort.** Diese Organisation stuft Standort C als Zweigstellenstandort ein, da er nur 600 Mitarbeiter umfasst. Die dortigen Benutzer halten jedoch untereinander viele A/V-Konferenzen ab. Wenn sie in Skype for Business Server als Zweigstelle bereitgestellt wurde, würden die Medien für diese Konferenzen über das Wan (Wide Area Network) zu und von einem zentralen Standort mit bereitgestellten Front-End-Servern ausgeführt. Um diese potenzielle Bandbreitenlast zu vermeiden, haben sie ein Paar Standard Edition Server an diesem Standort installiert, die diese Konferenzen hosten. Und da Standard Edition Server dort installiert sind, betrachtet Skype for Business Server ihn per Definition als zentralen Standort und wird im Topologie-Generator und im Planungstool als solcher behandelt.

    Hier reicht nur ein Standard Edition Server für die Leistung aus, aber die Organisation hat zwei bereitgestellt und kombiniert, um eine hohe Verfügbarkeit für den Fall zu gewährleisten, dass ein Server ausfällt.

    Auch wenn Standort C als zentraler Standort betrachtet wird, müssen Sie dort keine Edgeserver bereitstellen. In diesem Beispiel verwendet Standort C die an Standort A bereitgestellten Edgeserver.

- **Überwachung und Archivierung** Diese Organisation hat sowohl die Überwachung als auch die Archivierung bereitgestellt. Wenn Sie die Überwachung oder Archivierung bereitstellen, wird sie auf jedem Front-End-Server ausgeführt. Die Datenbanken für diese Features können mit der Back-End-Datenbank verbunden werden oder sich auf einem separaten Server befinden. Diese Organisation hat diese Datenbanken auf einem Server getrennt von den Back-End-Servern am zentralen Standort B gespeichert. Die Datenbanken hier empfangen Überwachungs- und Archivierungsdaten von den Front-End-Servern an allen Standorten.

- **Optionen für Bereitstellungen an Zweigstellenstandorten.** Diese Organisation verfügt tatsächlich über mehr als 50 Zweigstellen, von denen nur zwei in den detaillierten Diagrammen dargestellt sind. Zweigstelle 1 verfügt nicht über eine ausfallsichere WAN-Verbindung mit dem zentralen Standort, sodass Survivable Branch Appliances für die Bereitstellung von Telefondiensten bereitgestellt werden, falls die WAN-Verbindung zum zentralen Standort unterbrochen wird. Zweigstelle 2 verfügt jedoch über eine ausfallsichere WAN-Verbindung, sodass nur ein PSTN-Gateway (Public Switched Telephone Network) benötigt wird. Das bereitgestellte PSTN-Gateway unterstützt die Medienumgehung, deshalb wird an Zweigstellenstandort 2 kein Vermittlungsserver benötigt. Ausführliche Informationen zur Entscheidung darüber, was an einer Zweigstelle installiert werden soll, finden Sie unter [Plan for Enterprise-VoIP resiliency in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md).

- **SIP-Trunking und Vermittlungsserver.** Beachten Sie, dass an Standort B der Vermittlungsserver nicht gemeinsam mit den Front-End-Servern ausgeführt wird. Der Grund hierfür liegt darin, dass für Standorte mit SIP-Trunking ein eigenständiger Vermittlungsserver empfohlen wird. In den meisten anderen Fällen empfiehlt sich die gemeinsame Ausführung des Vermittlungsservers mit dem Front-End-Server. Ausführliche Informationen zu den Vermittlungsservertopologien finden Sie unter [Components and Topologies for Mediation Server](/previous-versions/office/lync-server-2013/lync-server-2013-components-and-topologies-for-mediation-server) in der Planungsdokumentation.

- **Beständiger Chat wird bereitgestellt.** Diese Organisation hat die Server bereitgestellt, die zum Aktivieren des beständigen Chats erforderlich sind. Es hat mehrere Front-End-Server für beständigen Chat bereitgestellt, um sowohl die Last für die Anzahl der Benutzer im Pool zu bewältigen als auch um hohe Verfügbarkeit zu gewährleisten. Außerdem wurde compliance für beständigen Chat bereitgestellt und die Store für beständigen Chat und die Kompatibilität für beständigen Chat Store auf separaten Servern gespeichert. Diese Speicher können verbunden sein und sogar mit dem Back-End-Server verbunden werden, aber diese Organisation hat sich entschieden, sie zu trennen, um eine bessere Leistung zu erzielen.

    > [!NOTE]
    > Beständiger Chat ist in Skype for Business Server 2015 verfügbar, wird jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter [Erste Schritte mit Ihrem Microsoft Teams Upgrade.](/microsoftteams/upgrade-start-here) Wenn Sie den beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktionalität zum Teams benötigen, oder Skype for Business Server 2015 weiterhin verwenden.

- **DNS-Lastenausgleich.** Der Front-End-Pool und der Edgeserverpool verwenden dns-Lastenausgleich. Auf diese Weise sind keine Hardwaregeräte zum Lastenausgleich für die interne Schnittstelle der Edgeserver erforderlich, und der für Setup und Wartung der Hardwaregeräte zum Lastenausgleich für die weiteren Pools erforderliche Zeitraum wird erheblich verringert, da die Hardwaregeräte zum Lastenausgleich nur für HTTP-Datenverkehr benötigt werden. Weitere Informationen finden Sie unter (.. /.. /plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing).

- **Exchange UM-Bereitstellung.** Skype for Business Server funktioniert sowohl mit lokalen Bereitstellungen von Exchange Unified Messaging (UM) als auch mit gehosteten Exchange UM. Der zentrale Standort A umfasst einen Exchange Unified Messaging (UM)-Server, der Microsoft Exchange Server und nicht Skype for Business Server ausgeführt wird. Die Exchange UM-Funktionalität für Skype for Business Server wird im Front-End-Pool ausgeführt.

    Am zentralen Standort B wird gehostetes Exchange eingesetzt, daher wird die Exchange UM-Serverfunktionalität ebenfalls gehostet.

    Ausführliche Informationen zu Exchange UM finden Sie in der Planungsdokumentation unter ["Lokale Exchange Unified Messaging-Integration](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-exchange-unified-messaging-integration) und [gehostete Exchange Unified Messaging-Integration".](/previous-versions/office/lync-server-2013/lync-server-2013-hosted-exchange-unified-messaging-integration)

- **Office Web Apps Server.** Wir empfehlen die Bereitstellung eines Office Web Apps Servers oder einer Office Web Apps Server-Farm in allen Organisation, die Webkonferenzen unterstützen. Sie können eine einzelne Office Web Apps Server-Farm an einem Standort bereitstellen, die den Datenverkehr von allen Standorten abwickelt, oder diese an allen Standorten bereitstellen. Mit Office Web Apps Server können Powerpoint-Folien in Webkonferenzen präsentiert werden.

- **Directors können hinzugefügt werden.** Wenn diese Organisation die Sicherheit im Hinblick auf Denial-of-Service-Angriffe erhöhen möchte, könnte sie auch einen Pool von Directors bereitstellen. Ein Director ist eine separate, optionale Serverrolle in Skype for Business Server, die keine Benutzerkonten verwaltet oder Anwesenheits- oder Konferenzdienste bereitstellt. Es dient als interner nächster Hopserver, an den ein Edgeserver eingehenden SIP-Datenverkehr weiterleitet, der für interne Server bestimmt ist. Der Director authentifiziert eingehende Anforderungen vorab und leitet sie an den Heimpool oder Server des Benutzers weiter. Die Vorabauthenitifizierung in Director ermöglicht das Aussortieren von Anfragen, die von Benutzerkonten stammen, die in der Bereitstellung nicht bekannt sind. Ein Director hilft dabei, Front-End-Server vor bösartigem Datenverkehr wie Denial-of-Service (DoS)-Angriffen zu schützen. Wenn das Netzwerk bei einem solchen Angriff mit ungültigen externen Datenverkehr überschwemmt wird, endet der Datenverkehr beim Director.

- **System Center Operations Manager wird empfohlen.** Es wird empfohlen, den Status Ihrer Skype for Business Server Bereitstellung zu überwachen, um die Dienstverfügbarkeit für Endbenutzer sicherzustellen. Sie können das System Center Operations Manager Management Pack für Skype for Business verwenden, das als kostenloser Download von Microsoft zur Verfügung steht. Mit dem Skype for Business Management Pack können Sie proaktiv Echtzeitwarnungen erhalten, wenn Probleme auftreten, synthetische Transaktionen ausführen, um End-to-End-Skype for Business-Funktionen zu testen, Berichte zur Dienstverfügbarkeit zu erhalten usw. Dies hilft Ihnen bei der proaktiven Behandlung von Problemen mit Ihrer Bereitstellung, bevor diese für Endbenutzer spürbar werden.