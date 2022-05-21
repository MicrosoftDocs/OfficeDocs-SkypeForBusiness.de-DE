---
title: Verwalten von Notruf-Routing-Richtlinien für Direct Routing
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Erfahren Sie, wie Sie Richtlinien für die Notrufweiterleitung in Microsoft Teams verwenden und verwalten, um Notrufnummern einzurichten und anzugeben, wie Notrufe weitergeleitet werden.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.openlocfilehash: 33a0493d038586aa51daf29e320e9ffa9c6c7b5b
ms.sourcegitcommit: 4435ac0efcb95e4e5e1f21289e46761e79482ab5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2022
ms.locfileid: "65624119"
---
# <a name="manage-emergency-call-routing-policies-for-direct-routing"></a>Verwalten von Notruf-Routing-Richtlinien für Direct Routing

Wenn Sie [Direct Routing](direct-routing-landing-page.md) in Ihrer Organisation bereitgestellt haben, können Sie Richtlinien für die Notrufweiterleitung in Microsoft Teams verwenden, um Notrufnummern einzurichten und anzugeben, wie Notrufe weitergeleitet werden. Eine Richtlinie für die Notrufweiterleitung bestimmt, ob erweiterte Notrufdienste für Benutzer aktiviert sind, denen die Richtlinie zugewiesen ist, welche Nummern für Notrufdienste verwendet werden (z. B. 911 im USA) und wie Anrufe an Notrufe weitergeleitet werden. 

> [!Note]
> **Beachten Sie, dass diese Anrufweiterleitungsrichtlinien nur für Direct Routing gelten – sie gelten nicht für Anrufpläne oder Telefonieanbieter.**

Sie verwalten Notrufweiterleitungsrichtlinien, indem Sie zu **VoiceEmergency-Richtlinien**  >  im Microsoft Teams Admin Center oder mithilfe von Windows PowerShell wechseln. Die Richtlinien können Benutzern und [Netzwerkstandorten](cloud-voice-network-settings.md) zugewiesen werden.

Für Benutzer können Sie die globale Richtlinie (organisationsweite Standardrichtlinie) verwenden oder benutzerdefinierte Richtlinien erstellen und zuweisen. Benutzer erhalten automatisch die globale Richtlinie, es sei denn, Sie erstellen und weisen eine benutzerdefinierte Richtlinie zu. Denken Sie daran, dass Sie die Einstellungen in der globalen Richtlinie bearbeiten können, sie jedoch nicht umbenennen oder löschen können. Für Netzwerkstandorte erstellen und weisen Sie benutzerdefinierte Richtlinien zu.

Wenn Sie einem Netzwerkstandort und einem Benutzer eine Richtlinie für die Notrufweiterleitung zugewiesen haben und sich dieser Benutzer an diesem Netzwerkstandort befindet, überschreibt die Richtlinie, die dem Netzwerkstandort zugewiesen ist, die Richtlinie, die dem Benutzer zugewiesen ist.

## <a name="create-a-custom-emergency-call-routing-policy"></a>Erstellen einer benutzerdefinierten Richtlinie für die Notrufweiterleitung

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **VoiceEmergency-Richtlinien** > , und klicken Sie dann auf die Registerkarte "**Anrufweiterleitungsrichtlinien**".
2. Klicken Sie auf **Hinzufügen**.
3. Geben Sie eine Bezeichnung und eine Beschreibung für die Richtlinie ein.
4. Um dynamische Notrufe zu aktivieren, aktivieren Sie **dynamische Notrufe**. Wenn dynamische Notrufe aktiviert sind, ruft Teams Richtlinien- und Standortinformationen vom Dienst ab und schließt diese Informationen als Teil des Notrufs ein.
5. Definieren Sie eine oder mehrere Notrufnummern. Klicken Sie dazu unter **"Notrufnummern****" auf "Hinzufügen"**, und führen Sie dann die folgenden Schritte aus:
    1. **Notruf-Wählzeichenfolge**: Geben Sie die Notrufzeichenfolge ein. Diese Wählzeichenfolge gibt an, dass ein Anruf ein Notruf ist und das Routenmuster genau mit dieser Wählzeichenfolge übereinstimmen muss. 
        > [!NOTE]
        > **Für Direct Routing senden Teams Clients keine Notrufe mehr mit einem "+" vor der Notrufzeichenfolge. Stellen Sie sicher, dass das VoIP-Routenmuster, das einer Notrufzeichenfolge entspricht, diese Änderung widerspiegelt.**
    2. **Notrufmaske**: Für jede Notrufnummer können Sie null oder mehr Notrufmasken angeben. Ein Wählformat ist die Nummer, die Sie in den Wert der Notrufzeichenfolge übersetzen möchten. Auf diese Weise können alternative Notrufnummern gewählt werden, und der Anruf kann weiterhin die Notrufdienste erreichen. <br>Beispielsweise fügen Sie 112 als Notrufmaske hinzu, die die Notrufnummer für die meisten europäischen Länder ist, und 911 als Notrufzeichenfolge. Ein Teams Benutzer aus Europa, der zu Besuch ist, weiß möglicherweise nicht, dass 911 die Notrufnummer im USA ist, und wenn er 112 wählt, wird der Anruf an 911 getätigt. Um mehrere Wählmasken zu definieren, trennen Sie jeden Wert durch ein Semikolon. Beispiel: 112;212.
    3. **PSTN-Verwendungsdatensatz**: Wählen Sie den PSTN-Verwendungsdatensatz (Public Switched Telephone Network) aus. Der PSTN-Verwendungseintrag wird verwendet, um zu bestimmen, welche Route zum Weiterleiten von Notrufen von Benutzern verwendet wird, die berechtigt sind, sie zu verwenden. Die dieser Verwendung zugeordnete Route sollte auf einen SIP-Trunk (Session Initiation Protocol) verweisen, der für Notrufe vorgesehen ist, oder auf ein ELIN-Gateway (Emergency Location Identification Number), das Notrufe an den nächstgelegenen Public Safety Answering Point (PSAP) weiterleitet.

    > [!NOTE]
    > Wählzeichenfolgen und Wählmasken müssen innerhalb einer Richtlinie eindeutig sein. Dies bedeutet, dass Sie für eine Richtlinie mehrere Notrufnummern definieren und mehrere Wählmasken für eine Wählzeichenfolge festlegen können, aber jede Wählzeichenfolge und Wählmaske darf nur einmal verwendet werden.

6. Klicken Sie auf **Speichern**.

### <a name="using-powershell"></a>Verwendung von PowerShell

Siehe [New-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/new-csteamsemergencycallroutingpolicy).

## <a name="edit-an-emergency-call-routing-policy"></a>Bearbeiten einer Richtlinie für die Notrufweiterleitung

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

Sie können die globale Standardrichtlinie bearbeiten oder eine von Ihnen erstellte, benutzerdefinierte Richtlinie zuweisen.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **VoiceEmergency-Richtlinien** > , und klicken Sie dann auf die Registerkarte "**Anrufweiterleitungsrichtlinien**".
2. Wählen Sie die Richtlinie aus, indem Sie zunächst links neben die Richtlinienbezeichnung und dann auf **Bearbeiten** klicken.
3. Nehmen Sie die gewünschten Änderungen vor, und klicken Sie dann auf **"Speichern"**.

### <a name="using-powershell"></a>Verwendung von PowerShell

Siehe [Set-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/set-csteamsemergencycallroutingpolicy).

## <a name="assign-a-custom-emergency-call-routing-policy-to-users"></a>Zuweisen einer benutzerdefinierten Richtlinie für das Routing von Notrufen zu Benutzern

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Siehe auch [Grant-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/grant-csteamsemergencycallroutingpolicy).

## <a name="assign-a-custom-emergency-call-routing-policy-to-a-network-site"></a>Zuweisen einer benutzerdefinierten Richtlinie für die Notrufweiterleitung zu einem Netzwerkstandort

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

Sie können die globale Richtlinie oder alle benutzerdefinierten Richtlinien zuweisen, die Sie erstellen.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **LocationsNetwork-Topologie** > , und klicken Sie auf die Registerkarte **"Netzwerkstandorte**".
2. Wählen Sie die Website aus, indem Sie links neben dem Namen klicken und dann auf **"Bearbeiten"** klicken.
3. Wählen Sie unter **"Richtlinie für die Notrufweiterleitung**" die Richtlinie aus, und klicken Sie dann auf **"Speichern"**.

### <a name="using-powershell"></a>Verwendung von PowerShell

Verwenden Sie das Cmdlet [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) , um einem Netzwerkstandort eine Richtlinie für die Notrufweiterleitung zuzuweisen.

In diesem Beispiel wird gezeigt, wie Sie dem Standort 1 eine Richtlinie mit dem Namen "Notrufweiterleitungsrichtlinie 1" zuweisen.

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a>Verwandte Themen

[Verwalten von Notrufrichtlinien in Teams](manage-emergency-calling-policies.md)

[Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)

[Benutzern in Microsoft Teams Richtlinien zuweisen](policy-assignment-overview.md)
