---
title: Überprüfen des Partnerverbunds und des Remotezugriffs für externe Benutzer
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Nachdem Sie die partnerverbundroute zum Skype for Business Server 2019 Edgeserver gewechselt haben, sollten Sie einige Funktionstests durchführen, um zu überprüfen, ob der Verbund wie erwartet ausgeführt wird. Tests für den Zugriff durch externe Benutzer sollten alle Typen von externen Benutzern enthalten, die von Ihrer Organisation unterstützt werden, einschließlich einer oder aller der folgenden.
ms.openlocfilehash: b2567f4e46bd39d2748e3a4a3ba6cc5d6c197b11
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751667"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="cb55f-104">Überprüfen des Partnerverbunds und des Remotezugriffs für externe Benutzer</span><span class="sxs-lookup"><span data-stu-id="cb55f-104">Verify federation and remote access for external users</span></span>

<span data-ttu-id="cb55f-105">Nachdem Sie die partnerverbundroute zum Skype for Business Server 2019 Edgeserver gewechselt haben, sollten Sie einige Funktionstests durchführen, um zu überprüfen, ob der Verbund wie erwartet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="cb55f-105">After transitioning the federation route to the Skype for Business Server 2019 Edge Server, you should perform some functional tests to verify that federation performs as expected.</span></span> <span data-ttu-id="cb55f-106">Tests für den Zugriff durch externe Benutzer sollten alle Typen von externen Benutzern enthalten, die von Ihrer Organisation unterstützt werden, einschließlich einer oder aller der folgenden.</span><span class="sxs-lookup"><span data-stu-id="cb55f-106">Tests for external user access should include each type of external user that your organization supports, including any or all of the following.</span></span>
  
### <a name="test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="cb55f-107">Testen der Konnektivität externer Benutzer und des externen Zugriffs</span><span class="sxs-lookup"><span data-stu-id="cb55f-107">Test connectivity of external users and external access</span></span>

- <span data-ttu-id="cb55f-108">Benutzer aus mindestens einer Verbunddomäne, einem internen Benutzer auf Skype for Business Server 2019 und einem Benutzer auf der Legacy Installation.</span><span class="sxs-lookup"><span data-stu-id="cb55f-108">Users from at least one federated domain, an internal user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="cb55f-109">Testen von Chatnachrichten, Anwesenheit, Audio/Video (A/V) und Desktopfreigabe.</span><span class="sxs-lookup"><span data-stu-id="cb55f-109">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>
    
- <span data-ttu-id="cb55f-110">Benutzer aller öffentlichen Sofortnachrichten-Dienstanbieter, die von Ihrer Organisation unterstützt werden (und für die die Bereitstellung abgeschlossen ist), die mit einem Benutzer auf Skype for Business Server 2019 und einem Benutzer auf der Legacy Installation kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="cb55f-110">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Skype for Business Server 2019 and a user on the legacy install.</span></span> 
    
- <span data-ttu-id="cb55f-111">Stellen Sie sicher, dass anonyme Benutzer in der Lage sind, an Konferenzen teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="cb55f-111">Verify that anonymous users are able to join conferences.</span></span>
    
- <span data-ttu-id="cb55f-112">Ein auf der Legacy Installation gehosteter Benutzer verwendet den Remotebenutzerzugriff (Protokollierung i num lync Server/Skype for Business von außerhalb des Intranets, aber ohne VPN) mit einem Benutzer unter Skype for Business Server 2019 und einem Benutzer auf der Legacy Installation.</span><span class="sxs-lookup"><span data-stu-id="cb55f-112">A user hosted on the legacy install using remote user access (logging i nto Lync Server/Skype for Business from outside the intranet but without VPN) with a user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="cb55f-113">Testen Sie Sofortnachrichten, Anwesenheit, A/V und Desktopfreigabe.</span><span class="sxs-lookup"><span data-stu-id="cb55f-113">Test IM, presence, A/V, and desktop sharing.</span></span>
    
- <span data-ttu-id="cb55f-114">Ein Benutzer, der auf Skype for Business Server 2019 mit Remotebenutzerzugriff (Anmeldung bei Skype for Business Server 2019 von außerhalb des Intranets, aber ohne VPN) mit einem Benutzer unter Skype for Business Server 2019 und einem Benutzer auf der Legacy Installation gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="cb55f-114">A user hosted on Skype for Business Server 2019 using remote user access (logging in to Skype for Business Server 2019 from outside the intranet but without VPN) with a user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="cb55f-115">Testen Sie Sofortnachrichten, Anwesenheit, A/V und Desktopfreigabe.</span><span class="sxs-lookup"><span data-stu-id="cb55f-115">Test IM, presence, A/V, and desktop sharing.</span></span>
    

