---
title: Benutzeranforderungen für Administratoren
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
ms.subservice: teams-apps
audience: admin
ms.collection:
- M365-collaboration
- m365-frontline
ms.reviewer: mhayrapetyan
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.manageapps.overview
description: Erfahren Sie, wie Sie die Endbenutzeranforderung für die Genehmigung der Apps verwalten und konfigurieren, die in einer Organisation blockiert sind.
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: 0967aec80bb88dff12141040fead94af9aae0616
ms.sourcegitcommit: 0bf44683f5263d7bf635689b4c1d813bd9842650
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2022
ms.locfileid: "67706224"
---
# <a name="manage-user-requests"></a>Verwalten von Benutzeranforderungen

Die in Ihrer Organisation blockierten Apps können sich auf die Produktivität und Zusammenarbeit der Endbenutzer auswirken. Endbenutzer können blockierte Apps nicht verwenden, aber solche Apps und ihre Informationen im Teams-Store anzeigen und die Genehmigung von Administratoren anfordern. Nachdem Sie die Anforderung ausgewertet haben, können Sie eine App zulassen oder die Anforderung schließen.

Diese Funktionalität gibt Ihnen ein Signal über die Nachfrage nach einer App in Ihrer Organisation. Sie können die Aggregatanzahl der Anforderungen für jede angeforderte App ganz einfach anzeigen. Es hilft Ihnen, eine fundierte Entscheidung darüber zu treffen, welche Apps zum Zulassen ausgewertet werden sollen.

Sie behalten die vollständige Kontrolle über die Apps, die für Benutzer zulässig oder blockiert sind. Wenn Sie eine App zulassen, bleiben die Steuerelemente und die Benutzeroberfläche zum Verwalten von Apps unverändert.

* Die Standardoption sendet die Benutzeranforderungen an das Teams Admin Center, in dem Sie [Benutzeranforderungen anzeigen und die angeforderten Apps zulassen](#view-user-requests-in-teams-admin-center) können.

   :::image type="content" source="media/user-request-blocked-apps.png" alt-text="Screenshot mit der Option, einen Administrator zur Genehmigung einer blockierten App anzufordern.":::

* Mit einer Anpassung können Sie die [Endbenutzererfahrung konfigurieren](#modify-the-default-setting-to-receive-end-user-requests) , die für Ihre Organisation am besten geeignet ist. Sie können eine Anweisung oder eine benutzerdefinierte Nachricht bereitstellen, die im Teams-App Store angezeigt wird, und die Anforderungsgenehmigungsoption leitet die Benutzer an eine organisationsspezifische URL, um ihre Anforderungen zu sammeln.

   :::image type="content" source="media/user-request-blocked-apps-redirected.png" alt-text="Screenshot, der die Endbenutzererfahrung für Apps im Store zeigt, wenn ein Administrator die URL zur Anforderung von Apps zulassen an eine organisationsspezifische URL umleitet.":::

## <a name="view-user-requests-in-teams-admin-center"></a>Anzeigen von Benutzeranforderungen im Teams Admin Center

Die von der Standardmethode empfangenen Endbenutzeranforderungen werden im Teams Admin Center angezeigt. Sie können die Anforderungen ganz einfach anzeigen und verwalten. Wir empfehlen eine regelmäßige Triage, um nach Endbenutzeranforderungen zu suchen. Führen Sie die folgenden Schritte aus, um die Apps anzuzeigen und zuzulassen:

1. Melden Sie sich beim Teams Admin Center an, und wechseln Sie zu "Apps verwalten" für **Teams-Apps** > .[](https://admin.teams.microsoft.com/policies/manage-apps)

1. Wählen Sie aus, ob die Spalte **"Anforderungen nach Benutzern** " angezeigt werden soll. Sie können die Spalte auch sortieren.

   :::image type="content" source="media/user-requests-tac.png" alt-text="Screenshot, der die Spalte für Benutzeranforderungen im Teams Admin Center zeigt und sortiert werden kann." lightbox="media/user-requests-tac-expanded.png":::

1. Um die App-Detailseite zu öffnen, die Sie zulassen möchten, wählen Sie den Namen der App aus.

1. Wählen Sie **"Anforderungen verwalten" aus**.

   :::image type="content" source="media/apps-manage-user-requests.png" alt-text="Screenshot der Option &quot;Anforderungen verwalten&quot; auf der Seite &quot;App-Details&quot;." lightbox="media/apps-manage-user-requests-expanded.png":::

1. Führen Sie einen oder mehrere der folgenden Schritte aus, wie im Popupdialogfeld angezeigt. Die Schritte zum Genehmigen einer App variieren je nach Methode zum Blockieren.

   * Wenn die App mithilfe von Berechtigungsrichtlinien blockiert wird, [ändern Sie die Berechtigungsrichtlinien](teams-app-permission-policies.md).
   * Wenn die App für alle Benutzer blockiert ist, [lassen Sie die App zu](manage-apps.md#allow-and-block-apps).
   * Wenn alle Apps für alle Benutzer blockiert sind, [ändern Sie organisationsweite Einstellungen](manage-apps.md#manage-org-wide-app-settings).

Endbenutzer können die Option **"Hinzufügen"** für eine App im Teams-Store anzeigen, um zu überprüfen, ob die App zulässig ist. Wenn Sie eine App nach dem Empfang von Anforderungen im Teams Admin Center zulassen, informiert Teams die Endbenutzer nicht darüber, dass auf ihre Anforderung reagiert wird. Wenn Sie eine App zulassen, wird der Anforderungszähler nicht auf Null zurückgesetzt.

## <a name="modify-the-default-setting-to-receive-end-user-requests"></a>Ändern der Standardeinstellung zum Empfangen von Endbenutzeranforderungen

Teams stellt eine Standardnachricht für Benutzer bereit, um eine Genehmigung für eine App anzufordern. Sie können die Standardeinstellung ändern, um eine benutzerdefinierte Nachricht mit Anweisungen, organisationsspezifischer URL oder beidem hinzuzufügen. Die Änderungen werden für jede App im Teams Store angezeigt.

Führen Sie die folgenden Schritte aus, um eine benutzerdefinierte Nachricht zu konfigurieren und Benutzer zu einer organisationsspezifischen URL umzuleiten:

1. Melden Sie sich beim Teams Admin Center an, und wechseln Sie zu "Apps verwalten" für **Teams-Apps** > .[](https://admin.teams.microsoft.com/policies/manage-apps)

1. Wählen Sie in der oberen rechten Ecke **organisationsweite App-Einstellungen** aus.

1. Um eine benutzerdefinierte Nachricht oder Anweisung im Teams-Speicher anzuzeigen, geben Sie eine Textnachricht in das Textfeld unter " **Konfiguration von Benutzeranforderungen**" ein. Das Feld hat einen Grenzwert von 300 Zeichen.

1. Führen Sie die folgenden Schritte aus, um eine organisationsspezifische URL zum Sammeln von Benutzeranforderungen bereitzustellen:

   1. Aktivieren Sie den **Umleitungsanforderungsschalter für externe Links** .
   1. Geben Sie Ihre organisationsspezifische URL an.

      :::image type="content" source="media/user-request-config-org-wide-setting.png" alt-text="Screenshot zum Umschalten der Anpassung der URL für die Benutzeranforderungen in der organisationsweiten Einstellungsbenutzeroberfläche.":::

1. Klicken Sie auf **Speichern**.

Wenn Sie sich dafür entscheiden, bleiben die Methoden zum Auswerten von Drittanbieter-Apps und zulassen, dass die angeforderten Apps unverändert bleiben.

## <a name="dismiss-user-requests"></a>Benutzeranforderungen schließen

Führen Sie die folgenden Schritte aus, um die Anforderungen an eine Zulassungs-App zu schließen:

1. Wählen Sie den Namen der App aus, für die Sie die Benutzeranfragen ablehnen möchten.
1. Wählen Sie **"Anforderungen verwalten" aus**.
1. Wählen Sie im Dialogfeld "Benutzeranforderungen verwalten" die Option " **Alle Anforderungen schließen" aus**.

   :::image type="content" source="media/dismiss-user-requests-apps.png" alt-text="Administratoren können eine Benutzeranfrage genehmigen, indem sie eine App zulassen, oder die Anfrage ablehnen und keine Maßnahmen ergreifen.":::

Wenn Sie eine Anfrage schließen, wird der Endbenutzer nicht darüber informiert, dass seine Anfrage darauf reagiert wird. Wenn Sie eine Anforderung zum Zulassen einer App schließen, wird die Anzahl der Anforderungen im Admin Center auf Null zurückgesetzt. Außerdem können Endbenutzer nach ein paar Stunden nach dem Schließen einer Anforderung erneut dieselbe App anfordern, um zugelassen zu werden.

## <a name="related-article"></a>Verwandter Artikel

* [Übersicht über die Verwaltung von Drittanbieter-Apps](manage-apps.md).
