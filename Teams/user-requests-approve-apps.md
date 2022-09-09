---
title: Benutzer fordert Administratoren auf, Apps zuzulassen
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
description: Erfahren Sie, wie Sie Endbenutzeranforderungen verwalten und konfigurieren, um die in einer Organisation blockierten Apps zuzulassen.
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: c47578184aa97f9c6cc366e186c1590ef1e3fba4
ms.sourcegitcommit: ebffec34c050421dc8d09a16907644657ce323f4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2022
ms.locfileid: "67637311"
---
# <a name="manage-user-requests-to-allow-apps-that-are-blocked-by-admins"></a>Verwalten von Benutzeranforderungen zum Zulassen von Apps, die von Administratoren blockiert werden

Die Apps, die Sie in Ihrer Organisation blockieren, können die Produktivität und Zusammenarbeit der Endbenutzer verringern. Apps, die im Teams-Store verfügbar sind, aber in Ihrer Organisation blockiert sind, können von den Endbenutzern nicht verwendet werden. Um jedoch auf dem Laufenden zu bleiben, können die Endbenutzer blockierte Apps anzeigen, die App-Informationen und die Anwendungsfälle anzeigen, in deren Server sie ausgeführt werden. Benutzer können die Administratorgenehmigung anfordern, damit sie diese Apps in Teams verwenden können, nachdem Sie die App zugelassen haben.

Diese Funktion gibt Ihnen ein Signal über die Nachfrage nach einer App in Ihrer Organisation. Sie können ganz einfach die aggregierte Anzahl von Anforderungen für Apps anzeigen und fundierte Entscheidungen darüber treffen, welche Apps in Ihrer Organisation zugelassen werden sollen.

Sie behalten die vollständige Kontrolle über die Apps, die für Benutzer zulässig oder blockiert sind. Wenn Sie eine App zulassen, bleiben die Steuerelemente und die Benutzeroberfläche zum Verwalten von Apps unverändert.

* Die Standardoption sendet die Benutzeranforderungen im Teams Admin Center, wo Sie [Benutzeranforderungen anzeigen und die angeforderten Apps zulassen](#view-user-requests-and-allow-the-requested-apps) können.

   :::image type="content" source="media/user-request-blocked-apps.png" alt-text="Screenshot mit der Option, einen Administrator zur Genehmigung einer blockierten App anzufordern.":::

* Mit einer Anpassung können Sie die [Endbenutzererfahrung konfigurieren](#modify-the-default-setting-to-receive-end-user-requests-to-allow-an-app) , indem Sie den Benutzer zu einer benutzerdefinierten App-Anforderungsmethode umleiten. Sie können eine benutzerdefinierte Textnachricht bereitstellen, um Benutzer zu informieren und die Benutzer an die interne URL Ihrer Organisation zu leiten, um Anforderungen zum Zulassen von Apps zu sammeln.

   :::image type="content" source="media/user-request-blocked-apps-redirected.png" alt-text="Screenshot, der die Endbenutzererfahrung für Apps im Store zeigt, wenn ein Administrator die ANFORDERUNGS-URL für apps zulassen an eine benutzerdefinierte URL umleitet.":::

## <a name="modify-the-default-setting-to-receive-end-user-requests-to-allow-an-app"></a>Ändern der Standardeinstellung zum Empfangen von Endbenutzeranforderungen zum Zulassen einer App

Führen Sie die folgenden Schritte aus, um eine benutzerdefinierte Nachricht zu konfigurieren und Benutzer an eine organisationsspezifische URL umzuleiten, um die App-Genehmigung anzufordern:

1. Melden Sie sich beim Teams Admin Center an, und greifen Sie auf die Seite "**[Apps verwalten"](https://admin.teams.microsoft.com/policies/manage-apps)** von **Teams-Apps** >  zu.

1. Wählen Sie organisationsweite App-Einstellungen aus.

1. Um eine benutzerdefinierte Nachricht oder Anweisung im Teams-Clientspeicher anzuzeigen, stellen Sie eine Textnachricht in der Konfiguration der Benutzeranforderungen bereit.

1. Gehen Sie wie folgt vor, um eine organisationsspezifische URL zum Sammeln von Benutzeranforderungen bereitzustellen:

   1. Ändern Sie die Option "Umleitungsanforderungen in externes Tool" in "Ein".
   1. Geben Sie Ihre organisationsspezifische, benutzerdefinierte URL an.

      :::image type="content" source="media/user-request-config-org-wide-setting.png" alt-text="Screenshot zum Umschalten der Anpassung der URL für die Benutzeranforderung zum Aufheben der Blockierung der App in der organisationsweiten Einstellungsbenutzeroberfläche.":::

1. Klicken Sie auf **Speichern**.

## <a name="view-user-requests-and-allow-the-requested-apps"></a>Anzeigen von Benutzeranforderungen und Zulassen der angeforderten Apps

Die von der Standardmethode empfangenen Endbenutzeranforderungen werden im Teams Admin Center angezeigt. Sie können die Anforderungen ganz einfach anzeigen und verwalten. Es wird dringend empfohlen, eine regelmäßige Einstufung für die Überprüfung auf Endbenutzeranforderungen zu verwenden. Führen Sie die folgenden Schritte aus, um die Apps anzuzeigen und zuzulassen:

1. Melden Sie sich beim Teams Admin Center an, und greifen Sie auf die Seite "**[Apps verwalten"](https://admin.teams.microsoft.com/policies/manage-apps)** von **Teams-Apps** >  zu.

1. Wählen Sie aus, ob die Spalte **"Anforderungen nach Benutzern** " angezeigt werden soll. Sie können die Spalte auch sortieren.

   :::image type="content" source="media/user-requests-tac.png" alt-text="Screenshot, der die Spalte für Benutzeranforderungen im Teams Admin Center zeigt und sortiert werden kann." lightbox="media/user-requests-tac-expanded.png":::

1. Um die App-Detailseite zu öffnen, die Sie zulassen möchten, wählen Sie den Namen der App aus.

1. Wählen Sie **"Anforderungen verwalten" aus**.

   :::image type="content" source="media/apps-manage-user-requests.png" alt-text="Screenshot der Option &quot;Anforderungen verwalten&quot; auf der Seite &quot;App-Details&quot;." lightbox="media/apps-manage-user-requests-expanded.png":::

1. Führen Sie einen oder mehrere der folgenden Schritte aus, wie im Popupdialogfeld angezeigt. Die Schritte zum Genehmigen einer App variieren je nach Methode zum Blockieren.

   * Wenn die App mithilfe von Berechtigungsrichtlinien blockiert wird, [ändern Sie die Berechtigungsrichtlinien](teams-app-permission-policies.md).
   * Wenn die App für alle Benutzer blockiert ist, [lassen Sie die App zu](manage-apps.md#allow-and-block-apps).
   * Wenn alle Apps für alle Benutzer blockiert sind, [ändern Sie organisationsweite Einstellungen](manage-apps.md#manage-org-wide-app-settings).

1. Wenn Sie optional zu einer benutzerdefinierten Konfiguration zu Ihrer organisationsspezifischen URL wechseln möchten, wählen Sie im Dialogfeld "Benutzeranforderungen verwalten" den Link "Benutzeranforderungen konfigurieren" aus. Es öffnet den organisationsweiten App-Einstellungsbereich, in dem Sie [die Endbenutzeranforderungsumgebung konfigurieren](#modify-the-default-setting-to-receive-end-user-requests-to-allow-an-app) können.

Wenn Sie eine App zulassen, nachdem Sie Anforderungen im Teams Admin Center erhalten haben, informiert Teams den Endbenutzer nicht darüber, dass seine Anforderung erfüllt wird. Der Benutzer kann die App im Teams Store überprüfen, um zu überprüfen, ob die App zulässig ist. Die Option zum Hinzufügen der App ist für den Benutzer verfügbar, nachdem Sie sie zugelassen haben. Wenn Sie eine App nach dem Empfang von Anforderungen über Ihre organisationsspezifische Methode zulassen, gelten Ihre internen Mechanismen zur Bereitstellung einer Statusaktualisierung für den Endbenutzer.

Schließen Sie die Anforderungen, um die Anzahl der App-Anforderungen auf Null zurückzusetzen. Durch das Zulassen einer App wird der Anforderungszähler nicht auf Null zurückgesetzt.

## <a name="dismiss-user-requests"></a>Benutzeranforderungen schließen

Führen Sie die folgenden Schritte aus, um die Anforderungen zum Zulassen der App zu schließen:

1. Wählen Sie den Namen der App aus, für die Sie die Benutzeranfragen ablehnen möchten.
1. Wählen Sie **Anforderungen verwalten** und im Dialogfeld **alle Anfragen ablehnen** aus.

   :::image type="content" source="media/dismiss-user-requests-apps.png" alt-text="Administratoren können eine Benutzeranfrage genehmigen, indem sie eine App zulassen, oder die Anfrage ablehnen und keine Maßnahmen ergreifen.":::

Wenn Sie eine Anfrage schließen, wird der Endbenutzer nicht darüber informiert, dass seine Anfrage darauf reagiert wird. Wenn Sie eine Anforderung zum Zulassen einer App schließen, wird die Anzahl der Anforderungen im Admin Center auf Null zurückgesetzt. Außerdem können Endbenutzer nach einigen Stunden nach dem Schließen einer Anforderung erneut dieselbe App anfordern, um zugelassen zu werden.

## <a name="related-article"></a>Verwandter Artikel

* [Übersicht über die Verwaltung von Drittanbieter-Apps](manage-apps.md).
