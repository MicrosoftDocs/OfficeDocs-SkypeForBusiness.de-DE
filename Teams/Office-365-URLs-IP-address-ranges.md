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
description: Hier erfahren Sie, wie Sie URLs und IP-Adressen von Office 365 ordnungsgemäß konfigurieren und den Weiterleitungsproxy umgehen, wenn dieser für Verbindungen mit dem Microsoft Teams-Dienst verfügbar ist. Zudem werden Sie über die Anforderungen für Netzwerk- und Sicherheitsrichtlinien informiert.
localization_priority: Normal
search.appverid: MET150
f1keywords: ms.teamsadmincenter.meetingsettings.network.ports
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5fc8d5bc41f7cf7a28140b30dd4a488c05b9b876
ms.sourcegitcommit: 4a4ed872eff22663720296ae29c0e644286857f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2019
ms.locfileid: "37563871"
---
<a name="office-365-urls-and-ip-address-ranges"></a>URLs und IP-Adressbereiche von Office 365
=====================================

Unter [URLs und IP-Adressbereiche von Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) finden Sie eine detaillierte und aktuelle Liste der URLs, IP-Adressen, Ports und Protokolle, die für Microsoft Teams richtig konfiguriert sein müssen. Microsoft verbessert den Office 365-Dienst ständig und fügt neue Funktionen hinzu. Daher können sich die erforderlichen Ports, URLs und IP-Adressen im Lauf der Zeit ändern. Wir empfehlen, den Artikel [über RSS zu abonnieren](https://go.microsoft.com/fwlink/p/?linkid=236301), damit Sie erfahren, wenn diese Informationen aktualisiert oder geändert werden.

Die Anruf- und Besprechungsfunktionen von Microsoft Teams beruhen auf der cloudbasierten Infrastruktur der nächsten Generation, die auch von Skype und Skype for Business genutzt wird. Zu diesen Technologieinvestitionen gehören Azure-basierte Cloud-Dienste für die Medienverarbeitung und Signalgebung, H. 264-Videocodec, Seiden-und Opus-Audiocodec, Netzwerkstabilität, Telemetrie und Qualitäts Diagnostik. Daher sind URLs und IPs erforderlich, die sowohl Skype als auch Skype for Business zugeordnet sein können.

Für alle Office 365-Arbeitsauslastungen wird empfohlen, beim Herstellen von Verbindungen mit Microsoft Teams-Diensten den Weiterleitungsproxy nach Möglichkeit zu umgehen. Wenn sich zwischen einem Client und den Office 365-Rechenzentren ein Proxyserver befindet, müssen die Medien möglicherweise über TCP anstatt über UDP übertragen werden. Dies wirkt sich auf die Medienqualität aus. Laden Sie unter [Verwalten von Office 365-Endpunkten](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a) Beispiele für PAC-Dateien für Proxys herunter, mit denen Sie Umgehungen für den Datenverkehr konfigurieren können.

Wenn Ihre Netzwerk-und Sicherheitsrichtlinien erfordern, dass Office 365-Datenverkehr über einen Proxy Server übermittelt wird, stellen Sie sicher, dass die oben genannten Anforderungen bereits erfüllt sind, bevor Sie Teams in der Produktion bereitstellen (überprüfen Sie die [Proxy Server für Teams oder Skype for Business Online](proxy-servers-for-skype-for-business-online.md) zur Anleitung).
