---
title: 'Lync Server 2013: Anzeigen von Informationen zur Konfiguration der lync Phone Edition-Einstellungen'
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
ms.openlocfilehash: a58450b1d69ce757f40194d179606f332e152d7d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765636"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-lync-phone-edition-configuration-settings-information-in-lync-server-2013"></a><span data-ttu-id="6577b-102">Anzeigen von Informationen zu den lync Phone Edition-Konfigurationseinstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6577b-102">View Lync Phone Edition configuration settings information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6577b-103">_**Letztes Änderungsdatum des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="6577b-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="6577b-104">Sie können Konfigurationsinformationen zu Geräten, auf denen lync Phone Edition ausgeführt wird, anzeigen.</span><span class="sxs-lookup"><span data-stu-id="6577b-104">You can view configuration information about devices running Lync Phone Edition.</span></span> <span data-ttu-id="6577b-105">Die Informationen sind in Sammlungen gegliedert.</span><span class="sxs-lookup"><span data-stu-id="6577b-105">The information is organized into collections.</span></span> <span data-ttu-id="6577b-106">Wenn Sie lync Server installieren, erhalten Sie eine Sammlung von lync Phone Edition-Einstellungen, die für alle Geräte gelten, die lync Phone Edition in Ihrer Bereitstellung ausführen.</span><span class="sxs-lookup"><span data-stu-id="6577b-106">When you install Lync Server, you get a collection of Lync Phone Edition settings that apply to all the devices running Lync Phone Edition in your deployment.</span></span> <span data-ttu-id="6577b-107">Sie können auch neue Sammlungen von Einstellungen für eine bestimmte Website erstellen.</span><span class="sxs-lookup"><span data-stu-id="6577b-107">You can also create new collections of settings for a specific site.</span></span> <span data-ttu-id="6577b-108">Websiteeinstellungen haben Vorrang vor globalen Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="6577b-108">Site settings take precedence over global settings.</span></span> <span data-ttu-id="6577b-109">Jede Sammlung von Einstellungen besteht aus einem Namen, dem Bereich (Global oder Website), SIP-Sicherheitseinstellung, Protokollierungsstufe, Sprachdienst Qualität (QoS)-Ebene, Festlegung der Telefonsperre und Details der Telefonsperre, also der Mindestlänge der persönlichen Identifikations Sperre Nummer (PIN) und Zeit, bevor sich das Telefon selbst sperrt.</span><span class="sxs-lookup"><span data-stu-id="6577b-109">Each collection of settings consists of a name, the scope (global or site), SIP security setting, logging level, voice quality of service (QoS) level, phone-lock setting, and phone-lock details, that is, the minimum length of the unlock personal identification number (PIN) and time before the phone locks itself.</span></span>

<div>

## <a name="to-view-configuration-information-about-devices-running-lync-phone-edition"></a><span data-ttu-id="6577b-110">So zeigen Sie Konfigurationsinformationen zu Geräten mit lync Phone Edition an</span><span class="sxs-lookup"><span data-stu-id="6577b-110">To view configuration information about devices running Lync Phone Edition</span></span>

1.  <span data-ttu-id="6577b-111">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="6577b-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6577b-112">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="6577b-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6577b-113">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="6577b-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6577b-114">Klicken Sie in der linken Navigationsleiste auf **Clients**, und klicken Sie dann auf die Navigationsschaltfläche **Gerätekonfiguration** .</span><span class="sxs-lookup"><span data-stu-id="6577b-114">In the left navigation bar, click **Clients**, and then click the **Device Configuration** navigation button.</span></span>

4.  <span data-ttu-id="6577b-115">Klicken Sie auf der Seite **Device Configuration** auf die Sammlung von Einstellungen, über die Sie Informationen anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="6577b-115">On the **Device Configuration** page, click the collection of settings you want to view information about.</span></span> <span data-ttu-id="6577b-116">Der Name, der Bereich, die SIP-Sicherheitseinstellung, die sprach Qualitätsstufe und die Einstellung der Telefonsperre sind auf der Hauptseite aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="6577b-116">The name, scope, SIP security setting, voice quality level, and phone lock setting are listed on the main page.</span></span> <span data-ttu-id="6577b-117">Klicken Sie auf das Menü **Bearbeiten** , und klicken Sie dann auf **Details anzeigen**, um die Details für Protokollierungsstufe und Telefonsperre anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="6577b-117">To view the logging level and phone lock details, click the **Edit** menu, and then click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-lync-phone-edition-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="6577b-118">Anzeigen von Informationen zur lync Phone Edition-Konfiguration mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="6577b-118">Viewing Lync Phone Edition Configuration Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="6577b-119">Sie können die lync Phone Edition-Konfigurationseinstellungen mithilfe der lync Server-Verwaltungsshell und dem Cmdlet **Get-CsUCPhoneConfiguration** anzeigen.</span><span class="sxs-lookup"><span data-stu-id="6577b-119">You can view Lync Phone Edition configuration settings by using Lync Server Management Shell and the **Get-CsUCPhoneConfiguration** cmdlet.</span></span> <span data-ttu-id="6577b-120">Sie können dieses Cmdlet in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="6577b-120">You can run this cmdlet can from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="6577b-121">Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="6577b-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-lync-phone-edition-configuration-information"></a><span data-ttu-id="6577b-122">So zeigen Sie die lync Phone Edition-Konfigurationsinformationen an</span><span class="sxs-lookup"><span data-stu-id="6577b-122">To view Lync Phone Edition configuration information</span></span>

  - <span data-ttu-id="6577b-123">Wenn Sie Informationen zu allen ihren lync Phone Edition-Konfigurationseinstellungen anzeigen möchten, geben Sie den folgenden Befehl in der lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="6577b-123">To view information about all your Lync Phone Edition configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsUCPhoneConfiguration
    
    <span data-ttu-id="6577b-124">Der Befehl gibt Informationen ähnlich der folgenden zurück:</span><span class="sxs-lookup"><span data-stu-id="6577b-124">The command returns information similar to the following:</span></span>
    
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

<span data-ttu-id="6577b-125">Ausführliche Informationen finden Sie unter [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).</span><span class="sxs-lookup"><span data-stu-id="6577b-125">For details, see [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6577b-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6577b-126">See Also</span></span>


[<span data-ttu-id="6577b-127">Erstellen oder Ändern einer Sammlung von lync Phone Edition-Konfigurationseinstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6577b-127">Create or modify a collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md)  
[<span data-ttu-id="6577b-128">Löschen einer vorhandenen Sammlung von lync Phone Edition-Konfigurationseinstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6577b-128">Delete an existing collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[<span data-ttu-id="6577b-129">Konfigurieren von Sicherheitseinstellungen für lync Phone Edition in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6577b-129">Configure security settings for Lync Phone Edition in Lync Server 2013</span></span>](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[<span data-ttu-id="6577b-130">Erzwingen der Telefon Sperrung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6577b-130">Enforce phone locking in Lync Server 2013</span></span>](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

