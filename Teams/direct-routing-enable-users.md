---
title: Aktivieren von Benutzern für das Direkte Routing
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
description: Hier erfahren Sie, wie Sie Microsoft-Telefon System Direct Routing aktivieren.
ms.openlocfilehash: 6dab88312634a0dc3c595fec109905b308acbdaa
ms.sourcegitcommit: 5720fa12bdabdfc2988bf835c8cf95e4d64fa54e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2021
ms.locfileid: "53354295"
---
# <a name="enable-users-for-direct-routing-voice-and-voicemail"></a>Aktivieren von Benutzern für Direct Routing, Voicemail und Voicemail

In diesem Artikel wird beschrieben, wie Sie Benutzer für das direkte Telefonsystem aktivieren.  Dies ist Schritt 2 der folgenden Schritte zum Konfigurieren von Direct-Routing:

- Schritt 1: [Verbinden des SBC mit Microsoft-Telefon System und Überprüfen der Verbindung](direct-routing-connect-the-sbc.md) 
- **Schritt 2. Aktivieren von Benutzern für Direct Routing, Voicemail**   und Voicemail (dieser Artikel)
- Schritt 3: [Konfigurieren von Voice Routing](direct-routing-voice-routing.md)
- Schritt 4: [Übersetzen von Zahlen in ein alternatives Format](direct-routing-translate-numbers.md) 


Informationen zu allen zum Einrichten von Direct-Routing erforderlichen Schritten finden Sie unter [Konfigurieren von Direct-Routing.](direct-routing-configure.md)

Wenn Sie bereit sind, Benutzer für Direct-Routing zu aktivieren, führen Sie die folgenden Schritte aus: 

1. Erstellen Sie einen Benutzer in Microsoft 365 oder Office 365, und weisen Sie eine Telefonsystem zu. 
2. Stellen Sie sicher, dass der Benutzer in Skype for Business Online verfügbar ist. 
3. Konfigurieren Sie die Telefonnummer, und aktivieren Sie Enterprise-Voicemail. 
4. Weisen Teams nur den Benutzer den Modus "Nur" zu.

## <a name="create-a-user-and-assign-the-license"></a>Erstellen eines Benutzers und Zuweisen der Lizenz

Es gibt zwei Optionen zum Erstellen eines neuen Benutzers in Microsoft 365 oder Office 365. Microsoft empfiehlt Ihrer Organisation jedoch, eine Option zur Vermeidung von Routingproblemen zu wählen: 

- Erstellen Sie den Benutzer im lokalen Active Directory, und synchronisieren Sie den Benutzer mit der Cloud. Weitere [Informationen finden Sie unter Integrieren Ihrer lokalen Verzeichnisse Azure Active Directory.](/azure/active-directory/connect/active-directory-aadconnect)
- Erstellen Sie den Benutzer direkt im Microsoft 365 Admin Center. Weitere Informationen finden Sie unter Hinzufügen von einzelnen Benutzern oder Massen [hinzufügen Microsoft 365 oder Office 365 – Administratorhilfe](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec). 

Wenn Ihre Skype for Business Online-Bereitstellung koexistent mit Skype for Business 2015 oder Lync 2010 oder 2013 lokal ist, besteht die einzige unterstützte Option in der Erstellung des Benutzers im lokalen Active Directory und dem Synchronisieren des Benutzers mit der Cloud (Option 1). 

Informationen zu den Lizenzanforderungen finden Sie unter [Lizenzierungs- und andere Anforderungen](direct-routing-plan.md#licensing-and-other-requirements) in [Planen von Direct Routing.](direct-routing-plan.md)

## <a name="ensure-that-the-user-is-homed-online"></a>Sicherstellen, dass der Benutzer online zu Hause ist 

Dieser Schritt gilt für Skype for Business Server Enterprise-VoIP Benutzer, die zu Direct-Routing migriert Teams werden.

Das direkte Routing setzt voraus, dass der Benutzer online zu Hause ist. Sie können dies überprüfen, indem Sie sich den Parameter RegistrarPool anschauen, der einen Wert in der Domäne "infra.lync.com muss. Es wird auch empfohlen,, aber nicht erforderlich, die Verwaltung des LineURI von der lokalen in die Onlineverwaltung zu ändern, wenn Benutzer zu Direct-Routing Teams werden. 

1. Verbinden einer Skype for Business PowerShell-Onlinesitzung.

2. Gibt den Befehl aus: 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri
    ``` 
    Für den Fall, dass "OnPremLineUriManuallySet" auf "False" festgelegt und "LineUri" mit einer <E.164-Telefonnummer> ausgefüllt wird, wurde die Telefonnummer lokal zugewiesen und mit O365 synchronisiert. Wenn Sie die Telefonnummer online verwalten möchten, bereinigen Sie den Parameter mit der lokalen Skype for Business-Verwaltungsshell, und synchronisieren Sie sie mit O365, bevor Sie die Telefonnummer mithilfe von Skype for Business Online PowerShell konfigurieren. 

1. Von Skype for Business-Verwaltungsshell wird der Befehl aus: 

   ```PowerShell
   Set-CsUser -Identity "<User name>" -LineUri $null
    ``` 
 > [!NOTE]
 > Legen Sie EnterpriseVoiceEnabled nicht auf False fest, da dies nicht erforderlich ist, und dies kann zu Problemen bei der Normalisierung des Wählplans führen, wenn ältere Skype for Business-Telefone verwendet werden und die Hybridkonfiguration des Mandanten mit "UseOnPremDialPlan $True" festgelegt ist. 
    
   Nachdem die Änderungen mit den änderungen synchronisiert Office 365 die erwartete Ausgabe `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` von:

   ```console
   RegistrarPool                        : pool.infra.lync.com
   OnPremLineURIManuallySet             : True
   OnPremLineURI                        : 
   LineURI                              : 
   ```
 > [!NOTE]
 > Die Telefonattribute aller Benutzer müssen online verwaltet werden, bevor Sie die lokale [Umgebung Skype for Business werden.](/skypeforbusiness/hybrid/decommission-on-prem-overview) 

## <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail-online"></a>Konfigurieren der Telefonnummer und Aktivieren von Enterprise-Voicemail und Online-Voicemail 

Nachdem Sie den Benutzer erstellt und eine Lizenz zugewiesen haben, besteht der nächste Schritt im Konfigurieren der Onlinetelefoneinstellungen des Benutzers. 

 
1. Verbinden einer Skype for Business PowerShell-Onlinesitzung. 

2. Wenn Sie die Telefonnummer des Benutzers lokal verwalten, lösen Sie den Befehl aus: 

    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```
3. Wenn Sie die Telefonnummer des Benutzers online verwalten, stellen Sie den Befehl aus: 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<phone number>
    ```
    
    Wenn Sie z. B. eine Telefonnummer für den Benutzer "Low" hinzufügen möchten, geben Sie Folgendes ein: 

    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```
    Wenn sich die Benutzer "Low" und "Stacy Zeln" dieselbe Basisnummer mit eindeutigen Erweiterungen teilen, geben Sie Folgendes ein:
    
    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI "tel:+14255388701;ext=1001" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    Set-CsUser -Identity "stacy.quinn@contoso.com" -OnPremLineURI "tel:+14255388701;ext=1002" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```

    Es wird empfohlen (aber nicht erforderlich), dass die verwendete Telefonnummer als vollständige E.164-Telefonnummer mit Landescode konfiguriert ist. Es wird unterstützt, Telefonnummern mit Erweiterungen zu konfigurieren, die verwendet werden, um Benutzer zu suchen, wenn beim Nachschlageergebnis für die Basisnummer mehr als ein Ergebnis zurückgegeben wird. Dies ermöglicht Unternehmen das Konfigurieren von Telefonnummern mit derselben Basisnummer und eindeutigen Erweiterungen. Damit die Suche erfolgreich ist, muss die Einladung die vollständige Anzahl mit der folgenden Erweiterung enthalten:
    ```PowerShell
    To: <sip:+14255388701;ext=1001@sbc1.adatum.biz
    ```
    
    > [!NOTE]
    > Wenn die Telefonnummer des Benutzers lokal verwaltet wird, verwenden Sie die lokale Skype for Business Verwaltungsshell oder Systemsteuerung, um die Telefonnummer des Benutzers zu konfigurieren. 


## <a name="configure-sending-calls-directly-to-voicemail"></a>Konfigurieren des direkten Sendens von Anrufen an Voicemail

Mit Direct Routing können Sie den Anruf an einen Benutzer beenden und direkt an die Voicemail des Benutzers senden. Wenn Sie den Anruf direkt an die Voicemail senden möchten, fügen Sie undurchsichtig=app:voicemail an den URI-Header anfordern an. Beispiel: "sip:user@yourdomain.com;opaque=app:voicemail". In diesem Fall erhält Teams Anrufer keine Anrufbenachrichtigung. Der Anruf wird direkt mit der Voicemail des Benutzers verbunden.

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a>Weisen Teams nur den Benutzern den Modus "Nur" zu, um sicherzustellen, dass Anrufe bei der Microsoft Teams

Das direkte Routing setzt voraus, dass sich Benutzer im Teams-Modus befinden, um sicherzustellen, dass eingehende Anrufe im Client Teams werden. Um Benutzer in den Teams modus zu setzen, weisen Sie ihnen die Instanz "UpgradeToTeams" von TeamsUpgradePolicy zu. Weitere Informationen finden Sie unter [Upgradestrategien für IT-Administratoren.](upgrade-to-teams-on-prem-implement.md) Wenn Ihre Organisation Skype for Business Server oder Skype for Business Online verwendet, finden Sie im folgenden Artikel Informationen zur Interoperabilität zwischen Skype und Teams: Migration und Interoperabilität mit [Skype for Business.](migration-interop-guidance-for-teams-with-skype.md)

## <a name="see-also"></a>Mehr dazu

[Planen von direktem Routing](direct-routing-plan.md)

[Konfigurieren von direktem Routing](direct-routing-configure.md)
