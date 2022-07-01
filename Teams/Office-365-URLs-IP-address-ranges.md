---
title: UrLs und IP-Adressbereiche von Microsoft 365 und Office 365
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 08/21/2018
ms.topic: article
audience: admin
ms.service: msteams
description: Erfahren Sie, wie Sie Microsoft 365 oder Office 365 URLs und IP-Adressbereiche ordnungsgemäß konfigurieren und den Weiterleitungsproxy bei Verbindungen mit dem Microsoft Teams-Dienst nach Möglichkeit umgehen.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingsettings.network.ports
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e2f638b9fb29c80806082e02f2d0b09ceec619d0
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2022
ms.locfileid: "66563733"
---
# <a name="microsoft-365-and-office-365-urls-and-ip-address-ranges"></a>UrLs und IP-Adressbereiche von Microsoft 365 und Office 365

Wechseln Sie zu [Microsoft 365 und Office 365 URLs und IP-Adressbereiche](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams), um eine detaillierte und aktuelle Liste der URLs, IP-Adressen, Ports und Protokolle zu erhalten, die ordnungsgemäß für Teams konfiguriert werden müssen. Microsoft verbessert die Microsoft 365- und Office 365-Dienste ständig und fügt neue Funktionen hinzu. Daher können sich die erforderlichen Ports, URLs und IP-Adressen im Lauf der Zeit ändern. Es wird empfohlen, dass Sie [sich über RSS abonnieren](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) , um Benachrichtigungen zu erhalten, wenn diese Informationen aktualisiert oder geändert werden.

Die Teams-Anruf- und Besprechungserfahrung basiert auf der cloudbasierten Infrastruktur der nächsten Generation, die auch von Skype und Skype for Business verwendet wird. Zu diesen Technologieinvestitionen gehören Azure-basierte Clouddienste für Medienverarbeitung und -signalisierung, H.264-Videocodec, SILK- und Opus-Audiocodec, Netzwerkresilienz, Telemetrie und Qualitätsdiagnose. Daher sind URLs und IPs erforderlich, die sowohl Skype als auch Skype for Business zugeordnet sein können.

Bei allen Microsoft 365- und Office 365-Workloads wird der Weiterleitungsproxy nach Möglichkeit von der empfohlenen Verbindungsmethode zu Teams-Diensten umgangen. Wenn sich ein Proxyserver zwischen einem Client und den Office 365 Rechenzentren befindet, werden Medien möglicherweise über TCP anstelle von UDP erzwungen, was sich auf die Medienqualität auswirken würde. Laden Sie Beispielproxy-PAC-Dateien herunter, die zum Konfigurieren der Datenverkehrsumgehung von [Microsoft 365 und Office 365 Endpunkten](/office365/enterprise/managing-office-365-endpoints) verwendet werden können.

Wenn Ihre Netzwerk- und Sicherheitsrichtlinien erfordern, dass Microsoft 365 oder Office 365 Datenverkehr über einen Proxyserver fließt, stellen Sie sicher, dass die oben genannten Anforderungen bereits erfüllt sind, bevor Sie Teams in der Produktion bereitstellen. Weitere Informationen finden Sie unter [Proxyserver für Teams oder Skype for Business Online](proxy-servers-for-skype-for-business-online.md).