---
title: 'Lync Server 2013: Anzeigen der Konfigurationseinstellungen für Clientversionen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View client version configuration settings
ms:assetid: c72df4e6-a889-4cb6-86f7-8334d7774c6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ923062(v=OCS.15)
ms:contentKeyID: 50675353
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9db03377f8f2fc880de61639f4eedc5b1c302d21
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847271"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-client-version-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="f9e3c-102">Anzeigen der Konfigurationseinstellungen für Clientversionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9e3c-102">View client version configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9e3c-103">_**Letztes Änderungsdatum des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="f9e3c-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="f9e3c-104">Client Version-Konfigurationseinstellungen werden verwendet, um die Client Versionskontrolle zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="f9e3c-104">Client version configuration settings are used to turn client version control on or off.</span></span> <span data-ttu-id="f9e3c-105">Die Konfiguration der globalen Client Version wird mit lync Server 2013 installiert und verwendet, um die Client Versionskontrolle für die gesamte Server Bereitstellung zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="f9e3c-105">The global client version configuration installs with Lync Server 2013 and is used to enable or disable client version control for the entire server deployment.</span></span> <span data-ttu-id="f9e3c-106">Wenn die globale Konfiguration aktiviert ist, werden alle von Ihnen eingerichteten clientversionsrichtlinien wirksam, wenn Benutzer versuchen, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="f9e3c-106">When the Global configuration is enabled, any client version policies you have in place will take effect when users attempt to log on.</span></span> <span data-ttu-id="f9e3c-107">Sie können die Konfigurationseinstellungen für Clientversionen in der lync Server 2013-Systemsteuerung oder in der lync Server 2013-Verwaltungsshell anzeigen.</span><span class="sxs-lookup"><span data-stu-id="f9e3c-107">You can view client version configuration settings from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f9e3c-108">Da anonyme Benutzer keinem Benutzer, Standort oder Dienst zugeordnet sind, unterliegen anonyme Benutzer ausschließlich globalen Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="f9e3c-108">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>



</div>

<div>

## <a name="to-view-client-version-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="f9e3c-109">So zeigen Sie die Konfigurationseinstellungen für Clientversionen mithilfe der lync Server-Systemsteuerung an</span><span class="sxs-lookup"><span data-stu-id="f9e3c-109">To view client version configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="f9e3c-110">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="f9e3c-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f9e3c-111">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f9e3c-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f9e3c-112">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f9e3c-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f9e3c-113">Klicken Sie in der linken Navigationsleiste auf **Clients**, und klicken Sie dann auf die Navigationsschaltfläche **Client Versions Konfiguration** .</span><span class="sxs-lookup"><span data-stu-id="f9e3c-113">In the left navigation bar, click **Clients**, and then click the **Client Version Configuration** navigation button.</span></span>

4.  <span data-ttu-id="f9e3c-114">Doppelklicken Sie auf den Namen der Client Versions Konfiguration, die Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="f9e3c-114">Double-click the name of the client version configuration you want to view.</span></span>

</div>

<div>

## <a name="viewing-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f9e3c-115">Anzeigen von Konfigurationseinstellungen für Client Versionen mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="f9e3c-115">Viewing Client Version Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="f9e3c-116">Sie können die Konfigurationseinstellungen für Clientversionen mit dem Cmdlet **Get-CsClientVersionConfiguration** anzeigen.</span><span class="sxs-lookup"><span data-stu-id="f9e3c-116">You can view client version configuration settings by using the **Get-CsClientVersionConfiguration** cmdlet.</span></span> <span data-ttu-id="f9e3c-117">Dieses Cmdlet kann entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f9e3c-117">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="f9e3c-118">Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="f9e3c-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-client-version-configuration-information"></a><span data-ttu-id="f9e3c-119">So zeigen Sie Client Versions Konfigurationsinformationen an</span><span class="sxs-lookup"><span data-stu-id="f9e3c-119">To view client version configuration information</span></span>

  - <span data-ttu-id="f9e3c-120">Wenn Sie Informationen zu allen Konfigurationseinstellungen Ihrer Client Version anzeigen möchten, geben Sie den folgenden Befehl in der lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="f9e3c-120">To view information about all your client version configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsClientVersionConfiguration
    
    <span data-ttu-id="f9e3c-121">Es werden etwa folgende Informationen zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="f9e3c-121">That will return information similar to this:</span></span>
    
        Identity      : Global
        DefaultAction : Allow
        DefaultURL    :
        Enabled       : True

</div>

<span data-ttu-id="f9e3c-122">Ausführliche Informationen finden Sie im Hilfethema zum Cmdlet [Get-CsClientVersionConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsClientVersionConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="f9e3c-122">For details, see the Help topic for the [Get-CsClientVersionConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsClientVersionConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

