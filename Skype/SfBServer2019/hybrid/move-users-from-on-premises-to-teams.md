---
title: Verschieben von Benutzern von lokalen Teams
ms.author: crowe
author: CarolynRowe
manager: serdars--
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: 'Zusammenfassung: Informationen Sie zum Migrieren von benutzereinstellungen und Migrieren von Benutzern zu Teams.'
ms.openlocfilehash: af0867bfdc2e12a248baf7cc07746845154d27fd
ms.sourcegitcommit: bb3f235265cddae9578ec1bf605c4edc7f14fb30
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "25851483"
---
# <a name="move-users-from-on-premises-to-teams"></a>Verschieben von Benutzern von lokalen Teams

Mit Skype für Business Server 2019 können Sie Ihre lokalen Benutzer Teams wie in diesem Artikel beschriebene migrieren.

Beachten Sie, nach dem Verschieben von Ihren Benutzern, Teams: 
 
- Ihre Besprechungen zu Skype für Business Online migriert werden, und ihre Kontakte zu Teams migriert werden. 
- Sie können Skype-Besprechungen über die Skype für Business-rich-Client (Benutzer werden nicht für jedes Mal Anmeldung aufgefordert) oder über die Skype Besprechungen App (erfordert eine einmalige herunter, und Anmeldung) teilnehmen. Klickt ein Benutzer auf einen Skype für Business Link zur Besprechung innerhalb von Teams, wird die Besprechung in der entsprechenden app gestartet.

- Unter Mobile werden Ihre Benutzer können vorhandene Skype für Business Besprechungen mit native app teilnehmen.

> [!NOTE]
> Nachdem ein Benutzer auf den TeamsOnly Modus verschoben wurde, wird der Benutzer in Skype für Business Online, verwaltet.

## <a name="prerequisites-for-moving-on-premises-users-to-teams"></a>Erforderliche Komponenten zum Verschieben von lokalen Benutzern, Teams 

Dieser Abschnitt beschreibt die erforderlichen Komponenten für Ihre lokalen Benutzer Teams verschieben. Du musst:
- [Einrichten von hybridkonnektivität](#set-up-hybrid-connectivity) (Wenn Sie dies nicht bereits geschehen ist)
- [Benachrichtigen Sie die Benutzer, der die Verschiebung Teams](#notify-your-users-of-the-move-to-teams) (optional)
- [Stellen Sie sicher, dass Ihre Benutzer eine gültige Lizenz verfügen.](#make-sure-your-users-have-a-valid-license)
- [Beachten Sie bei Anforderungen für die VoIP-Konfiguration](#voice-configuration-requirements)
- [Zuweisen einer Richtlinie auf Teams aktualisieren](#assign-a-teams-upgrade-policy) (optional)

## <a name="set-up-hybrid-connectivity"></a>Einrichten von hybridkonnektivität
Bevor Sie Ihre Benutzer migrieren, wenn Sie nicht bereits getan haben, müssen Sie sicherstellen, dass Sie hybridkonnektivität zwischen Ihrer Skype für Business Server lokalen Umgebung und Skype für Business Online konfiguriert haben. Hybrid-Diensten ist erforderlich, Active Directory-Synchronisierung, Konfigurieren von Verbund und So weiter. Weitere Informationen finden Sie unter [Planen von hybridkonnektivität](plan-hybrid-connectivity.md) und [hybridkonnektivität konfigurieren](configure-hybrid-connectivity.md).

## <a name="notify-your-users-of-the-move-to-teams"></a>Benachrichtigen Sie die Benutzer, der die Verschiebung Teams 
Dies ist ein optionaler Schritt, aber eine, die Sie berücksichtigen sollten. Um Benutzer des ausstehenden Teams Upgrades zu benachrichtigen, können Sie die lokale TeamsUpgradePolicy und TeamsUpgradeConfiguration-Cmdlets verwenden. Sie können auch automatische automatische-Download von Teams im Hintergrund vor dem Upgrade (nur Win32-Clients) konfigurieren. 

Verwenden Sie, um Benutzer zu benachrichtigen, dass sie Teams aktualisiert werden, beispielsweise das lokale TeamsUpgradePolicy-Cmdlet mit dem Parameter - NotifySbUser. Sie können die Richtlinie auf global, Standort, Pool oder Benutzer Ebene festlegen. Der folgende Befehl erstellt und eine Richtlinie auf Benutzerebene gewährt:
 
```
New-CsTeamsUpgradePolicy -Identity UpgradeNotice -NotifySfbUser $true 
Grant-CsTeamsUpgradePolicy -Identity user01 -PolicyName “UpgradeNotice”
```

Sie können diese Richtlinie mit dem Cmdlet Get-CsTeamsUpgradePolicy überprüfen.

Ihre Benutzer werden eine Benachrichtigung über den bevorstehenden Wechsel zu Teams angezeigt. Die Benachrichtigung wird auf Win32, Mac, Mobile und Web-Clients (mit der richtigen Version).

Sie können das automatische Herunterladen-Teams (Win32-Clients) für Benutzer mit dem lokalen TeamsUpgradeConfiguration-Cmdlet mit dem Parameter DownloadTeams aktualisierten angeben. Legen Sie diese Richtlinie auf der Ebene der Mandanten, und es können angewendet werden soll, klicken Sie auf eine globale, Standort- und pool-Ebene. Der folgende Befehl wird beispielsweise die Richtlinie auf Standortebene:

```
New-CsTeamsUpgradeConfiguration -Identity “site:redmond1” 
```

Standardmäßig müssen der Wert von DownloadTeams ist True, aber Sie auch NotifySfbUser auf "true", um Teams für einen bestimmten Benutzer zu aktivieren. 

## <a name="make-sure-your-users-have-a-valid-license"></a>Stellen Sie sicher, dass Ihre Benutzer eine gültige Lizenz verfügen.  
Vor der Migration muss der lokale Benutzer eine gültige Lizenz, wie folgt angegeben werden:

-   Benutzer benötigen eine Lizenz Teams.
-   Wenn der Benutzer für die Verwendung von lokalen Enterprise Voice konfiguriert ist, müssen sie eine online Voice-Lizenz verfügen, beim Verschieben. 
-   Wenn der Benutzer für einwahlkonferenzen lokale konfiguriert ist, müssen sie eine Lizenz für Telefonsystem (Cloud, PBX) verfügen.

## <a name="voice-configuration-requirements"></a>Anforderungen für die VoIP-Konfiguration

Wenn Ihre lokalen Benutzer lokale VoIP verfügen, haben Sie zwei Optionen:

-  **Migrieren von Benutzern mit Telefoniefunktionen.** Benutzer können tätigen und Entgegennehmen von Anrufen über den Client Teams.  Sie können entweder Microsoft aufrufen planen direkte Routing oder Teams die Telefondienste Verbindung auswählen.  

    -  Planen der Aufruf von Microsoft bietet eine all-in-Cloud-VoIP-Lösung. Weitere Informationen zu Microsoft aufrufen planen finden Sie unter (Link bald verfügbar). 
    -  Direktes Routing können Sie nahezu alle PSTN-Trunk verwenden, und Sie können Interoperabilität zwischen im Besitz des Kunden Telefoniegeräten und Microsoft Telefonsystem konfigurieren.  Weitere Informationen finden Sie unter [Planen der direkten Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-plan) und [Direkte Routing konfigurieren](https://docs.microsoft.com/MicrosoftTeams/direct-routing-configure).

-  **Migrieren von Benutzern ohne Telefoniefunktionen.** Wenn Sie Benutzer migrieren, ohne Telefoniefunktionen beizubehalten, stellen Sie sicher, dass Benutzer in der Cloud entsprechende Lizenzen haben. 

## <a name="assign-a-teams-upgrade-policy"></a>Zuweisen einer Richtlinie auf Teams aktualisieren  
Online-Tools können zum Verwalten von Richtlinien für Benutzer, wie beispielsweise routing von eingehenden Nachrichten und Anrufe steuern. Weitere Informationen finden Sie unter (Link bald verfügbar).

## <a name="move-on-premises-users-to-teams"></a>Migrieren von lokalen Benutzern zu Teams

Sie können Ihre lokalen Benutzer mithilfe von PowerShell-Cmdlets oder mithilfe der Skype Business Server 2019-Systemsteuerung Teams verschieben.

### <a name="move-users-by-using-powershell"></a>Verschieben Sie Benutzer mithilfe von PowerShell
Um Ihren Benutzern mithilfe von PowerShell Teams zu verschieben, werden Sie das Move-CsUser-Cmdlet mit dem Parameter MoveToTeams wie folgt verwenden:

```
Move-CsUser -Identity user0 -Target sipfed.online.lync.com -moveToTeams -credentials $cred. 
```

($cred = Get-Anmeldeinformationen. Sie müssen Office 365-Admin-Anmeldeinformationen angeben.)

> [!NOTE]
> Dieser Befehl legt die TeamsUpgradePolicy TeamsOnly Modus. 
 
Nachdem der Wechsel zu Teams erfolgreich ist, wird Skype für Business-Client des Benutzers die folgende Meldung angezeigt: 

![Migration zu Teams Nachricht wurde ordnungsgemäß abgeschlossen](../media/teams-upgrade-complete-message.png)

Beachten Sie, dass Skype für Unternehmen, die dem Benutzer mit Ausnahme von zum Teilnehmen an einer Besprechung nicht mehr verfügbar ist. 

In seltenen Fällen beim Verschieben von Ihren Benutzern, Teams möchten Sie möglicherweise außer Kraft setzen einwahlkonferenzen und cloud-Voice-Funktionen. Dazu können Sie mit den folgenden Parametern mit dem Befehl Move-CsUser:
- **BypassAudioConferencingCheck:** Wenn ein Benutzer einwahlkonferenzen für lokale aktiviert hat, muss der Benutzer auch eine AudioConf Lizenz zugewiesen in Office 365 vor der Migration verfügen. Nachdem die Cloud migriert werden, wird der Benutzer für Audiokonferenzen in der Cloud bereitgestellt werden. Wenn aus irgendeinem Grund soll Verschieben eines Benutzers in der Cloud, aber die Audiokonferenz-Funktionalität nicht verwenden, können Sie sie durch die Angabe dieses Parameters überschreiben.
- **ByPassEnterpriseVoice:** Wenn ein Benutzer Enterprise-VoIP für lokale aktiviert hat, muss der Benutzer eine zugeordnete in Office 365 vor dem Migrieren von Enterprise-VoIP-Lizenz verfügen. Nach der Migration zur Cloud wird der Benutzer für VoIP in der Cloud bereitgestellt werden. Wenn aus irgendeinem Grund soll Verschieben eines Benutzers in die Cloud aber Cloud Voice-Funktionen nicht verwenden, können Sie die Cloud VoIP durch Angabe dieses Parameters überschreiben.
 
### <a name="move-users-by-using-the-skype-for-business-server-control-panel"></a>Verschieben Sie Benutzer mithilfe der Skype für Business Server-Systemsteuerung 

So verschieben Sie Benutzer für Teams mithilfe der Skype für die Business-Systemsteuerung:

1. Öffnen Sie die Skype für die Business-Systemsteuerung, und melden Sie sich bei Ihrem Office 365-Konto.

2. Wählen Sie im linken Navigationsbereich **Benutzer** aus, und wählen Sie die Benutzer zum Migrieren. 
     
3. Wählen Sie im Menü **Aktion** **Verschieben Sie ausgewählte Benutzer in Teams**. 

    ![Durch Klicken auf Weiter, um die Migration zu bestätigen](../media/migration-confirmation.png)
    
4. Klicken Sie auf **Weiter** , um Ihre Migration zu bestätigen. 

Nachdem der Benutzer auf Teams verschoben wird, sehen Sie Bestätigungen wie folgt:

![Verschieben Sie Benutzer zur Bestätigung](../media/move-user-confirmation.png)
<br/><br/>
![Meldung, dass Benutzer verschoben wurden](../media/users-moved-successfully.png)

Wenn die Verschiebung nicht erfolgreich war, wird eine Meldung wie die folgende angezeigt:

![Nachricht, die Benutzer konnte nicht verschoben werden](../media/users-not-moved.png)
