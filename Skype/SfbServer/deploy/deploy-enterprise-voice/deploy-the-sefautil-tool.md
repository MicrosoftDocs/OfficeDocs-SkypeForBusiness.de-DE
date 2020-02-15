---
title: Bereitstellen des SEFAUtil-Tools in Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
description: Bereitstellen des SEFAUtil-Tools in Skype for Business Server.
ms.openlocfilehash: 306e2ec305e9e12cd3486691b3e239e2aedfb548
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "41986810"
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business"></a><span data-ttu-id="89eb5-103">Bereitstellen des SEFAUtil-Tools in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="89eb5-103">Deploy the SEFAUtil tool in Skype for Business</span></span>
 
<span data-ttu-id="89eb5-104">Bereitstellen des SEFAUtil-Tools in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="89eb5-104">Deploying the SEFAUtil tool in Skype for Business Server.</span></span>
  
<span data-ttu-id="89eb5-105">Zum Bereitstellen und Verwalten der gruppenanrufannahme müssen Sie die Skype for Business Server Version des SEFAUtil-Tools verwenden.</span><span class="sxs-lookup"><span data-stu-id="89eb5-105">To deploy and manage Group Call Pickup, you need to use the Skype for Business Server version of the SEFAUtil tool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="89eb5-106">Verwaltete API von Microsoft Unified Communications (UCMA) 5-Laufzeitmodul muss auf jedem Computer installiert sein, auf dem Sie das SEFAUtil-Tool ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="89eb5-106">Microsoft Unified Communications Managed API (UCMA) 5 Runtime must be installed on any computer where you plan to run the SEFAUtil tool.</span></span> <span data-ttu-id="89eb5-107">Laden Sie ihn hier herunter: [Unified Communications Managed API 5.0 Runtime](https://www.microsoft.com/download/details.aspx?id=47344).</span><span class="sxs-lookup"><span data-stu-id="89eb5-107">Download it here: [Unified Communications Managed API 5.0 Runtime](https://www.microsoft.com/download/details.aspx?id=47344).</span></span> <span data-ttu-id="89eb5-108">Sie können auch das UCMA 5 SDK, das die Laufzeit enthält, hier herunterladen: [SDK für UCMA 5.0](https://www.microsoft.com/download/details.aspx?id=47345).</span><span class="sxs-lookup"><span data-stu-id="89eb5-108">You can also download the UCMA 5 SDK, which includes the runtime, here: [UCMA 5.0 SDK](https://www.microsoft.com/download/details.aspx?id=47345).</span></span>
  
<span data-ttu-id="89eb5-109">Sie können das SEFAUtil-Tool in jeder Front-End-Pool in Ihrer Bereitstellung ausführen.</span><span class="sxs-lookup"><span data-stu-id="89eb5-109">You can run the SEFAUtil tool in any Front End pool in your deployment.</span></span> <span data-ttu-id="89eb5-110">Zum Ausführen des SEFAUtil-Tools müssen Sie die Schritte 1, 2 und 3 im Skype for Business-Bereitstellungs-Assistenten auf dem Computer mit vertrauenswürdigen Anwendungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="89eb5-110">To run the SEFAUtil tool you must run Steps 1, 2, and 3 from the Skype for Business Deployment Wizard on the Trusted Application Computer.</span></span> <span data-ttu-id="89eb5-111">SEFAUtil erfordert, dass der lokale Konfigurationsspeicher vorhanden ist, sowie ein Zertifikat.</span><span class="sxs-lookup"><span data-stu-id="89eb5-111">SEFAUtil requires the local configuration store to be present, as well as a certificate.</span></span>
  
> [!NOTE]
> <span data-ttu-id="89eb5-112">Weitere Informationen zur Ausführung von SEFAUtil finden Sie im Blog-Artikel "[How to Get SEFAUtil Running?](https://go.microsoft.com/fwlink/?LinkId=278940)".</span><span class="sxs-lookup"><span data-stu-id="89eb5-112">For more details about running SEFAUtil, see the  blog article, "[How to get SEFAutil running?](https://go.microsoft.com/fwlink/?LinkId=278940)".</span></span> 
  
### <a name="to-deploy-sefautil"></a><span data-ttu-id="89eb5-113">So stellen Sie SEFAUtil bereit</span><span class="sxs-lookup"><span data-stu-id="89eb5-113">To deploy SEFAUtil</span></span>

1. <span data-ttu-id="89eb5-114">Melden Sie sich an dem Computer an, auf dem Skype for Business Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe oder mit den erforderlichen Benutzerrechten installiert ist, wie unter **Delegieren von Setup Berechtigungen**beschrieben.</span><span class="sxs-lookup"><span data-stu-id="89eb5-114">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="89eb5-115">Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype for Business 2015**, und klicken Sie dann auf **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="89eb5-115">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="89eb5-116">Das SEFAUtil-Tool kann nur auf einem Computer ausgeführt werden, der Teil eines vertrauenswürdigen Anwendungspools ist.</span><span class="sxs-lookup"><span data-stu-id="89eb5-116">The SEFAUtil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="89eb5-117">Definieren Sie bei Bedarf einen vertrauenswürdigen Anwendungspool für die Front-End-Pool, in der Sie SEFAUtil ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="89eb5-117">If needed, define a trusted application pool for the Front End pool where you plan to run SEFAUtil.</span></span> <span data-ttu-id="89eb5-118">Führen Sie an der Eingabeaufforderung Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="89eb5-118">At the command line, run:</span></span>
    
   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```
    > [!NOTE]
    > <span data-ttu-id="89eb5-119">Pool-FQDN: der FQDN des Servers oder Pools, der als Host für die SEFAUtil-Anwendung verwendet wird (in der Regel ein Skype for Business-Front-End-Server oder-Pool).</span><span class="sxs-lookup"><span data-stu-id="89eb5-119">Pool FQDN: The FQDN of the server or pool that will host the SEFAUtil application (usually a Skype for Business Front End server or pool).</span></span>
    > <span data-ttu-id="89eb5-120">FQDN des Pool Registrierungsstelle: der FQDN des Skype for Business Front-End-Servers oder Pools, der diesem Anwendungspool zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="89eb5-120">Pool Registrar FQDN: The FQDN of the Skype for Business Front End server or pool associated with this application pool.</span></span>
    > <span data-ttu-id="89eb5-121">Pool Website: die Website-ID der Website, auf der dieser Pool verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="89eb5-121">Pool Site: The Site ID of the site on which this pool is homed.</span></span>

4. <span data-ttu-id="89eb5-122">Definieren Sie das SEFAUtil-Tool als vertrauenswürdige Anwendung.</span><span class="sxs-lookup"><span data-stu-id="89eb5-122">Define the SEFAUtil tool as a trusted application.</span></span> <span data-ttu-id="89eb5-123">Führen Sie an der Eingabeaufforderung Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="89eb5-123">At the command line, run:</span></span>
    
   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > <span data-ttu-id="89eb5-124">Sie können bei Bedarf einen anderen Port verwenden.</span><span class="sxs-lookup"><span data-stu-id="89eb5-124">You can use a different port if needed.</span></span> 
  
5. <span data-ttu-id="89eb5-125">Aktivieren Sie die Topologie mit Ihren Änderungen.</span><span class="sxs-lookup"><span data-stu-id="89eb5-125">Enable the topology with your changes.</span></span> <span data-ttu-id="89eb5-126">Führen Sie an der Eingabeaufforderung Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="89eb5-126">At the command line, run:</span></span>
    
   ```powershell
   Enable-CsTopology
   ```

6. <span data-ttu-id="89eb5-127">Wenn Sie noch nicht vorhanden sind, laden Sie die Skype for Business Server Version des SEFAUtil-Tools von [diesem Speicherort](https://www.microsoft.com/download/details.aspx?id=52631)herunter, und installieren Sie Sie in dem vertrauenswürdigen Anwendungspool, den Sie in Schritt 3 erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="89eb5-127">If you haven't already, download the Skype for Business Server version of the SEFAUtil tool from [this location](https://www.microsoft.com/download/details.aspx?id=52631), and install it on the trusted application pool you created in step 3.</span></span>
    
7. <span data-ttu-id="89eb5-128">Stellen Sie sicher, dass das SEFAUtil-Tool wie folgt ordnungsgemäß ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="89eb5-128">Verify that the SEFAUtil tool is running correctly, as follows:</span></span> 
    
    <span data-ttu-id="89eb5-129">a.</span><span class="sxs-lookup"><span data-stu-id="89eb5-129">a.</span></span> <span data-ttu-id="89eb5-130">Führen Sie das Tool über die Windows-Eingabeaufforderung mit Administratorrechten aus, um die Anrufweiterleitungseinstellungen eines Benutzers in Ihrer Bereitstellung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="89eb5-130">Run the tool from the Windows command prompt with administrator privileges to display the call forwarding settings of a user in your deployment.</span></span>
    
    <span data-ttu-id="89eb5-131">b.</span><span class="sxs-lookup"><span data-stu-id="89eb5-131">b.</span></span> <span data-ttu-id="89eb5-132">Zeigt die Anrufweiterleitungseinstellungen eines Benutzers an.</span><span class="sxs-lookup"><span data-stu-id="89eb5-132">Display the call forwarding settings of a user.</span></span> <span data-ttu-id="89eb5-133">Führen Sie an der Eingabeaufforderung Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="89eb5-133">At the command line, run:</span></span>
    
   ```console
   SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
   ```

<span data-ttu-id="89eb5-134">Die Anrufweiterleitungseinstellungen für den Benutzer werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="89eb5-134">The call forwarding settings for the user will be displayed.</span></span>
    

