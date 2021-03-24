---
title: Referenztopologien für Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0453aeee-c41f-44e6-a6e0-aaace526ca08
description: Referenztopologien für Skype for Business Server, einschließlich Diagrammen und Entscheidungen für große, mittlere und kleine Organisationen.
ms.openlocfilehash: f92474cf1d5a2057a81a0b69abef26d6a9d744f2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092873"
---
# <a name="reference-topologies-for-skype-for-business-server"></a>Referenztopologien für Skype for Business Server

Referenztopologien für Skype for Business Server, einschließlich Diagrammen und Entscheidungen für große, mittlere und kleine Organisationen.

Die beste Skype for Business Server-Topologie für Sie hängt von der Größe Ihrer Organisation, den Arbeitsauslastungen, die Sie bereitstellen möchten, und Ihren Präferenzen für hohe Verfügbarkeit und Investitionskosten ab.

In diesem Abschnitt werden drei Beispielreferenztopologien beschrieben, einschließlich der Gründe für viele entscheidungen, die in die einzelnen Topologien berücksichtigt wurden.

## <a name="reference-topology-for-a-small-organization"></a>Referenztopologie für eine kleine Organisation

Die Referenztopologie für kleine Organisationen zeigt, wie Sie eine stabile, hochverf nkende Lösung bereitstellen können, indem Sie nur drei Server mit Skype for Business Server bereitstellen.

**Referenztopologie für kleine Organisationen**

![Referenztopologie, in der drei Server bereitgestellt werden](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology1.jpg)

- **Paar bereitgestellter Standard Edition-Server** Diese Organisation verfügt über 4.000 Benutzer an ihrem zentralen Standort. Sie haben zwei Standard Edition-Server bereitgestellt und miteinander gekoppelt, um hohe Verfügbarkeit und Notfallwiederherstellung zu ermöglichen. Auf jedem Server werden 2.000 Benutzer gespeichert, aber Informationen zu allen Benutzern werden zwischen den beiden Servern synchronisiert. Wenn einer ausfällt, kann ein Administrator die Benutzer, die vom anderen Server bedient werden sollen, mit einem Minimum an Unterbrechungen für Die Benutzer nicht ausführen. Weitere Informationen zu Hochverfügbarkeits- und Notfallwiederherstellungsfeatures in Skype for Business Server finden Sie unter [Plan for high availability and disaster recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).

- **Empfehlung zur Bereitstellung eines Edgeservers.** Wenngleich die Bereitstellung eines Edgeservers für das interne Instant Messaging, für Anwesenheitsinformationen und Konferenzen nicht erforderlich ist, wird sie selbst für kleine Bereitstellung empfohlen. Sie können Ihre Skype for Business Server-Investition maximieren, indem Sie einen Edgeserver bereitstellen, um Benutzern, die sich derzeit außerhalb der Firewalls Ihrer Organisation befinden, Dienste zu bieten. Hierdurch bieten sich folgende Vorteile:

  - Die eigenen Benutzer Ihrer Organisation können die Skype for Business Server-Funktionalität verwenden, wenn sie von zu Hause aus arbeiten oder unterwegs sind.

  - Ihre Benutzer können externe Benutzer zur Teilnahme an Besprechungen einladen.

  - Wenn Sie über einen Partner, Anbieter oder eine Kundenorganisation verfügen, die auch Skype for Business Server verwendet, können Sie eine Verbundbeziehung mit dieser Organisation bilden. Ihre Skype for Business Server-Bereitstellung würde dann Benutzer aus dieser Verbundorganisation erkennen, was zu einer besseren Zusammenarbeit führt.

  - Ihre Benutzer können Chatnachrichten mit Benutzern einiger öffentlicher Chatdienste austauschen.

- **Ausfallsicherheit für Zweigstellen.** In dieser Organisation wird ein Pilotprogramm der Enterprise-VoIP von Skype for Business Server ausgeführt. Einige Benutzer verwenden Skype for Business Server als einzige Sprachlösung. Einige dieser Enterprise-VoIP Pilotbenutzer befinden sich am Zweigstellenstandort. Der Zweigstellenstandort verfügt nicht über eine zuverlässige WAN-Verbindung (Wide Area Network) zum zentralen Standort, daher wird dort eine Survivable Branch Appliance bereitgestellt. Wenn die WAN-Verbindung nicht mehr verfügbar ist, können Benutzer am Zweigstellenstandort weiterhin Anrufe (sowohl Anrufe innerhalb der Organisation als auch pstN-Anrufe) senden und empfangen, Voicemailfunktionen haben und mit Chatnachrichten mit zwei Parteien kommunizieren. Benutzer können darüber hinaus auch dann authentifiziert werden, wenn die WAN-Verbindung nicht verfügbar ist. Weitere Informationen finden Sie unter [Plan for Enterprise-VoIP resiliency in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md).

- **Exchange UM-Bereitstellung.** Diese Referenztopologie enthält einen Exchange Unified Messaging (UM)-Server, der Microsoft Exchange Server und nicht Skype for Business Server ausgeführt wird.

- **Office Web Apps Server.** Wir empfehlen die Bereitstellung eines Office Web Apps Servers oder einer Office Web Apps Server-Farm in allen Organisation, die Webkonferenzen unterstützen. Office Web Apps Server ermöglicht die Präsentation von PowerPoint-Folien in Webkonferenzen.

## <a name="reference-topology-for-a-medium-organization"></a>Referenztopologie für eine mittlere Organisation

Die Referenztopologie mit hoher Verfügbarkeit und einem einzelnen Rechenzentrum ist auf kleine bis mittelständische Organisationen mit einem zentralen Standort zugeschnitten. Die genaue Topologie im folgenden Diagramm gilt für eine Organisation von 20.000 Benutzern.

**Referenztopologie für mittlere Organisationen**

![Referenztopologie für ein einzelnes Datencenterdiagramm](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology2.jpg)

- **Möglichkeit zur Unterstützung weiterer Benutzer durch das Hinzufügen zusätzlicher Front-End-Server.** Die genaue Topologie in diesem Diagramm verfügt über drei Front-End-Server, die 20.000 Benutzer unterstützen. Wenn Sie über einen zentralen Standort und mehr Benutzer verfügen, können Sie einfach weitere Front-End-Server zum Pool hinzufügen. Die maximale Anzahl von Benutzern pro Pool beträgt 80.000, mit zwölf Front-End-Servern.

    Die Topologie mit einem einzelnen Standort kann jedoch noch mehr Benutzer unterstützen, wenn dem Standort ein weiterer Front-End-Pool hinzugefügt wird.

- **Notfallwiederherstellung könnte hinzugefügt werden.** Für diese Organisation ist die hohe Verfügbarkeit ihrer Skype for Business Server-Dienste ein notwendiges Feature, die Notfallwiederherstellung jedoch nicht. Der Pool der bereitgestellten Front-End-Server bietet hohe Verfügbarkeit.

    Wenn sie die Notfallwiederherstellungsfähigkeit hinzufügen möchten, könnten sie erwägen, ein weiteres Rechenzentrum zu erstellen und einen weiteren Front-End-Pool hinzuzufügen und ihn mit dem Front-End-Pool in ihrem aktuellen Rechenzentrum zu koppeln. Wenn sich dann ein Notfall auf den primären Pool ausdingt, könnten die Administratoren einen Failover der Benutzer zum Sicherungspool durchführen.

- **Back-End-Server werden gespiegelt** Um eine hohe Verfügbarkeit für grundlegende Benutzerfeatures zu gewährleisten, hat die Organisation ein gespiegeltes Back-End-Serverpaar für jeden Front-End-Pool bereitgestellt.

- **Optionen für die Monitoring Server-Datenbank.** Diese Organisation hat Monitoring bereitgestellt, um die Qualität von Enterprise-VoIP und A/V-Konferenzen sicherzustellen. Die Überwachung wird auf jedem Front-End-Server bereitgestellt, und die Überwachungsdatenbank ist mit den Back-End-Servern kollidiert. Außerdem unterstützen wir Topologien, in denen sich die Überwachungsdatenbank auf einem separaten Server befindet.

- **Hohe Verfügbarkeit von Edgeservern** In dieser Beispielorganisation mit 20.000 Benutzern würde nur ein Edgeserver für die Leistung ausreichen. Sie haben jedoch einen Pool mit zwei Bereitgestellten Edgeservern bereitgestellt, um hohe Verfügbarkeit zu bieten.

- **Optionen für Bereitstellungen an Zweigstellenstandorten.** Die Organisation in dieser Topologie hat Enterprise-VoIP als ihre VoIP-Lösung bereitgestellt. Zweigstelle 1 verfügt nicht über eine ausfallsichere WAN-Verbindung (Wide Area Network) zum zentralen Standort, daher ist eine Survivable Branch Appliance bereitgestellt, um viele Skype for Business Server-Features zu verwalten, falls die WAN-Verbindung zum zentralen Standort nicht mehr funktioniert. Zweigstellenstandort 2 verfügt über eine ausfallsichere WAN-Verbindung, daher wird nur ein PSTN-Gateway benötigt. Das bereitgestellte PSTN-Gateway unterstützt die Medienumgehung, deshalb wird an Zweigstellenstandort 2 kein Vermittlungsserver benötigt. Weitere Informationen finden Sie unter [Plan for Enterprise-VoIP resiliency in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md).

- **DNS-Lastenausgleich.** Der Front-End-Pool und der Edgeserverpool verfügen über einen DNS-Lastenausgleich für DEN SIP-Datenverkehr. Auf diese Weise sind keine Hardwaregeräte zum Lastenausgleich für die Edgeserver erforderlich, und Setup und Wartung der Hardwaregeräte zum Lastenausgleich für die weiteren Pools werden erheblich vereinfacht, da die Hardwaregeräte zum Lastenausgleich nur für HTTP-Datenverkehr benötigt werden. Weitere Informationen finden Sie unter [DNS Load Balancing](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing).

- **Exchange UM-Bereitstellung.** Diese Referenztopologie enthält einen Exchange Unified Messaging (UM)-Server, der Microsoft Exchange Server und nicht Skype for Business Server ausgeführt wird.

- **Office Web Apps Server.** Wir empfehlen die Bereitstellung eines Office Web Apps Servers oder einer Office Web Apps Server-Farm in allen Organisation, die Webkonferenzen unterstützen. Mit Office Web Apps Server können Powerpoint-Folien in Webkonferenzen präsentiert werden.

- **Directors können hinzugefügt werden.** Wenn diese Organisation dazu beitragen wollte, die Sicherheit vor Denial-of-Service-Angriffen zu erhöhen, könnte sie auch einen Pool von Directors bereitstellen. Ein Director ist eine separate, optionale Serverrolle in Skype for Business Server, die keine Benutzerkonten verwendet oder Anwesenheits- oder Konferenzdienste zur Verfügung stellt. Er dient als interner Next-Hop-Server, an den ein Edgeserver eingehenden SIP-Datenverkehr weiter leitet, der für interne Server bestimmt ist. Der Director authentifiziert eingehende Anforderungen vorab und leitet sie an den Startpool oder Server des Benutzers weiter. Die Vorabauthenitifizierung in Director ermöglicht das Aussortieren von Anfragen, die von Benutzerkonten stammen, die in der Bereitstellung nicht bekannt sind. Ein Director schützt Front-End-Server vor schädlichem Datenverkehr wie Denial-of-Service(DoS)-Angriffen. Wenn das Netzwerk bei einem solchen Angriff mit ungültigem externen Datenverkehr überflutet wird, endet der Datenverkehr am Director.

- **System Center Operations Manager wird empfohlen.** Es wird empfohlen, den Status Ihrer Skype for Business Server-Bereitstellung zu überwachen, um die Dienstverfügbarkeit für Endbenutzer sicherzustellen. Sie können das System Center Operations Manager Management Pack für Skype for Business verwenden, das als kostenloser Download von Microsoft verfügbar ist. Mit dem Skype for Business Management Pack können Sie proaktiv Echtzeitwarnungen erhalten, wenn Probleme auftreten, synthetische Transaktionen ausführen, um die End-to-End-Funktionalität von Skype for Business zu testen, Berichte zur Dienstverfügbarkeit zu erhalten und so weiter. Dies hilft Ihnen bei der proaktiven Behandlung von Problemen mit Ihrer Bereitstellung, bevor diese für Endbenutzer spürbar werden.

## <a name="reference-topology-for-a-large-organization"></a>Referenztopologie für eine große Organisation

Die Referenztopologie für eine große Organisation mit mehreren Rechenzentren gilt für jede Organisationsgröße mit mehr als einem zentralen Standort. Die genaue Topologie in dem folgenden Diagramm bezieht sich auf eine Organisation mit 50.000 Benutzern, von denen sich 20.000 Benutzer am zentralen Standort A, 20.000 Benutzer am zentralen Standort B und insgesamt 10.000 Benutzer am zentralen Standort C und an Zweigstellenstandorten befinden. Der in diesem Diagramm gezeigte Topologietyp kann Organisationen mit einer beliebigen Benutzeranzahl umfassen.

Zusätzlich zu der hohen Verfügbarkeit, die von Pools von Front-End-Servern bereitgestellt wird, bietet diese Topologie Unterstützung für die Notfallwiederherstellung. Die Front-End-Pools an den zentralen Standorten A und B sind miteinander gekoppelt. Wenn einer dieser Pools ausfällt, kann der Administrator die Dienste für die betroffenen Benutzer in den kombinierten Pool des nicht betroffenen Standorts verlagern.

Diese Topologie wird in mehreren Diagrammen gezeigt. Zunächst sehen Sie einen Überblick, gefolgt von detaillierten Ansichten der zentralen Standorte.

**Überblick über die Referenztopologie für große Organisationen mit mehreren Rechenzentren**

![Referenztopologie für mehrere Rechenzentren](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-1-new.jpg)

**Referenztopologie für große Organisationen: Detaillierte Ansicht des zentralen Standorts A**

![Topologie 3-2](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-2.jpg)

**Referenztopologie für große Organisationen: Detaillierte Ansicht des zentralen Standorts B**

![Topologie 3-3](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-3.jpg)

**Referenztopologie für große Organisationen: Detaillierte Ansicht des zentralen Standorts C**

![Topologie 3-4](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-4.jpg)

- **Front-End-Pools werden gekoppelt, um die Notfallwiederherstellung zu ermöglichen.** Die Front-End-Pools an Standort A und Standort B sind miteinander gekoppelt, um Notfallwiederherstellungsunterstützung zu bieten. Wenn für den Pool an einem Standort ein Fehler auftritt, kann der Administrator die Benutzer von diesem Standort zum gekoppelten Front-End-Pool am anderen Standort mit einer minimalen Dienstunterbrechung für Benutzer übergehen. Jeder dieser beiden Front-End-Pools hat sechs Server, was ausreicht, um alle 40.000 Benutzer beider Pools im Fall eines Failovers zu unterstützen. Weitere Informationen finden Sie unter [Plan for high availability and disaster recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).

- **Back-End-Server werden gespiegelt** Um eine hohe Verfügbarkeit für grundlegende Benutzerfeatures zu gewährleisten, hat die Organisation ein gespiegeltes Back-End-Serverpaar für jeden Front-End-Pool bereitgestellt. Dies ist eine optionale Topologie, und Sie können stattdessen einen einzelnen Back-End-Server bereitstellen. SQL Clustering- und AlwaysOn-Verfügbarkeitsgruppen werden ebenfalls unterstützt. Weitere Informationen finden Sie unter [Back End Server high availability in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md).

- **Verwenden des Standard Edition-Servers an einem Zweigstellenstandort.** Diese Organisation stuft Standort C als Zweigstellenstandort ein, da er nur 600 Mitarbeiter umfasst. Die dortigen Benutzer halten jedoch untereinander viele A/V-Konferenzen ab. Wenn sie in Skype for Business Server als Zweigstellenstandort bereitgestellt würde, würden die Medien für diese Konferenzen über das WAN (Wide Area Network) zu und von einem zentralen Standort ausgeführt, an dem ein Front-End-Server bereitgestellt wurde. Um diese potenzielle Bandbreitenlast zu vermeiden, haben sie an diesem Standort ein Paar Standard Edition-Server installiert, die diese Konferenzen hosten. Und da dort Standard Edition-Server installiert sind, betrachtet Skype for Business Server den Server per Definition als zentralen Standort und wird als solcher im Topologie-Generator und im Planungstool behandelt.

    Nur ein Standard Edition-Server würde hier für die Leistung ausreichen, aber die Organisation hat zwei bereitgestellt und sie miteinander gekoppelt, um hohe Verfügbarkeit für den Fall zu bieten, dass ein Server aus dem System ausgeht.

    Auch wenn Standort C als zentraler Standort betrachtet wird, müssen Sie dort keine Edgeserver bereitstellen. In diesem Beispiel verwendet Standort C die an Standort A bereitgestellten Edgeserver.

- **Überwachung und Archivierung** Diese Organisation hat sowohl Die Überwachung als auch die Archivierung bereitgestellt. Wenn Sie Überwachung oder Archivierung bereitstellen, wird sie auf jedem Front-End-Server ausgeführt. Die Datenbanken für diese Features können mit der Back-End-Datenbank oder auf einem separaten Server zusammengeknallt werden. Diese Organisation hat diese Datenbanken auf einem server getrennt von den Back-End-Servern am zentralen Standort B gespeichert. Die Datenbanken erhalten hier Überwachungs- und Archivierungsdaten von den Front-End-Servern an allen Standorten.

- **Optionen für Bereitstellungen an Zweigstellenstandorten.** Diese Organisation verfügt tatsächlich über mehr als 50 Zweigstellen, von denen nur zwei in den detaillierten Diagrammen angezeigt werden. Zweigstellenstandort 1 verfügt nicht über eine ausfallsichere WAN-Verbindung zum zentralen Standort, sodass survivable Branch Appliances für den Fall bereitgestellt werden, dass die WAN-Verbindung zum zentralen Standort nicht mehr funktioniert. Zweigstelle 2 verfügt jedoch über eine ausfallsichere WAN-Verbindung, sodass nur ein PstN-Gateway (Public Switched Telephone Network) benötigt wird. Das bereitgestellte PSTN-Gateway unterstützt die Medienumgehung, deshalb wird an Zweigstellenstandort 2 kein Vermittlungsserver benötigt. Weitere Informationen zur Entscheidung, was an einem Zweigstellenstandort installiert werden soll, finden Sie unter [Plan for Enterprise-VoIP resiliency in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md).

- **SIP-Trunking und Vermittlungsserver.** Beachten Sie, dass an Standort B der Vermittlungsserver nicht gemeinsam mit den Front-End-Servern ausgeführt wird. Der Grund hierfür liegt darin, dass für Standorte mit SIP-Trunking ein eigenständiger Vermittlungsserver empfohlen wird. In den meisten anderen Fällen empfiehlt sich die gemeinsame Ausführung des Vermittlungsservers mit dem Front-End-Server. Ausführliche Informationen zu den Vermittlungsservertopologien finden Sie unter [Components and Topologies for Mediation Server](/previous-versions/office/lync-server-2013/lync-server-2013-components-and-topologies-for-mediation-server) in der Planungsdokumentation.

- **Beständigen Chat wird bereitgestellt.** Diese Organisation hat die Server bereitgestellt, die zum Aktivieren des beständigen Chats erforderlich sind. Es wurden mehrere Front-End-Server für beständigen Chat bereitgestellt, um die Last für die Anzahl der Benutzer im Pool zu verarbeiten und hohe Verfügbarkeit zu bieten. Außerdem wurde Compliance für beständigen Chat bereitgestellt und der Speicher für beständigen Chat und der Compliancespeicher für beständigen Chat auf separaten Servern gespeichert. Diese Speicher können zusammengeknallt werden und sogar mit dem Back-End-Server zusammenarbeiten, aber diese Organisation hat sich entschieden, sie zu trennen, um eine bessere Leistung zu bieten.

    > [!NOTE]
    > Beständigen Chat ist in Skype for Business Server 2015 verfügbar, wird jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter [Erste Schritte mit Ihrem Microsoft Teams-Upgrade](/microsoftteams/upgrade-start-here). Wenn Sie beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktionalität benötigen, zu Teams migrieren oder Skype for Business Server 2015 weiterhin verwenden.

- **DNS-Lastenausgleich.** Der Front-End-Pool und der Edgeserverpool verwenden den DNS-Lastenausgleich. Auf diese Weise sind keine Hardwaregeräte zum Lastenausgleich für die interne Schnittstelle der Edgeserver erforderlich, und der für Setup und Wartung der Hardwaregeräte zum Lastenausgleich für die weiteren Pools erforderliche Zeitraum wird erheblich verringert, da die Hardwaregeräte zum Lastenausgleich nur für HTTP-Datenverkehr benötigt werden. Weitere Informationen finden Sie unter (.. /.. /plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing).

- **Exchange UM-Bereitstellung.** Skype for Business Server funktioniert sowohl mit lokalen Bereitstellungen von Exchange Unified Messaging (UM) als auch mit gehosteten Exchange UM. Zentraler Standort A umfasst einen Exchange Unified Messaging (UM)-Server, der Microsoft Exchange Server und nicht Skype for Business Server ausgeführt wird. Die Exchange -UM-Funktionalität für Skype for Business Server wird im Front-End-Pool ausgeführt.

    Am zentralen Standort B wird gehostetes Exchange eingesetzt, daher wird die Exchange UM-Serverfunktionalität ebenfalls gehostet.

    Ausführliche Informationen zu Exchange UM finden Sie unter [Lokale Exchange Unified Messaging-Integration](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-exchange-unified-messaging-integration) und [Gehostete Exchange Unified Messaging-Integration](/previous-versions/office/lync-server-2013/lync-server-2013-hosted-exchange-unified-messaging-integration) in der Planungsdokumentation.

- **Office Web Apps Server.** Wir empfehlen die Bereitstellung eines Office Web Apps Servers oder einer Office Web Apps Server-Farm in allen Organisation, die Webkonferenzen unterstützen. Sie können eine einzelne Office Web Apps Server-Farm an einem Standort bereitstellen, die den Datenverkehr von allen Standorten abwickelt, oder diese an allen Standorten bereitstellen. Mit Office Web Apps Server können Powerpoint-Folien in Webkonferenzen präsentiert werden.

- **Directors können hinzugefügt werden.** Wenn diese Organisation die Sicherheit im Hinblick auf Denial-of-Service-Angriffe erhöhen möchte, könnte sie auch einen Pool von Directors bereitstellen. Ein Director ist eine separate, optionale Serverrolle in Skype for Business Server, die keine Benutzerkonten verwendet oder Anwesenheits- oder Konferenzdienste zur Verfügung stellt. Er dient als interner Next-Hop-Server, an den ein Edgeserver eingehenden SIP-Datenverkehr weiter leitet, der für interne Server bestimmt ist. Der Director authentifiziert eingehende Anforderungen vorab und leitet sie an den Startpool oder Server des Benutzers weiter. Die Vorabauthenitifizierung in Director ermöglicht das Aussortieren von Anfragen, die von Benutzerkonten stammen, die in der Bereitstellung nicht bekannt sind. Ein Director schützt Front-End-Server vor schädlichem Datenverkehr wie Denial-of-Service(DoS)-Angriffen. Wenn das Netzwerk bei einem solchen Angriff mit ungültigem externen Datenverkehr überflutet wird, endet der Datenverkehr am Director.

- **System Center Operations Manager wird empfohlen.** Es wird empfohlen, den Status Ihrer Skype for Business Server-Bereitstellung zu überwachen, um die Dienstverfügbarkeit für Endbenutzer sicherzustellen. Sie können das System Center Operations Manager Management Pack für Skype for Business verwenden, das als kostenloser Download von Microsoft verfügbar ist. Mit dem Skype for Business Management Pack können Sie proaktiv Echtzeitwarnungen erhalten, wenn Probleme auftreten, synthetische Transaktionen ausführen, um die End-to-End-Funktionalität von Skype for Business zu testen, Berichte zur Dienstverfügbarkeit zu erhalten und so weiter. Dies hilft Ihnen bei der proaktiven Behandlung von Problemen mit Ihrer Bereitstellung, bevor diese für Endbenutzer spürbar werden.