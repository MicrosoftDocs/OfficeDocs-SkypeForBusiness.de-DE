---
title: URLs und IP-Adressbereiche von Office 365
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
description: Hier erfahren Sie, wie Sie URLs und IP-Adressen von Office 365 ordnungsgemäß konfigurieren und den Weiterleitungsproxy umgehen, wenn dieser für Verbindungen mit dem Microsoft Teams-Dienst verfügbar ist. Zudem werden Sie über die Anforderungen für Netzwerk- und Sicherheitsrichtlinien informiert.
localization_priority: Priority
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: a21130d3e1c2e81203bb409fc2a53c77645bf0ba
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23851923"
---
<a name="office-365-urls-and-ip-address-ranges"></a>URLs und IP-Adressbereiche von Office 365
=====================================

Wechseln Sie zu [Office 365-URLs und IP-Adressbereiche](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges) , eine Liste eine detaillierte und auf dem neuesten Stand mit den URLs, IP-Adressen, Ports und Protokolle, die für Teams ordnungsgemäß konfiguriert werden müssen. Office 365-Dienst wird von Microsoft ständig verbessert und hinzufügen neuen Funktionen, was bedeutet, dass die erforderlichen Ports, URLs und IP-Adressen mit der Zeit ändern können. Es wird empfohlen, Sie [über RSS abonnieren](https://go.microsoft.com/fwlink/p/?linkid=236301) von Benachrichtigungen empfangen, wenn diese Informationen aktualisiert oder geändert wird.

Die Teams Anruf- und Besprechungen Erfahrung basiert auf der nächsten Generation cloudbasierten-Infrastruktur, die auch von Skype und Skype für Unternehmen verwendet wird. Zu diesen Technologieinvestitionen gehören Azure-basierte Clouddienste für Medienverarbeitung und Signalisierung, der Videocodec H.264, die Audiocodecs SILK und Opus, Netzwerkresilienz, Telemetrie und Qualitätsdiagnose. Als solche vorhanden URLs und IP-Adressen, die erforderlich sind, die möglicherweise Skype und Skype für Unternehmen zugeordnet werden.

Für alle Office 365-Arbeitslasten ist die empfohlene Verbindungsmethode Teams Services dem Weiterleitungsproxy möglichst umgehen. Wenn ein Proxyserver zwischen einem Client und der Office 365-Rechenzentren befindet sich, möglicherweise Media über TCP anstelle von UDP, erzwungen werden die Medienqualität auswirken würde. Laden Sie Proxy PAC Beispieldateien, mit denen Umgehung der Datenverkehr von [Verwalten von Office 365-Endpunkten](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)konfiguriert werden können.

Wenn Ihre Netzwerke und Sicherheitsrichtlinien Office 365-Datenverkehr über einen Proxyserver benötigen, stellen Sie sicher, dass die oben genannten Anforderungen bereits vor der Bereitstellung von Teams in die Produktion erfüllt sind ( [Proxyserver für Skype für Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/proxy-servers-for-skype-for-business-online) überprüfen Anleitung).
