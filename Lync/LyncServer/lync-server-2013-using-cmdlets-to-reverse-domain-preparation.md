---
title: 'Lync Server 2013: Verwenden von Cmdlets zum Rückgängigmachen der Domänenvorbereitung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using cmdlets to reverse domain preparation
ms:assetid: 014dba5d-fcb3-44c9-9d63-ae0755276dac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398071(v=OCS.15)
ms:contentKeyID: 48183227
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b03ab3218a1568613731efe60eaa95b05a91ebc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847346"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-cmdlets-to-reverse-domain-preparation-for-lync-server-2013"></a><span data-ttu-id="6768a-102">Verwenden von Cmdlets zum Rückgängigmachen der Domänenvorbereitung für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6768a-102">Using cmdlets to reverse domain preparation for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6768a-103">_**Letztes Änderungsdatum des Themas:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="6768a-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="6768a-104">Verwenden Sie das Cmdlet **Disable-CsAdDomain** , um den Schritt zur Domänenvorbereitung umzukehren.</span><span class="sxs-lookup"><span data-stu-id="6768a-104">Use the **Disable-CsAdDomain** cmdlet to reverse the domain preparation step.</span></span>

<div>

## <a name="to-use-cmdlets-to-reverse-domain-preparation"></a><span data-ttu-id="6768a-105">So verwenden Sie Cmdlets zum Umkehren der Domänenvorbereitung</span><span class="sxs-lookup"><span data-stu-id="6768a-105">To use cmdlets to reverse domain preparation</span></span>

1.  <span data-ttu-id="6768a-106">Melden Sie sich bei einem beliebigen Server in der Domäne als Mitglied der Gruppe der Domänenadministratoren an.</span><span class="sxs-lookup"><span data-stu-id="6768a-106">Log on to any server in the domain as a member of the Domain Admins group.</span></span>

2.  <span data-ttu-id="6768a-107">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="6768a-107">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="6768a-108">Führen Sie folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="6768a-108">Run:</span></span>
    
        Disable-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-Force <SwitchParameter>] 
        [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>] 
    
    <span data-ttu-id="6768a-109">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6768a-109">For example:</span></span>
    
        Disable-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.net -Force
    
    <span data-ttu-id="6768a-110">Wenn der Parameter Force vorhanden ist, wird die Domänenvorbereitung zurückgesetzt, selbst wenn ein oder mehrere Front-End-Server oder A/V-Konferenzserver in der Domäne aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="6768a-110">If the Force parameter is present, domain preparation is rolled back, even if one or more Front End Servers or A/V Conferencing Servers in the domain are activated.</span></span> <span data-ttu-id="6768a-111">Wenn der Parameter Force nicht vorhanden ist, wird das Rollback zur Domänenvorbereitung beendet, wenn alle Front-End-Server oder A/V-Konferenzserver in der Domäne aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="6768a-111">If the Force parameter is not present, domain preparation rollback is terminated if any Front End Servers or A/V Conferencing Servers in the domain are activated.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6768a-112">Mit dem Parameter GlobalSettingsDomainController können Sie angeben, wo die globalen Einstellungen gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="6768a-112">The parameter GlobalSettingsDomainController allows you to indicate where global settings are stored.</span></span> <span data-ttu-id="6768a-113">Wenn Ihre Einstellungen im System Container gespeichert sind (typisch für Upgrade-Bereitstellungen, bei denen die globale Einstellung nicht zum Konfigurationscontainer migriert wurde), definieren Sie einen Domänencontroller im Stammverzeichnis Ihrer Active Directory-Gesamtstruktur.</span><span class="sxs-lookup"><span data-stu-id="6768a-113">If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global setting migrated to the Configuration container), you define a domain controller in the root of your Active Directory forest.</span></span> <span data-ttu-id="6768a-114">Wenn sich die globalen Einstellungen im Konfigurationscontainer befinden (dies ist bei neuen Bereitstellungen oder Upgradebereitstellungen typisch, bei denen die Einstellungen zum Konfigurationscontainer migriert wurden), definieren Sie einen beliebigen Domänencontroller in der Gesamtstruktur.</span><span class="sxs-lookup"><span data-stu-id="6768a-114">If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest.</span></span> <span data-ttu-id="6768a-115">Wenn Sie diesen Parameter nicht angeben, geht das Cmdlet davon aus, dass die Einstellungen im Konfigurationscontainer gespeichert sind und auf einen beliebigen Domänencontroller in&nbsp;AD DS verweisen.</span><span class="sxs-lookup"><span data-stu-id="6768a-115">If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in AD&nbsp;DS.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6768a-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6768a-116">See Also</span></span>


[<span data-ttu-id="6768a-117">Ausführen der Domänenvorbereitung für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6768a-117">Running domain preparation for Lync Server 2013</span></span>](lync-server-2013-running-domain-preparation.md)  


[<span data-ttu-id="6768a-118">Vorbereiten von Domänen für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6768a-118">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

