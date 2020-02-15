---
title: 'Lync Server 2013: Konfigurieren von Sicherheitseinstellungen für lync Phone Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure security settings for Lync Phone Edition
ms:assetid: 6e7cec17-8a79-4428-9300-8821256c46cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521014(v=OCS.15)
ms:contentKeyID: 48184464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68fad5a47f8b56bd97386dcab49aef9671c6f99e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035227"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-security-settings-for-lync-phone-edition-in-lync-server-2013"></a><span data-ttu-id="d211e-102">Konfigurieren von Sicherheitseinstellungen für lync Phone Edition in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d211e-102">Configure security settings for Lync Phone Edition in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d211e-103">_**Letztes Änderungsstand des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="d211e-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="d211e-104">Verbessern Sie die Sicherheit von Geräten, auf denen lync Phone Edition, über Ihre SIP-Sicherheitseinstellung und Einstellungen für die Telefonsperre.</span><span class="sxs-lookup"><span data-stu-id="d211e-104">Help improve the security of devices running Lync Phone Edition via your SIP security setting and phone lock settings.</span></span>

<div>

## <a name="to-configure-security-settings-for-lync-phone-edition"></a><span data-ttu-id="d211e-105">So konfigurieren Sie Sicherheitseinstellungen für lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="d211e-105">To configure security settings for Lync Phone Edition</span></span>

1.  <span data-ttu-id="d211e-106">Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="d211e-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d211e-107">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="d211e-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d211e-108">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d211e-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d211e-109">Klicken Sie in der linken Navigationsleiste auf **Clients** und dann auf **Gerätekonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="d211e-109">In the left navigation bar, click **Clients**, and then click **Device Configuration**.</span></span>

4.  <span data-ttu-id="d211e-110">Doppelklicken Sie auf der Seite **Gerätekonfiguration** in der Liste der Gerätekonfigurationen auf diejenige Konfiguration, deren Sicherheitseinstellungen Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="d211e-110">On the **Device Configuration** page, in the list of device configurations, double-click the configuration for which you want to change security settings.</span></span>

5.  <span data-ttu-id="d211e-p102">Geben Sie in **Gerätekonfiguration bearbeiten** in **SIP-Sicherheit** die SIP-Sicherheitsebene an. Die Standardebene, die auch empfohlen wird, lautet **Hoch**.</span><span class="sxs-lookup"><span data-stu-id="d211e-p102">In **Edit Device Configuration**, in **SIP security**, specify the SIP security level. The default level is **High**, which we recommend using.</span></span>

6.  <span data-ttu-id="d211e-p103">Aktivieren oder deaktivieren Sie in **Gerätekonfiguration bearbeiten** unter **Telefonsperre** das Kontrollkästchen **Gerätesperre erzwingen** (standardmäßig ausgewählt), und geben Sie die minimale PIN-Länge (standardmäßig 6 Zeichen) und die Timeoutdauer (standardmäßig 10 Minuten) an. Es wird empfohlen, die genannten Standardwerte zu verwenden oder die PIN-Länge zu erhöhen bzw. die Timeoutdauer herabzusetzen.</span><span class="sxs-lookup"><span data-stu-id="d211e-p103">In **Edit Device Configuration**, under **Phone Lock**, select or clear the **Enforce device locking** check box (selected by default) and specify the minimum PIN length (6 characters by default) and timeout period (10 minutes by default). We recommend using these defaults or increasing the PIN length and/or decreasing the timeout period.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d211e-115">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-enforce-phone-locking.md">erzwingen der Telefonsperre in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="d211e-115">For details, see <A href="lync-server-2013-enforce-phone-locking.md">Enforce phone locking in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="configuring-security-settings-for-lync-phone-edition-phones-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="d211e-116">Konfigurieren von Sicherheitseinstellungen für lync Phone Edition Telefone mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="d211e-116">Configuring Security Settings for Lync Phone Edition Phones by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="d211e-117">Sicherheitseinstellungen können mithilfe von lync Server-Verwaltungsshell und dem Cmdlet **Get-CsUCPhoneConfiguration** verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="d211e-117">Security settings can be managed by using Lync Server Management Shell and the **Get-CsUCPhoneConfiguration** cmdlet.</span></span> <span data-ttu-id="d211e-118">Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d211e-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="d211e-119">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="d211e-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-modify-the-sip-security-mode"></a><span data-ttu-id="d211e-120">So ändern Sie den SIP-Sicherheitsmodus</span><span class="sxs-lookup"><span data-stu-id="d211e-120">To modify the SIP security mode</span></span>

  - <span data-ttu-id="d211e-p105">Der folgende Befehl legt für die Eigenschaft "SIPSecurityMode" für die globale Auflistung UC-Telefoneinstellungen "Mittel" fest. Die SIP-Sicherheit kann auch auf "Niedrig" oder "Hoch" (den Standardwert) gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="d211e-p105">This command sets the SIPSecurityMode for the global collection of UC phone settings to Medium. SIP security could also be set to Low or High (the default value).</span></span>
    
        Set-CsUCPhoneConfiguration -Identity global -SIPSecurityMode "Medium"

</div>

<div>

## <a name="to-modify-the-minimum-pin-length"></a><span data-ttu-id="d211e-123">So ändern Sie die minimale PIN-Länge</span><span class="sxs-lookup"><span data-stu-id="d211e-123">To modify the minimum PIN length</span></span>

  - <span data-ttu-id="d211e-124">In diesem Beispiel werden alle UC-Telefoneinstellungen so geändert, dass eine minimale PIN-Länge von sieben Ziffern erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="d211e-124">In this example, all the UC phone settings are modified to require a minimum PIN length of 7 digits.</span></span>
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -MinPhonePinLength 7

</div>

<span data-ttu-id="d211e-125">Ausführliche Informationen finden Sie unter [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).</span><span class="sxs-lookup"><span data-stu-id="d211e-125">For details, see [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d211e-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d211e-126">See Also</span></span>


[<span data-ttu-id="d211e-127">Verwalten der lync Server 2013 Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="d211e-127">Managing Lync Server 2013 authentication</span></span>](lync-server-2013-managing-lync-server-authentication.md)  


[<span data-ttu-id="d211e-128">Verwalten von Geräten, Telefonen und Clientanwendungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d211e-128">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

