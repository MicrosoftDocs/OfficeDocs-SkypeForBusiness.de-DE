---
title: Konfigurieren von Einstellungen für den Anruf Park in Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
description: Ändern Sie die Einstellungen für den Anruf Park in Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 5ce9d15c4d233e620c5eb12c18688b5df958defb
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001365"
---
# <a name="configure-call-park-settings-in-skype-for-business"></a>Konfigurieren von Einstellungen für den Anruf Park in Skype for Business

Ändern Sie die Einstellungen für den Anruf Park in Skype for Business Server Enterprise Voice.

Wenn Sie die Standardeinstellungen für den Anruf Park nicht verwenden möchten, können Sie diese anpassen. Wenn Sie die Anwendung zum Parken von Anrufen installieren, werden standardmäßig die globalen Einstellungen konfiguriert. Sie können die globalen Einstellungen ändern und außerdem standortspezifische Einstellungen angeben. Verwenden Sie das Cmdlet **New-CsCpsConfiguration**, um neue standortspezifische Einstellungen zu erstellen. Verwenden Sie das Cmdlet **Set-CsCpsConfiguration**, um vorhandene Einstellungen zu ändern.

> [!NOTE]
> Es wird empfohlen, mindestens die Option **OnTimeoutURI** zu konfigurieren, um ein Fallbackziel anzugeben, das bei Auftreten einer Zeitüberschreitung für geparkte Anrufe und bei erfolglosen Rückrufversuchen verwendet wird.

Verwenden Sie das Cmdlet **New-CsCpsConfiguration** oder das Cmdlet **Set-CsCpsConfiguration**, um beliebige der folgenden Einstellungen zu konfigurieren:


| **Option**                     | **Festlegung**                                                                                                                                                                                                                                                                                                                   |
|:-------------------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **CallPickupTimeoutThreshold** <br/> | Die Zeitspanne, die nach dem Parken eines Anrufs verstreicht, bis das Telefon zurückgerufen wird, an dem der Anruf entgegengenommen wurde.  <br/> Der Wert muss im Format „hh:mm:ss“ eingegeben werden, um die Stunden, Minuten und Sekunden anzugeben. Der Mindestwert beträgt 10 Sekunden, der Maximalwert liegt bei 10 Minuten. Der Standardwert lautet „00:01:30“.  <br/> |
| **EnableMusicOnHold** <br/>          | Legt fest, ob der Anrufer eines geparkten Anrufs Wartemusik hört.  <br/> Gültige Werte sind „True“ oder „False“. Der Standardwert lautet „True“.  <br/>                                                                                                                                                                                                                 |
| **MaxCallPickupAttempts** <br/>      | Die Anzahl von Rückrufversuchen, die für einen geparkten Anruf bei dem Telefon erfolgt, an dem der Anruf entgegengenommen wurde, bevor der Anruf an den Fallback-URI (Uniform Resource Identifier) weitergeleitet wird, der für **OnTimeoutURI** angegeben ist. Der Standardwert ist 1.<br/>                                                                                                                         |
| **OnTimeoutURI** <br/>               | Die SIP-Adresse des Benutzers oder der Reaktionsgruppe, an die ein nicht beantworteter geparkter Anruf geroutet wird, wenn **MaxCallPickupAttempts** überschritten wird. <br/> Bei diesem Wert muss es sich um einen SIP-URI handeln, der mit „sip:“ beginnt. Beispiel: sip:bob@contoso.com. In der Standardeinstellung ist keine Weiterleitungsadresse angegeben.<br/>                                                   |

### <a name="to-configure-call-park-settings"></a>So konfigurieren Sie die Einstellungen für den Anruf Park

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.

2. Führen Sie folgenden Befehl aus:

   ```powershell
   New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
   ```

   > [!TIP]
   > Verwenden Sie das Cmdlet **Get-CsSite**, um den Standort zu ermitteln. Ausführliche Informationen finden Sie unter Dokumentation zur Skype for Business Server-Verwaltungsshell.

    Beispiel:

   ```powershell
   New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com
   ```

## <a name="see-also"></a>Siehe auch

[Anpassen der Wartemusik für das Parken von Anrufen in Skype for Business 2015](customize-call-park-music-on-hold.md)

[Neu – CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscpsconfiguration?view=skype-ps)

[Satz-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscpsconfiguration?view=skype-ps)

[Get-CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps)
