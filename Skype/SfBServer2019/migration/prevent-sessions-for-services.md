---
title: Verhindern von Sitzungen für Dienste
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Sie können der Vorversion installiert Systemsteuerung so verhindern Sie neue Sitzungen für alle legacy Dienste auf einem bestimmten Computer ausgeführt oder um neue Sitzungen für einen bestimmten legacy-Dienst zu verhindern.
ms.openlocfilehash: 9f3f9bb301841d7e71c18f4d3ca052f3d0c74dce
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231539"
---
# <a name="prevent-sessions-for-services"></a><span data-ttu-id="6ebef-103">Verhindern von Sitzungen für Dienste</span><span class="sxs-lookup"><span data-stu-id="6ebef-103">Prevent sessions for services</span></span>

<span data-ttu-id="6ebef-104">Sie können der Vorversion installiert Systemsteuerung so verhindern Sie neue Sitzungen für alle legacy Dienste auf einem bestimmten Computer ausgeführt oder um neue Sitzungen für einen bestimmten legacy-Dienst zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="6ebef-104">You can use the legacy installs Control Panel to prevent new sessions for all the legacy services running on a specific computer or to prevent new sessions for a specific legacy service.</span></span>
  
## <a name="to-prevent-new-sessions-for-services-on-a-computer"></a><span data-ttu-id="6ebef-105">So verhindern Sie neue Sitzungen für Dienste auf einem computer</span><span class="sxs-lookup"><span data-stu-id="6ebef-105">To prevent new sessions for services on a computer</span></span>

1. <span data-ttu-id="6ebef-106">Von einem Benutzerkonto, das Mitglied der Gruppe RTCUniversalServerAdmins (oder gleichwertige Benutzerrechte verfügt), oder der CsServerAdministrator oder CsAdministrator-Rolle, melden Sie sich an einem beliebigen Computer, die im Netzwerk ist in der Bereitstellung von Skype für Business Server zugeordnet ist 2019.</span><span class="sxs-lookup"><span data-stu-id="6ebef-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2019.</span></span>
    
2. <span data-ttu-id="6ebef-107">Öffnen von Skype für die Business-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="6ebef-107">Open Skype for Business Control Panel.</span></span>
    
3. <span data-ttu-id="6ebef-108">Klicken Sie in der linken Navigationsleiste auf \*\*Topologie \*\* und dann auf **Status**. </span><span class="sxs-lookup"><span data-stu-id="6ebef-108">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
    
4. <span data-ttu-id="6ebef-109">Erforderlich, auf der Seite **Status** sortieren oder Durchsuchen der Liste als zum Computer mit der die Dienste zu verhindern, dass neue Sitzungen, und klicken Sie dann auf es werden soll.</span><span class="sxs-lookup"><span data-stu-id="6ebef-109">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span> 
    
5. <span data-ttu-id="6ebef-110">Klicken Sie auf **Aktion**.</span><span class="sxs-lookup"><span data-stu-id="6ebef-110">Click **Action**.</span></span>
    
6. <span data-ttu-id="6ebef-111">Klicken Sie auf **neue Sitzungen für alle Dienste verhindern**.</span><span class="sxs-lookup"><span data-stu-id="6ebef-111">Click **Prevent new sessions for all services**.</span></span>
    
## <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="6ebef-112">So verhindern Sie neue Sitzungen für einen bestimmten Dienst</span><span class="sxs-lookup"><span data-stu-id="6ebef-112">To prevent new sessions for a specific service</span></span>

1. <span data-ttu-id="6ebef-113">Von einem Benutzerkonto, das Mitglied der Gruppe RTCUniversalServerAdmins (oder gleichwertige Benutzerrechte verfügt), oder der CsServerAdministrator oder CsAdministrator-Rolle, melden Sie sich an einem beliebigen Computer, die im Netzwerk ist in der Bereitstellung von Skype für Business Server zugeordnet ist 2019.</span><span class="sxs-lookup"><span data-stu-id="6ebef-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2019.</span></span>
    
2. <span data-ttu-id="6ebef-114">Öffnen von Skype für die Business-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="6ebef-114">Open Skype for Business Control Panel.</span></span>
    
3. <span data-ttu-id="6ebef-115">Klicken Sie in der linken Navigationsleiste auf \*\*Topologie \*\* und dann auf **Status**. </span><span class="sxs-lookup"><span data-stu-id="6ebef-115">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
    
4. <span data-ttu-id="6ebef-116">Sie möchten starten oder beenden, und klicken Sie dann auf, auf der Seite **Status** , sortieren oder Durchsuchen der Liste nach Bedarf an den Computer zu suchen, der der Dienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6ebef-116">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span> 
    
5. <span data-ttu-id="6ebef-117">Klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="6ebef-117">Click **Properties**.</span></span>
    
6. <span data-ttu-id="6ebef-118">Sortieren Sie die Liste der Dienste, bei Bedarf, und klicken Sie auf den Dienst, für den Sie neue Sitzungen verhindern möchten.</span><span class="sxs-lookup"><span data-stu-id="6ebef-118">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>
    
7. <span data-ttu-id="6ebef-119">Klicken Sie auf **Aktion**.</span><span class="sxs-lookup"><span data-stu-id="6ebef-119">Click **Action**.</span></span>
    
8. <span data-ttu-id="6ebef-120">Klicken Sie auf **neue Sitzungen für Dienst verhindern**.</span><span class="sxs-lookup"><span data-stu-id="6ebef-120">Click **Prevent new sessions for service**.</span></span>
    
9. <span data-ttu-id="6ebef-121">Klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="6ebef-121">Click **Close**.</span></span>
    

