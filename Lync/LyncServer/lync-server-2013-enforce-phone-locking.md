---
title: 'Lync Server 2013: Erzwingen der Telefonsperre'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enforce phone locking
ms:assetid: 1f89298b-aea9-4952-93ca-0270b565792b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520963(v=OCS.15)
ms:contentKeyID: 48183594
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f40f11f835c350b5038771f2ac9f47ab8fec0f2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207679"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enforce-phone-locking-in-lync-server-2013"></a><span data-ttu-id="74646-102">Erzwingen der Telefonsperre in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74646-102">Enforce phone locking in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74646-103">_**Letztes Änderungsstand des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="74646-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="74646-104">Lync Phone Edition-Geräte können aus Sicherheitsgründen gesperrt werden.</span><span class="sxs-lookup"><span data-stu-id="74646-104">Lync Phone Edition devices can be locked for security purposes.</span></span> <span data-ttu-id="74646-105">Wenn Sie die Telefonsperre erzwingen, sperrt das Gerät, auf dem lync installiert ist, Phone Edition nach einer von Ihnen konfigurierten Zeitspanne.</span><span class="sxs-lookup"><span data-stu-id="74646-105">If you enforce phone lock, the device running Lync Phone Edition locks after a period of time that you configure.</span></span> <span data-ttu-id="74646-106">Wenn ein Telefon gesperrt ist, kann ein Benutzer Anrufe tätigen, aber nicht auf Kalender-und Kontaktinformationen, Voicemails oder Anrufprotokolle zugreifen oder die Suche verwenden.</span><span class="sxs-lookup"><span data-stu-id="74646-106">When a phone is locked, a user can make calls but cannot access calendar and contact information, voice mail, or call logs or use search.</span></span> <span data-ttu-id="74646-107">Um das Telefon zu entsperren, gibt der Benutzer eine PIN ein.</span><span class="sxs-lookup"><span data-stu-id="74646-107">To unlock the phone, the user enters a PIN.</span></span>

<span data-ttu-id="74646-108">Um die Telefonsperre zu erzwingen, aktivieren und konfigurieren Sie Sie mithilfe von lync Server-Systemsteuerung oder lync Server PowerShell-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="74646-108">To enforce phone lock, enable and configure it by using Lync Server Control Panel or Lync Server PowerShell cmdlets.</span></span> <span data-ttu-id="74646-109">Sie können die Telefonsperre Global oder nur innerhalb der Website erzwingen, für die Sie konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="74646-109">You can enforce phone lock globally or only within the site for which it is configured.</span></span>

<div>

## <a name="to-configure-and-enforce-the-phone-lock"></a><span data-ttu-id="74646-110">So konfigurieren und erzwingen Sie die Telefonsperre</span><span class="sxs-lookup"><span data-stu-id="74646-110">To configure and enforce the phone lock</span></span>

1.  <span data-ttu-id="74646-111">Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="74646-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="74646-112">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="74646-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="74646-113">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="74646-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="74646-114">Klicken Sie auf **Clients** und anschließend auf **Gerätekonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="74646-114">Click **Clients**, and then click **Device Configuration**.</span></span>

4.  <span data-ttu-id="74646-115">Doppelklicken Sie auf der Registerkarte **Gerätekonfiguration** in der Liste der Gerätekonfigurationen auf diejenige Konfiguration, deren Einstellungen für die Telefonsperre Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="74646-115">On the **Device Configuration** tab, in the list of device configurations, double-click the configuration for which you want to change the phone lock settings.</span></span>

5.  <span data-ttu-id="74646-116">Stellen Sie im Dialogfeld **Gerätekonfiguration bearbeiten** sicher, dass das Kontrollkästchen **Gerätesperre erzwingen** aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="74646-116">In the **Edit Device Configuration** dialog box, verify that the **Enforce device locking** check box is selected.</span></span>

6.  <span data-ttu-id="74646-117">Übernehmen Sie in der **minimalen PIN-Länge**den Standardwert für die minimale Anzahl von stellen, die die Unlock-Pin enthalten muss, oder geben Sie einen neuen Wert an.</span><span class="sxs-lookup"><span data-stu-id="74646-117">In **Minimum PIN length**, accept the default value for the minimum number of digits that the unlock PIN must contain or specify a new value.</span></span> <span data-ttu-id="74646-118">Der Bereich für die PIN-Länge beträgt vier bis 15 Ziffern, der Standardwert ist 6.</span><span class="sxs-lookup"><span data-stu-id="74646-118">The range for the PIN length is four to 15 digits, and the default is six.</span></span>

7.  <span data-ttu-id="74646-119">Übernehmen Sie im **Telefon Sperrtimeout**den Standardwert für die minimale Zeitdauer, bevor das Telefon sich selbst sperrt, oder geben Sie einen neuen Wert ein.</span><span class="sxs-lookup"><span data-stu-id="74646-119">In **Phone lock time-out**, accept the default value for the minimum length of time before the phone locks itself or specify a new value.</span></span> <span data-ttu-id="74646-120">Der Bereich für das Timeout ist 0 bis 60 Minuten, und der Standardwert ist 10.</span><span class="sxs-lookup"><span data-stu-id="74646-120">The range for the timeout is 0 to 60 minutes, and the default is 10.</span></span> <span data-ttu-id="74646-121">Geben Sie den Wert im Format HH:MM:SS ein.</span><span class="sxs-lookup"><span data-stu-id="74646-121">Enter the value in the format HH:MM:SS.</span></span>

8.  <span data-ttu-id="74646-122">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="74646-122">Click **Commit**.</span></span>

</div>

<div>

## <a name="enforcing-phone-locking-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="74646-123">Erzwingen der Telefonsperre mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="74646-123">Enforcing Phone Locking by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="74646-124">Die Telefonsperre kann mithilfe des Cmdlets "CsUCPhoneConfiguration" erzwungen werden.</span><span class="sxs-lookup"><span data-stu-id="74646-124">Phone locking can be enforced by using the Set-CsUCPhoneConfiguration cmdlet.</span></span> <span data-ttu-id="74646-125">Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="74646-125">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="74646-126">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="74646-126">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-phone-locking"></a><span data-ttu-id="74646-127">So aktivieren Sie die Telefonsperre</span><span class="sxs-lookup"><span data-stu-id="74646-127">To enable phone locking</span></span>

  - <span data-ttu-id="74646-128">Mit dem folgenden Befehl können Sie die Telefonsperre für den Standort Redmond aktivieren.</span><span class="sxs-lookup"><span data-stu-id="74646-128">The following command enables phone locking for the Redmond site.</span></span> <span data-ttu-id="74646-129">Setzen Sie zum Deaktivieren der Telefonsperre die Eigenschaft "EnforcePhoneLock" auf "False" ($False).</span><span class="sxs-lookup"><span data-stu-id="74646-129">To disable phone locking, set the EnforcePhoneLock property to False ($False).</span></span>
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-enable-phone-locking-and-modify-the-phone-lock-timeout"></a><span data-ttu-id="74646-130">So aktivieren Sie das Sperren von Telefon sperren und Ändern des Timeouts für die Telefonsperre</span><span class="sxs-lookup"><span data-stu-id="74646-130">To enable phone locking and modify the phone lock timeout</span></span>

  - <span data-ttu-id="74646-131">Mit diesem Befehl wird die Telefonsperre aktiviert und das Timeout für die Telefonsperre auf 30 Minuten festgelegt.</span><span class="sxs-lookup"><span data-stu-id="74646-131">This command enables phone locking and also sets the phone lock timeout to 30 minutes.</span></span>
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True -PhoneLockTimeout "00:30:00"

</div>

<div>

## <a name="to-enable-phone-locking-throughout-the-organization"></a><span data-ttu-id="74646-132">So aktivieren Sie die Telefonsperre in der gesamten Organisation</span><span class="sxs-lookup"><span data-stu-id="74646-132">To enable phone locking throughout the organization</span></span>

  - <span data-ttu-id="74646-133">In diesem Beispiel ist die Telefonsperre für alle in der Organisation eingesetzten UC-Telefonkonfigurationseinstellungen aktiviert.</span><span class="sxs-lookup"><span data-stu-id="74646-133">In this example, phone locking is enabled on all the UC phone configuration settings in use in the organization.</span></span>
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration  -EnforcePhoneLock $True

</div>

<span data-ttu-id="74646-134">Weitere Informationen finden Sie im Hilfethema zum Cmdlet " [CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsUCPhoneConfiguration) ".</span><span class="sxs-lookup"><span data-stu-id="74646-134">For more information, see the help topic for the [Set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsUCPhoneConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="74646-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="74646-135">See Also</span></span>


[<span data-ttu-id="74646-136">Verwalten der lync Server 2013 Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="74646-136">Managing Lync Server 2013 authentication</span></span>](lync-server-2013-managing-lync-server-authentication.md)  


[<span data-ttu-id="74646-137">Verwalten von Geräten, Telefonen und Clientanwendungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74646-137">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

