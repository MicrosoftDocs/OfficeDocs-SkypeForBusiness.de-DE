---
title: Verwalten von Notfall-Anrufweiterleitungsrichtlinien
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Hier erfahren Sie, wie Sie in Microsoft Teams Notruf-Routing Richtlinien verwenden und verwalten, um Notrufnummern einzurichten und festzulegen, wie Notrufe weitergeleitet werden.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.openlocfilehash: 67ef3bb5700c223f3057ef0ba44c9df07a2e7be6
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217696"
---
# <a name="manage-emergency-call-routing-policies-in-microsoft-teams"></a>Verwalten von Notfall Anruf-Routing Richtlinien in Microsoft Teams

Wenn Sie in Ihrer Organisation ein [Direktes Routing für Telefonsysteme](direct-routing-landing-page.md) bereitgestellt haben, können Sie in Microsoft Teams Notfall-Anruf Weiterleitungsrichtlinien verwenden, um Notrufnummern einzurichten und festzulegen, wie Notrufe weitergeleitet werden. Eine Notruf Routing-Richtlinie legt fest, ob erweiterte Notfalldienste für Benutzer aktiviert sind, denen die Richtlinie zugewiesen ist, die Nummern, mit denen Notrufdienste aufgerufen werden (beispielsweise 911 in den USA) und wie Anrufe an Notfalldienste weitergeleitet werden.

Sie verwalten Notruf Routing Richtlinien, indem Sie **Voice**  >  im Microsoft Teams Admin Center oder mithilfe von Windows PowerShell zu VoIP-**Notfall Richtlinien** wechseln. Die Richtlinien können Benutzern und [Netzwerk Websites](cloud-voice-network-settings.md)zugewiesen werden.

Für Benutzer können Sie die globale (organisationsweite Standardrichtlinie) verwenden oder benutzerdefinierte Richtlinien erstellen und zuweisen. Benutzer erhalten automatisch die globale Richtlinie, es sei denn, Sie erstellen eine benutzerdefinierte Richtlinie und weisen diese zu. Beachten Sie, dass Sie die Einstellungen in der globalen Richtlinie bearbeiten, aber nicht umbenennen oder löschen können. Für Netzwerk Websites erstellen und zuweisen Sie benutzerdefinierte Richtlinien.

Wenn Sie einer Netzwerk Website und einem Benutzer eine Notfall Anruf-Routing Richtlinie zugewiesen haben und sich dieser Benutzer an dieser Netzwerk Website befindet, überschreibt die der Netzwerk Website zugewiesene Richtlinie die Richtlinie, die dem Benutzer zugewiesen ist.

## <a name="create-a-custom-emergency-call-routing-policy"></a>Erstellen einer benutzerdefinierten Routing Richtlinie für Notfallanrufe

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **VoIP**-  >  **Notfall Richtlinien**, und klicken Sie dann auf die Registerkarte **Anruf Weiterleitungsrichtlinien** .
2. Klicken Sie auf **Hinzufügen**.
3. Geben Sie eine Bezeichnung und eine Beschreibung für die Richtlinie ein.
4. Aktivieren Sie **dynamische**Notrufe, um dynamische Notrufe zu ermöglichen. Wenn dynamische Notrufe aktiviert sind, ruft Teams Richtlinien-und Standortinformationen vom Dienst ab und enthält diese Informationen im Rahmen des Notrufs.
5. Definieren Sie eine oder mehrere Notfallnummern. Klicken Sie dazu unter **Notrufnummern**auf **Hinzufügen**, und gehen Sie dann folgendermaßen vor:
    1. **Notfall Wahl Zeichenfolge**: Geben Sie die Notrufnummer ein. Diese Wählzeichenfolge zeigt an, dass ein Anruf ein Notruf ist.
        > [!NOTE]
        > Für das direkte Routing wechseln wir von Teams-Clients, die Notrufe mit einem "+" vor der Notruf Zeichenfolge senden. Bis zum Abschluss des Übergangs sollte das VoIP-Routenmuster einer Notruf Zeichenfolge entsprechen, um sicherzustellen, dass Zeichenfolgen mit einem vorangehenden "+", wie 911 und + 911, übereinstimmen. Beispiel: ^ \\ +? 911 oder. *.
    2. **Notfall-Wähl Maske**: Sie können für jede Notrufnummer NULL oder mehr Notrufnummern angeben. Eine Wähl Maske ist die Nummer, die Sie in den Wert der Notruf-Wählzeichenfolge übersetzen möchten. Auf diese Weise können alternative Notrufnummern gewählt werden, und der Anruf kann auch Notfalldienste erreichen. <br>Beispielsweise fügen Sie 112 als Notruf Maske hinzu, bei der es sich um die Notrufnummer für die meisten Europa und 911 als Notruf Zeichenfolge handelt. Ein Team Nutzer aus Europa, der gerade besucht, weiß möglicherweise nicht, dass 911 die Notrufnummer in den Vereinigten Staaten ist, und wenn Sie 112 wählen, wird der Anruf an 911 durchgeführt. Wenn Sie mehrere Wähl Masken definieren möchten, trennen Sie die einzelnen Werte durch ein Semikolon. Beispiel: 112; 212.
    3. **PSTN-Verwendungsdaten Satz**: Wählen Sie den Eintrag für die öffentliche Telefonnetz Nutzung (PSTN) aus. Der PSTN-Nutzungsdaten Satz wird verwendet, um zu ermitteln, welche Route zur Weiterleitung von Notrufen von Benutzern verwendet wird, die zur Verwendung autorisiert sind. Die Route, die mit dieser Verwendung verknüpft ist, sollte auf einen SIP-Stamm (Session Initiation Protocol) verweisen, der für Notrufe vorgesehen ist, oder für ein Notfall-Standort-ID (Elin)-Gateway, das Notrufe an den nächstgelegenen öffentlichen Sicherheits Beantwortungs Punkt (PSAP) weiterleitet.

    > [!NOTE]
    > Wählzeichenfolgen und Wähl Masken müssen innerhalb einer Richtlinie eindeutig sein. Das bedeutet, dass Sie für eine Richtlinie mehrere Notfallnummern definieren können, und Sie können mehrere Wähl Masken für eine Wählzeichenfolge festlegen, aber jede Wählzeichenfolge und Wähl Maske darf nur einmal verwendet werden.

6. Klicken Sie auf **Speichern**.

### <a name="using-powershell"></a>Verwendung von PowerShell

Weitere Informationen finden Sie unter [New-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallroutingpolicy).

## <a name="edit-an-emergency-call-routing-policy"></a>Bearbeiten einer Notfall Anruf-Routing Richtlinie

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

Sie können die globale Standardrichtlinie bearbeiten oder eine von Ihnen erstellte, benutzerdefinierte Richtlinie zuweisen.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **VoIP**-  >  **Notfall Richtlinien**, und klicken Sie dann auf die Registerkarte **Anruf Weiterleitungsrichtlinien** .
2. Wählen Sie die Richtlinie aus, indem Sie zunächst links neben die Richtlinienbezeichnung und dann auf **Bearbeiten** klicken.
3. Nehmen Sie die gewünschten Änderungen vor, und klicken Sie dann auf **Speichern**.

### <a name="using-powershell"></a>Verwendung von PowerShell

Weitere Informationen finden Sie unter [Satz-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallroutingpolicy).

## <a name="assign-a-custom-emergency-call-routing-policy-to-users"></a>Zuweisen einer benutzerdefinierten Notfall Routing Richtlinie für Benutzer

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Siehe auch [Grant-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallroutingpolicy).

## <a name="assign-a-custom-emergency-call-routing-policy-to-a-network-site"></a>Zuweisen einer benutzerdefinierten Notfall Routing Richtlinie zu einer Netzwerk Website

Verwenden Sie das Cmdlet " [CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) ", um einer Netzwerk Website eine Notfall Anruf-Routing Richtlinie zuzuweisen.

In diesem Beispiel wird gezeigt, wie der site1-Website eine Richtlinie namens "Emergency Call Routing Policy 1" zugewiesen wird.

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a>Verwandte Themen

[Verwalten von Notruf Richtlinien in Teams](manage-emergency-calling-policies.md)

[Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)

[Zuweisen von Richtlinien zu Ihren Benutzern in Microsoft Teams](assign-policies.md)
