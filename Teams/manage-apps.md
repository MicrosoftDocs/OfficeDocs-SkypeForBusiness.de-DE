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
ms.openlocfilehash: 3a79f25e9f260e798ec6e0456cacf6ba2dfe618b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822905"
---
<a name="manage-your-apps-in-the-microsoft-teams-admin-center"></a>Verwalten Ihrer Apps im Microsoft Teams Admin Center
======================================================

Als Administrator können Sie auf der Seite "Apps verwalten" im Microsoft Teams Admin Center alle Teams-Apps für Ihre Organisation anzeigen und verwalten. Hier können Sie den Status und die Eigenschaften von Apps auf Organisationsebene anzeigen, neue benutzerdefinierte Apps im App Store Ihrer Organisation genehmigen oder hochladen, Apps auf Organisationsebene blockieren oder zulassen, Apps zu Teams hinzufügen, Dienste für Apps von Drittanbietern kaufen, von Apps angeforderte Berechtigungen anzeigen, Administratorzuteilung für Apps erteilen und organisationsweite App-Einstellungen verwalten.

Auf der Seite "Apps verwalten" erhalten Sie einen Einblick in alle verfügbaren Apps und erhalten die Informationen, die Sie benötigen, um zu entscheiden, welche Apps in der gesamten Organisation zulässig oder blockiert werden müssen. Anschließend können Sie Berechtigungsrichtlinien für [Apps,](teams-app-permission-policies.md) [Richtlinien](teams-app-setup-policies.md)für die Einrichtung von Apps und benutzerdefinierte App-Richtlinien und -Einstellungen verwenden, um die Benutzererfahrung der App für bestimmte Benutzer in Ihrer Organisation zu konfigurieren. [](teams-custom-app-policies-and-settings.md)

Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **"Apps**  >  **verwalten".** Sie müssen ein globaler Administrator oder ein Teams-Dienstadministrator sein, um auf die Seite zugreifen zu können.

> [!NOTE]
> Die Seite "Apps verwalten" ist in Microsoft 365 Government Community Cloud (GCC)-Bereitstellungen von Teams noch nicht verfügbar.

## <a name="view-apps"></a>Anzeigen von Apps

Sie können jede App anzeigen, einschließlich der folgenden Informationen zu jeder App.

![Screenshot der Seite "Verwaltete Apps"](media/manage-apps.png)

- **Name:** Der App-Name. Klicken Sie auf den App-Namen, um zur Detailseite der App zu wechseln, um weitere Informationen zur App anzuzeigen. Dazu gehört eine Beschreibung der App, ob sie zulässig oder blockiert ist, Version, Datenschutzrichtlinie, Nutzungsbedingungen, Kategorien, die für die App gelten, Zertifizierungsstatus, unterstützte Funktionen und App-ID. Nachfolgend ein Beispiel:

  ![Screenshot der Seite "Apps-Details" für eine App](media/manage-apps-app-details.png)
  
- **Zertifizierung:** Wenn die App die Zertifizierung durchgegangen ist, wird entweder ein **Microsoft 365-zertifizierungs-** oder ein **Publisher-Nachweis angezeigt.** Klicken Sie auf den Link, um Zertifizierungsdetails für die App anzuzeigen. Wenn "" angezeigt wird, gibt **--** es keine Zertifizierungsinformationen für die App. Weitere Informationen zu zertifizierten Apps in Teams finden Sie im [Microsoft 365-App-Zertifizierungsprogramm.](https://docs.microsoft.com/teams-app-certification/all-apps)  
- **Herausgeber:** Name des Herausgebers.
- **Veröffentlichungsstatus:** Veröffentlichungsstatus von benutzerdefinierten Apps.
- **Status:** Status der App auf Organisationsebene, der eine der folgenden sein kann:

    - **Zulässig:** Die App ist für alle Benutzer in Ihrer Organisation verfügbar.
    
    - **Blockiert:** Die App ist blockiert und für keine Benutzer in Ihrer Organisation verfügbar.
    
    - **Organisationsweit blockiert:** Die App wird in organisationsweiten App-Einstellungen blockiert.
    
      Es ist wichtig zu wissen, dass diese Spalte den zulässigen und blockierten Status von Apps darstellt, die sich zuvor im **organisationsweiten Einstellungsbereich** hatten. Sie können Apps jetzt organisationsweit auf der Seite "Apps **verwalten"** anzeigen, blockieren und zulassen. 
- **Lizenzen:** Gibt an, ob eine App ein Software as a Service (SaaS)-Abonnement zum Kauf anbietet. Diese Spalte gilt nur für Apps von Drittanbietern. Jede Drittanbieter-App hat einen der folgenden Werte:
    - **Jetzt kaufen:** Die App bietet ein SaaS-Abonnement und ist zum Kauf verfügbar.  
    - **Gekauft:** Die App bietet ein SaaS-Abonnement, und Sie haben Lizenzen dafür erworben.
    - **–**: Die App bietet kein SaaS-Abonnement an.
- **Benutzerdefinierte App:** Gibt an, ob es sich bei der App um eine benutzerdefinierte App handelt.
- **Berechtigungen:** Gibt an, ob ein Drittanbieter oder eine benutzerdefinierte App, die in Azure Active Directory (Azure AD) registriert ist, über Berechtigungen verfügt, für die eine Zustimmung erforderlich ist. Es wird einer der folgenden Werte angezeigt:
    - **Details anzeigen:** Die App verfügt über Berechtigungen, für die eine Zustimmung erforderlich ist, bevor die App auf Daten zugreifen kann. 
    - **–**: Die App verfügt nicht über Berechtigungen, für die eine Zustimmung erforderlich ist.
- **Kategorien:** Kategorien, die für die App gelten.
- **Version:** App-Version.

Wenn Sie die Informationen anzeigen möchten, die in der Tabelle enthalten sein sollen, klicken Sie **in** der oberen rechten Ecke auf "Spalte bearbeiten", um der Tabelle Spalten hinzuzufügen oder spalten zu entfernen.

## <a name="publish-a-custom-app-to-your-organizations-app-store"></a>Veröffentlichen einer benutzerdefinierten App im App Store Ihrer Organisation

Verwenden Sie die Seite "Apps verwalten", um speziell für Ihre Organisation entwickelte Apps zu veröffentlichen. Nachdem Sie eine benutzerdefinierte App veröffentlicht haben, steht sie Benutzern im App Store Ihrer Organisation zur Verfügung. Es gibt zwei Möglichkeiten, eine benutzerdefinierte App im App Store Ihrer Organisation zu veröffentlichen. Die Verwendung hängt davon ab, wie Sie die App erhalten.

- [Genehmigen einer benutzerdefinierten](#approve-a-custom-app)App: Verwenden Sie diese Methode, wenn der Entwickler die App mithilfe der Teams-App-Übermittlungs-API direkt an die Seite "Apps verwalten" übermittelt. Anschließend können Sie die App direkt über die Detailseite der App überprüfen und veröffentlichen (oder ablehnen).
- [Hochladen eines App-Pakets:](#upload-an-app-package)Verwenden Sie diese Methode, wenn Ihnen der Entwickler das Paket im ZIP-Format sendet. Sie veröffentlichen die App durch Hochladen des App-Pakets.

###  <a name="approve-a-custom-app"></a>Genehmigen einer benutzerdefinierten App

Das **Widget "Ausstehende Genehmigungen"** auf der Seite "Apps verwalten" benachrichtigt Sie, wenn ein Entwickler eine App mithilfe der Teams-App-Übermittlungs-API übermittelt. Eine neu übermittelte App wird mit dem **Veröffentlichungsstatus** **"Übermittelt"** und dem **Status "Blockiert"** **aufgeführt.** Wechseln Sie zur Seite mit den App-Details, um weitere Informationen  zu der App anzuzeigen, und legen Sie dann zum Veröffentlichen den Veröffentlichungsstatus auf **"Veröffentlichen" festgelegt.**

Sie werden auch benachrichtigt, wenn ein Entwickler ein Update an eine benutzerdefinierte App übermittelt. Anschließend können Sie das Update auf der Detailseite der App überprüfen und veröffentlichen (oder ablehnen). Alle Berechtigungsrichtlinien und Richtlinien für das Einrichten von Apps bleiben für die aktualisierte App erzwungen.

Weitere Informationen finden Sie unter ["Veröffentlichen einer benutzerdefinierten App, die über die Übermittlungs-API für Teams-Apps übermittelt wird".](submit-approve-custom-apps.md)

### <a name="upload-an-app-package"></a>Hochladen eines App-Pakets

Der Entwickler erstellt mithilfe von Teams App Studio ein [Teams-App-Paket](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)und sendet es ihnen dann im ZIP-Format. Wenn Sie über das App-Paket verfügen, können Sie es in den App Store Ihrer Organisation hochladen.

Wenn Sie eine neue benutzerdefinierte App hochladen möchten, wählen Sie **"Hochladen" aus,** um das App-Paket hochzuladen. Da die App nach dem Hochladen nicht hervorgehoben wird, müssen Sie die Liste der Apps auf der Seite "Apps verwalten" durchsuchen, um sie zu finden.

Wenn Sie eine App nach dem Hochladen aktualisieren möchten, klicken Sie in der Liste der Apps auf der Seite "Apps verwalten" auf den Namen der App, und klicken Sie dann auf **"Aktualisieren".** Dadurch werden die vorhandenen App ersetzt, und alle Berechtigungsrichtlinien und Richtlinien für das Einrichten von Apps bleiben für die aktualisierte App erzwungen.

Weitere Informationen finden Sie unter ["Veröffentlichen einer benutzerdefinierten App durch Hochladen eines App-Pakets".](upload-custom-apps.md)

## <a name="allow-and-block-apps"></a>Zulassen und Blockieren von Apps

Auf der Seite "Apps verwalten" können Sie einzelne Apps auf Organisationsebene zulassen oder blockieren. Sie zeigt alle verfügbaren Apps und den aktuellen Status der App auf Organisationsebene an. (Das Blockieren und Zulassen von Apps auf Organisationsebene wurde aus dem **organisationsweiten** Einstellungsbereich der App nach hier verschoben.)

Wenn Sie eine App zulassen oder blockieren möchten, wählen Sie sie aus, und klicken Sie dann auf **"Zulassen"** oder **"Blockieren".** Wenn Sie eine App blockieren, werden alle Interaktionen mit dieser App deaktiviert, und die App wird in Teams für keine Benutzer in Ihrer Organisation angezeigt.

Wenn Sie eine App auf der Seite "Apps verwalten" blockieren oder zulassen, ist diese App für alle Benutzer in Ihrer Organisation blockiert oder zulässig.  Wenn Sie eine App in einer Berechtigungsrichtlinie für eine Teams-App blockieren oder zulassen, ist sie für Benutzer, denen diese Richtlinie zugewiesen ist, blockiert oder zulässig. Damit ein Benutzer eine beliebige App installieren und damit interagieren kann, müssen Sie die App auf Organisationsebene auf der Seite "Apps verwalten" und in der dem Benutzer zugewiesenen Berechtigungsrichtlinie zulassen.

 > [!NOTE]
 > Wenn Sie eine App deinstallieren möchten, klicken  Sie mit  der rechten Maustaste auf die App, und klicken Sie dann auf "Deinstallieren", oder verwenden Sie das Menü "Weitere Apps" auf der linken Seite.

## <a name="add-an-app-to-a-team"></a>Hinzufügen einer App zu einem Team

Sie verwenden die Schaltfläche **"Zu Team hinzufügen",** um eine App für ein Team zu installieren. Beachten Sie, dass dies nur für Apps gilt, die in einem Teambereich installiert werden können. Die **Schaltfläche "Zu Team hinzufügen"** steht für Apps, die nur im persönlichen Bereich installiert werden können, nicht zur Verfügung.

![Screenshot der Schaltfläche "Zum Team hinzufügen"](media/manage-apps-add-app-team.png)

1. Suchen Sie nach der App, und wählen Sie die App aus, indem Sie links des Namen der App klicken.
2. Wählen Sie **"Zum Team hinzufügen" aus.**
3. Suchen Sie **im Bereich "Zu** Team hinzufügen" nach dem Team, dem Sie die App hinzufügen möchten, wählen Sie das Team und dann "Übernehmen" **aus.**

## <a name="purchase-services-for-third-party-apps"></a>Dienste für Apps von Drittanbietern kaufen

Sie können lizenzen für Dienste, die von Apps von Drittanbietern für Benutzer in Ihrer Organisation angeboten werden, direkt über die Seite "Apps verwalten" suchen und kaufen. Die **Spalte "Lizenzen"** in der Tabelle gibt an, ob eine App ein kostenpflichtiges SaaS-Abonnement bietet. Klicken **Sie auf "Jetzt kaufen",** um Pläne und Preisinformationen anzeigen und Lizenzen für Ihre Benutzer zu kaufen. Weitere Informationen finden Sie unter "Dienste für [Microsoft Teams-Drittanbieter-Apps kaufen" im Microsoft Teams Admin Center.](purchase-third-party-apps.md)

## <a name="grant-admin-consent-to-apps"></a>Erteilen der Administratorzusendung für Apps

Sie können Apps, die Berechtigungen für alle Benutzer in Ihrer Organisation anfordern, eine Überprüfung und Zustimmung erteilen. Dadurch müssen benutzer beim Starten der App die von der App angeforderten Berechtigungen nicht überprüfen und akzeptieren. In **der Spalte** "Berechtigungen" wird angegeben, ob eine App über Berechtigungen verfügt, für die eine Zustimmung erforderlich ist. Es wird ein Link **"Details** anzeigen" für jede app angezeigt, die in Azure AD registriert ist und über Berechtigungen verfügt, die eine Zustimmung benötigen. Weitere Informationen finden Sie unter "Anzeigen [von App-Berechtigungen" und Erteilen der Administratorzusberechtigung im Microsoft Teams Admin Center.](app-permissions-admin-center.md)

## <a name="view-resource-specific-consent-permissions"></a>Ressourcenspezifische Zustimmungsberechtigungen anzeigen

Mit ressourcenspezifischen Zustimmungsberechtigungen (RSC) können Teambesitzer einer App die Zustimmung zum Zugreifen auf und Ändern von Teamdaten erteilen. RsC-Berechtigungen sind granulare, Teams-spezifische Berechtigungen, die definieren, was eine App in einem bestimmten Team tun kann. Sie können die Berechtigung "RSC" auf **der** Registerkarte "Berechtigungen" auf der Seite mit den App-Details für eine App anzeigen. Weitere Informationen finden Sie unter "Anzeigen [von App-Berechtigungen" und Erteilen der Administratorzusberechtigung im Microsoft Teams Admin Center.](app-permissions-admin-center.md)

## <a name="manage-org-wide-app-settings"></a>Verwalten von organisationsweiten App-Einstellungen

Verwenden Sie organisationsweite App-Einstellungen, um zu steuern, ob Benutzer Apps von Drittanbietern installieren können und ob Benutzer benutzerdefinierte Apps in Ihrer Organisation hochladen oder damit interagieren können. Organisationsweite App-Einstellungen steuern das Verhalten aller Benutzer und setzen alle anderen Benutzerberechtigungsrichtlinien für Apps außer Kraft. Sie können damit schädliche oder problematische Apps steuern.

> [!NOTE]
> Informationen zum Verwenden von organisationsweiten App-Einstellungen in Microsoft 365 Government - GCC-Bereitstellungen von Teams finden Sie unter "Verwalten von Richtlinien für App-Berechtigung [in Teams".](teams-app-permission-policies.md)

1. Wählen Sie auf der Seite "Apps verwalten" **die organisationsweiten App-Einstellungen aus.** Anschließend können Sie die im Bereich angezeigten Einstellungen konfigurieren.

    ![Screenshot der organisationsweiten App-Einstellungen](media/manage-apps-org-wide-app-settings.png)
    
2. Deaktivieren **oder aktivieren Sie unter "Apps** von Drittanbietern" diese Einstellungen, um den Zugriff auf Apps von Drittanbietern zu steuern:

    - **Apps von Drittanbietern zulassen:** Damit wird bestimmt, ob Benutzer Apps von Drittanbietern verwenden können. Wenn Sie diese Einstellung deaktivieren, können Ihre Benutzer keine Apps von Drittanbietern installieren oder verwenden, und der Status dieser Apps wird **in** der Tabelle organisationsweit als blockiert angezeigt.

        > [!NOTE]
        > Wenn **"Apps von Drittanbietern zulassen"** deaktiviert ist, werden [ausgehende Webhooks](https://docs.microsoft.com/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) deaktiviert, was bedeutet, dass Benutzer sie nicht erstellen können. Wenn diese Einstellung aktiviert ist, sind ausgehende Webhooks für alle Benutzer aktiviert, und Sie können sie auf Benutzerebene steuern, indem Sie die ausgehende Webhook-App über Berechtigungsrichtlinien für Apps zulassen oder [blockieren.](teams-app-permission-policies.md) <br><br>Beachten Sie: Wenn [](teams-app-permission-policies.md) Sie über vorhandene Berechtigungsrichtlinien für Apps für **Microsoft-Apps** verfügen, die die Einstellung "Bestimmte Apps zulassen" verwenden und alle anderen Einstellungen blockieren, und Sie ausgehende Webhooks für Benutzer aktivieren möchten, fügen Sie die ausgehende Webhook-App zur Liste hinzu. 
    - **Standardmäßig alle neuen Apps** von Drittanbietern zulassen, die im Store veröffentlicht werden: Mit dieser Steuerung wird festgelegt, ob neue Apps von Drittanbietern, die im Teams App Store veröffentlicht werden, automatisch in Teams verfügbar werden. Sie können diese Option nur festlegen, wenn Sie Apps von Drittanbietern zulassen.

3. Deaktivieren **oder aktivieren** Sie unter "Benutzerdefinierte Apps" die "Interaktion mit **benutzerdefinierten Apps zulassen".** Diese Einstellung steuert, ob Benutzer mit benutzerdefinierten Apps interagieren können. Weitere Informationen finden Sie unter "Verwalten von Richtlinien und Einstellungen [für benutzerdefinierte Apps in Teams".](teams-custom-app-policies-and-settings.md)
4. Klicken **Sie auf "Speichern** für organisationsweite App-Einstellungen", um sie wirksam zu machen.

## <a name="related-topics"></a>Verwandte Themen

- [Administratoreinstellungen für Apps in Microsoft Teams](admin-settings.md)