---
title: Microsoft 365-und Office 365-URLs und IP-Adressbereiche
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
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
ms.openlocfilehash: 94fd32cb4f68d636a6ff49ecf3b9c19689542142
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2020
ms.locfileid: "46582122"
---
<a name="microsoft-365-and-office-365-urls-and-ip-address-ranges"></a><span data-ttu-id="7947e-103">Microsoft 365-und Office 365-URLs und IP-Adressbereiche</span><span class="sxs-lookup"><span data-stu-id="7947e-103">Microsoft 365 and Office 365 URLs and IP address ranges</span></span>
=======================================================

<span data-ttu-id="7947e-104">Wechseln Sie zu [Microsoft 365-und Office 365-URLs und IP-Adressbereiche](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) , um eine detaillierte und aktuelle Liste der URLs, IP-Adressen, Ports und Protokolle zu finden, die für Teams ordnungsgemäß konfiguriert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="7947e-104">Go to [Microsoft 365 and Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) for a detailed and up-to-date list of the URLs, IP addresses, ports, and protocols that must be correctly configured for Teams.</span></span> <span data-ttu-id="7947e-105">Microsoft verbessert die Microsoft 365- und Office 365-Dienste ständig und fügt neue Funktionen hinzu. Daher können sich die erforderlichen Ports, URLs und IP-Adressen im Lauf der Zeit ändern.</span><span class="sxs-lookup"><span data-stu-id="7947e-105">Microsoft is continuously improving the Microsoft 365 and Office 365 services and adding new functionality, which means the required ports, URLs, and IP addresses may change over time.</span></span> <span data-ttu-id="7947e-106">Wir empfehlen, den Artikel [über RSS zu abonnieren](https://go.microsoft.com/fwlink/p/?linkid=236301), damit Sie erfahren, wenn diese Informationen aktualisiert oder geändert werden.</span><span class="sxs-lookup"><span data-stu-id="7947e-106">We recommend that you [subscribe via RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) to receive notifications when this information is updated or changed.</span></span>

<span data-ttu-id="7947e-107">Die Anruf- und Besprechungsfunktionen von Microsoft Teams beruhen auf der cloudbasierten Infrastruktur der nächsten Generation, die auch von Skype und Skype for Business genutzt wird.</span><span class="sxs-lookup"><span data-stu-id="7947e-107">The Teams calling and meetings experience is built on the next generation cloud-based infrastructure that is also used by Skype and Skype for Business.</span></span> <span data-ttu-id="7947e-108">Zu diesen Technologieinvestitionen gehören Azure-basierte Cloud-Dienste für die Medienverarbeitung und Signalgebung, H. 264-Videocodec, Seiden-und Opus-Audiocodec, Netzwerkstabilität, Telemetrie und Qualitäts Diagnostik.</span><span class="sxs-lookup"><span data-stu-id="7947e-108">These technology investments include Azure-based cloud services for media processing and signaling, H.264 video codec, SILK and Opus audio codec, network resiliency, telemetry, and quality diagnostics.</span></span> <span data-ttu-id="7947e-109">Daher sind URLs und IPs erforderlich, die sowohl Skype als auch Skype for Business zugeordnet sein können.</span><span class="sxs-lookup"><span data-stu-id="7947e-109">As such, there are URLs and IPs that are required that may be associated with both Skype and Skype for Business.</span></span>

<span data-ttu-id="7947e-110">Für alle Microsoft 365-und Office 365-Arbeitsauslastungen wird die empfohlene Verbindungsmethode für Teams-Dienste nach Möglichkeit den Forward-Proxy umgehen.</span><span class="sxs-lookup"><span data-stu-id="7947e-110">For all Microsoft 365 and Office 365 workloads, the recommended connection method to Teams services is bypassing the forward proxy where possible.</span></span> <span data-ttu-id="7947e-111">Wenn sich zwischen einem Client und den Office 365-Rechenzentren ein Proxyserver befindet, müssen die Medien möglicherweise über TCP anstatt über UDP übertragen werden. Dies wirkt sich auf die Medienqualität aus.</span><span class="sxs-lookup"><span data-stu-id="7947e-111">When a proxy server sits between a client and the Office 365 data centers, media might be forced over TCP instead of UDP, which would impact media quality.</span></span> <span data-ttu-id="7947e-112">Laden Sie Beispiel-Proxy-PAC-Dateien herunter, die zum Konfigurieren der Datenverkehrs Umgehung für die [Verwaltung von Microsoft 365 und Office 365-Endpunkten](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints)verwendet werden können</span><span class="sxs-lookup"><span data-stu-id="7947e-112">Download sample proxy PAC files that can be used to configure traffic bypass from [Managing Microsoft 365 and Office 365 endpoints](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints).</span></span>

<span data-ttu-id="7947e-113">Wenn für Ihre Netzwerk-und Sicherheitsrichtlinien Microsoft 365 oder Office 365-Datenverkehr über einen Proxy Server übermittelt werden muss, stellen Sie sicher, dass die oben genannten Anforderungen bereits erfüllt sind, bevor Sie Teams in der Produktion bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="7947e-113">If your networking and security policies require Microsoft 365 or Office 365 traffic to flow through a proxy server, make sure that the above requirements are already met before deploying Teams into production.</span></span> <span data-ttu-id="7947e-114">Weitere Informationen finden Sie unter [Proxy Server für Teams oder Skype for Business Online](proxy-servers-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="7947e-114">For more information, read [Proxy Servers for Teams or Skype for Business Online](proxy-servers-for-skype-for-business-online.md).</span></span>
