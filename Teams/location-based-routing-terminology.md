---
title: Terminologie für das standortbasierte Routing
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: conceptual
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: Informationen zu Terminologie und Konzepten, die mit Standort basiertem Routing für das direkte Routing verknüpft sind.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9d35b42453ac0eb9d9ae4a3f4c71f4452943a3b0
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245095"
---
# <a name="location-based-routing-terminology"></a>Terminologie für das standortbasierte Routing

> [!INCLUDE [Preview customer token](includes/preview-feature.md)] 

Nachfolgend finden Sie einige Begriffe und Konzepte, die in der standortbasierten Routing Dokumentation verwendet werden. Es ist ratsam, sich mit diesen Begriffen und Konzepten vertraut zu machen, bevor Sie die Dokumentation näher kennenlernen.

|Begriff  |Beschreibung  |
|---------|---------|
|Netzwerkregionen     | Eine Netzwerkregion enthält verschiedene Netzwerkstandorte. Wenn Ihre Organisation beispielsweise viele Websites in Indien hat, können Sie "Indien" als netzwerkregion angeben.        |
|Netzwerk Websites    | Eine Netzwerk Website steht für einen Standort, an dem Ihre Organisation über einen physikalischen Ort verfügt, beispielsweise ein Büro, einen Satz von Gebäuden oder einen Campus. Netzwerk Websites werden als eine Sammlung von IP-Subnetzen definiert. Eine bewährte Methode für standortbasiertes Routing ist das Erstellen einer separaten Website für jeden Standort, der über eine eindeutige PSTN-Konnektivität verfügt.  Jede Netzwerk Website muss einem Netzwerkbereich zugeordnet sein. Sie können eine Website erstellen, die für standortbasiertes Routing oder eine Website aktiviert ist, die für standortbasiertes Routing nicht aktiviert ist. So können Sie beispielsweise eine Website erstellen, die für standortbasiertes Routing nicht aktiviert ist, damit Benutzer, die für standortbasiertes Routing aktiviert sind, PSTN-Anrufe tätigen können, wenn Sie zu dieser Website wechseln. Beachten Sie, dass Netzwerk Websites auch zum Aktivieren und Konfigurieren von Notrufen verwendet werden können.        |
|Netzwerk-Subnetze     |IP-Subnetze an der Stelle, an der die Teams-Endpunkte eine Verbindung mit dem Netzwerk herstellen können, müssen definiert und einem festgelegten Netzwerk zugeordnet werden, um Maut Umgehung zu erzwingen Mehrere Subnetze sind möglicherweise mit derselben Netzwerk Website verknüpft, aber mehrere Websites sind möglicherweise nicht mit demselben Subnetz verbunden. Diese Zuordnung von Subnetzen ermöglicht standortbasiertes Routing, die Endpunkte geografisch zu finden, um festzustellen, ob ein bestimmter PSTN-Anruf zulässig ist. Sowohl IPv6-als auch IPv4-Subnetze werden unterstützt. Wenn Sie feststellen, ob sich ein Teams-Endpunkt an einer Website befindet, überprüft standortbasiertes Routing zunächst auf eine übereinstimmende IPv6-Adresse. Wenn keine IPv6-Adresse vorhanden ist, überprüft standortbasiertes Routing auf eine IPv4-Adresse. <br><br>
|Vertrauenswürdige externe IP-Adressen    |Vertrauenswürdige externe IP-Adressen sind die Internet-externen IP-Adressen des Unternehmensnetzwerks. Sie bestimmen, ob sich der Endpunkt des Benutzers innerhalb des Unternehmensnetzwerks befindet, bevor er auf eine bestimmte Website Übereinstimmung überprüft wird. Wenn die externe IP-Adresse des Benutzers mit einer IP-Adresse übereinstimmt, die in der vertrauenswürdigen Liste definiert ist, überprüft standortbasiertes Routing, um das interne Subnetz zu ermitteln, in dem sich der Endpunkt des Benutzers befindet. Wenn die externe IP-Adresse des Benutzers keiner IP-Adresse entspricht, die in der vertrauenswürdigen Liste definiert ist, wird der Endpunkt als an einem unbekannten Speicherort klassifiziert, und alle PSTN-Anrufe an oder von einem Benutzer, der für standortbasiertes Routing aktiviert ist, werden blockiert.          |

### <a name="related-topics"></a>Verwandte Themen
- [Planen des standortbasierten Routings für direktes Routing](location-based-routing-plan.md)
- [Konfigurieren der Netzwerkeinstellungen für das standortbasierte Routing](location-based-routing-configure-network-settings.md)
- [Aktivieren des standortbasierten Routings für direktes Routing](location-based-routing-enable.md)
