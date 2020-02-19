---
title: 'Lync Server 2013: Konfigurieren der Mobilitätsrichtlinie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring mobility policy
ms:assetid: 595536e0-9bb3-49a3-8d13-1a77351ebc62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690018(v=OCS.15)
ms:contentKeyID: 48184204
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82ca5fbd079f428edf48ef3f0c28bd3677a5acde
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134751"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-mobility-policy-in-lync-server-2013"></a><span data-ttu-id="fae41-102">Konfigurieren von mobilitätsrichtlinien in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fae41-102">Configuring mobility policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fae41-103">_**Letztes Änderungsstand des Themas:** 2013-02-13_</span><span class="sxs-lookup"><span data-stu-id="fae41-103">_**Topic Last Modified:** 2013-02-13_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="fae41-104">Lync Server 2013 bietet mobilitätsrichtlinien, die festlegen, wer Mobilitätsfunktionen nutzen, über Arbeit anrufen, VoIP (Voice over IP) oder Video verwenden kann und ob WLAN für VoIP oder Video erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="fae41-104">Lync Server 2013 provides mobility policies that determine who can use mobility features, Call via Work, voice over IP (VoIP) or video, and whether WiFi will be required for either VoIP or video.</span></span> <span data-ttu-id="fae41-105">Das Feature "Anruf über Arbeit" ermöglicht einem mobilen Benutzer das tätigen und annehmen von Anrufen auf einem Mobiltelefon mithilfe einer geschäftlichen Telefonnummer anstelle der Mobiltelefonnummer.</span><span class="sxs-lookup"><span data-stu-id="fae41-105">The Call via Work feature enables a mobile user to make and receive calls on a mobile phone by using a work phone number instead of the mobile phone number.</span></span> <span data-ttu-id="fae41-106">Dieses Feature verhindert, dass die angerufene Person die Mobiltelefonnummer des Anrufers sieht und einem Benutzer die Möglichkeit gibt, ausgehende Gebühren zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="fae41-106">This feature prevents the called party from seeing the caller's mobile phone number and enables a user to avoid outbound calling charges.</span></span> <span data-ttu-id="fae41-107">Durch die Konfiguration von VoIP und Video können Benutzer VoIP-Anrufe und Videos empfangen und tätigen.</span><span class="sxs-lookup"><span data-stu-id="fae41-107">Configuring VoIP and video makes it possible for users to receive and make VoIP calls and video.</span></span> <span data-ttu-id="fae41-108">Einstellungen für die WLAN-Nutzung definieren, ob das Gerät eines Benutzers ein WLAN-Netzwerk über ein Mobilfunknetz verwenden muss.</span><span class="sxs-lookup"><span data-stu-id="fae41-108">Settings for WiFi usage define if a user’s device will be required to use a WiFi network over a cellular data network.</span></span>

<span data-ttu-id="fae41-109">Standardmäßig sind Mobilität, Anruf über Arbeit und VoIP-und Videofunktionen aktiviert.</span><span class="sxs-lookup"><span data-stu-id="fae41-109">By default, mobility, Call via Work, and the VoIP and video features are enabled.</span></span> <span data-ttu-id="fae41-110">Die Einstellungen, die WLAN für VoIP und Video erfordern, sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="fae41-110">The settings to require WiFi for VoIp and video are disabled.</span></span> <span data-ttu-id="fae41-111">Administratoren können durch Ausführen eines Cmdlets bestimmen, wer Zugriff auf diese Features hat.</span><span class="sxs-lookup"><span data-stu-id="fae41-111">Administrators can determine who has access to these features by running a cmdlet.</span></span> <span data-ttu-id="fae41-112">Sie können die Optionen global, nach Standort oder nach Benutzer deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="fae41-112">You can turn options off globally, by site, or by user.</span></span>

<span data-ttu-id="fae41-113">Benutzer müssen die beiden folgenden Voraussetzungen erfüllen, um die Mobilitätsfeatures und das Feature "Geschäftlich anrufen" verwenden zu können:</span><span class="sxs-lookup"><span data-stu-id="fae41-113">To be able to use mobility features and Call via Work, users must meet the following prerequisites:</span></span>

  - <span data-ttu-id="fae41-114">Benutzer müssen für lync Server 2013 aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="fae41-114">Users must be enabled for Lync Server 2013.</span></span>

  - <span data-ttu-id="fae41-115">Benutzer müssen für Enterprise-VoIP aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="fae41-115">Users must be enabled for Enterprise Voice.</span></span>

  - <span data-ttu-id="fae41-116">Benutzern muss eine Mobilitätsrichtlinie zugewiesen sein, für die die Option **EnableMobility** auf TRUE gesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="fae41-116">Users must be assigned a mobility policy that has the **EnableMobility** option set to True.</span></span>

<span data-ttu-id="fae41-117">Zum Verwenden des Features Geschäftlich anrufen müssen Benutzer zudem die beiden folgenden Voraussetzungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="fae41-117">For users to be able to use Call via Work, they must meet the following two additional prerequisites:</span></span>

  - <span data-ttu-id="fae41-118">Benutzern muss eine VoIP-Richtlinie zugewiesen sein, für die die Option **Gleichzeitiges Klingeln von Telefonen aktivieren** aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="fae41-118">Users must be assigned a voice policy that has the **Enable simultaneous ringing of phones** option selected.</span></span>

  - <span data-ttu-id="fae41-119">Benutzern muss eine Mobilitätsrichtlinie mit der Option **EnableOutsideVoice** und dem Wert "True" zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="fae41-119">Users must be assigned a mobility policy that has the **EnableOutsideVoice** option set to True.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fae41-120">Benutzer, die nicht für Enterprise-VoIP aktiviert sind, können mit ihren mobilen Geräten lync-VoIP-Anrufe (Voice over IP) durchführen oder an Konferenzen teilnehmen, indem Sie den Link klicken, um auf Ihren mobilen Geräten zu verbinden, wenn Sie diesen Benutzern die entsprechenden Optionen für die VoIP-Richtlinie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="fae41-120">Users who are not enabled for Enterprise Voice can use their mobile devices to make Lync to Lync Voice over IP (VoIP) calls, or can join conferences by using the Click to Join link on their mobile devices, if you assign those users the appropriate options for voice policy.</span></span> <span data-ttu-id="fae41-121">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-defining-your-mobility-requirements.md">Definieren Ihrer Mobilitätsanforderungen für lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="fae41-121">For details, see <A href="lync-server-2013-defining-your-mobility-requirements.md">Defining your mobility requirements for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="fae41-122">Ausführliche Informationen zum Aktivieren von Benutzern für lync Server 2013 finden Sie unter [deaktivieren oder erneutes Aktivieren des Benutzerkontos für lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md).</span><span class="sxs-lookup"><span data-stu-id="fae41-122">For details about enabling users for Lync Server 2013, see [Disable or re-enable user account for Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md).</span></span> <span data-ttu-id="fae41-123">Ausführliche Informationen zum Aktivieren von Benutzern für Enterprise-VoIP finden Sie unter [Aktivieren von Benutzern für Enterprise-VoIP in lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span><span class="sxs-lookup"><span data-stu-id="fae41-123">For details about enabling users for Enterprise Voice, see [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span></span> <span data-ttu-id="fae41-124">Ausführliche Informationen zum Festlegen von VoIP-Richtlinienoptionen finden Sie unter [Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md).</span><span class="sxs-lookup"><span data-stu-id="fae41-124">For details about setting voice policy options, see [Modify a voice policy and configure PSTN usage records in Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md).</span></span>

<div>

## <a name="to-modify-global-mobility-policy"></a><span data-ttu-id="fae41-125">So ändern Sie die globale Mobilitätsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="fae41-125">To modify global mobility policy</span></span>

1.  <span data-ttu-id="fae41-126">Melden Sie sich an einem beliebigen Computer an, auf dem lync Server-Verwaltungsshell und OCSCore als Mitglied der CsAdministrator-Rolle installiert sind.</span><span class="sxs-lookup"><span data-stu-id="fae41-126">Log on to any computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="fae41-127">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="fae41-127">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="fae41-p105">Deaktivieren Sie den Zugriff auf die Mobilität und Geschäftlich anrufen global. Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="fae41-p105">Turn off access to mobility and Call via Work globally. At the command line, type:</span></span>
    
        Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fae41-p106">Sie können auch nur den Zugriff auf das Feature Geschäftlich anrufen deaktivieren, ohne den Zugriff auf die Mobilität zu deaktivieren. Es ist jedoch nicht möglich, den Zugriff auf die Mobilität deaktivieren, ohne auch den Zugriff auf Geschäftlich anrufen zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="fae41-p106">You can turn off Call via Work without turning off access to mobility. However, you cannot turn off mobility without also turning off Call via Work.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-mobility-policy-by-site"></a><span data-ttu-id="fae41-132">So ändern Sie die Mobilitätsrichtlinie nach Standort</span><span class="sxs-lookup"><span data-stu-id="fae41-132">To modify mobility policy by site</span></span>

1.  <span data-ttu-id="fae41-133">Melden Sie sich an einem beliebigen Computer an, auf dem lync Server-Verwaltungsshell und OCSCore als Mitglied der CsAdministrator-Rolle installiert sind.</span><span class="sxs-lookup"><span data-stu-id="fae41-133">Log on to any computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="fae41-134">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="fae41-134">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="fae41-135">Erstellen Sie eine Richtlinie auf Standortebene, und schalten Sie VoIP und Video aus, und aktivieren Sie WLAN für IP-Audio und IP-Video nach Standort.</span><span class="sxs-lookup"><span data-stu-id="fae41-135">Create a site-level policy, and turn off VoIP and video, and enable Require WiFi for IP Audio and for IP Video by site.</span></span> <span data-ttu-id="fae41-136">Geben Sie in die Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="fae41-136">At the command line, type:</span></span>
    
        New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $False -RequireWiFiForIPAudio $True -RequireWiFiForIPVideo $True

</div>

<div>

## <a name="to-modify-mobility-policy-by-user"></a><span data-ttu-id="fae41-137">So ändern Sie die Mobilitätsrichtlinie nach Benutzer</span><span class="sxs-lookup"><span data-stu-id="fae41-137">To modify mobility policy by user</span></span>

1.  <span data-ttu-id="fae41-138">Melden Sie sich an einem beliebigen Computer an, auf dem lync Server-Verwaltungsshell und OCSCore als Mitglied der CsAdministrator-Rolle installiert sind.</span><span class="sxs-lookup"><span data-stu-id="fae41-138">Log on to any computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="fae41-139">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="fae41-139">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="fae41-p108">Erstellen Sie Mobilitätsrichtlinien auf Benutzerebene, und deaktivieren Sie den Zugriff auf die Mobilität und Geschäftlich anrufen nach Benutzer. Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="fae41-p108">Create user level mobility policies and turn off mobility and Call via Work by user. At the command line, type:</span></span>
    
        New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
    
    <span data-ttu-id="fae41-p109">Sie können auch nur den Zugriff auf das Feature Geschäftlich anrufen deaktivieren, ohne den Zugriff auf die Mobilität zu deaktivieren. Es ist jedoch nicht möglich, den Zugriff auf die Mobilität deaktivieren, ohne auch den Zugriff auf Geschäftlich anrufen zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="fae41-p109">You can turn off Call via Work without turning off access to mobility. However, you cannot turn off mobility without also turning off Call via Work.</span></span>
    
    <span data-ttu-id="fae41-144">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="fae41-144">For example:</span></span>
    
        New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity -MobileUser1@contoso.com -PolicyName Tag:disableOutsideVoice

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fae41-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fae41-145">See Also</span></span>


[<span data-ttu-id="fae41-146">Deaktivieren oder erneutes Aktivieren des Benutzerkontos für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fae41-146">Disable or re-enable user account for Lync Server 2013</span></span>](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[<span data-ttu-id="fae41-147">Aktivieren von Benutzern für Enterprise-VoIP in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fae41-147">Enable users for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-enable-users-for-enterprise-voice.md)  
[<span data-ttu-id="fae41-148">Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fae41-148">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  


[<span data-ttu-id="fae41-149">Definieren der Mobilitätsanforderungen für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fae41-149">Defining your mobility requirements for Lync Server 2013</span></span>](lync-server-2013-defining-your-mobility-requirements.md)  


[<span data-ttu-id="fae41-150">New-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="fae41-150">New-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy)  
[<span data-ttu-id="fae41-151">Gruppe-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="fae41-151">Set-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy)  
[<span data-ttu-id="fae41-152">Get-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="fae41-152">Get-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy)  
[<span data-ttu-id="fae41-153">Grant-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="fae41-153">Grant-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy)  
[<span data-ttu-id="fae41-154">Remove-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="fae41-154">Remove-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

