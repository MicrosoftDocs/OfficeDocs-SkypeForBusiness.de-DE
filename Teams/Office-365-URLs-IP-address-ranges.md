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
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.meetingsettings.network.ports
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1258138ce6f57dfb0284e030f7a813acf8b94a62
ms.sourcegitcommit: 2511cd95a186d95f4571afa4212f8e0fc207817d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/08/2020
ms.locfileid: "41862795"
---
<a name="office-365-urls-and-ip-address-ranges"></a><span data-ttu-id="869be-103">URLs und IP-Adressbereiche von Office 365</span><span class="sxs-lookup"><span data-stu-id="869be-103">Office 365 URLs and IP address ranges</span></span>
=====================================

<span data-ttu-id="869be-104">Unter [URLs und IP-Adressbereiche von Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) finden Sie eine detaillierte und aktuelle Liste der URLs, IP-Adressen, Ports und Protokolle, die für Microsoft Teams richtig konfiguriert sein müssen.</span><span class="sxs-lookup"><span data-stu-id="869be-104">Go to [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) for a detailed and up-to-date list of the URLs, IP addresses, ports, and protocols that must be correctly configured for Teams.</span></span> <span data-ttu-id="869be-105">Microsoft verbessert den Office 365-Dienst ständig und fügt neue Funktionen hinzu. Daher können sich die erforderlichen Ports, URLs und IP-Adressen im Lauf der Zeit ändern.</span><span class="sxs-lookup"><span data-stu-id="869be-105">Microsoft is continuously improving the Office 365 service and adding new functionality, which means the required ports, URLs, and IP addresses may change over time.</span></span> <span data-ttu-id="869be-106">Wir empfehlen, den Artikel [über RSS zu abonnieren](https://go.microsoft.com/fwlink/p/?linkid=236301), damit Sie erfahren, wenn diese Informationen aktualisiert oder geändert werden.</span><span class="sxs-lookup"><span data-stu-id="869be-106">We recommend that you [subscribe via RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) to receive notifications when this information is updated or changed.</span></span>

<span data-ttu-id="869be-107">Die Anruf- und Besprechungsfunktionen von Microsoft Teams beruhen auf der cloudbasierten Infrastruktur der nächsten Generation, die auch von Skype und Skype for Business genutzt wird.</span><span class="sxs-lookup"><span data-stu-id="869be-107">The Teams calling and meetings experience is built on the next generation cloud-based infrastructure that is also used by Skype and Skype for Business.</span></span> <span data-ttu-id="869be-108">Zu diesen Technologieinvestitionen gehören Azure-basierte Cloud-Dienste für die Medienverarbeitung und Signalgebung, H. 264-Videocodec, Seiden-und Opus-Audiocodec, Netzwerkstabilität, Telemetrie und Qualitäts Diagnostik.</span><span class="sxs-lookup"><span data-stu-id="869be-108">These technology investments include Azure-based cloud services for media processing and signaling, H.264 video codec, SILK and Opus audio codec, network resiliency, telemetry, and quality diagnostics.</span></span> <span data-ttu-id="869be-109">Daher sind URLs und IPs erforderlich, die sowohl Skype als auch Skype for Business zugeordnet sein können.</span><span class="sxs-lookup"><span data-stu-id="869be-109">As such, there are URLs and IPs that are required that may be associated with both Skype and Skype for Business.</span></span>

<span data-ttu-id="869be-110">Für alle Office 365-Arbeitsauslastungen wird empfohlen, beim Herstellen von Verbindungen mit Microsoft Teams-Diensten den Weiterleitungsproxy nach Möglichkeit zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="869be-110">For all Office 365 workloads, the recommended connection method to Teams services is bypassing the forward proxy where possible.</span></span> <span data-ttu-id="869be-111">Wenn sich zwischen einem Client und den Office 365-Rechenzentren ein Proxyserver befindet, müssen die Medien möglicherweise über TCP anstatt über UDP übertragen werden. Dies wirkt sich auf die Medienqualität aus.</span><span class="sxs-lookup"><span data-stu-id="869be-111">When a proxy server sits between a client and the Office 365 data centers, media might be forced over TCP instead of UDP, which would impact media quality.</span></span> <span data-ttu-id="869be-112">Laden Sie unter [Verwalten von Office 365-Endpunkten](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints) Beispiele für PAC-Dateien für Proxys herunter, mit denen Sie Umgehungen für den Datenverkehr konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="869be-112">Download sample proxy PAC files that can be used to configure traffic bypass from [Managing Office 365 endpoints](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints).</span></span>

<span data-ttu-id="869be-113">Wenn Ihre Netzwerk-und Sicherheitsrichtlinien erfordern, dass Office 365-Datenverkehr über einen Proxy Server übermittelt wird, stellen Sie sicher, dass die oben genannten Anforderungen bereits erfüllt sind, bevor Sie Teams in der Produktion bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="869be-113">If your networking and security policies require Office 365 traffic to flow through a proxy server, make sure that the above requirements are already met before deploying Teams into production.</span></span> <span data-ttu-id="869be-114">Weitere Informationen finden Sie unter [Proxy Server für Teams oder Skype for Business Online](proxy-servers-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="869be-114">For more information, read [Proxy Servers for Teams or Skype for Business Online](proxy-servers-for-skype-for-business-online.md).</span></span>
