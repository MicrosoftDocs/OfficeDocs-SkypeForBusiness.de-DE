---
title: Netzwerkeinstellungen für Cloud Voice-Features
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: Erfahren Sie mehr über die Netzwerkeinstellungen, die Sie für das Routing Location-Based Direct-Routing und erweiterte Notfalldienste konfigurieren müssen.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
- m365initiative-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 10547a99b0e63585ae39cc90a5b0cf573a9c94e3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834335"
---
# <a name="network-settings-for-cloud-voice-features-in-microsoft-teams"></a>Netzwerkeinstellungen für Cloud-Sprachfeatures in Microsoft Teams

Erfahren Sie mehr über Netzwerkregionen, Netzwerkstandorte, Netzwerk-Subnetze und vertrauenswürdige IP-Adressen. Diese Begriffe und Konzepte werden in der gesamten Cloud-Sprachdokumentation für standortbasiertes Routing für [Direct-Routing](location-based-routing-plan.md) und [dynamische Notrufe verwendet.](configure-dynamic-emergency-calling.md) Wenn Sie diese Cloudfeatures in Ihrer Organisation bereitstellen, müssen Sie netzwerkeinstellungen für die Verwendung dieser Features in ihrer Microsoft Teams.

Dieser Artikel enthält eine Übersicht über die Netzwerkeinstellungen, die für das Routing und dynamische Notrufe Location-Based Netzwerkverbindung verwendet werden. Je nach Cloud-Sprachfunktion und -funktion, die Sie bereitstellen, konfigurieren Sie einige oder alle diese Einstellungen. Die Schritte zum Konfigurieren dieser Einstellungen finden Sie unter [Verwalten der Netzwerktopologie für Cloudfeatures in Teams.](manage-your-network-topology.md)

> [!NOTE]
> Alle featurespezifischen Anforderungen für Netzwerkeinstellungen sind in den Konfigurationsthemen für dieses Feature dokumentiert.

## <a name="network-region"></a>Netzwerkregion

Eine Netzwerkregion enthält verschiedene Netzwerkstandorte. Sie verbindet verschiedene Teile eines Netzwerks über mehrere geografische Bereiche hinweg. Wenn Ihre Organisation beispielsweise viele Standorte in Indien hat, können Sie "Indien" als Netzwerkregion festlegen. Jede Netzwerkwebsite muss einer Netzwerkregion zugeordnet sein.

Die gleichen Netzwerkregionen werden von Location-Based Routing für Direct-Routing und erweiterte Notfalldienste gemeinsam genutzt. Wenn Sie bereits Netzwerkregionen für ein Feature erstellt haben, müssen Sie für das andere Feature keine neuen Netzwerkregionen erstellen.

## <a name="network-site"></a>Netzwerkwebsite

Ein Netzwerkstandort steht für einen Ort, an dem Ihre Organisation über einen physischen Veranstaltungsort verfügt, z. B. ein Büro, eine Gruppe von Gebäuden oder einen Campus. Netzwerkstandorte sind als eine Sammlung von IP-Subnetzen definiert. Jede Netzwerkwebsite muss einer Netzwerkregion zugeordnet sein.

Sie können auch Netzwerkwebsites verwenden, um Notrufe zu aktivieren und zu konfigurieren.

## <a name="network-subnet"></a>Netzwerk-Subnetz

Jedes Subnetz muss einem bestimmten Netzwerkstandort zugeordnet sein. Der Standort eines Clients wird basierend auf dem Netzwerksubnetz und dem zugehörigen Netzwerkstandort bestimmt. Sie können demselben Netzwerkstandort mehrere Subnetze, aber nicht mehrere Standorte demselben Subnetz zuordnen.

Subnetzinformationen werden verwendet, um den Netzwerkstandort zu ermitteln, an dem sich ein Endpunkt befindet, wenn eine neue Sitzung initiiert wird. Wenn der Standort jeder Partei in einer Sitzung bekannt ist, kann das Cloud-Sprachfeature diese Informationen anwenden, um zu bestimmen, wie die Anrufeinrichtung oder das Routing zu behandeln ist.

Bestimmen Sie für jeden Netzwerkstandort zusammen mit dem Netzwerkadministrator, welche IP-Subnetze den einzelnen Netzwerkstandorten zugewiesen sind. Sie können z. B. dem Standort „New York“ in der Region „Nordamerika“ die folgenden IP-Subnetze zuweisen: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Wenn Bob, der normalerweise in Usa arbeitet, zu einer Schulung in New York reist, seinen Computer aktiviert und eine Verbindung mit dem Netzwerk herstellt, bekommt sein Computer eine IP-Adresse in einem der vier Bereiche, die New York zugewiesen sind, z. B. 172.29.80.103.

## <a name="trusted-ip-address"></a>Vertrauenswürdige IP-Adresse

Vertrauenswürdige IP-Adressen sind die externen Internetadressen des Unternehmensnetzwerks. Sie bestimmen, ob sich der Endpunkt des Benutzers innerhalb des Unternehmensnetzwerks befindet, bevor eine Überprüfung auf eine bestimmte Übereinstimmung der Website besteht.

Wenn die externe IP-Adresse des Benutzers einer IP-Adresse entspricht, die in der Liste der vertrauenswürdigen IP-Adressen aufgeführt ist, überprüft das Cloud-Sprachfeature, um das interne Subnetz zu ermitteln, in dem sich der Endpunkt des Benutzers befindet. Eine Übereinstimmung kann mit IPv4- oder IPv6-IP-Adressen vorgenommen werden und hängt vom Format des IP-Pakets ab, das an die Netzwerkeinstellungen gesendet wurde. (Wenn eine öffentliche IP-Adresse sowohl IPv4 als auch IPv6 enthält, müssen Sie beide als vertrauenswürdige IP-Adressen hinzufügen.)

Wenn die externe IP-Adresse des Benutzers nicht mit einer IP-Adresse in der Liste der vertrauenswürdigen IP-Adressen übereinstimmen, wird der Endpunkt als an einem unbekannten Speicherort klassifiziert.
