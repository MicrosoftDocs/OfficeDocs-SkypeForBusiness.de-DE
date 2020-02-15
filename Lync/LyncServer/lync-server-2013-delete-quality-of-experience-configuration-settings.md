---
title: 'Lync Server 2013: Quality of Experience-Konfigurationseinstellungen löschen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete Quality of Experience configuration settings
ms:assetid: fd0c4c2f-3bfb-42cb-9b6a-f0f8d5aa9e81
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182613(v=OCS.15)
ms:contentKeyID: 48185954
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf0a313e80674a7eefd57320a5a30a9dd999fc81
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029236"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-quality-of-experience-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="3e0c1-102">Löschen von Konfigurationseinstellungen für die Quality of Experience in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e0c1-102">Delete Quality of Experience configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e0c1-103">_**Letztes Änderungsstand des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="3e0c1-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="3e0c1-p101">QoE (Quality of Experience)-Metriken dienen der Überwachung der Qualität von Audio- und Videoanrufen in Ihrer Organisation, z. B. der Anzahl der verloren gegangenen Netzwerkpakete, von Hintergrundgeräuschen und der Unterschiede bei Paketverzögerung (Jitter). Diese Metriken werden in einer Datenbank getrennt von anderen Daten (z. B. den Kommunikationsdatensätzen) gespeichert, sodass QoE unabhängig von anderen Datenaufzeichnungen aktiviert und deaktiviert werden kann.</span><span class="sxs-lookup"><span data-stu-id="3e0c1-p101">Quality of Experience (QoE) metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay). These metrics are stored in a database apart from other data (such as call detail records), which allows you to enable and disable QoE independent of other data recording.</span></span>

<span data-ttu-id="3e0c1-106">Wenn Sie Microsoft lync Server 2013 installieren, wird eine einzelne globale Auflistung von QoE-Konfigurationseinstellungen für Sie erstellt.</span><span class="sxs-lookup"><span data-stu-id="3e0c1-106">When you install Microsoft Lync Server 2013, a single, global collection of QoE configuration settings is created for you.</span></span> <span data-ttu-id="3e0c1-107">Administratoren können darüber hinaus Auflistungen mit benutzerdefinierten Einstellungen erstellen, die auf die einzelnen Standorte angewendet werden können.</span><span class="sxs-lookup"><span data-stu-id="3e0c1-107">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="3e0c1-108">Prinzipiell haben Einstellungen auf Standortebene Vorrang vor globalen Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="3e0c1-108">By design, settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="3e0c1-109">Wenn Sie Einstellungen auf Standortebene löschen, wird QoE auf dieser Website mithilfe der globalen Einstellungen verwaltet.</span><span class="sxs-lookup"><span data-stu-id="3e0c1-109">If you delete site-scoped settings, then QoE will be managed in that site by using the global settings.</span></span>

<span data-ttu-id="3e0c1-110">Beachten Sie, dass Sie auch die globalen Einstellungen löschen können.</span><span class="sxs-lookup"><span data-stu-id="3e0c1-110">Note that you can also “delete” the global settings.</span></span> <span data-ttu-id="3e0c1-111">Diese globalen Einstellungen werden jedoch tatsächlich nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="3e0c1-111">However, the global settings will not actually be removed.</span></span> <span data-ttu-id="3e0c1-112">Stattdessen werden alle Eigenschaften in dieser Auflistung auf die Standardwerte zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="3e0c1-112">Instead, all the properties in that collection will be reset to their default values.</span></span> <span data-ttu-id="3e0c1-113">Beispielsweise ist die Bereinigung standardmäßig in einer Auflistung von QoE-Konfigurationseinstellungen aktiviert.</span><span class="sxs-lookup"><span data-stu-id="3e0c1-113">For example, by default purging is enabled in a collection of QoE configuration settings.</span></span> <span data-ttu-id="3e0c1-114">Angenommen, Sie ändern die globalen Einstellungen, sodass die Löschung deaktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="3e0c1-114">Suppose you modify the global collection so that purging is disabled.</span></span> <span data-ttu-id="3e0c1-115">Wenn Sie später die globalen Einstellungen löschen, werden alle Eigenschaften auf ihre Standardwerte zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="3e0c1-115">If you later delete the global settings, all the properties will be reset to their default values.</span></span> <span data-ttu-id="3e0c1-116">Das bedeutet in diesem Fall, dass die Löschung wieder aktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="3e0c1-116">In this case, that means that purging will once again be enabled.</span></span>

<span data-ttu-id="3e0c1-117">Sie können QoE-Konfigurationseinstellungen mithilfe der lync Server-Systemsteuerung oder mithilfe des Cmdlets [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsQoEConfiguration) entfernen.</span><span class="sxs-lookup"><span data-stu-id="3e0c1-117">You can remove QoE configuration settings by using the Lync Server Control Panel or by using the [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsQoEConfiguration) cmdlet.</span></span>

<div>

## <a name="to-delete-qoe-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="3e0c1-118">So löschen Sie QoE-Konfigurationseinstellungen mithilfe von lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="3e0c1-118">To delete QoE configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="3e0c1-119">Melden Sie sich am Computer als Mitglied der RTCUniversalServerAdmins-Gruppe oder als Mitglied der CsVoiceAdministrator-, CsServerAdministrator-oder CsAdministrator-Rolle an.</span><span class="sxs-lookup"><span data-stu-id="3e0c1-119">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="3e0c1-120">Ausführliche Informationen finden Sie unter [Delegate Setup Permissions in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="3e0c1-120">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="3e0c1-121">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="3e0c1-121">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3e0c1-122">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3e0c1-122">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3e0c1-123">Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **QoE-Daten**.</span><span class="sxs-lookup"><span data-stu-id="3e0c1-123">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4.  <span data-ttu-id="3e0c1-124">Klicken Sie auf der Seite **Quality of Experience-Daten** auf die gewünschte Richtlinie, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="3e0c1-124">On the **Quality of Experience Data** page, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="3e0c1-125">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3e0c1-125">Click **OK**.</span></span>

</div>

<div>

## <a name="removing-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="3e0c1-126">Entfernen von QoE-Konfigurationseinstellungen mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="3e0c1-126">Removing QoE Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="3e0c1-127">Sie können QoE-Konfigurationseinstellungen mithilfe von Windows PowerShell und dem Cmdlet **Remove-CsQoEConfiguration** löschen.</span><span class="sxs-lookup"><span data-stu-id="3e0c1-127">You can delete QoE configuration settings by using Windows PowerShell and the **Remove-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="3e0c1-128">Sie können dieses Cmdlet entweder über die lync Server 2013 Management-Shell oder über eine Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="3e0c1-128">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="3e0c1-129">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="3e0c1-129">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-qoe-configuration-settings"></a><span data-ttu-id="3e0c1-130">So entfernen Sie eine angegebene Auflistung von QoE-Konfigurationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="3e0c1-130">To remove a specified collection of QoE configuration settings</span></span>

  - <span data-ttu-id="3e0c1-131">Mit diesem Befehl werden die QoE-Konfigurationseinstellungen entfernt, die auf den Standort "Redmond" angewendet wurden:</span><span class="sxs-lookup"><span data-stu-id="3e0c1-131">This command removes the QoE configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsQoEConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-of-the-qoe-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="3e0c1-132">So entfernen Sie alle QoE-Konfigurationseinstellungen, die auf den Website Bereich angewendet werden</span><span class="sxs-lookup"><span data-stu-id="3e0c1-132">To remove all of the QoE configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="3e0c1-133">Mit diesem Befehl werden alle QoE-Konfigurationseinstellungen entfernt, die auf den Standortbereich angewendet wurden:</span><span class="sxs-lookup"><span data-stu-id="3e0c1-133">This command removes all the QoE configuration settings applied to the site scope:</span></span>
    
        Get-CsQoEConfiguration -Filter "site:*" | Remove-CsQoEConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a><span data-ttu-id="3e0c1-134">So entfernen Sie alle QoE-Konfigurationseinstellungen, bei denen die QoE-Überwachung deaktiviert ist</span><span class="sxs-lookup"><span data-stu-id="3e0c1-134">To remove all of the QoE configuration settings where QoE monitoring is disabled</span></span>

  - <span data-ttu-id="3e0c1-135">Mit diesem Befehl werden alle QoE-Konfigurationseinstellungen entfernt, bei denen die QoE-Überwachung deaktiviert wurde:</span><span class="sxs-lookup"><span data-stu-id="3e0c1-135">This command removes all the QoE configuration settings where QoE monitoring has been disabled:</span></span>
    
        Get-CsQoEConfiguration | Where-Object {$_.EnableQoE -eq $False} | Remove-CsQoEConfiguration

</div>

<span data-ttu-id="3e0c1-136">Ausführliche Informationen finden Sie unter [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsQoEConfiguration).</span><span class="sxs-lookup"><span data-stu-id="3e0c1-136">For details, see [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsQoEConfiguration).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

