---
title: Konfigurieren von Einstellungen für das Parken von Anrufen in Skype for Business 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
description: Ändern des Parkens von Anrufen in Skype für Business Server Enterprise-VoIP.
ms.openlocfilehash: c0aacdf23788c56d2bd0204665d5971dc715df3b
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568304"
---
# <a name="configure-call-park-settings-in-skype-for-business-2015"></a><span data-ttu-id="5838c-103">Konfigurieren von Einstellungen für das Parken von Anrufen in Skype for Business 2015</span><span class="sxs-lookup"><span data-stu-id="5838c-103">Configure Call Park settings in Skype for Business 2015</span></span>
 
<span data-ttu-id="5838c-104">Ändern des Parkens von Anrufen in Skype für Business Server Enterprise-VoIP.</span><span class="sxs-lookup"><span data-stu-id="5838c-104">Modify Call Park settings in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="5838c-105">Wenn Sie nicht Parken Standardeinstellungen verwenden möchten, können Sie diese anpassen.</span><span class="sxs-lookup"><span data-stu-id="5838c-105">If you don't want to use default Call Park settings, you can customize them.</span></span> <span data-ttu-id="5838c-106">Bei der Installation der Anwendung zum Parken werden globale Einstellungen standardmäßig konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="5838c-106">When you install the Call Park application, global settings are configured by default.</span></span> <span data-ttu-id="5838c-107">Sie können die globalen Einstellungen ändern und außerdem standortspezifische Einstellungen angeben.</span><span class="sxs-lookup"><span data-stu-id="5838c-107">You can modify the global settings, and you can also specify site-specific settings.</span></span> <span data-ttu-id="5838c-108">Verwenden Sie das Cmdlet **New-CsCpsConfiguration** , um neue websitespezifischen Einstellungen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5838c-108">Use the **New-CsCpsConfiguration** cmdlet to create new site-specific settings.</span></span> <span data-ttu-id="5838c-109">Verwenden Sie das Cmdlet **Set-CsCpsConfiguration** , um vorhandene Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="5838c-109">Use the **Set-CsCpsConfiguration** cmdlet to modify existing settings.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5838c-110">Es wird empfohlen, mindestens die Option **OnTimeoutURI** zu konfigurieren, um ein Fallbackziel anzugeben, das bei Auftreten einer Zeitüberschreitung für geparkte Anrufe und bei erfolglosen Rückrufversuchen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5838c-110">At a minimum, we recommend that you configure the **OnTimeoutURI** option for the fallback destination to use when a parked call times out and ringback fails.</span></span>
  
<span data-ttu-id="5838c-111">Verwenden Sie Cmdlet **New-CsCpsConfiguration** oder **Set-CsCpsConfiguration** -Cmdlet, um beliebige der folgenden Einstellungen zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="5838c-111">Use **New-CsCpsConfiguration** cmdlet or the **Set-CsCpsConfiguration** cmdlet to configure any of the following settings:</span></span>
  
|<span data-ttu-id="5838c-112">**Diese Option:**</span><span class="sxs-lookup"><span data-stu-id="5838c-112">**This option:**</span></span>|<span data-ttu-id="5838c-113">**Dadurch angegeben:**</span><span class="sxs-lookup"><span data-stu-id="5838c-113">**Specifies this:**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5838c-114">**CallPickupTimeoutThreshold**</span><span class="sxs-lookup"><span data-stu-id="5838c-114">**CallPickupTimeoutThreshold**</span></span> <br/> |<span data-ttu-id="5838c-115">Die Zeitspanne, die nach dem Parken eines Anrufs verstreicht, bis das Telefon zurückgerufen wird, an dem der Anruf entgegengenommen wurde.</span><span class="sxs-lookup"><span data-stu-id="5838c-115">The amount of time that elapses after a call has been parked before it rings back to the phone where the call was answered.</span></span>  <br/> <span data-ttu-id="5838c-p102">Der Wert muss im Format „hh:mm:ss“ eingegeben werden, um die Stunden, Minuten und Sekunden anzugeben. Der Mindestwert beträgt 10 Sekunden, der Maximalwert liegt bei 10 Minuten. Der Standardwert lautet „00:01:30“.</span><span class="sxs-lookup"><span data-stu-id="5838c-p102">The value must be entered in the format hh:mm:ss to specify the hours, minutes, and seconds. The minimum value is 10 seconds, and the maximum value is 10 minutes. The default is 00:01:30.</span></span>  <br/> |
|<span data-ttu-id="5838c-119">**EnableMusicOnHold**</span><span class="sxs-lookup"><span data-stu-id="5838c-119">**EnableMusicOnHold**</span></span> <br/> |<span data-ttu-id="5838c-120">Legt fest, ob der Anrufer eines geparkten Anrufs Wartemusik hört.</span><span class="sxs-lookup"><span data-stu-id="5838c-120">Whether music plays for a caller while a call is parked.</span></span>  <br/> <span data-ttu-id="5838c-p103">Gültige Werte sind „True“ oder „False“. Der Standardwert lautet „True“.</span><span class="sxs-lookup"><span data-stu-id="5838c-p103">Values are True or False. The default is True.</span></span>  <br/> |
|<span data-ttu-id="5838c-123">**MaxCallPickupAttempts**</span><span class="sxs-lookup"><span data-stu-id="5838c-123">**MaxCallPickupAttempts**</span></span> <br/> |<span data-ttu-id="5838c-p104">Die Anzahl von Rückrufversuchen, die für einen geparkten Anruf bei dem Telefon erfolgt, an dem der Anruf entgegengenommen wurde, bevor der Anruf an den Fallback-URI (Uniform Resource Identifier) weitergeleitet wird, der für **OnTimeoutURI** angegeben ist. Der Standardwert ist 1.</span><span class="sxs-lookup"><span data-stu-id="5838c-p104">The number of times a parked call rings back to the answering phone before it is forwarded to the fallback Uniform Resource Identifier (URI) that is specified for **OnTimeoutURI**. The default is 1.  </span></span><br/> |
|<span data-ttu-id="5838c-126">**Fallbackziel**</span><span class="sxs-lookup"><span data-stu-id="5838c-126">**OnTimeoutURI**</span></span> <br/> |<span data-ttu-id="5838c-127">Die SIP-Adresse des Benutzers oder der Reaktionsgruppe, an die ein nicht beantworteter geparkter Anruf geroutet wird, wenn **MaxCallPickupAttempts** überschritten wird.</span><span class="sxs-lookup"><span data-stu-id="5838c-127">The SIP address of the user or response group to which an unanswered parked call is routed when **MaxCallPickupAttempts** is exceeded.</span></span> <br/> <span data-ttu-id="5838c-p105">Bei diesem Wert muss es sich um einen SIP-URI handeln, der mit „sip:“ beginnt. Beispiel: sip:bob@contoso.com. In der Standardeinstellung ist keine Weiterleitungsadresse angegeben.</span><span class="sxs-lookup"><span data-stu-id="5838c-p105">Value must be a SIP URI beginning with the string sip:. For example, sip:bob@contoso.com. The default is no forwarding address.  </span></span><br/> |
   
### <a name="to-configure-call-park-settings"></a><span data-ttu-id="5838c-131">So konfigurieren Sie Einstellungen für das Parken von Anrufen</span><span class="sxs-lookup"><span data-stu-id="5838c-131">To configure Call Park settings</span></span>

1. <span data-ttu-id="5838c-132">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="5838c-132">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="5838c-133">Führen Sie folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="5838c-133">Run:</span></span>
    
   ```
   New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
   ```

   > [!TIP]
   > <span data-ttu-id="5838c-134">Verwenden Sie das Cmdlet " **Get-CsSite** ", um die Website zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="5838c-134">Use the **Get-CsSite** cmdlet to identify the site.</span></span> <span data-ttu-id="5838c-135">Weitere Informationen hierzu finden Sie unter Skype Dokumentation Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="5838c-135">For details, see Skype for Business Server Management Shell documentation.</span></span>
  
    <span data-ttu-id="5838c-136">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="5838c-136">For example:</span></span>
    
   ```
   New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com
   ```

## <a name="see-also"></a><span data-ttu-id="5838c-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5838c-137">See also</span></span>

[<span data-ttu-id="5838c-138">Anpassen des Parkens von Anrufen Musik in der Warteschleife InSkype für Business 2015</span><span class="sxs-lookup"><span data-stu-id="5838c-138">Customize Call Park music on hold inSkype for Business 2015</span></span>](customize-call-park-music-on-hold.md)

[<span data-ttu-id="5838c-139">New-CsCpsConfiguration</span><span class="sxs-lookup"><span data-stu-id="5838c-139">New-CsCpsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscpsconfiguration?view=skype-ps)
  
[<span data-ttu-id="5838c-140">Set-CsCpsConfiguration</span><span class="sxs-lookup"><span data-stu-id="5838c-140">Set-CsCpsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscpsconfiguration?view=skype-ps)
  
[<span data-ttu-id="5838c-141">Get-CsSite</span><span class="sxs-lookup"><span data-stu-id="5838c-141">Get-CsSite</span></span>](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps)