---
title: Erstellen eines Gebäudeplans für das Anruf Qualitäts Dashboard (CQD)
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
description: Hier erfahren Sie, wie Sie ein Gebäude Diagramm erstellen, das Sie zum Hochladen von Mandanten und Erstellen von Daten im Dashboard für die Anrufqualität (CQD) verwenden können.
ms.openlocfilehash: 890e5e9b394cf8b600e635014c90ebb9053a1e07
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2020
ms.locfileid: "46584034"
---
# <a name="create-a-building-map-for-call-quality-dashboard-cqd"></a>Erstellen eines Gebäudeplans für das Anruf Qualitäts Dashboard (CQD)

In einer Microsoft Teams-oder Skype for Business Online-Bereitstellung sind alle Clients extern. Standardmäßig werden alle Clients als "extern" im Anruf Qualitäts Dashboard (CQD) gemeldet, unabhängig davon, ob der Client in einem internen Unternehmensnetzwerk verbunden ist.

Wenn Sie mit CQD arbeiten, müssen Sie den Standort eines Endpunkts kennen und feststellen, ob er mit einem Netzwerk verbunden ist, das Sie verwalten können, oder ein Netzwerk, das Sie nicht verwalten können, und es wird davon ausgegangen, dass Sie nur Netzwerke verbessern können, die Sie verwalten können. Durch Hochladen von Subnetzen und Erstellen von Informationen in CQD aktivieren Sie CQD, um zu ermitteln, ob der Endpunkt mit einem internen (verwalteten) Netzwerk oder einem externen (nicht verwalteten) Netzwerk verbunden ist. Aus diesem Grund ist es wichtig, einen Bauplan für Ihre Organisation zu erstellen und [auf CQD hochzuladen](CQD-upload-tenant-building-data.md).

## <a name="building-mapping-tools"></a>Tools für die Gebäudezuordnung

Es gibt viele Möglichkeiten, die Subnetze Ihrer Organisation zuzuordnen. Wenn Sie Hilfe benötigen, können Sie das in diesem [Blogbeitrag](https://aka.ms/cqdtools)beschriebene CQDTools-PowerShell-Modul verwenden. Diese Tools basieren auf PowerShell und verwenden Active Directory (AD)-Websites und-Dienste sowie Microsoft DHCP-Dienste, um ihre Gebäude Datei vorab auszufüllen. Diese Tools können Ihnen bei den folgenden Aufgaben helfen:

1. AD-Websites und -Dienste abfragen und basierend auf den darin enthaltenen Informationen eine Gebäudedatei erstellen.
1. Abfragen eines Microsoft DHCP-Servers oder mehrerer Server ab, um Subnetzinformationen abzurufen, und automatisches Erstellen einer Gebäudedatei.
1. Validieren einer vorhandenen Gebäudedatei, Durchsuchen nach Duplikaten und Überlappungen.
1. Suchen nach nicht zugeordneten Subnetzen in CQD.

## <a name="related-topics"></a>Verwandte Themen

[Hochladen von Mandanten und Erstellen von Daten in CQD](CQD-upload-tenant-building-data.md)