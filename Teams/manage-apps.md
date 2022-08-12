---
title: Verwalten Sie Ihre Apps im Microsoft Teams Admin Center
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
ms.subservice: teams-apps
ms.custom: intro-get-started
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: vaibhava
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.manageapps.overview
description: Erfahren Sie, wie Sie Teams-Apps verwalten. Erfahren Sie, wie Sie Apps zulassen oder blockieren, den Status auf Organisationsebene und App-Eigenschaften überprüfen, benutzerdefinierte Apps hochladen und App-Einstellungen verwalten.
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: bbad8eb283fe3e27397b2ddd5d22a91fc6570394
ms.sourcegitcommit: 63dcc92b2d5d50e2c0c074a1209625e16086ca45
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2022
ms.locfileid: "67298864"
---
# <a name="manage-teams-apps-in-the-microsoft-teams-admin-center"></a>Verwalten Sie Teams-Apps im Microsoft Teams Admin Center

Sie verwalten Apps für Ihre Organisation auf der Seite **Teams-Apps** im Teams Admin Center-Portal. Verwenden Sie die Seite Apps verwalten, um alle Teams-Apps im App-Katalog Ihrer Organisation anzuzeigen und zu verwalten, wichtige Anwendungsfälle für die App-Verwaltung zu berücksichtigen, den Zugriff auf Apps mithilfe von Richtlinien zu definieren und vieles mehr.

:::image type="content" source="media/manage-apps.png" alt-text="Screenshot der Seite Apps verwalten." lightbox="media/manage-apps.png":::

Zum Verwalten von Apps verwenden Sie Richtlinien, um die Berechtigungen für Benutzer, die Installation von Apps und das Hochladen von benutzerdefinierten Apps zu steuern, die in Ihrer Organisation erstellt wurden. Informationen zum Verständnis von Richtlinien finden Sie unter [Übersicht über App-Richtlinien](app-policies.md).

Um das Teams Admin Center verwenden zu können, müssen Sie über die Rolle Globaler Administrator oder Teams-Administrator verfügen. Einzelheiten finden Sie unter [Teams-Administratorrollen](./using-admin-roles.md) und [Microsoft 365-Administratorrollen](/microsoft-365/admin/add-users/about-admin-roles).

> [!NOTE]
> Die Seite Apps verwalten ist in Microsoft 365 Government Community Cloud High (GCCH)- oder Department of Defense (DoD)-Bereitstellungen von Teams nicht verfügbar.

Während der Erstellung einer App erstellen die Entwickler eine App-ID und fügen sie der Manifestdatei hinzu. Sie können diese externe App-ID auf der Seite Apps verwalten anzeigen, nachdem Sie die Spalte `External app ID` in den Spalteneinstellungen aktiviert haben. Sie können es auch auf der App-Detailseite einer benutzerdefinierten App anzeigen. Die ID gilt nur für benutzerdefinierte Apps.

## <a name="app-management-use-cases-and-the-available-interfaces"></a>Anwendungsfälle für das App-Management und die verfügbaren Schnittstellen

Die Optionen zum Ausführen der meisten Anwendungsfälle für die App-Verwaltung sind im Teams Admin Center verfügbar. Darüber hinaus sind einige Optionen in anderen Portalen oder auf verschiedenen Seiten im Teams Admin Center verfügbar.

| Anwendungsfälle für die App-Verwaltung | Link zur Schnittstelle | Dokumentation |
|:----|:----|:----|
| **Im Teams Admin Center** | | |
| Steuern Sie, welche Apps Benutzern in Ihrer Organisation zur Verfügung stehen, indem Sie Apps zulassen und blockieren. Sie können auch benutzerdefinierte Apps hochladen und genehmigen. Nachdem Sie Apps auf dieser Seite verwaltet haben, können Sie App-Berechtigungen und App-Setup-Richtlinien verwenden, um zu konfigurieren, welche Apps für bestimmte Benutzer im App Store Ihrer Organisation verfügbar sind. | [Verwalten von Teams im Admin Center für Teams](https://admin.teams.microsoft.com/policies/manage-apps) | Aktueller Artikel |
| App-Berechtigungsrichtlinien steuern, welche Apps Sie Teams-Benutzern in Ihrer Organisation zur Verfügung stellen möchten. Sie können die globale (organisationsweite) Standardrichtlinie verwenden und anpassen, oder Sie können eine oder mehrere Richtlinien erstellen, um die Anforderungen Ihrer Organisation zu erfüllen. | [Berechtigungsrichtlinien](https://admin.teams.microsoft.com/policies/app-permission) | [App-Berechtigungsrichtlinien verwalten](teams-app-permission-policies.md) |
| App-Setup-Richtlinien steuern, wie Apps einem Benutzer mit der Teams-App zur Verfügung gestellt werden. Verwenden Sie die globale Richtlinie (organisationsweite Standardeinstellung) und passen Sie sie an oder erstellen Sie benutzerdefinierte Richtlinien und weisen Sie sie einer Gruppe von Benutzern zu. | [Setuprichtlinien](https://admin.teams.microsoft.com/policies/app-setup) | [Verwalten von Richtlinien für App-Setup in Teams](teams-app-setup-policies.md) |
| Sie können benutzerdefinierte Apps als App-Pakete entwickeln und hochladen und im App Store Ihrer Organisation verfügbar machen. | Organisationsweite App-Einstellungen in [Apps verwalten](https://admin.teams.microsoft.com/policies/manage-apps) | [Verwalten Sie benutzerdefinierte App-Richtlinien](teams-custom-app-policies-and-settings.md) |
| Sie können den Teams-App-Store mit dem Logo, dem benutzerdefinierten Hintergrund oder der Farbe Ihrer Organisation anpassen. | [Store anpassen](https://admin.teams.microsoft.com/policies/customize-appstore) | [Anpassen des App Store Ihrer Organisation](customize-your-app-store.md) |
| Der Team-App-Nutzungsbericht enthält Informationen darüber, welche Apps verwendet werden, aktive Benutzer und andere Informationen zur App-Nutzung. | [Verwendungsberichte](https://admin.teams.microsoft.com/analytics/reports) | [Teams-App-Nutzungsbericht](teams-analytics-and-reports/app-usage-report.md) |
| Ihre Benutzer können Apps hinzufügen, wenn sie Meetings veranstalten oder mit Gästen chatten. Sie können auch von Gästen geteilte Apps verwenden, wenn sie an extern gehosteten Meetings oder Chats teilnehmen. Es gelten die Datenrichtlinien der Organisation des hostenden Benutzers und die Datenfreigabepraktiken aller Apps von Drittanbietern, die von der Organisation dieses Benutzers freigegeben werden. | [Externer Zugriff](https://admin.teams.microsoft.com/company-wide-settings/external-communications) | [App-Verhalten je nach Benutzertypen](non-standard-users.md) |
| Mit dem Gastzugriff können Sie Personen außerhalb Ihrer Organisation Zugriff auf Anwendungen und andere Teams-Funktionen gewähren und gleichzeitig die Kontrolle über Ihre Unternehmensdaten behalten. | [Gastzugriff](https://admin.teams.microsoft.com/company-wide-settings/guest-configuration) | [Gastzugriff in Teams](guest-access.md) |
| Aktualisierungsrichtlinien werden verwendet, um Teams und Office-Vorschaubenutzer zu verwalten, die Vorabversions- oder Vorschaufeatures in der Teams-App sehen. | [Teams-Updaterichtlinien](https://admin.teams.microsoft.com/policies/updatemanagement) | [Öffentliche Teams-Vorschau](public-preview-doc-updates.md) |
| **Außerhalb des Teams Admin Centers** | | |
| Verwalten Sie Lizenzen und Abonnements von Drittanbieter-Apps im Microsoft 365 Admin Center | [Microsoft 365 Admin Center](https://admin.microsoft.com/#/licenses) | [Verwalten Sie App-Abonnements von Drittanbietern](/microsoft-365/commerce/manage-saas-apps) |
| Audit-Teams-App-Ereignisse im Microsoft Purview-Compliance-Portal. | [Überwachung](https://compliance.microsoft.com/auditlogsearch?viewid=Async%20Search) | [Microsoft Teams-Aktivitäten](audit-app-management-activities.md) |
| Anwendungen können auf drei Arten Berechtigungen für Ihre Organisation und ihre Daten erteilt werden: Ein Administrator stimmt der Anwendung für alle Benutzer zu, ein Benutzer erteilt der Anwendung seine Zustimmung oder ein Administrator integriert eine Anwendung und ermöglicht den Self-Service-Zugriff oder weist Benutzern direkt zu die Anwendung. Überprüfen Sie die Graph-Berechtigungen für Apps. Überprüfen Sie die Berechtigungen, die Benutzer bereitgestellt oder die Administratoren delegiert haben. | [Azure AD-Portal](https://aad.portal.azure.com/) | [Überprüfen von Berechtigungen, die Anwendungen erteilt wurden](/azure/active-directory/manage-apps/manage-application-permissions) |

<!---
| xxx | [Manage users](https://admin.teams.microsoft.com/users) | [Add users and assign licenses](/microsoft-365/admin/add-users/add-users?view=o365-worldwide) |  
--->

## <a name="allow-and-block-apps"></a>Zulassen und Blockieren von Apps

Auf der Seite Apps verwalten können Sie einzelne Apps auf Organisationsebene zulassen oder blockieren. Auf der Seite werden alle verfügbaren Apps und ihr aktueller App-Status auf Organisationsebene angezeigt. Die Liste der Apps umfasst Apps, die von Microsoft, von Drittentwicklern und von Entwicklern innerhalb Ihrer Organisation bereitgestellt werden.

So erlauben oder blockieren Sie eine App:

1. Melden Sie sich beim Teams Admin Center an.
1. Greifen Sie auf die **Seite** > **[Apps verwalten](https://admin.teams.microsoft.com/policies/manage-apps)** für Teams-Apps zu.
1. Wählen Sie eine App aus der Liste der Apps aus. Sie können nach dem Namen der App suchen und sie dann auswählen.
1. Wählen Sie die Option **Zulassen** oder **Blockieren**.

Wenn Sie eine App auf der Seite [Apps verwalten](https://admin.teams.microsoft.com/policies/manage-apps) im Admin Center von Teams zulassen (oder blockieren), wird die jeweilige App für alle Benutzer in Ihrer Organisation zugelassen (oder blockiert). Diese Methode unterscheidet sich von der App-Berechtigungsrichtlinie darin, dass das Zulassen (oder Blockieren) einer App über die Berechtigungsrichtlinie nur die spezifischen Benutzer betrifft, denen die Richtlinie zugewiesen ist.

Ein Benutzer kann eine App nur installieren und verwenden, wenn die App über die mandantenweite Einstellung und für den Benutzer über die Berechtigungsrichtlinie zugelassen ist.

## <a name="manage-user-requests-to-allow-apps"></a>Verwalten von Benutzeranforderungen zum Zulassen von Apps

Endbenutzer können die blockierten Apps im Teams Store anzeigen, aber nicht verwenden. Für die blockierten Apps steht eine Option zum Anfordern der Administratorgenehmigung zur Verfügung. Diese Anforderungen werden im Teams Admin Center gesammelt, und Administratoren können die Anforderungen anzeigen und verwalten, wenn sie möchten. Es wird dringend empfohlen, eine regelmäßige Einstufung für die Überprüfung auf Endbenutzeranforderungen zu verwenden.

  :::image type="content" source="media/user-request-blocked-apps.png" alt-text="Fordern Sie einen Administrator auf, eine blockierte App zu genehmigen, indem Sie die Option „Genehmigung anfordern“ im Teams Store auswählen.":::

### <a name="view-a-request"></a>Anzeigen einer Anforderung

 1. Melden Sie sich beim Teams Admin Center an, und wählen Sie **Teams Apps** > **[Apps verwalten](https://admin.teams.microsoft.com/policies/manage-apps)** aus.

    :::image type="content" source="media/requested-apps1.png" alt-text="Endbenutzeranforderungen für blockierte Apps werden im Teams Admin Center in der Spalte mit dem Titel Anforderungen von Benutzern angezeigt." lightbox="media/requested-apps.png":::

 1. Um die Anzahl der Anfragen für jede App anzuzeigen und zu überprüfen, sortieren Sie die Anforderungen in der Spalte **Anforderungen nach Benutzer**. Sie können den Namen der Benutzer, die eine App angefordert haben, nicht anzeigen.
 1. Um eine App zuzulassen, wählen Sie den Namen der App aus, und die Seite mit den App-Details wird geöffnet.
 1. Wählen Sie **Anforderungen verwalten** aus und führen Sie die im Popup-Dialogfeld angezeigten Schritte aus. Basierend auf der zum Blockieren einer App verwendeten Methode sind einer oder mehrere der folgenden Schritte erforderlich, um die Blockierung aufzuheben:

    * Wenn die App mithilfe von Berechtigungsrichtlinien blockiert ist, lassen Sie die App zu, indem Sie die [Berechtigungsrichtlinien ändern](teams-app-permission-policies.md).
    * Wenn die App für alle Benutzer blockiert ist, [lassen Sie die App zu](#allow-and-block-apps).
    * Wenn alle Apps für alle Benutzer blockiert sind, ändern Sie die [organisationsweiten Einstellungen](#manage-org-wide-app-settings).

 Wenn ein Administrator eine App zulässt, informiert Teams den Endbenutzer nicht darüber, dass auf seine Anfrage reagiert wird. Der Benutzer kann die App im Teams Store anzeigen, um zu prüfen, ob er die App zu seinem Teams-Client hinzufügen kann oder nicht. Wenn die App von einem Administrator genehmigt wurde, können Benutzer sie hinzufügen. Wenn ein Administrator die Anforderung alternativ nicht genehmigt und ablehnt, können Endbenutzer sie erneut anfordern.

### <a name="dismiss-a-user-request"></a>Ablehnen einer Benutzeranforderung

 1. Wählen Sie den Namen der App aus, für die Sie die Benutzeranfragen ablehnen möchten.
 1. Wählen Sie **Anforderungen verwalten** und im Dialogfeld **alle Anfragen ablehnen** aus.
 1. Wenn eine Anfrage verworfen wird, werden die Benutzeranfragen auf null zurückgesetzt.

  :::image type="content" source="media/reject.png" alt-text="Administratoren können eine Benutzeranfrage genehmigen, indem sie eine App zulassen, oder die Anfrage ablehnen und keine Maßnahmen ergreifen.":::

Wenn ein Administrator eine Anfrage ablehnt, wird der Endbenutzer nicht darüber informiert, dass auf seine Anfrage reagiert wird. Nachdem ein Administrator eine Anfrage abgelehnt hat, kann der Endbenutzer die App erneut anfordern.

## <a name="allow-the-apps-that-are-blocked-by-the-developers"></a>Lassen Sie die Apps zu, die von den Entwicklern blockiert werden

Wenn ein Entwickler eine App im Teams Store veröffentlicht, benötigen einige Apps möglicherweise einen Administrator, um die App zu konfigurieren. Die Administratoren stellen die App den Endbenutzern zur Verfügung, wenn die App eingerichtet wird.

Beispielsweise ist Contoso Electronics ein App-Entwickler, der eine Helpdesk-App für Microsoft Teams erstellt hat. Contoso Electronics möchte, dass seine Kunden bestimmte Eigenschaften der App einrichten, damit sie wie erwartet funktioniert, wenn Benutzer mit der App interagieren. Bevor ein Administrator die Anwendung zulässt, wird sie im Teams Admin Center als **vom Herausgeber blockiert** angezeigt und ist standardmäßig für Endbenutzer ausgeblendet. Nachdem Sie die Anleitung des Herausgebers zum Einrichten der App befolgt haben, können Sie sie Benutzern zur Verfügung stellen, indem Sie den Status in **Zugelassen** ändern.

:::image type="content" source="media/blocked-by-publisher.png" alt-text="Screenshot des Status Blockiert durch Herausgeber im Admin Center von Teams.":::

Informationen dazu, wie Entwickler eine App standardmäßig blockieren, finden Sie unter [App ausblenden, bis der Administrator zustimmt](/microsoftteams/platform/concepts/design/enable-app-customization#hide-teams-app-until-admin-approves).

## <a name="manage-org-wide-app-settings"></a>Verwalten Sie organisationsweite App-Einstellungen

Verwenden Sie organisationsweite App-Einstellungen, um zu steuern, ob Benutzer mit einer [F-Lizenz](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt) die maßgeschneiderte Frontline-App-Erfahrung erhalten, ob Benutzer Apps von Drittanbietern installieren können und ob Benutzer benutzerdefinierte Apps in Ihrer Organisation hochladen oder mit ihnen interagieren können. Organisationsweite App-Einstellungen regeln das Verhalten für alle Benutzer und setzen alle anderen App-Berechtigungsrichtlinien, die den Benutzern zugewiesen wurden, außer Kraft.

> [!NOTE]
> Informationen zum Verwenden von organisationsweiten App-Einstellungen in Bereitstellungen von Microsoft 365 Government – Government Community Cloud High GCCH und Department of Defense (DoD) von Teams finden Sie unter [Verwalten von App-Berechtigungsrichtlinien in Teams](teams-app-permission-policies.md).

1. Wählen Sie auf der Seite Apps verwalten die Option **Organisationsweite App-Einstellungen** aus. Sie können dann die gewünschten Einstellungen in diesem Bereich konfigurieren.

    :::image type="content" source="media/manage-apps-org-wide-app-settings.png" alt-text="Screenshot des Bereichs Organisationsweite App-Einstellungen auf der Seite Apps verwalten":::

1. Deaktivieren oder aktivieren Sie unter **Maßgeschneiderte Apps** die Option **Maßgeschneiderte Apps anzeigen**. Wenn diese Einstellung aktiviert ist, erhalten Benutzer mit einer [F-Lizenz](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt) die maßgeschneiderte Frontline-App-Erfahrung. Diese Erfahrung steckt die relevantesten Apps in Teams für Frontline-Mitarbeiter fest. Weitere Informationen finden Sie unter Passen Sie [Teams-Apps für Ihre Außendienstmitarbeiter an](pin-teams-apps-based-on-license.md).

    Diese Funktion ist für F-Lizenzen verfügbar. Andere Lizenztypen werden in Zukunft unterstützt.
1. Aktivieren oder deaktivieren Sie unter **Drittanbieter-Apps** diese Einstellungen, um den Zugriff auf Drittanbieter-Apps zu steuern:

    * **Drittanbieter-Apps zulassen**: Steuert, ob Benutzer Drittanbieter-Apps verwenden können. Wenn Sie diese Einstellung deaktivieren, können Ihre Benutzer keine Apps von Drittanbietern installieren oder verwenden, und der App-Status dieser Apps wird in der **Tabelle als organisationsweit blockiert** angezeigt.

        > [!NOTE]
        > Wenn **Drittanbieter-Apps zulassen** deaktiviert ist, sind [ausgehende Webhooks](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) weiterhin für alle Benutzer aktiviert, aber Sie können sie auf Benutzerebene steuern, indem Sie die ausgehende Webhook-App über [App-Berechtigungsrichtlinien](teams-app-permission-policies.md) zulassen oder blockieren. Beachten Sie Folgendes: Wenn Sie über vorhandene [App-Berechtigungsrichtlinien](teams-app-permission-policies.md) für **Microsoft-Apps** verfügen, die **die Einstellung Bestimmte Apps zulassen und alle anderen blockieren**, und Sie ausgehende Webhooks für Benutzer aktivieren möchten, fügen Sie die Ausgehende Webhook-App zur Liste hinzu.

        > [!NOTE]
        > Benutzer von Microsoft Teams können Apps hinzufügen, wenn sie Besprechungen oder Chats mit Personen aus anderen Organisationen hosten. Sie können auch Apps verwenden, die von Personen in anderen Organisationen freigegeben werden, wenn sie an Besprechungen oder Chats teilnehmen, die von diesen Organisationen gehostet werden. Es werden die Datenrichtlinien der Organisation des Hostingbenutzers sowie die Datenfreigabemethoden von Drittanbieter-Apps, die von der Organisation dieses Benutzers freigegen werden, angewendet.

    * **Alle neuen Drittanbieter-Apps, die im Store veröffentlicht werden, standardmäßig zulassen**: Steuert, ob neue Drittanbieter-Apps, die im Teams-App-Store veröffentlicht werden, automatisch in Teams verfügbar gemacht werden. Sie können diese Option nur aktivieren, wenn Sie Drittanbieter-Apps zulassen.

1. Deaktivieren oder aktivieren Sie unter **Benutzerdefinierte Apps** die Option **Interaktionen mit benutzerdefinierten Apps zulassen**. Diese Einstellung steuert, ob Benutzer mit benutzerdefinierten Apps interagieren können. Weitere Informationen finden Sie unter [Verwalten von benutzerdefinierten App-Richtlinien und Einstellungen in Teams](teams-custom-app-policies-and-settings.md).
1. Wählen Sie **Speichern** aus, damit die organisationsweiten App-Einstellungen wirksam werden.

## <a name="related-article"></a>Verwandter Artikel

* [Verwalten Sie Teams während des Übergangs vom Skype for Business Admin Center](manage-teams-skypeforbusiness-admin-center.md)
