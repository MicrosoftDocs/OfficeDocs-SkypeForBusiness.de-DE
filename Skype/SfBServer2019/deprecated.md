---
title: Veraltete Version von Skype for Business Server 2019
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Zusammenfassung: Diese Features wurden aus Skype for Business Server 2019 entfernt.'
ms.openlocfilehash: 5c5914493d7e2f4da4fd72d6acf7ff2b979d8e88
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49808725"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a>Veraltete Version von Skype for Business Server 2019

Erfahren Sie mehr über die Features und Funktionen, die in Skype for Business Server 2019 veraltet sind. Informationen zu neuen Funktionen in Skype for Business Server 2019 finden Sie [unter "Was ist in Skype for Business Server 2019".](whats-new.md)

Aus Kompatibilitätsgründen mit früheren Produktversionen sind einige Features mit einer bedeutungsverdingten Bedeutung in Skype for Business Server 2019 enthalten.

## <a name="features-deprecated-in-skype-for-business-server-2019"></a>Veraltete Features in Skype for Business Server 2019 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a>XMPP-Gateways für Skype for Business Server

Skype for Business Server 2015 und seine Vorgänger haben es Ihnen ermöglicht, einen XMPP (Extensible Messaging and Presence Protocol)-Proxy auf dem Edgeserver und ein XMPP-Gateway auf dem Front-End-Server oder Front-End-Pool zu konfigurieren. Diese Funktion ist in Skype for Business Server 2019 nicht mehr verfügbar.

### <a name="persistent-chat-for-skype-for-business-server"></a>Beständiger Chat für Skype for Business Server

Der Server für beständigen Chat ist eine optionale Rolle, mit der mehrere Benutzer in Ihrer Organisation an Chatroomunterhaltungen teilnehmen können, die im Laufe der Zeit bestehen bleiben. Beständiger Chat kann nicht mit Skype for Business Server 2019 bereitgestellt werden. Diese Serverrolle wird aus dem Topologie-Generator sowie aus dem Code entfernt. 

Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter ["Erste Schritte mit Ihrem Microsoft Teams-Upgrade".](/microsoftteams/upgrade-start-here)

### <a name="sql-mirroring-for-skype-for-business-server"></a>SQL Spiegelung für Skype for Business Server

SQL Spiegelung kann nicht mit Skype for Business Server 2019 bereitgestellt werden. Weitere Optionen für die Bereitstellung von hoher Verfügbarkeit und Notfallwiederherstellung werden weiterhin unterstützt, und Sie sollten unter ihnen wählen. Informationen zu den Optionen finden Sie unter ["Plan for high availability and disaster recovery in Skype for Business Server".](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)

### <a name="in-place-upgrades"></a>Direkte Upgrades 

In-Place-Upgrades waren in Skype for Business Server 2015 verfügbar, werden jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Das nebeneinander ausgeführte Upgrade und die Koexistenz werden unterstützt. Weitere Informationen finden Sie unter ["Migration zu Skype for Business Server 2019".](migration/migration-to-skype-for-business-server-2019.md)

### <a name="mobility-service-mcx"></a>Mobilitätsdienst (Mcx)

Von älteren mobilen Clients verwendete Mobilitätsdienstunterstützung ist in Skype for Business Server 2019 nicht mehr verfügbar. Dies wurde zuvor in Skype for Business Server 2015 angekündigt.

Alle aktuellen mobilen Skype for Business-Clients verwenden bereits unified Communications Web API (UCWA), um Chat, Anwesenheit und Kontakte zu unterstützen. Benutzer mit Legacyclients, die Mcx verwenden, müssen ein Upgrade auf einen aktuellen Client durchführen.

Weitere Informationen finden Sie unter [Plan for Mobility for Skype for Business Server](../SfbServer/plan-your-deployment/mobility.md) and Mobile client feature comparison for Skype for [Business](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).

## <a name="tools"></a>Tools

Die folgenden Tools stehen in der ersten Version von Skype for Business Server 2019 nicht zur Verfügung:

- Skype for Business Server: Rechner zur Kapazitätsplanung
- Debugtools für Skype for Business Server
- Skype for Business Server Resource Kit Tools (einige Tools werden entfernt)
    - Call Parkometer
    - Nachschlagebenutzerkonsole
    - Migration nicht zugewiesener Nummern : Ankündigungsmigration

Die folgenden Tools werden in Skype for Business Server 2019 nicht unterstützt:

- Call Quality Methodology (but not Call Quality Dashboard)
- Microsoft Call Quality Methodology Scorecard, v1.5
- Skype for Business Server 2015-Planungstool
- Skype for Business Server 2015 Stress and Performance Tool

### <a name="see-also"></a>Siehe auch

[Neues in Skype for Business Server 2019](whats-new.md)

[Migrieren eines XMPP-Partnerverbunds](migration/migrating-xmpp-federation.md)
