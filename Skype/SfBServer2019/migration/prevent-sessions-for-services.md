---
title: Verhindern von Sitzungen für Dienste
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Sie können die Systemsteuerung für Legacy Installationen verwenden, um neue Sitzungen für alle Legacy Dienste zu verhindern, die auf einem bestimmten Computer ausgeführt werden, oder um neue Sitzungen für einen bestimmten Legacy Dienst zu verhindern.
ms.openlocfilehash: 978c97bd7f610e6b40d467b80f5df8483b6d370f
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244365"
---
# <a name="prevent-sessions-for-services"></a><span data-ttu-id="1104c-103">Verhindern von Sitzungen für Dienste</span><span class="sxs-lookup"><span data-stu-id="1104c-103">Prevent sessions for services</span></span>

<span data-ttu-id="1104c-104">Sie können die Systemsteuerung für Legacy Installationen verwenden, um neue Sitzungen für alle Legacy Dienste zu verhindern, die auf einem bestimmten Computer ausgeführt werden, oder um neue Sitzungen für einen bestimmten Legacy Dienst zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="1104c-104">You can use the legacy installs Control Panel to prevent new sessions for all the legacy services running on a specific computer or to prevent new sessions for a specific legacy service.</span></span>
  
## <a name="to-prevent-new-sessions-for-services-on-a-computer"></a><span data-ttu-id="1104c-105">So verhindern Sie, dass neue Sitzungen für Dienste auf einem Computer</span><span class="sxs-lookup"><span data-stu-id="1104c-105">To prevent new sessions for services on a computer</span></span>

1. <span data-ttu-id="1104c-106">Melden Sie sich bei einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder über entsprechende Benutzerrechte verfügt) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, bei jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie Skype for Business Server bereitgestellt haben. 2019.</span><span class="sxs-lookup"><span data-stu-id="1104c-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2019.</span></span>
    
2. <span data-ttu-id="1104c-107">Öffnen Sie das Skype Control Panel für Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="1104c-107">Open Skype for Business Control Panel.</span></span>
    
3. <span data-ttu-id="1104c-108">Klicken Sie in der linken Navigationsleiste auf \*\*Topologie \*\* und dann auf **Status**. </span><span class="sxs-lookup"><span data-stu-id="1104c-108">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
    
4. <span data-ttu-id="1104c-109">Sortieren oder Durchsuchen Sie auf der **Status** Seite die Liste nach Bedarf, um den Computer zu finden, auf dem die Dienste ausgeführt werden, für die Sie neue Sitzungen verhindern möchten, und klicken Sie darauf.</span><span class="sxs-lookup"><span data-stu-id="1104c-109">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span> 
    
5. <span data-ttu-id="1104c-110">Klicken Sie auf **Aktion**.</span><span class="sxs-lookup"><span data-stu-id="1104c-110">Click **Action**.</span></span>
    
6. <span data-ttu-id="1104c-111">Klicken Sie auf **neue Sitzungen für alle Dienste verhindern**.</span><span class="sxs-lookup"><span data-stu-id="1104c-111">Click **Prevent new sessions for all services**.</span></span>
    
## <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="1104c-112">So verhindern Sie neue Sitzungen für einen bestimmten Dienst</span><span class="sxs-lookup"><span data-stu-id="1104c-112">To prevent new sessions for a specific service</span></span>

1. <span data-ttu-id="1104c-113">Melden Sie sich bei einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder über entsprechende Benutzerrechte verfügt) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, bei jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie Skype for Business Server bereitgestellt haben. 2019.</span><span class="sxs-lookup"><span data-stu-id="1104c-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2019.</span></span>
    
2. <span data-ttu-id="1104c-114">Öffnen Sie das Skype Control Panel für Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="1104c-114">Open Skype for Business Control Panel.</span></span>
    
3. <span data-ttu-id="1104c-115">Klicken Sie in der linken Navigationsleiste auf \*\*Topologie \*\* und dann auf **Status**. </span><span class="sxs-lookup"><span data-stu-id="1104c-115">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
    
4. <span data-ttu-id="1104c-116">Sortieren oder Durchsuchen Sie auf der **Status** Seite die Liste nach Bedarf, um den Computer zu finden, auf dem der Dienst ausgeführt wird, den Sie starten oder beenden möchten, und klicken Sie darauf.</span><span class="sxs-lookup"><span data-stu-id="1104c-116">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span> 
    
5. <span data-ttu-id="1104c-117">Klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="1104c-117">Click **Properties**.</span></span>
    
6. <span data-ttu-id="1104c-118">Sortieren Sie die Liste der Dienste, falls erforderlich, und klicken Sie auf den Dienst, für den Sie neue Sitzungen verhindern möchten.</span><span class="sxs-lookup"><span data-stu-id="1104c-118">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>
    
7. <span data-ttu-id="1104c-119">Klicken Sie auf **Aktion**.</span><span class="sxs-lookup"><span data-stu-id="1104c-119">Click **Action**.</span></span>
    
8. <span data-ttu-id="1104c-120">Klicken Sie auf **neue Sitzungen für Dienst verhindern**.</span><span class="sxs-lookup"><span data-stu-id="1104c-120">Click **Prevent new sessions for service**.</span></span>
    
9. <span data-ttu-id="1104c-121">Klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="1104c-121">Click **Close**.</span></span>
    

