---
title: Konfigurieren der Dienstqualität auf Microsoft lync Phone Edition-Geräten
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Quality of Service on Microsoft Lync Phone Edition devices
ms:assetid: a6eb2620-a512-4ab6-bdfd-eb76be43bbfe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205137(v=OCS.15)
ms:contentKeyID: 48185004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a9f7f96e90aa07da193f9ffb714fc3437ba46cd8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839189"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-quality-of-service-on-microsoft-lync-phone-edition-devices-in-lync-server-2013"></a><span data-ttu-id="41eff-102">Konfigurieren der Dienstqualität auf Microsoft lync Phone Edition-Geräten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41eff-102">Configuring Quality of Service on Microsoft Lync Phone Edition devices in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41eff-103">_**Letztes Änderungsdatum des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="41eff-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="41eff-104">Obwohl QoS (Quality of Service) nicht standardmäßig für Geräte wie iPhones aktiviert ist, ist QoS standardmäßig für Geräte mit lync Phone Edition aktiviert.</span><span class="sxs-lookup"><span data-stu-id="41eff-104">Although Quality of Service (QoS) is not enabled by default for devices such as iPhones, QoS is enabled by default for devices running Lync Phone Edition.</span></span> <span data-ttu-id="41eff-105">(Diese Geräte werden gemeinhin als UC-oder Unified Communication-Telefone bezeichnet.) Führen Sie den folgenden Windows PowerShell-Befehl in der lync Server-Verwaltungsshell aus, um dies zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="41eff-105">(These devices are commonly referred to as UC or Unified Communication phones.) To verify this, run the following Windows PowerShell command from within the Lync Server Management Shell:</span></span>

    Get-CsUCPhoneConfiguration

<span data-ttu-id="41eff-106">Wenn Sie keine Änderungen an Ihren UC-Telefon Konfigurationseinstellungen vorgenommen haben, erhalten Sie wieder Informationen, die wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="41eff-106">If you have not made any changes to your UC phone configuration settings then you will get back information that looks like this:</span></span>

    Identity             : Global
    CalendarPollInterval : 00:03:00
    EnforcePhoneLock     : True
    PhoneLockTimeout     : 00:10:00
    MinPhonePinLength    : 6
    SIPSecurityMode      : High
    VoiceDiffServTag     : 40
    Voice8021p           : 0
    LoggingLevel         : Off

<span data-ttu-id="41eff-107">Für Quality of Service-Zwecke ist nur eine dieser Eigenschaften von Interesse: VoiceDiffServTag.</span><span class="sxs-lookup"><span data-stu-id="41eff-107">For Quality of Service purposes, only one of these properties is of interest: VoiceDiffServTag.</span></span> <span data-ttu-id="41eff-108">VoiceDiffServTag stellt den DSCP-Wert dar, der dem VoIP-Datenverkehr zugewiesen ist, der von einem lync Phone Edition-Gerät ausgeht.</span><span class="sxs-lookup"><span data-stu-id="41eff-108">The VoiceDiffServTag represents the DSCP value assigned to voice traffic emanating from a Lync Phone Edition device.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="41eff-109">Der Voice8021p-Parameter wird in lync Server 2013 nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="41eff-109">The Voice8021p parameter is no longer supported in Lync Server 2013.</span></span> <span data-ttu-id="41eff-110">Der Parameter ist nach wie vor aus Gründen der Abwärtskompatibilität mit Microsoft lync Server 2010 gültig. Sie hat jedoch keine Auswirkungen auf Geräte, die mit lync Server 2013 verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="41eff-110">The parameter is still valid for backward compatibility with Microsoft Lync Server 2010; however, it has no effect on devices used with Lync Server 2013.</span></span>



</div>

<span data-ttu-id="41eff-111">In den meisten Netzwerken sollten die Kennzeichnung von lync Phone Edition-Paketen mit einem VoiceDiffServTag von 40 keine Probleme verursachen.</span><span class="sxs-lookup"><span data-stu-id="41eff-111">In most networks, marking Lync Phone Edition packets with a VoiceDiffServTag of 40 should not cause any problems.</span></span> <span data-ttu-id="41eff-112">40 ist jedoch nicht der in der Regel für den Audioverkehr verwendete Wert; Stattdessen wird der Audioverkehr fast immer mit dem DSCP-Code 46 markiert.</span><span class="sxs-lookup"><span data-stu-id="41eff-112">However, 40 is not the value typically used for audio traffic; instead, audio traffic is almost always marked with the DSCP code 46.</span></span> <span data-ttu-id="41eff-113">Um die Konsistenz im gesamten Netzwerk zu gewährleisten, sollten Sie die VoiceDiffServTag-Eigenschaft Ihrer UC-Telefone in 46 ändern.</span><span class="sxs-lookup"><span data-stu-id="41eff-113">In order to maintain consistency throughout your network, you might want to change the VoiceDiffServTag property of your UC phones to 46.</span></span>

<span data-ttu-id="41eff-114">Dazu können Sie entweder Windows PowerShell oder die lync Server-Systemsteuerung verwenden.</span><span class="sxs-lookup"><span data-stu-id="41eff-114">To do that, you can use either Windows PowerShell or the Lync Server Control Panel.</span></span> <span data-ttu-id="41eff-115">Führen Sie den folgenden Befehl in der lync Server-Verwaltungsshell aus, um den VoiceDiffServTag-Wert mithilfe von Windows PowerShell zu ändern:</span><span class="sxs-lookup"><span data-stu-id="41eff-115">To modify the VoiceDiffServTag value by using Windows PowerShell, run the following command from within the Lync Server Management Shell:</span></span>

    Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

<span data-ttu-id="41eff-116">Mit dem vorhergehenden Befehl wird die globale Sammlung der UC-Telefon Konfigurationseinstellungen geändert.</span><span class="sxs-lookup"><span data-stu-id="41eff-116">The preceding command modifies the global collection of UC phone configuration settings.</span></span> <span data-ttu-id="41eff-117">Beachten Sie jedoch, dass die Einstellungen für UC-Telefone auch dem Website Bereich zugewiesen werden können.</span><span class="sxs-lookup"><span data-stu-id="41eff-117">Note, however, that UC phone settings can also be assigned to the site scope.</span></span> <span data-ttu-id="41eff-118">Wenn Sie die Einstellungen für die UC-Telefon Konfiguration im Website Bereich ändern möchten, müssen Sie die Websiteidentität angeben.</span><span class="sxs-lookup"><span data-stu-id="41eff-118">To modify UC phone configuration settings at the site scope, you must specify the site Identity.</span></span> <span data-ttu-id="41eff-119">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="41eff-119">For example:</span></span>

    Set-CsUCPhoneConfiguration -Identity "site:Redmond" -VoiceDiffServTag 46

<span data-ttu-id="41eff-120">Sie können auch den folgenden Befehl verwenden, um alle Ihre UC-Telefon Konfigurationseinstellungen gleichzeitig zu ändern:</span><span class="sxs-lookup"><span data-stu-id="41eff-120">You can also use the following command to simultaneously modify all your UC phone configuration settings:</span></span>

    Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

<span data-ttu-id="41eff-121">Wenn Sie diese Änderung lieber mithilfe der lync Server-Systemsteuerung vornehmen möchten, starten Sie die Systemsteuerung, und führen Sie dann das folgende Verfahren aus:</span><span class="sxs-lookup"><span data-stu-id="41eff-121">If you prefer to make this change using Lync Server Control Panel, then start the Control Panel and then complete the following procedure:</span></span>

1.  <span data-ttu-id="41eff-122">Klicken Sie auf **Clients** , und klicken Sie dann auf **Gerätekonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="41eff-122">Click **Clients** and then click **Device Configuration**.</span></span>

2.  <span data-ttu-id="41eff-123">Doppelklicken Sie auf der Registerkarte **Gerätekonfiguration** auf die Sammlung von Einstellungen, die Sie ändern möchten (beispielsweise **Global**).</span><span class="sxs-lookup"><span data-stu-id="41eff-123">On the **Device Configuration** tab, double-click the collection of settings you want to modify (for example, **Global**).</span></span>

3.  <span data-ttu-id="41eff-124">Legen Sie im Dialogfeld **Gerätekonfiguration bearbeiten** den Wert für **Quality of Service (QoS) für Voicemail** auf **46** fest, und klicken Sie dann auf **Commit**.</span><span class="sxs-lookup"><span data-stu-id="41eff-124">In the **Edit Device Configuration** dialog box, set the value of the **Voice Quality of Service (QoS)** box to **46** and then click **Commit**.</span></span>

<span data-ttu-id="41eff-125">Wenn Sie über mehrere Sammlungen verfügen, müssen Sie diesen Vorgang für jede Sammlung von UC-Telefoneinstellungen wiederholen.</span><span class="sxs-lookup"><span data-stu-id="41eff-125">If you have multiple collections you will need to repeat this process for each collection of UC phone settings.</span></span> <span data-ttu-id="41eff-126">In der lync Server-Systemsteuerung können Sie mehrere Einstellungsauflistungen nicht gleichzeitig ändern.</span><span class="sxs-lookup"><span data-stu-id="41eff-126">Lync Server Control Panel will not allow you to simultaneously modify multiple setting collections.</span></span>

<span data-ttu-id="41eff-127">Wenn Sie Geräte haben, die nicht auf dem Windows-Betriebssystem (wie iPhones) in Ihrer Organisation basieren, sind diese Geräte durch Ändern der VoiceDiffServTag-Einstellung nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="41eff-127">If you have devices that are not based on the Windows operating system (such as iPhones) in your organization these devices will not be affected by changing the VoiceDiffServTag setting.</span></span> <span data-ttu-id="41eff-128">Wenn Sie DSCP-Werte auf diesen Geräten ändern möchten, müssen Sie für jeden Ihrer Gerätetypen auf das Verwaltungshandbuch verweisen.</span><span class="sxs-lookup"><span data-stu-id="41eff-128">If you want to change DSCP values on those devices you will need to refer to the administration manual for each of your device types.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

