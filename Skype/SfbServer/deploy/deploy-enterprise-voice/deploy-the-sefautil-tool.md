---
title: Bereitstellen des SEFAUtil-Tools in Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
description: Bereitstellen des SEFAUtil-Tools in Skype for Business Server.
ms.openlocfilehash: e36448652f245d1c81a00cc206b6e8047a8f9d28
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001885"
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business"></a><span data-ttu-id="41c1f-103">Bereitstellen des SEFAUtil-Tools in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="41c1f-103">Deploy the SEFAUtil tool in Skype for Business</span></span>
 
<span data-ttu-id="41c1f-104">Bereitstellen des SEFAUtil-Tools in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="41c1f-104">Deploying the SEFAUtil tool in Skype for Business Server.</span></span>
  
<span data-ttu-id="41c1f-105">Zur Bereitstellung und Verwaltung der Gruppenanruf Abholung müssen Sie die Skype for Business Server-Version des SEFAUtil-Tools verwenden.</span><span class="sxs-lookup"><span data-stu-id="41c1f-105">To deploy and manage Group Call Pickup, you need to use the Skype for Business Server version of the SEFAUtil tool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="41c1f-106">Microsoft Unified Communications Managed API (UCMA) 5 Runtime muss auf jedem Computer installiert sein, auf dem Sie das SEFAUtil-Tool ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="41c1f-106">Microsoft Unified Communications Managed API (UCMA) 5 Runtime must be installed on any computer where you plan to run the SEFAUtil tool.</span></span> <span data-ttu-id="41c1f-107">Laden Sie Sie hier herunter: [Unified Communications Managed API 5,0-Laufzeit](https://www.microsoft.com/en-us/download/details.aspx?id=47344).</span><span class="sxs-lookup"><span data-stu-id="41c1f-107">Download it here: [Unified Communications Managed API 5.0 Runtime](https://www.microsoft.com/en-us/download/details.aspx?id=47344).</span></span> <span data-ttu-id="41c1f-108">Sie können auch das UCMA 5 SDK, das die Laufzeit enthält, hier herunterladen: [UCMA 5,0 SDK](https://www.microsoft.com/en-us/download/details.aspx?id=47345).</span><span class="sxs-lookup"><span data-stu-id="41c1f-108">You can also download the UCMA 5 SDK, which includes the runtime, here: [UCMA 5.0 SDK](https://www.microsoft.com/en-us/download/details.aspx?id=47345).</span></span>
  
<span data-ttu-id="41c1f-109">Sie können das SEFAUtil-Tool in einem beliebigen Front-End-Pool in Ihrer Bereitstellung ausführen.</span><span class="sxs-lookup"><span data-stu-id="41c1f-109">You can run the SEFAUtil tool in any Front End pool in your deployment.</span></span> <span data-ttu-id="41c1f-110">Um das SEFAUtil-Tool ausführen zu können, müssen Sie die Schritte 1, 2 und 3 im Skype for Business-Bereitstellungs-Assistenten auf dem vertrauenswürdigen Anwendungs Computer ausführen.</span><span class="sxs-lookup"><span data-stu-id="41c1f-110">To run the SEFAUtil tool you must run Steps 1, 2, and 3 from the Skype for Business Deployment Wizard on the Trusted Application Computer.</span></span> <span data-ttu-id="41c1f-111">SEFAUtil erfordert das vorhanden sein des lokalen Konfigurationsspeichers sowie ein Zertifikat.</span><span class="sxs-lookup"><span data-stu-id="41c1f-111">SEFAUtil requires the local configuration store to be present, as well as a certificate.</span></span>
  
> [!NOTE]
> <span data-ttu-id="41c1f-112">Weitere Informationen zum Ausführen von SEFAUtil finden Sie im Blog Artikel "so wird es[gemacht: SEFAUtil läuft?](https://go.microsoft.com/fwlink/?LinkId=278940)".</span><span class="sxs-lookup"><span data-stu-id="41c1f-112">For more details about running SEFAUtil, see the  blog article, "[How to get SEFAutil running?](https://go.microsoft.com/fwlink/?LinkId=278940)".</span></span> 
  
### <a name="to-deploy-sefautil"></a><span data-ttu-id="41c1f-113">So stellen Sie das SEFAUtil-Tool bereit</span><span class="sxs-lookup"><span data-stu-id="41c1f-113">To deploy SEFAUtil</span></span>

1. <span data-ttu-id="41c1f-114">Melden Sie sich bei dem Computer an, auf dem die Skype for Business Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe oder mit den erforderlichen Benutzerrechten installiert ist, wie unter **Delegieren von Setup Berechtigungen**beschrieben.</span><span class="sxs-lookup"><span data-stu-id="41c1f-114">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="41c1f-115">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="41c1f-115">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="41c1f-116">Das SEFAUtil-Tool kann nur auf einem Computer ausgeführt werden, der zu einem vertrauenswürdigen Anwendungspool gehört.</span><span class="sxs-lookup"><span data-stu-id="41c1f-116">The SEFAUtil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="41c1f-117">Falls erforderlich, definieren Sie einen vertrauenswürdigen Anwendungspool für den Front-End-Pool, in dem Sie SEFAUtil ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="41c1f-117">If needed, define a trusted application pool for the Front End pool where you plan to run SEFAUtil.</span></span> <span data-ttu-id="41c1f-118">Führen Sie an der Eingabeaufforderung folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="41c1f-118">At the command line, run:</span></span>
    
   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```
    > [!NOTE]
    > <span data-ttu-id="41c1f-119">Pool-FQDN: der FQDN des Servers oder Pools, der die SEFAUtil-Anwendung hosten soll (in der Regel ein Skype for Business-Front-End-Server oder-Pool).</span><span class="sxs-lookup"><span data-stu-id="41c1f-119">Pool FQDN: The FQDN of the server or pool that will host the SEFAUtil application (usually a Skype for Business Front End server or pool).</span></span>
    > <span data-ttu-id="41c1f-120">Pool Registrar FQDN: der FQDN des Skype for Business-Front-End-Servers oder-Pools, der diesem Anwendungspool zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="41c1f-120">Pool Registrar FQDN: The FQDN of the Skype for Business Front End server or pool associated with this application pool.</span></span>
    > <span data-ttu-id="41c1f-121">Pool Website: die Website-ID der Website, auf der dieser Pool verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="41c1f-121">Pool Site: The Site ID of the site on which this pool is homed.</span></span>

4. <span data-ttu-id="41c1f-p105">Definieren Sie das SEFAUtil-Tool als eine vertrauenswürdige Anwendung. Führen Sie an der Eingabeaufforderung folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="41c1f-p105">Define the SEFAUtil tool as a trusted application. At the command line, run:</span></span>
    
   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > <span data-ttu-id="41c1f-124">Sie können ggf. einen anderen Port verwenden.</span><span class="sxs-lookup"><span data-stu-id="41c1f-124">You can use a different port if needed.</span></span> 
  
5. <span data-ttu-id="41c1f-p106">Aktivieren Sie die Topologie mit Ihren Änderungen. Führen Sie an der Eingabeaufforderung folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="41c1f-p106">Enable the topology with your changes. At the command line, run:</span></span>
    
   ```powershell
   Enable-CsTopology
   ```

6. <span data-ttu-id="41c1f-127">Wenn Sie dies noch nicht getan haben, laden Sie die Skype for Business Server-Version des SEFAUtil-Tools von [diesem Speicherort](https://www.microsoft.com/en-us/download/details.aspx?id=52631)herunter, und installieren Sie Sie in dem vertrauenswürdigen Anwendungspool, den Sie in Schritt 3 erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="41c1f-127">If you haven't already, download the Skype for Business Server version of the SEFAUtil tool from [this location](https://www.microsoft.com/en-us/download/details.aspx?id=52631), and install it on the trusted application pool you created in step 3.</span></span>
    
7. <span data-ttu-id="41c1f-128">Gehen Sie wie folgt vor, um sicherzustellen, dass Ihr SEFAUtil-Tool korrekt ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="41c1f-128">Verify that the SEFAUtil tool is running correctly, as follows:</span></span> 
    
    <span data-ttu-id="41c1f-129">a.</span><span class="sxs-lookup"><span data-stu-id="41c1f-129">a.</span></span> <span data-ttu-id="41c1f-130">Führen Sie das Tool an der Windows-Eingabeaufforderung mit Administratorberechtigungen aus, um die Anrufweiterleistungseinstellungen eines Benutzers in Ihrer Bereitstellung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="41c1f-130">Run the tool from the Windows command prompt with administrator privileges to display the call forwarding settings of a user in your deployment.</span></span>
    
    <span data-ttu-id="41c1f-131">b.</span><span class="sxs-lookup"><span data-stu-id="41c1f-131">b.</span></span> <span data-ttu-id="41c1f-132">Zeigen Sie die Anrufweiterleitungseinstellungen eines Benutzers an.</span><span class="sxs-lookup"><span data-stu-id="41c1f-132">Display the call forwarding settings of a user.</span></span> <span data-ttu-id="41c1f-133">Führen Sie an der Eingabeaufforderung folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="41c1f-133">At the command line, run:</span></span>
    
   ```console
   SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
   ```

<span data-ttu-id="41c1f-134">Die Anrufweiterleitungseinstellungen für den Benutzer werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="41c1f-134">The call forwarding settings for the user will be displayed.</span></span>
    

