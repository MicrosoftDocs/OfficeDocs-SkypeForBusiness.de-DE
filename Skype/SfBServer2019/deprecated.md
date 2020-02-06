---
title: Was ist in Skype for Business Server 2019 veraltet?
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Zusammenfassung: diese Features wurden von Skype for Business Server 2019 entfernt.'
ms.openlocfilehash: f77ccecd0ab963c0707a7b1dc1d24083ed0c3729
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813983"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a>Was ist in Skype for Business Server 2019 veraltet?

Informieren Sie sich über die Features und Funktionen, die in Skype for Business Server 2019 veraltet sind. Informationen zu den neuen Funktionen in Skype for Business Server 2019 finden Sie unter [Was ist in Skype for Business Server 2019](whats-new.md).

Einige dehervor gehobene Funktionen sind in Skype for Business Server 2019 zur Kompatibilität mit früheren Produktversionen enthalten.

## <a name="features-deprecated-in-skype-for-business-server-2019"></a>In Skype for Business Server 2019 als veraltet markierte Features 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a>XMPP-Gateways für Skype for Business Server

Mit Skype for Business Server 2015 und seinen Vorgängern können Sie einen Extensible Messaging and Presence Protocol (XMPP)-Proxy auf dem Edgeserver und ein XMPP-Gateway auf dem Front-End-Server oder Front-End-Pool konfigurieren. Diese Funktion steht in Skype for Business Server 2019 nicht mehr zur Verfügung.

### <a name="persistent-chat-for-skype-for-business-server"></a>Beständiger Chat für Skype for Business Server

Der beständige Chat Server ist eine optionale Rolle, mit der mehrere Benutzer in Ihrer Organisation an Chatroom-Unterhaltungen teilnehmen können, die im Laufe der Zeit fortbestehen. Beständiger Chat kann nicht mit Skype for Business Server 2019 bereitgestellt werden. Diese Serverrolle wird sowohl aus dem Topologie-Generator als auch aus dem Code entfernt. 

In Teams steht dieselbe Funktionalität zur Verfügung. Weitere Informationen finden Sie unter [Erste Schritte mit dem Upgrade für Microsoft Teams](/microsoftteams/upgrade-start-here).

### <a name="sql-mirroring-for-skype-for-business-server"></a>SQL-Spiegelung für Skype for Business Server

Die SQL-Spiegelung kann nicht mit Skype for Business Server 2019 bereitgestellt werden. Weitere Optionen für die Bereitstellung von Hochverfügbarkeits-und Disaster Recovery werden weiterhin unterstützt, und Sie sollten zwischen Ihnen auswählen. Informationen zu den Optionen finden Sie unter [Planen der Hochverfügbarkeits-und Disaster Recovery in Skype for Business Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) .

### <a name="in-place-upgrades"></a>In-Place-Upgrades 

In-Place-Upgrades waren in Skype for Business Server 2015 verfügbar, werden aber in Skype for Business Server 2019 nicht mehr unterstützt. Paralleles Upgrade und koexistieren werden unterstützt, lesen Sie [Migration zu Skype for Business Server 2019](migration/migration-to-skype-for-business-server-2019.md) , um weitere Informationen zu erhalten.

### <a name="mobility-service-mcx"></a>Mobilitätsdienst (MCX)

Der Support für Mobilitätsdienste, der von älteren mobilen Clients verwendet wird, ist in Skype for Business Server 2019 nicht mehr verfügbar. Dies wurde bereits in Skype for Business Server 2015 angekündigt.

Alle derzeitigen mobilen Skype for Business-Clients verwenden bereits Unified Communications Web API (UCWA) zur Unterstützung von Instant Messaging (im), Anwesenheitsinformationen und Kontakten. Benutzer mit Legacy-Clients, die MCX verwenden, müssen ein Upgrade auf einen aktuellen Client durchführen.

Weitere Informationen finden Sie unter [Planen der Mobilitätsfunktionen für Skype for Business Server](../SfbServer/plan-your-deployment/mobility.md) und [Vergleich der mobilen Clients für Skype for Business](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).

## <a name="tools"></a>Tools

Die folgenden Tools stehen bei der ersten Version von Skype for Business Server 2019 nicht zur Verfügung:

- Skype for Business Server: Rechner zur Kapazitätsplanung
- Skype for Business Server-Debugging-Tools
- Skype for Business Server Resource Kit-Tools (einige Tools werden entfernt)
    - Call Parkometer
    - Nachschlage Benutzerkonsole
    - Migration nicht zugewiesener Nummern Ankündigungen

Die folgenden Tools werden von Skype for Business Server 2019 nicht unterstützt:

- Methodik für die Anrufqualität (aber nicht die Anrufqualität)
- Microsoft Call Quality Method Scorecard, v 1.5
- Skype for Business Server 2015 – Planungstool
- Skype for Business Server 2015 Stress and Performance Tool

### <a name="see-also"></a>Siehe auch

[Neuerungen in Skype for Business Server 2019](whats-new.md)

[Migrieren eines XMPP-Partnerverbunds](migration/migrating-xmpp-federation.md)
