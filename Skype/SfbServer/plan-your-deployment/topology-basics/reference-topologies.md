---
title: Referenz Topologien für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0453aeee-c41f-44e6-a6e0-aaace526ca08
description: Referenz Topologien für Skype for Business Server, einschließlich Diagrammen und Entscheidungen, die für große, mittlere und kleine Organisationen zu treffen sind.
ms.openlocfilehash: 7f284b141da25175e3a41545349a0e61f6036019
ms.sourcegitcommit: 5d29e8eb7a0c13edde8015da1e63b01b7081b4b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2019
ms.locfileid: "37028281"
---
# <a name="reference-topologies-for-skype-for-business-server"></a>Referenz Topologien für Skype for Business Server

Referenz Topologien für Skype for Business Server, einschließlich Diagrammen und Entscheidungen, die für große, mittlere und kleine Organisationen zu treffen sind.

Die beste Skype for Business Server-Topologie hängt von der Größe Ihrer Organisation, den Arbeitslasten, die Sie bereitstellen möchten, und Ihren Einstellungen für eine höhere Verfügbarkeit versus Investitionskosten ab.

In diesem Abschnitt werden drei Beispiele für Referenztopologien sowie die Gründe beleuchtet, die hinter den Entscheidungen für die jeweilige Topologie standen.

## <a name="reference-topology-for-a-small-organization"></a>Referenztopologie für kleine Organisationen

Die Referenztopologie für kleine Organisationen zeigt, wie Sie eine robuste, hoch verfügbare Lösung bereitstellen können, indem Sie nur drei Server bereitstellen, auf denen Skype for Business Server ausgeführt wird.

**Referenztopologie für kleine Organisationen**

![Referenztopologie mit drei Servern (Diagramm)](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology1.jpg)

- **Paar von Standard Edition-Servern bereitgestellt** Diese Organisation hat 4.000-Benutzer an Ihrem zentralen Standort. Sie haben zwei Standard Edition-Server bereitgestellt und kombiniert, um eine höhere Verfügbarkeit und Disaster Recovery zu ermöglichen. Jeder Server verfügt über 2.000-Benutzer, aber Informationen zu allen Benutzern werden zwischen den beiden Servern synchronisiert. Wenn einer ausfällt, kann ein Administrator für diese Benutzer einen Failover durchführen, um von dem anderen Server bedient zu werden, mit einem mindestunterbrechungs Intervall für die Benutzer. Weitere Informationen zu Hochverfügbarkeits-und Disaster Recovery-Funktionen in Skype for Business Server finden Sie unter [Planen von Hochverfügbarkeits-und Disaster Recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).

- **Empfehlung der Bereitstellung eines Edgeservers.** Auch wenn die Bereitstellung eines Edgeservers für interne Chats, für Anwesenheitsinformationen und für Konferenzen nicht erforderlich ist, wird sie selbst für kleine Bereitstellungen empfohlen. Sie können Ihre Skype for Business Server-Investition maximieren, indem Sie einen Edgeserver bereitstellen, um den Benutzern Dienst zu bieten, die sich derzeit außerhalb der Firewalls Ihrer Organisation befinden. Dies bietet folgende Vorteile:

  - Die Benutzer Ihrer Organisation können die Skype for Business-Server Funktionalität nutzen, wenn Sie von zu Hause aus arbeiten oder unterwegs sind.

  - Ihre Benutzer können externe Benutzer zur Teilnahme an Besprechungen einladen.

  - Wenn Sie über einen Partner, einen Anbieter oder eine Kundenorganisation verfügen, die ebenfalls Skype for Business Server verwendet, können Sie eine Verbundbeziehung mit dieser Organisation bilden. Ihre Skype for Business Server-Bereitstellung erkennt dann Benutzer aus dieser Verbundorganisation, was zu einer besseren Zusammenarbeit führt.

  - Ihre Benutzer können Chatnachrichten mit Benutzern von bestimmten öffentlichen Chatdiensten austauschen.

- **Ausfallsicherheit für Zweigstellen.** Diese Organisation führt ein Pilotprogramm der Enterprise-VoIP-Funktion von Skype for Business Server aus. Einige Nutzer nutzen Skype for Business Server als einzige Sprachlösung. Einige dieser Enterprise-VoIP-Pilotbenutzer befinden sich auf der Zweigstelle. Die Verzweigungs Website verfügt nicht über einen zuverlässigen WAN-Link (Wide Area Network) mit dem zentralen Standort, daher wird eine Survivable Branch-Appliance dort bereitgestellt. Dank der Survivable Branch-Anwendung können die Benutzer in der Zweigstelle bei Ausfall der WAN-Verbindung weiterhin Anrufe tätigen und entgegennehmen (sowohl innerhalb der Organisation als auch über das Festnetz), die Voicemailfunktion nutzen und per Chat kommunizieren. Benutzer können darüber hinaus auch dann authentifiziert werden, wenn die WAN-Verbindung nicht verfügbar ist. Weitere Informationen hierzu finden Sie unter [Plan for Enterprise Voice resiliency in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md).

- **Exchange UM-Bereitstellung.** Diese Referenztopologie umfasst einen Exchange Unified Messaging (um)-Server, auf dem Microsoft Exchange Server ausgeführt wird, nicht Skype for Business Server.

- **Office Web Apps Server.** Es wird empfohlen, in jeder Organisation, in der der Webkonferenzdienst verwendet wird, einen Office Web Apps Server oder eine Office Web Apps-Serverfarm bereitzustellen. Der Office Web Apps Server ermöglicht die Präsentation von PowerPoint-Folien in Webkonferenzen.

## <a name="reference-topology-for-a-medium-organization"></a>Referenztopologie für mittelständische Organisationen

Die Referenztopologie mit hoher Verfügbarkeit und einem einzelnen Rechenzentrum ist auf kleine bis mittelständische Organisationen mit einem zentralen Standort zugeschnitten. Die im folgenden Diagramm gezeigte exakte Topologie ist auf 20.000 Benutzer ausgelegt.

**Referenztopologie für mittelständige Organisationen**

![Referenztopologie für ein einziges Rechenzentrum (Diagramm)](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology2.jpg)

- **Möglichkeit, durch Hinzufügen zusätzlicher Front-End-Server weitere Benutzer zu unterstützen.** Die im Diagramm gezeigte Topologie umfasst drei Front-End-Server und kann daher bis zu 20.000 Benutzer unterstützen. Wenn Sie über einen einzelnen zentralen Standort und mehr Benutzer verfügen, können Sie dem Pool einfach weitere Front-End-Server hinzufügen. Die maximale Anzahl von Benutzern pro Pool beträgt 80.000 mit zwölf Front-End-Servern.

    Die Topologie mit einem einzelnen Standort kann jedoch noch mehr Benutzer unterstützen, wenn dem Standort ein weiterer Front-End-Pool hinzugefügt wird.

- **Möglichkeit, eine Notfallwiederherstellung hinzuzufügen.** Für diese Organisation ist eine höhere Verfügbarkeit für Ihre Skype for Business Server-Dienste ein notwendiges Feature, aber Disaster Recovery ist nicht erforderlich. Der von Ihnen bereitgestellte Pool der Front-End-Server bietet eine große Verfügbarkeit.

    Wenn die Fähigkeit zur Notfallwiederherstellung hinzugefügt werden soll, könnte die Organisation ein weiteres Rechenzentrum einrichten und dort einen weiteren Front-End-Pool hinzufügen, der dann mit dem Front-End-Pool im aktuellen Rechenzentrum kombiniert wird. Dadurch könnten die Administratoren bei einem Notfall, der den primären Pool betrifft, einen Failover der Benutzer auf den Sicherungspool durchführen.

- **Back-End-Server werden gespiegelt** Zur Bereitstellung höherer Verfügbarkeit für grundlegende Benutzer Features hat die Organisation ein gespiegeltes paar von Back-End-Servern für jeden Front-End-Pool bereitgestellt.

- **Optionen für die Monitoring Server-Datenbank.** Diese Organisation hat die Überwachung bereitgestellt, um die Qualität von Enterprise-Sprachanrufen und A/V-Konferenzen zu gewährleisten. Die Überwachung wird auf jedem Front-End-Server bereitgestellt und die Überwachungsdatenbank wird mit den Back-End-Servern verbunden. Außerdem werden Topologien unterstützt, in denen sich die Überwachungsdatenbank auf einem separaten Server befindet.

- Spitzen **Server-Verfügbarkeit** In dieser Beispielorganisation mit 20.000-Benutzern reicht nur ein Edgeserver für die Leistung aus. Es wird aber ein Pool mit zwei Edgeservern bereitgestellt, um hohe Verfügbarkeit sicherzustellen.

- **Optionen für Bereitstellungen an Zweigstellen.** Die Organisation in dieser Topologie hat Enterprise-VoIP als Sprachlösung bereitgestellt. Branch Site 1 verfügt nicht über eine stabile WAN-Verbindung (Wide Area Network) mit dem zentralen Standort, sodass eine überlebensfähige Branch-Appliance bereitgestellt wird, um viele Funktionen von Skype for Business Server zu verwalten, falls die WAN-Verbindung zur zentralen Website ausfällt. Zweigstelle 2 verfügt über eine ausfallsichere WAN-Verbindung, daher wird nur ein PSTN-Gateway benötigt. Das bereitgestellte PSTN-Gateway unterstützt die Medienumgehung, deshalb wird in Zweigstelle 2 kein Vermittlungsserver benötigt. Ausführliche Informationen hierzu finden Sie unter [Plan for Enterprise Voice resiliency in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md).

- **DNS-Lastenausgleich.** Der Front-End-Pool und der Edgeserver-Pool wurden zum DNS-Lastenausgleich für SIP-Datenverkehr konfiguriert. Auf diese Weise sind keine Hardwaregeräte zum Lastenausgleich für die Edgeserver erforderlich und Setup und Wartung der Hardwaregeräte zum Lastenausgleich für die weiteren Pools werden erheblich vereinfacht, da die Hardwaregeräte zum Lastenausgleich nur für HTTP-Datenverkehr benötigt werden. Weitere Informationen finden Sie unter [DNS-Lastenausgleich](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing).

- **Exchange UM-Bereitstellung.** Diese Referenztopologie umfasst einen Exchange Unified Messaging (um)-Server, auf dem Microsoft Exchange Server ausgeführt wird, nicht Skype for Business Server.

- **Office Web Apps Server.** Es wird empfohlen, in jeder Organisation, in der der Webkonferenzdienst verwendet wird, einen Office Web Apps Server oder eine Office Web Apps-Serverfarm bereitzustellen. Der Office Web Apps Server ermöglicht die Präsentation von PowerPoint-Folien in Webkonferenzen.

- **Möglichkeit, Directors hinzuzufügen.** Wenn diese Organisation die Sicherheit gegenüber Denial-of-Service-Angriffen erhöhen möchte, kann auch ein Director-Pool bereitgestellt werden. Bei einem Director handelt es sich um eine separate, optionale Serverrolle in Skype for Business Server, auf der keine Benutzerkonten zu Hause sind, oder Anwesenheits-oder Konferenzdienste bereitstellen. Sie fungiert als interner Server für den nächsten Hop, auf dem ein Edgeserver eingehenden SIP-Datenverkehr für interne Server weiterleitet. Der Director authentifiziert eingehende Anforderungen vorab und leitet Sie an den privaten Pool oder Server des Benutzers weiter. Die Vorabauthentifizierung durch den Director ermöglicht das Verwerfen von Anfragen von Benutzerkonten, die der Bereitstellung nicht bekannt sind. Ein Director hilft, Front-End-Server vor böswilligem Datenverkehr zu isolieren, wie DOS-Attacken (Denial-of-Service). Wenn das Netzwerk bei einem solchen Angriff mit einem ungültigen externen Datenverkehr überflutet wird, endet der Datenverkehr beim Director.

- **System Center Operations Manager wird empfohlen.** Wir empfehlen, dass Sie den Status Ihrer Skype for Business Server-Bereitstellung überwachen, um die Verfügbarkeit der Dienste für Endbenutzer zu gewährleisten. Sie können das System Center Operations Manager-Management Pack für Skype for Business verwenden, das als kostenloser Download von Microsoft zur Verfügung steht. Mit dem Skype for Business Management Pack können Sie unter anderem bei auftretenden Problemen proaktiv Echtzeitwarnungen empfangen, synthetische Transaktionen zum Testen der End-to-End-Funktionalität von Skype for Business ausführen und Berichte über die Dienstverfügbarkeit erhalten. Dadurch können Sie proaktiv auf Probleme mit Ihrer Bereitstellung reagieren, bevor Endbenutzer davon betroffen sind.

## <a name="reference-topology-for-a-large-organization"></a>Referenztopologie für große Organisationen

Die Referenztopologie für eine große Organisation mit mehreren Rechenzentren gilt für jede Organisationsgröße mit mehr als einem zentralen Standort. Die genaue Topologie im folgenden Diagramm bezieht sich auf eine Organisation mit 50.000 Benutzern, von denen sich 20.000 Benutzer am zentralen Standort A, 20.000 Benutzer am zentralen Standort B und insgesamt 10.000 Benutzer am zentralen Standort C und an Zweigstellen befinden. Der in diesem Diagramm gezeigte Topologietyp kann Organisationen mit einer beliebigen Benutzeranzahl umfassen.

Neben der großen Verfügbarkeit, die von den Pools der Front-End-Server bereitgestellt wird, fügt diese Topologie Disaster Recovery-Unterstützung hinzu. Die Front-End-Pools an zentralen Standorten A und B sind zusammen gekoppelt. Wenn einer dieser Pools ausfällt, kann der Administrator die Dienste für die betroffenen Benutzer in den kombinierten Pool des nicht betroffenen Standorts verlagern.

Diese Topologie wird in mehreren Diagrammen gezeigt. Zunächst sehen Sie einen Überblick, gefolgt von detaillierten Ansichten der zentralen Standorte.

**Überblick über die Referenztopologie für große Organisationen mit mehreren Rechenzentren**

![Referenztopologie für mehrere Rechenzentren](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-1-new.jpg)

**Referenztopologie für große Organisationen: Detaillierte Ansicht des zentralen Standorts A**

![Topologie 3-2](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-2.jpg)

**Referenztopologie für große Organisationen: Detaillierte Ansicht des zentralen Standorts B**

![Topologie 3-3](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-3.jpg)

**Referenztopologie für große Organisationen: Detaillierte Ansicht des zentralen Standorts C**

![Topologie 3-4](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-4.jpg)

- **Front-End-Pools sind gekoppelt, um eine Disaster Recovery zu ermöglichen.** Die Front-End-Pools an Standort a und Standort B sind miteinander gekoppelt, um Disaster Recovery-Unterstützung bereitzustellen. Wenn der Pool an einer Website fehlschlägt, kann der Administrator für die Benutzer von dieser Website an den gekoppelten Front-End-Pool am anderen Standort ein Failover durchführen, wobei für die Benutzer mindestens eine Dienstunterbrechung erforderlich ist. Jeder dieser beiden Front-End-Pools verfügt über sechs Server, was für alle 40.000-Benutzer in beiden Pools ausreichend ist, wenn ein Failover durchgeführt wird. Weitere Informationen finden Sie unter [Planen von Höchstverfügbarkeit und Disaster Recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).

- **Back-End-Server werden gespiegelt** Zur Bereitstellung höherer Verfügbarkeit für grundlegende Benutzer Features hat die Organisation ein gespiegeltes paar von Back-End-Servern für jeden Front-End-Pool bereitgestellt. Hierbei handelt es sich um eine optionale Topologie, und Sie können stattdessen einen einzelnen Back-End-Server bereitstellen. SQL-Clustering-und AlwaysOn-Verfügbarkeitsgruppen werden ebenfalls unterstützt. Weitere Informationen dazu finden Sie unter [Back End Server high availability in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md).

- **Verwenden des Standard Edition-Servers an einer Zweigstelle** Diese Organisation berücksichtigt Website C als Zweigstellen Website, da Sie nur 600 Mitarbeiter hat. Allerdings haben die Benutzer dort viele A/V-Konferenzen unter sich. Wenn Sie in Skype for Business Server als Verzweigungs Website bereitgestellt wurde, würden die Medien für diese Konferenzen über das WAN (Wide Area Network) zu und von einem zentralen Standort aus ausgeführt, auf dem ein Front-End-Server bereitgestellt ist. Um diese potenzielle Bandbreitenauslastung zu vermeiden, haben Sie auf dieser Website ein paar Standard Edition-Server installiert, auf denen diese Konferenzen gehostet werden. Da die Standard Edition-Server dort installiert sind, sieht Skype for Business Server per Definition eine zentrale Website und wird als solche im Topologie-Generator und im Planungs Tool behandelt.

    Nur ein Standard Edition-Server würde hier die Leistung ausreichen, aber die Organisation hat zwei bereitgestellt und zusammengefügt, um eine höhere Verfügbarkeit zu gewährleisten, wenn ein Server ausfällt.

    Auch wenn Standort C als zentraler Standort betrachtet wird, müssen Sie dort keine Edgeserver bereitstellen. In diesem Beispiel verwendet Standort C die an Standort A bereitgestellten Edgeserver.

- **Überwachung und Archivierung** Diese Organisation hat sowohl die Überwachung als auch die Archivierung bereitgestellt. Wenn Sie die Überwachung oder Archivierung bereitstellen, wird Sie auf jedem Front-End-Server ausgeführt. Die Datenbanken für diese Features können mit der Back-End-Datenbank oder auf einem separaten Server gespeichert werden. Diese Organisation hat diese Datenbanken auf einem Server getrennt von den Back-End-Servern auf dem zentralen Standort B lokalisiert. Die Datenbanken hier empfangen Überwachungs-und Archivierungsdaten von den Front-End-Servern an allen Standorten.

- **Optionen für Bereitstellungen an Zweigstellen.** Diese Organisation verfügt tatsächlich über mehr als 50 Zweigstellen, von denen nur zwei in den detaillierten Diagrammen angezeigt werden. Branch Site 1 verfügt nicht über eine stabile WAN-Verbindung mit dem zentralen Standort, daher sind überlebensfähige Branch-Appliances bereitgestellt, um einen Telefondienst bereitzustellen, falls die WAN-Verbindung zum zentralen Standort ausfällt. Branch Site 2 verfügt jedoch über eine stabile WAN-Verbindung, sodass nur ein PSTN-Gateway (Public Switched Telephone Network) benötigt wird. Das bereitgestellte PSTN-Gateway unterstützt die Medienumgehung, deshalb wird in Zweigstelle 2 kein Vermittlungsserver benötigt. Details zur Entscheidung, was Sie an einer Zweigstelle installieren sollten, finden Sie unter [Planen der Enterprise-VoIP-Widerstandsfähigkeit in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md).

- **SIP-Trunking und Vermittlungsserver.** Beachten Sie, dass am zentralen Standort B der Vermittlungsserver nicht gemeinsam mit den Front-End-Servern ausgeführt wird. Der Grund dafür ist, dass für Standorte mit SIP-Trunking ein eigenständiger Vermittlungsserver empfohlen wird. In den meisten anderen Fällen empfiehlt sich die gemeinsame Ausführung des Vermittlungsservers mit dem Front-End-Server. Ausführliche Informationen zu den Vermittlungsservertopologien finden Sie unter [Components and Topologies for Mediation Server](https://technet.microsoft.com/library/71397168-36c3-4d21-b8ef-db6a751634ee.aspx).

- **Beständiger Chat wird bereitgestellt.** Diese Organisation hat die erforderlichen Server zum Aktivieren des beständigen Chats bereitgestellt. Es wurden mehrere beständige Chat-Front-End-Server bereitgestellt, um die Last für die Anzahl der Benutzer im Pool zu behandeln und eine hohe Verfügbarkeit bereitzustellen. Darüber hinaus wurde Compliance für beständigen Chat bereitgestellt und der beständige Chat Speicher und der Compliance-Speicher für beständigen Chat auf separaten Servern gespeichert. Diese Stores können mit dem Back-End-Server kombiniert werden, aber diese Organisation hat sich entschieden, diese zu trennen, um eine bessere Leistung zu gewährleisten.

    > [!NOTE]
    > Der beständige Chat ist in Skype for Business Server 2015 verfügbar, wird aber in Skype for Business Server 2019 nicht mehr unterstützt. In Teams steht dieselbe Funktionalität zur Verfügung. Weitere Informationen finden Sie unter [Erste Schritte mit dem Upgrade für Microsoft Teams](/microsoftteams/upgrade-start-here). Wenn Sie den beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktion für Teams benötigen, oder die Verwendung von Skype for Business Server 2015 fortsetzen.

- **DNS-Lastenausgleich.** Der Front-End-Pool und der Edgeserverpool nutzen den DNS-Lastenausgleich. Dadurch sind keine Hardwaregeräte zum Lastenausgleich für die interne Schnittstelle der Edgeserver erforderlich und der für Setup und Wartung der Hardwaregeräte zum Lastenausgleich für die weiteren Pools erforderliche Zeitraum wird erheblich verringert, da die Hardwaregeräte zum Lastenausgleich nur für HTTP-Datenverkehr benötigt werden. Weitere Informationen finden Sie unter (.. /.. /plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing).

- **Exchange UM-Bereitstellung.** Skype for Business Server funktioniert sowohl mit lokalen Bereitstellungen von Exchange Unified Messaging (um) als auch mit Hosted Exchange um. Der zentrale Standort A umfasst einen Exchange Unified Messaging (um)-Server, auf dem Microsoft Exchange Server ausgeführt wird, nicht Skype for Business Server. Die Exchange um-Funktionalität für Skype for Business Server wird im Front-End-Pool ausgeführt.

    Am zentralen Standort B wird gehostetes Exchange eingesetzt, daher wird die Exchange UM-Serverfunktionalität ebenfalls gehostet.

    Ausführliche Informationen zu Exchange um finden Sie unter [lokale Exchange Unified Messaging-Integration](https://technet.microsoft.com/library/e7c63a71-2d99-4aa9-b649-36c1a431bdf1.aspx) und [gehostete Exchange Unified Messaging-Integration](https://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx) in die Planungsdokumentation.

- **Office Web Apps Server.** Es wird empfohlen, in jeder Organisation, in der der Webkonferenzdienst verwendet wird, einen Office Web Apps Server oder eine Office Web Apps-Serverfarm bereitzustellen. Sie können eine einzelne Office Web Apps-Server Farm auf einer Website bereitstellen, die Datenverkehr von allen Websites dient, oder Sie auf jeder Website bereitstellen. Der Office Web Apps Server ermöglicht die Präsentation von PowerPoint-Folien in Webkonferenzen.

- **Möglichkeit, Directors hinzuzufügen.** Wenn diese Organisation die Sicherheit im Hinblick auf Denial-of-Service-Angriffe erhöhen möchte, könnte sie auch einen Pool von Directors bereitstellen. Bei einem Director handelt es sich um eine separate, optionale Serverrolle in Skype for Business Server, auf der keine Benutzerkonten zu Hause sind, oder Anwesenheits-oder Konferenzdienste bereitstellen. Sie fungiert als interner Server für den nächsten Hop, auf dem ein Edgeserver eingehenden SIP-Datenverkehr für interne Server weiterleitet. Der Director authentifiziert eingehende Anforderungen vorab und leitet Sie an den privaten Pool oder Server des Benutzers weiter. Die Vorabauthentifizierung durch den Director ermöglicht das Verwerfen von Anfragen von Benutzerkonten, die der Bereitstellung nicht bekannt sind. Ein Director hilft, Front-End-Server vor böswilligem Datenverkehr zu isolieren, wie DOS-Attacken (Denial-of-Service). Wenn das Netzwerk bei einem solchen Angriff mit einem ungültigen externen Datenverkehr überflutet wird, endet der Datenverkehr beim Director.

- **System Center Operations Manager wird empfohlen.** Wir empfehlen, dass Sie den Status Ihrer Skype for Business Server-Bereitstellung überwachen, um die Verfügbarkeit der Dienste für Endbenutzer zu gewährleisten. Sie können das System Center Operations Manager-Management Pack für Skype for Business verwenden, das als kostenloser Download von Microsoft zur Verfügung steht. Mit dem Skype for Business Management Pack können Sie unter anderem bei auftretenden Problemen proaktiv Echtzeitwarnungen empfangen, synthetische Transaktionen zum Testen der End-to-End-Funktionalität von Skype for Business ausführen und Berichte über die Dienstverfügbarkeit erhalten. Dadurch können Sie proaktiv auf Probleme mit Ihrer Bereitstellung reagieren, bevor Endbenutzer davon betroffen sind.


