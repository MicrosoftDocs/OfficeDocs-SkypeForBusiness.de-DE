---
title: Verwalten Ihrer Apps im Microsoft Teams Admin Center
author: cichur
ms.author: v-cichur
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
description: Erfahren Sie, wie Sie Ihre Teams-Apps auf der Seite "Apps verwalten" im Microsoft Teams Admin Center verwalten.
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: ae060bf68b265c4e1e828d2f7a1848e1515db04e
ms.sourcegitcommit: d3883b3d9de7251e60033bece53a2bab17d7b1b8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/30/2021
ms.locfileid: "51450622"
---
# <a name="manage-your-apps-in-the-microsoft-teams-admin-center"></a>Verwalten Ihrer Apps im Microsoft Teams Admin Center

Als Administrator können Sie auf der Seite Apps verwalten im Microsoft Teams Admin Center alle Teams-Apps für Ihre Organisation anzeigen und verwalten. Hier können Sie den Status und die Eigenschaften von Apps auf Organisationsebene anzeigen, neue benutzerdefinierte Apps im App Store Ihrer Organisation genehmigen oder hochladen, Apps auf Organisationsebene blockieren oder zulassen, Apps zu Teams hinzufügen, Dienste für Drittanbieter-Apps erwerben, von Apps angeforderte Berechtigungen anzeigen, Apps administratorweite Zustimmung erteilen und organisationsweite App-Einstellungen verwalten.

Auf der Seite "Apps verwalten" erhalten Sie einen Einblick in alle verfügbaren Apps und erhalten die Informationen, die Sie benötigen, um zu entscheiden, welche Apps in Ihrer Organisation zulässig oder blockiert werden. Anschließend können Sie Richtlinien für [App-Berechtigungen,](teams-app-permission-policies.md)Richtlinien für die App-Einrichtung und benutzerdefinierte App-Richtlinien und -Einstellungen verwenden, um die App-Benutzererfahrung für bestimmte Benutzer in Ihrer Organisation zu konfigurieren. [](teams-app-setup-policies.md) [](teams-custom-app-policies-and-settings.md)

Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Teams-Apps** > **Apps verwalten**. Sie müssen ein globaler Administrator oder Teams-Dienstadministrator sein, um auf die Seite zugreifen zu können.

> [!NOTE]
> Die Seite "Apps verwalten" ist in Microsoft 365 Government Community Cloud (GCC)-Bereitstellungen von Teams noch nicht verfügbar.

## <a name="view-apps"></a>Anzeigen von Apps

Sie können jede App anzeigen, einschließlich der folgenden Informationen zu jeder App.

![Screenshot der Seite "Verwaltete Apps"](media/manage-apps.png)

- **Name:** Der Name der App. Klicken Sie auf den Namen der App, um zur Seite mit den App-Details zu wechseln, um weitere Informationen zur App anzuzeigen. Dies umfasst eine Beschreibung der App, unabhängig davon, ob sie zulässig oder blockiert ist, Version, Datenschutzrichtlinien, Nutzungsbedingungen, Kategorien, die für die App gelten, Zertifizierungsstatus, unterstützte Funktionen und App-ID. Nachfolgend ein Beispiel:

  ![Screenshot der Seite "Apps-Details" für eine App](media/manage-apps-app-details.png)
  
- **Zertifizierung:** Wenn die App die Zertifizierung durchgegangen ist, wird entweder **microsoft 365** zertifiziert oder **publisher attestiert.** Klicken Sie auf den Link, um Zertifizierungsdetails für die App anzuzeigen. Wenn "" angezeigt wird, gibt **--** es keine Zertifizierungsinformationen für die App. Weitere Informationen zu zertifizierten Apps in Teams finden Sie unter Zertifizierungsprogramm für [Microsoft 365-Apps.](/teams-app-certification/all-apps)  
- **Publisher:** Name des Herausgebers.
- **Veröffentlichungsstatus:** Veröffentlichungsstatus von benutzerdefinierten Apps.
- **Status**: Status der App auf Organisationsebene, der eine der folgenden Sein kann:

    - **Zulässig:** Die App ist für alle Benutzer in Ihrer Organisation verfügbar.
    
    - **Blockiert:** Die App ist blockiert und für Keine Benutzer in Ihrer Organisation verfügbar.
    
    - **Organisationsweit blockiert:** Die App wird in organisationsweiten App-Einstellungen blockiert.
    
      Es ist wichtig zu wissen, dass diese Spalte den zulässigen und blockierten Status von Apps darstellt, die sich zuvor im **Organisationsweiten Einstellungsbereich auf dem Aktuellen Stand** hatten. Sie können apps jetzt auf der Seite Apps verwalten in der organisationsweiten Website anzeigen, **blockieren und** zulassen. 
- **Lizenzen:** Gibt an, ob eine App ein Software as a Service (SaaS)-Abonnement zum Kauf anbietet. Diese Spalte gilt nur für Apps von Drittanbietern. Jede Drittanbieter-App hat einen der folgenden Werte:
    - **Jetzt kaufen:** Die App bietet ein SaaS-Abonnement und steht zum Kauf zur Verfügung.  
    - **Gekauft:** Die App bietet ein SaaS-Abonnement, und Sie haben Lizenzen dafür erworben.
    - **- -**: Die App bietet kein SaaS-Abonnement an.
- **Benutzerdefinierte App:** Gibt an, ob es sich bei der App um eine benutzerdefinierte App handelt.
- **Berechtigungen:** Gibt an, ob eine in Azure Active Directory (Azure AD) registrierte Drittanbieter- oder benutzerdefinierte App über Berechtigungen verfügt, die zustimmungs erforderlich sind. Es wird einer der folgenden Werte angezeigt:
    - **Details anzeigen:** Die App verfügt über Berechtigungen, die eine Zustimmung erfordern, bevor die App auf Daten zugreifen kann. 
    - **- -**: Die App verfügt nicht über Berechtigungen, für die eine Zustimmung erforderlich ist.
- **Kategorien:** Kategorien, die für die App gelten.
- **Version:** App-Version.

Wenn Sie die in der Tabelle angezeigten Informationen anzeigen möchten, klicken Sie **in** der oberen rechten Ecke auf Spalte bearbeiten, um der Tabelle Spalten hinzuzufügen oder zu entfernen.

## <a name="publish-a-custom-app-to-your-organizations-app-store"></a>Veröffentlichen einer benutzerdefinierten App im App Store Ihrer Organisation

Verwenden Sie die Seite Apps verwalten, um Apps zu veröffentlichen, die speziell für Ihre Organisation entwickelt wurden. Nachdem Sie eine benutzerdefinierte App veröffentlicht haben, steht sie benutzern im App Store Ihrer Organisation zur Verfügung. Es gibt zwei Möglichkeiten, eine benutzerdefinierte App im App Store Ihrer Organisation zu veröffentlichen. Wie Sie die App verwenden, hängt davon ab, wie Sie die App erhalten.

- [Genehmigen einer benutzerdefinierten App:](#approve-a-custom-app)Verwenden Sie diese Methode, wenn der Entwickler die App direkt über die Teams App Submission API an die Seite Apps verwalten sendet. Anschließend können Sie die App direkt auf der Seite mit den App-Details überprüfen und veröffentlichen (oder ablehnen).
- [Hochladen eines App-Pakets:](#upload-an-app-package)Verwenden Sie diese Methode, wenn der Entwickler Ihnen das App-Paket im ZIP-Format sendet. Sie veröffentlichen die App, indem Sie das App-Paket hochladen.

###  <a name="approve-a-custom-app"></a>Genehmigen einer benutzerdefinierten App

Das **Widget "Ausstehende Genehmigungen"** auf der Seite Apps verwalten benachrichtigt Sie, wenn ein Entwickler eine App mithilfe der Teams-App-Übermittlungs-API übermittelt. Eine neu übermittelte App wird mit dem **Veröffentlichungsstatus** Übermittelt **und** dem **Status** Blockiert **aufgelistet.** Wechseln Sie zur Seite mit den App-Details, um weitere Informationen  zur App anzuzeigen, und legen Sie dann den Veröffentlichungsstatus auf **Veröffentlichen festlegen.**

Sie werden auch benachrichtigt, wenn ein Entwickler ein Update an eine benutzerdefinierte App sendet. Sie können das Update dann auf der Seite mit den App-Details überprüfen und veröffentlichen (oder ablehnen). Alle Richtlinien für Die App-Berechtigung und Die App-Setuprichtlinien bleiben für die aktualisierte App erzwungen.

Weitere Informationen finden Sie unter Veröffentlichen einer benutzerdefinierten App, die über die [Übermittlungs-API für Teams-Apps übermittelt wurde.](submit-approve-custom-apps.md)

### <a name="upload-an-app-package"></a>Hochladen eines App-Pakets

Der Entwickler erstellt ein Teams-App-Paket mit [Teams App Studio](/microsoftteams/platform/get-started/get-started-app-studio)und sendet es dann im ZIP-Format an Sie. Wenn Sie über das App-Paket verfügen, können Sie es in den App Store Ihrer Organisation hochladen.

Um eine neue benutzerdefinierte App hochzuladen, wählen Sie **Hochladen aus,** um das App-Paket hochzuladen. Die App wird nach dem Hochladen nicht hervorgehoben, daher müssen Sie die Liste der Apps auf der Seite Apps verwalten durchsuchen, um sie zu finden.

Wenn Sie eine App nach dem Hochladen aktualisieren möchten, klicken Sie in der Liste der Apps auf der Seite Apps verwalten auf den Namen der App, und klicken Sie dann auf **Aktualisieren.** Dadurch wird die vorhandene App ersetzt, und alle Richtlinien für App-Berechtigungsrichtlinien und App-Setup bleiben für die aktualisierte App erzwungen.

Weitere Informationen finden Sie unter [Veröffentlichen einer benutzerdefinierten App durch Hochladen eines App-Pakets.](upload-custom-apps.md)

## <a name="allow-and-block-apps"></a>Zulassen und Blockieren von Apps

Auf der Seite "Apps verwalten" können Sie einzelne Apps auf Organisationsebene zulassen oder blockieren. Es zeigt jede verfügbare App und den aktuellen App-Status auf Organisationsebene an. (Das Blockieren und Zulassen von Apps auf Organisationsebene wurde aus dem **Organisationsweiten App-Einstellungsbereich** hierher verschoben.)

Wenn Sie eine App zulassen oder blockieren möchten, wählen Sie sie aus, und klicken Sie dann auf **Zulassen** oder **Blockieren.** Wenn Sie eine App blockieren, werden alle Interaktionen mit dieser App deaktiviert, und die App wird in Teams für benutzer in Ihrer Organisation nicht angezeigt.

Wenn Sie eine App auf der Seite Apps verwalten blockieren oder zulassen, ist diese App für alle Benutzer in Ihrer Organisation blockiert oder zulässig.  Wenn Sie eine App in einer Berechtigungsrichtlinie für Teams-Apps blockieren oder zulassen, ist sie für Benutzer, denen diese Richtlinie zugewiesen ist, blockiert oder zulässig. Damit ein Benutzer apps installieren und mit ihnen interagieren kann, müssen Sie die App auf Organisationsebene auf der Seite Apps verwalten und in der Dem Benutzer zugewiesenen App-Berechtigungsrichtlinie zulassen.

 > [!NOTE]
 > Klicken Sie zum Deinstallieren einer App mit  der rechten  Maustaste auf die App, und klicken Sie dann auf Deinstallieren, oder verwenden Sie das Menü Weitere Apps auf der linken Seite.

## <a name="add-an-app-to-a-team"></a>Hinzufügen einer App zu einem Team

Sie verwenden die Schaltfläche **Zum Team hinzufügen,** um eine App in einem Team zu installieren. Denken Sie daran, dass dies nur für Apps gilt, die in einem Teambereich installiert werden können. Die **Schaltfläche Zum Team hinzufügen** ist nicht für Apps verfügbar, die nur im persönlichen Bereich installiert werden können.

![Screenshot der Schaltfläche "Zum Team hinzufügen"](media/manage-apps-add-app-team.png)

1. Suchen Sie nach der app, die Sie wünschen, und wählen Sie dann die App aus, indem Sie links vom App-Namen klicken.
2. Wählen **Sie Zum Team hinzufügen aus.**
3. Suchen Sie **im Bereich** Zum Team hinzufügen nach dem Team, dem Sie die App hinzufügen möchten, wählen Sie das Team und dann **Übernehmen aus.**

## <a name="purchase-services-for-third-party-apps"></a>Erwerben von Diensten für Apps von Drittanbietern

Sie können Lizenzen für Dienste suchen und erwerben, die von Apps von Drittanbietern für Benutzer in Ihrer Organisation angeboten werden, direkt über die Seite Apps verwalten. Die **Spalte Lizenzen** in der Tabelle gibt an, ob eine App ein kostenpflichtiges SaaS-Abonnement anbietet. Klicken **Sie auf Jetzt kaufen,** um Pläne und Preisinformationen zu sehen und Lizenzen für Ihre Benutzer zu kaufen. Weitere Informationen finden Sie unter [Erwerben von Diensten für Drittanbieter-Apps von Teams im Microsoft Teams Admin Center.](purchase-third-party-apps.md)

## <a name="grant-admin-consent-to-apps"></a>Erteilen der Zustimmung des Administrators zu Apps

Sie können Apps, die Berechtigungen für alle Benutzer in Ihrer Organisation anfordern, eine Überprüfung und Zustimmung erteilen. Sie tun dies, damit Benutzer die von der App beim Starten der App angeforderten Berechtigungen nicht überprüfen und akzeptieren müssen. In **der Spalte** Berechtigungen wird angegeben, ob eine App über Berechtigungen verfügt, die einer Zustimmung bedarf. Es wird ein Link **Details** anzeigen für jede App angezeigt, die in Azure AD registriert ist und über Berechtigungen verfügt, für die eine Zustimmung erforderlich ist. Weitere Informationen finden Sie unter [Anzeigen von App-Berechtigungen und Erteilen der Administratorberechtigung](app-permissions-admin-center.md)im Microsoft Teams Admin Center.

## <a name="view-resource-specific-consent-permissions"></a>Ressourcenspezifische Zustimmungsberechtigungen anzeigen

Ressourcenspezifische Zustimmungsberechtigungen (Resource-Specific Consent, RSC) lassen Teambesitzer die Zustimmung für eine App erteilen, um auf die Daten eines Teams zu zugreifen und diese zu ändern. RsC-Berechtigungen sind granulare, teamsspezifische Berechtigungen, die definieren, was eine App in einem bestimmten Team tun kann. Sie können RSC-Berechtigungen auf **der** Registerkarte Berechtigungen auf der Seite "App-Details" für eine App anzeigen. Weitere Informationen finden Sie unter [Anzeigen von App-Berechtigungen und Erteilen der Administratorberechtigung](app-permissions-admin-center.md)im Microsoft Teams Admin Center.

## <a name="manage-org-wide-app-settings"></a>Verwalten von organisationsweiten App-Einstellungen

Verwenden Sie organisationsweite App-Einstellungen, um zu steuern, ob Benutzer Apps von Drittanbietern installieren können und ob Benutzer benutzerdefinierte Apps in Ihrer Organisation hochladen oder mit ihnen interagieren können. Organisationsweite App-Einstellungen regeln das Verhalten für alle Benutzer und setzen alle anderen App-Berechtigungsrichtlinien, die den Benutzern zugewiesen wurden, außer Kraft. Sie können sie verwenden, um bösartige oder problematische Apps zu kontrollieren.

> [!NOTE]
> Informationen zum Verwenden organisationsweiter App-Einstellungen in Microsoft 365 Government - GCC-Bereitstellungen von Teams finden Sie unter Verwalten von [App-Berechtigungsrichtlinien in Teams.](teams-app-permission-policies.md)

1. Wählen Sie auf der Seite Apps verwalten die **Option Organisationsweite App-Einstellungen aus.** Sie können in dem Fenster dann die gewünschten Einstellungen konfigurieren.

    ![Screenshot organisationsweiter App-Einstellungen](media/manage-apps-org-wide-app-settings.png)
    
2. Aktivieren oder deaktivieren Sie unter **Drittanbieter-Apps** diese Einstellungen, um den Zugriff auf Drittanbieter-Apps zu steuern:

    - **Drittanbieter-Apps zulassen**: Steuert, ob Benutzer Drittanbieter-Apps verwenden können. Wenn Sie diese Einstellung deaktivieren, können Ihre Benutzer keine Apps von Drittanbietern installieren oder verwenden, und der App-Status dieser Apps wird **in** der Tabelle organisationsweit als blockiert angezeigt.

        > [!NOTE]
        > Wenn Apps von Drittanbietern zulassen deaktiviert **ist,** werden [ausgehende Webhooks](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) deaktiviert, was bedeutet, dass Benutzer sie nicht erstellen können. Wenn diese Einstellung aktiviert ist, werden ausgehende Webhooks für alle Benutzer aktiviert, und Sie können sie auf Benutzerebene steuern, indem Sie die Ausgehende Webhook-App über App-Berechtigungsrichtlinien zulassen oder [blockieren.](teams-app-permission-policies.md) <br><br>Beachten Sie: Wenn [](teams-app-permission-policies.md) Sie über richtlinien für  App-Berechtigungsrichtlinien für **Microsoft-Apps** verfügen, die die Einstellung Bestimmte Apps zulassen und alle anderen Blockieren verwenden, und Sie ausgehende Webhooks für Benutzer aktivieren möchten, fügen Sie der Liste die Postausgangs-Webhook-App hinzu.
    - **Alle neuen Drittanbieter-Apps, die im Store veröffentlicht werden, standardmäßig zulassen**: Steuert, ob neue Drittanbieter-Apps, die im Teams-App-Store veröffentlicht werden, automatisch in Teams verfügbar gemacht werden. Sie können diese Option nur aktivieren, wenn Sie Drittanbieter-Apps zulassen.

3. Deaktivieren **oder aktivieren** Sie unter Benutzerdefinierte Apps die Interaktion mit **benutzerdefinierten Apps zulassen.** Diese Einstellung steuert, ob Benutzer mit benutzerdefinierten Apps interagieren können. Weitere Informationen finden Sie unter [Verwalten von benutzerdefinierten App-Richtlinien und Einstellungen in Teams](teams-custom-app-policies-and-settings.md).
4. Klicken Sie auf **Speichern**, damit die organisationsweiten App-Einstellungen wirksam werden.

## <a name="customize-an-app-in-preview"></a>Anpassen einer App (in der Vorschau)

Sie können jetzt eine App anpassen, um ein bestimmtes Erscheinungsbild entsprechend den Anforderungen Ihrer Organisation zu erhalten. [Anpassen von Apps in Teams](customize-apps.md)

## <a name="related-topics"></a>Verwandte Themen

- [Administratoreinstellungen für Apps in Microsoft Teams](admin-settings.md)