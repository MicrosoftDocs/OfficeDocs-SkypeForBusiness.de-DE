---
title: Das Tool SEFAUtil in Skype für Unternehmen bereitstellen
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
description: Bereitstellen von dem Tool SEFAUtil in Skype für Business Server ein.
ms.openlocfilehash: fc8b26dbc0f81be3ea7dd9f0fc3f5c728d49e965
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375259"
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business"></a><span data-ttu-id="6960b-103">Das Tool SEFAUtil in Skype für Unternehmen bereitstellen</span><span class="sxs-lookup"><span data-stu-id="6960b-103">Deploy the SEFAUtil tool in Skype for Business</span></span>
 
<span data-ttu-id="6960b-104">Bereitstellen von dem Tool SEFAUtil in Skype für Business Server ein.</span><span class="sxs-lookup"><span data-stu-id="6960b-104">Deploying the SEFAUtil tool in Skype for Business Server.</span></span>
  
<span data-ttu-id="6960b-105">Zum Bereitstellen und Verwalten der Gruppe anrufen Pickup-, müssen Sie die Skype für Business Server-Version des Tools SEFAUtil verwenden.</span><span class="sxs-lookup"><span data-stu-id="6960b-105">To deploy and manage Group Call Pickup, you need to use the Skype for Business Server version of the SEFAUtil tool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="6960b-106">Microsoft Unified Communications Managed API (UCMA) 5 Runtime muss auf jedem Computer installiert sein, auf dem Sie das Tool SEFAUtil ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="6960b-106">Microsoft Unified Communications Managed API (UCMA) 5 Runtime must be installed on any computer where you plan to run the SEFAUtil tool.</span></span> <span data-ttu-id="6960b-107">Hier herunterladen: [Unified Communications Managed API 5.0 Runtime](https://www.microsoft.com/en-us/download/details.aspx?id=47344).</span><span class="sxs-lookup"><span data-stu-id="6960b-107">Download it here: [Unified Communications Managed API 5.0 Runtime](https://www.microsoft.com/en-us/download/details.aspx?id=47344).</span></span> <span data-ttu-id="6960b-108">Sie können auch die UCMA 5-SDK, einschließlich die Laufzeit hier herunterladen: [UCMA 5.0 SDK](https://www.microsoft.com/en-us/download/details.aspx?id=47345).</span><span class="sxs-lookup"><span data-stu-id="6960b-108">You can also download the UCMA 5 SDK, which includes the runtime, here: [UCMA 5.0 SDK](https://www.microsoft.com/en-us/download/details.aspx?id=47345).</span></span>
  
<span data-ttu-id="6960b-109">Sie können das Tool SEFAUtil in Ihrer Bereitstellung in einem beliebigen Front-End-Pool ausführen.</span><span class="sxs-lookup"><span data-stu-id="6960b-109">You can run the SEFAUtil tool in any Front End pool in your deployment.</span></span> <span data-ttu-id="6960b-110">Zum Ausführen des Tools SEFAUtil müssen Sie die Schritte 1, 2 und 3 aus der Skype für Business Bereitstellungs-Assistenten auf dem Computer für die vertrauenswürdige Anwendung ausführen.</span><span class="sxs-lookup"><span data-stu-id="6960b-110">To run the SEFAUtil tool you must run Steps 1, 2, and 3 from the Skype for Business Deployment Wizard on the Trusted Application Computer.</span></span> <span data-ttu-id="6960b-111">SEFAUtil ist der lokale Konfigurationsspeicher vorhanden sein muss, sowie ein Zertifikat erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6960b-111">SEFAUtil requires the local configuration store to be present, as well as a certificate.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6960b-112">Weitere Informationen zum Ausführen von SEFAUtil, finden Sie im Blog-Artikel "[SEFAutil unter Abrufen von?](https://go.microsoft.com/fwlink/?LinkId=278940)".</span><span class="sxs-lookup"><span data-stu-id="6960b-112">For more details about running SEFAUtil, see the  blog article, "[How to get SEFAutil running?](https://go.microsoft.com/fwlink/?LinkId=278940)".</span></span> 
  
### <a name="to-deploy-sefautil"></a><span data-ttu-id="6960b-113">So stellen Sie das SEFAUtil-Tool bereit</span><span class="sxs-lookup"><span data-stu-id="6960b-113">To deploy SEFAUtil</span></span>

1. <span data-ttu-id="6960b-114">Melden Sie sich an dem Computer, auf dem Skype für Business Server-Verwaltungsshell, als Mitglied der Gruppe RTCUniversalServerAdmins oder mit den erforderlichen Benutzerrechten installiert ist wie beschrieben unter **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="6960b-114">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="6960b-115">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="6960b-115">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="6960b-116">Das SEFAUtil-Tool kann nur auf einem Computer ausgeführt werden, der zu einem vertrauenswürdigen Anwendungspool gehört.</span><span class="sxs-lookup"><span data-stu-id="6960b-116">The SEFAUtil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="6960b-117">Definieren Sie bei Bedarf einen vertrauenswürdigen Anwendungspool für den Front-End-Pool, SEFAUtil ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="6960b-117">If needed, define a trusted application pool for the Front End pool where you plan to run SEFAUtil.</span></span> <span data-ttu-id="6960b-118">Führen Sie an der Eingabeaufforderung folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="6960b-118">At the command line, run:</span></span>
    
   ```
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```

4. <span data-ttu-id="6960b-p104">Definieren Sie das SEFAUtil-Tool als eine vertrauenswürdige Anwendung. Führen Sie an der Eingabeaufforderung folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="6960b-p104">Define the SEFAUtil tool as a trusted application. At the command line, run:</span></span>
    
   ```
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > <span data-ttu-id="6960b-121">Sie können ggf. einen anderen Port verwenden.</span><span class="sxs-lookup"><span data-stu-id="6960b-121">You can use a different port if needed.</span></span> 
  
5. <span data-ttu-id="6960b-p105">Aktivieren Sie die Topologie mit Ihren Änderungen. Führen Sie an der Eingabeaufforderung folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="6960b-p105">Enable the topology with your changes. At the command line, run:</span></span>
    
   ```
   Enable-CsTopology
   ```

6. <span data-ttu-id="6960b-124">Wenn Sie noch nicht geschehen ist, laden Sie die Skype für Business Server-Version des Tools SEFAUtil aus [diesem Speicherort](https://www.microsoft.com/en-us/download/details.aspx?id=52631), und installieren Sie es auf den vertrauenswürdigen Anwendungspool in Schritt 3 erstellte.</span><span class="sxs-lookup"><span data-stu-id="6960b-124">If you haven't already, download the Skype for Business Server version of the SEFAUtil tool from [this location](https://www.microsoft.com/en-us/download/details.aspx?id=52631), and install it on the trusted application pool you created in step 3.</span></span>
    
7. <span data-ttu-id="6960b-125">Gehen Sie wie folgt vor, um sicherzustellen, dass Ihr SEFAUtil-Tool korrekt ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="6960b-125">Verify that the SEFAUtil tool is running correctly, as follows:</span></span> 
    
    <span data-ttu-id="6960b-126">a.</span><span class="sxs-lookup"><span data-stu-id="6960b-126">a.</span></span> <span data-ttu-id="6960b-127">Führen Sie das Tool an der Windows-Eingabeaufforderung mit Administratorberechtigungen aus, um die Anrufweiterleistungseinstellungen eines Benutzers in Ihrer Bereitstellung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="6960b-127">Run the tool from the Windows command prompt with administrator privileges to display the call forwarding settings of a user in your deployment.</span></span>
    
    <span data-ttu-id="6960b-128">b.</span><span class="sxs-lookup"><span data-stu-id="6960b-128">b.</span></span> <span data-ttu-id="6960b-129">Zeigen Sie die Anrufweiterleitungseinstellungen eines Benutzers an.</span><span class="sxs-lookup"><span data-stu-id="6960b-129">Display the call forwarding settings of a user.</span></span> <span data-ttu-id="6960b-130">Führen Sie an der Eingabeaufforderung folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="6960b-130">At the command line, run:</span></span>
    
   ```
   SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
   ```

<span data-ttu-id="6960b-131">Die Anrufweiterleitungseinstellungen für den Benutzer werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6960b-131">The call forwarding settings for the user will be displayed.</span></span>
    

