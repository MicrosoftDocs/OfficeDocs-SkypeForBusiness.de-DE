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
description: Erfahren Sie, wie Sie Benutzern das direkte Routing von Microsoft Phone-Systemen ermöglichen.
ms.openlocfilehash: 2ae485398cef1cef2444de07dcabc4bf3f949ad5
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691371"
---
# <a name="enable-users-for-direct-routing-voice-and-voicemail"></a>Aktivieren von Benutzern für Direct Routing, Voicemail und Voicemail

In diesem Artikel wird beschrieben, wie Benutzer für das direkte Routing von Telefonsystemen aktiviert werden.  Schritt 2 der folgenden Schritte zum Konfigurieren des direkten Routings:

- Schritt 1: [Verbinden des SBC mit dem Microsoft Phone-System und Überprüfen der Verbindung](direct-routing-connect-the-sbc.md) 
- **Schritt 2. Aktivieren von Benutzern für Direct Routing, Voicemail und Voicemail** (dieser Artikel)
- Schritt 3: [Konfigurieren des VoIP-Routings](direct-routing-voice-routing.md)
- Schritt 4: [Übersetzen von Zahlen in ein anderes Format](direct-routing-translate-numbers.md) 


Informationen zu allen Schritten, die für das Einrichten des direkten Routings erforderlich sind, finden Sie unter [Konfigurieren des direkten Routings](direct-routing-configure.md).

Wenn Sie bereit sind, Benutzer für die direkte Weiterleitung zu aktivieren, führen Sie die folgenden Schritte aus: 

1. Erstellen Sie einen Benutzer in Microsoft 365 oder Office 365, und weisen Sie eine Telefon System Lizenz zu. 
2. Stellen Sie sicher, dass der Benutzer in Skype for Business Online verwaltet wird. 
3. Konfigurieren Sie die Telefonnummer, und aktivieren Sie Enterprise-VoIP und Voicemail. 
4. Weisen Sie den Benutzern nur den Modus "nur Teams" zu.

## <a name="create-a-user-and-assign-the-license"></a>Erstellen eines Benutzers und Zuweisen der Lizenz 

Es gibt zwei Möglichkeiten zum Erstellen eines neuen Benutzers in Microsoft 365 oder Office 365. Microsoft empfiehlt allerdings, dass Ihre Organisation eine Option zum Vermeiden von Routingproblemen wählt: 

- Erstellen Sie den Benutzer im lokalen Active Directory, und synchronisieren Sie ihn mit der Cloud. Weitere Informationen finden Sie unter [integrieren Ihrer lokalen Verzeichnisse in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).
- Erstellen Sie den Benutzer direkt im Microsoft 365 Admin Center. Weitere Informationen finden Sie unter [Hinzufügen von Benutzern einzeln oder in Massen zu Microsoft 365 oder Office 365 – Administratorhilfe](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec). 

Wenn Ihre Skype for Business Online-Bereitstellung mit Skype for Business 2015 oder lync 2010 oder 2013 lokal koexistiert, besteht die einzige unterstützte Option darin, den Benutzer im lokalen Active Directory zu erstellen und den Benutzer mit der Cloud zu synchronisieren (Option 1). 

Informationen zu den Lizenzanforderungen finden Sie unter [Lizenzierung und andere Anforderungen](direct-routing-plan.md#licensing-and-other-requirements) in [Planen des direkten Routings](direct-routing-plan.md).

## <a name="ensure-that-the-user-is-homed-in-skype-for-business-online"></a>Sicherstellen, dass der Benutzer in Skype for Business Online verwaltet wird 

Für die direkte Weiterleitung muss der Benutzer in Skype for Business Online verwaltet werden. Sie können überprüfen, indem Sie den RegistrarPool-Parameter sehen, der einen Wert in der Infra.lync.com-Domäne aufweisen muss.

1. Herstellen einer Verbindung mit der Remote-PowerShell
2. Geben Sie den folgenden Befehl ein: 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool
    ``` 

## <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a>Konfigurieren Sie die Telefonnummer, und aktivieren Sie Enterprise-VoIP und Voicemail. 

Nachdem Sie den Benutzer erstellt und eine Lizenz zugewiesen haben, besteht der nächste Schritt darin, die Telefonnummer und die Voicemail des Benutzers zu konfigurieren. 

So fügen Sie die Telefonnummer hinzu und aktivieren für Voicemail:
 
1. Stellen Sie eine Verbindung mit einer PowerShell-Remotesitzung her. 
2. Geben Sie den folgenden Befehl ein: 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<E.164 phone number>
    ```

    Wenn Sie beispielsweise eine Telefonnummer für den Benutzer "Spencer Low" hinzufügen möchten, geben Sie Folgendes ein: 

    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```

    Die verwendete Telefonnummer muss als vollständige E. 164-Telefonnummer mit Landesvorwahl konfiguriert werden. 

      > [!NOTE]
      > Wenn die Telefonnummer des Benutzers lokal verwaltet wird, verwenden Sie die lokale Skype for Business-Verwaltungsshell oder die Systemsteuerung, um die Telefonnummer des Benutzers zu konfigurieren. 


## <a name="configuring-sending-calls-directly-to-voicemail"></a>Konfigurieren des direkten Sendens von Anrufen an Voicemail

Mit der direkten Weiterleitung können Sie den Anruf an einen Benutzer beenden und ihn direkt an die Voicemail des Benutzers senden. Wenn Sie den Anruf direkt an Voicemail senden möchten, fügen Sie Opaque = App: Voicemail an den URI-Header der Anforderung an. Beispielsweise "SIP: User@yourdomain. com; Opaque = App: Voicemail". In diesem Fall erhält der Benutzer des Teams keine Anrufbenachrichtigung, der Anruf wird direkt mit der Voicemail des Benutzers verbunden.

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a>Zuweisen des Modus "nur Teams" für Benutzer, um sicherzustellen, dass Anrufe in Microsoft Teams landen

Das direkte Routing setzt voraus, dass Benutzer nur im Modus "Teams" angemeldet sind, um sicherzustellen, dass eingehende Anrufe im Team-Client landen. Um Benutzer nur im Modus "Teams" zu platzieren, weisen Sie Ihnen die "UpgradeToTeams"-Instanz von TeamsUpgradePolicy zu. Weitere Informationen finden Sie unter [Upgrade-Anleitung für IT-Administratoren](upgrade-to-teams-on-prem-overview.md). Wenn Ihre Organisation Skype for Business Server oder Skype for Business Online verwendet, lesen Sie den folgenden Artikel, um Informationen zur Interoperabilität zwischen Skype und Teams zu erhalten: [Migration und Interoperabilität mit Skype for Business](migration-interop-guidance-for-teams-with-skype.md).

## <a name="see-also"></a>Siehe auch

[Planen von direktem Routing](direct-routing-plan.md)

[Konfigurieren von direktem Routing](direct-routing-configure.md)
