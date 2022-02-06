---
title: Konfigurieren von Netzwerkeinstellungen – Standortbasiertes Routing
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: 'Hier erfahren Sie, wie Sie Netzwerkregionen, Standorte und Subnetze für die Verwendung Location-Based Direct-Routing erstellen und einrichten.'
ms.localizationpriority: medium
f1.keywords:
  - NOCSH
ms.collection:
  - M365-voice
appliesto:
  - Microsoft Teams
ms.custom: seo-marvel-mar2020
---

# <a name="configure-network-settings-for-location-based-routing"></a>Konfigurieren der Netzwerkeinstellungen für das standortbasierte Routing

Wenn dies noch nicht geschehen ist, lesen Sie Planen von Location-Based-Routing für [Direct-Routing](location-based-routing-plan.md) , um weitere Schritte zu überprüfen, die Sie ausführen müssen, bevor Sie die Netzwerkeinstellungen für das Routing Location-Based konfigurieren.

In diesem Artikel wird beschrieben, wie Sie Netzwerkeinstellungen für das Routing Location-Based konfigurieren. Nachdem Sie Ihr Telefonsystem Direct-Routing in Ihrer Organisation bereitgestellt haben, sind die nächsten Schritte das Erstellen und Einrichten von Netzwerkregionen, Netzwerkstandorten und Netzwerksubnetzen.

## <a name="define-network-regions"></a>Definieren von Netzwerkregionen

Eine Netzwerkregion enthält eine Sammlung von Netzwerkwebsites und verbindet verschiedene Teile eines Netzwerks über mehrere geografische Bereiche hinweg. Die Schritte zum Konfigurieren von Netzwerkregionen finden Sie unter [Verwalten der Netzwerktopologie für Cloudfeatures in Teams](manage-your-network-topology.md).

## <a name="define-network-sites"></a>Definieren von Netzwerkwebsites

Ein Netzwerkstandort steht für einen Ort, an dem Ihre Organisation über einen physischen Veranstaltungsort verfügt, z. B. ein Büro, eine Gruppe von Gebäuden oder einen Campus. Sie müssen jede Netzwerkwebsite in der Topologie einer Netzwerkregion zuordnen. Die Schritte zum Konfigurieren von Netzwerkwebsites finden Sie unter [Verwalten der Netzwerktopologie für Cloudfeatures in Teams](manage-your-network-topology.md).

Eine bewährte Methode für Location-Based Besteht im Erstellen einer separaten Website für jeden Standort, der über eine eindeutige PSTN-Verbindung verfügt. Sie können eine Website erstellen, die für Routing Location-Based aktiviert ist, oder eine Website, die nicht für das Routing Location-Based ist. So möchten Sie beispielsweise eine Website erstellen, die nicht für Location-Based-Routing aktiviert ist, damit Benutzer, die für Location-Based-Routing aktiviert sind, PSTN-Anrufe beim Routing zu dieser Website verwenden können.

## <a name="define-network-subnets"></a>Definieren von Netzwerk-Subnetzen

Jedes Subnetz muss einem bestimmten Netzwerkstandort zugeordnet sein. Sie können demselben Netzwerkstandort mehrere Subnetze, aber nicht mehrere Standorte demselben Subnetz zuordnen. Die Schritte zum Konfigurieren von Netzwerksubnetzen finden Sie unter [Verwalten der Netzwerktopologie für Cloudfunktionen in Teams](manage-your-network-topology.md).

Für Location-Based-Routing müssen IP-Subnetze an dem Standort, an dem Teams-Endpunkte eine Verbindung mit dem Netzwerk herstellen können, definiert und einem definierten Netzwerk zugeordnet sein, um eine gebührenpflichtige Umgehung zu erzwingen. Durch diese Zuordnung von Subnetzen Location-Based Routing die Endpunkte geografisch finden, um zu bestimmen, ob ein gegebener PSTN-Anruf zulässig sein soll. Sowohl IPv6- als auch IPv4-Subnetze werden unterstützt. Bei der Ermittlung, Teams sich ein Endpunkt an einem Standort befindet, überprüft Location-Based Routing zuerst auf eine übereinstimmende IPv6-Adresse. Wenn keine IPv6-Adresse vorhanden ist, wird Location-Based auf eine IPv4-Adresse überprüft.

## <a name="define-trusted-ip-addresses-external-subnets"></a>Definieren vertrauenswürdiger IP-Adressen (externe Subnetze)

Vertrauenswürdige IP-Adressen sind die externen Internet-IP-Adressen des Unternehmensnetzwerks und werden verwendet, um festzustellen, ob sich der Endpunkt des Benutzers innerhalb des Unternehmensnetzwerks befindet. Die Schritte zum Konfigurieren von vertrauenswürdigen IP-Adressen finden Sie unter [Verwalten der Netzwerktopologie für Cloudfeatures in Teams](manage-your-network-topology.md).

Wenn die externe IP-Adresse des Benutzers einer IP-Adresse entspricht, die in der Liste der vertrauenswürdigen IP-Adressen aufgeführt ist, überprüft Location-Based Routing, um das interne Subnetz zu ermitteln, in dem sich der Endpunkt des Benutzers befindet. Wenn die externe IP-Adresse des Benutzers nicht mit einer IP-Adresse übereinstimmen, die in der Liste der vertrauenswürdigen IP-Adressen definiert ist, wird der Endpunkt als an einem unbekannten Ort klassifiziert, und alle PSTN-Anrufe an oder von einem Benutzer, der für Location-Based Routing aktiviert ist, werden blockiert.

## <a name="next-steps"></a>Nächste Schritte

Wechseln Sie [zu Aktivieren Location-Based Für Direct-Routing](location-based-routing-enable.md).

## <a name="related-topics"></a>Verwandte Themen

- [Netzwerkeinstellungen für Cloud-Sprachfeatures in Teams](cloud-voice-network-settings.md)
