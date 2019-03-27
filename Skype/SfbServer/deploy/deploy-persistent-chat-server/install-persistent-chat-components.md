---
title: Installieren der Komponenten für beständigen Chat in Skype for Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61370aa6-9708-4ff8-b531-b258a928806f
description: 'Zusammenfassung: Lesen Sie in diesem Thema erfahren, wie die Skype für Business Server-Bereitstellungs-Assistenten verwenden, um Skype für Business Server 2015 Komponenten und Dienste zu installieren.'
ms.openlocfilehash: 78fb134ef8db5b0c47c890db9454858ff392a624
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899554"
---
# <a name="install-persistent-chat-components-in-skype-for-business-server-2015"></a><span data-ttu-id="bb456-103">Installieren der Komponenten für beständigen Chat in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="bb456-103">Install Persistent Chat components in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="bb456-104">**Zusammenfassung:** Lesen Sie in diesem Thema erfahren, wie die Skype für Business Server-Bereitstellungs-Assistenten verwenden, um Skype für Business Server 2015 Komponenten und Dienste zu installieren.</span><span class="sxs-lookup"><span data-stu-id="bb456-104">**Summary:** Read this topic to learn how to use the Skype for Business Server Deployment Wizard to install Skype for Business Server 2015 components and services.</span></span>
  
<span data-ttu-id="bb456-105">Vor der Installation von Persistent Chat-Komponenten werden Sie sicher, dass Sie bereits erforderliche Hardware und Software installiert haben, und die entsprechende Topologie zur Unterstützung von Persistent Chat Server erstellt.</span><span class="sxs-lookup"><span data-stu-id="bb456-105">Before you install Persistent Chat components, be sure you have already installed prerequisite hardware and software, and created the appropriate topology to support Persistent Chat Server.</span></span> <span data-ttu-id="bb456-106">Ausführliche Informationen zur Planung und Anforderungen finden Sie unter [Anforderungen für Ihre Skype für geschäftsumgebung](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md) und [Planen von Persistent Chat Server in Skype für Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="bb456-106">For details about planning and requirements, see [Requirements for your Skype for Business environment](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md) and [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span></span> <span data-ttu-id="bb456-107">Informationen zum Aktualisieren und Veröffentlichen Ihrer Topologie zum Einschließen von Persistent Chat Server finden Sie unter [Persistent Chat Server hinzufügen, um Ihre Skype für Business Server 2015 Topologie](add-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="bb456-107">For information about how to update and publish your topology to include Persistent Chat Server, see [Add Persistent Chat Server to your Skype for Business Server 2015 topology](add-persistent-chat-server.md).</span></span>
  
> [!NOTE] 
> <span data-ttu-id="bb456-108">Beständiger Chat wird steht in Skype für Business Server 2015 jedoch nicht mehr unterstützt in Skype Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="bb456-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="bb456-109">Die gleiche Funktionalität ist in Teams verfügbar.</span><span class="sxs-lookup"><span data-stu-id="bb456-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="bb456-110">Weitere Informationen finden Sie unter [Weg von Skype für Unternehmen, die Microsoft-Teams](/microsoftteams/journey-skypeforbusiness-teams).</span><span class="sxs-lookup"><span data-stu-id="bb456-110">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="bb456-111">Wenn Sie Persistent Chat verwenden müssen, sind Ihrer Auswahl an Benutzer, die diese Funktionalität Teams migrieren oder weiterhin Skype für Business Server 2015 verwenden.</span><span class="sxs-lookup"><span data-stu-id="bb456-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="install-and-start-services"></a><span data-ttu-id="bb456-112">Installations- und Startdienste</span><span class="sxs-lookup"><span data-stu-id="bb456-112">Install and start services</span></span>

<span data-ttu-id="bb456-113">Wählen Sie mithilfe der Skype für Business Server-Bereitstellungs-Assistenten installieren oder Update Skype für Business Server-System, um die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="bb456-113">Using the Skype for Business Server Deployment Wizard, choose Install or Update Skype for Business Server System to perform the following steps:</span></span> 
  
1. <span data-ttu-id="bb456-114">Lokalen Konfigurationsspeicher installieren</span><span class="sxs-lookup"><span data-stu-id="bb456-114">Install Local Configuration Store</span></span>
    
2. <span data-ttu-id="bb456-115">Skype for Business Server-Komponenten einrichten oder entfernen</span><span class="sxs-lookup"><span data-stu-id="bb456-115">Setup or Remove Skype for Business Server Components</span></span>
    
3. <span data-ttu-id="bb456-116">Zertifikate anfordern, installieren oder zuweisen</span><span class="sxs-lookup"><span data-stu-id="bb456-116">Request, Install or Assign Certificates</span></span>
    
4. <span data-ttu-id="bb456-117">Dienste starten</span><span class="sxs-lookup"><span data-stu-id="bb456-117">Start services</span></span>
    
<span data-ttu-id="bb456-118">Weitere Informationen zur Verwendung des Bereitstellungs-Assistenten zum Installieren von Komponenten Zuweisen von Zertifikaten, und Starten von Diensten, finden Sie unter [Installieren von Skype für Business Server 2015](../../deploy/install/install.md) und [Skype für Business Server 2015 auf Servern in der Topologie installieren](../../deploy/install/install-skype-for-business-server.md).</span><span class="sxs-lookup"><span data-stu-id="bb456-118">For details on how to use the Deployment Wizard to install components, assign certificates, and start services, see [Install Skype for Business Server 2015](../../deploy/install/install.md) and [Install Skype for Business Server 2015 on servers in the topology](../../deploy/install/install-skype-for-business-server.md).</span></span>
  

