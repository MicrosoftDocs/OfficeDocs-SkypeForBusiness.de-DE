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
<a name="office-365-urls-and-ip-address-ranges"></a><span data-ttu-id="582fe-103">URLs und IP-Adressbereiche von Office 365</span><span class="sxs-lookup"><span data-stu-id="582fe-103">Office 365 URLs and IP address ranges</span></span>
=====================================

<span data-ttu-id="582fe-104">Wechseln Sie zu [Office 365-URLs und IP-Adressbereiche](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges) , eine Liste eine detaillierte und auf dem neuesten Stand mit den URLs, IP-Adressen, Ports und Protokolle, die für Teams ordnungsgemäß konfiguriert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="582fe-104">Go to [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges) for a detailed and up-to-date list of the URLs, IP addresses, ports, and protocols that must be correctly configured for Teams.</span></span> <span data-ttu-id="582fe-105">Office 365-Dienst wird von Microsoft ständig verbessert und hinzufügen neuen Funktionen, was bedeutet, dass die erforderlichen Ports, URLs und IP-Adressen mit der Zeit ändern können.</span><span class="sxs-lookup"><span data-stu-id="582fe-105">Microsoft is continuously improving the Office 365 service and adding new functionality, which means the required ports, URLs, and IP addresses may change over time.</span></span> <span data-ttu-id="582fe-106">Es wird empfohlen, Sie [über RSS abonnieren](https://go.microsoft.com/fwlink/p/?linkid=236301) von Benachrichtigungen empfangen, wenn diese Informationen aktualisiert oder geändert wird.</span><span class="sxs-lookup"><span data-stu-id="582fe-106">We recommend that you [subscribe via RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) to receive notifications when this information is updated or changed.</span></span>

<span data-ttu-id="582fe-107">Die Teams Anruf- und Besprechungen Erfahrung basiert auf der nächsten Generation cloudbasierten-Infrastruktur, die auch von Skype und Skype für Unternehmen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="582fe-107">The Teams calling and meetings experience is built on the next generation cloud-based infrastructure that is also used by Skype and Skype for Business.</span></span> <span data-ttu-id="582fe-108">Zu diesen Technologieinvestitionen gehören Azure-basierte Clouddienste für Medienverarbeitung und Signalisierung, der Videocodec H.264, die Audiocodecs SILK und Opus, Netzwerkresilienz, Telemetrie und Qualitätsdiagnose.</span><span class="sxs-lookup"><span data-stu-id="582fe-108">These technology investments include Azure-based cloud services for media processing and signaling, H.264 video codec, SILK and Opus audio codec, network resiliency, telemetry, and quality diagnostics.</span></span> <span data-ttu-id="582fe-109">Als solche vorhanden URLs und IP-Adressen, die erforderlich sind, die möglicherweise Skype und Skype für Unternehmen zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="582fe-109">As such, there are URLs and IPs that are required that may be associated with both Skype and Skype for Business.</span></span>

<span data-ttu-id="582fe-110">Für alle Office 365-Arbeitslasten ist die empfohlene Verbindungsmethode Teams Services dem Weiterleitungsproxy möglichst umgehen.</span><span class="sxs-lookup"><span data-stu-id="582fe-110">For all Office 365 workloads, the recommended connection method to Teams services is bypassing the forward proxy where possible.</span></span> <span data-ttu-id="582fe-111">Wenn ein Proxyserver zwischen einem Client und der Office 365-Rechenzentren befindet sich, möglicherweise Media über TCP anstelle von UDP, erzwungen werden die Medienqualität auswirken würde.</span><span class="sxs-lookup"><span data-stu-id="582fe-111">When a proxy server sits between a client and the Office 365 data centers, media might be forced over TCP instead of UDP, which would impact media quality.</span></span> <span data-ttu-id="582fe-112">Laden Sie Proxy PAC Beispieldateien, mit denen Umgehung der Datenverkehr von [Verwalten von Office 365-Endpunkten](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)konfiguriert werden können.</span><span class="sxs-lookup"><span data-stu-id="582fe-112">Download sample proxy PAC files that can be used to configure traffic bypass from [Managing Office 365 endpoints](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a).</span></span>

<span data-ttu-id="582fe-113">Wenn Ihre Netzwerke und Sicherheitsrichtlinien Office 365-Datenverkehr über einen Proxyserver benötigen, stellen Sie sicher, dass die oben genannten Anforderungen bereits vor der Bereitstellung von Teams in die Produktion erfüllt sind ( [Proxyserver für Skype für Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/proxy-servers-for-skype-for-business-online) überprüfen Anleitung).</span><span class="sxs-lookup"><span data-stu-id="582fe-113">If your networking and security policies require Office 365 traffic to flow through a proxy server, make sure that the above requirements are already met before deploying Teams into production (review [Proxy Servers for Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/proxy-servers-for-skype-for-business-online) for guidance).</span></span>
