---
title: Konfigurieren von Einstellungen für das Parken von Anrufen in Skype for Business 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
description: Ändern des Parkens von Anrufen in Skype für Business Server Enterprise-VoIP.
ms.openlocfilehash: 56b0e2508fda61bddc94a6f8813708e8186c99c7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="configure-call-park-settings-in-skype-for-business-2015"></a>Konfigurieren von Einstellungen für das Parken von Anrufen in Skype for Business 2015
 
Ändern des Parkens von Anrufen in Skype für Business Server Enterprise-VoIP.
  
Wenn Sie nicht Parken Standardeinstellungen verwenden möchten, können Sie diese anpassen. Bei der Installation der Anwendung zum Parken werden globale Einstellungen standardmäßig konfiguriert. Sie können die globalen Einstellungen ändern und außerdem standortspezifische Einstellungen angeben. Verwenden Sie das Cmdlet **New-CsCpsConfiguration** , um neue websitespezifischen Einstellungen zu erstellen. Verwenden Sie das Cmdlet **Set-CsCpsConfiguration** , um vorhandene Einstellungen zu ändern.
  
> [!NOTE]
> Es wird empfohlen, mindestens die Option **OnTimeoutURI** zu konfigurieren, um ein Fallbackziel anzugeben, das bei Auftreten einer Zeitüberschreitung für geparkte Anrufe und bei erfolglosen Rückrufversuchen verwendet wird.
  
Verwenden Sie Cmdlet **New-CsCpsConfiguration** oder **Set-CsCpsConfiguration** -Cmdlet, um beliebige der folgenden Einstellungen zu konfigurieren:
  
|**Diese Option:**|**Dadurch angegeben:**|
|:-----|:-----|
|**CallPickupTimeoutThreshold** <br/> |Die Zeitspanne, die nach dem Parken eines Anrufs verstreicht, bis das Telefon zurückgerufen wird, an dem der Anruf entgegengenommen wurde.  <br/> Der Wert muss im Format „hh:mm:ss“ eingegeben werden, um die Stunden, Minuten und Sekunden anzugeben. Der Mindestwert beträgt 10 Sekunden, der Maximalwert liegt bei 10 Minuten. Der Standardwert lautet „00:01:30“.  <br/> |
|**EnableMusicOnHold** <br/> |Legt fest, ob der Anrufer eines geparkten Anrufs Wartemusik hört.  <br/> Gültige Werte sind „True“ oder „False“. Der Standardwert lautet „True“.  <br/> |
|**MaxCallPickupAttempts** <br/> |Die Anzahl von Rückrufversuchen, die für einen geparkten Anruf bei dem Telefon erfolgt, an dem der Anruf entgegengenommen wurde, bevor der Anruf an den Fallback-URI (Uniform Resource Identifier) weitergeleitet wird, der für **OnTimeoutURI** angegeben ist. Der Standardwert ist 1.<br/> |
|**Fallbackziel** <br/> |Die SIP-Adresse des Benutzers oder der Reaktionsgruppe, an die ein nicht beantworteter geparkter Anruf geroutet wird, wenn **MaxCallPickupAttempts** überschritten wird. <br/> Bei diesem Wert muss es sich um einen SIP-URI handeln, der mit „sip:“ beginnt. Beispiel: sip:bob@contoso.com. In der Standardeinstellung ist keine Weiterleitungsadresse angegeben.<br/> |
   
### <a name="to-configure-call-park-settings"></a>So konfigurieren Sie Einstellungen für das Parken von Anrufen

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
2. Führen Sie folgenden Befehl aus:
    
   ```
   New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
   ```

   > [!TIP]
   > Verwenden Sie das Cmdlet " **Get-CsSite** ", um die Website zu identifizieren. Weitere Informationen hierzu finden Sie unter Dokumentation zur Lync Server-Verwaltungsshell.
  
    Beispiel:
    
   ```
   New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com
   ```

## <a name="see-also"></a>Siehe auch

#### 

[Anpassen des Parkens von Anrufen Musik in der Warteschleife InSkype für Business 2015](customize-call-park-music-on-hold.md)
#### 

[New-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscpsconfiguration?view=skype-ps)
  
[Set-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscpsconfiguration?view=skype-ps)
  
[Get-CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps)

