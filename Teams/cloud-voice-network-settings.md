---
title: Netzwerkeinstellungen für Cloud Voice-Features
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: conceptual
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: Erfahren Sie mehr über die Netzwerkeinstellungen, die Sie für Location-Based Routing für Direct Routing und erweiterte Notfalldienste konfigurieren müssen.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
- m365initiative-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 49709c2c3cc8816b404c88970c6ec916470f200e
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2022
ms.locfileid: "66790150"
---
# <a name="network-settings-for-cloud-voice-features-in-microsoft-teams"></a>Netzwerkeinstellungen für Cloud Voice-Features in Microsoft Teams

Erfahren Sie mehr über Netzwerkregionen, Netzwerkstandorte, Netzwerksubnetze und vertrauenswürdige IP-Adressen. Diese Begriffe und Konzepte werden in unserer [Cloud-VoIP-Dokumentation für standortbasiertes Routing für Direct Routing](location-based-routing-plan.md) und [dynamische Notrufe](configure-dynamic-emergency-calling.md) verwendet. Wenn Sie diese Cloudfeatures in Ihrer Organisation bereitstellen, müssen Sie Netzwerkeinstellungen für die Verwendung mit diesen Features in Microsoft Teams konfigurieren.

In diesem Artikel erhalten Sie einen Überblick über die Netzwerkeinstellungen, die für Location-Based Routing und dynamische Notrufe üblich sind. Abhängig von der Cloud-VoIP-Funktion und -Funktion, die Sie bereitstellen, konfigurieren Sie einige oder alle diese Einstellungen. Schritte zum Konfigurieren dieser Einstellungen finden [Sie unter Verwalten Ihrer Netzwerktopologie für Cloudfeatures in Teams](manage-your-network-topology.md).

> [!NOTE]
> Alle featurespezifischen Anforderungen für Netzwerkeinstellungen sind in den Konfigurationsthemen für dieses Feature dokumentiert.

## <a name="network-region"></a>Netzwerkregion

Eine Netzwerkregion enthält verschiedene Netzwerkstandorte. Es verbindet verschiedene Teile eines Netzwerks über mehrere geografische Bereiche hinweg. Wenn Ihre Organisation beispielsweise über viele Standorte in Indien verfügt, können Sie "Indien" als Netzwerkregion festlegen. Jeder Netzwerkstandort muss einer Netzwerkregion zugeordnet sein.

Die gleichen Netzwerkregionen werden von Location-Based Routing für Direct Routing und erweiterte Notfalldienste gemeinsam genutzt. Wenn Sie bereits Netzwerkregionen für ein Feature erstellt haben, müssen Sie keine neuen Netzwerkregionen für das andere Feature erstellen.

## <a name="network-site"></a>Netzwerkstandort

Ein Netzwerkstandort stellt einen Ort dar, an dem Ihre Organisation über einen physischen Veranstaltungsort verfügt, z. B. ein Büro, eine Reihe von Gebäuden oder einen Campus. Netzwerkstandorte sind als eine Sammlung von IP-Subnetzen definiert. Jeder Netzwerkstandort muss einer Netzwerkregion zugeordnet sein.

Sie können auch Netzwerkstandorte verwenden, um Notrufe zu aktivieren und zu konfigurieren.

## <a name="network-subnet"></a>Netzwerksubnetz

Jedes Subnetz muss einem bestimmten Netzwerkstandort zugeordnet sein. Der Standort eines Clients wird basierend auf dem Netzwerksubnetz und dem zugehörigen Netzwerkstandort bestimmt. Sie können mehrere Subnetze demselben Netzwerkstandort zuordnen, aber nicht mehrere Standorte demselben Subnetz zuordnen.

Subnetzinformationen werden verwendet, um den Netzwerkstandort zu ermitteln, an dem sich ein Endpunkt befindet, wenn eine neue Sitzung initiiert wird. Wenn der Standort jeder Partei in einer Sitzung bekannt ist, kann die Cloud-VoIP-Funktion diese Informationen anwenden, um zu bestimmen, wie die Anrufeinrichtung oder -weiterleitung behandelt wird.

Arbeiten Sie für jeden Netzwerkstandort mit Ihrem Netzwerkadministrator zusammen, um zu ermitteln, welche IP-Subnetze jedem Netzwerkstandort zugewiesen sind. Sie können z. B. dem Standort „New York“ in der Region „Nordamerika“ die folgenden IP-Subnetze zuweisen: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Wenn Bob, der normalerweise in Detroit arbeitet, zur Schulung in das Büro in New York reist, seinen Computer einschaltet und sich mit dem Netzwerk verbindet, erhält sein Computer eine IP-Adresse in einem der vier Bereiche, die New York zugeordnet sind, z. B. 172.29.80.103.

## <a name="trusted-ip-address"></a>Vertrauenswürdige IP-Adresse

Vertrauenswürdige IP-Adressen sind die externen IP-Adressen des Unternehmensnetzwerks. Sie bestimmen, ob sich der Endpunkt des Benutzers innerhalb des Unternehmensnetzwerks befindet, bevor eine bestimmte Übereinstimmung mit der Website überprüft wird.

Wenn die externe IP-Adresse des Benutzers mit einer IP-Adresse übereinstimmt, die sich in der Liste der vertrauenswürdigen IP-Adressen befindet, überprüft das Cloud voice-Feature, um das interne Subnetz zu ermitteln, in dem sich der Endpunkt des Benutzers befindet. Eine Übereinstimmung kann für IPv4- oder IPv6-IP-Adressen vorgenommen werden und hängt vom Format des IP-Pakets ab, das an die Netzwerkeinstellungen gesendet wird. (Wenn eine öffentliche IP-Adresse sowohl IPv4 als auch IPv6 aufweist, müssen Sie beide als vertrauenswürdige IP-Adressen hinzufügen.)

Wenn die externe IP-Adresse des Benutzers nicht mit einer IP-Adresse übereinstimmt, die sich in der Liste der vertrauenswürdigen IP-Adressen befindet, wird der Endpunkt als an einem unbekannten Speicherort klassifiziert.

> [!Important]
> Netzwerkkonfigurationseinstellungssuchen werden bei Bereitstellungen von Cloudproxydiensten, die die Quell-IP-Adressen von Teams-Clients ändern, nicht unterstützt.
