---
title: Konfigurieren von Einstellungen für den Anruf Park in Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
description: Ändern Sie die Einstellungen für den Anruf Park in Skype for Business Server Enterprise Voice.
ms.openlocfilehash: e9410d3b088e5978588de991aeaa9da73327f50a
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768128"
---
# <a name="configure-call-park-settings-in-skype-for-business"></a><span data-ttu-id="af8da-103">Konfigurieren von Einstellungen für den Anruf Park in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="af8da-103">Configure Call Park settings in Skype for Business</span></span>

<span data-ttu-id="af8da-104">Ändern Sie die Einstellungen für den Anruf Park in Skype for Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="af8da-104">Modify Call Park settings in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="af8da-105">Wenn Sie die Standardeinstellungen für den Anruf Park nicht verwenden möchten, können Sie diese anpassen.</span><span class="sxs-lookup"><span data-stu-id="af8da-105">If you don't want to use default Call Park settings, you can customize them.</span></span> <span data-ttu-id="af8da-106">Wenn Sie die Anwendung zum Parken von Anrufen installieren, werden standardmäßig die globalen Einstellungen konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="af8da-106">When you install the Call Park application, global settings are configured by default.</span></span> <span data-ttu-id="af8da-107">Sie können die globalen Einstellungen ändern und außerdem standortspezifische Einstellungen angeben.</span><span class="sxs-lookup"><span data-stu-id="af8da-107">You can modify the global settings, and you can also specify site-specific settings.</span></span> <span data-ttu-id="af8da-108">Verwenden Sie das Cmdlet **New-CsCpsConfiguration**, um neue standortspezifische Einstellungen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="af8da-108">Use the **New-CsCpsConfiguration** cmdlet to create new site-specific settings.</span></span> <span data-ttu-id="af8da-109">Verwenden Sie das Cmdlet **Set-CsCpsConfiguration**, um vorhandene Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="af8da-109">Use the **Set-CsCpsConfiguration** cmdlet to modify existing settings.</span></span>

> [!NOTE]
> <span data-ttu-id="af8da-110">Es wird empfohlen, mindestens die Option **OnTimeoutURI** zu konfigurieren, um ein Fallbackziel anzugeben, das bei Auftreten einer Zeitüberschreitung für geparkte Anrufe und bei erfolglosen Rückrufversuchen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="af8da-110">At a minimum, we recommend that you configure the **OnTimeoutURI** option for the fallback destination to use when a parked call times out and ringback fails.</span></span>

<span data-ttu-id="af8da-111">Verwenden Sie das Cmdlet **New-CsCpsConfiguration** oder das Cmdlet **Set-CsCpsConfiguration**, um beliebige der folgenden Einstellungen zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="af8da-111">Use **New-CsCpsConfiguration** cmdlet or the **Set-CsCpsConfiguration** cmdlet to configure any of the following settings:</span></span>


| <span data-ttu-id="af8da-112">**Option**</span><span class="sxs-lookup"><span data-stu-id="af8da-112">**This option:**</span></span>                     | <span data-ttu-id="af8da-113">**Festlegung**</span><span class="sxs-lookup"><span data-stu-id="af8da-113">**Specifies this:**</span></span>                                                                                                                                                                                                                                                                                                                   |
|:-------------------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="af8da-114">**CallPickupTimeoutThreshold**</span><span class="sxs-lookup"><span data-stu-id="af8da-114">**CallPickupTimeoutThreshold**</span></span> <br/> | <span data-ttu-id="af8da-115">Die Zeitspanne, die nach dem Parken eines Anrufs verstreicht, bis das Telefon zurückgerufen wird, an dem der Anruf entgegengenommen wurde.</span><span class="sxs-lookup"><span data-stu-id="af8da-115">The amount of time that elapses after a call has been parked before it rings back to the phone where the call was answered.</span></span>  <br/> <span data-ttu-id="af8da-p102">Der Wert muss im Format „hh:mm:ss“ eingegeben werden, um die Stunden, Minuten und Sekunden anzugeben. Der Mindestwert beträgt 10 Sekunden, der Maximalwert liegt bei 10 Minuten. Der Standardwert lautet „00:01:30“.</span><span class="sxs-lookup"><span data-stu-id="af8da-p102">The value must be entered in the format hh:mm:ss to specify the hours, minutes, and seconds. The minimum value is 10 seconds, and the maximum value is 10 minutes. The default is 00:01:30.</span></span>  <br/> |
| <span data-ttu-id="af8da-119">**EnableMusicOnHold**</span><span class="sxs-lookup"><span data-stu-id="af8da-119">**EnableMusicOnHold**</span></span> <br/>          | <span data-ttu-id="af8da-120">Legt fest, ob der Anrufer eines geparkten Anrufs Wartemusik hört.</span><span class="sxs-lookup"><span data-stu-id="af8da-120">Whether music plays for a caller while a call is parked.</span></span>  <br/> <span data-ttu-id="af8da-p103">Gültige Werte sind „True“ oder „False“. Der Standardwert lautet „True“.</span><span class="sxs-lookup"><span data-stu-id="af8da-p103">Values are True or False. The default is True.</span></span>  <br/>                                                                                                                                                                                                                 |
| <span data-ttu-id="af8da-123">**MaxCallPickupAttempts**</span><span class="sxs-lookup"><span data-stu-id="af8da-123">**MaxCallPickupAttempts**</span></span> <br/>      | <span data-ttu-id="af8da-p104">Die Anzahl von Rückrufversuchen, die für einen geparkten Anruf bei dem Telefon erfolgt, an dem der Anruf entgegengenommen wurde, bevor der Anruf an den Fallback-URI (Uniform Resource Identifier) weitergeleitet wird, der für **OnTimeoutURI** angegeben ist. Der Standardwert ist 1.</span><span class="sxs-lookup"><span data-stu-id="af8da-p104">The number of times a parked call rings back to the answering phone before it is forwarded to the fallback Uniform Resource Identifier (URI) that is specified for **OnTimeoutURI**. The default is 1.  </span></span><br/>                                                                                                                         |
| <span data-ttu-id="af8da-126">**OnTimeoutURI**</span><span class="sxs-lookup"><span data-stu-id="af8da-126">**OnTimeoutURI**</span></span> <br/>               | <span data-ttu-id="af8da-127">Die SIP-Adresse des Benutzers oder der Reaktionsgruppe, an die ein nicht beantworteter geparkter Anruf geroutet wird, wenn **MaxCallPickupAttempts** überschritten wird.</span><span class="sxs-lookup"><span data-stu-id="af8da-127">The SIP address of the user or response group to which an unanswered parked call is routed when **MaxCallPickupAttempts** is exceeded.</span></span> <br/> <span data-ttu-id="af8da-p105">Bei diesem Wert muss es sich um einen SIP-URI handeln, der mit „sip:“ beginnt. Beispiel: sip:bob@contoso.com. In der Standardeinstellung ist keine Weiterleitungsadresse angegeben.</span><span class="sxs-lookup"><span data-stu-id="af8da-p105">Value must be a SIP URI beginning with the string sip:. For example, sip:bob@contoso.com. The default is no forwarding address.  </span></span><br/>                                                   |

### <a name="to-configure-call-park-settings"></a><span data-ttu-id="af8da-131">So konfigurieren Sie die Einstellungen für den Anruf Park</span><span class="sxs-lookup"><span data-stu-id="af8da-131">To configure Call Park settings</span></span>

1. <span data-ttu-id="af8da-132">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="af8da-132">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="af8da-133">Führen Sie folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="af8da-133">Run:</span></span>

   ```powershell
   New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
   ```

   > [!TIP]
   > <span data-ttu-id="af8da-134">Verwenden Sie das Cmdlet **Get-CsSite**, um den Standort zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="af8da-134">Use the **Get-CsSite** cmdlet to identify the site.</span></span> <span data-ttu-id="af8da-135">Ausführliche Informationen finden Sie unter Dokumentation zur Skype for Business Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="af8da-135">For details, see Skype for Business Server Management Shell documentation.</span></span>

    <span data-ttu-id="af8da-136">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="af8da-136">For example:</span></span>

   ```powershell
   New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com
   ```

## <a name="see-also"></a><span data-ttu-id="af8da-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="af8da-137">See also</span></span>

[<span data-ttu-id="af8da-138">Anpassen der Wartemusik für das Parken von Anrufen in Skype for Business 2015</span><span class="sxs-lookup"><span data-stu-id="af8da-138">Customize Call Park music on hold inSkype for Business 2015</span></span>](customize-call-park-music-on-hold.md)

[<span data-ttu-id="af8da-139">Neu – CsCpsConfiguration</span><span class="sxs-lookup"><span data-stu-id="af8da-139">New-CsCpsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscpsconfiguration?view=skype-ps)

[<span data-ttu-id="af8da-140">Satz-CsCpsConfiguration</span><span class="sxs-lookup"><span data-stu-id="af8da-140">Set-CsCpsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscpsconfiguration?view=skype-ps)

[<span data-ttu-id="af8da-141">Get-CsSite</span><span class="sxs-lookup"><span data-stu-id="af8da-141">Get-CsSite</span></span>](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps)
