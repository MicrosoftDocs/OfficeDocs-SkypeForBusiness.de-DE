---
title: Verwalten von Notfall-Anrufweiterleitungsrichtlinien
author: cichur
ms.author: v-cichur
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
localization_priority: Normal
search.appverid: MET150
description: Erfahren Sie, wie Sie Richtlinien für das Routing von Notrufen in Microsoft Teams verwenden und verwalten, um Notrufnummern zu erstellen und anzugeben, wie Notrufe geroutet werden.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.openlocfilehash: f2e7ce7ee2557745f3819efc84dada77b4a70635
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804675"
---
# <a name="manage-emergency-call-routing-policies-in-microsoft-teams"></a>Verwalten von Richtlinien für das Routing von Notrufen in Microsoft Teams

Wenn Sie direct [Routing](direct-routing-landing-page.md) für Telefonsystem in Ihrer Organisation bereitgestellt haben, können Sie mithilfe der Richtlinien für das Routing von Notrufen in Microsoft Teams Notrufnummern einrichten und angeben, wie Notrufe weiterleiten werden. Eine Richtlinie zum Routing von Notrufen bestimmt, ob erweiterte Notrufdienste für Benutzer aktiviert sind, denen die Richtlinie zugewiesen ist, die Nummern, über die Notrufe angerufen werden (z. B. 911 in den USA) und wie Anrufe an Notdienste weiterleiten werden.

Sie verwalten Richtlinien für das Routing von Notrufen, indem Sie zu den **Richtlinien** für Notrufe im Microsoft Teams Admin Center oder mithilfe von  >   Windows PowerShell. Die Richtlinien können Benutzern und [Netzwerkwebsites zugewiesen werden.](cloud-voice-network-settings.md)

Für Benutzer können Sie die globale (organisationsweite Standardrichtlinie) verwenden oder benutzerdefinierte Richtlinien erstellen und zuweisen. Die Benutzer erhalten die globale Richtlinie automatisch, es sei denn, Sie erstellen und weisen eine benutzerdefinierte Richtlinie zu. Denken Sie daran, dass Sie die Einstellungen in der globalen Richtlinie bearbeiten, sie aber nicht umbenennen oder löschen können. Für Netzwerkwebsites erstellen und weisen Sie benutzerdefinierte Richtlinien zu.

Wenn Sie einer Netzwerkwebsite und einem Benutzer eine Richtlinie für das Routing von Notrufen zugewiesen haben und sich der Benutzer an diesem Netzwerkstandort befindet, setzt die Richtlinie, die dem Netzwerkstandort zugewiesen ist, die Richtlinie außer Kraft, die dem Benutzer zugewiesen ist.

## <a name="create-a-custom-emergency-call-routing-policy"></a>Erstellen einer benutzerdefinierten Richtlinie für die Weiterleitung von Notrufen

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu "Notfallrichtlinien für Sprachanrufe", und klicken Sie dann auf die Registerkarte "Anrufroutingrichtlinien".  >   
2. Klicken Sie auf **Hinzufügen**.
3. Geben Sie eine Bezeichnung und eine Beschreibung für die Richtlinie ein.
4. Um dynamische Notrufe zu ermöglichen, aktivieren Sie **dynamische Notrufe.** Wenn dynamische Notrufe aktiviert sind, ruft Teams Richtlinien- und Standortinformationen vom Dienst ab und enthält diese Informationen als Teil des Notrufs.
5. Definieren Sie eine oder mehrere Notfallnummern. Klicken Sie dazu unter **"Notrufnummern"** auf "Hinzufügen", und gehen Sie dann wie folgt vor:
    1. **Notrufzeichenfolge:** Geben Sie die Notrufzeichenfolge ein. Diese Wählzeichenfolge gibt an, dass es sich bei einem Anruf um einen Notruf handelt.
        > [!NOTE]
        > Für das direkte Routing werden die Teams-Clients, die Notrufe senden, mit einem "+" vor der Notrufzeichenfolge umschalten. Bis zum Abschluss des Übergangs sollte das Sprachroutenmuster, das einer Notrufzeichenfolge entspricht, sicherstellen, dass eine Übereinstimmung für Zeichenfolgen vorgenommen wird, die ein vorangehendes "+" wie 911 und +911 enthalten. Beispiel: ^ \\ +?911 oder .*.
    2. **Notrufnummer:** Für jede Notfallnummer können Sie Null- oder mehr Notrufmasken angeben. Eine Wählmaske ist die Nummer, die Sie in den Wert der Notrufzeichenfolge übersetzen möchten. Auf diese Weise können alternative Notrufnummern gewählt werden, und die Notrufe bleiben erhalten. <br>So fügen Sie beispielsweise 112 als Notrufnummer, die die Notrufnummer für die meisten Benutzer in Europa ist, und 911 als Notrufzeichenfolge hinzu. Ein Teambenutzer aus Europa, der zu Gast ist, weiß möglicherweise nicht, dass 911 die Notrufnummer in den USA ist, und wenn er 112 wählt, wird bei 911 angerufen. Um mehrere Wählmasken zu definieren, trennen Sie jeden Wert durch ein Semikolon. Beispiel: 112;212.
    3. **PSTN-Nutzungsdatensatz:** Wählen Sie den Nutzungsdatensatz für das öffentliche Telefonnetz (PSTN) aus. Der PstN-Nutzungsdatensatz wird verwendet, um zu bestimmen, welche Route verwendet wird, um Notrufe von Benutzern weiter zu routen, die berechtigt sind, sie zu verwenden. Die dieser Verwendung zugeordnete Route sollte auf einen Sip (Session Initiation Protocol)-Trunk verweisen, der für Notrufe oder ein ELIN (Emergency Location Identification Number)-Gateway verwendet wird, das Notrufe zum nächstgelegenen Public Safety Answering Point (PSAP) weiter leitet.

    > [!NOTE]
    > Wählzeichenfolgen und Wählmasken müssen innerhalb einer Richtlinie eindeutig sein. Dies bedeutet, dass Sie für eine Richtlinie mehrere Notfallnummern definieren und mehrere Wählmasken für eine Wählzeichenfolge festlegen können, aber jede Wählzeichenfolge und jede Wählmaske darf nur einmal verwendet werden.

6. Klicken Sie auf **Speichern**.

### <a name="using-powershell"></a>Verwendung von PowerShell

Siehe ["New-CsTeamsEmergencyCallRoutingPolicy".](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallroutingpolicy)

## <a name="edit-an-emergency-call-routing-policy"></a>Bearbeiten einer Richtlinie für die Weiterleitung von Notrufen

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

Sie können die globale Standardrichtlinie bearbeiten oder eine von Ihnen erstellte, benutzerdefinierte Richtlinie zuweisen.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu "Notfallrichtlinien für Sprachanrufe", und klicken Sie dann auf die Registerkarte "Anrufroutingrichtlinien".  >   
2. Wählen Sie die Richtlinie aus, indem Sie zunächst links neben die Richtlinienbezeichnung und dann auf **Bearbeiten** klicken.
3. Nehmen Sie die von Ihnen vorgenommenen Änderungen vor, und klicken Sie dann auf **"Speichern".**

### <a name="using-powershell"></a>Verwendung von PowerShell

Siehe [Set-CsTeamsEmergencyCallRoutingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallroutingpolicy)

## <a name="assign-a-custom-emergency-call-routing-policy-to-users"></a>Zuweisen einer benutzerdefinierten Richtlinie für die Weiterleitung von Notrufen zu Benutzern

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Siehe auch [Grant-CsTeamsEmergencyCallRoutingPolicy.](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallroutingpolicy)

## <a name="assign-a-custom-emergency-call-routing-policy-to-a-network-site"></a>Zuweisen einer benutzerdefinierten Richtlinie für das Routing von Notrufen zu einem Netzwerkstandort

Verwenden Sie [das Cmdlet "Set-CsTenantNetworkSite",](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) um einer Netzwerkwebsite eine Routingrichtlinie für Notrufe zuzuordnen.

Dieses Beispiel zeigt, wie Sie der Website "Site1" eine Richtlinie namens "Routingrichtlinie für Notrufe 1" zuweisen.

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a>Verwandte Themen

[Verwalten von Richtlinien für Notrufe in Teams](manage-emergency-calling-policies.md)

[Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)

[Benutzern in Microsoft Teams Richtlinien zuweisen](assign-policies.md)
