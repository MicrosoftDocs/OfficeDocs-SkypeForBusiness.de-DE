---
title: Behandeln von Verbindungsproblemen mit dem Microsoft Teams-Client
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/21/2018
ms.topic: troubleshooting
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
description: Behandeln Sie Konnektivitätsprobleme mit dem Microsoft Teams-Client, die in erster Linie durch die Firewall- oder Proxyverbindung verursacht werden, und informieren Sie sich, wie Sie diese beheben können.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 116ce1afef08a6f1639ed011b799f9ca43ea57f5
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085231"
---
<a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a><span data-ttu-id="92c00-103">Behandeln von Verbindungsproblemen mit dem Microsoft Teams-Client</span><span class="sxs-lookup"><span data-stu-id="92c00-103">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>
==============================================================

<span data-ttu-id="92c00-104">Most issues discovered with the Microsoft Teams client can be traced back to firewall or proxy connectivity.</span><span class="sxs-lookup"><span data-stu-id="92c00-104">Most issues discovered with the Microsoft Teams client can be traced back to firewall or proxy connectivity.</span></span> <span data-ttu-id="92c00-105">Verifying that the necessary URLs, IP addresses and ports are opened in your firewall or proxy will minimize unnecessary troubleshooting.</span><span class="sxs-lookup"><span data-stu-id="92c00-105">Verifying that the necessary URLs, IP addresses and ports are opened in your firewall or proxy will minimize unnecessary troubleshooting.</span></span> <span data-ttu-id="92c00-106">For specific information on URLs and IPs required for Microsoft Teams, please see the [Microsoft 365 and Office 365 URLs and IP Address](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) support article.</span><span class="sxs-lookup"><span data-stu-id="92c00-106">For specific information on URLs and IPs required for Microsoft Teams, please see the [Microsoft 365 and Office 365 URLs and IP Address](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) support article.</span></span> <span data-ttu-id="92c00-107">The following scenarios require specific URLs and ports to be opened in the firewall.</span><span class="sxs-lookup"><span data-stu-id="92c00-107">The following scenarios require specific URLs and ports to be opened in the firewall.</span></span>

-   <span data-ttu-id="92c00-108">Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="92c00-108">Authentication</span></span>

-   <span data-ttu-id="92c00-109">Microsoft Teams-Clientkonnektivität</span><span class="sxs-lookup"><span data-stu-id="92c00-109">Microsoft Teams Client Connectivity</span></span>

-   <span data-ttu-id="92c00-110">Zusammenarbeit</span><span class="sxs-lookup"><span data-stu-id="92c00-110">Collaboration</span></span>

-   <span data-ttu-id="92c00-111">Medien</span><span class="sxs-lookup"><span data-stu-id="92c00-111">Media</span></span>

-   <span data-ttu-id="92c00-112">Gemeinsame Dienste</span><span class="sxs-lookup"><span data-stu-id="92c00-112">Shared Services</span></span>

-   <span data-ttu-id="92c00-113">Drittanbieterintegration</span><span class="sxs-lookup"><span data-stu-id="92c00-113">Third Party Integration</span></span>

-   <span data-ttu-id="92c00-114">Interoperabilität von Skype for Business</span><span class="sxs-lookup"><span data-stu-id="92c00-114">Skype for Business Interoperability</span></span>

-   <span data-ttu-id="92c00-115">Interoperabilität des Skype for Business-Clients</span><span class="sxs-lookup"><span data-stu-id="92c00-115">Skype for Business Client Interoperability</span></span>


## <a name="related-topics"></a><span data-ttu-id="92c00-116">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="92c00-116">Related topics</span></span>

[<span data-ttu-id="92c00-117">Teams-Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="92c00-117">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)