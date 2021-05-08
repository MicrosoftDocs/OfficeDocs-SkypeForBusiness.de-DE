---
title: Erstellen eines Gebäudeplans für das Anrufqualitätsdashboard (CQD)
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: Hier erfahren Sie, wie Sie eine Gebäudezuordnung erstellen, die Sie zum Hochladen von Mandanten- und Gebäudedaten im Anrufqualitäts-Dashboard (CQD) verwenden können.
ms.openlocfilehash: 890e5e9b394cf8b600e635014c90ebb9053a1e07
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2020
ms.locfileid: "46584034"
---
# <a name="create-a-building-map-for-call-quality-dashboard-cqd"></a>Erstellen eines Gebäudeplans für das Anrufqualitätsdashboard (CQD)

In einer Microsoft Teams oder Skype for Business Onlinebereitstellung sind alle Clients extern. Daher werden standardmäßig alle Clients im Anrufqualitätsdashboard als außerhalb des Anrufqualitätsdashboards gemeldet, unabhängig davon, ob der Client mit einem internen Unternehmensnetzwerk verbunden ist.

Wenn Sie mit einem AQD arbeiten, müssen Sie den Standort eines Endpunkts kennen und wissen, ob er mit einem Netzwerk verbunden war, das Sie verwalten können, oder ob sie ein Netzwerk nicht verwalten können, unter der Annahme, dass Sie nur Netzwerke verbessern können, die Sie verwalten können. Durch das Hochladen von Subnetz- und Gebäudeinformationen in das AQD aktivieren Sie das AQD, um festzustellen, ob der Endpunkt mit einem internen (verwalteten) Netzwerk oder einem externen (nicht verwalteten) Netzwerk verbunden war. Deshalb ist es wichtig, einen Gebäudeplan für Ihre Organisation zu erstellen und in das [AQD hochzuladen.](CQD-upload-tenant-building-data.md)

## <a name="building-mapping-tools"></a>Tools für die Gebäudezuordnung

Es gibt viele Möglichkeiten, die Subnetze Ihrer Organisation zu karten. Wenn Sie Hilfe benötigen, können Sie das PowerShell-Modul für CQDTools verwenden, das in diesem [Blogbeitrag beschrieben ist.](https://aka.ms/cqdtools) Diese Tools basieren auf PowerShell und verwenden Active Directory-Websites und -Dienste sowie Microsoft DHCP-Dienste, um die Gebäudedatei vorab zu füllen. Diese Tools können Ihnen bei den folgenden Aufgaben helfen:

1. AD-Websites und -Dienste abfragen und basierend auf den darin enthaltenen Informationen eine Gebäudedatei erstellen.
1. Abfragen eines Microsoft DHCP-Servers oder mehrerer Server ab, um Subnetzinformationen abzurufen, und automatisches Erstellen einer Gebäudedatei.
1. Validieren einer vorhandenen Gebäudedatei, Durchsuchen nach Duplikaten und Überlappungen.
1. Suchen nach nicht zugeordneten Subnetzen in CQD.

## <a name="related-topics"></a>Verwandte Themen

[Hochladen mandanten- und gebäudedaten im AQD](CQD-upload-tenant-building-data.md)