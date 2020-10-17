---
title: 'Lync Server 2013: Aktivieren oder Deaktivieren von Push-Benachrichtigungen für Windows phones'
description: 'Lync Server 2013: Aktivieren oder Deaktivieren von Push-Benachrichtigungen für Windows phones.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling push notifications for Windows Phones
ms:assetid: a34f0c5c-4228-40e3-9d93-bc0b5df4895d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688162(v=OCS.15)
ms:contentKeyID: 49733767
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba3748c56291b8c6eb236edaac7e23a9e00e5e98
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543467"
---
# <a name="enabling-or-disabling-push-notifications-for-windows-phones-in-lync-server-2013"></a><span data-ttu-id="89461-103">Aktivieren oder Deaktivieren von Push-Benachrichtigungen für Windows Phones in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="89461-103">Enabling or disabling push notifications for Windows Phones in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="89461-104">_**Letztes Änderungsstand des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="89461-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="89461-105">Push-Benachrichtigungen in Form von Abzeichen, Symbolen oder Warnungen können an eine Windows Phone gesendet werden, auch wenn die Mobile Anwendung inaktiv ist.</span><span class="sxs-lookup"><span data-stu-id="89461-105">Push notifications, in the form of badges, icons, or alerts, can be sent to a Windows Phone even when the mobile application is inactive.</span></span> <span data-ttu-id="89461-106">Mit Pushbenachrichtigungen werden Benutzer über Ereignisse informiert, beispielsweise neue oder entgangene Chateinladungen oder Voicemail.</span><span class="sxs-lookup"><span data-stu-id="89461-106">Push notifications notify a user of events such as a new or missed IM invitation and voice mail.</span></span> <span data-ttu-id="89461-107">Sie können Push-Benachrichtigungen für Windows Phone Geräte aktivieren oder deaktivieren, indem Sie entweder lync Server 2013 Systemsteuerung oder lync Server 2013 Management Shell verwenden.</span><span class="sxs-lookup"><span data-stu-id="89461-107">You can enable or disable push notifications for Windows Phone devices by using either Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-enable-push-notifications-for-windows-phone-by-using-lync-server-control-panel"></a><span data-ttu-id="89461-108">So aktivieren Sie Push-Benachrichtigungen für Windows Phone mithilfe von lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="89461-108">To enable push notifications for Windows Phone by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="89461-109">Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="89461-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="89461-110">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="89461-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="89461-111">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="89461-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="89461-112">Klicken Sie in der linken Navigationsleiste auf **Clients**, und klicken Sie dann auf die Navigationsschaltfläche **Pushbenachrichtigungskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="89461-112">In the left navigation bar, click **Clients**, and then click the **Push Notification Configuration** navigation button.</span></span>

4.  <span data-ttu-id="89461-113">Klicken Sie auf der Seite **Konfiguration der Push-Benachrichtigung** auf die Website, die Sie bearbeiten möchten, klicken Sie auf das Menü **Bearbeiten** , und klicken Sie dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="89461-113">On the **Push Notification Configuration** page, click the site you want to edit, click the **Edit** menu, and then click **Show details**.</span></span>

5.  <span data-ttu-id="89461-114">Aktivieren Sie das Kontrollkästchen **Microsoft-Pushbenachrichtigungen aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="89461-114">Click the **Enable Microsoft push notifications** checkbox.</span></span>

6.  <span data-ttu-id="89461-115">Klicken Sie auf **Commit**.</span><span class="sxs-lookup"><span data-stu-id="89461-115">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-disable-push-notifications-for-windows-phone-by-using-lync-server-control-panel"></a><span data-ttu-id="89461-116">So deaktivieren Sie Push-Benachrichtigungen für Windows Phone mithilfe von lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="89461-116">To disable push notifications for Windows Phone by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="89461-117">Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="89461-117">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="89461-118">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="89461-118">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="89461-119">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="89461-119">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="89461-120">Klicken Sie in der linken Navigationsleiste auf **Clients**, und klicken Sie dann auf die Navigationsschaltfläche **Pushbenachrichtigungskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="89461-120">In the left navigation bar, click **Clients**, and then click the **Push Notification Configuration** navigation button.</span></span>

4.  <span data-ttu-id="89461-121">Klicken Sie auf der Seite **Konfiguration der Push-Benachrichtigung** auf die Website, die Sie bearbeiten möchten, klicken Sie auf das Menü **Bearbeiten** , und klicken Sie dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="89461-121">On the **Push Notification Configuration** page, click the site you want to edit, click the **Edit** menu, and then click **Show details**.</span></span>

5.  <span data-ttu-id="89461-122">Deaktivieren Sie das Kontrollkästchen **Microsoft-Pushbenachrichtigungen aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="89461-122">Clear the **Enable Microsoft push notifications** checkbox.</span></span>

6.  <span data-ttu-id="89461-123">Klicken Sie auf **Commit**.</span><span class="sxs-lookup"><span data-stu-id="89461-123">Click **Commit**.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-push-notifications-for-windows-phone-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="89461-124">Aktivieren oder Deaktivieren von Push-Benachrichtigungen für Windows Phone mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="89461-124">Enabling or Disabling Push Notifications for Windows Phone by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="89461-125">Sie können Push-Benachrichtigungen für Windows Phone aktivieren oder deaktivieren, indem Sie das Cmdlet "Cmdlet **festlegen-CsPushNotificationConfiguration** " verwenden.</span><span class="sxs-lookup"><span data-stu-id="89461-125">You can enable or disable push notifications for Windows Phone by using the **Set-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="89461-126">Sie können dieses Cmdlet entweder über die lync Server 2013 Management-Shell oder über eine Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="89461-126">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="89461-127">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="89461-127">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-push-notifications-for-windows-phone"></a><span data-ttu-id="89461-128">So aktivieren Sie Push-Benachrichtigungen für Windows Phone</span><span class="sxs-lookup"><span data-stu-id="89461-128">To enable push notifications for Windows Phone</span></span>

  - <span data-ttu-id="89461-129">Um Push-Benachrichtigungen für Windows Phone zu aktivieren, legen Sie den Wert der EnableMicrosoftPushNotificationService-Eigenschaft auf true ($true) fest.</span><span class="sxs-lookup"><span data-stu-id="89461-129">To enable push notifications for Windows Phone set the value of the EnableMicrosoftPushNotificationService property to True ($True).</span></span> <span data-ttu-id="89461-130">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="89461-130">For example:</span></span>
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableMicrosoftPushNotificationService $True

</div>

<div>

## <a name="to-disable-push-notifications-for-windows-phone"></a><span data-ttu-id="89461-131">So deaktivieren Sie Push-Benachrichtigungen für Windows Phone</span><span class="sxs-lookup"><span data-stu-id="89461-131">To disable push notifications for Windows Phone</span></span>

  - <span data-ttu-id="89461-132">Wenn Sie Push-Benachrichtigungen für Windows Phone deaktivieren möchten, legen Sie den Wert der EnableMicrosoftPushNotificationService-Eigenschaft auf false ($false) fest.</span><span class="sxs-lookup"><span data-stu-id="89461-132">To disable push notifications for Windows Phone set the value of the EnableMicrosoftPushNotificationService property to False ($False).</span></span> <span data-ttu-id="89461-133">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="89461-133">For example:</span></span>
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableMicrosoftPushNotificationService $False

</div>

<span data-ttu-id="89461-134">Weitere Informationen dazu finden Sie im Hilfethema für das Cmdlet [Set-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPushNotificationConfiguration).</span><span class="sxs-lookup"><span data-stu-id="89461-134">For more information, see the help topic for the [Set-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPushNotificationConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="89461-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="89461-135">See Also</span></span>


[<span data-ttu-id="89461-136">Konfigurieren von Push-Benachrichtigungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="89461-136">Configuring for push notifications in Lync Server 2013</span></span>](lync-server-2013-configuring-for-push-notifications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

