---
title: Verwalten von Microsoft Teams-Einstellungen in Ihrer Organisation
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: ritikag
search.appverid: MET150
description: Erfahren Sie, wie Sie unternehmensweite Microsoft Teams-Einstellungen für Ihre Organisation aktivieren oder deaktivieren, einschließlich Apps, externem Zugriff, Gastzugriff, Teams-Einstellungen und Teams-Aktualisierungseinstellungen.
localization_priority: Priority
ms.custom:
- NewAdminCenter_Update
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 596c3a3df6fc29706eea083859c65e1b1381e9ea
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235348"
---
# <a name="manage-microsoft-teams-settings-for-your-organization"></a>Verwalten von Microsoft Teams-Einstellungen in Ihrer Organisation

## <a name="teams-apps-settings-in-the-microsoft-teams-admin-center"></a>Einstellungen von Teams-Apps im Admin Center für Microsoft Teams

Sie verwalten Apps für Ihre Organisation in **Teams-Apps** im Microsoft Teams Admin Center. Sie können z. B. Richtlinien festlegen, um zu steuern, welche Apps organisationsweit oder für bestimmte Microsoft Teams-Benutzer verfügbar sind, und Sie können Microsoft Teams anpassen, indem Sie die Apps anheften, die für Ihre Benutzer am wichtigsten sind.

Weitere Informationen finden Sie unter [Administratoreinstellungen für Apps in Microsoft Teams](admin-settings.md).  

## <a name="teams-org-wide-settings-in-the-microsoft-teams-admin-center"></a>Unternehmensweite Teams-Einstellungen im Admin Center für Microsoft Teams

Sie können organisationsweite Benutzereinstellungen im Microsoft Teams Admin Center steuern. Um organisationsweite Einstellungen zu bearbeiten, gehen Sie zum Microsoft Teams Admin Center, und wählen Sie dann **Organisationsweite Einstellungen** aus. Sie können die folgenden Einstellungen konfigurieren.

### <a name="external-access"></a>Externer Zugriff

**Externer Zugriff** ermöglicht Ihren Microsoft Teams- und Skype for Business-Benutzern die Kommunikation mit Benutzern außerhalb der Organisation oder Domäne. Um den externen Zugriff zu konfigurieren, wechseln Sie zu [Microsoft Teams-Benutzern das Chatten und Kommunizieren mit Benutzern in einer anderen Microsoft Teams-Organisation ermöglichen](let-your-teams-users-communicate-with-other-people.md).

Hinzufügen oder Sperren einer Domäne:

1. Wählen Sie **Domäne hinzufügen**.
2. Geben Sie im Bereich „Domäne hinzufügen“ den Domänennamen ein, und drücken Sie die LEERTASTE, um den Namen zu speichern.
3. Wählen Sie **Zulässig** oder **Blockiert**.
4. Wählen Sie **Fertig** aus, um die Änderungen zu speichern. 

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

#### <a name="devices"></a>Geräte

Diese Einstellungen steuern das Verhalten von Ressourcenkonten für Surface Hub-Geräte, die an Microsoft Teams-Besprechungen teilnehmen. Verwenden Sie diese Einstellungen, um Authentifizierungsanforderungen zu konfigurieren, festzulegen, dass eine Inhalts-PIN erforderlich ist, und das Senden von Nachrichten durch Surface Hub-Ressourcenkonten zu aktivieren.

- **Require a secondary form of authentication to access meeting content** (Für den Zugriff auf Besprechungsinhalte ist eine sekundäre Authentifizierungsmethode erforderlich): Wählen Sie die Zugriffsebene aus, über die Benutzer verfügen, wenn sie die Inhalts-PIN eingeben.
- **Set content PIN** (Inhalts-PIN festlegen): Legen Sie fest, dass Benutzer diese PIN eingeben müssen, damit der nicht autorisierte Zugriff auf Dokumente nicht möglich ist. Damit verhindern Sie, dass nicht autorisierte Benutzer an bevorstehenden Besprechungen teilnehmen und Anlagen durchsuchen.
- **Resource accounts can send messages** (Ressourcenkonten können Nachrichten senden): Legen Sie diese Einstellung auf **Ein** fest, um das Senden von Nachrichten über das Surface Hub-Ressourcenkonto zuzulassen.

#### <a name="search-by-name"></a>Nach Name suchen

Die Verzeichnissuche in Microsoft Teams verwendet Exchange-Adressbuchrichtlinien, damit Organisationen virtuelle Grenzen erstellen können. Diese steuern, wie Benutzer andere Benutzer in der Organisation suchen und mit diesen kommunizieren können. Eine bereichsbezogene Verzeichnissuche eignet sich zum Beispiel in diesen Situationen:

- Der Mandant Ihrer Organisation enthält mehrere Unternehmen, die voneinander getrennt sein sollen. 
- Ihre Bildungseinrichtung möchte Chats zwischen dem Lehrpersonal und den Kursteilnehmern begrenzen. 

Ändern Sie diese Einstellung in **Ein**, um die bereichsbezogene Verzeichnissuche zu aktivieren.

### <a name="teams-upgrade"></a>„Teams upgrade“ (Microsoft Teams-Upgrade)

Mit diesen Einstellungen können Sie konfigurieren, wie die Benutzer von Skype for Business auf Microsoft Teams aktualisiert werden. 

#### <a name="coexistence-mode"></a>Koexistenzmodus
Sie können einen Koexistenzmodus angeben: **Nur Microsoft Teams**, **Inseln** (Microsoft Teams und Skype for Business werden zusammen verwendet) oder **Nur Skype for Business**. Der ausgewählte Koexistenzmodus bestimmt, wie eingehende Anrufe und Chats weitergeleitet werden und welche App die Benutzer zum Einleiten von Chats und Anrufen oder zum Planen von Besprechungen verwenden. Detaillierte Informationen zu Koexistenzmodi finden Sie unter [Grundlegendes zur Koexistenz und Interoperabilität von Skype for Business und Microsoft Teams](teams-and-skypeforbusiness-coexistence-and-interoperability.md).

#### <a name="app-preferences"></a>„App preferences“ (App-Einstellungen)

Hier können Sie die App auswählen, die Benutzer für die Teilnahme an Skype for Business-Besprechungen verwenden (Skype for Business oder die [Skype-Besprechungs-App](https://support.office.com/de-DE/article/What-is-Skype-Meetings-App-Skype-for-Business-Web-App-1FF3D412-718A-4982-8FF2-A4992608CDB5)). Diese Einstellung ist nicht von der Einstellung für den Koexistenzmodus abhängig.

## <a name="how-can-i-tell-which-features-are-available"></a>Woran erkenne ich, welche Funktionen verfügbar sind?

In der [Microsoft 365-Roadmap](https://www.microsoft.com/en-us/microsoft-365/roadmap?rtc=1&filters=Microsoft%20Teams) finden Sie Informationen zu neuen Microsoft Teams-Funktionen. Weitere Informationen zu neuen und geplanten Funktionen finden Sie in Microsoft Teams auf der Seite [Neuigkeiten](https://support.office.com/de-DE/article/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de?ui=en-US&rs=en-US&ad=US) und im [Microsoft Teams-Blog der Tech Community](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/What-s-new-in-Teams-Microsoft-Ignite-Edition/ba-p/252531). 

## <a name="more-information"></a>Weitere Informationen

Weitere Informationen dazu, welche Rollen Administratorfunktionen ausführen können, finden Sie unter [Verwenden der Microsoft Teams-Administratorrollen zum Verwalten von Microsoft Teams](using-admin-roles.md).
