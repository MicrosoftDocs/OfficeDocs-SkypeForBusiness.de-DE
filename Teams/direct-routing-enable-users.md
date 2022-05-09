---
title: Aktivieren von Benutzern für Direct Routing
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
description: Erfahren Sie, wie Sie Benutzer für Microsoft Teams Telefon Direct Routing aktivieren.
ms.openlocfilehash: edf02077bf5c15da56fe7894d1faec2a9b87b0d5
ms.sourcegitcommit: 9968ef7d58c526e35cb58174db3535fd6b2bd1db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/09/2022
ms.locfileid: "65284080"
---
# <a name="enable-users-for-direct-routing"></a>Aktivieren von Benutzern für Direct Routing

In diesem Artikel wird beschrieben, wie Sie Benutzer für Direct Routing aktivieren. Dies ist Schritt 2 der folgenden Schritte zum Konfigurieren von Direct Routing:

- Schritt 1: [Verbinden des SBC mit Telefonsystem und Überprüfen der Verbindung](direct-routing-connect-the-sbc.md) 
- **Schritt 2. Aktivieren von Benutzern für Direct Routing**   (dieser Artikel)
- Schritt 3: [Konfigurieren des VoIP-Routings](direct-routing-voice-routing.md)
- Schritt 4: [Übersetzen von Zahlen in ein alternatives Format](direct-routing-translate-numbers.md) 


Informationen zu allen erforderlichen Schritten zum Einrichten von Direct Routing finden [Sie unter Konfigurieren von Direct Routing](direct-routing-configure.md).

Wenn Sie bereit sind, Benutzer für Direct Routing zu aktivieren, führen Sie die folgenden Schritte aus: 

1. Erstellen Sie einen Benutzer in Microsoft 365, und weisen Sie eine Telefonsystem Lizenz zu.  
2. Stellen Sie sicher, dass der Benutzer online verwaltet wird.
3. Konfigurieren Sie die Telefonnummer, und aktivieren Sie Enterprise-VoIP. 
4. Weisen Sie Benutzern Teams Modus "Nur" zu.

## <a name="create-a-user-and-assign-the-license"></a>Erstellen eines Benutzers und Zuweisen der Lizenz

Es gibt zwei Optionen zum Erstellen eines neuen Benutzers in Microsoft 365. Microsoft empfiehlt Ihrer Organisation jedoch, eine Option auszuwählen, um Routingprobleme zu vermeiden: 

- Erstellen Sie den Benutzer in lokales Active Directory, und synchronisieren Sie den Benutzer mit der Cloud. Weitere Informationen finden [Sie unter Integrieren Ihrer lokalen Verzeichnisse in Azure Active Directory](/azure/active-directory/connect/active-directory-aadconnect).
- Erstellen Sie den Benutzer direkt im Microsoft 365 Admin Center. Siehe ["Benutzer einzeln oder massenhin hinzufügen" zu Microsoft 365 oder Office 365 – Administratorhilfe](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec). 

Wenn Ihre Skype for Business Onlinebereitstellung zusammen mit Skype for Business 2015 oder Lync 2010 oder 2013 lokal vorhanden ist, besteht die einzige unterstützte Option darin, den Benutzer in der lokales Active Directory zu erstellen und den Benutzer mit der Cloud zu synchronisieren (Option 1). 

Informationen zu Lizenzanforderungen finden Sie unter [Lizenzierung und andere Anforderungen](direct-routing-plan.md#licensing-and-other-requirements) in [Plan Direct Routing](direct-routing-plan.md).

## <a name="ensure-that-the-user-is-homed-online"></a>Sicherstellen, dass der Benutzer online verwaltet wird 

Dieser Schritt gilt für Skype for Business Server Enterprise-VoIP aktivierten Benutzer, die zu Teams Direct Routing migriert werden.

Direct Routing erfordert, dass der Benutzer online verwaltet wird. Sie können dies überprüfen, indem Sie sich den Parameter RegistrarPool ansehen, der einen Wert in der infra.lync.com Domäne aufweisen muss. Microsoft empfiehlt, aber nicht, dass Sie den LineURI beim Migrieren von Benutzern zu Teams Direct Routing von lokal in online ändern. 

1. Verbinden einer Microsoft Teams PowerShell-Sitzung.

2. Führen Sie den Folgenden Befehl aus: 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUri,LineUri
    ``` 
    Wenn OnPremLineUri mit einer <E.164-Telefonnummer> aufgefüllt wird, wurde die Telefonnummer lokal zugewiesen und mit Microsoft 365 synchronisiert. Wenn Sie die Telefonnummer online verwalten möchten, löschen Sie den Parameter mithilfe der lokalen Skype for Business-Verwaltungsshell, und synchronisieren Sie mit Microsoft 365, bevor Sie die Telefonnummer mit Teams PowerShell konfigurieren. 

1. Geben Sie in Skype for Business Verwaltungsshell den folgenden Befehl aus: 

   ```PowerShell
   Set-CsUser -Identity "<User name>" -LineUri $null
    ``` 
 > [!NOTE]
 > Legen Sie EnterpriseVoiceEnabled nicht auf "False" fest, da dies nicht erforderlich ist und dies zu Normalisierungsproblemen bei Wählplänen führen kann, wenn ältere Skype for Business Telefone verwendet werden und die Hybridkonfiguration des Mandanten mit useOnPremDialPlan $True festgelegt ist. 
    
   Nachdem die Änderungen mit Microsoft 365 synchronisiert wurden, lautet die erwartete Ausgabe von`Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUri,LineUri`:

   ```console
   RegistrarPool                        : pool.infra.lync.com
   OnPremLineURI                        : 
   LineURI                              : 
   ```
 > [!NOTE]
 > Alle Telefonattribute des Benutzers müssen online verwaltet werden, bevor Sie [Ihre lokale Skype for Business-Umgebung entschlüsseln](/skypeforbusiness/hybrid/decommission-on-prem-overview). 

## <a name="configure-the-phone-number-and-enable-enterprise-voice"></a>Konfigurieren der Telefonnummer und Aktivieren von Enterprise-VoIP 

Nachdem Sie den Benutzer erstellt und eine Lizenz zugewiesen haben, müssen Sie die Onlinetelefoneinstellungen des Benutzers konfigurieren. Die Konfiguration von Cloud-Voicemail für den Benutzer erfolgt automatisch. Es muss keine andere Konfiguration ausgeführt werden.

Sie können die Telefonnummer über das Teams Admin Center oder mit Teams PowerShell konfigurieren.

### <a name="use-teams-admin-center"></a>Verwenden Teams Admin Center

1. Wechseln Sie zu **UsersManage-Benutzern** -> .

2. Wählen Sie einen Benutzer aus.

2. Wählen Sie unter **"****Allgemeine Kontoinformationen**" die Option **"Bearbeiten"** aus.

3. Wählen **Sie unter "Telefonnummer zuweisen**" im Dropdownmenü **"Telefon Nummerntyp**" die Option **"Direct Routing" aus**.

4. Geben Sie ggf. eine zugewiesene Telefonnummer und eine Telefonnummernerweiterung ein.

5. Wählen Sie **"Übernehmen" aus.**

In den allgemeinen Kontoinformationen werden nun die zugewiesene Telefonnummer und direct Routing als Telefonnummerntyp angezeigt.


### <a name="use-powershell"></a>Verwenden von PowerShell

1. Verbinden zu einer Microsoft Teams PowerShell-Sitzung. 

2. Die nächsten Schritte hängen davon ab, ob Sie die Telefonnummer des Benutzers lokal oder online verwalten. Wenn Sie die Telefonnummer lokal verwalten, müssen Sie die lokale Skype for Business Verwaltungsshell, Systemsteuerung oder eine der Methoden verwenden, die in ["Entscheiden, wie Attribute nach der Außerbetriebnahme verwaltet werden sollen](/skypeforbusiness/hybrid/cloud-consolidation-managing-attributes)".

   - Wenn Sie die Telefonnummer des Benutzers lokal verwalten, müssen Sie mit dem folgenden Befehl sicherstellen, dass der Benutzer online aktiviert Enterprise-VoIP:

       ```PowerShell
       Set-CsPhoneNumberAssignment -Identity "<User name>" -EnterpriseVoiceEnabled $true
       ```
       
   - Wenn Sie die Telefonnummer des Benutzers online verwalten, müssen Sie die Telefonnummer dem Benutzer mithilfe des folgenden Befehls in Teams PowerShell zuweisen. Der Benutzer wird automatisch durch den Folgenden Befehl aktiviert Enterprise-VoIP: 
 
       ```PowerShell
       Set-CsPhoneNumberAssignment -Identity "<User name>" -PhoneNumber <phone number> -PhoneNumberType DirectRouting
       ```
    
       Wenn Sie beispielsweise eine Telefonnummer für den Benutzer "Spencer Low" hinzufügen möchten, geben Sie Folgendes ein: 

       ```PowerShell
       Set-CsPhoneNumberAssignment -Identity "spencer.low@contoso.com" -PhoneNumber "+14255388797" -PhoneNumberType DirectRouting
       ```
       Wenn die Benutzer "Spencer Low" und "Stacy Quinn" die gleiche Basisnummer mit eindeutigen Erweiterungen teilen, geben Sie Folgendes ein:
    
       ```PowerShell
       Set-CsPhoneNumberAssignment -Identity "spencer.low@contoso.com" -PhoneNumber "+14255388701;ext=1001" -PhoneNumberType DirectRouting
       Set-CsPhoneNumberAssignment -Identity "stacy.quinn@contoso.com" -PhoneNumber "+14255388701;ext=1002" -PhoneNumberType DirectRouting
       ```

    Microsoft empfiehlt, aber nicht, dass die Telefonnummer als vollständige E.164-Telefonnummer mit Ländervorwahl konfiguriert ist. Sie können Telefonnummern mit Erweiterungen konfigurieren. Diese Erweiterungen werden verwendet, um Benutzer nachzuschlagen, wenn der Nachschlagevorgang für die Basisnummer mehr als ein Ergebnis zurückgibt. Mit dieser Funktion können Unternehmen Telefonnummern mit derselben Basisnummer und eindeutigen Erweiterungen konfigurieren. Damit die Suche erfolgreich ist, muss die Einladung die vollständige Nummer mit der Folgenden Erweiterung enthalten:
    
    ```PowerShell
    To: <sip:+14255388701;ext=1001@sbc1.adatum.biz
    ```


## <a name="configure-sending-calls-directly-to-voicemail"></a>Konfigurieren des direkten Sendens von Anrufen an Voicemail

Direct Routing ermöglicht es Ihnen, den Anruf an einen Benutzer zu beenden und direkt an die Voicemail des Benutzers zu senden. Wenn Sie den Anruf direkt an die Voicemail senden möchten, fügen Sie opaque=app:voicemail an den Anforderungs-URI-Header an. Beispiel: "sip:user@yourdomain.com;opaque=app:voicemail". Der Teams Benutzer erhält die Anrufbenachrichtigung nicht. Stattdessen wird der Anruf direkt mit der Voicemail des Benutzers verbunden.

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a>Weisen Sie Benutzern den Modus "Nur Teams" zu, um sicherzustellen, dass Anrufe in Microsoft Teams

Direct Routing erfordert, dass sich Benutzer im Modus "Nur Teams" befinden, um sicherzustellen, dass eingehende Anrufe im Teams-Client landen. Um Benutzer in Teams Modus "Nur" zu versetzen, weisen Sie ihnen die "UpgradeToTeams"-Instanz von TeamsUpgradePolicy zu. Weitere Informationen finden Sie unter [Upgradestrategien für IT-Administratoren](upgrade-to-teams-on-prem-implement.md). Wenn Ihre Organisation Skype for Business Server verwendet, finden Sie im folgenden Artikel Informationen zur Interoperabilität zwischen Skype und Teams: [Migration und Interoperabilität mit Skype for Business](migration-interop-guidance-for-teams-with-skype.md).

## <a name="see-also"></a>Siehe auch

[Planen von direktem Routing](direct-routing-plan.md)

[Konfigurieren von direktem Routing](direct-routing-configure.md)
