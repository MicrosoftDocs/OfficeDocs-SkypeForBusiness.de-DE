---
title: Installieren der erforderlichen Komponenten für Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2ef91a1e-2899-44c8-8e2c-527cb9114a0a
description: 'Zusammenfassung: Informationen Sie zu den Servern und Serverrollen, die Sie vor der Installation von Skype für Business Server 2015 konfigurieren müssen. Laden Sie eine kostenlose Testversion von Skype für Business Server 2015 aus dem Microsoft Evaluation Center herunter: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: f37954b4eddffbcef08c270dc86234e3a56e7079
ms.sourcegitcommit: 2c084358844f02fbf7953f2ea49ed6d710cbf06f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="install-prerequisites-for-skype-for-business-server-2015"></a><span data-ttu-id="915bd-104">Installieren der erforderlichen Komponenten für Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="915bd-104">Install prerequisites for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="915bd-105">**Zusammenfassung:** Informationen Sie zu den Servern und Serverrollen, die Sie vor der Installation von Skype für Business Server 2015 konfigurieren müssen.</span><span class="sxs-lookup"><span data-stu-id="915bd-105">**Summary:** Learn about the servers and server roles you must configure before you install Skype for Business Server 2015.</span></span> <span data-ttu-id="915bd-106">Laden Sie eine kostenlose Testversion von Skype für Business Server 2015 aus dem [Microsoft-Evaluierungscenter](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="915bd-106">Download a free trial of Skype for Business Server 2015 from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="915bd-107">Die Installation der erforderlichen Softwarekomponenten besteht in der Einrichtung von Windows Server durch Installation der erforderlichen Rollen und Funktionen auf jedem Server in der Topologie.</span><span class="sxs-lookup"><span data-stu-id="915bd-107">Installing prerequisites consists of setting up Windows Server by installing the required roles and features on each of the servers in the topology.</span></span> <span data-ttu-id="915bd-108">Welche Komponenten erforderlich sind, hängt von der Rolle des jeweiligen Servers in der Topologie ab.</span><span class="sxs-lookup"><span data-stu-id="915bd-108">The requirements are based on the role the server will fulfill in the topology.</span></span> <span data-ttu-id="915bd-109">Sie können die Schritte 1 bis 5 in einer beliebigen Reihenfolge ausführen.</span><span class="sxs-lookup"><span data-stu-id="915bd-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="915bd-110">Die Schritte 6, 7 und 8 müssen jedoch wie in der Abbildung dargestellt nacheinander und nach den Schritten 1 bis 5 ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="915bd-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="915bd-111">Die Installation der erforderlichen Softwarekomponenten ist Schritt 1 von 8.</span><span class="sxs-lookup"><span data-stu-id="915bd-111">Installing prerequisites is step 1 of 8.</span></span>
  
![Übersichtsdiagramm – Voraussetzungen für die Installation](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a><span data-ttu-id="915bd-113">Einrichten von Windows Server</span><span class="sxs-lookup"><span data-stu-id="915bd-113">Setup Windows Server</span></span>

<span data-ttu-id="915bd-114">Skype für Business Server 2015 erfordert das Betriebssystem Windows Server und eine Anzahl von erforderlichen Komponenten, bevor es installiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="915bd-114">Skype for Business Server 2015 requires the Windows Server operating system and a number of prerequisites before it can be installed.</span></span> <span data-ttu-id="915bd-115">Weitere Informationen zur Planung der erforderlichen Komponenten finden Sie unter [Server-Anforderungen für Skype für Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="915bd-115">For details on planning for prerequisites, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span> 
  
> [!TIP]
> <span data-ttu-id="915bd-p105">Das nachfolgende Verfahren basiert auf Windows Server 2012 R2. Wenn Sie eine andere Windows Server-Version verwenden, kann die Vorgehensweise leicht abweichen.</span><span class="sxs-lookup"><span data-stu-id="915bd-p105">This procedure uses Windows Server 2012 R2. If you are using a different version of Windows Server, the procedure might be slightly different.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="915bd-118">Bevor Sie beginnen, stellen Sie sicher, dass Windows Server mithilfe von Windows Update auf dem neuesten Stand ist.</span><span class="sxs-lookup"><span data-stu-id="915bd-118">Before you begin, make sure that Windows Server is up-to-date by using Windows Update.</span></span> 
  
![Windows Server auf dem neuesten Stand.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
<span data-ttu-id="915bd-120">Schauen Sie sich das Video mit den Schritten zum **Imstallieren der erforderlichen Komponenten** an:</span><span class="sxs-lookup"><span data-stu-id="915bd-120">Watch the video steps for **install prerequisites**:</span></span>
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a><span data-ttu-id="915bd-121">Installieren der erforderlichen Rollen und Funktionen für Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="915bd-121">Install required roles and features for front-end servers</span></span>

<span data-ttu-id="915bd-122">Sie können der erforderlichen Rollen und Funktionen, die mit dem Server-Manager installieren.</span><span class="sxs-lookup"><span data-stu-id="915bd-122">You can install the required roles and features using Server Manager.</span></span> 
    
1. <span data-ttu-id="915bd-123">Installieren Sie die erforderliche Software Features, die in [Server-Anforderungen für Skype für Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="915bd-123">Install the prerequisite software features listed in [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span> <span data-ttu-id="915bd-124">Die erforderliche Software muss auf dem Server sein, die für Business Server 2015 Skype ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="915bd-124">The required software must be on the server that will run Skype for Business Server 2015.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="915bd-125">Windows Server 2012 R2 installiert nicht standardmäßig alle Quelldateien der erforderlichen Funktionen.</span><span class="sxs-lookup"><span data-stu-id="915bd-125">Windows Server 2012 R2 does not install all of the source files for the required features by default.</span></span> <span data-ttu-id="915bd-126">Wenn der Server nicht mit dem Internet verbunden ist, müssen Sie das Windows Server 2012 R2-Installationsmedium einlegen und **Alternativen Quellpfad angeben** auswählen, um die erforderlichen Funktionen zu installieren.</span><span class="sxs-lookup"><span data-stu-id="915bd-126">If the server is not connected to the Internet, you will need to insert the Windows Server 2012 R2 media and select **Specify an alternate source path** in order to install the required features.</span></span> <span data-ttu-id="915bd-127">Die Quelldateien befinden sich im Verzeichnis „sources\sxs“.</span><span class="sxs-lookup"><span data-stu-id="915bd-127">The source files are located in the sources\sxs directory.</span></span> <span data-ttu-id="915bd-128">Wenn das Windows Server 2012 R2-Medium beispielsweise in Laufwerk D eingelegt wurde, würde der Pfad `d:\sources\sxs` lauten.</span><span class="sxs-lookup"><span data-stu-id="915bd-128">For example, if the Windows Server 2012 R2 media is in drive D, you would set the path to `d:\sources\sxs`.</span></span> <span data-ttu-id="915bd-129">Es ist wichtig, dass Sie die neuesten Updates von Windows Update verfügen.</span><span class="sxs-lookup"><span data-stu-id="915bd-129">It is important that you have the latest updates from Windows Update.</span></span> <span data-ttu-id="915bd-130">Wenn Sie nicht mit dem Internet verbunden sind, müssen Sie alle relevanten Updates sowie alle erforderlichen Komponenten über die erforderlichen Updates manuell zu installieren.</span><span class="sxs-lookup"><span data-stu-id="915bd-130">If you are not connected to the Internet, you will need to manually install all relevant updates as well as any prerequisites to the required updates.</span></span> 
  
1. <span data-ttu-id="915bd-131">Wenn der Abschluss der Installation angezeigt wird, müssen Sie den Server neu starten, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="915bd-131">When the dialog box indicates that the installation has completed, you will need to reboot the server to complete the process.</span></span>
    
1. <span data-ttu-id="915bd-132">Führen Sie **Windows Update** erneut aus, um zu prüfen, ob es ein Update für die installierten Rollen und Dienste gibt.</span><span class="sxs-lookup"><span data-stu-id="915bd-132">Run **Windows Update** again to check if there are any updates to the roles and services that were installed.</span></span>
    
1. <span data-ttu-id="915bd-133">Wenn Sie Skype Business Server-Systemsteuerung auf diesem Server verwenden müssen Sie auch Silverlight installieren.</span><span class="sxs-lookup"><span data-stu-id="915bd-133">If you will be using Skype for Business Server Control Panel on this server then you must also install Silverlight.</span></span> <span data-ttu-id="915bd-134">Zum Installieren von Silverlight finden Sie unter [Microsoft Silverlight](https://www.microsoft.com/silverlight/).</span><span class="sxs-lookup"><span data-stu-id="915bd-134">To install Silverlight, see [Microsoft Silverlight](https://www.microsoft.com/silverlight/).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="915bd-135">Für Server, die eine andere Funktion als die eines Front-End-Servers haben, z. B. Director, Persistent Chat oder Edge, sind eigene Softwarekomponenten erforderlich.</span><span class="sxs-lookup"><span data-stu-id="915bd-135">The prerequisites for servers performing roles other than front-end server, such as the role of Director, Persistent Chat, or Edge, have their own prerequisites.</span></span> <span data-ttu-id="915bd-136">Ausführliche Informationen zum die genauen erforderlichen Komponenten erforderlich, die für jeden Servertyp finden Sie unter [Anforderungen für Skype für Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="915bd-136">For details on the exact prerequisites required by each server type, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span> 
  

