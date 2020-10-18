---
title: 'Lync Server 2013: Verwenden von Cmdlets zum Rückgängigmachen der Domänenvorbereitung'
description: 'Lync Server 2013: Verwenden von Cmdlets zum Rückgängigmachen der Domänenvorbereitung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using cmdlets to reverse domain preparation
ms:assetid: 014dba5d-fcb3-44c9-9d63-ae0755276dac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398071(v=OCS.15)
ms:contentKeyID: 48183227
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d26cc97ee934ee959838f38f4e2f52f9bf89566
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580411"
---
# <a name="using-cmdlets-to-reverse-domain-preparation-for-lync-server-2013"></a><span data-ttu-id="40a04-103">Verwenden von Cmdlets zum Rückgängigmachen der Domänenvorbereitung für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="40a04-103">Using cmdlets to reverse domain preparation for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="40a04-104">_**Letztes Änderungsstand des Themas:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="40a04-104">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="40a04-105">Verwenden Sie das Cmdlet **Disable-CsAdDomain**, um die Domänenvorbereitung rückgängig zu machen.</span><span class="sxs-lookup"><span data-stu-id="40a04-105">Use the **Disable-CsAdDomain** cmdlet to reverse the domain preparation step.</span></span>

<div>

## <a name="to-use-cmdlets-to-reverse-domain-preparation"></a><span data-ttu-id="40a04-106">So machen Sie mithilfe von Cmdlets die Domänenvorbereitung rückgängig</span><span class="sxs-lookup"><span data-stu-id="40a04-106">To use cmdlets to reverse domain preparation</span></span>

1.  <span data-ttu-id="40a04-107">Melden Sie sich als Mitglied der Gruppe der Domänenadministratoren bei einem beliebigen Server an.</span><span class="sxs-lookup"><span data-stu-id="40a04-107">Log on to any server in the domain as a member of the Domain Admins group.</span></span>

2.  <span data-ttu-id="40a04-108">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="40a04-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="40a04-109">Ausführen</span><span class="sxs-lookup"><span data-stu-id="40a04-109">Run:</span></span>
    
        Disable-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-Force <SwitchParameter>] 
        [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>] 
    
    <span data-ttu-id="40a04-110">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="40a04-110">For example:</span></span>
    
        Disable-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.net -Force
    
    <span data-ttu-id="40a04-111">Wenn der Parameter Force vorhanden ist, wird die Domänenvorbereitung zurückgesetzt, auch wenn ein oder mehrere Front-End-Server oder A/V-Konferenzserver in der Domäne aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="40a04-111">If the Force parameter is present, domain preparation is rolled back, even if one or more Front End Servers or A/V Conferencing Servers in the domain are activated.</span></span> <span data-ttu-id="40a04-112">Wenn der Parameter Force nicht vorhanden ist, wird das Rollback der Domänenvorbereitung beendet, wenn alle Front-End-Server oder A/V-Konferenzserver in der Domäne aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="40a04-112">If the Force parameter is not present, domain preparation rollback is terminated if any Front End Servers or A/V Conferencing Servers in the domain are activated.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="40a04-113">Über den Parameter "GlobalSettingsDomainController" können Sie den Speicherort der globalen Einstellungen angeben.</span><span class="sxs-lookup"><span data-stu-id="40a04-113">The parameter GlobalSettingsDomainController allows you to indicate where global settings are stored.</span></span> <span data-ttu-id="40a04-114">Wenn Ihre Einstellungen im Systemcontainer gespeichert sind (dies ist bei Upgradebereitstellungen typisch, in denen die globalen Einstellungen nicht zum Konfigurationscontainer migriert wurden), definieren Sie einen Domänencontroller im Stammverzeichnis Ihrer Active Directory-Gesamtstruktur.</span><span class="sxs-lookup"><span data-stu-id="40a04-114">If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global setting migrated to the Configuration container), you define a domain controller in the root of your Active Directory forest.</span></span> <span data-ttu-id="40a04-115">Wenn sich die globalen Einstellungen im Konfigurationscontainer befinden (dies ist bei neuen Bereitstellungen oder Upgradebereitstellungen typisch, bei denen die Einstellungen zum Konfigurationscontainer migriert wurden), definieren Sie einen beliebigen Domänencontroller in der Gesamtstruktur.</span><span class="sxs-lookup"><span data-stu-id="40a04-115">If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest.</span></span> <span data-ttu-id="40a04-116">Wenn Sie diesen Parameter nicht angeben, geht das Cmdlet davon aus, dass die Einstellungen im Konfigurationscontainer gespeichert sind, und verweist auf einen beliebigen Domänencontroller in AD &nbsp; DS.</span><span class="sxs-lookup"><span data-stu-id="40a04-116">If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in AD&nbsp;DS.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="40a04-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="40a04-117">See Also</span></span>


[<span data-ttu-id="40a04-118">Ausführung der Domänenvorbereitung für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="40a04-118">Running domain preparation for Lync Server 2013</span></span>](lync-server-2013-running-domain-preparation.md)  


[<span data-ttu-id="40a04-119">Vorbereiten von Domänen für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="40a04-119">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

