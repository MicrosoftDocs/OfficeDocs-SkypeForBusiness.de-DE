---
title: Installieren der Komponenten für beständigen Chat in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61370aa6-9708-4ff8-b531-b258a928806f
description: 'Zusammenfassung: Lesen Sie dieses Thema, um zu erfahren, wie Sie den Skype for Business Server-Bereitstellungs-Assistenten verwenden, um Komponenten und Dienste von Skype for Business Server 2015 zu installieren.'
ms.openlocfilehash: 5b8205cb2ab828001eae76eeaab8cd4f697c9315
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234744"
---
# <a name="install-persistent-chat-components-in-skype-for-business-server-2015"></a><span data-ttu-id="e3a50-103">Installieren der Komponenten für beständigen Chat in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e3a50-103">Install Persistent Chat components in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="e3a50-104">**Zusammenfassung:** In diesem Thema erfahren Sie, wie Sie den Skype for Business Server-Bereitstellungs-Assistenten verwenden, um Komponenten und Dienste von Skype for Business Server 2015 zu installieren.</span><span class="sxs-lookup"><span data-stu-id="e3a50-104">**Summary:** Read this topic to learn how to use the Skype for Business Server Deployment Wizard to install Skype for Business Server 2015 components and services.</span></span>
  
<span data-ttu-id="e3a50-105">Bevor Sie Komponenten für beständigen Chat installieren, müssen Sie sicherstellen, dass Sie die erforderliche Hardware und Software bereits installiert haben, und die geeignete Topologie zur Unterstützung des beständigen Chat Servers erstellt.</span><span class="sxs-lookup"><span data-stu-id="e3a50-105">Before you install Persistent Chat components, be sure you have already installed prerequisite hardware and software, and created the appropriate topology to support Persistent Chat Server.</span></span> <span data-ttu-id="e3a50-106">Einzelheiten zu Planung und Anforderungen finden Sie unter [Voraussetzungen für Ihre Skype for Business-Umgebung](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md) und [Planen des Servers für beständigen Chat in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="e3a50-106">For details about planning and requirements, see [Requirements for your Skype for Business environment](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md) and [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span></span> <span data-ttu-id="e3a50-107">Informationen dazu, wie Sie Ihre Topologie aktualisieren und veröffentlichen, um den Server für beständigen Chat einzubeziehen, finden Sie unter [Hinzufügen von beständigem Chat Server zu Ihrer Skype for Business Server 2015-Topologie](add-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="e3a50-107">For information about how to update and publish your topology to include Persistent Chat Server, see [Add Persistent Chat Server to your Skype for Business Server 2015 topology](add-persistent-chat-server.md).</span></span>
  
> [!NOTE] 
> <span data-ttu-id="e3a50-108">Der beständige Chat ist in Skype for Business Server 2015 verfügbar, wird aber in Skype for Business Server 2019 nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e3a50-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="e3a50-109">In Teams steht dieselbe Funktionalität zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="e3a50-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="e3a50-110">Weitere Informationen finden Sie unter [Erste Schritte mit dem Upgrade für Microsoft Teams](/microsoftteams/upgrade-start-here).</span><span class="sxs-lookup"><span data-stu-id="e3a50-110">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="e3a50-111">Wenn Sie den beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktion für Teams benötigen, oder die Verwendung von Skype for Business Server 2015 fortsetzen.</span><span class="sxs-lookup"><span data-stu-id="e3a50-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="install-and-start-services"></a><span data-ttu-id="e3a50-112">Installations- und Startdienste</span><span class="sxs-lookup"><span data-stu-id="e3a50-112">Install and start services</span></span>

<span data-ttu-id="e3a50-113">Wählen Sie im Skype for Business Server-Bereitstellungs-Assistenten installieren oder aktualisieren Sie das Skype for Business Server-System aus, um die folgenden Schritte auszuführen:</span><span class="sxs-lookup"><span data-stu-id="e3a50-113">Using the Skype for Business Server Deployment Wizard, choose Install or Update Skype for Business Server System to perform the following steps:</span></span> 
  
1. <span data-ttu-id="e3a50-114">Lokalen Konfigurationsspeicher installieren</span><span class="sxs-lookup"><span data-stu-id="e3a50-114">Install Local Configuration Store</span></span>
    
2. <span data-ttu-id="e3a50-115">Skype for Business Server-Komponenten einrichten oder entfernen</span><span class="sxs-lookup"><span data-stu-id="e3a50-115">Setup or Remove Skype for Business Server Components</span></span>
    
3. <span data-ttu-id="e3a50-116">Zertifikate anfordern, installieren oder zuweisen</span><span class="sxs-lookup"><span data-stu-id="e3a50-116">Request, Install or Assign Certificates</span></span>
    
4. <span data-ttu-id="e3a50-117">Dienste starten</span><span class="sxs-lookup"><span data-stu-id="e3a50-117">Start services</span></span>
    
<span data-ttu-id="e3a50-118">Details zur Verwendung des Bereitstellungs-Assistenten, um Komponenten zu installieren, Zertifikate zuzuweisen und Dienste zu starten, finden Sie unter [Installieren von Skype for Business Server 2015](../../deploy/install/install.md) und [Installieren von Skype for Business Server 2015 auf Servern in der Topologie](../../deploy/install/install-skype-for-business-server.md).</span><span class="sxs-lookup"><span data-stu-id="e3a50-118">For details on how to use the Deployment Wizard to install components, assign certificates, and start services, see [Install Skype for Business Server 2015](../../deploy/install/install.md) and [Install Skype for Business Server 2015 on servers in the topology](../../deploy/install/install-skype-for-business-server.md).</span></span>
  

