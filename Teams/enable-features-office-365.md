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
description: Informationen Sie zum Aktivieren oder Deaktivieren der apps in Office 365-Organisation, einschließlich Registerkarten, Connectors, Bots oder eine beliebige Kombination der drei Microsoft-Teams.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7f78876064ae50221562bd42b334545f627a02fb
ms.sourcegitcommit: 9138325ba2652a9ee3602d259de811082080e358
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2018
ms.locfileid: "25842076"
---
# <a name="manage-microsoft-teams-features-in-your-office-365-organization"></a>Verwalten von Microsoft Teams-Funktionen in Ihrer Office 365-Organisation

Alle Einstellungen für Teams werden bald zu der neuen Microsoft-Teams & Skype für Business-Verwaltungskonsole migriert werden. Das einzige Teams-Feature, das in der Office 365-Verwaltungskonsole verwaltet wird, ist Apps. 

Sofern nicht anders angegeben, ist der Standardwert für eine Option **auf**.

## <a name="office-365-tenant-wide-settings"></a>Mandantenweite Einstellungen in Office 365 

In den **Mandanten geltende Einstellungen**können Sie aktivieren oder Deaktivieren von Apps.

Bearbeiten von **Mandanten geltende Einstellungen** für Teams, wechseln in der Microsoft-Teams & Skype für Business Admin Center, und wählen **Legacy-Portal**. Wählen Sie **Einstellungen** > **Dienste und Add-Ins** > **Microsoft Teams** aus. Wenn Sie als Office 365-Administrator angemeldet sind, können Sie diesen Link verwenden: 
>  
> https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns  

### <a name="apps"></a>Apps

Apps sind Registerkarten, Connectors und Bots bzw. eine beliebige Kombination dieser drei Elemente, die von einem Drittanbieterdienst bereitgestellt werden. Im Office 365 Admin Center können Microsoft Teams-Administratorrichtlinien konfiguriert werden, um zu steuern, welche externen Drittanbieter-Apps zulässig sind. Diese Richtlinien können Sie angeben, welche apps zulässig sind und nicht zulässig, neue externe app Verhalten und ob Seite laden apps zulässig ist. 

Unter **Apps** können Sie die folgenden Einstellungen für Ihre Organisation konfigurieren: 

![Screenshot des Abschnitts „Apps“](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.png)

- **Allow external apps in Microsoft Teams** (Externe Apps in Microsoft Teams zulassen): Wenn diese Option aktiviert ist, können Benutzer Registerkarten und Bots hinzufügen, die für den Office 365-Mandanten verfügbar sind. 
 
    ![Screenshot des Steuerelements zum Zulassen externer Apps im Abschnitt „Apps“](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.2.png)

- **Enable new external apps by default** (Neue externe Apps standardmäßig aktivieren): Wenn diese Option aktiviert ist, können Benutzer neue Apps aktivieren, sobald diese zum Microsoft Teams-App-Katalog hinzugefügt werden. Deaktivieren Sie diese Option, wenn Sie neue Apps steuern möchten. Wenn Sie die Option deaktiviert haben, müssen Sie natürlich daran denken, neue Apps regelmäßig zu überprüfen, damit Ihrer Organisation keine tollen neuen Apps entgehen. 

- **Zulassen von Sideloading von externen apps**: Wenn diese Option aktiviert ist, Benutzer installieren und aktivieren Sie benutzerdefinierte Bots und Registerkarten können. 

Weitere Informationen finden Sie unter [Administratoreinstellungen für Apps in Microsoft Teams](admin-settings.md). 

## <a name="teams-org-wide-settings"></a>Teams Org geltende Einstellungen

Organisationsweite benutzereinstellungen im Microsoft-Teams & Skype für Business Admin Center können Sie steuern. Um Org geltende Einstellungen bearbeiten möchten, besuchen Sie die Microsoft Skype für Business Admin Center, und wählen Sie dann auf **Einstellungen für die gesamte Org**. Sie können die folgenden Einstellungen konfigurieren.

### <a name="external-access"></a>Externer Zugriff

**Zugriff durch externe** können Ihre Teams und Skype für Unternehmensbenutzer mit Benutzern kommunizieren, die sich außerhalb Ihrer Organisation befinden. Um den externen Zugriff konfigurieren, wechseln Sie zur [können Sie Ihren Teams Benutzer Chat und zur Kommunikation mit Benutzern in anderen Organisationen von Teams](let-your-teams-users-communicate-with-other-people.md).

### <a name="guest-access"></a>Gastzugriff

**Gast Access** in Microsoft-Teams können Teams in Ihrer Organisation für die Zusammenarbeit mit Personen außerhalb Ihrer Organisation von ihnen Zugriff auf Teams und Kanäle gewähren. Jeder Benutzer mit einer Business "oder" Consumer e-Mail-Konto, wie Outlook, Google Mail oder andere, kann als Gast in Teams vollen Zugriff auf Team Chats, Besprechungen und Dateien teilnehmen. Weitere Informationen finden Sie unter [Gast Access in Microsoft-Teams](guest-access.md).

### <a name="teams-settings"></a>Einstellungen für Teams

In den **Einstellungen für Teams**können Sie e-Mail-Integration, Cloud Speicheroptionen, Skype für Business Interoperabilität und Geräte einrichten.

#### <a name="email-integration"></a>E-Mail-Integration

Aktivieren Sie diese Funktion, damit Benutzer über die Kanal-E-Mail-Adresse eine E-Mail an einen Kanal in Microsoft Teams senden können. Benutzer können dies für jeden Kanal tun, der zu einem Team gehört, dessen Besitzer sie sind. Benutzer können auch-e-Mails zu jeder Kanal ein Team senden, deren Connectors für Teammitglieder eingeschaltet hinzufügen. Zum Aktivieren von e-Mail-Integration sicher, dass **Benutzer zum Senden von e-Mails an eine e-Mail-Adresse des DDE-Kanal** **auf**ist. 

#### <a name="files"></a>Dateien

Hier können Sie aktivieren oder Deaktivieren der Datei Freigabe und Cloud-Datei Speicheroptionen. 

Benutzer können Dateien aus Cloudspeicherdiensten in Microsoft Teams-Kanäle und -Chats hochladen und dort freigeben. Cloud-Speicheroptionen in Teams umfassen derzeit ShareFile, Ablage, Feld und Google Laufwerk. Aktivieren Sie die Option für die Cloudspeicheranbieter, die Ihre Organisation verwenden möchte.

#### <a name="organization"></a>Organisation

Hier können Sie auf der Registerkarte **Organisation** aktivieren, die ausführlichen Organigramms für die Organisation des Benutzers angezeigt wird. Weitere Informationen finden Sie unter [Verwenden der Registerkarte Organisation in Teams](https://support.office.com/article/use-the-organization-tab-in-teams-ff02568b-290a-46d6-ae7a-cda22f723894).

#### <a name="skype-for-business-interop"></a>Skype für Business-interop

Verwenden Sie diese Einstellung, um Teams Benutzer chatten mit Skype für Unternehmensbenutzer lassen. Ausführliche Informationen über die Interoperabilität zwischen Teams und Skype für Unternehmen wechseln Sie zur [Microsoft-Teams, zu verstehen und Skype für Interoperabilität und Koexistenz Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md).

#### <a name="devices"></a>Geräte

Diese Einstellungen steuern Konto Verhalten der Ressourcen für Fläche Hub Geräte teilnehmen an Besprechungen mit Microsoft-Teams. Verwenden Sie diese Einstellungen Anforderungen für die Authentifizierung zu konfigurieren, benötigen eine PIN Content und Fläche Hub Ressourcenkonten zum Senden von Nachrichten zu aktivieren.

- ANHEFTEN **erfordern eine sekundäre Form der Authentifizierung auf Inhalte zugreifen** – wählen Sie die Zugriffsebene, die Benutzer haben, wenn sie den Inhalt eingeben.
- **Legen Sie Inhalt PIN** – Benutzer müssen diese PIN zum Entsperren des unbefugten Zugriff auf Dokumente verhindern eingeben. Dies verhindert, dass einen nicht autorisierten Benutzer von bevorstehenden-Besprechungen teilnehmen und Anlagen durchsuchen.
- **Ressourcenkonten Nachrichten senden können** – diese Einstellung **auf** aktivieren, damit Nachrichten von der Fläche Hub Ressourcenkonto gesendet werden können.

#### <a name="search"></a>Suche

Microsoft-Teams, bereichsbasierte Verzeichnissuche finden verwendet Exchange adressbuchrichtlinie (APB) für Organisationen virtuelle Grenzen dieses Steuerelement erstellen, wie Benutzer suchen und mit anderen Benutzern in ihrer Organisation kommunizieren können. Sie sollten eine bereichsbasierte Verzeichnissuche in solchen Situationen verwenden:

- Ihre Organisation verfügt über mehrere Mandanten innerhalb dessen Mandanten, die Sie trennen möchten. 
- Ihre Schule möchte Chats zwischen Fakultät und Schüler zu beschränken. 

Wechseln Sie diese Einstellung **auf** um bereichsbezogenen Verzeichnissuchen zu aktivieren.

### <a name="teams-upgrade"></a>Upgrade von Teams

Diese Einstellungen können Sie konfigurieren, wie die Benutzer von Skype für Unternehmen, die Microsoft-Teams aktualisiert werden sollen. 

#### <a name="coexistence-mode"></a>Koexistenzmodus
Sie können einen Koexistenzmodus angeben: **nur Teams**, **Inseln** (Teams und Skype für Business wird Koexistenz) oder **Skype für Unternehmen nur**. Der Koexistenzmodus gewählte bestimmt das routing von eingehenden Anrufen und Chats und der app, die vom Benutzer, Chats und Anrufe initiieren oder Besprechungstermine verwendet wird. Weitere Informationen zur Koexistenz Modi wechseln Sie zur [Microsoft-Teams, zu verstehen und Skype für Interoperabilität und Koexistenz Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md).

#### <a name="app-preferences"></a>App-Einstellungen

Hier können Sie wählen Sie die app, mit denen Benutzer teilnehmen Skype für Unternehmen Besprechungen (Skype für Geschäftskunden und die [Skype Besprechungen App](https://support.office.com/en-us/article/What-is-Skype-Meetings-App-Skype-for-Business-Web-App-1FF3D412-718A-4982-8FF2-A4992608CDB5)). Diese Einstellung ist nicht die Einstellung für die Koexistenz abhängig.


