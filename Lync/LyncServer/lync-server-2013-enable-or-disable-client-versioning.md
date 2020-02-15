---
title: 'Lync Server 2013: Aktivieren oder Deaktivieren der Client Versionsverwaltung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable client versioning
ms:assetid: 33a98cb9-a979-4bb6-afb2-512f601d7ac5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898475(v=OCS.15)
ms:contentKeyID: 50873755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d86fc41847485cbe797da9e9c9ace4a0a8794280
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042542"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-client-versioning-in-lync-server-2013"></a><span data-ttu-id="fe737-102">Aktivieren oder Deaktivieren der Client Versionsverwaltung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe737-102">Enable or disable client versioning in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe737-103">_**Letztes Änderungsstand des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="fe737-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="fe737-104">Konfigurationseinstellungen für Clientversionen werden verwendet, um die Client Versionskontrolle entweder global oder für bestimmte Websites ein-oder auszuschalten.</span><span class="sxs-lookup"><span data-stu-id="fe737-104">Client version configuration settings are used to turn client version control on or off, either globally or for particular sites.</span></span> <span data-ttu-id="fe737-105">Die Konfiguration der globalen Client Version wird mit lync Server 2013 installiert und dient zum Aktivieren oder Deaktivieren der Client Versionskontrolle für die gesamte Server Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="fe737-105">The global client version configuration installs with Lync Server 2013 and is used to enable or disable client version control for the entire server deployment.</span></span> <span data-ttu-id="fe737-106">Wenn die globale Konfiguration aktiviert ist, werden alle clientversionsrichtlinien, die Sie in Kraft setzen, wirksam, wenn sich Benutzer anmelden.</span><span class="sxs-lookup"><span data-stu-id="fe737-106">When the global configuration is enabled, any client version policies you have in place will take effect when users attempt to log on.</span></span> <span data-ttu-id="fe737-107">Sie können die Konfiguration der globalen Client Version deaktivieren, wenn keine Client Versionskontrolle ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="fe737-107">You can disable the global client version configuration if you do not want any client version control to occur.</span></span> <span data-ttu-id="fe737-108">Sie können die Client Versionsverwaltung in lync Server 2013 Systemsteuerung oder lync Server 2013 Verwaltungsshell aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="fe737-108">You can enable or disable client versioning from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fe737-109">Da anonyme Benutzer keinem Benutzer, Standort oder Dienst zugeordnet sind, unterliegen anonyme Benutzer ausschließlich globalen Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="fe737-109">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-client-versioning-by-using-lync-server-control-panel"></a><span data-ttu-id="fe737-110">So aktivieren oder deaktivieren Sie die Client Versionsverwaltung mithilfe von lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="fe737-110">To enable or disable client versioning by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="fe737-111">Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="fe737-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="fe737-112">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="fe737-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="fe737-113">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="fe737-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="fe737-114">Klicken Sie in der linken Navigationsleiste auf **Clients**, und klicken Sie dann auf die Navigationsschaltfläche **Client Versions Konfiguration** .</span><span class="sxs-lookup"><span data-stu-id="fe737-114">In the left navigation bar, click **Clients**, and then click the **Client Version Configuration** navigation button.</span></span>

4.  <span data-ttu-id="fe737-115">Gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="fe737-115">Do the following:</span></span>
    
      - <span data-ttu-id="fe737-116">Um die Client Versionsverwaltung Global zu aktivieren oder zu deaktivieren, doppelklicken Sie auf die **globale** Konfiguration, und ändern Sie dann die Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="fe737-116">To globally enable or disable client versioning, double-click the **Global** configuration, and then modify the settings.</span></span>
    
      - <span data-ttu-id="fe737-117">Klicken Sie auf **neu**, wählen Sie den Standort aus, klicken Sie auf **OK**, und ändern Sie dann die Einstellungen für die Website, um die Client Versionsverwaltung für eine bestimmte Website zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="fe737-117">To enable or disable client versioning for a particular site, click **New**, select the site, click **OK**, and then modify the settings for the site.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-client-versioning-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="fe737-118">Aktivieren oder Deaktivieren der Client Versionsverwaltung mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="fe737-118">Enabling or Disabling Client Versioning by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="fe737-119">Sie können die Client Versionsverwaltung mithilfe des Cmdlets " **CsClientVersionConfiguration** " aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="fe737-119">You can enable or disable client versioning by using the **Set-CsClientVersionConfiguration** cmdlet.</span></span> <span data-ttu-id="fe737-120">Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="fe737-120">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="fe737-121">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="fe737-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-client-versioning"></a><span data-ttu-id="fe737-122">So aktivieren Sie die Client Versionsverwaltung</span><span class="sxs-lookup"><span data-stu-id="fe737-122">To enable client versioning</span></span>

  - <span data-ttu-id="fe737-123">Sie können die Client Versionsverwaltung aktivieren, indem Sie die **Enabled** -Eigenschaft auf true ($true) festlegen.</span><span class="sxs-lookup"><span data-stu-id="fe737-123">You can enable client versioning by setting the **Enabled** property to True ($True).</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<div>

## <a name="to-disable-client-versioning"></a><span data-ttu-id="fe737-124">So deaktivieren Sie die Client Versionsverwaltung</span><span class="sxs-lookup"><span data-stu-id="fe737-124">To disable client versioning</span></span>

  - <span data-ttu-id="fe737-125">Sie können die Client Versionsverwaltung deaktivieren, indem Sie die **Enabled** -Eigenschaft auf false ($false) festlegen.</span><span class="sxs-lookup"><span data-stu-id="fe737-125">You can disable client versioning by setting the **Enabled** property to False ($False).</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<span data-ttu-id="fe737-126">Ausführliche Informationen finden Sie im Hilfethema zum Cmdlet " [CsClientVersionConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionConfiguration) ".</span><span class="sxs-lookup"><span data-stu-id="fe737-126">For details, see the Help topic for the [Set-CsClientVersionConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

