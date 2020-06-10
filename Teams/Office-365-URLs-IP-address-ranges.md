---
title: Microsoft 365-und Office 365-URLs und IP-Adressbereiche
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/21/2018
ms.topic: article
audience: admin
ms.service: msteams
description: Erfahren Sie, wie Sie Microsoft 365-oder Office 365-URLs und IP-Adressbereiche ordnungsgemäß konfigurieren und den Forward-Proxy nach Möglichkeit für Verbindungen mit Microsoft Teams-Dienst umgehen können.
localization_priority: Normal
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
ms.openlocfilehash: 30736a347f447d265059de1a26ded5ef690e53dc
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "44665689"
---
<a name="microsoft-365-and-office-365-urls-and-ip-address-ranges"></a>Microsoft 365-und Office 365-URLs und IP-Adressbereiche
=======================================================

Wechseln Sie zu [Microsoft 365-und Office 365-URLs und IP-Adressbereiche](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) , um eine detaillierte und aktuelle Liste der URLs, IP-Adressen, Ports und Protokolle zu finden, die für Teams ordnungsgemäß konfiguriert werden müssen. Microsoft verbessert ständig die Microsoft 365-und Office 365-Dienste und fügt neue Funktionen hinzu, was bedeutet, dass sich die erforderlichen Ports, URLs und IP-Adressen im Laufe der Zeit ändern können. Wir empfehlen, den Artikel [über RSS zu abonnieren](https://go.microsoft.com/fwlink/p/?linkid=236301), damit Sie erfahren, wenn diese Informationen aktualisiert oder geändert werden.

Die Anruf- und Besprechungsfunktionen von Microsoft Teams beruhen auf der cloudbasierten Infrastruktur der nächsten Generation, die auch von Skype und Skype for Business genutzt wird. Zu diesen Technologieinvestitionen gehören Azure-basierte Cloud-Dienste für die Medienverarbeitung und Signalgebung, H. 264-Videocodec, Seiden-und Opus-Audiocodec, Netzwerkstabilität, Telemetrie und Qualitäts Diagnostik. Daher sind URLs und IPs erforderlich, die sowohl Skype als auch Skype for Business zugeordnet sein können.

Für alle Microsoft 365-und Office 365-Arbeitsauslastungen wird die empfohlene Verbindungsmethode für Teams-Dienste nach Möglichkeit den Forward-Proxy umgehen. Wenn sich zwischen einem Client und den Office 365-Rechenzentren ein Proxyserver befindet, müssen die Medien möglicherweise über TCP anstatt über UDP übertragen werden. Dies wirkt sich auf die Medienqualität aus. Laden Sie Beispiel-Proxy-PAC-Dateien herunter, die zum Konfigurieren der Datenverkehrs Umgehung für die [Verwaltung von Microsoft 365 und Office 365-Endpunkten](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints)verwendet werden können

Wenn für Ihre Netzwerk-und Sicherheitsrichtlinien Microsoft 365 oder Office 365-Datenverkehr über einen Proxy Server übermittelt werden muss, stellen Sie sicher, dass die oben genannten Anforderungen bereits erfüllt sind, bevor Sie Teams in der Produktion bereitstellen. Weitere Informationen finden Sie unter [Proxy Server für Teams oder Skype for Business Online](proxy-servers-for-skype-for-business-online.md).
