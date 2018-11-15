---
title: Was ist aus Skype für Business Server 2019 veraltet
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 7/10/2018
ms.audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Zusammenfassung: Diese Features wurden aus Skype für Business Server 2019 entfernt.'
ms.openlocfilehash: 66366c2272db8d6f605fde6dc066f730543883b6
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2018
ms.locfileid: "26530542"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a>Was ist aus Skype für Business Server 2019 veraltet 

Informationen Sie zu den Features und Funktionen, die in Skype für Business Server 2019 veraltet sind. Informationen zu neuen Features in Skype für Business Server 2019 finden Sie unter [Was ist in Skype für Business Server 2019](whats-new.md).

Einige Aufhebung der emphasised Features sind für die Kompatibilität mit früheren Produktversionen in Skype für Business Server 2019 enthalten. 

## <a name="features-deprecated-in-skype-for-business-server-2019"></a>Veraltete Features in Skype für Business Server 2019 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a>XMPP-Gateways für Skype für Business Server

Skype für Business Server 2015 und seine Vorgänger konnten Sie einen Proxy Extensible Messaging and Presence Protocol (XMPP) auf dem Edge-Server und einem XMPP-Gateway auf dem Front-End-Server oder Front-End-Pool zu konfigurieren. Diese Funktion ist nicht mehr in Skype für Business Server 2019 verfügbar.


### <a name="persistent-chat-for-skype-for-business-server"></a>Beständigen Chat für Skype für Business Server

Persistent Chat-Server ist eine optionale Rolle, die mehrere Benutzer in Ihrer Organisation kann an Chatroom-Unterhaltungen, die über einen Zeitraum beibehalten teilnehmen. Beständiger Chat kann nicht mit Skype für Business Server 2019 bereitgestellt werden. Diese Serverrolle wird von der Topologie-Generator, ebenso wie aus dem Code entfernt. 

Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter [Weg von Skype für Unternehmen, die Microsoft-Teams](/microsoftteams/journey-skypeforbusiness-teams).   

### <a name="sql-mirroring-for-skype-for-business-server"></a>SQL-Spiegelung für Skype für Business Server

SQL-Spiegelung kann nicht mit Skype für Business Server 2019 bereitgestellt werden. Weitere Optionen für die Bereitstellung von High Availability and Disaster Recovery werden weiterhin unterstützt, und wählen Sie daraus. Finden Sie unter [Planen für hohe Verfügbarkeit und notfallwiederherstellung in Skype für Business Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) , um die Optionen zu überprüfen.

### <a name="in-place-upgrades"></a>In-Place-upgrades 

Compliance-Upgrades in Skype für Business Server 2015 verfügbar waren, jedoch werden in Skype für Business Server 2019 nicht mehr unterstützt. Upgrade und Koexistenz nebeneinander unterstützt wird, finden Sie weitere Informationen unter [Migration zu Skype für Business Server 2019](migration/migration-to-skype-for-business-server-2019.md) .

###  <a name="mobility-service-mcx"></a>Mobilitätsdienst ("MCX")

Mobility Service-Unterstützung von mobilen Clients von Vorversionen verwendet, ist nicht mehr in Skype für Business Server 2019 verfügbar. Dies wurde zuvor in Skype für Business Server 2015 vorgestellt.

Alle aktuellen Skype für mobile Clients Business Unified Communications Web API (UCWA) zur Unterstützung von Sofortnachrichten (IM), Anwesenheit und Kontakte bereits verwenden. Benutzer mit Clients von Vorversionen von Mcx müssen an einen aktuellen Client aktualisieren.

Weitere Informationen finden Sie unter [Planen für die Mobilität für Skype für Business Server](../SfbServer/plan-your-deployment/mobility.md) und [mobilen Client Featurevergleich für Skype für Unternehmen](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).

## <a name="tools"></a>Tools

Die folgenden Tools werden nicht auf die erste Version von Skype für Business Server 2019 zur Verfügung:

- Skype für Rechner Business Server-Kapazitätsplanung
- Skype für Business Server Debugging-Werkzeuge
- Skype für Business Server Resource Kit-Tools (einige Tools werden entfernt)
    - Call Parkometer
    - Lookup-Benutzer-Konsole
    - Nicht zugewiesene Nummer Ankündigung Migration

Die folgenden Tools werden mit Skype für Business Server 2019 nicht unterstützt:

- Rufen Sie der Qualität Methodik auf (aber nicht rufen Sie Qualitätsdashboard auf)
- Microsoft-Aufruf Qualität Methodik Scorecard, v1. 5
- Skype for Business Server 2015 Planning Tool
- Skype for Business Server 2015 Stress and Performance Tool

### <a name="see-also"></a>Siehe auch

[Was ist neu in Skype für Business Server 2019](whats-new.md)

[Migrieren von XMPP-Verbund](migration/migrating-xmpp-federation.md)