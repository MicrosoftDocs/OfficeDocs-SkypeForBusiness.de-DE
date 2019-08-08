---
title: Behandeln von Konnektivitätsproblemen mit dem Microsoft Teams-Client
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/21/2018
ms.topic: troubleshooting
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
description: Behandeln Sie Konnektivitätsprobleme mit dem Microsoft Teams-Client, die in erster Linie durch die Firewall- oder Proxyverbindung verursacht werden, und informieren Sie sich, wie Sie diese beheben können.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 79718ebc58205cd63ab291f0985e4dd7e452be3e
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236551"
---
<a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a><span data-ttu-id="0e14c-103">Behandeln von Konnektivitätsproblemen mit dem Microsoft Teams-Client</span><span class="sxs-lookup"><span data-stu-id="0e14c-103">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>
==============================================================

<span data-ttu-id="0e14c-104">Die meisten Probleme, die mit dem Microsoft Teams-Client gefunden wurden, können auf Firewall-oder Proxy Konnektivität zurückverfolgt werden.</span><span class="sxs-lookup"><span data-stu-id="0e14c-104">Most issues discovered with the Microsoft Teams client can be traced back to firewall or proxy connectivity.</span></span> <span data-ttu-id="0e14c-105">Überprüfen, ob die erforderlichen URLs, IP-Adressen und Ports in Ihrer Firewall oder Ihrem Proxy geöffnet werden, minimiert unnötige Fehlerbehebung.</span><span class="sxs-lookup"><span data-stu-id="0e14c-105">Verifying that the necessary URLs, IP addresses and ports are opened in your firewall or proxy will minimize unnecessary troubleshooting.</span></span> <span data-ttu-id="0e14c-106">Spezifische Informationen zu URLs und IPS, die für Microsoft Teams erforderlich sind, finden Sie im Artikel [Office 365-URLs und Support für IP-Adressen](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) .</span><span class="sxs-lookup"><span data-stu-id="0e14c-106">For specific information on URLs and IPs required for Microsoft Teams, please see the [Office 365 URLs and IP Address](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) support article.</span></span> <span data-ttu-id="0e14c-107">In den folgenden Szenarien müssen bestimmte URLs und Ports in der Firewall geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="0e14c-107">The following scenarios require specific URLs and ports to be opened in the firewall.</span></span>

-   <span data-ttu-id="0e14c-108">Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="0e14c-108">Authentication</span></span>

-   <span data-ttu-id="0e14c-109">Microsoft Teams-Clientkonnektivität</span><span class="sxs-lookup"><span data-stu-id="0e14c-109">Microsoft Teams Client Connectivity</span></span>

-   <span data-ttu-id="0e14c-110">Zusammenarbeit</span><span class="sxs-lookup"><span data-stu-id="0e14c-110">Collaboration</span></span>

-   <span data-ttu-id="0e14c-111">Medien</span><span class="sxs-lookup"><span data-stu-id="0e14c-111">Media</span></span>

-   <span data-ttu-id="0e14c-112">Gemeinsame Dienste</span><span class="sxs-lookup"><span data-stu-id="0e14c-112">Shared Services</span></span>

-   <span data-ttu-id="0e14c-113">Drittanbieterintegration</span><span class="sxs-lookup"><span data-stu-id="0e14c-113">Third Party Integration</span></span>

-   <span data-ttu-id="0e14c-114">Interoperabilität von Skype for Business</span><span class="sxs-lookup"><span data-stu-id="0e14c-114">Skype for Business Interoperability</span></span>

-   <span data-ttu-id="0e14c-115">Interoperabilität des Skype for Business-Clients</span><span class="sxs-lookup"><span data-stu-id="0e14c-115">Skype for Business Client Interoperability</span></span>
