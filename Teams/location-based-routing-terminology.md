---
title: Terminologie für das standortbasierte Routing
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
search.appverid: MET150
description: Hier erfahren Sie, Terminologie und Konzepte speicherortbasierte Routing für das direkte Routing zugeordnet.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- Strat_SB_PSTN
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 122ded988b9bf3c2cd8d439e84cb132e3a3f690d
ms.sourcegitcommit: 59eda0c17ff39a3e6632810391d78bbadc214419
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/01/2019
ms.locfileid: "30352331"
---
# <a name="location-based-routing-terminology"></a>Terminologie für das standortbasierte Routing

> [!INCLUDE [Preview customer token](includes/preview-feature.md)] 

Hier sind einige Begriffe und Konzepte, die in der gesamten standortbasierten Routing-Dokumentation verwendet werden. Es ist ratsam, die mit diesen Begriffen und Konzepten vertraut sein, bevor Sie in der Dokumentation tiefer erhalten.

|Begriff  |Beschreibung  |
|---------|---------|
|Netzwerkregionen     | Eine Netzwerkregion enthält verschiedene Netzwerkstandorte. Wenn Ihre Organisation viele Standorte in Indien verfügt, können Sie beispielsweise "Indien" als eine netzwerkregion festzulegen.        |
|Netzwerkstandorte    | Ein Netzwerkstandort stellt einen Speicherort, in dem Ihre Organisation eine physische Ort, wie ein Büro, eine Reihe von Gebäude oder ein Campus verfügt. Netzwerkstandorte sind als eine Auflistung von IP-Subnetze definiert. Bewährte Methode für das Routing speicherortbasierte ist für jeden Standort eine separate Website erstellen, die eindeutige PSTN-Anbindung hat.  Jedem Netzwerkstandort muss eine netzwerkregion zugeordnet werden. Sie können Erstellen einer Website, die für das Routing speicherortbasierte aktiviert ist oder einer Website, die für das Routing speicherortbasierte nicht aktiviert ist. Beispiel: Sie möchten eine Website erstellen, die nicht aktiviert ist, für das Routing speicherortbasierte, um Benutzern zu ermöglichen, die für das Routing an PSTN-Anrufe zu tätigen, wenn sie diese Website Roaming speicherortbasierte aktiviert sind. Beachten Sie, dass Netzwerkstandorten auch zur Aktivierung und Konfiguration von notrufdienste verwendet werden.        |
|Von Netzwerksubnetzen     |IP-Subnetze an der Stelle, wo Teams Endpunkte mit dem Netzwerk verbinden können, müssen definiert und verknüpft ist mit einem definierten Netzwerk zum Erzwingen von gebührenpflichtige umgehen. Mehrere Subnetze möglicherweise den gleichen Netzwerkstandort zugeordnet, aber mehrere Websites möglicherweise kein demselben Subnetz zugeordnet. Diese Zuordnung von Subnetzen ermöglicht speicherortbasierte Routing, suchen die Endpunkte geografisch, um festzustellen, ob es sich bei ein bestimmten PSTN-Anruf zugelassen werden soll. Sowohl IPv4 als auch IPv6-Subnetze werden unterstützt. Bei der Entscheidung, ob ein Endpunkt Teams an einem Standort befindet, überprüft speicherortbasierte Routing zuerst entsprechende IPv6-Adresse. Wenn Sie eine IPv6-Adresse nicht vorhanden ist, überprüft speicherortbasierte Routing für eine IPv4-Adresse. <br><br>Unterstützung für IPv6 ist in Arbeit und wird durch allgemeine Verfügbarkeit (GA) des Routing speicherortbasierte verfügbar sein.          |
|Vertrauenswürdige externe IP-Adressen    |Vertrauenswürdige externe IP-Adressen sind Internet externen IP-Adressen des Unternehmensnetzwerks. Sie bestimmen, ob der Endpunkt des Benutzers innerhalb des Unternehmensnetzwerks ist, bevor Sie eine bestimmte Website Übereinstimmung gesucht. Wenn externe IP-Adresse des Benutzers eine IP-Adresse, die in der Liste der vertrauenswürdigen definiert wird übereinstimmt, überprüft speicherortbasierte Routing im interne Subnetz bestimmen, wo sich der Endpunkt des Benutzers befindet. Wenn externe IP-Adresse des Benutzers beliebige IP-Adresse übereinstimmt, die in der Liste der vertrauenswürdigen definiert ist, der Endpunkt gilt als an einem unbekannten Standort wird und alle PSTN-Anrufe zu oder von einem Benutzer, die für das Routing speicherortbasierte aktiviert ist, werden blockiert.          |

### <a name="related-topics"></a>Verwandte Themen
- [Planen des standortbasierten Routings für direktes Routing](location-based-routing-plan.md)
- [Konfigurieren der Netzwerkeinstellungen für das standortbasierte Routing](location-based-routing-configure-network-settings.md)
- [Aktivieren des standortbasierten Routings für direktes Routing](location-based-routing-enable.md)
