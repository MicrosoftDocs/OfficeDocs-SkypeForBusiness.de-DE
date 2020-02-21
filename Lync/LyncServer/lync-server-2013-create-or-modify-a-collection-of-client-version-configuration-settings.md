---
title: Erstellen oder Ändern einer Auflistung von Konfigurationseinstellungen für Clientversionen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of client version configuration settings
ms:assetid: 4e6faffd-a36f-40f1-8734-78d84b7df921
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898477(v=OCS.15)
ms:contentKeyID: 50873757
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6851a332b0b2c33d769328a0656f206d5f7d271c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180112"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-client-version-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="c19ba-102">Erstellen oder Ändern einer Auflistung von Konfigurationseinstellungen für Clientversionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c19ba-102">Create or modify a collection of client version configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c19ba-103">_**Letztes Änderungsstand des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="c19ba-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="c19ba-104">Konfigurationseinstellungen für Clientversionen werden verwendet, um die Client Versionskontrolle zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="c19ba-104">Client version configuration settings are used to turn client version control on or off.</span></span> <span data-ttu-id="c19ba-105">Die Konfiguration der globalen Client Version wird mit lync Server installiert und dient zum Aktivieren oder Deaktivieren der Client Versionskontrolle für die gesamte Server Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="c19ba-105">The global client version configuration installs with Lync Server and is used to enable or disable client version control for the entire server deployment.</span></span> <span data-ttu-id="c19ba-106">Sie können auch Konfigurationseinstellungen für Clientversionen für einzelne Websites konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c19ba-106">You can also configure client version configuration settings for individual sites.</span></span> <span data-ttu-id="c19ba-107">Sie können Client Versions Konfigurationseinstellungen in lync Server 2013 Systemsteuerung oder in lync Server 2013 Verwaltungsshell erstellen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="c19ba-107">You can create or modify client version configuration settings from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="c19ba-108">Da anonyme Benutzer keinem Benutzer, Standort oder Dienst zugeordnet sind, unterliegen anonyme Benutzer ausschließlich globalen Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="c19ba-108">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>



</div>

<div>

## <a name="to-create-or-modify-client-version-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="c19ba-109">So erstellen oder ändern Sie Konfigurationseinstellungen für Clientversionen mithilfe von lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="c19ba-109">To create or modify client version configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="c19ba-110">Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="c19ba-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c19ba-111">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="c19ba-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c19ba-112">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c19ba-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c19ba-113">Klicken Sie in der linken Navigationsleiste auf **Clients**, und klicken Sie dann auf die Navigationsschaltfläche **Client Versions Konfiguration** .</span><span class="sxs-lookup"><span data-stu-id="c19ba-113">In the left navigation bar, click **Clients**, and then click the **Client Version Configuration** navigation button.</span></span>

4.  <span data-ttu-id="c19ba-114">Führen Sie auf der Seite **Client Versions Konfiguration** die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="c19ba-114">On the **Client Version Configuration** page, do the following:</span></span>
    
      - <span data-ttu-id="c19ba-115">Um eine neue Konfiguration zu erstellen, klicken Sie auf **neu**, wählen Sie einen Standort aus, klicken Sie auf **OK** Name, und aktualisieren Sie die Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="c19ba-115">To create a new configuration, click **New**, select a site, click **OK** name, and update the settings.</span></span>
    
      - <span data-ttu-id="c19ba-116">Um eine Konfiguration zu ändern, wählen Sie die Konfiguration aus, klicken Sie auf **Bearbeiten**, klicken Sie auf **Details anzeigen**, und nehmen Sie Änderungen an den Einstellungen vor.</span><span class="sxs-lookup"><span data-stu-id="c19ba-116">To modify a configuration, select the configuration, click **Edit**, click **Show details**, and make changes to the settings.</span></span>

</div>

<div>

## <a name="creating-or-modifying-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c19ba-117">Erstellen oder Ändern von Konfigurationseinstellungen für Client Versionen mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="c19ba-117">Creating or Modifying Client Version Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="c19ba-118">Sie können Konfigurationseinstellungen für Clientversionen mithilfe des **New-CsClientVersionConfiguration-** Cmdlets erstellen und diese mithilfe des Cmdlets " **CsClientVersionConfiguration** " ändern.</span><span class="sxs-lookup"><span data-stu-id="c19ba-118">You can create client version configuration settings by using the **New-CsClientVersionConfiguration** cmdlet, and modify them by using the **Set-CsClientVersionConfiguration** cmdlet.</span></span> <span data-ttu-id="c19ba-119">Diese Cmdlets können entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c19ba-119">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="c19ba-120">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="c19ba-120">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-collection-of-client-version-configuration-settings"></a><span data-ttu-id="c19ba-121">So erstellen Sie eine neue Auflistung von Konfigurationseinstellungen für Clientversionen</span><span class="sxs-lookup"><span data-stu-id="c19ba-121">To create a new collection of client version configuration settings</span></span>

  - <span data-ttu-id="c19ba-122">Mit dem folgenden Befehl wird eine neue Auflistung von Client Versions-Konfigurationseinstellungen erstellt, die auf den Standort "Redmond" angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="c19ba-122">The following command creates a new collection of client version configuration settings applied to the Redmond site.</span></span> <span data-ttu-id="c19ba-123">In diesem Beispiel ist die Client Versionsverwaltung für den Standort "Redmond" deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="c19ba-123">In this example, client versioning is disabled for the Redmond site.</span></span>
    
        New-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $False

</div>

<div>

## <a name="to-enable-client-versioning-for-a-site"></a><span data-ttu-id="c19ba-124">So aktivieren Sie die Client Versionsverwaltung für einen Standort</span><span class="sxs-lookup"><span data-stu-id="c19ba-124">To enable client versioning for a site</span></span>

  - <span data-ttu-id="c19ba-125">Mit diesem Befehl wird die Client Versionsverwaltung für den Standort "Redmond" aktiviert.</span><span class="sxs-lookup"><span data-stu-id="c19ba-125">This command enables client versioning for the Redmond site.</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<div>

## <a name="to-disable-client-versioning-throughout-the-organization"></a><span data-ttu-id="c19ba-126">So deaktivieren Sie die Client Versionsverwaltung in der gesamten Organisation</span><span class="sxs-lookup"><span data-stu-id="c19ba-126">To disable client versioning throughout the organization</span></span>

  - <span data-ttu-id="c19ba-127">In diesem Beispiel ist die Client Versionsverwaltung für alle Client Versions Konfigurationseinstellungen deaktiviert, die in der Organisation verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c19ba-127">In this example, client versioning is disabled for all the client version configuration settings in use in the organization.</span></span>
    
        Get-CsClientVersionConfiguration | Set-CsClientVersionConfiguration  -Enabled $False

</div>

<span data-ttu-id="c19ba-128">Ausführliche Informationen finden Sie im Hilfethema zu den Cmdlets [New-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg399029(v=OCS.15)) und [CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg398623(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="c19ba-128">For details, see the Help topic for the [New-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg399029(v=OCS.15)) and [Set-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg398623(v=OCS.15)) cmdlets.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

