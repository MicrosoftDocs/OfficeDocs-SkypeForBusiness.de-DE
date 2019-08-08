---
title: Überprüfen des Partnerverbunds und des Remotezugriffs für externe Benutzer
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Nachdem Sie die Föderations Route zum Skype for Business Server 2019 Edge-Server gewechselt haben, sollten Sie einige Funktionstests durchführen, um zu überprüfen, ob der Verbund wie erwartet funktioniert. Tests für den Zugriff durch externe Benutzer sollten alle externen Benutzertypen enthalten, die von Ihrer Organisation unterstützt werden, einschließlich der folgenden:'
ms.openlocfilehash: ea17cbc8643d864f464da8e8a582191504970059
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243768"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="3eb71-104">Überprüfen des Partnerverbunds und des Remotezugriffs für externe Benutzer</span><span class="sxs-lookup"><span data-stu-id="3eb71-104">Verify federation and remote access for external users</span></span>

<span data-ttu-id="3eb71-105">Nachdem Sie die Föderations Route zum Skype for Business Server 2019 Edge-Server gewechselt haben, sollten Sie einige Funktionstests durchführen, um zu überprüfen, ob der Verbund wie erwartet funktioniert.</span><span class="sxs-lookup"><span data-stu-id="3eb71-105">After transitioning the federation route to the Skype for Business Server 2019 Edge Server, you should perform some functional tests to verify that federation performs as expected.</span></span> <span data-ttu-id="3eb71-106">Tests für den Zugriff durch externe Benutzer sollten alle externen Benutzertypen enthalten, die von Ihrer Organisation unterstützt werden, einschließlich der folgenden:</span><span class="sxs-lookup"><span data-stu-id="3eb71-106">Tests for external user access should include each type of external user that your organization supports, including any or all of the following.</span></span>
  
### <a name="test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="3eb71-107">Testen der Konnektivität externer Benutzer und des externen Zugriffs</span><span class="sxs-lookup"><span data-stu-id="3eb71-107">Test connectivity of external users and external access</span></span>

- <span data-ttu-id="3eb71-108">Benutzer aus mindestens einer Föderationsdomäne, einem internen Benutzer in Skype for Business Server 2019 und einem Benutzer auf der Legacy Installation.</span><span class="sxs-lookup"><span data-stu-id="3eb71-108">Users from at least one federated domain, an internal user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="3eb71-109">Testen Sie Instant Messaging (im), Anwesenheitsinformationen, Audio/Video (A/V) und Desktopfreigabe.</span><span class="sxs-lookup"><span data-stu-id="3eb71-109">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>
    
- <span data-ttu-id="3eb71-110">Benutzer jedes öffentlichen Chat Dienstanbieters, die von Ihrer Organisation unterstützt werden (und für die Bereitstellung abgeschlossen wurde), die mit einem Benutzer in Skype for Business Server 2019 und einem Benutzer auf der Legacy Installation kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="3eb71-110">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Skype for Business Server 2019 and a user on the legacy install.</span></span> 
    
- <span data-ttu-id="3eb71-111">Überprüfen Sie, ob anonyme Benutzer an Konferenzen teilnehmen können.</span><span class="sxs-lookup"><span data-stu-id="3eb71-111">Verify that anonymous users are able to join conferences.</span></span>
    
- <span data-ttu-id="3eb71-112">Ein Benutzer, der auf der Legacy Installation mit einem Benutzer in Skype for Business Server 2019 und einem Benutzer auf der Legacy Installation unter Verwendung des Remotebenutzerzugriffs (Protokollierung von lync Server/Skype for Business außerhalb des Intranets, aber ohne VPN) gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="3eb71-112">A user hosted on the legacy install using remote user access (logging i nto Lync Server/Skype for Business from outside the intranet but without VPN) with a user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="3eb71-113">Testen Sie Chat, Anwesenheit, A/V und Desktopfreigabe.</span><span class="sxs-lookup"><span data-stu-id="3eb71-113">Test IM, presence, A/V, and desktop sharing.</span></span>
    
- <span data-ttu-id="3eb71-114">Ein Benutzer, der auf Skype for Business Server 2019 mit dem Remotebenutzerzugriff (Anmeldung bei Skype for Business Server 2019 von außerhalb des Intranets, aber ohne VPN) mit einem Benutzer in Skype for Business Server 2019 und einem Benutzer auf der Legacy Installation gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="3eb71-114">A user hosted on Skype for Business Server 2019 using remote user access (logging in to Skype for Business Server 2019 from outside the intranet but without VPN) with a user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="3eb71-115">Testen Sie Chat, Anwesenheit, A/V und Desktopfreigabe.</span><span class="sxs-lookup"><span data-stu-id="3eb71-115">Test IM, presence, A/V, and desktop sharing.</span></span>
    

