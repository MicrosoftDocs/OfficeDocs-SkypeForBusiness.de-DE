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
ms.openlocfilehash: 830850be078da8086253bbb57bb4a29ce6d7c951
ms.sourcegitcommit: bf0071417188b33fc23e2a420187da5024d4bd40
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2022
ms.locfileid: "64961238"
---
# <a name="manage-your-apps-in-the-microsoft-teams-admin-center"></a>Verwalten Ihrer Apps im Microsoft Teams Admin Center

Als Administrator können Sie alle Teams Apps für Ihre Organisation anzeigen und verwalten. Auf der Seite "Apps verwalten" im Teams Admin Center haben Sie folgende Möglichkeiten:

- [Zulassen oder Blockieren von Apps auf Organisationsebene](#allow-and-block-apps)
- [Von Herausgebern blockierte Apps](#apps-blocked-by-publishers)
- [Hinzufügen von Apps zu Teams](#add-an-app-to-a-team)
- [Genehmigen oder Hochladen neuer benutzerdefinierter Apps in den App Store Ihrer Organisation](#publish-a-custom-app-to-your-organizations-app-store)
- [Von Apps angeforderte Berechtigungen anzeigen](#view-resource-specific-consent-permissions)
- [Erteilen der Zustimmung zu Apps](#grant-admin-consent-to-apps)
- [Kaufdienst für Drittanbieter-Apps](#purchase-services-for-third-party-apps)
- [Anzeigen des Status und der Eigenschaften von Apps auf Organisationsebene](#view-apps)
- [Organisationsweite App-Einstellungen verwalten](#manage-org-wide-app-settings)
- [Anzeigen von Sicherheits- und Complianceinformationen für Microsoft 365 zertifizierte Apps](#view-security-and-compliance-information-for-microsoft-365-certified-apps)

Auf der Seite "Apps verwalten" erhalten Sie einen Einblick in alle verfügbaren Apps und erhalten die Informationen, die Sie benötigen, um zu entscheiden, welche Apps in Ihrer Organisation zugelassen oder blockiert werden sollen. Anschließend können Sie [App-Berechtigungsrichtlinien](teams-app-permission-policies.md), [App-Setuprichtlinien](teams-app-setup-policies.md) und [benutzerdefinierte App-Richtlinien und -Einstellungen](teams-custom-app-policies-and-settings.md) verwenden, um die App-Erfahrung für bestimmte Benutzer in Ihrer Organisation zu konfigurieren.

Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Teams-Apps** > **Apps verwalten**. Sie müssen ein globaler Administrator oder Teams Dienstadministrator sein, um auf die Seite zugreifen zu können.

![Screenshot der Seite "Verwaltete Apps".](media/manage-apps.png)

> [!NOTE]
> Die Seite "Apps verwalten" ist in Microsoft 365 Government Community Cloud High(GCCH)- oder Department of Defense (DoD)-Bereitstellungen von Teams noch nicht verfügbar.

## <a name="view-apps"></a>Anzeigen von Apps

Sie können jede App einschließlich der folgenden Informationen zu jeder App anzeigen.

![Screenshot der App-Detailseite für eine App.](media/app-detail-page.jpg)

- **Name**: Der App-Name. Wählen Sie den App-Namen aus, um zur Seite mit den App-Details zu wechseln, um weitere Informationen zur App anzuzeigen. Dazu gehört eine Beschreibung der App, unabhängig davon, ob sie zulässig oder blockiert ist, Version, Datenschutzrichtlinie, Nutzungsbedingungen, Kategorien, die für die App gelten, Zertifizierungsstatus, unterstützte Funktionen und App-ID.
- **Zertifizierung**: Wenn die App zertifiziert wurde, wird entweder **Microsoft 365 zertifiziert** oder **Publisher Nachweis angezeigt**. Wählen Sie den Link aus, um Zertifizierungsdetails für die App anzuzeigen. Wenn sie angezeigt wird `--`, verfügen wir nicht über Zertifizierungsinformationen für die App. Weitere Informationen zu zertifizierten Apps in Teams finden Sie [unter Microsoft 365 App-Zertifizierungsprogramm](/microsoft-365-app-certification/overview).
- **Publisher**: Name des Herausgebers.
- **Veröffentlichungsstatus**: Veröffentlichungsstatus benutzerdefinierter Apps.
- **Status**: Status der App auf Organisationsebene, der eine der folgenden sein kann:
  - **Zulässig**: Die App ist für alle Benutzer in Ihrer Organisation verfügbar.
  - **Blockiert**: Die App ist blockiert und nicht für Benutzer in Ihrer Organisation verfügbar.
  - **Vom Herausgeber blockiert**: Die App wird vom Herausgeber blockiert und standardmäßig für Endbenutzer ausgeblendet. Nachdem Sie die App mithilfe der Anleitungen des Herausgebers eingerichtet haben, können Sie die App zulassen oder blockieren, um sie Endbenutzern zur Verfügung zu stellen.
  - **Organisationsweit blockiert**: Die App wird in organisationsweiten App-Einstellungen blockiert.
      Es ist wichtig zu wissen, dass diese Spalte den zulässigen und blockierten Status von Apps darstellt, die sich zuvor im **organisationsweiten Einstellungsbereich** befanden. Jetzt können Sie Apps organisationsweit auf der Seite " **Apps verwalten"** anzeigen, blockieren und zulassen.
- **Lizenzen**: Gibt an, ob eine App ein SaaS-Abonnement (Software as a Service) zum Kauf anbietet. Diese Spalte gilt nur für Apps von Drittanbietern. Jede Drittanbieter-App weist einen der folgenden Werte auf:
  - **Kauf**: Die App bietet ein SaaS-Abonnement und steht zum Kauf zur Verfügung.  
  - **Gekauft**: Die App bietet ein SaaS-Abonnement an, und Sie haben Lizenzen dafür erworben.
  - **- -**: Die App bietet kein SaaS-Abonnement an.
- **Benutzerdefinierte App**: Gibt an, ob es sich bei der App um eine benutzerdefinierte App handelt.
- **Berechtigungen**: Gibt an, ob eine in Azure Active Directory (Azure AD) registrierte Drittanbieter- oder benutzerdefinierte App über Berechtigungen verfügt, die zustimmungsbedürftig sind. Es wird einer der folgenden Werte angezeigt:
  - **Details anzeigen**: Die App verfügt über Berechtigungen, die eine Zustimmung erfordern, bevor die App auf Daten zugreifen kann.
  - **- -**: Die App verfügt nicht über Berechtigungen, die zustimmungsbedürftig sind.
- **Kategorien**: Kategorien, die für die App gelten.
- **Version**: App-Version.
- **Administrator kann in Besprechungen installieren**: Gibt an, ob eine App von Administratoren in Teambesprechungen installiert werden kann. [Weitere Informationen](teams-app-setup-policies.md#install-apps)

Wenn Sie die gewünschten Informationen in der Tabelle anzeigen möchten, wählen Sie in der oberen rechten Ecke **"Spalte bearbeiten** " aus, um der Tabelle Spalten hinzuzufügen oder zu entfernen.

## <a name="publish-a-custom-app-to-your-organizations-app-store"></a>Veröffentlichen einer benutzerdefinierten App im App Store Ihrer Organisation

Verwenden Sie die Seite "Apps verwalten", um Apps zu veröffentlichen, die speziell für Ihre Organisation erstellt wurden. Nachdem Sie eine benutzerdefinierte App veröffentlicht haben, steht sie Benutzern im App Store Ihrer Organisation zur Verfügung. Es gibt zwei Möglichkeiten zum Veröffentlichen einer benutzerdefinierten App im App Store Ihrer Organisation. Die Art und Weise, wie Sie die App verwenden, hängt davon ab, wie Sie die App erhalten.

- [Genehmigen einer benutzerdefinierten App](#approve-a-custom-app): Verwenden Sie diese Methode, wenn der Entwickler die App mithilfe der Teams App-Übermittlungs-API direkt an die Seite "Apps verwalten" übermittelt. Sie können die App dann direkt über die App-Detailseite überprüfen und veröffentlichen (oder ablehnen).
- [Hochladen eines App-Pakets](#upload-an-app-package): Verwenden Sie diese Methode, wenn der Entwickler Ihnen das App-Paket im .zip Format sendet. Sie veröffentlichen die App, indem Sie das App-Paket hochladen.

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
2. Wählen Sie **"Zum Team hinzufügen" aus**.
3. Suchen **Sie im Bereich "Zu Team hinzufügen** " nach dem Team, dem Sie die App hinzufügen möchten, wählen Sie das Team aus, und wählen Sie dann **"Übernehmen"** aus.

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

## <a name="view-security-and-compliance-information-for-microsoft-365-certified-apps"></a>Anzeigen von Sicherheits- und Complianceinformationen für Microsoft 365 zertifizierte Apps

Beim Auswerten einer App für ihre Organisation können Administratoren unabhängige Cloud Access Security Broker (CASB) verwenden, z. B. Microsoft Cloud App Security (MCAS), um Informationen zu Sicherheit und Verhalten einer App zu finden. Das Teams Admin Center enthält Sicherheits- und Complianceinformationen von MCAS für Microsoft 365 zertifizierte Apps, sodass Sie weitere Informationen dazu erhalten, ob die App Ihren Anforderungen entspricht.

> [!NOTE]
> Dieses Feature steht allen Administratoren zur Verfügung, unabhängig davon, ob Ihre Organisation über eine Lizenz verfügt, die MCAS unterstützt.

Führen Sie die folgenden Schritte aus, um auf MCAS Informationen zuzugreifen:

1. Wählen Sie im Teams Admin Center unter **Teams Apps** "**Apps verwalten"** aus.
1. Wählen Sie **"Zertifizierung**" aus, um Apps zu sortieren und alle Microsoft 365 zertifizierten Apps an den Anfang der Tabelle zu verschieben.
1. Wählen Sie eine Microsoft 365 Zertifizierte App aus.
1. Wählen Sie die Registerkarte **"Sicherheit und Compliance** " aus.

![Screenshot der Registerkarte "Sicherheit und Compliance" im Admin Center Teams.](media/mcas.png)

Auf dieser Registerkarte finden Sie Informationen zu Sicherheit, Compliance und Datenschutz. Sie können auch jede Dropdownliste erweitern, um weitere Details dazu zu erhalten, welche Funktionen für die ausgewählte Anwendung unterstützt werden.

## <a name="related-topics"></a>Verwandte Themen

- [Administratoreinstellungen für Apps in Microsoft Teams](admin-settings.md)
