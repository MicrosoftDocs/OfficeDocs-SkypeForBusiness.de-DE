---
title: Was ist veraltet von Skype for Business Server 2019
ms.reviewer: ''
ms.author: v-lanac
author: LanaChin
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Zusammenfassung: diese Features wurden aus Skype for Business Server 2019 entfernt.'
ms.openlocfilehash: 40a202f802ec8ac1a0f880f92ad9cf59ce68a627
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42125218"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a>Was ist veraltet von Skype for Business Server 2019

Erfahren Sie mehr über die Features und Funktionen, die in Skype for Business Server 2019 veraltet sind. Informationen zu neuen Features in Skype for Business Server 2019 finden Sie unter [What es in Skype for Business Server 2019](whats-new.md).

Einige Features mit hervorgehobener Bedeutung sind in Skype for Business Server 2019 für die Kompatibilität mit früheren Produktversionen enthalten.

## <a name="features-deprecated-in-skype-for-business-server-2019"></a>In Skype for Business Server 2019 veraltete Features 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a>XMPP-Gateways für Skype for Business Server

Mit Skype for Business Server 2015 und seinen Vorgängern können Sie einen XMPP-Proxy (Extensible Messaging and Presence Protocol) auf dem Edgeserver und ein XMPP-Gateway auf dem Front-End-Server oder Front-End-Pool konfigurieren. Diese Funktion steht in Skype for Business Server 2019 nicht mehr zur Verfügung.

### <a name="persistent-chat-for-skype-for-business-server"></a>Beständiger Chat für Skype for Business Server

Server für beständigen Chat ist eine optionale Rolle, mit der mehrere Benutzer in Ihrer Organisation an Chatroom-Unterhaltungen teilnehmen können, die im Laufe der Zeit beibehalten werden. Beständiger Chat kann nicht mit Skype for Business Server 2019 bereitgestellt werden. Diese Serverrolle wird sowohl aus dem Topologie-Generator als auch aus dem Code entfernt. 

Die gleiche Funktionalität ist in Microsoft Teams verfügbar. Weitere Informationen finden Sie unter [Erste Schritte mit Ihrem Microsoft Teams-Upgrade](/microsoftteams/upgrade-start-here).

### <a name="sql-mirroring-for-skype-for-business-server"></a>SQL-Spiegelung für Skype for Business Server

Die SQL-Spiegelung kann nicht mit Skype for Business Server 2019 bereitgestellt werden. Weitere Optionen für die Bereitstellung von hoher Verfügbarkeit und Notfallwiederherstellung werden weiterhin unterstützt, und Sie sollten unter Ihnen auswählen. Siehe [Plan for High Availability and Disaster Recovery in Skype for Business Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) , um die Optionen zu überprüfen.

### <a name="in-place-upgrades"></a>Direkte Upgrades 

In-Place-Upgrades waren in Skype for Business Server 2015 verfügbar, werden jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Paralleles Upgrade und nebeneinander wird unterstützt, siehe [Migration zu Skype for Business Server 2019](migration/migration-to-skype-for-business-server-2019.md) , um weitere Informationen zu erhalten.

### <a name="mobility-service-mcx"></a>Mobilitätsdienst (MCX)

Die von älteren mobilen Clients verwendete Mobilitätsdienst Unterstützung steht in Skype for Business Server 2019 nicht mehr zur Verfügung. Dies wurde zuvor in Skype for Business Server 2015 angekündigt.

Alle aktuellen Skype for Business mobilen Clients verwenden bereits Unified Communications Web API (UCWA), um Chatnachrichten, Anwesenheitsinformationen und Kontakte zu unterstützen. Benutzer mit älteren Clients, die MCX verwenden, müssen auf einen aktuellen Client aktualisieren.

Weitere Informationen finden Sie unter [Plan for Mobility for Skype for Business Server](../SfbServer/plan-your-deployment/mobility.md) and [Mobile Client Feature Comparison for Skype for Business](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).

## <a name="tools"></a>Tools

Die folgenden Tools stehen nicht zur Verwendung in der ersten Version von Skype for Business Server 2019 zur Verfügung:

- Skype for Business Server Kapazitäts planungsrechner
- Skype for Business Server Debugging-Tools
- Skype for Business Server Resource Kit-Tools (einige Tools werden entfernt)
    - Parkometer aufrufen
    - Lookup-Benutzerkonsole
    - Migration nicht zugewiesener Nummern Ankündigungen

Die folgenden Tools werden mit Skype for Business Server 2019 nicht unterstützt:

- Methode für die Anrufqualität (aber kein Qualitäts Dashboard für die Anrufqualität)
- Microsoft Call Quality Method Scorecard, v 1.5
- Skype for Business Server 2015 Planungs Tool
- Skype for Business Server 2015-Tool für Stress und Leistung

### <a name="see-also"></a>Siehe auch

[Neuerungen in Skype for Business Server 2019](whats-new.md)

[Migrieren des XMPP-Verbunds](migration/migrating-xmpp-federation.md)
