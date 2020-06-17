---
title: Verhindern von Sitzungen für Dienste
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
description: Sie können die Systemsteuerung "Legacy installs" verwenden, um neue Sitzungen für alle auf einem bestimmten Computer ausgeführten Legacy Dienste zu verhindern oder um neue Sitzungen für einen bestimmten Legacy Dienst zu verhindern.
ms.openlocfilehash: c5cc8846febaf690376e01c36b9fa023b8377970
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752287"
---
# <a name="prevent-sessions-for-services"></a><span data-ttu-id="d497b-103">Verhindern von Sitzungen für Dienste</span><span class="sxs-lookup"><span data-stu-id="d497b-103">Prevent sessions for services</span></span>

<span data-ttu-id="d497b-104">Sie können die Systemsteuerung "Legacy installs" verwenden, um neue Sitzungen für alle auf einem bestimmten Computer ausgeführten Legacy Dienste zu verhindern oder um neue Sitzungen für einen bestimmten Legacy Dienst zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="d497b-104">You can use the legacy installs Control Panel to prevent new sessions for all the legacy services running on a specific computer or to prevent new sessions for a specific legacy service.</span></span>
  
## <a name="to-prevent-new-sessions-for-services-on-a-computer"></a><span data-ttu-id="d497b-105">So verhindern Sie neue Sitzungen für Dienste auf einem Computer</span><span class="sxs-lookup"><span data-stu-id="d497b-105">To prevent new sessions for services on a computer</span></span>

1. <span data-ttu-id="d497b-106">Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe (oder gleichwertigen Benutzerrechten) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, an jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie Skype for Business Server 2019 bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="d497b-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2019.</span></span>
    
2. <span data-ttu-id="d497b-107">Öffnen Sie Skype for Business Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="d497b-107">Open Skype for Business Control Panel.</span></span>
    
3. <span data-ttu-id="d497b-108">Klicken Sie in der linken Navigationsleiste auf **Topologie** und dann auf **Status**.</span><span class="sxs-lookup"><span data-stu-id="d497b-108">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
    
4. <span data-ttu-id="d497b-109">Sortieren oder durchsuchen Sie auf der Seite **Status** die Liste, um den Computer zu ermitteln, auf dem die Dienste ausgeführt werden, für die Sie neue Sitzungen verhindern möchten. Klicken Sie anschließend auf den Computer.</span><span class="sxs-lookup"><span data-stu-id="d497b-109">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span> 
    
5. <span data-ttu-id="d497b-110">Klicken Sie auf **Aktion**.</span><span class="sxs-lookup"><span data-stu-id="d497b-110">Click **Action**.</span></span>
    
6. <span data-ttu-id="d497b-111">Klicken Sie auf **Neue Sitzungen für alle Dienste verhindern**.</span><span class="sxs-lookup"><span data-stu-id="d497b-111">Click **Prevent new sessions for all services**.</span></span>
    
## <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="d497b-112">So verhindern Sie neue Sitzungen für einen bestimmten Dienst</span><span class="sxs-lookup"><span data-stu-id="d497b-112">To prevent new sessions for a specific service</span></span>

1. <span data-ttu-id="d497b-113">Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe (oder gleichwertigen Benutzerrechten) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, an jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie Skype for Business Server 2019 bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="d497b-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2019.</span></span>
    
2. <span data-ttu-id="d497b-114">Öffnen Sie Skype for Business Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="d497b-114">Open Skype for Business Control Panel.</span></span>
    
3. <span data-ttu-id="d497b-115">Klicken Sie in der linken Navigationsleiste auf **Topologie** und dann auf **Status**.</span><span class="sxs-lookup"><span data-stu-id="d497b-115">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
    
4. <span data-ttu-id="d497b-116">Sortieren oder durchsuchen Sie die Liste auf der Seite **Status**, um den Computer zu ermitteln, auf dem der Dienst ausgeführt wird, den Sie starten oder beenden möchten. Klicken Sie anschließend auf den Computer.</span><span class="sxs-lookup"><span data-stu-id="d497b-116">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span> 
    
5. <span data-ttu-id="d497b-117">Klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="d497b-117">Click **Properties**.</span></span>
    
6. <span data-ttu-id="d497b-118">Sortieren Sie ggf. die Liste der Dienste, und klicken Sie auf den Dienst, für den Sie neue Sitzungen verhindern möchten.</span><span class="sxs-lookup"><span data-stu-id="d497b-118">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>
    
7. <span data-ttu-id="d497b-119">Klicken Sie auf **Aktion**.</span><span class="sxs-lookup"><span data-stu-id="d497b-119">Click **Action**.</span></span>
    
8. <span data-ttu-id="d497b-120">Klicken Sie auf **Neue Sitzungen für Dienst verhindern**.</span><span class="sxs-lookup"><span data-stu-id="d497b-120">Click **Prevent new sessions for service**.</span></span>
    
9. <span data-ttu-id="d497b-121">Klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="d497b-121">Click **Close**.</span></span>
    

