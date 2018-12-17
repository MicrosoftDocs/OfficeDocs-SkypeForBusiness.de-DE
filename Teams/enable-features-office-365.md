---
title: Verwalten von Microsoft Teams-Funktionen in Ihrer Office 365-Organisation
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/29/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
search.appverid: MET150
description: Hier erfahren Sie, wie Sie in Ihrer Office 365-Organisation Microsoft Teams-Apps einschließlich Registerkarten, Connectors, Bots oder einer Kombination aus diesen drei Komponenten aktivieren bzw. deaktivieren.
localization_priority: Priority
ms.custom:
- NewAdminCenter_Update
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: da071250eb45fbad9e83b2d79d6e86166072a474
ms.sourcegitcommit: 1ad4120af98240f1b54c0ca18286598b289a97f1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/12/2018
ms.locfileid: "27240693"
---
# <a name="manage-microsoft-teams-features-in-your-office-365-organization"></a>Verwalten von Microsoft Teams-Funktionen in Ihrer Office 365-Organisation

Alle Teams-Einstellungen werden in Kürze zum neuen Admin Center für Microsoft Teams und Skype for Business migriert. Apps werden als einzige Teams-Funktion im Office 365 Admin Center verwaltet. 

Wenn nichts anderes angegeben ist, lautet der Standardwert für die jeweilige Option **Ein**.

## <a name="office-365-tenant-wide-settings"></a>Mandantenweite Einstellungen in Office 365 

Unter **Mandantenweite Einstellungen** können Sie Apps aktivieren oder deaktivieren.

Zum Bearbeiten der **mandantenweiten Einstellungen** für Microsoft Teams wechseln Sie zum Admin Center für Microsoft Teams und Skype for Business. Wählen Sie **Legacy portal** (Legacyportal) aus. Wählen Sie **Einstellungen** > **Dienste und Add-Ins** > **Microsoft Teams** aus. Wenn Sie als Office 365-Administrator angemeldet sind, können Sie diesen Link verwenden: 
>  
> https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns  

### <a name="apps"></a>Apps

Apps sind Registerkarten, Connectors und Bots bzw. eine beliebige Kombination dieser drei Elemente, die von einem Drittanbieterdienst bereitgestellt werden. Im Office 365 Admin Center können Microsoft Teams-Administratorrichtlinien konfiguriert werden, um zu steuern, welche externen Drittanbieter-Apps zulässig sind. Mit diesen Richtlinien können Sie festlegen, welche Apps zulässig bzw. nicht zulässig sind, das Verhalten neuer externer Apps definieren und angeben, ob das Querladen von Apps zulässig ist. 

Unter **Apps** können Sie die folgenden Einstellungen für Ihre Organisation konfigurieren: 

![Screenshot des Abschnitts „Apps“](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.png)

- **Allow external apps in Microsoft Teams** (Externe Apps in Microsoft Teams zulassen): Wenn diese Option aktiviert ist, können Benutzer Registerkarten und Bots hinzufügen, die für den Office 365-Mandanten verfügbar sind. 
 
    ![Screenshot des Steuerelements zum Zulassen externer Apps im Abschnitt „Apps“](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.2.png)

- **Enable new external apps by default** (Neue externe Apps standardmäßig aktivieren): Wenn diese Option aktiviert ist, können Benutzer neue Apps aktivieren, sobald diese zum Microsoft Teams-App-Katalog hinzugefügt werden. Deaktivieren Sie diese Option, wenn Sie neue Apps steuern möchten. Wenn Sie die Option deaktiviert haben, müssen Sie natürlich daran denken, neue Apps regelmäßig zu überprüfen, damit Ihrer Organisation keine tollen neuen Apps entgehen. 

- **Querladen externer Apps zulassen**: Wenn diese Option aktiviert ist, können Benutzer benutzerdefinierte Bots und Registerkarten installieren und aktivieren. 

Weitere Informationen finden Sie unter [Administratoreinstellungen für Apps in Microsoft Teams](admin-settings.md). 

## <a name="teams-org-wide-settings"></a>Organisationsweite Einstellungen für Microsoft Teams

Sie können organisationsweite Benutzereinstellungen im Admin Center für Microsoft Teams und Skype for Business steuern. Zum Bearbeiten der organisationsweiten Einstellungen wechseln Sie zum Admin Center für Microsoft Teams und Skype for Business. Wählen Sie **Org-wide settings** (Organisationsweite Einstellungen) aus. Sie können die folgenden Einstellungen konfigurieren:

### <a name="external-access"></a>Externer Zugriff

**Externer Zugriff** ermöglicht Ihren Microsoft Teams- und Skype for Business-Benutzern die Kommunikation mit Benutzern außerhalb der Organisation. Um den externen Zugriff zu konfigurieren, wechseln Sie zu [Let your Teams users chat and communicate with users in another Teams organization](let-your-teams-users-communicate-with-other-people.md) (Microsoft Teams-Benutzern das Chatten und Kommunizieren mit Benutzern in einer anderen Microsoft Teams-Organisation ermöglichen).

### <a name="guest-access"></a>Gastzugriff

**Gastzugriff** in Microsoft Teams ermöglicht Teams in Ihrer Organisation, mit Personen außerhalb der Organisation zusammenzuarbeiten, indem ihnen Zugriff auf Teams und Kanäle gewährt wird. Alle Benutzer, die über ein E-Mail-Konto für Geschäftsbenutzer oder Heimanwender (z. B. Outlook, Gmail usw.) verfügen, können als Gäste in Microsoft Teams teilnehmen und erhalten Vollzugriff auf Chats, Besprechungen und Dateien des Teams. Weitere Informationen finden Sie unter [Gastzugriff in Microsoft Teams](guest-access.md).

### <a name="teams-settings"></a>„Teams settings“ (Microsoft Teams-Einstellungen)

Unter **Teams settings** (Microsoft Teams-Einstellungen) können Sie E-Mail-Integration, Cloudspeicheroptionen, Interoperabilität mit Skype for Business und Geräte einrichten.

#### <a name="email-integration"></a>E-Mail-Integration

Aktivieren Sie diese Funktion, damit Benutzer über die Kanal-E-Mail-Adresse eine E-Mail an einen Kanal in Microsoft Teams senden können. Benutzer können dies für jeden Kanal tun, der zu einem Team gehört, dessen Besitzer sie sind. Außerdem können Benutzer E-Mails an jeden Kanal in einem Team senden, in dem das Hinzufügen von Connectors für Teammitglieder aktiviert ist. Stellen Sie zum Aktivieren der E-Mail-Integration sicher, dass für **Allow users to send emails to a channel email address** (Zulassen, dass Benutzer E-Mails an eine Kanal-E-Mail-Adresse senden) die Option **Ein** festgelegt ist. 

#### <a name="files"></a>Dateien

Hier können Sie die Dateifreigabe und Optionen für Cloudspeicherdateien aktivieren oder deaktivieren. 

Benutzer können Dateien aus Cloudspeicherdiensten in Microsoft Teams-Kanäle und -Chats hochladen und dort freigeben. Zu den Cloudspeicheroptionen in Microsoft Teams gehören zurzeit ShareFile, Dropbox, Box und Google Drive. Aktivieren Sie die Option für die Cloudspeicheranbieter, die Ihre Organisation verwenden möchte.

#### <a name="organization"></a>Organisation

Hier können Sie die Registerkarte **Organisation** aktivieren, auf der das detaillierte Organigramm für die Organisation des Benutzers angezeigt wird. Weitere Informationen finden Sie unter [Verwenden der Registerkarte „Organisation“ in Microsoft Teams](https://support.office.com/article/use-the-organization-tab-in-teams-ff02568b-290a-46d6-ae7a-cda22f723894).

#### <a name="skype-for-business-interop"></a>„Skype for Business interop“ (Interoperabilität mit Skype for Business)

Verwenden Sie diese Einstellung, um Microsoft Teams-Benutzern das Chatten mit Skype for Business-Benutzern zu ermöglichen. Detaillierte Informationen zur Interoperabilität zwischen Microsoft Teams und Skype for Business finden Sie unter [Grundlegendes zur Koexistenz und Interoperabilität von Skype for Business und Microsoft Teams](teams-and-skypeforbusiness-coexistence-and-interoperability.md).

#### <a name="devices"></a>Geräte

Diese Einstellungen steuern das Verhalten von Ressourcenkonten für Surface Hub-Geräte, die an Microsoft Teams-Besprechungen teilnehmen. Verwenden Sie diese Einstellungen, um Authentifizierungsanforderungen zu konfigurieren, festzulegen, dass eine Inhalts-PIN erforderlich ist, und das Senden von Nachrichten durch Surface Hub-Ressourcenkonten zu aktivieren.

- **Require a secondary form of authentication to access meeting content** (Für den Zugriff auf Besprechungsinhalte ist eine sekundäre Authentifizierungsmethode erforderlich): Wählen Sie die Zugriffsebene aus, über die Benutzer verfügen, wenn sie die Inhalts-PIN eingeben.
- **Set content PIN** (Inhalts-PIN festlegen): Legen Sie fest, dass Benutzer diese PIN eingeben müssen, damit der nicht autorisierte Zugriff auf Dokumente nicht möglich ist. Damit verhindern Sie, dass nicht autorisierte Benutzer an bevorstehenden Besprechungen teilnehmen und Anlagen durchsuchen.
- **Resource accounts can send messages** (Ressourcenkonten können Nachrichten senden): Legen Sie diese Einstellung auf **Ein** fest, um das Senden von Nachrichten über das Surface Hub-Ressourcenkonto zuzulassen.

#### <a name="search"></a>Suche

Die Verzeichnissuche in Microsoft Teams verwendet Exchange-Adressbuchrichtlinien, damit Organisationen virtuelle Grenzen erstellen können. Diese steuern, wie Benutzer andere Benutzer in der Organisation suchen und mit diesen kommunizieren können. Eine bereichsbezogene Verzeichnissuche eignet sich zum Beispiel in diesen Situationen:

- Der Mandant Ihrer Organisation enthält mehrere Unternehmen, die voneinander getrennt sein sollen. 
- Ihre Bildungseinrichtung möchte Chats zwischen dem Lehrpersonal und den Kursteilnehmern begrenzen. 

Ändern Sie diese Einstellung in **Ein**, um die bereichsbezogene Verzeichnissuche zu aktivieren.

### <a name="teams-upgrade"></a>„Teams upgrade“ (Microsoft Teams-Upgrade)

Mit diesen Einstellungen können Sie konfigurieren, wie die Benutzer von Skype for Business auf Microsoft Teams aktualisiert werden. 

#### <a name="coexistence-mode"></a>Koexistenzmodus
Sie können einen Koexistenzmodus angeben: **Teams only** (Nur Microsoft Teams), **Inseln** (Microsoft Teams und Skype for Business werden zusammen verwendet) oder **Skype for Business only** (Nur Skype for Business). Der ausgewählte Koexistenzmodus bestimmt, wie eingehende Anrufe und Chats weitergeleitet werden und welche App die Benutzer zum Einleiten von Chats und Anrufen oder zum Planen von Besprechungen verwenden. Detaillierte Informationen zu Koexistenzmodi finden Sie unter [Grundlegendes zur Koexistenz und Interoperabilität von Skype for Business und Microsoft Teams](teams-and-skypeforbusiness-coexistence-and-interoperability.md).

#### <a name="app-preferences"></a>„App preferences“ (App-Einstellungen)

Hier können Sie die App auswählen, die Benutzer für die Teilnahme an Skype for Business-Besprechungen verwenden (Skype for Business oder die [Skype-Besprechungs-App](https://support.office.com/en-us/article/What-is-Skype-Meetings-App-Skype-for-Business-Web-App-1FF3D412-718A-4982-8FF2-A4992608CDB5)). Diese Einstellung ist nicht von der Einstellung für den Koexistenzmodus abhängig.

## <a name="how-can-i-tell-which-features-are-available"></a>Woran erkenne ich, welche Funktionen verfügbar sind?

In der [Office 365-Roadmap](https://www.microsoft.com/en-us/microsoft-365/roadmap?rtc=1&filters=Microsoft%20Teams) finden Sie Informationen zu neuen Microsoft Teams-Funktionen. Weitere Informationen zu neuen und geplanten Funktionen finden Sie in Microsoft Teams auf der Seite [Neuigkeiten](https://support.office.com/en-us/article/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de?ui=en-US&rs=en-US&ad=US) und im [Microsoft Teams-Blog der Tech Community](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/What-s-new-in-Teams-Microsoft-Ignite-Edition/ba-p/252531). 

## <a name="more-information"></a>Weitere Informationen

Weitere Informationen dazu, welche Rollen Administratorfunktionen ausführen können, finden Sie unter [Verwenden der Microsoft Teams-Administratorrollen zum Verwalten von Microsoft Teams](using-admin-roles.md).
