---
title: Verwalten Ihrer Apps im Microsoft Teams Admin Center
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: vaibhava
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.manageapps.overview
description: Erfahren Sie, wie Sie Ihre Teams-Apps auf der Seite "Apps verwalten" im Microsoft Teams Admin Center verwalten.
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: facb10f1ad20482c8760a32ba1319b3ed80100e8
ms.sourcegitcommit: 836926a4914eb33fc3e0d8d6c84cee886cb1a5a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2022
ms.locfileid: "65137026"
---
# <a name="manage-teams-apps-in-the-microsoft-teams-admin-center"></a>Verwalten Teams Apps im Microsoft Teams Admin Center

Sie verwalten Apps für Ihre Organisation in **Teams Apps** im Admin Center. Verwenden Sie die Seite ["Apps verwalten](https://admin.teams.microsoft.com/policies/manage-apps)", um alle Teams Apps im App-Katalog Ihrer Organisation anzuzeigen und zu verwalten. Auf der Seite "Apps verwalten" erhalten Sie einen Einblick in alle verfügbaren Apps in Ihrem Mandantenkatalog, die Ihnen die Informationen bereitstellen, die Sie benötigen, um zu entscheiden, welche Apps in Ihrer Organisation zugelassen oder blockiert werden sollen. Sie können den Status und die Eigenschaften von Apps auf Organisationsebene anzeigen, Apps auf Organisationsebene blockieren oder zulassen, neue benutzerdefinierte Apps in Ihren Mandantenkatalog hochladen und organisationsweite App-Einstellungen verwalten.

![Screenshot der Seite "Apps verwalten".](media/manage-apps.png)

Um Teams Admin Center verwenden zu können, müssen Sie ein globaler Administrator oder Teams Dienstadministrator sein. Ausführliche Informationen finden Sie [unter Teams Administratorrollen](./using-admin-roles.md).

Zum Verwalten von Apps verwenden Sie Richtlinien, um Berechtigungen für Benutzer, die Installation von Apps und das Hochladen von benutzerdefinierten Apps zu steuern, die in Ihrer Organisation erstellt wurden. Informationen zu Richtlinien finden Sie [unter Übersicht über App-Richtlinien](app-policies.md).

> [!NOTE]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

> [!NOTE]
> Die Seite "Apps verwalten" ist in Microsoft 365 Government Community Cloud High(GCCH)- oder Department of Defense (DoD)-Bereitstellungen von Teams nicht verfügbar.

<!--- TBD: This info belongs in the app policy overview article. Title it as mentioned in the spreadsheet.

* **App permission policy**: With it, you can control what apps are available to specific users in your organization. You can allow or block all apps or specific apps published by Microsoft, third-parties, and your organization. See [Manage app permission policies in Teams](teams-app-permission-policies.md).
* **App setup policies**: It lets you customize the app experience for your users. You choose the apps that you want to pin to the app bar in the Teams clients and the order in which they appear, on web, desktop, and mobile clients. See [Manage app setup policies in Teams](teams-app-setup-policies.md).
* **Custom app policies and settings**: Teams allows developers in your organization to build, test, and deploy custom apps to other users. Custom apps can be added to Teams by uploading an app package in a .zip file directly to a team or in the personal context. You can use app setup policies to control who in your organization can upload custom apps. You can also set org-wide settings to control whether users can interact with specific custom apps. See [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings).

The following are the important use cases you can accomplish via the the Manage apps page:

* [Allow or block apps at the org level](#allow-and-block-apps)
* [Apps blocked by publishers](#apps-blocked-by-publishers)
* [Add apps to teams](#add-an-app-to-a-team)
* [Approve or upload new custom apps to your organization's app store](#publish-a-custom-app-to-your-organizations-app-store)
* [View permissions requested by apps](#view-resource-specific-consent-permissions)
* [Grant consent to apps](#grant-admin-consent-to-apps)
* [Purchase service for third-party apps](#purchase-services-for-third-party-apps)
* [See org-level status and properties of apps](#view-apps)
* [Manage org-wide app settings](#manage-org-wide-app-settings)
* [View security and compliance information for Microsoft 365 Certified apps](#view-security-and-compliance-information-for-microsoft-365-certified-apps)

<!--- TBD: Commenting for now in favor of the definition list above: 

The Manage apps page gives you a view into all available apps, providing you with the information you need to decide which apps to allow or block across your organization. You can then use [app permission policies](teams-app-permission-policies.md), [app setup policies](teams-app-setup-policies.md), and [custom app policies and settings](teams-custom-app-policies-and-settings.md) to configure the app experience for specific users in your organization.

In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**. You must be a global admin or Teams service admin to access the page.

--->

<!--- TBD: Move this view apps section to a new article about navigating and understanding TAC. It is yet to be created.

## View apps

You can view every app including the following information about each app.

![Screenshot of the apps details page for an app.](media/app-detail-page.jpg)

- **Name**: The app name. Select the app name to go to the app details page to see more information about the app. This includes a description of the app, whether it's allowed or blocked, version, privacy policy, terms of use, categories that apply to the app, certification status, supported capabilities, and app ID.
- **Certification**: If the app has gone through certification, you'll see either **Microsoft 365 certified** or **Publisher attestation**. Select the link to view certification details for the app. If you see `--`, we don't have certification information for the app. To learn more about certified apps in Teams, read [Microsoft 365 App Certification program](/microsoft-365-app-certification/overview).
- **Publisher**: Name of the publisher.
- **Publishing status**: Publishing status of custom apps.
- **Status**: Status of the app at the org level, which can be one of the following:
  - **Allowed**: The app is available for all users in your organization.
  - **Blocked**: The app is blocked and not available for any users in your organization.
  - **Blocked by publisher**: The app is blocked by the publisher and is hidden from end-users by default. After you set up the app using the publisher's guidance, you can allow or block the app to make it available to end-users.
  - **Blocked org-wide**: The app is blocked in org-wide app settings.
      It's important to know that this column represents the allowed and blocked status of apps that were formerly on the **Org-wide settings** pane. You now view, block, and allow apps at the org-wide on the **Manage apps** page.
- **Licenses**: Indicates whether an app offers a Software as a Service (SaaS) subscription for purchase. This column applies only to third-party apps. Each third-party app will have one of the following values:
  - **Purchase**: The app offers a SaaS subscription and is available to purchase.  
  - **Purchased**: The app offers a SaaS subscription and you've purchased licenses for it.
  - **- -**: The app doesn't offer a SaaS subscription.
- **Custom app**: Whether the app is a custom app.
- **Permissions**: Indicates whether a third-party or custom app that's registered in Azure Active Directory (Azure AD) has permissions that need consent. You'll see one of the following values:
  - **View details**: The app has permissions that require consent before the app can access data.
  - **- -**: The app doesn't have permissions that need consent.
- **Categories**: Categories that apply to the app.
- **Version**: App version.
- **Admin can install in meetings**: Indicates whether an app can be installed by admins in Team meetings. [Learn more](teams-app-setup-policies.md#install-apps)

To see the information that you want in the table, select **Edit Column** in the upper-right corner to add or remove columns to the table.
--->

## <a name="publish-a-custom-app-to-your-organizations-app-store"></a>Veröffentlichen einer benutzerdefinierten App im App Store Ihrer Organisation

Verwenden Sie die Seite "Apps verwalten", um Apps zu veröffentlichen, die speziell für Ihre Organisation erstellt wurden. Nachdem Sie eine benutzerdefinierte App veröffentlicht haben, steht sie Benutzern im App Store Ihrer Organisation zur Verfügung. Es gibt zwei Möglichkeiten zum Veröffentlichen einer benutzerdefinierten App im App Store Ihrer Organisation. Die Art und Weise, wie Sie die App verwenden, hängt davon ab, wie Sie die App erhalten.

* [Genehmigen einer benutzerdefinierten App](#approve-a-custom-app): Verwenden Sie diese Methode, wenn der Entwickler die App mithilfe der Teams App-Übermittlungs-API direkt an die Seite "Apps verwalten" übermittelt. Sie können die App dann direkt über die App-Detailseite überprüfen und veröffentlichen (oder ablehnen).
* [Hochladen eines App-Pakets](#upload-an-app-package): Verwenden Sie diese Methode, wenn der Entwickler Ihnen das App-Paket im .zip Format sendet. Sie veröffentlichen die App, indem Sie das App-Paket hochladen.

### <a name="approve-a-custom-app"></a>Genehmigen einer benutzerdefinierten App

Das Widget "**Ausstehende Genehmigungen**" auf der Seite "Apps verwalten" benachrichtigt Sie, wenn ein Entwickler eine App mithilfe der Teams App-Übermittlungs-API übermittelt. Eine neu übermittelte App wird mit dem **Veröffentlichungsstatus** **"Gesendet** " und dem **Status** " **Blockiert**" aufgelistet. Wechseln Sie zur Seite mit den App-Details, um weitere Informationen zur App anzuzeigen, und legen Sie dann zum Veröffentlichen den **Veröffentlichungsstatus** auf **"Veröffentlichen**" fest.

Sie werden auch benachrichtigt, wenn ein Entwickler ein Update an eine benutzerdefinierte App übermittelt. Anschließend können Sie das Update auf der App-Detailseite überprüfen und veröffentlichen (oder ablehnen). Alle App-Berechtigungsrichtlinien und App-Setuprichtlinien bleiben für die aktualisierte App erzwungen.

Weitere Informationen finden Sie unter [Veröffentlichen einer benutzerdefinierten App, die über die Teams App-Übermittlungs-API übermittelt wurde](submit-approve-custom-apps.md).

### <a name="upload-an-app-package"></a>Hochladen eines App-Pakets

Der Entwickler erstellt ein Teams App-Paket [mithilfe von Teams App Studio](/microsoftteams/platform/get-started/get-started-app-studio) und sendet es dann im .zip-Format an Sie. Wenn Sie über das App-Paket verfügen, können Sie es in den App Store Ihrer Organisation hochladen.

Um eine neue benutzerdefinierte App hochzuladen, wählen Sie **Hochladen** aus, um das App-Paket hochzuladen. Die App wird nach dem Hochladen nicht hervorgehoben, sodass Sie die Liste der Apps auf der Seite "Apps verwalten" durchsuchen müssen, um sie zu finden.

Um eine App nach dem Hochladen zu aktualisieren, wählen Sie in der Liste der Apps auf der Seite "Apps verwalten" den Namen der App und dann **"Aktualisieren**" aus. Dadurch wird die vorhandene App ersetzt, und alle App-Berechtigungsrichtlinien und App-Setuprichtlinien bleiben für die aktualisierte App erzwungen.

Weitere Informationen finden Sie unter [Veröffentlichen einer benutzerdefinierten App durch Hochladen eines App-Pakets](upload-custom-apps.md).

## <a name="allow-and-block-apps"></a>Apps zulassen und blockieren

Auf der Seite "Apps verwalten" können Sie einzelne Apps auf Organisationsebene zulassen oder blockieren. Es zeigt jede verfügbare App und ihren aktuellen App-Status auf Organisationsebene an. (Das Blockieren und Zulassen von Apps auf Organisationsebene wurde vom **organisationsweiten App-Einstellungsbereich** zu hier verschoben.)

Um eine App zuzulassen oder zu blockieren, wählen Sie sie aus, und wählen Sie dann **"Zulassen"** oder " **Blockieren"** aus. Wenn Sie eine App blockieren, werden alle Interaktionen mit dieser App deaktiviert, und die App wird nicht in Teams für Benutzer in Ihrer Organisation angezeigt.

Wenn Sie eine App auf der Seite "Apps verwalten" blockieren oder zulassen, ist diese App für alle Benutzer in Ihrer Organisation blockiert oder zulässig.  Wenn Sie eine App in einer Teams App-Berechtigungsrichtlinie blockieren oder zulassen, wird sie für Benutzer blockiert oder zugelassen, denen diese Richtlinie zugewiesen ist. Damit ein Benutzer eine beliebige App installieren und mit dieser interagieren kann, müssen Sie die App auf Organisationsebene auf der Seite "Apps verwalten" und in der App-Berechtigungsrichtlinie zulassen, die dem Benutzer zugewiesen ist.

 > [!NOTE]
 > Um eine App zu deinstallieren, klicken Sie mit der rechten Maustaste auf die App, und klicken Sie dann auf **"Deinstallieren** ", oder verwenden Sie das Menü **"Weitere Apps** " auf der linken Seite.

## <a name="apps-blocked-by-publishers"></a>Von Herausgebern blockierte Apps

Wenn ein ISV eine App im globalen App Store veröffentlicht, benötigen sie möglicherweise Administratoren, um die App-Erfahrung zu konfigurieren oder anzupassen. Der Administrator kann es Endbenutzern zur Verfügung stellen, wenn die App vollständig eingerichtet ist.

Contoso Electronics ist beispielsweise ein ISV, der eine Helpdesk-App für Microsoft Teams erstellt hat. Contoso Electronics möchte, dass seine Kunden bestimmte Eigenschaften der App so einrichten, dass die App wie erwartet funktioniert, wenn Benutzer mit der App interagieren. Bevor ein Administrator die Anwendung zulassen oder blockieren kann, wird sie im Teams Admin Center als **vom Herausgeber blockiert** angezeigt und standardmäßig für Endbenutzer ausgeblendet. Nachdem Sie den Anweisungen des Herausgebers zum Einrichten der App gefolgt sind, können Sie sie Benutzern zur Verfügung stellen, indem Sie zu Status **"Zulässig**" wechseln oder Benutzer daran hindern, die App zu verwenden, indem Sie den Status in **"Blockiert**" ändern.

![Screenshot des Status "Vom Herausgeber blockiert" im Teams Admin Center.](media/blocked-by-publisher.png)

## <a name="add-an-app-to-a-team"></a>Hinzufügen einer App zu einem Team

Sie verwenden die Schaltfläche " **Zu Team hinzufügen** ", um eine App für ein Team zu installieren. Beachten Sie, dass dies nur für Apps gilt, die in einem Teambereich installiert werden können. Die Schaltfläche " **Zu Team hinzufügen** " ist nicht für Apps verfügbar, die nur im persönlichen Bereich installiert werden können.

![Screenshot der Schaltfläche "Zum Team hinzufügen".](media/manage-apps-add-app-team.png)

1. Suchen Sie nach der gewünschten App, und wählen Sie die App aus, indem Sie links neben dem App-Namen klicken.
1. Wählen Sie **"Zum Team hinzufügen" aus**.
1. Suchen **Sie im Bereich "Zu Team hinzufügen** " nach dem Team, dem Sie die App hinzufügen möchten, wählen Sie das Team aus, und wählen Sie dann **"Übernehmen"** aus.

## <a name="customize-an-app"></a>Anpassen einer App

Sie können jetzt eine App so anpassen, dass sie ein bestimmtes Aussehen und Verhalten entsprechend den Anforderungen Ihrer Organisation enthält. Siehe [Anpassen von Apps in Teams](customize-apps.md).

## <a name="purchase-services-for-third-party-apps"></a>Erwerben von Diensten für Drittanbieter-Apps

Sie können direkt auf der Seite "Apps verwalten" nach Lizenzen für Dienste suchen und erwerben, die von Drittanbieter-Apps für Benutzer in Ihrer Organisation angeboten werden. Die Spalte **"Lizenzen** " in der Tabelle gibt an, ob eine App ein kostenpflichtiges SaaS-Abonnement anbietet. Wählen Sie **"Jetzt kaufen** " aus, um Pläne und Preisinformationen anzuzeigen und Lizenzen für Ihre Benutzer zu kaufen. Weitere Informationen finden Sie [unter "Dienste für Teams Drittanbieter-Apps kaufen" im Microsoft Teams Admin Center](purchase-third-party-apps.md).

## <a name="grant-admin-consent-to-apps"></a>Erteilen der Administratorzustimmung für Apps

Sie können Apps, die Berechtigungen im Namen aller Benutzer in Ihrer Organisation anfordern, überprüfen und deren Zustimmung erteilen. Sie tun dies, damit Benutzer die von der App angeforderten Berechtigungen beim Starten der App nicht überprüfen und akzeptieren müssen. Die Spalte **"Berechtigungen"** gibt an, ob eine App über Berechtigungen verfügt, die zustimmungsbedürftig sind. Für jede in Azure AD registrierte App mit Berechtigungen, die zustimmungsbedürftig sind, wird ein Link "**Details anzeigen**" angezeigt. Weitere Informationen finden [Sie unter Anzeigen von App-Berechtigungen und Erteilen der Administratorzustimmung im Microsoft Teams Admin Center](app-permissions-admin-center.md).

## <a name="view-resource-specific-consent-permissions"></a>Ressourcenspezifische Zustimmungsberechtigungen anzeigen

Mit ressourcenspezifischen Zustimmungsberechtigungen (Resource Specific Consent, RSC) können Teambesitzer einer App die Zustimmung erteilen, auf die Daten eines Teams zuzugreifen und diese zu ändern. RSC-Berechtigungen sind präzise, Teams-spezifische Berechtigungen, die definieren, was eine App in einem bestimmten Team tun kann. Sie können RSC-Berechtigungen auf der Registerkarte **"Berechtigungen** " der Seite "App-Details" für eine App anzeigen. Weitere Informationen finden [Sie unter Anzeigen von App-Berechtigungen und Erteilen der Administratorzustimmung im Microsoft Teams Admin Center](app-permissions-admin-center.md).

## <a name="manage-org-wide-app-settings"></a>Organisationsweite App-Einstellungen verwalten

Verwenden Sie organisationsweite App-Einstellungen, um zu steuern, ob Benutzer mit einer [F-Lizenz](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt) die maßgeschneiderte Frontline-App-Erfahrung erhalten, ob Benutzer Apps von Drittanbietern installieren können und ob Benutzer benutzerdefinierte Apps in Ihrer Organisation hochladen oder mit diesen interagieren können. Organisationsweite App-Einstellungen regeln das Verhalten für alle Benutzer und setzen alle anderen App-Berechtigungsrichtlinien, die den Benutzern zugewiesen wurden, außer Kraft. Sie können sie verwenden, um bösartige oder problematische Apps zu kontrollieren.

> [!NOTE]
> Informationen zum Verwenden organisationsweiter App-Einstellungen in Microsoft 365 Government – Government Community Cloud High GCCH- und Department of Defense (DoD)-Bereitstellungen von Teams finden [Sie unter Verwalten von App-Berechtigungsrichtlinien in Teams](teams-app-permission-policies.md).

1. Wählen Sie auf der Seite "Apps verwalten" die Option " **Organisationsweite App-Einstellungen"** aus. Sie können dann die gewünschten Einstellungen im Bereich konfigurieren.

    :::image type="content" source="media/manage-apps-org-wide-app-settings.png" alt-text="Screenshot des Bereichs &quot;Organisationsweite App-Einstellungen&quot; auf der Seite &quot;Apps verwalten&quot;":::

1. Deaktivieren oder aktivieren Sie unter **"Maßgeschneiderte Apps****" die Option "Maßgeschneiderte Apps anzeigen**". Wenn diese Einstellung aktiviert ist, erhalten Benutzer mit einer [F-Lizenz](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt) die maßgeschneiderte Frontline-App-Erfahrung. Diese Erfahrung heftt die relevantesten Apps in Teams für Mitarbeiter in Service und Produktion an. Weitere Informationen finden Sie unter ["Anpassen Teams Apps für Mitarbeiter in Service und Produktion](pin-teams-apps-based-on-license.md)".

    Dieses Feature ist für F-Lizenzen verfügbar. Weitere Lizenztypen werden in Zukunft unterstützt.
1. Aktivieren oder deaktivieren Sie unter **Drittanbieter-Apps** diese Einstellungen, um den Zugriff auf Drittanbieter-Apps zu steuern:

    - **Drittanbieter-Apps zulassen**: Steuert, ob Benutzer Drittanbieter-Apps verwenden können. Wenn Sie diese Einstellung deaktivieren, können Ihre Benutzer keine Drittanbieter-Apps installieren oder verwenden, und der **App-Status** dieser Apps wird in der Tabelle organisationsweit als blockiert angezeigt.

        > [!NOTE]
        > Wenn **"Apps von Drittanbietern zulassen** " deaktiviert ist, sind [ausgehende Webhooks](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) weiterhin für alle Benutzer aktiviert. Sie können sie jedoch auf Benutzerebene steuern, indem Sie die ausgehende Webhook-App über [App-Berechtigungsrichtlinien](teams-app-permission-policies.md) zulassen oder blockieren. Wenn Sie über vorhandene [App-Berechtigungsrichtlinien](teams-app-permission-policies.md) für **Microsoft-Apps** verfügen, die **die Einstellung "Bestimmte Apps zulassen" verwenden und alle anderen blockieren** , und Ausgehende Webhooks für Benutzer aktivieren möchten, fügen Sie die Ausgehende Webhook-App zur Liste hinzu.

        > [!NOTE]
        > Benutzer von Microsoft Teams können Apps hinzufügen, wenn sie Besprechungen oder Chats mit Personen aus anderen Organisationen hosten. Sie können auch Apps verwenden, die von Personen in anderen Organisationen freigegeben werden, wenn sie an Besprechungen oder Chats teilnehmen, die von diesen Organisationen gehostet werden. Es werden die Datenrichtlinien der Organisation des Hostingbenutzers sowie die Datenfreigabemethoden von Drittanbieter-Apps, die von der Organisation dieses Benutzers freigegen werden, angewendet.

    - **Alle neuen Drittanbieter-Apps, die im Store veröffentlicht werden, standardmäßig zulassen**: Steuert, ob neue Drittanbieter-Apps, die im Teams-App-Store veröffentlicht werden, automatisch in Teams verfügbar gemacht werden. Sie können diese Option nur aktivieren, wenn Sie Drittanbieter-Apps zulassen.

1. Deaktivieren oder aktivieren Sie unter **"Benutzerdefinierte Apps**" **die Option "Interaktion mit benutzerdefinierten Apps zulassen**". Diese Einstellung steuert, ob Benutzer mit benutzerdefinierten Apps interagieren können. Weitere Informationen finden Sie unter [Verwalten von benutzerdefinierten App-Richtlinien und Einstellungen in Teams](teams-custom-app-policies-and-settings.md).
1. Wählen Sie "Für organisationsweite App-Einstellungen **speichern"** aus, um wirksam zu werden.
