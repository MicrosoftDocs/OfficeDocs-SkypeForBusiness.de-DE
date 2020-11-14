---
title: Netzwerkeinstellungen für Cloud Voice-Features
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: Informieren Sie sich über die Netzwerkeinstellungen, die Sie für Location-Based Routing für Direct Routing und erweiterte Notfalldienste konfigurieren müssen.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
- m365initiative-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a01f80e00be75600fdd93f9758a1974b57954e87
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031831"
---
# <a name="network-settings-for-cloud-voice-features-in-microsoft-teams"></a>Netzwerkeinstellungen für Cloud-Sprachfeatures in Microsoft Teams

Erfahren Sie mehr über netzwerkregionen, Netzwerk Websites, Netzwerk-Subnetze und vertrauenswürdige IP-Adressen. Diese Begriffe und Konzepte werden in unserer Cloud-Sprachdokumentation für [standortbasiertes Routing für direktes Routing](location-based-routing-plan.md) und [dynamische Notrufe](configure-dynamic-emergency-calling.md)verwendet. Wenn Sie diese Cloud-Features in Ihrer Organisation bereitstellen, müssen Sie die Netzwerkeinstellungen für die Verwendung mit diesen Features in Microsoft Teams konfigurieren.

In diesem Artikel erhalten Sie einen Überblick über die Netzwerkeinstellungen, die für Location-Based Routing und dynamische Notrufe üblich sind. Je nach der von Ihnen bereitgestellten Cloud-Sprachfunktion und-Funktion konfigurieren Sie einige oder alle dieser Einstellungen. Eine schrittweise Anleitung zum Konfigurieren dieser Einstellungen finden Sie unter [Verwalten der Netzwerktopologie für Cloud-Features in Teams](manage-your-network-topology.md).

> [!NOTE]
> Alle funktionsspezifischen Anforderungen für Netzwerkeinstellungen werden in den Konfigurationsthemen für dieses Feature dokumentiert.

## <a name="network-region"></a>Netzwerkregion

Eine Netzwerkregion enthält verschiedene Netzwerkstandorte. Es verbindet verschiedene Teile eines Netzwerks über mehrere geographische Regionen hinweg. Wenn Ihre Organisation beispielsweise viele Websites in Indien hat, können Sie "Indien" als netzwerkregion angeben. Jede Netzwerk Website muss einem Netzwerkbereich zugeordnet sein.

Die gleichen netzwerkregionen werden von Location-Based Routing für direktes Routing und erweiterte Notfalldienste freigegeben. Wenn Sie bereits netzwerkregionen für ein Feature erstellt haben, müssen Sie keine neuen netzwerkregionen für das andere Feature erstellen.

## <a name="network-site"></a>Netzwerk Website

Eine Netzwerk Website steht für einen Standort, an dem Ihre Organisation über einen physikalischen Ort verfügt, beispielsweise ein Büro, einen Satz von Gebäuden oder einen Campus. Netzwerk Websites werden als eine Sammlung von IP-Subnetzen definiert. Jede Netzwerk Website muss einem Netzwerkbereich zugeordnet sein.

Sie können auch Netzwerk Websites verwenden, um Notrufe zu aktivieren und zu konfigurieren.

## <a name="network-subnet"></a>Netzwerk-Subnetz

Jedes Subnetz muss einer bestimmten Netzwerk Website zugeordnet sein. Der Standort eines Clients wird basierend auf dem Netzwerk-Subnetz und der zugehörigen Netzwerk Website bestimmt. Sie können mehrere Subnetze mit derselben Netzwerk Website verknüpfen, aber Sie können nicht mehrere Websites mit demselben Subnetz verknüpfen.

Subnetinformationen werden verwendet, um die Netzwerk Website zu ermitteln, auf der sich ein Endpunkt befindet, wenn eine neue Sitzung initiiert wird. Wenn die Position jeder Partei in einer Sitzung bekannt ist, kann die Cloud-Sprachfunktion diese Informationen anwenden, um festzulegen, wie die Anrufeinrichtung oder das Routing gehandhabt werden soll.

Arbeiten Sie für jede Netzwerk Website mit Ihrem Netzwerkadministrator zusammen, um zu ermitteln, welche IP-Subnetze jedem Netzwerkstandort zugewiesen sind. Sie können z. B. dem Standort „New York“ in der Region „Nordamerika“ die folgenden IP-Subnetze zuweisen: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Wenn Bob, der in der Regel in Detroit arbeitet, in das Büro von New York für Schulungen reist, seinen Computer anwendet und eine Verbindung mit dem Netzwerk herstellt, erhält sein Computer eine IP-Adresse in einem der vier Bereiche, die für New York zugewiesen sind, beispielsweise 172.29.80.103.

## <a name="trusted-ip-address"></a>Vertrauenswürdige IP-Adresse

Vertrauenswürdige IP-Adressen sind die Internet externen IP-Adressen des Unternehmensnetzwerks. Sie bestimmen, ob sich der Endpunkt des Benutzers innerhalb des Unternehmensnetzwerks befindet, bevor er auf eine bestimmte Website Übereinstimmung überprüft wird.

Wenn die externe IP-Adresse des Benutzers mit einer IP-Adresse übereinstimmt, die sich in der Liste der vertrauenswürdigen IP-Adressen befindet, überprüft das Cloud-Sprachfeature das interne Subnetz, in dem sich der Endpunkt des Benutzers befindet. Eine Übereinstimmung kann entweder für IPv4-oder IPv6-IP-Adressen erfolgen und hängt vom Format des IP-Pakets ab, das an die Netzwerkeinstellungen gesendet wird. (Wenn eine öffentliche IP-Adresse sowohl IPv4 als auch IPv6 hat, müssen Sie beide als vertrauenswürdige IP-Adressen hinzufügen.)

Wenn die externe IP-Adresse des Benutzers nicht mit einer IP-Adresse übereinstimmt, die sich in der Liste der vertrauenswürdigen IP-Adressen befindet, wird der Endpunkt als an einem unbekannten Speicherort klassifiziert.
