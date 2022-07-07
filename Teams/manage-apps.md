---
title: Verwalten Ihrer Apps im Microsoft Teams Admin Center
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
ms.subservice: teams-apps
ms.custom: intro-get-started
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: vaibhava
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.manageapps.overview
description: Erfahren Sie, wie Sie Teams-Apps verwalten. Erfahren Sie, wie Sie Apps zulassen oder blockieren, den Status und die App-Eigenschaften auf Organisationsebene überprüfen, benutzerdefinierte Apps hochladen und App-Einstellungen verwalten.
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: 92f7c6d69fbc9f680c204f0210aaa80742dd6384
ms.sourcegitcommit: 90f03a841f8ca33092dce65c543357c7c2f7b82a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2022
ms.locfileid: "66647747"
---
# <a name="manage-teams-apps-in-the-microsoft-teams-admin-center"></a>Verwalten von Teams-Apps im Microsoft Teams Admin Center

Sie verwalten Apps für Ihre Organisation auf der Seite **"Teams-Apps** " im Teams Admin Center-Portal. Verwenden Sie die Seite "Apps verwalten", um alle Teams-Apps im App-Katalog Ihrer Organisation anzuzeigen und zu verwalten.

:::image type="content" source="media/manage-apps.png" alt-text="Screenshot der Seite &quot;Apps verwalten&quot;." lightbox="media/manage-apps.png":::

Um das Teams Admin Center verwenden zu können, müssen Sie über eine Globale Admin- oder Teams-Administratorrolle verfügen. Ausführliche Informationen finden Sie in den folgenden Hilfeartikeln:

* [Teams-Administratorrollen](./using-admin-roles.md).
* [Microsoft 365-Administratorrollen](/microsoft-365/admin/add-users/about-admin-roles)

Zum Verwalten von Apps verwenden Sie Richtlinien, um Berechtigungen für Benutzer, die Installation von Apps und das Hochladen von benutzerdefinierten Apps zu steuern, die in Ihrer Organisation erstellt wurden. Informationen zu Richtlinien finden Sie [unter Übersicht über App-Richtlinien](app-policies.md).

> [!NOTE]
> Die Seite "Apps verwalten" ist in Microsoft 365 Government Community Cloud High (GCCH)- oder Department of Defense (DoD)-Bereitstellungen von Teams nicht verfügbar.

Während der Erstellung einer App erstellen die Entwickler eine App-ID und fügen sie der Manifestdatei hinzu. Sie können diese externe App-ID auf der Seite "Apps verwalten" anzeigen, nachdem Sie die Spalte `External app ID` in den Spalteneinstellungen aktiviert haben. Sie können sie auch auf der App-Detailseite einer benutzerdefinierten App anzeigen. Die ID gilt nur für benutzerdefinierte Apps.

## <a name="app-management-use-cases-and-the-available-interfaces"></a>Anwendungsfälle für die App-Verwaltung und die verfügbaren Schnittstellen

Die Optionen zum Ausführen der meisten Anwendungsfälle für die App-Verwaltung sind im Teams Admin Center verfügbar. Darüber hinaus stehen einige Optionen in anderen Portalen zur Verfügung.

| Anwendungsfälle für die App-Verwaltung | Verknüpfung mit der Schnittstelle | Dokumentation |
|:----|:----|:----|
| **Im Teams Admin Center** | | |
| Steuern Sie, welche Apps benutzern in Ihrer Organisation zur Verfügung stehen, indem Sie Apps zulassen und blockieren. Sie können auch benutzerdefinierte Apps hochladen und genehmigen. Nach dem Verwalten von Apps auf dieser Seite können Sie App-Berechtigungs- und App-Setuprichtlinien verwenden, um zu konfigurieren, welche Apps für bestimmte Benutzer im App Store Ihrer Organisation verfügbar sind. | [Verwalten von Apps im Teams Admin Center](https://admin.teams.microsoft.com/policies/manage-apps) | Aktueller Artikel |
| App-Berechtigungsrichtlinien steuern, welche Apps Sie Teams-Benutzern in Ihrer Organisation zur Verfügung stellen möchten. Sie können die globale (organisationsweite) Standardrichtlinie verwenden und anpassen oder eine oder mehrere Richtlinien erstellen, um die Anforderungen Ihrer Organisation zu erfüllen. | [Berechtigungsrichtlinien](https://admin.teams.microsoft.com/policies/app-permission) | [Verwalten von App-Berechtigungsrichtlinien](teams-app-permission-policies.md) |
| App-Setuprichtlinien steuern, wie Apps einem Benutzer mit der Teams-App zur Verfügung gestellt werden. Verwenden Sie die globale Richtlinie (organisationsweite Standardrichtlinie), passen Sie sie an, oder erstellen Sie benutzerdefinierte Richtlinien, und weisen Sie sie einer Gruppe von Benutzern zu. | [Setuprichtlinien](https://admin.teams.microsoft.com/policies/app-setup) | [Verwalten von App-Setuprichtlinien](teams-app-setup-policies.md) |
| Sie können benutzerdefinierte Apps als App-Pakete entwickeln und hochladen und sie im App Store Ihrer Organisation verfügbar machen. | Organisationsweite App-Einstellungen in ["Apps verwalten"](https://admin.teams.microsoft.com/policies/manage-apps) | [Verwalten von benutzerdefinierten App-Richtlinien](teams-custom-app-policies-and-settings.md) |
| Sie können den Teams-App-Store mit dem Logo, dem benutzerdefinierten Hintergrund oder der Farbe Ihrer Organisation anpassen. | [Store anpassen](https://admin.teams.microsoft.com/policies/customize-appstore) | [Anpassen des App Store Ihrer Organisation](customize-your-app-store.md) |
| Der Teams-App-Nutzungsbericht enthält Informationen dazu, welche Apps verwendet werden, aktive Benutzer und andere Informationen zur App-Nutzung. | [Verwendungsberichte](https://admin.teams.microsoft.com/analytics/reports) | [Teams-App-Nutzungsbericht](teams-analytics-and-reports/app-usage-report.md) |
| Ihre Benutzer können Apps hinzufügen, wenn sie Besprechungen oder Chats mit Gästen hosten. Sie können auch Apps verwenden, die von Gästen geteilt werden, wenn sie an Besprechungen oder Chats teilnehmen, die extern gehostet werden. Die Datenrichtlinien der Organisation des hostenden Benutzers und die Datenfreigabepraktiken von Drittanbieter-Apps, die von der Organisation dieses Benutzers gemeinsam genutzt werden, werden angewendet. | [Externer Zugriff](https://admin.teams.microsoft.com/company-wide-settings/external-communications) | [App-Verhalten je nach Benutzertypen](non-standard-users.md) |
| Mit Gastzugriff können Sie Personen außerhalb Ihrer Organisation Zugriff auf Anwendungen und andere Teams-Funktionen gewähren und gleichzeitig die Kontrolle über Ihre Unternehmensdaten behalten. | [Gastzugriff](https://admin.teams.microsoft.com/company-wide-settings/guest-configuration) | [Gastzugriff in Teams](guest-access.md) |
| Updaterichtlinien werden verwendet, um Teams- und Office Preview-Benutzer zu verwalten, die Vorabversions- oder Vorschaufeatures in der Teams-App sehen.  | [Teams-Updaterichtlinien](https://admin.teams.microsoft.com/policies/updatemanagement) | [Öffentliche Teams-Vorschau](public-preview-doc-updates.md) |
| **Außerhalb des Teams Admin Centers** | | |
| Verwalten von Lizenzen und Abonnements von Drittanbieter-Apps in Microsoft 365 Admin Center | [Microsoft 365 Admin Center](https://admin.microsoft.com/#/licenses) | [Verwalten von App-Abonnements von Drittanbietern](/microsoft-365/commerce/manage-saas-apps) |
| Überwachen von Teams-App-Ereignissen auf Microsoft Purview-Complianceportal. | [Audit](https://compliance.microsoft.com/auditlogsearch?viewid=Async%20Search) | [Microsoft Teams-Aktivitäten](audit-app-management-activities.md) |
| Anwendungen können Berechtigungen für Ihre Organisation und deren Daten mit drei Methoden gewährt werden: ein Administrator stimmt der Anwendung für alle Benutzer zu, ein Benutzer erteilt der Anwendung die Zustimmung oder ein Administrator, der eine Anwendung integriert und den Self-Service-Zugriff aktiviert oder Benutzer direkt der Anwendung zuweist. Überprüfen Sie die Graph-Berechtigungen für Apps. Überprüfen Sie die Berechtigungen, die Benutzer bereitgestellt haben oder die die Administratoren delegiert haben. | [Azure AD-Portal](https://aad.portal.azure.com/) | [Überprüfen von Berechtigungen, die Anwendungen erteilt wurden](/azure/active-directory/manage-apps/manage-application-permissions) |

<!---
| xxx | [Manage users](https://admin.teams.microsoft.com/users) | [Add users and assign licenses](/microsoft-365/admin/add-users/add-users?view=o365-worldwide) |  
--->

## <a name="publish-a-custom-app-to-your-organizations-app-store"></a>Veröffentlichen einer benutzerdefinierten App im App Store Ihrer Organisation

Verwenden Sie die Seite "Apps verwalten", um Apps zu veröffentlichen, die speziell für Ihre Organisation erstellt wurden. Nachdem Sie eine benutzerdefinierte App veröffentlicht haben, steht sie Benutzern im App Store Ihrer Organisation zur Verfügung. Es gibt zwei Möglichkeiten zum Veröffentlichen einer benutzerdefinierten App im App Store Ihrer Organisation. Die Art und Weise, wie Sie die App verwenden, hängt davon ab, wie Sie die App erhalten.

* [Genehmigen einer benutzerdefinierten App](#approve-a-custom-app): Verwenden Sie diese Methode, wenn der Entwickler die App mithilfe der Teams-App-Übermittlungs-API direkt an die Seite "Apps verwalten" übermittelt. Sie können die App dann direkt über die App-Detailseite überprüfen und veröffentlichen (oder ablehnen).
* [Hochladen eines App-Pakets](#upload-an-app-package): Verwenden Sie diese Methode, wenn der Entwickler Ihnen das App-Paket im .zip Format sendet. Sie veröffentlichen die App, indem Sie das App-Paket hochladen.

### <a name="approve-a-custom-app"></a>Genehmigen einer benutzerdefinierten App

Das Widget " **Ausstehende Genehmigungen** " auf der Seite "Apps verwalten" benachrichtigt Sie, wenn ein Entwickler eine App mithilfe der Teams-App-Übermittlungs-API übermittelt. Eine neu übermittelte App wird mit dem **Veröffentlichungsstatus** **"Gesendet** " und dem **Status** " **Blockiert**" aufgelistet. Wechseln Sie zur Seite mit den App-Details, um weitere Informationen zur App anzuzeigen, und legen Sie dann zum Veröffentlichen den **Veröffentlichungsstatus** auf **"Veröffentlichen**" fest.

Sie werden auch benachrichtigt, wenn ein Entwickler ein Update an eine benutzerdefinierte App übermittelt. Anschließend können Sie das Update auf der App-Detailseite überprüfen und veröffentlichen (oder ablehnen). Alle App-Berechtigungsrichtlinien und App-Setuprichtlinien bleiben für die aktualisierte App erzwungen.

Weitere Informationen finden Sie unter [Veröffentlichen einer benutzerdefinierten App, die über die Teams-App-Übermittlungs-API übermittelt wurde](submit-approve-custom-apps.md).

### <a name="upload-an-app-package"></a>Hochladen eines App-Pakets

Der Entwickler erstellt ein Teams-App-Paket mithilfe von [Teams App Studio](/microsoftteams/platform/get-started/get-started-app-studio) und sendet es dann im .zip-Format an Sie. Wenn Sie über das App-Paket verfügen, können Sie es in den App Store Ihrer Organisation hochladen.

Um eine neue benutzerdefinierte App hochzuladen, wählen Sie **"Hochladen** " aus, um das App-Paket hochzuladen. Die App wird nach dem Hochladen nicht hervorgehoben, sodass Sie die Liste der Apps auf der Seite "Apps verwalten" durchsuchen müssen, um sie zu finden.

Um eine App nach dem Hochladen zu aktualisieren, wählen Sie in der Liste der Apps auf der Seite "Apps verwalten" den Namen der App und dann **"Aktualisieren**" aus. Wenn Sie ein Update ausführen, wird die vorhandene App ersetzt, und alle App-Berechtigungsrichtlinien und App-Setuprichtlinien bleiben für die aktualisierte App erzwungen.

Weitere Informationen finden Sie unter [Veröffentlichen einer benutzerdefinierten App durch Hochladen eines App-Pakets](upload-custom-apps.md).

## <a name="allow-and-block-apps"></a>Apps zulassen und blockieren

Auf der Seite "Apps verwalten" können Sie einzelne Apps auf Organisationsebene zulassen oder blockieren. Es zeigt jede verfügbare App und ihren aktuellen App-Status auf Organisationsebene an.

So lassen Sie eine App zu oder blockieren sie:

1. Wechseln Sie zum Teams Admin Center > Teams-Apps > Apps verwalten.
1. Wählen Sie eine App aus der App-Liste aus.
1. Wählen Sie **"Zulassen"** oder **"Blockieren"** aus.

Wenn Sie eine App auf der Seite "Apps verwalten" blockieren oder zulassen, ist diese App für alle Benutzer in Ihrer Organisation blockiert oder zulässig.  Wenn Sie eine App in einer Teams-App-Berechtigungsrichtlinie blockieren oder zulassen, wird sie für Benutzer blockiert oder zugelassen, denen diese Richtlinie zugewiesen ist. Damit ein Benutzer eine beliebige App installieren und mit dieser interagieren kann, müssen Sie die App auf Organisationsebene auf der Seite "Apps verwalten" und in der App-Berechtigungsrichtlinie zulassen, die dem Benutzer zugewiesen ist.

 > [!NOTE]
 > Um eine App zu deinstallieren, klicken Sie mit der rechten Maustaste auf die App, und klicken Sie dann auf **"Deinstallieren** ", oder verwenden Sie das Menü **"Weitere Apps** " auf der linken Seite.

## <a name="manage-user-requests-to-unblock-apps"></a>Verwalten von Benutzeranforderungen zum Aufheben der Blockierung von Apps

Sie können Anforderungen anzeigen, um eine blockierte App zur Verwendung zur Verfügung zu stellen. Die Anforderung wird an den IT-Administrator gesendet, der Benutzeranforderungen im Teams Admin Center anzeigen und verwalten kann.

  :::image type="content" source="media/user-request.png" alt-text="Stellen einer Anforderung für die Genehmigung blockierter Apps":::

### <a name="view-a-request"></a>Anzeigen einer Anforderung

 1. Melden Sie sich beim Teams Admin Center an, und wählen Sie ["Apps verwalten"](https://admin.teams.microsoft.com/policies/manage-apps) aus.

    :::image type="content" source="media/requested-apps1.png" alt-text="Anforderung durch Benutzer" lightbox="media/requested-apps.png" border="true":::

 1. Um die Anzahl der Anforderungen für jede App anzuzeigen und zu überprüfen, sortieren Sie die Anforderungen in der Spalte **"Anforderungen nach Benutzer** ".
 1. Wählen Sie den Namen der App aus, die Sie entsperren möchten, und es wird die Detailseite der App geöffnet.
 1. Wählen Sie **"Anforderungen verwalten"** aus, und führen Sie die im Popupdialogfeld angezeigten Schritte aus. Die Schritte zum Genehmigen einer App variieren je nach der Methode, mit der sie blockiert wird.

    * Wenn die App mithilfe von Berechtigungsrichtlinien blockiert wird, lassen Sie die App zu, indem Sie [Berechtigungsrichtlinien](teams-app-permission-policies.md) ändern.
    * Wenn die App für alle Benutzer blockiert ist, [lassen Sie die App zu](#allow-and-block-apps).
    * Wenn alle Apps für alle Benutzer blockiert sind, ändern Sie [organisationsweite Einstellungen](#manage-org-wide-app-settings).

 Wenn ein Administrator eine App zulässt, wird der Endbenutzer nicht darüber informiert, dass seine Anforderung erfüllt wird. Der Benutzer muss die App im Store besuchen, um zu überprüfen, ob die App nicht blockiert ist oder nicht.

### <a name="dismiss-a-user-request"></a>Schließen einer Benutzeranforderung

 1. Wählen Sie den Namen der App aus, für die Sie die Benutzeranforderungen schließen möchten.
 1. Wählen Sie **"Anforderungen verwalten"** und dann **im Dialogfeld "Alle Anforderungen schließen** " aus.
 1. Wenn eine Anforderung geschlossen wird, werden die Benutzeranforderungen auf Null zurückgesetzt.

  :::image type="content" source="media/reject.png" alt-text="Die Ablehnung von Apps wurde blockiert."border="true":::

Wenn ein Administrator eine Anforderung schließt, wird der Endbenutzer nicht darüber informiert, dass seine Anforderung erfüllt wird. Der Benutzer muss die App im Store besuchen, um zu überprüfen, ob die App nicht blockiert ist oder nicht.

## <a name="apps-blocked-by-publishers"></a>Von Herausgebern blockierte Apps

Wenn ein ISV eine App im globalen App Store veröffentlicht, benötigen sie möglicherweise Administratoren, um die App-Erfahrung zu konfigurieren oder anzupassen. Der Administrator kann es Endbenutzern zur Verfügung stellen, wenn die App eingerichtet ist.

Contoso Electronics ist beispielsweise ein ISV, der eine Helpdesk-App für Microsoft Teams erstellt hat. Contoso Electronics möchte, dass seine Kunden bestimmte Eigenschaften der App so einrichten, dass die App wie erwartet funktioniert, wenn Benutzer mit der App interagieren. Bevor ein Administrator die Anwendung zulassen oder blockieren kann, wird sie im Teams Admin Center als **vom Herausgeber blockiert** angezeigt und standardmäßig für Endbenutzer ausgeblendet. Nachdem Sie den Anweisungen des Herausgebers zum Einrichten der App gefolgt sind, können Sie sie Benutzern zur Verfügung stellen, indem Sie den Status auf **"Zulässig**" ändern oder benutzer die Verwendung der App blockieren, indem Sie den Status in **"Blockiert**" ändern.

<!--- 
![Screenshot of blocked by publisher status in teams admin center.](media/blocked-by-publisher.png)
--->

## <a name="add-an-app-to-a-team"></a>Hinzufügen einer App zu einem Team

Sie verwenden die Schaltfläche " **Zu Team hinzufügen** ", um eine App für ein Team zu installieren. Diese Option ist nur für die Apps verfügbar, die in einem Teambereich installiert werden können. Die Option ist nicht für Apps verfügbar, die nur im persönlichen Bereich installiert werden können.

1. Suchen Sie nach einer App anhand ihres Namens, und wählen Sie die App aus. Öffnen Sie die Seite mit den App-Details nicht.
1. Wählen Sie **"Zum Team hinzufügen" aus**.

   :::image type="content" source="media/manage-apps-add-app-team-trimmed.png" alt-text="Screenshot der Option &quot;Zu Team hinzufügen&quot; für die App, die dem Teambereich hinzugefügt werden kann.":::

1. Suchen **Sie im Bereich "Zu Team hinzufügen** " nach dem Team, dem Sie die App hinzufügen möchten, wählen Sie das Team aus, und wählen Sie dann **"Übernehmen"** aus.

## <a name="customize-an-app"></a>Anpassen einer App

Sie können jetzt eine App so anpassen, dass sie ein bestimmtes Aussehen und Verhalten entsprechend den Anforderungen Ihrer Organisation enthält. Siehe [Anpassen von Apps in Teams](customize-apps.md).

## <a name="purchase-services-for-third-party-apps"></a>Erwerben von Diensten für Drittanbieter-Apps

Sie können direkt auf der Seite "Apps verwalten" nach Lizenzen für Dienste suchen und erwerben, die von Drittanbieter-Apps für Benutzer in Ihrer Organisation angeboten werden. Die Spalte **"Lizenzen** " in der Tabelle gibt an, ob eine App ein kostenpflichtiges SaaS-Abonnement anbietet. Wählen Sie **"Jetzt kaufen** " aus, um Pläne und Preisinformationen anzuzeigen und Lizenzen für Ihre Benutzer zu kaufen. Weitere Informationen finden Sie [unter "Dienste für Teams-Drittanbieter-Apps kaufen" im Microsoft Teams Admin Center](purchase-third-party-apps.md).

## <a name="grant-permissions-and-consent-to-apps-to-use-end-user-information"></a>Erteilen von Berechtigungen und Zustimmung zu Apps zur Verwendung von Endbenutzerinformationen

Sie können Apps, die Berechtigungen im Namen aller Benutzer in Ihrer Organisation anfordern, überprüfen und deren Zustimmung erteilen. Sie tun dies, damit Benutzer die von der App angeforderten Berechtigungen beim Starten der App nicht überprüfen und akzeptieren müssen. Die Spalte **"Berechtigungen"** gibt an, ob eine App über Berechtigungen verfügt, die zustimmungsbedürftig sind. Für jede in Azure AD registrierte App mit Berechtigungen, die zustimmungsbedürftig sind, wird ein Link " **Details anzeigen** " angezeigt. Weitere Informationen finden [Sie unter Anzeigen von App-Berechtigungen und Erteilen der Administratorzustimmung im Microsoft Teams Admin Center](app-permissions-admin-center.md).

## <a name="view-resource-specific-consent-permissions"></a>Ressourcenspezifische Zustimmungsberechtigungen anzeigen

Mit ressourcenspezifischen Zustimmungsberechtigungen (Resource Specific Consent, RSC) können Teambesitzer einer App die Zustimmung erteilen, auf die Daten eines Teams zuzugreifen und diese zu ändern. RSC-Berechtigungen sind präzise, teamsspezifische Berechtigungen, die definieren, was eine App in einem bestimmten Team tun kann. Sie können RSC-Berechtigungen auf der Registerkarte **"Berechtigungen** " der Seite "App-Details" für eine App anzeigen. Weitere Informationen finden [Sie unter Anzeigen von App-Berechtigungen und Erteilen der Administratorzustimmung im Microsoft Teams Admin Center](app-permissions-admin-center.md).

## <a name="manage-org-wide-app-settings"></a>Organisationsweite App-Einstellungen verwalten

Verwenden Sie organisationsweite App-Einstellungen, um zu steuern, ob Benutzer mit einer [F-Lizenz](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt) die maßgeschneiderte Frontline-App-Erfahrung erhalten, ob Benutzer Apps von Drittanbietern installieren können und ob Benutzer benutzerdefinierte Apps in Ihrer Organisation hochladen oder mit diesen interagieren können. Organisationsweite App-Einstellungen regeln das Verhalten für alle Benutzer und setzen alle anderen App-Berechtigungsrichtlinien, die den Benutzern zugewiesen wurden, außer Kraft. Sie können sie verwenden, um bösartige oder problematische Apps zu kontrollieren.

> [!NOTE]
> Informationen zum Verwenden organisationsweiter App-Einstellungen in Microsoft 365 Government - Government Community Cloud High GCCH und DoD-Bereitstellungen von Teams finden Sie unter [Verwalten von App-Berechtigungsrichtlinien in Teams](teams-app-permission-policies.md).

1. Wählen Sie auf der Seite "Apps verwalten" die Option " **Organisationsweite App-Einstellungen"** aus. Sie können dann die gewünschten Einstellungen im Bereich konfigurieren.

    :::image type="content" source="media/manage-apps-org-wide-app-settings.png" alt-text="Screenshot des Bereichs &quot;Organisationsweite App-Einstellungen&quot; auf der Seite &quot;Apps verwalten&quot;":::

1. Deaktivieren oder aktivieren Sie unter **"Maßgeschneiderte Apps****" die Option "Maßgeschneiderte Apps anzeigen**". Wenn diese Einstellung aktiviert ist, erhalten Benutzer mit einer [F-Lizenz](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt) die maßgeschneiderte Frontline-App-Erfahrung. Diese Erfahrung heftt die relevantesten Apps in Teams für Mitarbeiter in Service und Produktion an. Weitere Informationen finden Sie [unter "Anpassen von Teams-Apps für Ihre Mitarbeiter in Service und Produktion](pin-teams-apps-based-on-license.md)".

    Dieses Feature ist für F-Lizenzen verfügbar. Weitere Lizenztypen werden in Zukunft unterstützt.
1. Aktivieren oder deaktivieren Sie unter **Drittanbieter-Apps** diese Einstellungen, um den Zugriff auf Drittanbieter-Apps zu steuern:

    * **Drittanbieter-Apps zulassen**: Steuert, ob Benutzer Drittanbieter-Apps verwenden können. Wenn Sie diese Einstellung deaktivieren, können Ihre Benutzer keine Drittanbieter-Apps installieren oder verwenden, und der **App-Status** dieser Apps wird in der Tabelle organisationsweit als blockiert angezeigt.

        > [!NOTE]
        > Wenn **"Apps von Drittanbietern zulassen** " deaktiviert ist, sind [ausgehende Webhooks](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) weiterhin für alle Benutzer aktiviert. Sie können sie jedoch auf Benutzerebene steuern, indem Sie die ausgehende Webhook-App über [App-Berechtigungsrichtlinien](teams-app-permission-policies.md) zulassen oder blockieren. Wenn Sie über vorhandene [App-Berechtigungsrichtlinien](teams-app-permission-policies.md) für **Microsoft-Apps** verfügen, die **die Einstellung "Bestimmte Apps zulassen" verwenden und alle anderen blockieren** , und Ausgehende Webhooks für Benutzer aktivieren möchten, fügen Sie die Ausgehende Webhook-App zur Liste hinzu.

        > [!NOTE]
        > Benutzer von Microsoft Teams können Apps hinzufügen, wenn sie Besprechungen oder Chats mit Personen aus anderen Organisationen hosten. Sie können auch Apps verwenden, die von Personen in anderen Organisationen freigegeben werden, wenn sie an Besprechungen oder Chats teilnehmen, die von diesen Organisationen gehostet werden. Es werden die Datenrichtlinien der Organisation des Hostingbenutzers sowie die Datenfreigabemethoden von Drittanbieter-Apps, die von der Organisation dieses Benutzers freigegen werden, angewendet.

    * **Alle neuen Drittanbieter-Apps, die im Store veröffentlicht werden, standardmäßig zulassen**: Steuert, ob neue Drittanbieter-Apps, die im Teams-App-Store veröffentlicht werden, automatisch in Teams verfügbar gemacht werden. Sie können diese Option nur aktivieren, wenn Sie Drittanbieter-Apps zulassen.

1. Deaktivieren oder aktivieren Sie unter **"Benutzerdefinierte Apps**" **die Option "Interaktion mit benutzerdefinierten Apps zulassen**". Diese Einstellung steuert, ob Benutzer mit benutzerdefinierten Apps interagieren können. Weitere Informationen finden Sie unter [Verwalten von benutzerdefinierten App-Richtlinien und Einstellungen in Teams](teams-custom-app-policies-and-settings.md).
1. Wählen Sie "Für organisationsweite App-Einstellungen **speichern"** aus, um wirksam zu werden.

## <a name="see-also"></a>Siehe auch

* [Verwalten von Teams während des Übergangs vom Skype for Business Admin Center](manage-teams-skypeforbusiness-admin-center.md)
