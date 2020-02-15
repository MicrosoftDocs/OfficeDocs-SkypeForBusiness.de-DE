---
title: 'Lync Server 2013: Informationen zur lync Phone Edition-Konfigurationseinstellungen anzeigen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View Lync Phone Edition configuration settings information
ms:assetid: 15f94478-651f-4063-9918-6a059f98df16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687976(v=OCS.15)
ms:contentKeyID: 49733564
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 509bc25e6466e4e6f90271645b2a3a8ff271bd84
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050957"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-lync-phone-edition-configuration-settings-information-in-lync-server-2013"></a><span data-ttu-id="f1e48-102">Anzeigen von Informationen zu lync Phone Edition Konfigurationseinstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1e48-102">View Lync Phone Edition configuration settings information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1e48-103">_**Letztes Änderungsstand des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="f1e48-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="f1e48-104">Sie können Konfigurationsinformationen zu Geräten anzeigen, auf denen lync Phone Edition ausführt.</span><span class="sxs-lookup"><span data-stu-id="f1e48-104">You can view configuration information about devices running Lync Phone Edition.</span></span> <span data-ttu-id="f1e48-105">Die Informationen sind in Auflistungen angeordnet.</span><span class="sxs-lookup"><span data-stu-id="f1e48-105">The information is organized into collections.</span></span> <span data-ttu-id="f1e48-106">Wenn Sie lync Server installieren, erhalten Sie eine Sammlung von lync Phone Edition-Einstellungen, die für alle Geräte gelten, auf denen lync Phone Edition in Ihrer Bereitstellung ausführt.</span><span class="sxs-lookup"><span data-stu-id="f1e48-106">When you install Lync Server, you get a collection of Lync Phone Edition settings that apply to all the devices running Lync Phone Edition in your deployment.</span></span> <span data-ttu-id="f1e48-107">Sie können auch neuen Auflistungen von Einstellungen für einen bestimmten Standort erstellen.</span><span class="sxs-lookup"><span data-stu-id="f1e48-107">You can also create new collections of settings for a specific site.</span></span> <span data-ttu-id="f1e48-108">Standorteinstellungen haben Vorrang vor globalen Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="f1e48-108">Site settings take precedence over global settings.</span></span> <span data-ttu-id="f1e48-109">Jede Auflistung von Einstellungen besteht aus einem Namen, dem Bereich (global oder Standort), der SIP-Sicherheitseinstellung, dem Protokolliergrad, der VoIP-Dienstqualitätsebene, der Telefonsperreinstellung und Details zur Telefonsperre, d. h., die Mindestlänge der PIN zum Entsperren und die Zeit bis zur Sperrung des Telefons.</span><span class="sxs-lookup"><span data-stu-id="f1e48-109">Each collection of settings consists of a name, the scope (global or site), SIP security setting, logging level, voice quality of service (QoS) level, phone-lock setting, and phone-lock details, that is, the minimum length of the unlock personal identification number (PIN) and time before the phone locks itself.</span></span>

<div>

## <a name="to-view-configuration-information-about-devices-running-lync-phone-edition"></a><span data-ttu-id="f1e48-110">So zeigen Sie Konfigurationsinformationen zu Geräten an, auf denen lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="f1e48-110">To view configuration information about devices running Lync Phone Edition</span></span>

1.  <span data-ttu-id="f1e48-111">Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="f1e48-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f1e48-112">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f1e48-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f1e48-113">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f1e48-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f1e48-114">Klicken Sie in der linken Navigationsleiste auf **Clients** und dann auf die Navigationsschaltfläche **Gerätekonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="f1e48-114">In the left navigation bar, click **Clients**, and then click the **Device Configuration** navigation button.</span></span>

4.  <span data-ttu-id="f1e48-p103">Klicken Sie auf der Seite **Gerätekonfiguration** auf die Auflistung von Einstellungen, zu der Sie Informationen anzeigen möchten. Der Name, der Bereich, die SIP-Sicherheitseinstellung, die VoIP-Qualitätsebene und die Telefonsperreinstellung werden auf der Hauptseite aufgeführt. Zum Anzeigen des Protokolliergrads und der Details zur Telefonsperre klicken Sie auf das Menü **Bearbeiten** und dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="f1e48-p103">On the **Device Configuration** page, click the collection of settings you want to view information about. The name, scope, SIP security setting, voice quality level, and phone lock setting are listed on the main page. To view the logging level and phone lock details, click the **Edit** menu, and then click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-lync-phone-edition-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f1e48-118">Anzeigen von lync Phone Edition-Konfigurationsinformationen mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="f1e48-118">Viewing Lync Phone Edition Configuration Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="f1e48-119">Sie können lync Phone Edition-Konfigurationseinstellungen mithilfe von lync Server-Verwaltungsshell und dem Cmdlet **Get-CsUCPhoneConfiguration** anzeigen.</span><span class="sxs-lookup"><span data-stu-id="f1e48-119">You can view Lync Phone Edition configuration settings by using Lync Server Management Shell and the **Get-CsUCPhoneConfiguration** cmdlet.</span></span> <span data-ttu-id="f1e48-120">Sie können dieses Cmdlet in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="f1e48-120">You can run this cmdlet can from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="f1e48-121">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="f1e48-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-lync-phone-edition-configuration-information"></a><span data-ttu-id="f1e48-122">So zeigen Sie lync Phone Edition-Konfigurationsinformationen an</span><span class="sxs-lookup"><span data-stu-id="f1e48-122">To view Lync Phone Edition configuration information</span></span>

  - <span data-ttu-id="f1e48-123">Wenn Sie Informationen zu allen lync Phone Edition-Konfigurationseinstellungen anzeigen möchten, geben Sie den folgenden Befehl in das lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="f1e48-123">To view information about all your Lync Phone Edition configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsUCPhoneConfiguration
    
    <span data-ttu-id="f1e48-124">Der Befehl gibt ähnliche Informationen wie die Folgenden zurück:</span><span class="sxs-lookup"><span data-stu-id="f1e48-124">The command returns information similar to the following:</span></span>
    
        Identity             : Global
        CalendarPollInterval : 00:03:00
        EnforcePhoneLock     : True
        PhoneLockTimeout     : 00:10:00
        MinPhonePinLength    : 6
        SIPSecurityMode      : High
        VoiceDiffServTag     : 40
        Voice8021p           : 0
        LoggingLevel         : Off

</div>

<span data-ttu-id="f1e48-125">Ausführliche Informationen finden Sie unter [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).</span><span class="sxs-lookup"><span data-stu-id="f1e48-125">For details, see [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f1e48-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f1e48-126">See Also</span></span>


[<span data-ttu-id="f1e48-127">Erstellen oder Ändern einer Sammlung von lync Phone Edition Konfigurationseinstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1e48-127">Create or modify a collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md)  
[<span data-ttu-id="f1e48-128">Löschen einer vorhandenen Sammlung von lync Phone Edition Konfigurationseinstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1e48-128">Delete an existing collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[<span data-ttu-id="f1e48-129">Konfigurieren von Sicherheitseinstellungen für lync Phone Edition in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1e48-129">Configure security settings for Lync Phone Edition in Lync Server 2013</span></span>](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[<span data-ttu-id="f1e48-130">Erzwingen der Telefonsperre in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1e48-130">Enforce phone locking in Lync Server 2013</span></span>](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

