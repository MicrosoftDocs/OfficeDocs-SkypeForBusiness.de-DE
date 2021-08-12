---
title: Veraltete Skype for Business Server 2019
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
ms.openlocfilehash: 43fa8bae64e65fcba1aaf21c75e06d396d3c47eee8df40cec0db0eb1d5d646eb
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54282468"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a>Veraltete Skype for Business Server 2019

Erfahren Sie mehr über die Features und Funktionen, die in Skype for Business Server 2019 veraltet sind. Informationen zu neuen Features in Skype for Business Server 2019 finden Sie [unter What's in Skype for Business Server 2019](whats-new.md).

Einige features de-emphasized sind in Skype for Business Server 2019 aus Gründen der Kompatibilität mit früheren Produktversionen enthalten.

## <a name="features-deprecated-in-skype-for-business-server-2019"></a>Veraltete Features in Skype for Business Server 2019 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a>XMPP-Gateways für Skype for Business Server

Skype for Business Server 2015 und seinen Vorgängern konnten Sie einen XMPP-Proxy (Extensible Messaging and Presence Protocol) auf dem Edgeserver und ein XMPP-Gateway auf dem Front-End-Server oder Front-End-Pool konfigurieren. Diese Funktionalität ist in Skype for Business Server 2019 nicht mehr verfügbar.

### <a name="persistent-chat-for-skype-for-business-server"></a>Beständiger Chat für Skype for Business Server

Der Server für beständigen Chat ist eine optionale Rolle, mit der mehrere Benutzer in Ihrer Organisation an Chatroomunterhaltungen teilnehmen können, die im Laufe der Zeit bestehen bleiben. Beständiger Chat kann nicht mit Skype for Business Server 2019 bereitgestellt werden. Diese Serverrolle wird sowohl aus dem Topologie-Generator als auch aus dem Code entfernt. 

Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter [Erste Schritte mit Ihrem Microsoft Teams-Upgrade.](/microsoftteams/upgrade-start-here)

### <a name="sql-mirroring-for-skype-for-business-server"></a>SQL Spiegelung für Skype for Business Server

SQL Spiegelung kann nicht mit Skype for Business Server 2019 bereitgestellt werden. Andere Optionen für die Bereitstellung von Hoher Verfügbarkeit und Notfallwiederherstellung werden weiterhin unterstützt, und Sie sollten zwischen diesen optionen auswählen. Informationen zu den Optionen finden Sie [unter Plan for high availability and disaster recovery in Skype for Business Server.](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)

### <a name="in-place-upgrades"></a>Direkte Upgrades 

Direkte Upgrades waren in Skype for Business Server 2015 verfügbar, werden jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Paralleles Upgrade und Koexistenz werden unterstützt. Weitere Informationen finden Sie unter [Migration zu Skype for Business Server 2019.](migration/migration-to-skype-for-business-server-2019.md)

### <a name="mobility-service-mcx"></a>Mobilitätsdienst (Mcx)

Mobilitätsdienstunterstützung, die von älteren mobilen Clients verwendet wird, ist in Skype for Business Server 2019 nicht mehr verfügbar. Dies wurde bereits im Skype for Business Server 2015 angekündigt.

Alle aktuellen Skype for Business mobile Clients verwenden bereits unified Communications Web API (UCWA), um Chatnachrichten, Anwesenheitsinformationen und Kontakte zu unterstützen. Benutzer mit Legacyclients, die Mcx verwenden, müssen auf einen aktuellen Client aktualisieren.

Weitere Informationen finden Sie unter [Plan for Mobility for Skype for Business Server](../SfbServer/plan-your-deployment/mobility.md) and Mobile client feature comparison for [Skype for Business](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).

## <a name="tools"></a>Tools

Die folgenden Tools stehen in der ersten Version von Skype for Business Server 2019 nicht zur Verfügung:

- Skype for Business Server: Rechner zur Kapazitätsplanung
- Skype for Business Server Debugtools
- Skype for Business Server Resource Kit-Tools (einige Tools werden entfernt)
    - Call Parkometer
    - Benutzerkonsole nachschlagen
    - Ankündigungsmigration nicht zugewiesener Nummern

Die folgenden Tools werden mit Skype for Business Server 2019 nicht unterstützt:

- Call Quality Methodology (but not Call Quality Dashboard)
- Microsoft Call Quality Methodology Scorecard, v1.5
- Skype for Business Server 2015-Planungstool
- Skype for Business Server 2015 Stress and Performance Tool

### <a name="see-also"></a>Siehe auch

[Neuigkeiten in Skype for Business Server 2019](whats-new.md)

[Migrieren eines XMPP-Partnerverbunds](migration/migrating-xmpp-federation.md)
