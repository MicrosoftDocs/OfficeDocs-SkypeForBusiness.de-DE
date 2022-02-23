---
title: Aktivieren von Benutzern für das Direkte Routing
ms.reviewer: filippse
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Hier erfahren Sie, wie Sie Benutzer für das direkte Microsoft Teams Telefon aktivieren.
ms.openlocfilehash: be2f0e0f33bd236591c8c8a2d9cf415972e018d6
ms.sourcegitcommit: e9b0a274fdfee3d5bc8211cb099155546b281fe0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2022
ms.locfileid: "62926298"
---
# <a name="enable-users-for-direct-routing"></a>Aktivieren von Benutzern für das Direkte Routing

In diesem Artikel wird beschrieben, wie Sie Benutzer für Direct-Routing aktivieren. Dies ist Schritt 2 der folgenden Schritte zum Konfigurieren von Direct-Routing:

- Schritt 1: [Verbinden des SBC mit Telefonsystem und Überprüfen der Verbindung](direct-routing-connect-the-sbc.md) 
- **Schritt 2. Aktivieren von Benutzern für Direct-Routing**   (dieser Artikel)
- Schritt 3: [Konfigurieren von Voice Routing](direct-routing-voice-routing.md)
- Schritt 4: [Übersetzen von Zahlen in ein alternatives Format](direct-routing-translate-numbers.md) 


Informationen zu allen erforderlichen Schritten zum Einrichten von Direct-Routing finden Sie unter [Konfigurieren von Direct-Routing](direct-routing-configure.md).

Wenn Sie bereit sind, Benutzer für Direct-Routing zu aktivieren, führen Sie die folgenden Schritte aus: 

1. Erstellen Sie einen Benutzer in Microsoft 365, und weisen Sie eine Telefonsystem zu.  
2. Stellen Sie sicher, dass der Benutzer online zu Hause ist.
3. Konfigurieren Sie die Telefonnummer, und aktivieren Sie Enterprise-Sprachanrufe. 
4. Weisen Teams nur den Benutzer den Modus "Nur" zu.

## <a name="create-a-user-and-assign-the-license"></a>Erstellen eines Benutzers und Zuweisen der Lizenz

Es gibt zwei Optionen zum Erstellen eines neuen Benutzers in Microsoft 365. Microsoft empfiehlt Ihrer Organisation jedoch, eine Option zur Vermeidung von Routingproblemen zu wählen: 

- Erstellen Sie den Benutzer im lokalen Active Directory, und synchronisieren Sie den Benutzer mit der Cloud. Weitere [Informationen finden Sie unter Integrieren Ihrer lokalen Verzeichnisse Azure Active Directory](/azure/active-directory/connect/active-directory-aadconnect).
- Erstellen Sie den Benutzer direkt im Microsoft 365 Admin Center. Weitere [Informationen finden Sie unter Hinzufügen von einzelnen Benutzern oder Massen hinzufügen Microsoft 365 oder Office 365 – Administratorhilfe](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec). 

Wenn ihre Skype for Business Online-Bereitstellung koexistent mit Skype for Business 2015 oder Lync 2010 oder 2013 lokal ist, besteht die einzige unterstützte Option in der Erstellung des Benutzers im lokalen Active Directory und dem Synchronisieren des Benutzers mit der Cloud (Option 1). 

Informationen zu den Lizenzanforderungen finden Sie unter [Lizenzierungs- und andere Anforderungen](direct-routing-plan.md#licensing-and-other-requirements) in [Planen von Direct Routing](direct-routing-plan.md).

## <a name="ensure-that-the-user-is-homed-online"></a>Sicherstellen, dass der Benutzer online zu Hause ist 

Dieser Schritt bezieht sich auf Skype for Business Server Enterprise-VoIP Benutzer, die zum Direct-Routing Teams werden.

Das direkte Routing setzt voraus, dass der Benutzer online zu Hause ist. Sie können dies überprüfen, indem Sie sich den Parameter RegistrarPool anschauen, der einen Wert in der Domäne infra.lync.com muss. Microsoft empfiehlt (aber erfordert nicht), dass Sie den LineURI bei der Migration von Benutzern zu Direct-Routing von lokal in online Teams ändern. 

1. Verbinden einer Microsoft Teams PowerShell-Sitzung.

2. Gibt den Befehl aus: 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri
    ``` 
    Wenn "OnPremLineUriManuallySet" auf False festgelegt ist und "LineUri" mit einer <E.164-Telefonnummer> ausgefüllt wird, wurde die Telefonnummer lokal zugewiesen und mit Microsoft 365 synchronisiert. Wenn Sie die Telefonnummer online verwalten möchten, bereinigen Sie den Parameter mit der lokalen Skype for Business-Verwaltungsshell, und synchronisieren Sie sie mit Microsoft 365, bevor Sie die Telefonnummer mithilfe der PowerShell Teams konfigurieren. 

1. Aus Skype for Business Der Verwaltungsshell den folgenden Befehl aus: 

   ```PowerShell
   Set-CsUser -Identity "<User name>" -LineUri $null
    ``` 
 > [!NOTE]
 > Legen Sie EnterpriseVoiceEnabled nicht auf False fest, da dies nicht erforderlich ist, und dies kann zu Problemen bei der Normalisierung des Wählplans führen, wenn ältere Skype for Business-Telefone verwendet werden und die Mandanten-Hybridkonfiguration mit "UseOnPremDialPlan $True" festgelegt ist. 
    
   Nachdem die Änderungen mit synchronisiert wurden, Microsoft 365 die erwartete Ausgabe von`Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri`:

   ```console
   RegistrarPool                        : pool.infra.lync.com
   OnPremLineURIManuallySet             : True
   OnPremLineURI                        : 
   LineURI                              : 
   ```
 > [!NOTE]
 > Die Telefonattribute aller Benutzer müssen online verwaltet werden, bevor Sie ihre lokale [Umgebung Skype for Business werden](/skypeforbusiness/hybrid/decommission-on-prem-overview). 

## <a name="configure-the-phone-number-and-enable-enterprise-voice"></a>Konfigurieren der Telefonnummer und Aktivieren von Enterprise-Sprachanrufen 

Nachdem Sie den Benutzer erstellt und eine Lizenz zugewiesen haben, müssen Sie die Onlinetelefoneinstellungen des Benutzers konfigurieren. Beachten Sie, dass die Cloud-Voicemail für den Benutzer automatisch erfolgt. Es ist keine weitere Konfiguration erforderlich.

Sie können die Telefonnummer über das Teams Admin Center oder mithilfe von Teams PowerShell konfigurieren.

### <a name="use-teams-admin-center"></a>Verwenden Teams Admin Centers

1. Wechseln Sie **zu** **BenutzerManage-Benutzer** -> .

2. Wählen Sie einen Benutzer aus.

2. Wählen **Sie unter** **Allgemeine Kontoinformationen** die Option **Bearbeiten aus**.

3. Wählen **Sie unter Telefonnummer zuweisen** im **Dropdownmenü Telefon** Telefonnummer zuweisen die Option **Direktes Routing aus**.

4. Geben Sie eine zugewiesene Telefonnummer und eine Durchwahlnummer ein, wenn die App verfügbar ist.

5. Wählen Sie **Übernehmen aus.**

In den allgemeinen Kontoinformationen sind jetzt die zugewiesene Telefonnummer und Direct Routing als Telefonnummerntyp enthalten.


### <a name="use-powershell"></a>Verwenden von PowerShell

1. Verbinden zu einer Microsoft Teams PowerShell-Sitzung. 

2. Die nächsten Schritte hängen davon ab, ob Sie die Telefonnummer des Benutzers lokal oder online verwalten. Wenn Sie die Telefonnummer lokal verwalten, müssen Sie die lokale Skype for Business-Verwaltungsshell, die Systemsteuerung oder eine der in Entscheiden, wie Attribute nach demBefehl verwaltet werden erläutert erläuterten [verwenden.](/skypeforbusiness/hybrid/cloud-consolidation-managing-attributes)

   - Wenn Sie die Telefonnummer des Benutzers lokal verwalten, müssen Sie mithilfe des folgenden Befehls sicherstellen, dass der Enterprise-VoIP online aktiviert ist:

       ```PowerShell
       Set-CsPhoneNumberAssignment -Identity "<User name>" -EnterpriseVoiceEnabled $true
       ```
       
   - Wenn Sie die Telefonnummer des Benutzers online verwalten, müssen Sie dem Benutzer die Telefonnummer mithilfe des folgenden Befehls in Teams PowerShell zuweisen. Der Benutzer wird automatisch Enterprise-VoIP Befehl aktiviert: 
 
       ```PowerShell
       Set-CsPhoneNumberAssignment -Identity "<User name>" -PhoneNumber <phone number> -PhoneNumberType DirectRouting
       ```
    
       Wenn Sie z. B. eine Telefonnummer für den Benutzer "Low" hinzufügen möchten, geben Sie Folgendes ein: 

       ```PowerShell
       Set-CsPhoneNumberAssignment -Identity "spencer.low@contoso.com" -PhoneNumber "+14255388797" -PhoneNumberType DirectRouting
       ```
       Wenn sich die Benutzer "Low" und "Stacy Zeln" dieselbe Basisnummer mit eindeutigen Erweiterungen teilen, geben Sie Folgendes ein:
    
       ```PowerShell
       Set-CsPhoneNumberAssignment -Identity "spencer.low@contoso.com" -PhoneNumber "+14255388701;ext=1001" -PhoneNumberType DirectRouting
       Set-CsPhoneNumberAssignment -Identity "stacy.quinn@contoso.com" -PhoneNumber "+14255388701;ext=1002" -PhoneNumberType DirectRouting
       ```

    Microsoft empfiehlt ,aber erfordert nicht, dass die Telefonnummer als vollständige E.164-Telefonnummer mit Landescode konfiguriert ist. Sie können Telefonnummern mit Erweiterungen konfigurieren. Diese Erweiterungen werden verwendet, um Benutzer zu suchen, wenn der Nachschlage nach der Basisnummer mehr als ein Ergebnis zurückgibt. Diese Funktion ermöglicht Es Unternehmen, Telefonnummern mit derselben Basisnummer und eindeutigen Erweiterungen zu konfigurieren. Damit die Suche erfolgreich ist, muss die Einladung die vollständige Anzahl mit der folgenden Erweiterung enthalten:
    
    ```PowerShell
    To: <sip:+14255388701;ext=1001@sbc1.adatum.biz
    ```


## <a name="configure-sending-calls-directly-to-voicemail"></a>Konfigurieren des direkten Sendens von Anrufen an Voicemail

Mit Direct Routing können Sie den Anruf an einen Benutzer beenden und direkt an die Voicemail des Benutzers senden. Wenn Sie den Anruf direkt an die Voicemail senden möchten, fügen Sie undurchsichtig =app:voicemail an den URI-Header anfordern an. Beispiel: "sip:user@yourdomain.com;opaque=app:voicemail". Der Teams erhält die Anrufbenachrichtigung nicht. Der Anruf wird direkt mit der Voicemail des Benutzers verbunden.

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a>Weisen sie Teams nur den Benutzer den Modus "Nur" zu, um sicherzustellen, dass Anrufe im Microsoft Teams

Das direkte Routing setzt voraus, dass sich die Benutzer im Teams-Modus befinden, um sicherzustellen, dass eingehende Anrufe im Client Teams werden. Um Benutzer in den Teams modus zu setzen, weisen Sie ihnen die Instanz "UpgradeToTeams" von TeamsUpgradePolicy zu. Weitere Informationen finden Sie unter [Upgradestrategien für IT-Administratoren](upgrade-to-teams-on-prem-implement.md). Wenn Ihre Organisation Skype for Business Server verwendet, finden Sie im folgenden Artikel Informationen zur Interoperabilität zwischen Skype und Teams: Migration und Interoperabilität mit [Skype for Business](migration-interop-guidance-for-teams-with-skype.md).

## <a name="see-also"></a>Mehr dazu

[Planen von direktem Routing](direct-routing-plan.md)

[Konfigurieren von direktem Routing](direct-routing-configure.md)
