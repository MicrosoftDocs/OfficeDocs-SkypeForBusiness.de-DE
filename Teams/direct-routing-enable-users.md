---
title: Aktivieren von Benutzern für das direkte Routing
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Erfahren Sie, wie Sie Benutzer microsoft Phone System Direct Routing aktivieren.
ms.openlocfilehash: 858b9073106945d414c2dbe56a16e6cecd104ee7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122219"
---
# <a name="enable-users-for-direct-routing-voice-and-voicemail"></a>Aktivieren von Benutzern für Direct Routing, Voicemail und Voicemail

In diesem Artikel wird beschrieben, wie Benutzer für das direkte Routing des Telefonsystems aktiviert werden.  Dies ist Schritt 2 der folgenden Schritte zum Konfigurieren von Direct Routing:

- Schritt 1: [Verbinden des SBC mit Microsoft Phone System und Überprüfen der Verbindung](direct-routing-connect-the-sbc.md) 
- **Schritt 2. Aktivieren von Benutzern für Direct Routing, Voicemail und Voicemail**   (dieser Artikel)
- Schritt 3: [Konfigurieren des Sprachroutings](direct-routing-voice-routing.md)
- Schritt 4: [Übersetzen von Zahlen in ein alternatives Format](direct-routing-translate-numbers.md) 


Informationen zu allen schritten, die zum Einrichten von Direct Routing erforderlich sind, finden Sie unter [Konfigurieren von Direct Routing](direct-routing-configure.md).

Wenn Sie bereit sind, Benutzer für direct Routing zu aktivieren, führen Sie die folgenden Schritte aus: 

1. Erstellen Sie einen Benutzer in Microsoft 365 oder Office 365, und weisen Sie eine Telefonsystemlizenz zu. 
2. Stellen Sie sicher, dass der Benutzer in Skype for Business Online zu Hause ist. 
3. Konfigurieren Sie die Telefonnummer, und aktivieren Sie Unternehmensstimme und Voicemail. 
4. Weisen Sie Benutzern den Modus "Teams only" zu.

## <a name="create-a-user-and-assign-the-license"></a>Erstellen eines Benutzers und Zuweisen der Lizenz 

Es gibt zwei Optionen zum Erstellen eines neuen Benutzers in Microsoft 365 oder Office 365. Microsoft empfiehlt Ihrer Organisation jedoch, eine Option zu wählen, um Routingprobleme zu vermeiden: 

- Erstellen Sie den Benutzer in lokalem Active Directory, und synchronisieren Sie den Benutzer mit der Cloud. Weitere Informationen finden Sie unter Integrieren Ihrer lokalen [Verzeichnisse in Azure Active Directory.](/azure/active-directory/connect/active-directory-aadconnect)
- Erstellen Sie den Benutzer direkt im Microsoft 365 Admin Center. Weitere Informationen finden Sie unter Hinzufügen von Benutzern einzeln oder in Massen [zu Microsoft 365 oder Office 365 – Hilfe für Administratoren.](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec) 

Wenn Ihre Skype for Business Online-Bereitstellung mit Skype for Business 2015 oder Lync 2010 oder Lync 2013 lokal besteht, besteht die einzige unterstützte Option in der Erstellung des Benutzers im lokalen Active Directory und dem Synchronisieren des Benutzers mit der Cloud (Option 1). 

Informationen zu Den Lizenzanforderungen finden Sie unter [Lizenzierung und andere Anforderungen](direct-routing-plan.md#licensing-and-other-requirements) unter Planen des direkten [Routings.](direct-routing-plan.md)

## <a name="ensure-that-the-user-is-homed-online-and-phone-number-is-not-being-synced-from-on-premises-applicable-for-skype-for-business-server-enterprise-voice-enabled-users-being-migrated-to-teams-direct-routing"></a>Stellen Sie sicher, dass der Benutzer online zuhause ist und die Telefonnummer nicht von lokal synchronisiert wird (gilt für Skype for Business Server Enterprise-VoIP aktivierte Benutzer, die zu Teams Direct Routing migriert werden)

Direct Routing setzt voraus, dass der Benutzer online zu Hause ist. Sie können dies überprüfen, indem Sie sich den Parameter RegistrarPool anschaun, der einen Wert in der Domäne infra.lync.com muss. Der Parameter OnPremLineUriManuallySet sollte ebenfalls auf True festgelegt werden. Dies wird durch Konfigurieren der Telefonnummer und Aktivieren von Unternehmensstimmen und Voicemail mithilfe von Skype for Business Online PowerShell erreicht.

1. Verbinden einer Skype for Business Online PowerShell-Sitzung.

2. Ausführen des Befehls: 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri
    ``` 
    Wenn OnPremLineUriManuallySet auf False festgelegt ist und LineUri mit einer <E.164-Telefonnummer> gefüllt ist, bereinigen Sie die Parameter mit der lokalen Skype for Business Management Shell, bevor Sie die Telefonnummer mit Skype for Business Online PowerShell konfigurieren. 

1. Führen Sie in der Skype for Business Management Shell den Folgenden Befehl aus: 

   ```PowerShell
   Set-CsUser -Identity "<User name>" -LineUri $null -EnterpriseVoiceEnabled $False -HostedVoiceMail $False
    ``` 
   Nachdem die Änderungen mit Office 365 synchronisiert wurden, wird die erwartete Ausgabe von `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` wie erwartet angezeigt:

   ```console
   RegistrarPool                        : pool.infra.lync.com
   OnPremLineURIManuallySet             : True
   OnPremLineURI                        : 
   LineURI                              : 
   ```

## <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a>Konfigurieren der Telefonnummer und Aktivieren von Unternehmensstimmen und Voicemail 

Nachdem Sie den Benutzer erstellt und eine Lizenz zugewiesen haben, besteht der nächste Schritt im Konfigurieren der Telefonnummer und Voicemail des Benutzers. 

So fügen Sie die Telefonnummer hinzu, und aktivieren Sie voicemail:
 
1. Verbinden einer Skype for Business Online PowerShell-Sitzung. 

2. Ausführen des Befehls: 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<phone number>
    ```
    
    Wenn Sie beispielsweise eine Telefonnummer für den Benutzer "Spencer Low" hinzufügen möchten, geben Sie Folgendes ein: 

    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```
    Wenn die Benutzer "Spencer Low" und "Stacy Quinn" dieselbe Basisnummer mit eindeutigen Erweiterungen teilen, geben Sie Folgendes ein:
    
    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388701;ext=1001 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    Set-CsUser -Identity "stacy.quinn@contoso.com" -OnPremLineURI tel:+14255388701;ext=1002 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```

    Es wird empfohlen, aber nicht erforderlich, dass die verwendete Telefonnummer als vollständige E.164-Telefonnummer mit Ländercode konfiguriert ist. Es wird unterstützt, Telefonnummern mit Erweiterungen zu konfigurieren, die verwendet werden, um Benutzer zu suchen, wenn das Nachschlageergebnis für die Basisnummer mehr als ein Ergebnis zurückgibt. Auf diese Weise können Unternehmen Telefonnummern mit derselben Basisnummer und eindeutigen Erweiterungen konfigurieren. Damit die Suche erfolgreich ist, muss die Einladung die vollständige Nummer mit der Erweiterung wie folgt enthalten:
    ```PowerShell
    To: <sip:+14255388701;ext=1001@sbc1.adatum.biz
    ```
    
    > [!NOTE]
    > Wenn die Telefonnummer des Benutzers lokal verwaltet wird, verwenden Sie die lokale Skype for Business Management Shell oder Systemsteuerung, um die Telefonnummer des Benutzers zu konfigurieren. 


## <a name="configuring-sending-calls-directly-to-voicemail"></a>Konfigurieren des direkten Sendens von Anrufen an voicemail

Direct Routing ermöglicht es Ihnen, den Anruf an einen Benutzer zu beenden und direkt an die Voicemail des Benutzers zu senden. Wenn Sie den Anruf direkt an voicemail senden möchten, fügen Sie opaque=app:voicemail an den URI-Header Anfordern an. Beispiel: "sip:user@yourdomain.com;opaque=app:voicemail". In diesem Fall erhält der Teams-Benutzer die Anrufbenachrichtigung nicht, der Anruf wird direkt mit der Voicemail des Benutzers verbunden.

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a>Zuweisen des Modus "Nur Teams" zu Benutzern, um sicherzustellen, dass Anrufe in Microsoft Teams landen

Für direktes Routing muss sich der Benutzer im Modus "Nur Teams" befinden, um sicherzustellen, dass eingehende Anrufe im Teams-Client landen. Um Benutzer in den Modus "Nur Teams" zu setzen, weisen Sie ihnen die Instanz "UpgradeToTeams" von TeamsUpgradePolicy zu. Weitere Informationen finden Sie unter [Upgradestrategien für IT-Administratoren.](upgrade-to-teams-on-prem-implement.md) Wenn Ihre Organisation Skype for Business Server oder Skype for Business Online verwendet, finden Sie im folgenden Artikel Informationen zur Interoperabilität zwischen Skype und Teams: Migration und Interoperabilität mit [Skype for Business.](migration-interop-guidance-for-teams-with-skype.md)

## <a name="see-also"></a>Mehr dazu

[Planen von direktem Routing](direct-routing-plan.md)

[Konfigurieren von direktem Routing](direct-routing-configure.md)