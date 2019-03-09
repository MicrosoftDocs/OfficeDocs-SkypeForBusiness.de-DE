---
title: URLs und IP-Adressbereiche von Office 365
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
description: Hier erfahren Sie, wie Sie URLs und IP-Adressen von Office 365 ordnungsgemäß konfigurieren und den Weiterleitungsproxy umgehen, wenn dieser für Verbindungen mit dem Microsoft Teams-Dienst verfügbar ist. Zudem werden Sie über die Anforderungen für Netzwerk- und Sicherheitsrichtlinien informiert.
localization_priority: Normal
search.appverid: MET150
f1keywords: ms.teamsadmincenter.meetingsettings.network.ports
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 06079ccb801cb73c8fc4851beab8694f772bb59b
ms.sourcegitcommit: f3b41e7abafc84571bd9e8267d41decc0fe78e4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/08/2019
ms.locfileid: "30493513"
---
<a name="office-365-urls-and-ip-address-ranges"></a><span data-ttu-id="59a76-103">URLs und IP-Adressbereiche von Office 365</span><span class="sxs-lookup"><span data-stu-id="59a76-103">Office 365 URLs and IP address ranges</span></span>
=====================================

<span data-ttu-id="59a76-104">Wechseln Sie zu [Office 365-URLs und IP-Adressbereiche](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) , eine Liste eine detaillierte und auf dem neuesten Stand mit den URLs, IP-Adressen, Ports und Protokolle, die für Teams ordnungsgemäß konfiguriert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="59a76-104">Go to [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) for a detailed and up-to-date list of the URLs, IP addresses, ports, and protocols that must be correctly configured for Teams.</span></span> <span data-ttu-id="59a76-105">Microsoft verbessert den Office 365-Dienst ständig und fügt neue Funktionen hinzu. Daher können sich die erforderlichen Ports, URLs und IP-Adressen im Lauf der Zeit ändern.</span><span class="sxs-lookup"><span data-stu-id="59a76-105">Microsoft is continuously improving the Office 365 service and adding new functionality, which means the required ports, URLs, and IP addresses may change over time.</span></span> <span data-ttu-id="59a76-106">Es wird empfohlen, Sie [über RSS abonnieren](https://go.microsoft.com/fwlink/p/?linkid=236301) von Benachrichtigungen empfangen, wenn diese Informationen aktualisiert oder geändert wird.</span><span class="sxs-lookup"><span data-stu-id="59a76-106">We recommend that you [subscribe via RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) to receive notifications when this information is updated or changed.</span></span>

<span data-ttu-id="59a76-107">Die Teams Anruf- und Besprechungen Erfahrung basiert auf der nächsten Generation cloudbasierten-Infrastruktur, die auch von Skype und Skype für Unternehmen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="59a76-107">The Teams calling and meetings experience is built on the next generation cloud-based infrastructure that is also used by Skype and Skype for Business.</span></span> <span data-ttu-id="59a76-108">Zu diesen Technologieinvestitionen gehören Azure-basierte Clouddienste für Medienverarbeitung und Signalisierung, der Videocodec H.264, die Audiocodecs SILK und Opus, Netzwerkresilienz, Telemetrie und Qualitätsdiagnose.</span><span class="sxs-lookup"><span data-stu-id="59a76-108">These technology investments include Azure-based cloud services for media processing and signaling, H.264 video codec, SILK and Opus audio codec, network resiliency, telemetry, and quality diagnostics.</span></span> <span data-ttu-id="59a76-109">Als solche vorhanden URLs und IP-Adressen, die erforderlich sind, die möglicherweise Skype und Skype für Unternehmen zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="59a76-109">As such, there are URLs and IPs that are required that may be associated with both Skype and Skype for Business.</span></span>

<span data-ttu-id="59a76-110">Für alle Office 365-Arbeitslasten ist die empfohlene Verbindungsmethode Teams Services dem Weiterleitungsproxy möglichst umgehen.</span><span class="sxs-lookup"><span data-stu-id="59a76-110">For all Office 365 workloads, the recommended connection method to Teams services is bypassing the forward proxy where possible.</span></span> <span data-ttu-id="59a76-111">Wenn ein Proxyserver zwischen einem Client und der Office 365-Rechenzentren befindet sich, möglicherweise Media über TCP anstelle von UDP, erzwungen werden die Medienqualität auswirken würde.</span><span class="sxs-lookup"><span data-stu-id="59a76-111">When a proxy server sits between a client and the Office 365 data centers, media might be forced over TCP instead of UDP, which would impact media quality.</span></span> <span data-ttu-id="59a76-112">Laden Sie Proxy PAC Beispieldateien, mit denen Umgehung der Datenverkehr von [Verwalten von Office 365-Endpunkten](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)konfiguriert werden können.</span><span class="sxs-lookup"><span data-stu-id="59a76-112">Download sample proxy PAC files that can be used to configure traffic bypass from [Managing Office 365 endpoints](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a).</span></span>

<span data-ttu-id="59a76-113">Wenn Ihre Netzwerke und Sicherheitsrichtlinien Office 365-Datenverkehr über einen Proxyserver erforderlich, stellen Sie sicher, dass die oben genannten Anforderungen bereits vor der Bereitstellung von Teams in die Produktion (überprüfen [Proxyserver für Teams oder Skype für Business Online](proxy-servers-for-skype-for-business-online.md) erfüllt sind Anleitung).</span><span class="sxs-lookup"><span data-stu-id="59a76-113">If your networking and security policies require Office 365 traffic to flow through a proxy server, make sure that the above requirements are already met before deploying Teams into production (review [Proxy Servers for Teams or Skype for Business Online](proxy-servers-for-skype-for-business-online.md) for guidance).</span></span>
