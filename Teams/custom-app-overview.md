---
title: Verwalten von benutzerdefinierten und quergeladenen Apps
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-apps
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Verstehen Sie, was benutzerdefinierte Apps und quergeladene Apps in Microsoft Teams sind, und verwalten Sie die Apps, um ihr Verhalten, ihr Rollout und ihre Berechtigungen zu steuern.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: 4ba559d605f1465fda7caf9b253c18864c8b4c20
ms.sourcegitcommit: ceba5fd8f098c8d0eafaffe5c5301c845a3ae7ab
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2022
ms.locfileid: "67837375"
---
# <a name="understand-and-manage-custom-and-sideloaded-apps"></a>Verstehen und Verwalten von benutzerdefinierten und quergeladenen Apps

Microsoft Teams ermöglicht Es Entwicklern in Ihrer Organisation, benutzerdefinierte Apps für interne Benutzer der Organisation zu erstellen, zu testen und bereitzustellen. Solche Apps werden als benutzerdefinierte Apps oder Branchen-Apps bezeichnet. Ihre Organisation kann die Erstellung von benutzerdefinierten Apps für organisationsspezifische Anforderungen in Auftrag geben.

Sie als Administrator haben die Möglichkeit, solche Apps für die gesamte Organisation oder für bestimmte Benutzer zuzulassen oder zu blockieren. Entwickler in Ihrer Organisation können mithilfe der Microsoft Teams-Integration mit [Microsoft Power Platform](/microsoftteams/platform/samples/teams-low-code-solutions) schnell benutzerdefinierte Low-Code-Lösungen erstellen.

Entwickler können ihre benutzerdefinierten Apps über Teams zur Genehmigung durch den Administrator übermitteln. Sie können App-Setuprichtlinien verwenden, um das Rollout, die Verteilung und die Berechtigungen benutzerdefinierter Apps zu steuern.

:::image type="content" source="media/custom-app-policy-trimmed.png" alt-text="Screenshot, der zeigt, wie Sie benutzerdefinierte Apps in Ihrer Organisation im organisationsweiten Einstellungsbereich zulassen." lightbox="media/custom-app-policy.png":::

Nachdem Sie die Verwendung einer benutzerdefinierten App zugelassen haben, können Ihre Endbenutzer sie finden, indem sie im linken Navigationsbereich des Teams-Stores die Option **"Für Ihre Organisation erstellt** " auswählen.

:::image type="content" source="media/built-for-your-org1.png" alt-text="Screenshot von benutzerdefinierten Apps im Teams Store in der Teams-Desktop-App." lightbox="media/built-for-your-org2.png":::

## <a name="understand-sideloading-of-custom-apps"></a>Grundlegendes zum Querladen benutzerdefinierter Apps

Beim Entwickeln benutzerdefinierter Apps und vor der Verteilung dieser Apps an die Endbenutzer testen Entwickler die Apps, indem sie sie zum Teams Store hinzufügen, um sie zu testen. Die Entwickler können tests allein oder mit einer bestimmten Gruppe von Benutzern, aber die App ist nicht für andere Endbenutzer in der Organisation über den Store verfügbar. Diese Methode wird „Querladen von Apps“ genannt und gilt nur für benutzerdefinierte Apps.

Entwickler können eine App querladen, um sie den Mitgliedern eines bestimmten Teams zur Verfügung zu stellen, in der Regel um eine App zu testen, die sich in der Entwicklungsphase befindet. Die Verwendung einer App auf diese Weise beschränkt die Verwendung auf die App-Entwickler und erfordert keine Administratorgenehmigung, solange der Administrator das Querladen in Teams zulässt.

Entwickler können eine quergeladene App für ein bestimmtes Team freigeben, ohne sie an den Teams-App-Katalog zu übermitteln. Dadurch wird die quergeladene benutzerdefinierte App einer begrenzten Gruppe von Endbenutzern zur Verfügung gestellt, jedoch nicht im App Store Ihrer Organisation für alle Endbenutzer.

Als Administrator können Sie das Querladen von Apps für alle Entwickler nicht zulassen. Wenn Sie das Querladen nicht zulassen, können die Entwickler ihre Apps dennoch testen, indem sie [einen separaten Testmandanten erstellen](/microsoftteams/platform/concepts/build-and-test/prepare-your-o365-tenant). Sobald die Entwicklung benutzerdefinierter Apps abgeschlossen ist, fordern Entwickler Administratoren auf, ihre benutzerdefinierte App Endbenutzern zur Verfügung zu stellen. Weitere Informationen finden Sie unter [So veröffentlichen Sie eine benutzerdefinierte App](/microsoftteams/upload-custom-apps). Als Administrator können Sie die Verwendung einer benutzerdefinierten App für bestimmte Benutzer zulassen oder verweigern.

## <a name="allow-developers-to-upload-custom-apps"></a>Entwicklern das Hochladen benutzerdefinierter Apps erlauben

Sie können eine benutzerdefinierte Richtlinie erstellen oder die globale Richtlinie bearbeiten, um benutzerdefinierte Apps basierend auf den Anforderungen Ihrer Organisation zuzulassen oder zu blockieren. Führen Sie die folgenden Schritte aus, um eine benutzerdefinierte Richtlinie zu erstellen, mit der Entwickler benutzerdefinierte Apps hochladen können:

1. Melden Sie sich beim Microsoft Teams Admin Center an, und greifen Sie auf **Microsoft Teams-Apps** > **[Setuprichtlinien](https://admin.teams.microsoft.com/policies/app-setup)** zu.

1. Klicken Sie auf **Hinzufügen**.

1. Geben Sie einen Namen und eine Beschreibung für die Richtlinie ein.

1. Aktivieren oder deaktivieren Sie **Hochladen benutzerdefinierter Apps zulassen**.

> [!NOTE]
> Um diese Einstellung zu ändern, lassen Sie Apps von Drittanbietern in den [organisationsweiten App-Einstellungen](manage-apps.md#manage-org-wide-app-settings) Ihres Mandanten zu.

## <a name="related-articles"></a>Verwandte Artikel

* [Verwalten der Richtlinien und Einstellungen für benutzerdefinierte Apps](teams-custom-app-policies-and-settings.md)
* [Grundlegendes zu Richtlinien zum Steuern von Apps](app-policies.md)
* [Grundlegendes zu Drittanbieter-Apps](overview-third-party-apps.md)
