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
ms.openlocfilehash: 958f6630faf295a16aebe7513ee9e5c98daeeaa5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831735"
---
# <a name="reference-topologies-for-skype-for-business-server"></a>Referenztopologien für Skype for Business Server

Referenztopologien für Skype for Business Server, einschließlich Diagrammen und Entscheidungen für große, mittlere und kleine Organisationen.

Die beste Skype for Business Server-Topologie für Sie hängt von der Größe Ihrer Organisation, den Arbeitsauslastungen, die Sie bereitstellen möchten, und Ihren Bevorzugten für hohe Verfügbarkeit und Investitionskosten ab.

In diesem Abschnitt werden drei Beispielreferenztopologien beschrieben, einschließlich der Gründe für viele entscheidungen, die bei jeder Topologie berücksichtigt wurden.

## <a name="reference-topology-for-a-small-organization"></a>Referenztopologie für eine kleine Organisation

Die Referenztopologie für kleine Organisationen zeigt, wie Sie eine stabile, hoch verfügbare Lösung bereitstellen können, indem Sie nur drei Server mit Skype for Business Server bereitstellen.

**Referenztopologie für kleine Organisationen**

![Diagramm zur Referenztopologie zur Bereitstellung von drei Servern](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology1.jpg)

- **Bereitgestelltes Standard Edition-Serverpaar** Diese Organisation hat 4.000 Benutzer am zentralen Standort. Sie haben zwei Standard Edition-Server bereitgestellt und miteinander gekoppelt, um hohe Verfügbarkeit und Notfallwiederherstellung zu ermöglichen. Auf jedem Server werden 2.000 Benutzer gespeichert, aber Die Informationen zu allen Benutzern werden zwischen den beiden Servern synchronisiert. Wenn einer ausfällt, kann ein Administrator ein Failover für diese Benutzer ausführen, um vom anderen Server bedient zu werden, mit einer minimalen Unterbrechung für die Benutzer. Weitere Informationen zu den Funktionen für hohe Verfügbarkeit und Notfallwiederherstellung in Skype for Business Server finden Sie unter [Plan for high availability and disaster recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).

- **Empfehlung zur Bereitstellung eines Edgeservers.** Wenngleich die Bereitstellung eines Edgeservers für das interne Instant Messaging, für Anwesenheitsinformationen und Konferenzen nicht erforderlich ist, wird sie selbst für kleine Bereitstellung empfohlen. Sie können Ihre Investition in Skype for Business Server maximieren, indem Sie einen Edgeserver bereitstellen, um Benutzern, die sich derzeit außerhalb der Firewalls Ihrer Organisation befinden, Dienste zu bieten. Hierdurch bieten sich folgende Vorteile:

  - Die Benutzer Ihrer Organisation können die Skype for Business Server-Funktionalität verwenden, wenn sie von zu Hause aus arbeiten oder unterwegs sind.

  - Ihre Benutzer können externe Benutzer zur Teilnahme an Besprechungen einladen.

  - Wenn Sie über eine Partner-, Lieferanten- oder Kundenorganisation verfügen, die auch Skype for Business Server verwendet, können Sie eine Verbundbeziehung mit dieser Organisation bilden. Ihre Skype for Business Server-Bereitstellung würde dann Benutzer aus dieser Verbundorganisation erkennen, was zu einer besseren Zusammenarbeit führt.

  - Ihre Benutzer können Chatnachrichten mit Benutzern einiger öffentlicher Chatdienste austauschen.

- **Ausfallsicherheit für Zweigstellen.** In dieser Organisation wird ein Pilotprogramm der Enterprise-VoIP Skype for Business Server ausgeführt. Einige Benutzer verwenden Skype for Business Server als einzige Sprachlösung. Einige dieser Enterprise-VoIP Pilotbenutzer befinden sich am Zweigstellenstandort. Der Zweigstellenstandort verfügt nicht über eine zuverlässige Wide Area Network (WAN)-Verbindung zum zentralen Standort, daher wird dort eine Survivable Branch Appliance bereitgestellt. Wenn dieS bereitgestellt ist, können Benutzer am Zweigstellenstandort weiterhin Anrufe (sowohl innerhalb der Organisation als auch über FESTNETZanrufe) senden und empfangen, voicemailfunktionen nutzen und mit Chatnachrichten von zwei Parteien kommunizieren. Benutzer können darüber hinaus auch dann authentifiziert werden, wenn die WAN-Verbindung nicht verfügbar ist. Weitere Informationen finden Sie unter [Plan for Enterprise-VoIP resiliency in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md).

- **Exchange UM-Bereitstellung.** Diese Referenztopologie enthält einen Exchange Unified Messaging (UM)-Server, auf dem Microsoft Exchange Server, nicht Skype for Business Server ausgeführt wird.

- **Office Web Apps Server.** Wir empfehlen die Bereitstellung eines Office Web Apps Servers oder einer Office Web Apps Server-Farm in allen Organisation, die Webkonferenzen unterstützen. Office Web Apps Server ermöglicht die Präsentation von PowerPoint-Folien in Webkonferenzen.

## <a name="reference-topology-for-a-medium-organization"></a>Referenztopologie für eine mittlere Organisation

Die Referenztopologie mit hoher Verfügbarkeit und einem einzelnen Rechenzentrum ist auf kleine bis mittelständische Organisationen mit einem zentralen Standort zugeschnitten. Die genaue Topologie im folgenden Diagramm gilt für eine Organisation mit 20.000 Benutzern.

**Referenztopologie für mittlere Organisationen**

![Referenztopologie für einzelnes Rechenzentrumsdiagramm](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology2.jpg)

- **Möglichkeit zur Unterstützung weiterer Benutzer durch das Hinzufügen zusätzlicher Front-End-Server.** Die genaue Topologie in diesem Diagramm enthält drei Front-End-Server, die 20.000 Benutzer unterstützen. Wenn Sie über einen zentralen Standort und mehr Benutzer verfügen, können Sie dem Pool einfach weitere Front-End-Server hinzufügen. Die maximale Anzahl von Benutzern pro Pool beträgt 80.000 mit zwölf Front-End-Servern.

    Die Topologie mit einem einzelnen Standort kann jedoch noch mehr Benutzer unterstützen, wenn dem Standort ein weiterer Front-End-Pool hinzugefügt wird.

- **Die Notfallwiederherstellung kann hinzugefügt werden.** Für diese Organisation ist die hohe Verfügbarkeit ihrer Skype for Business Server-Dienste ein erforderliches Feature, die Notfallwiederherstellung jedoch nicht. Der Pool der bereitgestellten Front-End-Server bietet hohe Verfügbarkeit.

    Wenn sie die Notfallwiederherstellungs fähigkeit hinzufügen möchten, könnten sie ein weiteres Datencenter einrichten und dort einen weiteren Front-End-Pool hinzufügen und mit dem Front-End-Pool in ihrem aktuellen Datencenter koppeln. Wenn sich dann ein Notfall auf den primären Pool ausdingt, könnten die Administratoren ein Failover der Benutzer zum Sicherungspool durchführen.

- **Back-End-Server werden gespiegelt** Um eine hohe Verfügbarkeit für grundlegende Benutzerfeatures zu bieten, hat die Organisation ein gespiegelte Back-End-Serverpaar für jeden Front-End-Pool bereitgestellt.

- **Optionen für die Monitoring Server-Datenbank.** Diese Organisation hat eine Überwachung bereitgestellt, um die Qualität von Enterprise-VoIP und A/V-Konferenzen sicherzustellen. Die Überwachung wird auf jedem Front-End-Server bereitgestellt, und die Überwachungsdatenbank wird mit den Back-End-Servern ausgeführt. Außerdem unterstützen wir Topologien, in denen sich die Überwachungsdatenbank auf einem separaten Server befindet.

- **Hohe Verfügbarkeit des Edgeservers** In dieser Beispielorganisation mit 20.000 Benutzern wäre nur ein Edgeserver für die Leistung ausreichend. Sie haben jedoch einen Pool von zwei Edgeservern bereitgestellt, um hohe Verfügbarkeit zu bieten.

- **Optionen für Bereitstellungen an Zweigstellenstandorten.** Die Organisation in dieser Topologie hat Enterprise-VoIP als ihre VoIP-Lösung bereitgestellt. Zweigstelle 1 verfügt nicht über eine ausfallsichere WAN(Wide Area Network)-Verbindung zum zentralen Standort, daher ist eine Survivable Branch Appliance für die Aufrechterhaltung vieler Skype for Business Server-Funktionen für den Fall bereitgestellt, dass die WAN-Verbindung zum zentralen Standort ausbleicht. Zweigstellenstandort 2 verfügt über eine ausfallsichere WAN-Verbindung, daher wird nur ein PSTN-Gateway benötigt. Das bereitgestellte PSTN-Gateway unterstützt die Medienumgehung, deshalb wird an Zweigstellenstandort 2 kein Vermittlungsserver benötigt. Weitere Informationen finden Sie unter [Plan for Enterprise-VoIP resiliency in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md).

- **DNS-Lastenausgleich.** Der Front-End-Pool und der Edgeserverpool verfügen über einen bereitgestellten DNS-Lastenausgleich für SIP-Datenverkehr. Auf diese Weise sind keine Hardwaregeräte zum Lastenausgleich für die Edgeserver erforderlich, und Setup und Wartung der Hardwaregeräte zum Lastenausgleich für die weiteren Pools werden erheblich vereinfacht, da die Hardwaregeräte zum Lastenausgleich nur für HTTP-Datenverkehr benötigt werden. Weitere Informationen finden Sie unter [DNS Load Balancing](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing).

- **Exchange UM-Bereitstellung.** Diese Referenztopologie enthält einen Exchange Unified Messaging (UM)-Server, auf dem Microsoft Exchange Server, nicht Skype for Business Server ausgeführt wird.

- **Office Web Apps Server.** Wir empfehlen die Bereitstellung eines Office Web Apps Servers oder einer Office Web Apps Server-Farm in allen Organisation, die Webkonferenzen unterstützen. Mit Office Web Apps Server können Powerpoint-Folien in Webkonferenzen präsentiert werden.

- **Directors können hinzugefügt werden.** Wenn diese Organisation dazu beitragen möchte, die Sicherheit vor Denial-of-Service-Angriffen zu erhöhen, könnte sie auch einen Pool von Directors bereitstellen. Ein Director ist eine separate, optionale Serverrolle in Skype for Business Server, die keine Benutzerkonten enthält oder Anwesenheits- oder Konferenzdienste bietet. Er dient als interner Next-Hop-Server, an den ein Edgeserver eingehenden SIP-Datenverkehr weiter leitet, der für interne Server bestimmt ist. Der Director authentifiziert eingehende Anforderungen vorab und leitet sie an den Homepool oder Server des Benutzers weiter. Die Vorabauthenitifizierung in Director ermöglicht das Aussortieren von Anfragen, die von Benutzerkonten stammen, die in der Bereitstellung nicht bekannt sind. Ein Director schützt Front-End-Server vor bösartigem Datenverkehr wie Denial-of-Service(DoS)-Angriffen. Wenn das Netzwerk bei einem solchen Angriff mit ungültigem externen Datenverkehr überflutet wird, endet der Datenverkehr beim Director.

- **System Center Operations Manager wird empfohlen.** Es wird empfohlen, den Status Ihrer Skype for Business Server-Bereitstellung zu überwachen, um die Dienstverfügbarkeit für Endbenutzer sicherzustellen. Sie können das System Center Operations Manager Management Pack für Skype for Business verwenden, das als kostenloser Download von Microsoft verfügbar ist. Mit dem Skype for Business Management Pack können Sie proaktiv Echtzeitwarnungen erhalten, wenn Probleme auftreten, synthetische Transaktionen ausführen, um die End-to-End-Skype for Business-Funktionalität zu testen, Berichte zur Dienstverfügbarkeit zu erhalten und so weiter. Dies hilft Ihnen bei der proaktiven Behandlung von Problemen mit Ihrer Bereitstellung, bevor diese für Endbenutzer spürbar werden.

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

- **Front-End-Pools sind gekoppelt, um die Notfallwiederherstellung zu ermöglichen.** Die Front-End-Pools an Standort A und Standort B sind miteinander gekoppelt, um Unterstützung für die Notfallwiederherstellung zu bieten. Wenn der Pool an einem Standort ausfällt, kann der Administrator ein Failover der Benutzer von diesem Standort zum gekoppelten Front-End-Pool am anderen Standort ausführen, mit einer minimalen Dienstunterbrechung für die Benutzer. Jeder dieser beiden Front-End-Pools hat sechs Server, was ausreicht, um alle 40.000 Benutzer beider Pools im Fall eines Failovers zu unterstützen. Weitere Informationen finden Sie unter [Plan for high availability and disaster recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).

- **Back-End-Server werden gespiegelt** Um eine hohe Verfügbarkeit für grundlegende Benutzerfeatures zu bieten, hat die Organisation ein gespiegelte Back-End-Serverpaar für jeden Front-End-Pool bereitgestellt. Dies ist eine optionale Topologie, und Sie können stattdessen einen einzelnen Back-End-Server bereitstellen. SQL Clustering- und AlwaysOn-Verfügbarkeitsgruppen werden ebenfalls unterstützt. Weitere Informationen finden Sie unter [Back-End-Server hohe Verfügbarkeit in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md).

- **Verwenden des Standard Edition-Servers an einem Zweigstellenstandort.** Diese Organisation stuft Standort C als Zweigstellenstandort ein, da er nur 600 Mitarbeiter umfasst. Die dortigen Benutzer halten jedoch untereinander viele A/V-Konferenzen ab. Wenn sie in Skype for Business Server als Zweigstelle bereitgestellt würde, würden die Medien für diese Konferenzen über das Wan (Wide Area Network) zu und von einem zentralen Standort mit bereitgestellten Front-End-Servern laufen. Um diese potenzielle Bandbreitenauslastung zu vermeiden, haben sie an diesem Standort ein Standard Edition-Serverpaar installiert, das diese Konferenzen hosten wird. Und da Standard Edition-Server dort installiert sind, betrachtet Skype for Business Server ihn per Definition als zentralen Standort und wird im Topologie-Generator und im Planungstool als solcher behandelt.

    Hier würde nur ein Standard Edition-Server für die Leistung ausreichen, aber die Organisation hat zwei bereitgestellt und zusammen verwendet, um hohe Verfügbarkeit für den Fall zu bieten, dass ein Server ausfalle.

    Auch wenn Standort C als zentraler Standort betrachtet wird, müssen Sie dort keine Edgeserver bereitstellen. In diesem Beispiel verwendet Standort C die an Standort A bereitgestellten Edgeserver.

- **Überwachung und Archivierung** Diese Organisation hat sowohl die Überwachung als auch die Archivierung bereitgestellt. Wenn Sie die Überwachung oder Archivierung bereitstellen, wird sie auf jedem Front-End-Server ausgeführt. Die Datenbanken für diese Features können mit der Back-End-Datenbank ausgeführt werden oder sich auf einem separaten Server befinden. Diese Organisation hat diese Datenbanken auf einem server, der von den Back-End-Servern getrennt ist, am zentralen Standort B gespeichert. Die datenbanken hier empfangen Überwachungs- und Archivierungsdaten von den Front-End-Servern an allen Standorten.

- **Optionen für Bereitstellungen an Zweigstellenstandorten.** Diese Organisation verfügt tatsächlich über mehr als 50 Zweigstellen, von denen nur zwei in den detaillierten Diagrammen dargestellt sind. Zweigstelle 1 verfügt nicht über eine ausfallsichere WAN-Verbindung zum zentralen Standort, sodass survivable Branch Appliances für den Fall bereitgestellt werden, dass die WAN-Verbindung zum zentralen Standort ausbleicht. Zweigstelle 2 verfügt jedoch über eine ausfallsichere WAN-Verbindung, sodass nur ein PstN-Gateway (Public Switched Telephone Network) benötigt wird. Das bereitgestellte PSTN-Gateway unterstützt die Medienumgehung, deshalb wird an Zweigstellenstandort 2 kein Vermittlungsserver benötigt. Weitere Informationen zur Entscheidung, was an einem Zweigstellenstandort installiert werden soll, finden Sie unter ["Plan for Enterprise-VoIP resiliency in Skype for Business Server ".](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md)

- **SIP-Trunking und Vermittlungsserver.** Beachten Sie, dass an Standort B der Vermittlungsserver nicht gemeinsam mit den Front-End-Servern ausgeführt wird. Der Grund hierfür liegt darin, dass für Standorte mit SIP-Trunking ein eigenständiger Vermittlungsserver empfohlen wird. In den meisten anderen Fällen empfiehlt sich die gemeinsame Ausführung des Vermittlungsservers mit dem Front-End-Server. Ausführliche Informationen zu den Vermittlungsservertopologien finden Sie unter [Components and Topologies for Mediation Server](https://technet.microsoft.com/library/71397168-36c3-4d21-b8ef-db6a751634ee.aspx) in der Planungsdokumentation.

- **Beständiger Chat wird bereitgestellt.** Diese Organisation hat die Server bereitgestellt, die zum Aktivieren des beständigen Chats erforderlich sind. Es wurden mehrere Front-End-Server für beständigen Chat bereitgestellt, um sowohl die Last für die Anzahl der Benutzer im Pool zu bewältigen als auch hohe Verfügbarkeit zu bieten. Außerdem wurde kompatibilität für beständigen Chat bereitgestellt, und der Speicher für beständigen Chat und der Konformitätsspeicher für beständigen Chat wurden auf separaten Servern gespeichert. Diese Speicher können mit dem Back-End-Server und sogar mit dem Back-End-Server ausgeführt werden, aber diese Organisation hat sich entschieden, sie zu trennen, um eine bessere Leistung zu erzielen.

    > [!NOTE]
    > Beständiger Chat ist in Skype for Business Server 2015 verfügbar, wird jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter ["Erste Schritte mit Ihrem Microsoft Teams-Upgrade".](/microsoftteams/upgrade-start-here) Wenn Sie beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktionalität benötigen, zu Teams migrieren oder Weiterhin Skype for Business Server 2015 verwenden.

- **DNS-Lastenausgleich.** Der Front-End-Pool und der Edgeserverpool verwenden den DNS-Lastenausgleich. Auf diese Weise sind keine Hardwaregeräte zum Lastenausgleich für die interne Schnittstelle der Edgeserver erforderlich, und der für Setup und Wartung der Hardwaregeräte zum Lastenausgleich für die weiteren Pools erforderliche Zeitraum wird erheblich verringert, da die Hardwaregeräte zum Lastenausgleich nur für HTTP-Datenverkehr benötigt werden. Weitere Informationen finden Sie unter (.. /.. /plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing).

- **Exchange UM-Bereitstellung.** Skype for Business Server kann sowohl mit lokalen Bereitstellungen von Exchange Unified Messaging (UM) als auch mit gehosteten Exchange UM-Bereitstellungen verwendet werden. Der zentrale Standort A umfasst einen Exchange Unified Messaging (UM)-Server, auf dem Microsoft Exchange Server, nicht Skype for Business Server ausgeführt wird. Die Exchange -UM-Funktion für Skype for Business Server wird im Front-End-Pool ausgeführt.

    Am zentralen Standort B wird gehostetes Exchange eingesetzt, daher wird die Exchange UM-Serverfunktionalität ebenfalls gehostet.

    Ausführliche Informationen zu Exchange UM finden Sie unter ["Lokale Exchange Unified Messaging-Integration"](https://technet.microsoft.com/library/e7c63a71-2d99-4aa9-b649-36c1a431bdf1.aspx) und "Integration gehosteter [Exchange Unified Messaging"](https://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx) in der Planungsdokumentation.

- **Office Web Apps Server.** Wir empfehlen die Bereitstellung eines Office Web Apps Servers oder einer Office Web Apps Server-Farm in allen Organisation, die Webkonferenzen unterstützen. Sie können eine einzelne Office Web Apps Server-Farm an einem Standort bereitstellen, die den Datenverkehr von allen Standorten abwickelt, oder diese an allen Standorten bereitstellen. Mit Office Web Apps Server können Powerpoint-Folien in Webkonferenzen präsentiert werden.

- **Directors können hinzugefügt werden.** Wenn diese Organisation die Sicherheit im Hinblick auf Denial-of-Service-Angriffe erhöhen möchte, könnte sie auch einen Pool von Directors bereitstellen. Ein Director ist eine separate, optionale Serverrolle in Skype for Business Server, die keine Benutzerkonten enthält oder Anwesenheits- oder Konferenzdienste bietet. Er dient als interner Next-Hop-Server, an den ein Edgeserver eingehenden SIP-Datenverkehr weiter leitet, der für interne Server bestimmt ist. Der Director authentifiziert eingehende Anforderungen vorab und leitet sie an den Homepool oder Server des Benutzers weiter. Die Vorabauthenitifizierung in Director ermöglicht das Aussortieren von Anfragen, die von Benutzerkonten stammen, die in der Bereitstellung nicht bekannt sind. Ein Director schützt Front-End-Server vor bösartigem Datenverkehr wie Denial-of-Service(DoS)-Angriffen. Wenn das Netzwerk bei einem solchen Angriff mit ungültigem externen Datenverkehr überflutet wird, endet der Datenverkehr beim Director.

- **System Center Operations Manager wird empfohlen.** Es wird empfohlen, den Status Ihrer Skype for Business Server-Bereitstellung zu überwachen, um die Dienstverfügbarkeit für Endbenutzer sicherzustellen. Sie können das System Center Operations Manager Management Pack für Skype for Business verwenden, das als kostenloser Download von Microsoft verfügbar ist. Mit dem Skype for Business Management Pack können Sie proaktiv Echtzeitwarnungen erhalten, wenn Probleme auftreten, synthetische Transaktionen ausführen, um die End-to-End-Skype for Business-Funktionalität zu testen, Berichte zur Dienstverfügbarkeit zu erhalten und so weiter. Dies hilft Ihnen bei der proaktiven Behandlung von Problemen mit Ihrer Bereitstellung, bevor diese für Endbenutzer spürbar werden.


