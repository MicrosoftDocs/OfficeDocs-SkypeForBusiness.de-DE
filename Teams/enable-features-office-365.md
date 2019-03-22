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
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a302d27884f92fb5cf17cc605cead6addbe98bfd
ms.sourcegitcommit: 28dd9b8ca3de35a73e4d6923eff5546925435b8b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2019
ms.locfileid: "30683892"
---
# <a name="manage-microsoft-teams-features-in-your-office-365-organization"></a>Verwalten von Microsoft Teams-Funktionen in Ihrer Office 365-Organisation

Alle Teams-Einstellungen werden in Kürze zum neuen Admin Center für Microsoft Teams migriert. Apps werden als einzige Teams-Funktion im Microsoft 365 Admin Center verwaltet. 

Wenn nichts anderes angegeben ist, lautet der Standardwert für die jeweilige Option **Ein**.

## <a name="tenant-wide-settings"></a>Mandantenweite Einstellungen 

Sie können Apps für Microsoft Teams in **Mandantenweite Einstellungen** im Microsoft 365 Admin Center deaktivieren oder aktivieren. 

Zum Bearbeiten der **mandantenweiten Einstellungen** für Microsoft Teams wechseln Sie zum Admin Center für Microsoft 365. Wählen Sie **Einstellungen** > **Dienste und Add-Ins** > **Microsoft Teams** aus. Wenn Sie als Office 365-Administrator angemeldet sind, können Sie diesen Link verwenden: 

https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns  

### <a name="apps"></a>Apps

Apps sind Registerkarten, Connectors, Bots oder eine Kombination dieser drei, die von Teams (Erstanbieter-Apps, auch bekannt als Standard-Apps) oder von einem Drittanbieter (auch bekannt als externe Apps) bereitgestellt werden.Unter **Apps** können Sie Standard-Apps aktivieren bzw. deaktivieren und Einstellungen für die Steuerung externer Apps konfigurieren. Um mehr über das Einführen von Apps, Bots, Connectors und Registerkarten in Teams zu erfahren, lesen Sie (Apps, Bots und Connectors)[deploy-apps-microsoft-teams-landing-page.md].

#### <a name="default-apps"></a>Standard-Apps

Diese Apps, wie Planner, Lob und Wetter, werden von Teams bereitgestellt. Um eine App zu aktivieren, aktivieren Sie das Kontrollkästchen für diese App. Um eine App zu deaktivieren, deaktivieren Sie das Kontrollkästchen für diese App. 

![Screenshot des Abschnitts für Standard-Apps.](media/teams-manage-features-in-office365-image1.png "Screenshot des Abschnitts für Standard-Apps")

#### <a name="external-apps"></a>Externe Apps

Diese Apps werden von Drittanbietern bereitgestellt. Sie können die folgenden Einstellungen für externe Apps konfigurieren.

![Screenshot des Abschnitts für externe Apps.](media/teams-manage-features-in-office365-image2.png "Screenshot des Abschnitts für externe Apps, mit Einstellungen, die Sie aktivieren oder deaktivieren können")

- **Allow external apps in Microsoft Teams** (Externe Apps in Microsoft Teams zulassen): Wenn diese Einstellung aktiviert ist, können Benutzer externe Apps hinzufügen, die für Ihre Organisation verfügbar sind. 

- **Allow sideloading of external apps** (Querladen von externen Apps zulassen): Wenn Sie einige externe Apps aktivieren und andere deaktivieren möchten, deaktivieren Sie diese Einstellung, und deaktivieren Sie anschließend in der Liste der externen Apps die Apps, auf die Benutzer nicht zugreifen sollen. Wenn diese Einstellung aktiviert ist, können Teambesitzer und Mitglieder, denen eine Berechtigung erteilt wurde, Apps in Microsoft Teams querladen. 

- **Enable new external apps by default** (Neue externe Apps standardmäßig aktivieren): Wenn diese Einstellung aktiviert ist, können Benutzer neue Apps aktivieren, sobald diese zum Microsoft Teams-App-Katalog hinzugefügt werden. Deaktivieren Sie diese Einstellung, wenn Sie neue Apps steuern möchten. Wenn Sie die Einstellung deaktiviert haben, müssen Sie natürlich daran denken, neue Apps regelmäßig zu überprüfen, damit Ihrer Organisation keine tollen neuen Apps entgehen. 

Weitere Informationen finden Sie unter [Administratoreinstellungen für Apps in Microsoft Teams](admin-settings.md). 

## <a name="teams-org-wide-settings"></a>Organisationsweite Einstellungen für Microsoft Teams

Sie können organisationsweite Benutzereinstellungen im Microsoft Teams Admin Center steuern. Um organisationsweite Einstellungen zu bearbeiten, gehen Sie zum Microsoft Teams Admin Center, und wählen Sie dann **Organisationsweite Einstellungen** aus. Sie können die folgenden Einstellungen konfigurieren.

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

Hier können Sie die App auswählen, die Benutzer für die Teilnahme an Skype for Business-Besprechungen verwenden (Skype for Business oder die [Skype-Besprechungs-App](https://support.office.com/de-DE/article/What-is-Skype-Meetings-App-Skype-for-Business-Web-App-1FF3D412-718A-4982-8FF2-A4992608CDB5)). Diese Einstellung ist nicht von der Einstellung für den Koexistenzmodus abhängig.

## <a name="how-can-i-tell-which-features-are-available"></a>Woran erkenne ich, welche Funktionen verfügbar sind?

In der [Microsoft 365-Roadmap](https://www.microsoft.com/en-us/microsoft-365/roadmap?rtc=1&filters=Microsoft%20Teams) finden Sie Informationen zu neuen Microsoft Teams-Funktionen. Weitere Informationen zu neuen und geplanten Funktionen finden Sie in Microsoft Teams auf der Seite [Neuigkeiten](https://support.office.com/en-us/article/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de?ui=en-US&rs=en-US&ad=US) und im [Microsoft Teams-Blog der Tech Community](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/What-s-new-in-Teams-Microsoft-Ignite-Edition/ba-p/252531). 

## <a name="more-information"></a>Weitere Informationen

Weitere Informationen dazu, welche Rollen Administratorfunktionen ausführen können, finden Sie unter [Verwenden der Microsoft Teams-Administratorrollen zum Verwalten von Microsoft Teams](using-admin-roles.md).
