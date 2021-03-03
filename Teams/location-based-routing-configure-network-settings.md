---
title: Konfigurieren von Netzwerkeinstellungen – standortbasiertes Routing
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: Hier erfahren Sie, wie Sie Netzwerkbereiche, Standorte und Subnetze für die Verwendung Location-Based für direktes Routing erstellen und einrichten.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a7dd707a6066cfe9a8dfcbcc9b3ae36d450d1dd1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822945"
---
# <a name="configure-network-settings-for-location-based-routing"></a>Konfigurieren der Netzwerkeinstellungen für das standortbasierte Routing

Wenn dies noch nicht geschehen ist, lesen Sie "Plan Location-Based Routing für [Direct-Routing",](location-based-routing-plan.md) um weitere Schritte zu überprüfen, die Sie ausführen müssen, bevor Sie Netzwerkeinstellungen für das Routing Location-Based konfigurieren.

In diesem Artikel wird beschrieben, wie Sie Netzwerkeinstellungen für das Routing Location-Based konfigurieren. Nachdem Sie das direkte Telefonsystemrouting in Ihrer Organisation bereitgestellt haben, müssen Sie im nächsten Schritt Netzwerkregionen, Netzwerkstandorte und Netzwerksubnetze erstellen und einrichten.

## <a name="define-network-regions"></a>Definieren von Netzwerkregionen

Eine Netzwerkregion enthält eine Sammlung von Netzwerkwebsites und verbindet verschiedene Teile eines Netzwerks über mehrere geografische Bereiche hinweg. Schritte zum Konfigurieren von Netzwerkregionen finden Sie unter ["Verwalten Ihrer Netzwerktopologie für Cloudfeatures in Teams".](manage-your-network-topology.md)

## <a name="define-network-sites"></a>Definieren von Netzwerkwebsites

Eine Netzwerkwebsite stellt einen Ort dar, an dem Ihre Organisation über einen Veranstaltungsort verfügt, z. B. ein Büro, eine Reihe von Gebäuden oder einen Campus. Sie müssen jede Netzwerkwebsite in Ihrer Topologie einem Netzwerkbereich zuordnen. Schritte zum Konfigurieren von Netzwerkwebsites finden Sie unter ["Verwalten Ihrer Netzwerktopologie für Cloudfeatures in Teams".](manage-your-network-topology.md)

Eine bewährte Methode für das Location-Based besteht im Erstellen einer separaten Website für jeden Standort mit eindeutiger PSTN-Konnektivität. Sie können eine Website erstellen, die für das Routing Location-Based aktiviert ist, oder eine Website, die nicht für das Routing Location-Based ist. So möchten Sie beispielsweise eine Website erstellen, die nicht für Location-Based-Routing aktiviert ist, damit Benutzer, die für das Routing von Location-Based aktiviert sind, beim Routing zu dieser Website Anrufe über das Festnetz erhalten.

## <a name="define-network-subnets"></a>Definieren von Netzwerksubnetzen

Jedes Subnetz muss einem bestimmten Netzwerkstandort zugeordnet sein. Sie können demselben Netzwerkstandort mehrere Subnetze, aber nicht mehrere Standorte demselben Subnetz zuordnen. Schritte zum Konfigurieren von Netzwerksubnetzen finden Sie unter "Verwalten Ihrer [Netzwerktopologie für Cloudfeatures in Teams".](manage-your-network-topology.md)

Für Location-Based müssen IP-Subnetze an dem Ort, an dem Die Endpunkte von Teams eine Verbindung mit dem Netzwerk herstellen können, definiert und einem definierten Netzwerk zugeordnet sein, um die gebührenpflichtige Umgehung zu erzwingen. Diese Zuordnung von Subnetzen ermöglicht Location-Based, die Endpunkte geografisch zu finden, um zu bestimmen, ob ein gegebener Festnetzanruf zulässig sein soll. Sowohl IPv6- als auch IPv4-Subnetze werden unterstützt. Bei der Ermittlung, ob sich ein Endpunkt in Teams an einer Website befindet, überprüft Location-Based Routing zuerst auf eine übereinstimmende IPv6-Adresse. Wenn keine IPv6-Adresse vorhanden ist, wird Location-Based A0 auf eine IPv4-Adresse überprüft.

## <a name="define-trusted-ip-addresses-external-subnets"></a>Definieren vertrauenswürdiger IP-Adressen (externe Subnetze)

Vertrauenswürdige IP-Adressen sind die externen Internetadressen des Unternehmensnetzwerks und werden verwendet, um festzustellen, ob sich der Endpunkt des Benutzers innerhalb des Unternehmensnetzwerks befindet. Schritte zum Konfigurieren von vertrauenswürdigen IP-Adressen finden Sie unter "Verwalten Ihrer [Netzwerktopologie für Cloudfeatures in Teams".](manage-your-network-topology.md)

Wenn die externe IP-Adresse des Benutzers einer in der Liste der vertrauenswürdigen IP-Adressen aufgeführten IP-Adresse entspricht, überprüft Location-Based Routing, ob das interne Subnetz ermittelt wird, in dem sich der Endpunkt des Benutzers befindet. Wenn die externe IP-Adresse des Benutzers nicht mit einer in der Liste der vertrauenswürdigen IP-Adresslisten definierten IP-Adresse übereinstimmen, wird der Endpunkt als an einem unbekannten Speicherort klassifiziert, und alle ANRUFE über das Festnetz an oder von einem Benutzer, der für das Routing aktiviert ist, Location-Based werden blockiert.

## <a name="next-steps"></a>Nächste Schritte

Wechseln Sie [zu "Enable Location-Based Routing for Direct Routing".](location-based-routing-enable.md)

## <a name="related-topics"></a>Verwandte Themen

- [Netzwerkeinstellungen für Cloud-Sprachfeatures in Teams](cloud-voice-network-settings.md)
