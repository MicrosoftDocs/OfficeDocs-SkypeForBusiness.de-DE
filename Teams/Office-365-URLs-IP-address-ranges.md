---
title: URLs und IP-Adressbereiche von Office 365
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/21/2018
ms.topic: article
audience: admin
ms.service: msteams
description: Erfahren Sie, wie Sie Office 365-URLs und IP-Adressbereiche ordnungsgemäß konfigurieren und den Forward-Proxy nach Möglichkeit für Verbindungen mit Microsoft Teams-Dienst umgehen können.
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
ms.openlocfilehash: 8056758fc707c53b780843f2fc25123b92f6e252
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/03/2020
ms.locfileid: "43136485"
---
<a name="office-365-urls-and-ip-address-ranges"></a>URLs und IP-Adressbereiche von Office 365
=====================================

Unter [URLs und IP-Adressbereiche von Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) finden Sie eine detaillierte und aktuelle Liste der URLs, IP-Adressen, Ports und Protokolle, die für Microsoft Teams richtig konfiguriert sein müssen. Microsoft verbessert den Office 365-Dienst ständig und fügt neue Funktionen hinzu. Daher können sich die erforderlichen Ports, URLs und IP-Adressen im Lauf der Zeit ändern. Wir empfehlen, den Artikel [über RSS zu abonnieren](https://go.microsoft.com/fwlink/p/?linkid=236301), damit Sie erfahren, wenn diese Informationen aktualisiert oder geändert werden.

Die Anruf- und Besprechungsfunktionen von Microsoft Teams beruhen auf der cloudbasierten Infrastruktur der nächsten Generation, die auch von Skype und Skype for Business genutzt wird. Zu diesen Technologieinvestitionen gehören Azure-basierte Cloud-Dienste für die Medienverarbeitung und Signalgebung, H. 264-Videocodec, Seiden-und Opus-Audiocodec, Netzwerkstabilität, Telemetrie und Qualitäts Diagnostik. Daher sind URLs und IPs erforderlich, die sowohl Skype als auch Skype for Business zugeordnet sein können.

Für alle Office 365-Arbeitsauslastungen wird empfohlen, beim Herstellen von Verbindungen mit Microsoft Teams-Diensten den Weiterleitungsproxy nach Möglichkeit zu umgehen. Wenn sich zwischen einem Client und den Office 365-Rechenzentren ein Proxyserver befindet, müssen die Medien möglicherweise über TCP anstatt über UDP übertragen werden. Dies wirkt sich auf die Medienqualität aus. Laden Sie unter [Verwalten von Office 365-Endpunkten](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints) Beispiele für PAC-Dateien für Proxys herunter, mit denen Sie Umgehungen für den Datenverkehr konfigurieren können.

Wenn Ihre Netzwerk-und Sicherheitsrichtlinien erfordern, dass Office 365-Datenverkehr über einen Proxy Server übermittelt wird, stellen Sie sicher, dass die oben genannten Anforderungen bereits erfüllt sind, bevor Sie Teams in der Produktion bereitstellen. Weitere Informationen finden Sie unter [Proxy Server für Teams oder Skype for Business Online](proxy-servers-for-skype-for-business-online.md).
