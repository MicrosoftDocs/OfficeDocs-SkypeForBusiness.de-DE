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
ms.openlocfilehash: 39a7f0791def99e0b42a57b1f13aae88abbfafa4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763399"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-mobility-policy-in-lync-server-2013"></a><span data-ttu-id="4cbf0-102">Konfigurieren der Mobilitätsrichtlinie in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4cbf0-102">Configuring mobility policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4cbf0-103">_**Letztes Änderungsdatum des Themas:** 2013-02-13_</span><span class="sxs-lookup"><span data-stu-id="4cbf0-103">_**Topic Last Modified:** 2013-02-13_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="4cbf0-104">Lync Server 2013 bietet mobilitätsrichtlinien, die bestimmen, wer Mobilitätsfunktionen nutzen, über Arbeit anrufen, VoIP (Voice over IP) oder Video verwenden kann und ob WLAN für VoIP oder Video erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="4cbf0-104">Lync Server 2013 provides mobility policies that determine who can use mobility features, Call via Work, voice over IP (VoIP) or video, and whether WiFi will be required for either VoIP or video.</span></span> <span data-ttu-id="4cbf0-105">Mit der Funktion Anruf über Arbeit kann ein Mobilfunknutzer Anrufe auf einem Mobiltelefon tätigen und empfangen, indem er eine geschäftliche Telefonnummer anstelle der Mobiltelefonnummer verwendet.</span><span class="sxs-lookup"><span data-stu-id="4cbf0-105">The Call via Work feature enables a mobile user to make and receive calls on a mobile phone by using a work phone number instead of the mobile phone number.</span></span> <span data-ttu-id="4cbf0-106">Dieses Feature verhindert, dass der angerufene die Handynummer des Anrufers sieht und es einem Benutzer ermöglicht, ausgehende Gebühren zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="4cbf0-106">This feature prevents the called party from seeing the caller's mobile phone number and enables a user to avoid outbound calling charges.</span></span> <span data-ttu-id="4cbf0-107">Die Konfiguration von VoIP und Video ermöglicht es Benutzern, VoIP-Anrufe und Videos zu empfangen und zu führen.</span><span class="sxs-lookup"><span data-stu-id="4cbf0-107">Configuring VoIP and video makes it possible for users to receive and make VoIP calls and video.</span></span> <span data-ttu-id="4cbf0-108">Einstellungen für die WLAN-Nutzung definieren, ob das Gerät eines Benutzers ein WLAN-Netzwerk über ein Mobilfunknetz verwenden muss.</span><span class="sxs-lookup"><span data-stu-id="4cbf0-108">Settings for WiFi usage define if a user’s device will be required to use a WiFi network over a cellular data network.</span></span>

<span data-ttu-id="4cbf0-109">Standardmäßig sind Mobilität, Anruf über die Arbeit und die VoIP-und Videofunktionen aktiviert.</span><span class="sxs-lookup"><span data-stu-id="4cbf0-109">By default, mobility, Call via Work, and the VoIP and video features are enabled.</span></span> <span data-ttu-id="4cbf0-110">Die Einstellungen für WLAN für VoIP und Video sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="4cbf0-110">The settings to require WiFi for VoIp and video are disabled.</span></span> <span data-ttu-id="4cbf0-111">Administratoren können ermitteln, wer Zugriff auf diese Features hat, indem Sie ein Cmdlet ausführen.</span><span class="sxs-lookup"><span data-stu-id="4cbf0-111">Administrators can determine who has access to these features by running a cmdlet.</span></span> <span data-ttu-id="4cbf0-112">Sie können Optionen Global, nach Website oder nach Benutzer deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="4cbf0-112">You can turn options off globally, by site, or by user.</span></span>

<span data-ttu-id="4cbf0-113">Um Mobilitätsfunktionen nutzen und über die Arbeit anrufen zu können, müssen die Benutzer die folgenden Voraussetzungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="4cbf0-113">To be able to use mobility features and Call via Work, users must meet the following prerequisites:</span></span>

  - <span data-ttu-id="4cbf0-114">Benutzer müssen für lync Server 2013 aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="4cbf0-114">Users must be enabled for Lync Server 2013.</span></span>

  - <span data-ttu-id="4cbf0-115">Benutzer müssen für Enterprise-VoIP aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="4cbf0-115">Users must be enabled for Enterprise Voice.</span></span>

  - <span data-ttu-id="4cbf0-116">Benutzern muss eine Mobilitätsrichtlinie zugewiesen werden, bei der die **EnableMobility** -Option auf "true" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="4cbf0-116">Users must be assigned a mobility policy that has the **EnableMobility** option set to True.</span></span>

<span data-ttu-id="4cbf0-117">Damit Benutzer den Anruf über die Arbeit nutzen können, müssen Sie die beiden folgenden zusätzlichen Voraussetzungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="4cbf0-117">For users to be able to use Call via Work, they must meet the following two additional prerequisites:</span></span>

  - <span data-ttu-id="4cbf0-118">Benutzern muss eine VoIP-Richtlinie zugewiesen sein, für die die Option **gleichzeitiges Anrufen von Telefonen aktivieren** aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="4cbf0-118">Users must be assigned a voice policy that has the **Enable simultaneous ringing of phones** option selected.</span></span>

  - <span data-ttu-id="4cbf0-119">Benutzern muss eine Mobilitätsrichtlinie zugewiesen werden, bei der die **EnableOutsideVoice** -Option auf "true" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="4cbf0-119">Users must be assigned a mobility policy that has the **EnableOutsideVoice** option set to True.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4cbf0-120">Benutzer, die nicht für Enterprise-VoIP aktiviert sind, können Ihre mobilen Geräte verwenden, um lync zu lync-VoIP-Anrufen (Voice over IP) zu machen oder an Konferenzen teilzunehmen, indem Sie auf Ihren mobilen Geräten über den Link zum teilnehmen klicken, wenn Sie diesen Benutzern die entsprechenden Optionen für VoIP-Richtlinien zuweisen.</span><span class="sxs-lookup"><span data-stu-id="4cbf0-120">Users who are not enabled for Enterprise Voice can use their mobile devices to make Lync to Lync Voice over IP (VoIP) calls, or can join conferences by using the Click to Join link on their mobile devices, if you assign those users the appropriate options for voice policy.</span></span> <span data-ttu-id="4cbf0-121">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-defining-your-mobility-requirements.md">Definieren Ihrer Mobilitätsanforderungen für lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="4cbf0-121">For details, see <A href="lync-server-2013-defining-your-mobility-requirements.md">Defining your mobility requirements for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="4cbf0-122">Details zum Aktivieren von Benutzern für lync Server 2013 finden Sie unter [deaktivieren oder erneutes Aktivieren des Benutzerkontos für lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md).</span><span class="sxs-lookup"><span data-stu-id="4cbf0-122">For details about enabling users for Lync Server 2013, see [Disable or re-enable user account for Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md).</span></span> <span data-ttu-id="4cbf0-123">Details zum Aktivieren von Benutzern für Enterprise-VoIP finden Sie unter [Aktivieren von Benutzern für Enterprise-VoIP in lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span><span class="sxs-lookup"><span data-stu-id="4cbf0-123">For details about enabling users for Enterprise Voice, see [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span></span> <span data-ttu-id="4cbf0-124">Details zum Festlegen von VoIP-Richtlinienoptionen finden Sie unter [Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md).</span><span class="sxs-lookup"><span data-stu-id="4cbf0-124">For details about setting voice policy options, see [Modify a voice policy and configure PSTN usage records in Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md).</span></span>

<div>

## <a name="to-modify-global-mobility-policy"></a><span data-ttu-id="4cbf0-125">So ändern Sie die globale Mobilitätsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="4cbf0-125">To modify global mobility policy</span></span>

1.  <span data-ttu-id="4cbf0-126">Melden Sie sich bei einem beliebigen Computer an, auf dem die lync Server-Verwaltungsshell und OCSCore als Mitglied der CsAdministrator-Rolle installiert sind.</span><span class="sxs-lookup"><span data-stu-id="4cbf0-126">Log on to any computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="4cbf0-127">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="4cbf0-127">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="4cbf0-128">Deaktivieren Sie den Zugriff auf Mobilität, und rufen Sie über die Arbeit weltweit an.</span><span class="sxs-lookup"><span data-stu-id="4cbf0-128">Turn off access to mobility and Call via Work globally.</span></span> <span data-ttu-id="4cbf0-129">Geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="4cbf0-129">At the command line, type:</span></span>
    
        Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4cbf0-130">Sie können den Anruf über die Arbeit ausschalten, ohne den Zugriff auf Mobilität zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="4cbf0-130">You can turn off Call via Work without turning off access to mobility.</span></span> <span data-ttu-id="4cbf0-131">Sie können die Mobilität jedoch nicht deaktivieren, ohne dass Sie den Anruf über die Arbeit abschalten.</span><span class="sxs-lookup"><span data-stu-id="4cbf0-131">However, you cannot turn off mobility without also turning off Call via Work.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-mobility-policy-by-site"></a><span data-ttu-id="4cbf0-132">So ändern Sie die mobilitätsrichtlinien nach Website</span><span class="sxs-lookup"><span data-stu-id="4cbf0-132">To modify mobility policy by site</span></span>

1.  <span data-ttu-id="4cbf0-133">Melden Sie sich bei einem beliebigen Computer an, auf dem die lync Server-Verwaltungsshell und OCSCore als Mitglied der CsAdministrator-Rolle installiert sind.</span><span class="sxs-lookup"><span data-stu-id="4cbf0-133">Log on to any computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="4cbf0-134">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="4cbf0-134">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="4cbf0-135">Erstellen Sie eine Richtlinie auf Websiteebene, und deaktivieren Sie VoIP und Video, und aktivieren Sie WLAN für IP-Audio und für IP-Video nach Website anfordern.</span><span class="sxs-lookup"><span data-stu-id="4cbf0-135">Create a site-level policy, and turn off VoIP and video, and enable Require WiFi for IP Audio and for IP Video by site.</span></span> <span data-ttu-id="4cbf0-136">Geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="4cbf0-136">At the command line, type:</span></span>
    
        New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $False -RequireWiFiForIPAudio $True -RequireWiFiForIPVideo $True

</div>

<div>

## <a name="to-modify-mobility-policy-by-user"></a><span data-ttu-id="4cbf0-137">So ändern Sie die mobilitätsrichtlinien nach Benutzern</span><span class="sxs-lookup"><span data-stu-id="4cbf0-137">To modify mobility policy by user</span></span>

1.  <span data-ttu-id="4cbf0-138">Melden Sie sich bei einem beliebigen Computer an, auf dem die lync Server-Verwaltungsshell und OCSCore als Mitglied der CsAdministrator-Rolle installiert sind.</span><span class="sxs-lookup"><span data-stu-id="4cbf0-138">Log on to any computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="4cbf0-139">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="4cbf0-139">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="4cbf0-140">Erstellen Sie mobilitätsrichtlinien auf Benutzerebene, deaktivieren Sie Mobilität, und rufen Sie Sie über die Arbeit des Benutzers an.</span><span class="sxs-lookup"><span data-stu-id="4cbf0-140">Create user level mobility policies and turn off mobility and Call via Work by user.</span></span> <span data-ttu-id="4cbf0-141">Geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="4cbf0-141">At the command line, type:</span></span>
    
        New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
    
    <span data-ttu-id="4cbf0-142">Sie können den Anruf über die Arbeit ausschalten, ohne den Zugriff auf Mobilität zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="4cbf0-142">You can turn off Call via Work without turning off access to mobility.</span></span> <span data-ttu-id="4cbf0-143">Sie können die Mobilität jedoch nicht deaktivieren, ohne dass Sie den Anruf über die Arbeit abschalten.</span><span class="sxs-lookup"><span data-stu-id="4cbf0-143">However, you cannot turn off mobility without also turning off Call via Work.</span></span>
    
    <span data-ttu-id="4cbf0-144">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="4cbf0-144">For example:</span></span>
    
        New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity -MobileUser1@contoso.com -PolicyName Tag:disableOutsideVoice

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4cbf0-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4cbf0-145">See Also</span></span>


[<span data-ttu-id="4cbf0-146">Deaktivieren oder erneutes Aktivieren des Benutzerkontos für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4cbf0-146">Disable or re-enable user account for Lync Server 2013</span></span>](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[<span data-ttu-id="4cbf0-147">Aktivieren von Benutzern für Enterprise-VoIP in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4cbf0-147">Enable users for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-enable-users-for-enterprise-voice.md)  
[<span data-ttu-id="4cbf0-148">Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4cbf0-148">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  


[<span data-ttu-id="4cbf0-149">Definieren der Mobilitätsanforderungen für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4cbf0-149">Defining your mobility requirements for Lync Server 2013</span></span>](lync-server-2013-defining-your-mobility-requirements.md)  


[<span data-ttu-id="4cbf0-150">New-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="4cbf0-150">New-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy)  
[<span data-ttu-id="4cbf0-151">Set-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="4cbf0-151">Set-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy)  
[<span data-ttu-id="4cbf0-152">Get-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="4cbf0-152">Get-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy)  
[<span data-ttu-id="4cbf0-153">Grant-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="4cbf0-153">Grant-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy)  
[<span data-ttu-id="4cbf0-154">Remove-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="4cbf0-154">Remove-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

