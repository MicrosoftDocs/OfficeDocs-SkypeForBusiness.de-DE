---
title: Überprüfen des partnerverbunds und Remotezugriff für externe Benutzer
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Nach dem Übergang der partnerverbundroute, der Skype für Business Server 2019 Edge-Server, sollten Sie Funktionstests aus, um sicherzustellen, dass der Partnerverbund erwartungsgemäß ausgeführt wird, durchführen. Tests für den Zugriff externer Benutzer sollte jede Art von externer Benutzer enthalten, die Ihre Organisation einige oder alle der folgenden einschließlich unterstützt.
ms.openlocfilehash: ce0e2dd6ee7d4fb605f844d7dfb26b3f9d13bf14
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027235"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="7bfbc-104">Überprüfen des partnerverbunds und Remotezugriff für externe Benutzer</span><span class="sxs-lookup"><span data-stu-id="7bfbc-104">Verify federation and remote access for external users</span></span>

<span data-ttu-id="7bfbc-105">Nach dem Übergang der partnerverbundroute, der Skype für Business Server 2019 Edge-Server, sollten Sie Funktionstests aus, um sicherzustellen, dass der Partnerverbund erwartungsgemäß ausgeführt wird, durchführen.</span><span class="sxs-lookup"><span data-stu-id="7bfbc-105">After transitioning the federation route to the Skype for Business Server 2019 Edge Server, you should perform some functional tests to verify that federation performs as expected.</span></span> <span data-ttu-id="7bfbc-106">Tests für den Zugriff externer Benutzer sollte jede Art von externer Benutzer enthalten, die Ihre Organisation einige oder alle der folgenden einschließlich unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7bfbc-106">Tests for external user access should include each type of external user that your organization supports, including any or all of the following.</span></span>
  
### <a name="test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="7bfbc-107">Testen der Konnektivität von externen Benutzern und den externen Zugriff</span><span class="sxs-lookup"><span data-stu-id="7bfbc-107">Test connectivity of external users and external access</span></span>

- <span data-ttu-id="7bfbc-108">Benutzer aus mindestens eine verbunddomäne, ein interner Benutzer auf Skype für Business Server 2019 und einem Benutzer von der Vorgängerversion installieren.</span><span class="sxs-lookup"><span data-stu-id="7bfbc-108">Users from at least one federated domain, an internal user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="7bfbc-109">Testen von Sofortnachrichten (IM), Anwesenheit, Audio/Video (A / V), und Desktopfreigabe.</span><span class="sxs-lookup"><span data-stu-id="7bfbc-109">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>
    
- <span data-ttu-id="7bfbc-110">Benutzer aller öffentlichen Sofortnachrichten-Dienstanbieter, die von Ihrer Organisation unterstützt (und für die Bereitstellung abgeschlossen) zum Kommunizieren mit einem Benutzer von Skype für Business Server 2019 und einem Benutzer von der Vorversion installieren.</span><span class="sxs-lookup"><span data-stu-id="7bfbc-110">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Skype for Business Server 2019 and a user on the legacy install.</span></span> 
    
- <span data-ttu-id="7bfbc-111">Stellen Sie sicher, dass anonyme Benutzer an Konferenzen teilnehmen können.</span><span class="sxs-lookup"><span data-stu-id="7bfbc-111">Verify that anonymous users are able to join conferences.</span></span>
    
- <span data-ttu-id="7bfbc-112">Ein Benutzer auf der Vorgängerversion gehostet installieren mithilfe des Zugriffs durch Remotebenutzer (i Protokollierung bringt Lync Server/Skype für Unternehmen von außerhalb des Intranets, aber ohne VPN) mit einem Benutzer von Skype für Business Server 2019 und einem Benutzer von der Vorversion installieren.</span><span class="sxs-lookup"><span data-stu-id="7bfbc-112">A user hosted on the legacy install using remote user access (logging i nto Lync Server/Skype for Business from outside the intranet but without VPN) with a user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="7bfbc-113">Testen von im-, Anwesenheits-, A / V und Desktop freigeben.</span><span class="sxs-lookup"><span data-stu-id="7bfbc-113">Test IM, presence, A/V, and desktop sharing.</span></span>
    
- <span data-ttu-id="7bfbc-114">Ein Benutzer auf Skype für Zugriff durch Remotebenutzer (Anmelden bei Skype für Business Server 2019 von außerhalb des Intranets, aber ohne VPN) mit einem Benutzer von Skype für Business Server 2019 und einem Benutzer von der Vorgängerversion mithilfe von Business Server 2019 gehostet installieren.</span><span class="sxs-lookup"><span data-stu-id="7bfbc-114">A user hosted on Skype for Business Server 2019 using remote user access (logging in to Skype for Business Server 2019 from outside the intranet but without VPN) with a user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="7bfbc-115">Testen von im-, Anwesenheits-, A / V und Desktop freigeben.</span><span class="sxs-lookup"><span data-stu-id="7bfbc-115">Test IM, presence, A/V, and desktop sharing.</span></span>
    

