---
title: UrLs und IP-Adressbereiche von Microsoft 365 und Office 365
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 08/21/2018
ms.topic: article
audience: admin
ms.service: msteams
description: Erfahren Sie, wie Sie URLs und IP-Adressbereiche von Microsoft 365 oder Office 365 ordnungsgemäß konfigurieren und den Weiterleitungsproxy umgehen, wenn dies für Verbindungen mit dem Microsoft Teams-Dienst möglich ist.
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
ms.openlocfilehash: 9a29984b0b389bacb50a9aa6512a9ccc8bfe07de
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094517"
---
<a name="microsoft-365-and-office-365-urls-and-ip-address-ranges"></a>UrLs und IP-Adressbereiche von Microsoft 365 und Office 365
=======================================================

Wechseln Sie zu UrLs und IP-Adressbereiche von [Microsoft 365 und Office 365,](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) um eine detaillierte und aktuelle Liste der URLs, IP-Adressen, Ports und Protokolle zu erhalten, die für Teams ordnungsgemäß konfiguriert sein müssen. Microsoft verbessert die Microsoft 365- und Office 365-Dienste ständig und fügt neue Funktionen hinzu. Daher können sich die erforderlichen Ports, URLs und IP-Adressen im Lauf der Zeit ändern. Es wird empfohlen, über [RSS zu](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) abonnieren, um Benachrichtigungen zu erhalten, wenn diese Informationen aktualisiert oder geändert werden.

Die Anruf- und Besprechungserfahrung von Teams basiert auf der cloudbasierten Infrastruktur der nächsten Generation, die auch von Skype und Skype for Business verwendet wird. Diese Technologieinvestitionen umfassen Azure-basierte Clouddienste für die Medienverarbeitung und -signalisierung, H.264-Videocodec, SILK- und Opus-Audiocodec, Netzwerkresilienz, Telemetrie und Qualitätsdiagnose. Daher sind URLs und IPs erforderlich, die sowohl mit Skype als auch mit Skype for Business verknüpft sein können.

Für alle Microsoft 365- und Office 365-Workloads wird die empfohlene Verbindungsmethode zu Teams-Diensten nach Möglichkeit umgangen. Wenn sich ein Proxyserver zwischen einem Client und den Office 365-Rechenzentren befindet, werden Medien möglicherweise über TCP statt über UDP erzwungen, was sich auf die Medienqualität auswirken würde. Laden Sie Beispielproxy-PAC-Dateien herunter, die verwendet werden können, um die Umgehung des Datenverkehrs über die Verwaltung von [Microsoft 365- und Office 365-Endpunkten zu konfigurieren.](/office365/enterprise/managing-office-365-endpoints)

Wenn Für Ihre Netzwerk- und Sicherheitsrichtlinien microsoft 365- oder Office 365-Datenverkehr über einen Proxyserver fließen muss, stellen Sie sicher, dass die oben genannten Anforderungen bereits erfüllt sind, bevor Sie Teams in der Produktion bereitstellen. Weitere Informationen finden Sie unter [Proxyserver für Teams oder Skype for Business Online.](proxy-servers-for-skype-for-business-online.md)