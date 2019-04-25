---
title: Überprüfen des Partnerverbunds und des Remotezugriffs für externe Benutzer
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Nach dem Übergang der partnerverbundroute, der Skype für Business Server 2019 Edge-Server, sollten Sie Funktionstests aus, um sicherzustellen, dass der Partnerverbund erwartungsgemäß ausgeführt wird, durchführen. Tests für den Zugriff externer Benutzer sollte jede Art von externer Benutzer enthalten, die Ihre Organisation einige oder alle der folgenden einschließlich unterstützt.
ms.openlocfilehash: 3a520b39d76ab93f4ec7fcaacd139b3f83a3326a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231350"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="fe5cc-104">Überprüfen des Partnerverbunds und des Remotezugriffs für externe Benutzer</span><span class="sxs-lookup"><span data-stu-id="fe5cc-104">Verify federation and remote access for external users</span></span>

<span data-ttu-id="fe5cc-105">Nach dem Übergang der partnerverbundroute, der Skype für Business Server 2019 Edge-Server, sollten Sie Funktionstests aus, um sicherzustellen, dass der Partnerverbund erwartungsgemäß ausgeführt wird, durchführen.</span><span class="sxs-lookup"><span data-stu-id="fe5cc-105">After transitioning the federation route to the Skype for Business Server 2019 Edge Server, you should perform some functional tests to verify that federation performs as expected.</span></span> <span data-ttu-id="fe5cc-106">Tests für den Zugriff externer Benutzer sollte jede Art von externer Benutzer enthalten, die Ihre Organisation einige oder alle der folgenden einschließlich unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fe5cc-106">Tests for external user access should include each type of external user that your organization supports, including any or all of the following.</span></span>
  
### <a name="test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="fe5cc-107">Testen der Konnektivität von externen Benutzern und den externen Zugriff</span><span class="sxs-lookup"><span data-stu-id="fe5cc-107">Test connectivity of external users and external access</span></span>

- <span data-ttu-id="fe5cc-108">Benutzer aus mindestens eine verbunddomäne, ein interner Benutzer auf Skype für Business Server 2019 und einem Benutzer von der Vorgängerversion installieren.</span><span class="sxs-lookup"><span data-stu-id="fe5cc-108">Users from at least one federated domain, an internal user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="fe5cc-109">Testen von Sofortnachrichten (IM), Anwesenheit, Audio/Video (A / V), und Desktopfreigabe.</span><span class="sxs-lookup"><span data-stu-id="fe5cc-109">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>
    
- <span data-ttu-id="fe5cc-110">Benutzer aller öffentlichen Sofortnachrichten-Dienstanbieter, die von Ihrer Organisation unterstützt (und für die Bereitstellung abgeschlossen) zum Kommunizieren mit einem Benutzer von Skype für Business Server 2019 und einem Benutzer von der Vorversion installieren.</span><span class="sxs-lookup"><span data-stu-id="fe5cc-110">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Skype for Business Server 2019 and a user on the legacy install.</span></span> 
    
- <span data-ttu-id="fe5cc-111">Stellen Sie sicher, dass anonyme Benutzer an Konferenzen teilnehmen können.</span><span class="sxs-lookup"><span data-stu-id="fe5cc-111">Verify that anonymous users are able to join conferences.</span></span>
    
- <span data-ttu-id="fe5cc-112">Ein Benutzer auf der Vorgängerversion gehostet installieren mithilfe des Zugriffs durch Remotebenutzer (i Protokollierung bringt Lync Server/Skype für Unternehmen von außerhalb des Intranets, aber ohne VPN) mit einem Benutzer von Skype für Business Server 2019 und einem Benutzer von der Vorversion installieren.</span><span class="sxs-lookup"><span data-stu-id="fe5cc-112">A user hosted on the legacy install using remote user access (logging i nto Lync Server/Skype for Business from outside the intranet but without VPN) with a user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="fe5cc-113">Testen von im-, Anwesenheits-, A / V und Desktop freigeben.</span><span class="sxs-lookup"><span data-stu-id="fe5cc-113">Test IM, presence, A/V, and desktop sharing.</span></span>
    
- <span data-ttu-id="fe5cc-114">Ein Benutzer auf Skype für Zugriff durch Remotebenutzer (Anmelden bei Skype für Business Server 2019 von außerhalb des Intranets, aber ohne VPN) mit einem Benutzer von Skype für Business Server 2019 und einem Benutzer von der Vorgängerversion mithilfe von Business Server 2019 gehostet installieren.</span><span class="sxs-lookup"><span data-stu-id="fe5cc-114">A user hosted on Skype for Business Server 2019 using remote user access (logging in to Skype for Business Server 2019 from outside the intranet but without VPN) with a user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="fe5cc-115">Testen von im-, Anwesenheits-, A / V und Desktop freigeben.</span><span class="sxs-lookup"><span data-stu-id="fe5cc-115">Test IM, presence, A/V, and desktop sharing.</span></span>
    

