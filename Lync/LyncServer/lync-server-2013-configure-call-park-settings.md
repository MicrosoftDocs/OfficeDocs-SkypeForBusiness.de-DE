---
title: 'Lync Server 2013: Konfigurieren der Einstellungen für den Anruf Park'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Call Park settings
ms:assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425886(v=OCS.15)
ms:contentKeyID: 48183922
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee4f12ccf614816e27262f8b393cdc1dac4a7a5e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757779"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-call-park-settings-in-lync-server-2013"></a><span data-ttu-id="c9c3b-102">Konfigurieren von Einstellungen für den Anruf Park in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9c3b-102">Configure Call Park settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9c3b-103">_**Letztes Änderungsdatum des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="c9c3b-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="c9c3b-104">Wenn Sie die Standardeinstellungen für den Anruf Park nicht verwenden möchten, können Sie diese anpassen.</span><span class="sxs-lookup"><span data-stu-id="c9c3b-104">If you don't want to use default Call Park settings, you can customize them.</span></span> <span data-ttu-id="c9c3b-105">Wenn Sie die Anwendung zum Parken von Anrufen installieren, werden standardmäßig die globalen Einstellungen konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="c9c3b-105">When you install the Call Park application, global settings are configured by default.</span></span> <span data-ttu-id="c9c3b-106">Sie können die globalen Einstellungen ändern und außerdem standortspezifische Einstellungen angeben.</span><span class="sxs-lookup"><span data-stu-id="c9c3b-106">You can modify the global settings, and you can also specify site-specific settings.</span></span> <span data-ttu-id="c9c3b-107">Verwenden Sie das Cmdlet **New-CsCpsConfiguration**, um neue standortspezifische Einstellungen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c9c3b-107">Use the **New-CsCpsConfiguration** cmdlet to create new site-specific settings.</span></span> <span data-ttu-id="c9c3b-108">Verwenden Sie das Cmdlet **Set-CsCpsConfiguration**, um vorhandene Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="c9c3b-108">Use the **Set-CsCpsConfiguration** cmdlet to modify existing settings.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c9c3b-109">Es wird empfohlen, mindestens die Option <STRONG>OnTimeoutURI</STRONG> zu konfigurieren, um ein Fallbackziel anzugeben, das bei Auftreten einer Zeitüberschreitung für geparkte Anrufe und bei erfolglosen Rückrufversuchen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c9c3b-109">At a minimum, we recommend that you configure the <STRONG>OnTimeoutURI</STRONG> option for the fallback destination to use when a parked call times out and ringback fails.</span></span>



</div>

<span data-ttu-id="c9c3b-110">Verwenden Sie das Cmdlet **New-CsCpsConfiguration** oder das Cmdlet **Set-CsCpsConfiguration**, um beliebige der folgenden Einstellungen zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="c9c3b-110">Use **New-CsCpsConfiguration** cmdlet or the **Set-CsCpsConfiguration** cmdlet to configure any of the following settings:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c9c3b-111">Option</span><span class="sxs-lookup"><span data-stu-id="c9c3b-111">This option:</span></span></th>
<th><span data-ttu-id="c9c3b-112">Festlegung</span><span class="sxs-lookup"><span data-stu-id="c9c3b-112">Specifies this:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c9c3b-113"><strong>CallPickupTimeoutThreshold</strong></span><span class="sxs-lookup"><span data-stu-id="c9c3b-113"><strong>CallPickupTimeoutThreshold</strong></span></span></p></td>
<td><p><span data-ttu-id="c9c3b-114">Die Zeitspanne, die nach dem Parken eines Anrufs verstreicht, bis das Telefon zurückgerufen wird, an dem der Anruf entgegengenommen wurde.</span><span class="sxs-lookup"><span data-stu-id="c9c3b-114">The amount of time that elapses after a call has been parked before it rings back to the phone where the call was answered.</span></span></p>
<p><span data-ttu-id="c9c3b-p102">Der Wert muss im Format „hh:mm:ss“ eingegeben werden, um die Stunden, Minuten und Sekunden anzugeben. Der Mindestwert beträgt 10 Sekunden, der Maximalwert liegt bei 10 Minuten. Der Standardwert lautet „00:01:30“.</span><span class="sxs-lookup"><span data-stu-id="c9c3b-p102">The value must be entered in the format hh:mm:ss to specify the hours, minutes, and seconds. The minimum value is 10 seconds, and the maximum value is 10 minutes. The default is 00:01:30.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9c3b-118"><strong>EnableMusicOnHold</strong></span><span class="sxs-lookup"><span data-stu-id="c9c3b-118"><strong>EnableMusicOnHold</strong></span></span></p></td>
<td><p><span data-ttu-id="c9c3b-119">Legt fest, ob der Anrufer eines geparkten Anrufs Wartemusik hört.</span><span class="sxs-lookup"><span data-stu-id="c9c3b-119">Whether music plays for a caller while a call is parked.</span></span></p>
<p><span data-ttu-id="c9c3b-p103">Gültige Werte sind „True“ oder „False“. Der Standardwert lautet „True“.</span><span class="sxs-lookup"><span data-stu-id="c9c3b-p103">Values are True or False. The default is True.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9c3b-122"><strong>MaxCallPickupAttempts</strong></span><span class="sxs-lookup"><span data-stu-id="c9c3b-122"><strong>MaxCallPickupAttempts</strong></span></span></p></td>
<td><p><span data-ttu-id="c9c3b-p104">Die Anzahl von Rückrufversuchen, die für einen geparkten Anruf bei dem Telefon erfolgt, an dem der Anruf entgegengenommen wurde, bevor der Anruf an den Fallback-URI (Uniform Resource Identifier) weitergeleitet wird, der für <strong>OnTimeoutURI</strong> angegeben ist. Der Standardwert ist 1.</span><span class="sxs-lookup"><span data-stu-id="c9c3b-p104">The number of times a parked call rings back to the answering phone before it is forwarded to the fallback Uniform Resource Identifier (URI) that is specified for <strong>OnTimeoutURI</strong>. The default is 1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9c3b-125"><strong>OnTimeoutURI</strong></span><span class="sxs-lookup"><span data-stu-id="c9c3b-125"><strong>OnTimeoutURI</strong></span></span></p></td>
<td><p><span data-ttu-id="c9c3b-126">Die SIP-Adresse des Benutzers oder der Reaktionsgruppe, an die ein nicht beantworteter geparkter Anruf geroutet wird, wenn <strong>MaxCallPickupAttempts</strong> überschritten wird.</span><span class="sxs-lookup"><span data-stu-id="c9c3b-126">The SIP address of the user or response group to which an unanswered parked call is routed when <strong>MaxCallPickupAttempts</strong> is exceeded.</span></span></p>
<p><span data-ttu-id="c9c3b-p105">Bei diesem Wert muss es sich um einen SIP-URI handeln, der mit „sip:“ beginnt. Beispiel: sip:bob@contoso.com. In der Standardeinstellung ist keine Weiterleitungsadresse angegeben.</span><span class="sxs-lookup"><span data-stu-id="c9c3b-p105">Value must be a SIP URI beginning with the string sip:. For example, sip:bob@contoso.com. The default is no forwarding address.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-call-park-settings"></a><span data-ttu-id="c9c3b-130">So konfigurieren Sie die Einstellungen für den Anruf Park</span><span class="sxs-lookup"><span data-stu-id="c9c3b-130">To configure Call Park settings</span></span>

1.  <span data-ttu-id="c9c3b-131">Melden Sie sich bei dem Computer an, auf dem die lync Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe oder mit den erforderlichen Benutzerrechten installiert ist, wie unter [Delegieren von Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c9c3b-131">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="c9c3b-132">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="c9c3b-132">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="c9c3b-133">Führen Sie folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="c9c3b-133">Run:</span></span>
    
        New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="c9c3b-134">Verwenden Sie das Cmdlet <STRONG>Get-CsSite</STRONG>, um den Standort zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="c9c3b-134">Use the <STRONG>Get-CsSite</STRONG> cmdlet to identify the site.</span></span> <span data-ttu-id="c9c3b-135">Ausführliche Informationen finden Sie unter Dokumentation zur lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="c9c3b-135">For details, see Lync Server Management Shell documentation.</span></span>

    
    </div>
    
    <span data-ttu-id="c9c3b-136">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c9c3b-136">For example:</span></span>
    
        New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c9c3b-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c9c3b-137">See Also</span></span>


[<span data-ttu-id="c9c3b-138">Anpassen der Musik zum Parken von Anrufen im Wartebereich in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9c3b-138">Customize Call Park music on hold in Lync Server 2013</span></span>](lync-server-2013-customize-call-park-music-on-hold.md)  


[<span data-ttu-id="c9c3b-139">Neu – CsCpsConfiguration</span><span class="sxs-lookup"><span data-stu-id="c9c3b-139">New-CsCpsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsCpsConfiguration)  
[<span data-ttu-id="c9c3b-140">Satz-CsCpsConfiguration</span><span class="sxs-lookup"><span data-stu-id="c9c3b-140">Set-CsCpsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCpsConfiguration)  
[<span data-ttu-id="c9c3b-141">Get-CsSite</span><span class="sxs-lookup"><span data-stu-id="c9c3b-141">Get-CsSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsSite)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

