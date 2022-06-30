---
title: Konfigurieren von Netzwerkeinstellungen – standortbasiertes Routing
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: Erfahren Sie, wie Sie Netzwerkregionen, Standorte und Subnetze für Location-Based Routing für Direct Routing erstellen und einrichten.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 75aa7b4968ca2a549c35edbccdf6d87bd7df3106
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562614"
---
# <a name="configure-network-settings-for-location-based-routing"></a>Konfigurieren der Netzwerkeinstellungen für das standortbasierte Routing

In diesem Artikel wird beschrieben, wie Sie Netzwerkeinstellungen für Location-Based Routing konfigurieren. Wenn dies noch nicht geschehen ist, lesen Sie ["Planen Location-Based Routing für Direct Routing](location-based-routing-plan.md) ", um weitere Schritte zu überprüfen, die Sie ausführen müssen, bevor Sie Netzwerkeinstellungen konfigurieren.

Nachdem Sie Direct Routing in Ihrer Organisation bereitgestellt haben, sind die nächsten Schritte das Erstellen und Einrichten von Netzwerkregionen, Netzwerkstandorten und Netzwerksubnetzen.

## <a name="define-network-regions"></a>Definieren von Netzwerkregionen

Eine Netzwerkregion enthält eine Sammlung von Netzwerkstandorten und verbindet verschiedene Teile eines Netzwerks über mehrere geografische Bereiche hinweg. Die Schritte zum Konfigurieren von Netzwerkregionen finden [Sie unter Verwalten Ihrer Netzwerktopologie für Cloudfeatures in Teams](manage-your-network-topology.md).

## <a name="define-network-sites"></a>Definieren von Netzwerkstandorten

Ein Netzwerkstandort stellt einen Ort dar, an dem Ihre Organisation über einen physischen Veranstaltungsort verfügt, z. B. ein Büro, eine Reihe von Gebäuden oder einen Campus. Sie müssen jeden Netzwerkstandort in Ihrer Topologie einer Netzwerkregion zuordnen. Schritte zum Konfigurieren von Netzwerkstandorten finden Sie unter [Verwalten Ihrer Netzwerktopologie für Cloudfeatures in Teams](manage-your-network-topology.md).

Eine bewährte Methode für Location-Based Routing ist das Erstellen eines separaten Standorts für jeden Standort mit eindeutiger PSTN-Konnektivität (Public Switched Telephone Network). Sie können eine Website erstellen, die für Location-Based Routing aktiviert ist, oder eine Website, die nicht für Location-Based Routing aktiviert ist. Sie können z. B. eine Website erstellen, die nicht für Location-Based Routing aktiviert ist, damit Benutzer, die für Location-Based Routing aktiviert sind, PSTN-Anrufe tätigen können, wenn sie zu dieser Website wechseln.

## <a name="define-network-subnets"></a>Definieren von Netzwerksubnetzen

Jedes Subnetz muss einem bestimmten Netzwerkstandort zugeordnet sein. Sie können mehrere Subnetze demselben Netzwerkstandort zuordnen, aber nicht mehrere Standorte mit demselben Subnetz verknüpfen. Schritte zum Konfigurieren von Netzwerksubnetzen finden  [Sie unter Verwalten Ihrer Netzwerktopologie für Cloudfeatures in Teams](manage-your-network-topology.md).

Für Location-Based Routing müssen IP-Subnetze an dem Ort, an dem Teams-Endpunkte eine Verbindung mit dem Netzwerk herstellen können, definiert und einem definierten Netzwerk zugeordnet werden, um eine gebührenpflichtige Umgehung zu erzwingen. Diese Zuordnung von Subnetzen ermöglicht es Location-Based Routing, die Endpunkte geografisch zu finden, um zu bestimmen, ob ein bestimmter PSTN-Anruf zulässig sein soll. Sowohl IPv6- als auch IPv4-Subnetze werden unterstützt. Bei der Ermittlung, ob sich ein Teams-Endpunkt an einem Standort befindet, überprüft Location-Based Routing zuerst nach einer übereinstimmenden IPv6-Adresse. Wenn keine IPv6-Adresse vorhanden ist, überprüft Location-Based Routing auf eine IPv4-Adresse.

## <a name="define-trusted-ip-addresses-external-subnets"></a>Definieren vertrauenswürdiger IP-Adressen (externe Subnetze)

Vertrauenswürdige IP-Adressen sind die externen IP-Adressen des Unternehmensnetzwerks und werden verwendet, um festzustellen, ob sich der Endpunkt des Benutzers im Unternehmensnetzwerk befindet. Schritte zum Konfigurieren vertrauenswürdiger IP-Adressen finden Sie unter [Verwalten Ihrer Netzwerktopologie für Cloudfeatures in Teams](manage-your-network-topology.md).

Wenn die externe IP-Adresse des Benutzers mit einer IP-Adresse übereinstimmt, die sich in der Liste der vertrauenswürdigen IP-Adressen befindet, überprüft Location-Based Routing, um das interne Subnetz zu ermitteln, in dem sich der Endpunkt des Benutzers befindet. Wenn die externe IP-Adresse des Benutzers keiner IP-Adresse entspricht, die in der Liste der vertrauenswürdigen IP-Adressen definiert ist, wird der Endpunkt als an einem unbekannten Ort klassifiziert, und PSTN-Anrufe an oder von einem Benutzer, der für Location-Based Routing aktiviert ist, werden blockiert.

## <a name="next-steps"></a>Nächste Schritte

Wechseln Sie zu ["Location-Based Routing für Direct Routing aktivieren](location-based-routing-enable.md)".

## <a name="related-topics"></a>Verwandte Themen

- [Netzwerkeinstellungen für Cloud Voice-Features in Teams](cloud-voice-network-settings.md)
