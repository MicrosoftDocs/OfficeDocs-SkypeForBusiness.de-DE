---
title: Verwalten von Ressourcenkonten in Microsoft Teams
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: jastark, wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
description: Erfahren Sie mehr über das Verwalten von Ressourcenkonten in Microsoft-Teams
ms.openlocfilehash: ad435a812191cc8f7b9061ac5fba2bbe626b908e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30886061"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a>Verwalten von Ressourcenkonten in Microsoft Teams

Ein Ressourcenkonto wird auch als ein deaktiviertes Benutzerobjekt in Azure Active Directory und kann verwendet werden, um Ressourcen im Allgemeinen darstellen. In Exchange kann verwendet werden, Konferenzräumen, beispielsweise darstellen und ermöglicht es ihnen, Sie haben eine Telefonnummer ein. Ein Ressourcenkonto kann in Microsoft 365 oder lokal mit Skype für Business Server verwaltet werden, und diese Konten werden mithilfe von Powershell-Befehlen erstellt.

In Microsoft-Teams oder Skype für Business Online, jeden Anruf Warteschlange oder automatische wird Attendant erforderlich, um ein Ressourcenkonto zugeordneten verfügen. Ob ein Ressourcenkonto eine zugewiesene Telefonnummer benötigt wird abhängig von der beabsichtigten Verwendung von der zugehörigen Aufruf Warteschlange oder automatische Telefonzentrale. Finden Sie in den Artikeln für Anruf Warteschlangen und automatische um-Telefonzentralen verknüpft unten in diesem Artikel, bevor Sie eine Telefonnummer ein Ressourcenkonto zuweisen.

> [!NOTE]
> Dieser Artikel bezieht sich auf Microsoft-Teams und Skype für Business Online.

## <a name="prerequisites-to-assign-a-phone-number-to-a-resource-account"></a>Erforderliche Komponenten ein Ressourcenkonto eine Telefonnummer zuweisen

Erste Schritte beim es ist wichtig, sollten Sie einige Dinge bedenken:
  
- Sie müssen ein Ressourcenkonto eine Telefonsystem Lizenz zuweisen, die die automatische Telefonzentrale oder ein Anruf Warteschlange zugeordnet werden. Weitere Informationen zu Lizenzierung finden Sie unter [Microsoft-Teams, Add-On-Lizenzierung](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).
    

    > [!NOTE]
    > Zum Umleiten von Anrufen an Personen in Ihrer Organisation, die Online sind, sie benötigen eine Lizenz **Telefonsystem** und für Enterprise-VoIP aktiviert sein oder Office 365 aufrufen Plans. Finden Sie unter [Microsoft-Teams, Zuweisen von Lizenzen](assign-teams-licenses.md). Um diese Lizenzen für Enterprise-VoIP zu aktivieren, können Sie die Windows PowerShell verwenden. Führen Sie beispielsweise folgenden Befehl aus:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Sie können eine direkte Routing Hybrid Anzahl Ihrer Ressourcenkonto zuweisen.  Einzelheiten finden Sie unter [Planen der direkten Routing](direct-routing-plan.md) .
- Für Microsoft aufrufende plant können Sie nur zuweisen gebührenpflichtige oder gebührenfreie Service Telefonnummern, die Sie haben Sie in der **Microsoft-Teams, Administrationscenter** oder in einem Ressourcenkonto aus einer anderen Dienstanbieter übertragen. Um gebührenfreie Servicenummern zu erhalten müssen Sie Communication Credits einrichten.

> [!NOTE]
> Ein Ressourcenkonto können nicht Benutzer (Abonnent) Rufnummern zugewiesen werden. Nur Service gebührenpflichtige oder gebührenfreie Telefonnummern können verwendet werden.

Eine Telefonnummer ein, um ein Ressourcenkonto zuzuweisen, müssen Sie erhalten möchten, oder übertragen Ihre vorhandenen gebührenpflichtige oder gebührenfreie Service Zahlen. Nachdem Sie die gebührenpflichtige oder gebührenfreie Service Telefonnummern erhalten möchten, sie werden angezeigt, in der **Microsoft-Teams, Administrationscenter** > **VoIP** > **Telefonnummern**und die **Typ-Nummer** aufgeführt wird als **Dienst - gebührenfreie**aufgeführt werden. Um die Rufnummern Service erhalten möchten, finden Sie unter [Getting Service Rufnummern](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) oder wenn Sie eine vorhandene Servicenummer durchstellen möchten, finden Sie unter [Weiterleiten von Telefonnummern zu Office 365](transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> Wenn Sie sich außerhalb der USA sind, können das Microsoft-Teams, Administrationscenter Sie um Service Zahlen zu erhalten. Wechseln Sie zum [Verwalten von Rufnummern für Ihre Organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) stattdessen, wie Sie von außerhalb der USA finden Sie unter.

## <a name="create-a-resource-account-in-powershell"></a>Erstellen Sie ein Ressourcenkonto in Powershell

 Sie würden ein Ressourcenkonto durch Ausführen des entsprechenden Powershell-Cmdlets (für eine oder mehrere Ressourcenkonten) nach Bedarf erstellen, und geben Sie jeweils einen Namen und so weiter. Derzeit keine Option zum Erstellen einer Ressource-Konto in der Verwaltungskonsole von Microsoft-Teams vorliegt, aber Sie können Telefonnummern bearbeiten und ändern Sie die Anruf Warteschlange oder Auto attendant Zuordnungen für ein Ressourcenkonto.

Je nachdem, ob Ihre Telefonnummer online oder lokal befindet müssen Sie in der entsprechenden Aufforderung Powershell mit Administratorberechtigungen eine Verbindung herstellen.

- Hybrid Implementierungen (Zahlen Zahlen verwaltet auf direktes Routing, OPCH und CCE) werden [Neu CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) verwenden, um ein Ressourcenkonto erstellen, die lokal verwaltet wird.  
- Nur Online Implementierungen [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) verwendet, die ein Resource-Konto verfügen, die online verwaltet wird.

Es folgt ein Beispiel für online-Umgebung ein Ressourcenkonto erstellen:

``` Powershell
New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId “ce933385-9390-45d1-9512-c8d228074e07” -DisplayName "Resource account 1"
$resacct=Get-MsolUser -UserPrincipalName testra1@contoso.com
```

Weitere Informationen zu diesem Befehl finden Sie unter [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps) .

> [!NOTE]
> Es ist am einfachsten, die mit dem Microsoft-Teams, Administrationscenter online Telefonnummer festgelegt, wie im nächsten Abschnitt beschrieben. Sie können auch die `Set-CsOnlineVoiceApplicationInstance` Befehl für eine Zuweisung eine Rufnummer, das Ressourcenkonto nach der anfänglichen Erstellung wie dargestellt:

``` Powershell
Set-CsOnlineVoiceApplicationInstance -Identity $resacct.ObjectId
 -TelephoneNumber +14255550100
Get-CsOnlineTelephoneNumber -TelephoneNumber 19294450177
```

Weitere Informationen zu diesem Befehl finden Sie unter [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) .

## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a>Verwalten von Einstellungen für Ressource-Konto im Microsoft-Teams, Administrationscenter

Navigieren Sie zum Verwalten von Einstellungen der Ressource-Konto im Microsoft-Teams, Administrationscenter zu **Org geltende Settings**  > **Ressource Firmen**, auswählen das Ressourcenkonto Sie Einstellungen für ändern müssen und dann auf die Schaltfläche **Bearbeiten** . Klicken Sie im Bildschirm **Bearbeiten Ressourcenkonto** werden Sie ändern die:

- **Anzeigename** für das Konto
- Rufen Sie die Warteschlange oder automatische um-Telefonzentrale, die das Konto verwendet
- Das Konto zugewiesene Telefonnummer

Klicken Sie abschließend auf **Speichern**.

## <a name="related-information"></a>Verwandte Informationen

Für Implementierungen sind, Hybrid mit Skype für Business Server:

[Planen automatischer Cloudtelefonzentralen](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)

[Konfigurieren automatischer Cloudtelefonzentralen](/SkypeForBusiness/hybrid/configure-cloud-auto-attendant)

Für Implementierungen in Teams oder Skype für Business Online:

[Was sind automatische Telefonzentralen des Telefonsystems?](what-are-phone-system-auto-attendants.md)

[Einrichten einer automatischen Telefonzentrale des Telefonsystems](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)

[Beispiel für Kleinunternehmen – Einrichten einer automatischen Telefonzentrale](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa)

[Erstellen einer Warteschlange für das Telefonsystem](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[Neue CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[Neue CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
