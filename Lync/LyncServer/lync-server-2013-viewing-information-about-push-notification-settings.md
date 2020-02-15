---
title: 'Lync Server 2013: Anzeigen von Informationen zu Einstellungen für die Push-Benachrichtigung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing information about push notification settings
ms:assetid: be5c6b01-4294-4d17-9772-fed40201e8a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721868(v=OCS.15)
ms:contentKeyID: 49733801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c74bbc90b0b7ef27da6b38b626fc91bc04383685
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007144"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-information-about-push-notification-settings-in-lync-server-2013"></a><span data-ttu-id="085ff-102">Anzeigen von Informationen zu Einstellungen für die Push-Benachrichtigung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="085ff-102">Viewing information about push notification settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="085ff-103">_**Letztes Änderungsstand des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="085ff-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="085ff-104">Pushbenachrichtigungen in Form von Signalen, Symbolen oder Warnungen können an ein mobiles Gerät gesendet werden, auch wenn die mobile Anwendung inaktiv ist.</span><span class="sxs-lookup"><span data-stu-id="085ff-104">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the mobile application is inactive.</span></span> <span data-ttu-id="085ff-105">Mit Pushbenachrichtigungen werden Benutzer über Ereignisse informiert, beispielsweise neue oder entgangene Chateinladungen oder Voicemail.</span><span class="sxs-lookup"><span data-stu-id="085ff-105">Push notifications notify a user of events such as a new or missed IM invitation and voice mail.</span></span> <span data-ttu-id="085ff-106">Sie können Informationen Push-Benachrichtigungseinstellungen für mobile Geräte anzeigen, indem Sie entweder lync Server 2013 Systemsteuerung oder lync Server 2013 Verwaltungsshell verwenden.</span><span class="sxs-lookup"><span data-stu-id="085ff-106">You can view information push notifications settings for mobile devices by using either Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-view-push-notification-information-from-lync-server-control-panel"></a><span data-ttu-id="085ff-107">So zeigen Sie Push-Benachrichtigungsinformationen aus lync Server-Systemsteuerung an</span><span class="sxs-lookup"><span data-stu-id="085ff-107">To view push notification information from Lync Server Control Panel</span></span>

1.  <span data-ttu-id="085ff-108">Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="085ff-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="085ff-109">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="085ff-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="085ff-110">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="085ff-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="085ff-111">Klicken Sie in der linken Navigationsleiste auf **Clients**, und klicken Sie dann auf die Navigationsschaltfläche **Pushbenachrichtigungskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="085ff-111">In the left navigation bar, click **Clients**, and then click the **Push Notification Configuration** navigation button.</span></span>

4.  <span data-ttu-id="085ff-112">Klicken Sie auf der Seite **Konfiguration der Push-Benachrichtigung** auf die Website, die Sie anzeigen möchten, klicken Sie auf das Menü **Bearbeiten** , und klicken Sie dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="085ff-112">On the **Push Notification Configuration** page, click the site you want to view, click the **Edit** menu, and then click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-push-notification-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="085ff-113">Anzeigen von Push-Benachrichtigungsinformationen mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="085ff-113">Viewing Push Notification Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="085ff-114">Sie können die Konfigurationseinstellungen für Push-Benachrichtigungen mithilfe von Windows PowerShell und dem Cmdlet **Get-CsPushNotificationConfiguration** anzeigen.</span><span class="sxs-lookup"><span data-stu-id="085ff-114">You can view push notification configuration settings by using Windows PowerShell and the **Get-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="085ff-115">Sie können dieses Cmdlet entweder über die lync Server 2013 Management-Shell oder über eine Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="085ff-115">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="085ff-116">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="085ff-116">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-push-notification-configuration-information"></a><span data-ttu-id="085ff-117">So zeigen Sie Informationen zur Pushbenachrichtigungskonfiguration an</span><span class="sxs-lookup"><span data-stu-id="085ff-117">To view push notification configuration information</span></span>

  - <span data-ttu-id="085ff-118">Wenn Sie Informationen zu allen Konfigurationseinstellungen für die Push-Benachrichtigung anzeigen möchten, geben Sie den folgenden Befehl in das lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="085ff-118">To view information about all your push notification configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsPushNotificationConfiguration
    
    <span data-ttu-id="085ff-119">Hiermit werden Informationen zurückgegeben, die so oder ähnlich aussehen:</span><span class="sxs-lookup"><span data-stu-id="085ff-119">That will return information similar to this:</span></span>
    
        Identity                               : Global
        EnableApplePushNotificationService     : False
        EnableMicrosoftPushNotificationService : False

</div>

<span data-ttu-id="085ff-120">Weitere Informationen finden Sie im Hilfethema für das [Get-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsPushNotificationConfiguration)-Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="085ff-120">For more information, see the help topic for the [Get-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsPushNotificationConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="085ff-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="085ff-121">See Also</span></span>


[<span data-ttu-id="085ff-122">Konfigurieren von Push-Benachrichtigungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="085ff-122">Configuring for push notifications in Lync Server 2013</span></span>](lync-server-2013-configuring-for-push-notifications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

