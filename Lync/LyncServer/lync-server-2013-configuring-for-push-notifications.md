---
title: 'Lync Server 2013: Konfigurieren von Push-Benachrichtigungen'
description: 'Lync Server 2013: Konfigurieren von Push-Benachrichtigungen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring for push notifications
ms:assetid: d77f2c06-0fe6-45d5-8f08-808ab871b3e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690047(v=OCS.15)
ms:contentKeyID: 48185574
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 24c22ff42f666add9eac4966134c88b9bf680046
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548331"
---
# <a name="configuring-for-push-notifications-in-lync-server-2013"></a><span data-ttu-id="9b9dd-103">Konfigurieren von Push-Benachrichtigungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9b9dd-103">Configuring for push notifications in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9b9dd-104">_**Letztes Änderungsstand des Themas:** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="9b9dd-104">_**Topic Last Modified:** 2013-02-12_</span></span>

<span data-ttu-id="9b9dd-105">Pushbenachrichtigungen in Form von Signalen, Symbolen oder Warnungen können an ein mobiles Gerät gesendet werden, auch wenn die mobile Anwendung inaktiv ist.</span><span class="sxs-lookup"><span data-stu-id="9b9dd-105">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the mobile application is inactive.</span></span> <span data-ttu-id="9b9dd-106">Mit Pushbenachrichtigungen werden Benutzer über Ereignisse informiert, beispielsweise neue oder entgangene Chateinladungen oder Voicemail.</span><span class="sxs-lookup"><span data-stu-id="9b9dd-106">Push notifications notify a user of events such as a new or missed IM invitation and voice mail.</span></span> <span data-ttu-id="9b9dd-107">Der lync Server 2013 Mobilitätsdienst sendet die Benachrichtigungen an den cloudbasierten lync Server Push-Benachrichtigungsdienst, der dann die Benachrichtigungen an den Apple Push Notification Service (APNS) (für ein Apple-Gerät mit dem lync 2010 Mobile Client) oder den Microsoft Push Notification Service (MPNS) (für ein Windows Phone Gerät mit dem lync 2010 Mobile oder dem lync 2013 mobilen Client) sendet.</span><span class="sxs-lookup"><span data-stu-id="9b9dd-107">The Lync Server 2013 Mobility Service sends the notifications to the cloud-based Lync Server Push Notification Service, which then sends the notifications to the Apple Push Notification Service (APNS) (for an Apple device running the Lync 2010 Mobile client) or the Microsoft Push Notification Service (MPNS) (for a Windows Phone device running the Lync 2010 Mobile or the Lync 2013 Mobile client).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9b9dd-108">Wenn Sie Windows Phone mit lync 2010 Mobile oder lync 2013 mobilen Clients verwenden, ist die Push-Benachrichtigung eine wichtige Überlegung.</span><span class="sxs-lookup"><span data-stu-id="9b9dd-108">If you use Windows Phone with Lync 2010 Mobile or Lync 2013 Mobile client, push notification is an important consideration.</span></span><BR><span data-ttu-id="9b9dd-109">Wenn Sie lync 2010 Mobile auf Apple-Geräten verwenden, ist die Push-Benachrichtigung eine wichtige Überlegung.</span><span class="sxs-lookup"><span data-stu-id="9b9dd-109">If you use Lync 2010 Mobile on Apple devices, push notification is an important consideration.</span></span><BR><span data-ttu-id="9b9dd-110">Wenn Sie lync 2013 Mobile auf Apple-Geräten verwenden, benötigen Sie keine Push-Benachrichtigungen mehr.</span><span class="sxs-lookup"><span data-stu-id="9b9dd-110">If you use Lync 2013 Mobile on Apple devices, you no longer need push notification.</span></span>



</div>

<span data-ttu-id="9b9dd-111">Gehen Sie wie folgt vor, um die Topologie zur Unterstützung von Pushbenachrichtigungen zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="9b9dd-111">Configure your topology to support push notifications by doing the following:</span></span>

  - <span data-ttu-id="9b9dd-112">Wenn Ihre Umgebung über eine lync Server 2010 oder lync Server 2013 Edgeserver verfügt, müssen Sie einen neuen Hostinganbieter, Microsoft lync Online, hinzufügen und dann den Anbieter Verbund für den Hostinganbieter zwischen Ihrer Organisation und lync Online einrichten.</span><span class="sxs-lookup"><span data-stu-id="9b9dd-112">If your environment has a Lync Server 2010 or Lync Server 2013 Edge Server, you need to add a new hosting provider, Microsoft Lync Online, and then set up hosting provider federation between your organization and Lync Online.</span></span>

  - <span data-ttu-id="9b9dd-113">Wenn Ihre Umgebung über eine Office Communications Server 2007 R2 Edgeserver verfügt, müssen Sie den direkten SIP-Partnerverbund mit Push.lync.com einrichten.</span><span class="sxs-lookup"><span data-stu-id="9b9dd-113">If your environment has a Office Communications Server 2007 R2 Edge Server, you need to set up direct SIP federation with push.lync.com.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9b9dd-114">Push.lync.com ist eine Microsoft Office 365-Domäne für den Pushbenachrichtigungsdienst.</span><span class="sxs-lookup"><span data-stu-id="9b9dd-114">Push.lync.com is a Microsoft Office 365 domain for Push Notification Service.</span></span>

    
    </div>

  - <span data-ttu-id="9b9dd-115">Zur Aktivierung von Pushbenachrichtigungen müssen Sie das **Set-CsPushNotificationConfiguration**-Cmdlet ausführen.</span><span class="sxs-lookup"><span data-stu-id="9b9dd-115">To enable push notifications, you need to run the **Set-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="9b9dd-116">Pushbenachrichtigungen sind standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="9b9dd-116">By default, push notifications are turned off.</span></span>

  - <span data-ttu-id="9b9dd-117">Testen Sie die Partnerverbundkonfiguration und die Pushbenachrichtigungen.</span><span class="sxs-lookup"><span data-stu-id="9b9dd-117">Test the federation configuration and push notifications.</span></span>

<div>

## <a name="to-configure-for-push-notifications-with-lync-server-2013-or-lync-server-2010edge-server"></a><span data-ttu-id="9b9dd-118">So konfigurieren Sie Push-Benachrichtigungen mit lync Server 2013 oder lync Server 2010 Edgeserver</span><span class="sxs-lookup"><span data-stu-id="9b9dd-118">To configure for push notifications with Lync Server 2013 or Lync Server 2010 Edge Server</span></span>

1.  <span data-ttu-id="9b9dd-119">Melden Sie sich an einem Computer an, auf dem lync Server-Verwaltungsshell und OCSCore als Mitglied der RtcUniversalServerAdmins-Gruppe installiert sind.</span><span class="sxs-lookup"><span data-stu-id="9b9dd-119">Log on to a computer where Lync Server Management Shell and Ocscore are installed as a member of the RtcUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="9b9dd-120">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="9b9dd-120">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="9b9dd-121">Fügen Sie einen lync Server Online Hosting-Anbieter hinzu.</span><span class="sxs-lookup"><span data-stu-id="9b9dd-121">Add a Lync Server online hosting provider.</span></span> <span data-ttu-id="9b9dd-122">Geben Sie in die Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="9b9dd-122">At the command line, type:</span></span>
    
        New-CsHostingProvider -Identity <unique identifier for Lync Online hosting provider> -Enabled $True -ProxyFqdn <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
    
    <span data-ttu-id="9b9dd-123">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9b9dd-123">For example:</span></span>
    
        New-CsHostingProvider -Identity "LyncOnline" -Enabled $True -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9b9dd-p104">Es kann nur maximal eine Partnerverbundbeziehung mit einem einzelnen Hostinganbieter bestehen. Wenn Sie also bereits einen Hostinganbieter eingerichtet haben, der eine Partnerverbundbeziehung mit "sipfed.online.lync.com" hat, fügen Sie keinen weiteren Hostinganbieter hinzu, auch wenn die Identität des Hostinganbieters nicht "LyncOnline" ist.</span><span class="sxs-lookup"><span data-stu-id="9b9dd-p104">You cannot have more than one federation relationship with a single hosting provider. That is, if you have already set up a hosting provider that has a federation relationship with sipfed.online.lync.com, do not add another hosting provider for it, even if the identity of the hosting provider is something other than LyncOnline.</span></span>

    
    </div>

4.  <span data-ttu-id="9b9dd-p105">Einrichten eines Hostinganbieter-Partnerverbunds zwischen Ihrer Organisation und dem Pushbenachrichtigungsdienst bei Lync Online. Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="9b9dd-p105">Set up hosting provider federation between your organization and the Push Notification Service at Lync Online. At the command line, type:</span></span>
    
        New-CsAllowedDomain -Identity "push.lync.com"

</div>

<div>

## <a name="to-configure-for-push-notifications-with-office-communications-server-2007-r2edge-server"></a><span data-ttu-id="9b9dd-128">So konfigurieren Sie für Push-Benachrichtigungen mit Office Communications Server 2007 R2 Edgeserver</span><span class="sxs-lookup"><span data-stu-id="9b9dd-128">To configure for push notifications with Office Communications Server 2007 R2 Edge Server</span></span>

1.  <span data-ttu-id="9b9dd-129">Melden Sie sich beim Edgeserver als Mitglied der RtcUniversalServerAdmins-Gruppe an.</span><span class="sxs-lookup"><span data-stu-id="9b9dd-129">Log on to the Edge Server as a member of the RtcUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="9b9dd-130">Klicken Sie nacheinander auf **Start**, **Alle Programme**, **Verwaltung** und **Computerverwaltung**.</span><span class="sxs-lookup"><span data-stu-id="9b9dd-130">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **Computer Management**.</span></span>

3.  <span data-ttu-id="9b9dd-131">Erweitern Sie in der Konsolenstruktur **Dienste und Anwendungen**, klicken Sie mit der rechten Maustaste auf **Microsoft Office Communications Server 2007 R2**, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="9b9dd-131">In the console tree, expand **Services and Applications**, right-click **Microsoft Office Communications Server 2007 R2**, and then click **Properties**.</span></span>

4.  <span data-ttu-id="9b9dd-132">Klicken Sie auf der Registerkarte **Zulassen** auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="9b9dd-132">On the **Allow** tab, click **Add**.</span></span>

5.  <span data-ttu-id="9b9dd-133">Gehen Sie im Dialogfeld **Verbundpartner hinzufügen** wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="9b9dd-133">In the **Add Federated Partner** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="9b9dd-134">Geben Sie im Feld **Domänenname des Verbundpartners** den Namen **push.lync.com** ein.</span><span class="sxs-lookup"><span data-stu-id="9b9dd-134">In **Federated partner domain name**, type **push.lync.com**.</span></span>
    
      - <span data-ttu-id="9b9dd-135">Geben Sie **sipfed.online.lync.com** im Feld **Zugriffs-Edgeserver des Verbundpartners** ein.</span><span class="sxs-lookup"><span data-stu-id="9b9dd-135">In **Federated partner Access Edge Server**, type **sipfed.online.lync.com**.</span></span>
    
      - <span data-ttu-id="9b9dd-136">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="9b9dd-136">Click **OK**.</span></span>

</div>

<div>

## <a name="to-enable-push-notifications"></a><span data-ttu-id="9b9dd-137">So aktivieren Sie Pushbenachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="9b9dd-137">To enable push notifications</span></span>

1.  <span data-ttu-id="9b9dd-138">Melden Sie sich an einem Computer an, auf dem lync Server-Verwaltungsshell und OCSCore als Mitglied der CsAdministrator-Rolle installiert sind.</span><span class="sxs-lookup"><span data-stu-id="9b9dd-138">Log on to a computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="9b9dd-139">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="9b9dd-139">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="9b9dd-p106">Aktivieren Sie Pushbenachrichtigungen. Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="9b9dd-p106">Enable push notifications. At the command line, type:</span></span>
    
        Set-CsPushNotificationConfiguration -EnableApplePushNotificationService $True -EnableMicrosoftPushNotificationService $True

4.  <span data-ttu-id="9b9dd-p107">Aktivieren Sie den Partnerverbund. Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="9b9dd-p107">Enable federation. At the command line, type:</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-test-federation-and-push-notifications"></a><span data-ttu-id="9b9dd-144">So testen Sie den Partnerverbund und die Pushbenachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="9b9dd-144">To test federation and push notifications</span></span>

1.  <span data-ttu-id="9b9dd-145">Melden Sie sich an einem Computer an, auf dem lync Server-Verwaltungsshell und OCSCore als Mitglied der CsAdministrator-Rolle installiert sind.</span><span class="sxs-lookup"><span data-stu-id="9b9dd-145">Log on to a computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="9b9dd-146">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="9b9dd-146">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="9b9dd-p108">Testen Sie die Partnerverbundkonfiguration. Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="9b9dd-p108">Test the federation configuration. At the command line, type:</span></span>
    
        Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
    
    <span data-ttu-id="9b9dd-149">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9b9dd-149">For example:</span></span>
    
        Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com

4.  <span data-ttu-id="9b9dd-p109">Testen Sie die Pushbenachrichtigungen. Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="9b9dd-p109">Test push notifications. At the command line, type:</span></span>
    
        Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
    
    <span data-ttu-id="9b9dd-152">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9b9dd-152">For example:</span></span>
    
        Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9b9dd-153">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9b9dd-153">See Also</span></span>


[<span data-ttu-id="9b9dd-154">Test-CsFederatedPartner</span><span class="sxs-lookup"><span data-stu-id="9b9dd-154">Test-CsFederatedPartner</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
[<span data-ttu-id="9b9dd-155">Test-CsMcxPushNotification</span><span class="sxs-lookup"><span data-stu-id="9b9dd-155">Test-CsMcxPushNotification</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

