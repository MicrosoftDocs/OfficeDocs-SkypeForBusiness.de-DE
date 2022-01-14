---
title: Verwalten Ihrer Apps im Microsoft Teams Admin Center
author: KarliStites
ms.author: kastites
manager: serdars
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
description: Erfahren Sie, wie Sie ihre Teams-Apps auf der Seite Apps verwalten im Microsoft Teams Admin Center verwalten.
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: ec9caa743f9a8cd5bf43d7b6e67f83d15ee2a045
ms.sourcegitcommit: c7904086e6956ad8d0e5544530bcc90d608b6e6a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2022
ms.locfileid: "62039908"
---
# <a name="manage-your-apps-in-the-microsoft-teams-admin-center"></a>Verwalten Ihrer Apps im Microsoft Teams Admin Center

Als Administrator können Sie alle Ihre Teams für Ihre Organisation anzeigen und verwalten. Auf der Seite Apps verwalten im Teams Admin Center können Sie:

- [Zulassen oder Blockieren von Apps auf Organisationsebene](#allow-and-block-apps)
- [Von Herausgebern blockierte Apps](#apps-blocked-by-publishers)
- [Hinzufügen von Apps zu Teams](#add-an-app-to-a-team)
- [Genehmigen oder Hochladen neuer benutzerdefinierter Apps im App Store Ihrer Organisation](#publish-a-custom-app-to-your-organizations-app-store)
- [Anzeigen von von Apps angeforderten Berechtigungen](#view-resource-specific-consent-permissions)
- [Zustimmung für Apps erteilen](#grant-admin-consent-to-apps)
- [Kaufdienst für Apps von Drittanbietern](#purchase-services-for-third-party-apps)
- [Anzeigen des Status und der Eigenschaften von Apps auf Organisationsebene](#view-apps)
- [Verwalten von organisationsweiten App-Einstellungen](#manage-org-wide-app-settings)
- [Anzeigen von Sicherheits- und Complianceinformationen Microsoft 365 zertifizierten Apps](#view-security-and-compliance-information-for-microsoft-365-certified-apps)

Auf der Seite "Apps verwalten" erhalten Sie einen Einblick in alle verfügbaren Apps und erhalten so die Informationen, die Sie benötigen, um zu entscheiden, welche Apps in der gesamten Organisation zulässig sind oder blockiert werden. Anschließend können Sie App-Berechtigungsrichtlinien, Richtlinien [](teams-custom-app-policies-and-settings.md) [](teams-app-setup-policies.md)für die App-Einrichtung und benutzerdefinierte App-Richtlinien und -Einstellungen verwenden, um die App-Benutzererfahrung für bestimmte Benutzer in Ihrer Organisation zu konfigurieren. [](teams-app-permission-policies.md)

Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Teams-Apps** > **Apps verwalten**. Sie müssen ein globaler Administrator oder ein Teams sein, um auf die Seite zugreifen zu können.

> [!NOTE]
> Die Seite Apps verwalten steht in Microsoft 365 Government Community Cloud High-Bereitstellungen (GCCH) oder Department of Defense (DoD) von Teams.

## <a name="view-apps"></a>Anzeigen von Apps

Sie können jede App einschließlich der folgenden Informationen zu jeder App anzeigen.

![Screenshot der Seite "Verwaltete Apps"](media/manage-apps.png)

- **Name:** Der App-Name. Wählen Sie den App-Namen aus, um zur Seite mit den App-Details zu wechseln, um weitere Informationen zur App anzuzeigen. Dies umfasst eine Beschreibung der App, ob zulässig oder blockiert, Version, Datenschutzrichtlinie, Nutzungsbedingungen, Kategorien, die für die App gelten, den Zertifizierungsstatus, unterstützte Funktionen und die App-ID. Nachfolgend ein Beispiel:

  ![Screenshot der Seite "Apps-Details" für eine App](media/manage-apps-app-details.png)
  
- **Zertifizierung:** Wenn die App die Zertifizierung durchgegangen ist, sehen Sie entweder **Microsoft 365** Zertifizierung oder **Publisher Nachweis.** Wählen Sie den Link aus, um Zertifizierungsdetails für die App anzuzeigen. Wenn "" angezeigt wird, gibt es **--** keine Zertifizierungsinformationen für die App. Weitere Informationen zu zertifizierten Apps in Teams finden Sie unter [Microsoft 365-Zertifizierungsprogramm für Apps.](/teams-app-certification/all-apps)  
- **Publisher:** Name des Herausgebers.
- **Veröffentlichungsstatus:** Veröffentlichungsstatus von benutzerdefinierten Apps.
- **Status:** Status der App auf Organisationsebene. Dies kann einer der folgenden sein:
    - **Zulässig:** Die App ist für alle Benutzer in Ihrer Organisation verfügbar.
    - **Blockiert:** Die App ist blockiert und für keine Benutzer in Ihrer Organisation verfügbar.
    - **Vom Herausgeber blockiert:** Die App wird vom Herausgeber blockiert und standardmäßig für Endbenutzer ausgeblendet. Nachdem Sie die App anhand der Richtlinien des Herausgebers eingerichtet haben, können Sie die App zulassen oder blockieren, um sie Endbenutzern zur Verfügung zu stellen.
    - **Organisationsweit blockiert:** Die App wird in organisationsweiten App-Einstellungen blockiert.
      Es ist wichtig zu wissen, dass diese Spalte den zulässigen und blockierten Status von Apps darstellt, die sich zuvor im bereich **"Organisationsweite Einstellungen"** hatten. Sie können apps jetzt organisationsweit auf der Seite "Apps verwalten" anzeigen, **blockieren und** zulassen.
- **Lizenzen:** Gibt an, ob eine App ein SaaS-Abonnement (Software as a Service) zum Kauf anbietet. Diese Spalte gilt nur für Apps von Drittanbietern. Jede Drittanbieter-App hat einen der folgenden Werte:
- **Kaufen:** Die App bietet ein SaaS-Abonnement und kann zum Kauf angeboten werden.  
- **Gekauft:** Die App bietet ein SaaS-Abonnement, und Sie haben Lizenzen dafür erworben.
- **- –**: Die App bietet kein SaaS-Abonnement an.
- **Benutzerdefinierte App:** Gibt an, ob es sich bei der App um eine benutzerdefinierte App handelt.
- **Berechtigungen:** Gibt an, ob ein Drittanbieter oder eine benutzerdefinierte App, die in Azure Active Directory (Azure AD) registriert ist, über Berechtigungen verfügt, die eine Zustimmung benötigen. Es wird einer der folgenden Werte angezeigt:
- **Details anzeigen:** Die App verfügt über Berechtigungen, die eine Zustimmung erfordern, bevor die App auf Daten zugreifen kann.
- **- –**: Die App verfügt nicht über Berechtigungen, für die eine Zustimmung erforderlich ist.
- **Kategorien:** Kategorien, die für die App gelten.
- **Version:** App-Version.
- **Administrator kann in Besprechungen installieren:** Gibt an, ob eine App von Administratoren in Teambesprechungen installiert werden kann. [Weitere Informationen](teams-app-setup-policies.md#install-apps)

Wenn Sie die Informationen anzeigen möchten, die in der Tabelle enthalten sein sollen, wählen Sie **in** der oberen rechten Ecke Spalte bearbeiten aus, um der Tabelle Spalten hinzuzufügen oder spalten zu entfernen.

## <a name="publish-a-custom-app-to-your-organizations-app-store"></a>Veröffentlichen einer benutzerdefinierten App im App Store Ihrer Organisation

Verwenden Sie die Seite "Apps verwalten", um Apps zu veröffentlichen, die speziell für Ihre Organisation erstellt wurden. Nachdem Sie eine benutzerdefinierte App veröffentlicht haben, steht sie Benutzern im App Store Ihrer Organisation zur Verfügung. Es gibt zwei Möglichkeiten, eine benutzerdefinierte App im App Store Ihrer Organisation zu veröffentlichen. Die Art der Verwendung hängt davon ab, wie Sie die App erhalten.

- [Genehmigen einer benutzerdefinierten](#approve-a-custom-app)App: Verwenden Sie diese Methode, wenn der Entwickler die App mithilfe der API für die App-Übermittlung direkt an die Seite "Apps verwalten Teams übermittelt. Anschließend können Sie die App direkt über die Seite mit den App-Details überprüfen und veröffentlichen (oder ablehnen).
- [Hochladen eines App-Pakets:](#upload-an-app-package)Verwenden Sie diese Methode, wenn Ihnen der Entwickler das App-Paket im .zip sendet. Sie veröffentlichen die App, indem Sie das App-Paket hochladen.

### <a name="approve-a-custom-app"></a>Genehmigen einer benutzerdefinierten App

Das **Widget "Ausstehende Genehmigungen"** auf der Seite "Apps verwalten" benachrichtigt Sie, wenn ein Entwickler eine App über die API Teams App-Übermittlung übermittelt. Eine neu übermittelte App wird mit dem **Veröffentlichungsstatus** **Übermittelt** und dem **Status Blockiert** **aufgeführt.** Wechseln Sie zur Seite mit den App-Details, um weitere Informationen  zu der App anzuzeigen. Um sie dann zu veröffentlichen, legen Sie Veröffentlichungsstatus auf **Veröffentlichen .**

Sie werden auch benachrichtigt, wenn ein Entwickler ein Update an eine benutzerdefinierte App übermittelt. Anschließend können Sie das Update auf der Seite mit den App-Details überprüfen und veröffentlichen (oder ablehnen). Alle App-Berechtigungs- und App-Setuprichtlinien bleiben für die aktualisierte App erhalten.

Weitere Informationen finden Sie unter [Veröffentlichen einer benutzerdefinierten App, die](submit-approve-custom-apps.md)über die API für Teams-Übermittlung übermittelt wird.

### <a name="upload-an-app-package"></a>Hochladen eines App-Pakets

Der Entwickler erstellt ein Teams-App-Paket [mit Teams App Studio](/microsoftteams/platform/get-started/get-started-app-studio)und sendet es dann im .zip an Sie. Wenn Sie über das App-Paket verfügen, können Sie es in den App Store Ihrer Organisation hochladen.

Wählen Sie zum Hochladen einer neuen benutzerdefinierten App **Hochladen,** um das App-Paket hochzuladen. Da die App nach dem Hochladen nicht hervorgehoben wird, müssen Sie die Liste der Apps auf der Seite Apps verwalten durchsuchen, um sie zu finden.

Wenn Sie eine App nach dem Hochladen aktualisieren möchten, wählen Sie in der Liste der Apps auf der Seite Apps verwalten den App-Namen und dann **Aktualisieren aus.** Dadurch werden die vorhandene App ersetzt, und alle App-Berechtigungsrichtlinien und App-Setuprichtlinien bleiben für die aktualisierte App erhalten.

Weitere Informationen finden Sie unter [Veröffentlichen einer benutzerdefinierten App durch Hochladen eines App-Pakets.](upload-custom-apps.md)

## <a name="allow-and-block-apps"></a>Zulassen und Blockieren von Apps

Auf der Seite "Apps verwalten" können Sie einzelne Apps auf Organisationsebene zulassen oder blockieren. Es zeigt jede verfügbare App und den aktuellen App-Status auf Organisationsebene an. (Das Blockieren und Zulassen von Apps auf Organisationsebene wurde aus dem Einstellungsbereich der **organisationsweiten** App zu diesem Bereich verschoben.)

Wenn Sie eine App zulassen oder blockieren möchten, wählen Sie sie und dann Zulassen **oder** Blockieren **aus.** Wenn Sie eine App blockieren, werden alle Interaktionen mit dieser App deaktiviert, und die App wird nicht in Teams Benutzern in Ihrer Organisation angezeigt.

Wenn Sie eine App auf der Seite Apps verwalten blockieren oder zulassen, wird diese App für alle Benutzer in Ihrer Organisation blockiert oder zulässig.  Wenn Sie eine App in einer Berechtigungsrichtlinie für eine Teams-App blockieren oder zulassen, wird sie für Benutzer, denen diese Richtlinie zugewiesen ist, blockiert oder zulässig. Damit ein Benutzer beliebige Apps installieren und damit interagieren kann, müssen Sie die App auf Organisationsebene auf der Seite Apps verwalten und in der dem Benutzer zugewiesenen App-Berechtigungsrichtlinie zulassen.

 > [!NOTE]
 > Wenn Sie eine App deinstallieren möchten, klicken  Sie mit  der rechten Maustaste auf die App, und klicken Sie dann auf der linken Seite auf Deinstallieren, oder verwenden Sie das Menü Weitere Apps.

## <a name="apps-blocked-by-publishers"></a>Von Herausgebern blockierte Apps

Wenn ein ISV eine App im globalen App Store veröffentlicht, benötigt er möglicherweise Administratoren, um die App-Erfahrung zu konfigurieren oder anzupassen. Der Administrator kann es Endbenutzern zur Verfügung stellen, wenn die App vollständig eingerichtet ist.

Contoso Electronics beispielsweise ist ein ISV, der eine Helpdesk-App für Microsoft Teams. Contoso Electronics möchte, dass Kunden bestimmte Eigenschaften der App einrichten, sodass die App bei der Interaktion der Benutzer mit der App wie erwartet funktioniert. Bevor ein Administrator die Anwendung zulassen oder  blockieren kann, wird sie im Teams Admin Center als Vom Herausgeber blockiert angezeigt und für Endbenutzer standardmäßig ausgeblendet. Nachdem Sie den Anweisungen des Herausgebers zum Einrichten der App folgen, können Sie sie Benutzern zur Verfügung stellen, indem Sie den Status in Zulässig ändern **oder** die Verwendung der App blockieren, indem Sie den Status in Blockiert **ändern.**

![Screenshot des Status "Vom Herausgeber blockiert" im Teams Admin Center.](media/blocked-by-publisher.png)

## <a name="add-an-app-to-a-team"></a>Hinzufügen einer App zu einem Team

Sie verwenden die **Schaltfläche Zu Team hinzufügen,** um eine App für ein Team zu installieren. Beachten Sie, dass dies nur für Apps gilt, die in einem Teambereich installiert werden können. Die **Schaltfläche Zu Team hinzufügen** steht für Apps, die nur im persönlichen Bereich installiert werden können, nicht zur Verfügung.

![Screenshot der Schaltfläche "Zu Team hinzufügen"](media/manage-apps-add-app-team.png)

1. Suchen Sie nach der app, und wählen Sie die App aus, indem Sie links des App-Namens klicken.
2. Wählen Sie **Zu Team hinzufügen aus.**
3. Suchen Sie **im Bereich Zu Team** hinzufügen nach dem Team, dem Sie die App hinzufügen möchten, wählen Sie das Team und dann Übernehmen **aus.**

## <a name="customize-an-app"></a>Anpassen einer App

Sie können eine App jetzt so anpassen, dass sie ein bestimmtes Erscheinungsbild gemäß den Anforderungen Ihrer Organisation bietet. Siehe [Anpassen von Apps in Teams](customize-apps.md).

## <a name="purchase-services-for-third-party-apps"></a>Erwerben von Diensten für Apps von Drittanbietern

Sie können direkt über die Seite Apps verwalten nach Lizenzen für Dienste suchen und kaufen, die von Drittanbieter-Apps für Benutzer in Ihrer Organisation angeboten werden. Die **Spalte Lizenzen** in der Tabelle gibt an, ob eine App ein kostenpflichtiges SaaS-Abonnement anbietet. Wählen **Sie Jetzt kaufen** aus, um Pläne und Preisinformationen zu sehen und Lizenzen für Ihre Benutzer zu kaufen. Weitere Informationen finden Sie unter Erwerben von [Teams für Drittanbieter-Apps im Microsoft Teams Admin Center.](purchase-third-party-apps.md)

## <a name="grant-admin-consent-to-apps"></a>Erteilen der Administratorzusendung für Apps

Sie können Apps, die Berechtigungen für alle Benutzer in Ihrer Organisation anfordern, eine Überprüfung und Zustimmung erteilen. Dadurch müssen Benutzer die von der App angeforderten Berechtigungen beim Starten der App nicht überprüfen und akzeptieren. In **der Spalte** Berechtigungen wird angegeben, ob eine App Über Berechtigungen verfügt, für die eine Zustimmung erforderlich ist. Es wird ein Link **Details** anzeigen für jede App angezeigt, die in einer App registriert Azure AD, die über Berechtigungen verfügt, die ihre Zustimmung benötigen. Weitere Informationen finden Sie unter Anzeigen [von App-Berechtigungen und Erteilen der Administratorzusberechtigung im Microsoft Teams Admin Center.](app-permissions-admin-center.md)

## <a name="view-resource-specific-consent-permissions"></a>Anzeigen ressourcenspezifischer Zustimmungsberechtigungen

Mit ressourcenspezifischen Zustimmungsberechtigungen (RSC) können Teambesitzer einer App die Zustimmung zum Zugreifen auf und Ändern von Teamdaten erteilen. RSC-Berechtigungen sind granular und Teams Berechtigungen, die definieren, was eine App in einem bestimmten Team tun kann. RsC-Berechtigungen können Sie auf der **Registerkarte** Berechtigungen der App-Detailseite für eine App anzeigen. Weitere Informationen finden Sie unter Anzeigen [von App-Berechtigungen und Erteilen der Administratorzusberechtigung im Microsoft Teams Admin Center.](app-permissions-admin-center.md)

## <a name="manage-org-wide-app-settings"></a>Verwalten von organisationsweiten App-Einstellungen

Verwenden Sie organisationsweite App-Einstellungen, um zu steuern, ob Benutzer eine angepasste App-Erfahrung basierend auf der Lizenz erhalten (in Kürze verfügbar), ob Benutzer Apps von Drittanbietern installieren können und ob Benutzer benutzerdefinierte Apps in Ihrer Organisation hochladen oder damit interagieren können. Organisationsweite App-Einstellungen regeln das Verhalten für alle Benutzer und setzen alle anderen App-Berechtigungsrichtlinien, die den Benutzern zugewiesen wurden, außer Kraft. Sie können sie verwenden, um bösartige oder problematische Apps zu kontrollieren.

> [!NOTE]
> Informationen zur Verwendung von organisationsweiten App-Einstellungen in Microsoft 365 Government – Government Community Cloud High GCCH and Department of Defense (DoD)-Bereitstellungen von Teams finden Sie unter Verwalten von Richtlinien für App-Berechtigungen [in Teams.](teams-app-permission-policies.md)

1. Wählen Sie auf der Seite Apps verwalten die **Option Organisationsweite App-Einstellungen aus.** Sie können in dem Fenster dann die gewünschten Einstellungen konfigurieren.

    ![Screenshot der organisationsweiten App-Einstellungen.](media/manage-apps-org-wide-app-settings.png)

1. (In Kürze folgen) Deaktivieren **oder aktivieren Sie unter** Maßgeschneiderte Apps die Maßgeschneiderte Apps basierend auf Lizenzen **anzeigen.** Wenn diese Einstellung aktivieren, erhalten Die Benutzer eine Erfahrung, in der Apps basierend auf ihrer Lizenz angeheftet werden. Weitere Informationen finden Sie unter [Anpassen ihrer Teams basierend auf einer Lizenz.](pin-teams-apps-based-on-license.md)

    Dieses Feature ist für F-Lizenzen verfügbar. Andere Lizenztypen werden in Zukunft unterstützt.
1. Aktivieren oder deaktivieren Sie unter **Drittanbieter-Apps** diese Einstellungen, um den Zugriff auf Drittanbieter-Apps zu steuern:

    - **Drittanbieter-Apps zulassen**: Steuert, ob Benutzer Drittanbieter-Apps verwenden können. Wenn Sie diese Einstellung deaktivieren, können Ihre Benutzer keine Drittanbieter-Apps installieren oder verwenden, und der **App-Status** dieser Apps wird in der Tabelle als "Blockiert" angezeigt.

        > [!NOTE]
        > Wenn Drittanbieter-Apps zulassen deaktiviert ist, sind ausgehende [Webhooks](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) weiterhin für alle Benutzer aktiviert, aber Sie können sie auf Benutzerebene steuern, indem Sie die ausgehende Webhook-App über **App-Berechtigungsrichtlinien** zulassen oder [blockieren.](teams-app-permission-policies.md) <br><br>Wenn Sie über [](teams-app-permission-policies.md) vorhandene App-Berechtigungsrichtlinien für  **Microsoft-Apps** verfügen, die die Einstellung Bestimmte Apps zulassen und alle anderen blockieren verwenden, und Sie ausgehende Webhooks für Benutzer aktivieren möchten, fügen Sie die ausgehende Webhook-App zur Liste hinzu.

        > [!NOTE]
        > Benutzer von Microsoft Teams können Apps hinzufügen, wenn sie Besprechungen oder Chats mit Personen aus anderen Organisationen hosten. Sie können auch Apps verwenden, die von Personen in anderen Organisationen freigegeben werden, wenn sie an Besprechungen oder Chats teilnehmen, die von diesen Organisationen gehostet werden. Es werden die Datenrichtlinien der Organisation des Hostingbenutzers sowie die Datenfreigabemethoden von Drittanbieter-Apps, die von der Organisation dieses Benutzers freigegen werden, angewendet.

    - **Alle neuen Drittanbieter-Apps, die im Store veröffentlicht werden, standardmäßig zulassen**: Steuert, ob neue Drittanbieter-Apps, die im Teams-App-Store veröffentlicht werden, automatisch in Teams verfügbar gemacht werden. Sie können diese Option nur aktivieren, wenn Sie Drittanbieter-Apps zulassen.

1. Deaktivieren **oder aktivieren Sie unter** Benutzerdefinierte Apps das Bzw. die Aktivieren von Interaktion mit **benutzerdefinierten Apps zulassen.** Diese Einstellung steuert, ob Benutzer mit benutzerdefinierten Apps interagieren können. Weitere Informationen finden Sie unter [Verwalten von benutzerdefinierten App-Richtlinien und Einstellungen in Teams](teams-custom-app-policies-and-settings.md).
1. Wählen **Sie Speichern** aus, damit die Organisationsweiten App-Einstellungen wirksam werden.

## <a name="view-security-and-compliance-information-for-microsoft-365-certified-apps"></a>Anzeigen von Sicherheits- und Complianceinformationen für Microsoft 365 zertifizierte Apps

Bei der Auswertung einer App für ihre Organisation können Administratoren unabhängige Cloud Access Security Broker (CASB), z. B. Microsoft Cloud App Security (MCAS), verwenden, um Informationen zu Sicherheit und Verhalten einer App zu finden. Das Teams Admin Center enthält Sicherheits- und Complianceinformationen von MCAS für Microsoft 365-zertifizierte Apps, sodass Sie weitere Informationen dazu erhalten, ob die App Ihren Anforderungen entspricht oder nicht.

> [!NOTE]
> Dieses Feature steht allen Administratoren zur Verfügung, unabhängig davon, ob Ihre Organisation über eine Lizenz verfügt, die MCAS unterstützt.

Führen Sie die folgenden Schritte aus, um auf MCAS-Informationen zu zugreifen:

1. Wählen Sie Teams Admin Center  unter Apps Teams **aus.**
1. Wählen **Sie Zertifizierung** aus, um Apps zu sortieren und Microsoft 365 zertifizierten Apps an den Tabellen oben zu bringen.
1. Wählen Sie eine Microsoft 365 aus.
1. Wählen Sie **die Registerkarte Sicherheit und Compliance** aus.

![Screenshot der Teams Admin Center auf der Registerkarte "Sicherheit und Compliance".](media/mcas.png)

Auf dieser Registerkarte finden Sie Informationen zu Sicherheit, Compliance und Datenschutz. Sie können auch jede Dropdownliste erweitern, um weitere Details dazu zu erhalten, welche Funktionen für die ausgewählte Anwendung unterstützt werden.

## <a name="related-topics"></a>Verwandte Themen

- [Administratoreinstellungen für Apps in Microsoft Teams](admin-settings.md)
