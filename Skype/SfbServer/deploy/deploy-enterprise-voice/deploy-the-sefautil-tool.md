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
ms.openlocfilehash: 48fa0077315169e6a80e65e91d7ce9a31583cdb5
ms.sourcegitcommit: 4e9574c8a9eac270135684aa4a8b77621aa46403
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/09/2018
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business-2015"></a><span data-ttu-id="a4c20-103">Bereitstellen des SEFAUtil-Tools in Skype for Business 2015</span><span class="sxs-lookup"><span data-stu-id="a4c20-103">Deploy the SEFAUtil tool in Skype for Business 2015</span></span>
 
<span data-ttu-id="a4c20-104">Bereitstellen von dem Tool SEFAUtil in Skype für Business Server ein.</span><span class="sxs-lookup"><span data-stu-id="a4c20-104">Deploying the SEFAUtil tool in Skype for Business Server.</span></span>
  
<span data-ttu-id="a4c20-105">Zum Bereitstellen und Verwalten der Gruppe anrufen Pickup-, müssen Sie die Skype für Business Server-Version des Tools SEFAUtil verwenden.</span><span class="sxs-lookup"><span data-stu-id="a4c20-105">To deploy and manage Group Call Pickup, you need to use the Skype for Business Server version of the SEFAUtil tool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="a4c20-106">Microsoft Unified Communications Managed API (UCMA) 5 Runtime muss auf jedem Computer installiert sein, auf dem Sie das Tool SEFAUtil ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="a4c20-106">Microsoft Unified Communications Managed API (UCMA) 5 Runtime must be installed on any computer where you plan to run the SEFAUtil tool.</span></span> <span data-ttu-id="a4c20-107">Hier herunterladen: [Unified Communications Managed API 5.0 Runtime](https://www.microsoft.com/en-us/download/details.aspx?id=47344).</span><span class="sxs-lookup"><span data-stu-id="a4c20-107">Download it here: [Unified Communications Managed API 5.0 Runtime](https://www.microsoft.com/en-us/download/details.aspx?id=47344).</span></span> <span data-ttu-id="a4c20-108">Sie können auch die UCMA 5-SDK, einschließlich die Laufzeit hier herunterladen: [UCMA 5.0 SDK](https://www.microsoft.com/en-us/download/details.aspx?id=47345).</span><span class="sxs-lookup"><span data-stu-id="a4c20-108">You can also download the UCMA 5 SDK, which includes the runtime, here: [UCMA 5.0 SDK](https://www.microsoft.com/en-us/download/details.aspx?id=47345).</span></span>
  
<span data-ttu-id="a4c20-109">Sie können das Tool SEFAUtil in Ihrer Bereitstellung in einem beliebigen Front-End-Pool ausführen.</span><span class="sxs-lookup"><span data-stu-id="a4c20-109">You can run the SEFAUtil tool in any Front End pool in your deployment.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a4c20-110">Weitere Informationen zum Ausführen von SEFAUtil, finden Sie im Technet-Blog-Artikel "[SEFAutil unter Abrufen von?](https://go.microsoft.com/fwlink/?LinkId=278940)".</span><span class="sxs-lookup"><span data-stu-id="a4c20-110">For more details about running SEFAUtil, see the Technet blog article, "[How to get SEFAutil running?](https://go.microsoft.com/fwlink/?LinkId=278940)".</span></span> 
  
### <a name="to-deploy-sefautil"></a><span data-ttu-id="a4c20-111">So stellen Sie das SEFAUtil-Tool bereit</span><span class="sxs-lookup"><span data-stu-id="a4c20-111">To deploy SEFAUtil</span></span>

1. <span data-ttu-id="a4c20-112">Melden Sie sich an dem Computer, auf dem Skype für Business Server-Verwaltungsshell, als Mitglied der Gruppe RTCUniversalServerAdmins oder mit den erforderlichen Benutzerrechten installiert ist wie beschrieben unter **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="a4c20-112">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="a4c20-113">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="a4c20-113">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="a4c20-114">Das SEFAUtil-Tool kann nur auf einem Computer ausgeführt werden, der zu einem vertrauenswürdigen Anwendungspool gehört.</span><span class="sxs-lookup"><span data-stu-id="a4c20-114">The SEFAUtil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="a4c20-115">Definieren Sie bei Bedarf einen vertrauenswürdigen Anwendungspool für den Front-End-Pool, SEFAUtil ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="a4c20-115">If needed, define a trusted application pool for the Front End pool where you plan to run SEFAUtil.</span></span> <span data-ttu-id="a4c20-116">Führen Sie an der Eingabeaufforderung folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="a4c20-116">At the command line, run:</span></span>
    
   ```
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```

4. <span data-ttu-id="a4c20-p103">Definieren Sie das SEFAUtil-Tool als eine vertrauenswürdige Anwendung. Führen Sie an der Eingabeaufforderung folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="a4c20-p103">Define the SEFAUtil tool as a trusted application. At the command line, run:</span></span>
    
   ```
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > <span data-ttu-id="a4c20-119">Sie können ggf. einen anderen Port verwenden.</span><span class="sxs-lookup"><span data-stu-id="a4c20-119">You can use a different port if needed.</span></span> 
  
5. <span data-ttu-id="a4c20-p104">Aktivieren Sie die Topologie mit Ihren Änderungen. Führen Sie an der Eingabeaufforderung folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="a4c20-p104">Enable the topology with your changes. At the command line, run:</span></span>
    
  ```
  Enable-CsTopology
  ```

6. <span data-ttu-id="a4c20-122">Wenn Sie noch nicht geschehen ist, laden Sie die Skype für Business Server-Version des Tools SEFAUtil aus [diesem Speicherort](https://www.microsoft.com/en-us/download/details.aspx?id=52631), und installieren Sie es auf den vertrauenswürdigen Anwendungspool in Schritt 3 erstellte.</span><span class="sxs-lookup"><span data-stu-id="a4c20-122">If you haven't already, download the Skype for Business Server version of the SEFAUtil tool from [this location](https://www.microsoft.com/en-us/download/details.aspx?id=52631), and install it on the trusted application pool you created in step 3.</span></span>
    
7. <span data-ttu-id="a4c20-123">Gehen Sie wie folgt vor, um sicherzustellen, dass Ihr SEFAUtil-Tool korrekt ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="a4c20-123">Verify that the SEFAUtil tool is running correctly, as follows:</span></span> 
    
    <span data-ttu-id="a4c20-124">a.</span><span class="sxs-lookup"><span data-stu-id="a4c20-124">a.</span></span> <span data-ttu-id="a4c20-125">Führen Sie das Tool an der Windows-Eingabeaufforderung mit Administratorberechtigungen aus, um die Anrufweiterleistungseinstellungen eines Benutzers in Ihrer Bereitstellung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a4c20-125">Run the tool from the Windows command prompt with administrator privileges to display the call forwarding settings of a user in your deployment.</span></span>
    
    <span data-ttu-id="a4c20-126">b.</span><span class="sxs-lookup"><span data-stu-id="a4c20-126">b.</span></span> <span data-ttu-id="a4c20-127">Zeigen Sie die Anrufweiterleitungseinstellungen eines Benutzers an.</span><span class="sxs-lookup"><span data-stu-id="a4c20-127">Display the call forwarding settings of a user.</span></span> <span data-ttu-id="a4c20-128">Führen Sie an der Eingabeaufforderung folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="a4c20-128">At the command line, run:</span></span>
    
  ```
  SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
  ```

<span data-ttu-id="a4c20-129">Die Anrufweiterleitungseinstellungen für den Benutzer werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a4c20-129">The call forwarding settings for the user will be displayed.</span></span>
    

