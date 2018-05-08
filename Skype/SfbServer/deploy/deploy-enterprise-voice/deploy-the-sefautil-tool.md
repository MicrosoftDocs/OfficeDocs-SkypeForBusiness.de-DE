---
title: Bereitstellen des SEFAUtil-Tools in Skype for Business 2015
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
ms.assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
description: Bereitstellen von dem Tool SEFAUtil in Skype für Business Server ein.
ms.openlocfilehash: f0bb660218b761e513e120f4ea5786eb9278b12a
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business-2015"></a><span data-ttu-id="f5e0d-103">Bereitstellen des SEFAUtil-Tools in Skype for Business 2015</span><span class="sxs-lookup"><span data-stu-id="f5e0d-103">Deploy the SEFAUtil tool in Skype for Business 2015</span></span>
 
<span data-ttu-id="f5e0d-104">Bereitstellen von dem Tool SEFAUtil in Skype für Business Server ein.</span><span class="sxs-lookup"><span data-stu-id="f5e0d-104">Deploying the SEFAUtil tool in Skype for Business Server.</span></span>
  
<span data-ttu-id="f5e0d-105">Zum Bereitstellen und Verwalten der Gruppe anrufen Pickup-, müssen Sie die Skype für Business Server-Version des Tools SEFAUtil verwenden.</span><span class="sxs-lookup"><span data-stu-id="f5e0d-105">To deploy and manage Group Call Pickup, you need to use the Skype for Business Server version of the SEFAUtil tool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="f5e0d-106">Das Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK muss auf jedem Computer installiert sein, auf dem Sie das SEFAUtil-Tool ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="f5e0d-106">Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK must be installed on any computer where you plan to run the SEFAUtil tool.</span></span> 
  
<span data-ttu-id="f5e0d-107">Sie können das Tool SEFAUtil in Ihrer Bereitstellung in einem beliebigen Front-End-Pool ausführen.</span><span class="sxs-lookup"><span data-stu-id="f5e0d-107">You can run the SEFAUtil tool in any Front End pool in your deployment.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f5e0d-108">Weitere Informationen zum Ausführen von SEFAUtil, finden Sie im Technet-Blog-Artikel "[SEFAutil unter Abrufen von?](https://go.microsoft.com/fwlink/?LinkId=278940)".</span><span class="sxs-lookup"><span data-stu-id="f5e0d-108">For more details about running SEFAUtil, see the Technet blog article, "[How to get SEFAutil running?](https://go.microsoft.com/fwlink/?LinkId=278940)".</span></span> 
  
### <a name="to-deploy-sefautil"></a><span data-ttu-id="f5e0d-109">So stellen Sie das SEFAUtil-Tool bereit</span><span class="sxs-lookup"><span data-stu-id="f5e0d-109">To deploy SEFAUtil</span></span>

1. <span data-ttu-id="f5e0d-110">Melden Sie sich an dem Computer, auf dem Skype für Business Server-Verwaltungsshell, als Mitglied der Gruppe RTCUniversalServerAdmins oder mit den erforderlichen Benutzerrechten installiert ist wie beschrieben unter **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="f5e0d-110">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="f5e0d-111">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="f5e0d-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="f5e0d-112">Das SEFAUtil-Tool kann nur auf einem Computer ausgeführt werden, der zu einem vertrauenswürdigen Anwendungspool gehört.</span><span class="sxs-lookup"><span data-stu-id="f5e0d-112">The SEFAUtil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="f5e0d-113">Definieren Sie bei Bedarf einen vertrauenswürdigen Anwendungspool für den Front-End-Pool, SEFAUtil ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="f5e0d-113">If needed, define a trusted application pool for the Front End pool where you plan to run SEFAUtil.</span></span> <span data-ttu-id="f5e0d-114">Führen Sie an der Eingabeaufforderung folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="f5e0d-114">At the command line, run:</span></span>
    
   ```
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```

4. <span data-ttu-id="f5e0d-p102">Definieren Sie das SEFAUtil-Tool als eine vertrauenswürdige Anwendung. Führen Sie an der Eingabeaufforderung folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="f5e0d-p102">Define the SEFAUtil tool as a trusted application. At the command line, run:</span></span>
    
   ```
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > <span data-ttu-id="f5e0d-117">Sie können ggf. einen anderen Port verwenden.</span><span class="sxs-lookup"><span data-stu-id="f5e0d-117">You can use a different port if needed.</span></span> 
  
5. <span data-ttu-id="f5e0d-p103">Aktivieren Sie die Topologie mit Ihren Änderungen. Führen Sie an der Eingabeaufforderung folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="f5e0d-p103">Enable the topology with your changes. At the command line, run:</span></span>
    
  ```
  Enable-CsTopology
  ```

6. <span data-ttu-id="f5e0d-120">Wenn Sie noch nicht geschehen ist, laden Sie die Skype für Business Server-Version des Tools SEFAUtil aus [diesem Speicherort](https://www.microsoft.com/en-us/download/details.aspx?id=52631), und installieren Sie es auf den vertrauenswürdigen Anwendungspool in Schritt 3 erstellte.</span><span class="sxs-lookup"><span data-stu-id="f5e0d-120">If you haven't already, download the Skype for Business Server version of the SEFAUtil tool from [this location](https://www.microsoft.com/en-us/download/details.aspx?id=52631), and install it on the trusted application pool you created in step 3.</span></span>
    
7. <span data-ttu-id="f5e0d-121">Gehen Sie wie folgt vor, um sicherzustellen, dass Ihr SEFAUtil-Tool korrekt ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="f5e0d-121">Verify that the SEFAUtil tool is running correctly, as follows:</span></span> 
    
    <span data-ttu-id="f5e0d-122">a.</span><span class="sxs-lookup"><span data-stu-id="f5e0d-122">a.</span></span> <span data-ttu-id="f5e0d-123">Führen Sie das Tool an der Windows-Eingabeaufforderung mit Administratorberechtigungen aus, um die Anrufweiterleistungseinstellungen eines Benutzers in Ihrer Bereitstellung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f5e0d-123">Run the tool from the Windows command prompt with administrator privileges to display the call forwarding settings of a user in your deployment.</span></span>
    
    <span data-ttu-id="f5e0d-124">b.</span><span class="sxs-lookup"><span data-stu-id="f5e0d-124">b.</span></span> <span data-ttu-id="f5e0d-125">Zeigen Sie die Anrufweiterleitungseinstellungen eines Benutzers an.</span><span class="sxs-lookup"><span data-stu-id="f5e0d-125">Display the call forwarding settings of a user.</span></span> <span data-ttu-id="f5e0d-126">Führen Sie an der Eingabeaufforderung folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="f5e0d-126">At the command line, run:</span></span>
    
  ```
  SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
  ```

<span data-ttu-id="f5e0d-127">Die Anrufweiterleitungseinstellungen für den Benutzer werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f5e0d-127">The call forwarding settings for the user will be displayed.</span></span>
    

