---
title: URLs und IP-Adressbereiche von Office 365 | Microsoft-Support
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Hier erfahren Sie, wie Sie URLs und IP-Adressen von Office 365 ordnungsgemäß konfigurieren und den Weiterleitungsproxy umgehen, wenn dieser für Verbindungen mit dem Microsoft Teams-Dienst verfügbar ist. Zudem werden Sie über die Anforderungen für Netzwerk- und Sicherheitsrichtlinien informiert."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: a226a2d541119c61a3538c86f3502defb739147d
ms.sourcegitcommit: 2e557e90b4e30fe99ff9df3897b8e54f38ea2f2e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2017
---
<a name="office-365-urls-and-ip-address-ranges"></a>URLs und IP-Adressbereiche von Office 365
=====================================

Über die folgende Verknüpfung erhalten Sie eine detaillierte und aktuelle Liste der genauen IP-Adressen und Ports, die ordnungsgemäß konfiguriert werden müssen: [URLs und IP-Adressbereiche von Office 365](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&rs=en-US&ad=US). Microsoft verbessert fortlaufend den Office 365-Dienst und fügt neue Funktionen hinzu. Aus diesem Grund können sich die erforderlichen Ports, URLs und IP-Adressen von Zeit zu Zeit ändern. Informationen zu den aktuellen Port- und Protokollversionen finden Sie im Handbuch [URLs und IP-Adressbereiche von Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2). Das [Abonnieren eines RSS-Feeds](https://go.microsoft.com/fwlink/p/?linkid=236301) wird ebenfalls dringend empfohlen, um Benachrichtigungen über aktualisierte oder geänderte Endpunkte zu erhalten.

Wie bereits erwähnt, basieren die Anruf- und Besprechungsfunktionen von Microsoft Teams auf der cloudbasierten Infrastruktur der nächsten Generation, die auch von Skype und Skype for Business genutzt wird. Zu diesen Technologieinvestitionen gehören Azure-basierte Clouddienste für Medienverarbeitung und Signalisierung, der Videocodec H.264, die Audiocodecs SILK und Opus, Netzwerkresilienz, Telemetrie und Qualitätsdiagnose. Es gibt daher erforderliche URLs und IP-Adressen, die möglicherweise sowohl Skype als auch Skype for Business zugeordnet sind.

Für alle Office 365-Arbeitsauslastungen besteht die empfohlene Verbindungsmethode zu Microsoft Teams-Diensten darin, den Weiterleitungsproxy zu umgehen (falls möglich). Wenn sich ein Proxyserver zwischen einem Client und den Office 365-Datencentern befindet, werden die Medien möglicherweise über TCP anstelle von UDP erzwungen, wodurch die Medienqualität eingeschränkt wird. Proxy-PAC-Beispieldateien können zum Konfigurieren der Umgehung des Datenverkehrs über das Handbuch [Verwalten von Office 365-Endpunkten](https://support.office.com/article/managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a) heruntergeladen werden.

Wenn es aufgrund Ihrer Netzwerk- und Sicherheitsrichtlinien erforderlich ist, dass der Office 365-Datenverkehr über eine Proxyserver geleitet wird, stellen Sie sicher, dass die Anforderungen oben bereits erfüllt sind, bevor Sie Microsoft Teams in einer Produktionsumgebung bereitstellen (Informationen dazu finden Sie unter [Proxyserver für Skype for Business Online](https://support.office.com/en-us/article/Proxy-Servers-for-Skype-for-Business-Online-7acaf2c2-35fa-490f-84cd-822e446e0fc7?ui=en-US&rs=en-US&ad=US)).
