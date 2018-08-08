---
title: URLs und IP-Adressbereiche von Office 365
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
description: Hier erfahren Sie, wie Sie URLs und IP-Adressen von Office 365 ordnungsgemäß konfigurieren und den Weiterleitungsproxy umgehen, wenn dieser für Verbindungen mit dem Microsoft Teams-Dienst verfügbar ist. Zudem werden Sie über die Anforderungen für Netzwerk- und Sicherheitsrichtlinien informiert.
localization_priority: Priority
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: f946bc45fae230c0fd0ead9c06d0ced537bc7f92
ms.sourcegitcommit: 0c2d1766b96b99d9985f5a0f4f90b8d8bd9aa3ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "18998973"
---
<a name="office-365-urls-and-ip-address-ranges"></a>URLs und IP-Adressbereiche von Office 365
=====================================

Wechseln Sie zu [Office 365-URLs und IP-Adressbereiche](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) , eine Liste eine detaillierte und auf dem neuesten Stand mit den URLs, IP-Adressen, Ports und Protokolle, die für Teams ordnungsgemäß konfiguriert werden müssen. Office 365-Dienst wird von Microsoft ständig verbessert und hinzufügen neuen Funktionen, was bedeutet, dass die erforderlichen Ports, URLs und IP-Adressen mit der Zeit ändern können. Es wird empfohlen, Sie [über RSS abonnieren](https://go.microsoft.com/fwlink/p/?linkid=236301) von Benachrichtigungen empfangen, wenn diese Informationen aktualisiert oder geändert wird.

Die Teams Anruf- und Besprechungen Erfahrung basiert auf der nächsten Generation cloudbasierten-Infrastruktur, die auch von Skype und Skype für Unternehmen verwendet wird. Zu diesen Technologieinvestitionen gehören Azure-basierte Clouddienste für Medienverarbeitung und Signalisierung, der Videocodec H.264, die Audiocodecs SILK und Opus, Netzwerkresilienz, Telemetrie und Qualitätsdiagnose. Als solche vorhanden URLs und IP-Adressen, die erforderlich sind, die möglicherweise Skype und Skype für Unternehmen zugeordnet werden.

Für alle Office 365-Arbeitslasten ist die empfohlene Verbindungsmethode Teams Services dem Weiterleitungsproxy möglichst umgehen. Wenn ein Proxyserver zwischen einem Client und der Office 365-Rechenzentren befindet sich, möglicherweise Media über TCP anstelle von UDP, erzwungen werden die Medienqualität auswirken würde. Laden Sie Proxy PAC Beispieldateien, mit denen Umgehung der Datenverkehr von [Verwalten von Office 365-Endpunkten](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)konfiguriert werden können.

Wenn Ihre Netzwerke und Sicherheitsrichtlinien Office 365-Datenverkehr über einen Proxyserver benötigen, stellen Sie sicher, dass die oben genannten Anforderungen bereits vor der Bereitstellung von Teams in die Produktion erfüllt sind ( [Proxyserver für Skype für Business Online](https://support.office.com/article/Proxy-Servers-for-Skype-for-Business-Online-7acaf2c2-35fa-490f-84cd-822e446e0fc7?ui=en-US&rs=en-US&ad=US) überprüfen Anleitung).
