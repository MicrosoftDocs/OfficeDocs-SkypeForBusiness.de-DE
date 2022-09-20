---
title: Übersicht über App-Richtlinien zum Verwalten von Apps in Microsoft Teams
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: conceptual
ms.service: msteams
ms.subservice: teams-apps
search.appverid: ''
description: Erfahren Sie mehr über App-Berechtigungsrichtlinien, App-Setup-Richtlinien und Richtlinien für benutzerdefinierte Apps, die zum Verwalten von Apps in Microsoft Teams verwendet werden.
audience: admin
ms.localizationpriority: high
appliesto:
- Microsoft Teams
ms.collection:
- M365-collaboration
ms.openlocfilehash: ad7e99d10ebf53c7a85394edda84061f6caf0d29
ms.sourcegitcommit: ceba5fd8f098c8d0eafaffe5c5301c845a3ae7ab
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2022
ms.locfileid: "67837565"
---
# <a name="overview-of-app-policies-used-to-manage-access-to-apps"></a>Übersicht über App-Richtlinien zum Verwalten des Zugriffs auf Apps

Microsoft Teams verwendet Richtlinien, um das Zugriffs- und Installationsverhalten zu steuern. Richtlinien helfen Teams-Administratoren, das folgende App-Verhalten zu steuern:

* Konfigurieren Sie den Zugriff auf Apps für die Benutzer auf einer präzisen Ebene. Es hilft jedem Endbenutzer, nur die Apps zu verwenden, die ein Administrator für ihn zugelassen hat.

* Heften Sie die relevanten Apps für einen bestimmten Benutzer an. Es hilft Endbenutzern, einfach zu beginnen und schnell auf die relevanten Apps zuzugreifen, da angeheftete Apps ohne Eingriff automatisch installiert werden.

## <a name="app-permission-policies"></a>App-Berechtigungsrichtlinien

Mit App-Berechtigungsrichtlinien kann der Teams-Administrator steuern, welche Apps für welche bestimmten Benutzer in ihrer Organisation verfügbar sind. Sie können eine genaue Zugriffszuordnung zwischen App und Benutzer oder eine beliebige Kombination aus beidem definieren. Sie können z. B. einige Apps für alle Benutzer zulassen, einige Apps für eine bestimmte Benutzergruppe zulassen oder eine bestimmte App für einen bestimmten Benutzer zulassen.

Die App-Berechtigungsrichtlinien gelten für alle Arten von Apps, die in Teams verfügbar sind. Sie können z. B. App-Berechtigungsrichtlinien verwenden, um eine Drittanbieter-App oder eine benutzerdefinierte App schrittweise zu rollouten, indem Sie sie für bestimmte Benutzer zulassen.

:::image type="content" source="media/app-permission-policy-trimmed.png" alt-text="Screenshot einer App-Berechtigungsrichtlinie." lightbox="media/app-permission-policy.png":::

Weitere Informationen finden Sie [unter Verwalten von benutzerdefinierten App-Richtlinien und -Einstellungen](teams-app-permission-policies.md).

## <a name="app-setup-policies"></a>Richtlinien für das App-Setup

Mithilfe von App-Setuprichtlinien können Sie die App-Benutzeroberfläche für Ihre Benutzer anpassen. Sie wählen die Apps aus, die Sie an die App-Leiste in den Teams-Clients anheften möchten, und die Reihenfolge, in der sie angezeigt werden, auf Web-, Desktop- und mobilen Clients.

Hier sind einige Beispiele für die Verwendung von App-Setuprichtlinien:

* Installieren von Apps für Endbenutzer in deren persönlicher Microsoft Teams-Umgebung. Es trägt dazu bei, das Bewusstsein und die Akzeptanz der gewünschten Apps zu fördern. Heften Sie beispielsweise eine benutzerdefinierte Recruiting- und Talentmanagement-App für Mitglieder Ihres HR-Teams an.
* Heften Sie ausgewählte Kern-Apps an, z. B. Chat, Teams und Anrufe.

:::image type="content" source="media/app-setup-policy-trimmed.png" alt-text="Screenshot einer App-Setup-Richtlinie im Microsoft Teams Admin Center." lightbox="media/app-setup-policy.png":::

Weitere Informationen finden Sie [unter Verwalten von App-Setuprichtlinien](teams-app-setup-policies.md).

## <a name="custom-app-policies"></a>Richtlinien für benutzerdefinierte Apps

Teams ermöglicht Es Entwicklern in Ihrer Organisation, benutzerdefinierte Apps für interne Benutzer der Organisation zu erstellen, zu testen und bereitzustellen. Entwickler können ihre benutzerdefinierten Apps über Teams zur Genehmigung durch Teams-Administratoren übermitteln. Sie können App-Setuprichtlinien verwenden, um zu steuern, wer in Ihrer Organisation benutzerdefinierte Apps hochladen kann. Administratoren können den Endbenutzern ihrer Organisation erlauben, benutzerdefinierte Apps und Entwickler mithilfe der organisationsweiten App-Einstellungen hochzuladen.

:::image type="content" source="media/custom-app-policy-trimmed.png" alt-text="Screenshot, der zeigt, wie Sie benutzerdefinierte Apps in Ihrer Organisation im organisationsweiten Einstellungsbereich zulassen." lightbox="media/custom-app-policy.png":::

Weitere Informationen finden Sie [unter Verwalten von benutzerdefinierten App-Richtlinien und -Einstellungen](teams-custom-app-policies-and-settings.md).

## <a name="related-articles"></a>Verwandte Artikel

* [Verwalten von Microsoft Teams mit Richtlinien](manage-teams-with-policies.md)
