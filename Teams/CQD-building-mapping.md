---
title: Erstellen einer Gebäudekarte für das Anrufqualitätsdashboard (CQD)
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: Erfahren Sie, wie Sie eine Gebäudezuordnung erstellen, die Sie zum Hochladen von Mandanten- und Gebäudedaten im Anrufqualitätsdashboard (CQD) verwenden können.
ms.openlocfilehash: 71d1872bbd81769f9a49f4ca9f6ac9aae641252f
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789820"
---
# <a name="create-a-building-map-for-call-quality-dashboard-cqd"></a>Erstellen einer Gebäudekarte für das Anrufqualitätsdashboard (CQD)

In einer Microsoft Teams- oder Skype for Business Onlinebereitstellung sind alle Clients extern. Daher werden standardmäßig alle Clients im Anrufqualitätsdashboard (Call Quality Dashboard, CQD) als extern gemeldet, unabhängig davon, ob der Client in einem internen Unternehmensnetzwerk verbunden ist.

Wenn Sie mit CQD arbeiten, müssen Sie den Standort eines Endpunkts kennen und wissen, ob er mit einem Netzwerk verbunden war, das Sie verwalten können oder ein Netzwerk, das Sie nicht verwalten können. Es wird davon ausgegangen, dass Sie nur Netzwerke verbessern können, die Sie verwalten können. Indem Sie Subnetz- und Gebäudeinformationen in CQD hochladen, können Sie CQD aktivieren, um zu bestimmen, ob der Endpunkt mit einem internen (verwalteten) Netzwerk oder mit einem externen (nicht verwalteten) Netzwerk verbunden war. Aus diesem Grund ist es wichtig, eine Gebäudekarte für Ihre Organisation zu erstellen und [auf CQD hochzuladen](CQD-upload-tenant-building-data.md).

## <a name="building-mapping-tools"></a>Tools für die Gebäudezuordnung

Es gibt viele Möglichkeiten, die Subnetze Ihrer Organisation zuzuordnen. Wenn Sie Hilfe benötigen, können Sie das in diesem [Blogbeitrag](https://aka.ms/cqdtools) beschriebene CQDTools PowerShell-Modul verwenden. Diese Tools basieren auf PowerShell und verwenden Active Directory(AD)-Websites und -Dienste sowie Microsoft DHCP-Dienste, um Die Gebäudedatei vorab aufzufüllen. Diese Tools können Ihnen bei den folgenden Aufgaben helfen:

1. AD-Websites und -Dienste abfragen und basierend auf den darin enthaltenen Informationen eine Gebäudedatei erstellen.
1. Abfragen eines Microsoft DHCP-Servers oder mehrerer Server ab, um Subnetzinformationen abzurufen, und automatisches Erstellen einer Gebäudedatei.
1. Validieren einer vorhandenen Gebäudedatei, Durchsuchen nach Duplikaten und Überlappungen.
1. Suchen nach nicht zugeordneten Subnetzen in CQD.

## <a name="related-topics"></a>Verwandte Themen

[Hochladen von Mandanten- und Gebäudedaten in CQD](CQD-upload-tenant-building-data.md)