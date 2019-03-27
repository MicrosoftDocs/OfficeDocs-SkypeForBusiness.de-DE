---
title: Behandeln von Konnektivitätsproblemen mit dem Microsoft Teams-Client
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/21/2018
ms.topic: troubleshooting
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
description: Behandeln Sie Konnektivitätsprobleme mit dem Microsoft Teams-Client, die in erster Linie durch die Firewall- oder Proxyverbindung verursacht werden, und informieren Sie sich, wie Sie diese beheben können.
appliesto:
- Microsoft Teams
ms.openlocfilehash: d208671415e44ca5ec83313d0d8af666534f2b20
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30872702"
---
<a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a><span data-ttu-id="83cb9-103">Behandeln von Konnektivitätsproblemen mit dem Microsoft Teams-Client</span><span class="sxs-lookup"><span data-stu-id="83cb9-103">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>
==============================================================

<span data-ttu-id="83cb9-104">Die meisten Probleme mit der Client für Microsoft-Teams können Firewall oder der Proxyserver Connectivity zurückverfolgt werden.</span><span class="sxs-lookup"><span data-stu-id="83cb9-104">Most issues discovered with the Microsoft Teams client can be traced back to firewall or proxy connectivity.</span></span> <span data-ttu-id="83cb9-105">Überprüfen, dass die erforderlichen URLs, IP-Adressen und Ports in der Firewall geöffnet oder Proxy wird nicht benötigter Problembehandlung zu minimieren.</span><span class="sxs-lookup"><span data-stu-id="83cb9-105">Verifying that the necessary URLs, IP addresses and ports are opened in your firewall or proxy will minimize unnecessary troubleshooting.</span></span> <span data-ttu-id="83cb9-106">Spezifische Informationen zu URLs und IP-Adressen für Microsoft-Teams erforderlich sind finden Sie unter der [Office 365-URLs und IP-Adresse](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) Artikel zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="83cb9-106">For specific information on URLs and IPs required for Microsoft Teams, please see the [Office 365 URLs and IP Address](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) support article.</span></span> <span data-ttu-id="83cb9-107">Die folgenden Szenarien erfordern, dass bestimmte URLs und Ports in der Firewall geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="83cb9-107">The following scenarios require specific URLs and ports to be opened in the firewall.</span></span>

-   <span data-ttu-id="83cb9-108">Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="83cb9-108">Authentication</span></span>

-   <span data-ttu-id="83cb9-109">Microsoft Teams-Clientkonnektivität</span><span class="sxs-lookup"><span data-stu-id="83cb9-109">Microsoft Teams Client Connectivity</span></span>

-   <span data-ttu-id="83cb9-110">Zusammenarbeit</span><span class="sxs-lookup"><span data-stu-id="83cb9-110">Collaboration</span></span>

-   <span data-ttu-id="83cb9-111">Medien</span><span class="sxs-lookup"><span data-stu-id="83cb9-111">Media</span></span>

-   <span data-ttu-id="83cb9-112">Gemeinsame Dienste</span><span class="sxs-lookup"><span data-stu-id="83cb9-112">Shared Services</span></span>

-   <span data-ttu-id="83cb9-113">Drittanbieterintegration</span><span class="sxs-lookup"><span data-stu-id="83cb9-113">Third Party Integration</span></span>

-   <span data-ttu-id="83cb9-114">Interoperabilität von Skype for Business</span><span class="sxs-lookup"><span data-stu-id="83cb9-114">Skype for Business Interoperability</span></span>

-   <span data-ttu-id="83cb9-115">Interoperabilität des Skype for Business-Clients</span><span class="sxs-lookup"><span data-stu-id="83cb9-115">Skype for Business Client Interoperability</span></span>
