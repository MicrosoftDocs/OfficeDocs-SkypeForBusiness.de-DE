---
title: Verwalten des Angebots für einen Test der kommerziellen Cloud
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.topic: reference
audience: Admin
ms.reviewer: baluc
ms.service: msteams
search.appverid: MET150
localization_priority: Priority
description: Erfahren Sie, wie Benutzer von Microsoft 365 oder Office 365, die nicht für Microsoft Teams lizenziert sind, eine 1-Jahres-Testversion von Teams initiieren können.
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5f8735cc328f06fd612fb86e292bc4291b99e21f
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2020
ms.locfileid: "43904530"
---
<a name="manage-the-microsoft-teams-commercial-cloud-trial-offer"></a>Verwalten des Angebots für einen Test der kommerziellen Cloud von Microsoft Teams
=======================================================

Die Testversion der kommerziellen Cloud von Microsoft Teams bietet bestehenden Microsoft 365- oder Office 365-Benutzern in Ihrer Organisation, die nicht für Microsoft Teams lizenziert sind, die Möglichkeit, eine 1-Jahres-Testversion des Produkts zu initiieren. Administratoren können dieses Feature für Benutzer in ihrer Organisation aktivieren oder deaktivieren.

> [!IMPORTANT]
> Die Microsoft Teams Commercial Cloud-Testversion wird ab Januar 2020 durch Microsoft Teams Exploratory ersetzt. Informationen zu diesem neuen Angebot finden Sie unter [Manage Teams Exploratory-Lizenz](teams-exploratory.md).

## <a name="whats-in-the-offer"></a>Was ist im Angebot enthalten?

Die Servicepläne in diesem Angebot umfassen Folgendes:

- Exchange Foundation
- Microsoft Flow für Office 365 Plan 1
- Formulare
- Microsoft Planner
- Microsoft Teams (Teams1, Teams IW)
- Office 
- PowerApps für Office 365 Plan 1
- SharePoint Online-Kiosk
- Stream
- Sway
- Whiteboard
- Yammer Enterprise 

Die Testversion gewährt ein 1-Jahres-Testabonnement für Ihre gesamte Organisation. Jeder zugewiesenen Lizenz werden im Rahmen der Testversion 2 GB SharePoint Onlinespeicher zur Verfügung gestellt. 

## <a name="who-is-eligible"></a>Wer ist berechtigt?

Benutzern muss (im Microsoft 365 Admin Center) die Möglichkeit bereitgestellt werden, sich für Apps und Testversionen zu registrieren. Weitere Informationen finden Sie weiter unten in diesem Artikel unter [Verwalten der Testversion](#manage-the-trial). 

Benutzer, die keine Office 365-Lizenz besitzen, können das Angebot für einen Test der kommerziellen Cloud von Microsoft Teams in Anspruch nehmen. Wenn ein Benutzer beispielsweise über Microsoft 365 Apps for Business verfügt (was Teams nicht einschließt), ist er zu der Testversion berechtigt.

## <a name="who-is-not-eligible"></a>Wer ist nicht berechtigt?

Ihre Organisation ist nicht für die Testversion berechtigt, wenn Sie ein Syndication-Partnerkunde oder ein GCC-, GCC High-, DoD- oder EDU-Kunde sind.

Wenn Ihre Organisation nicht berechtigt ist, das Angebot für einen Test der kommerziellen Cloud von Microsoft Teams in Anspruch zu nehmen, wird die Option **Benutzer Test-Apps und -dienste installieren lassen** nicht angezeigt.

## <a name="how-users-sign-up-for-the-trial"></a>Wie können Benutzer sich für die Testversion registrieren?

Berechtigte Benutzer können sich für das Testangebot registrieren, indem sie sich bei Microsoft Teams ([teams.microsoft.com](https://teams.microsoft.com)) anmelden. Der folgende Bildschirm wird angezeigt, um die Testversion zu starten. 

![Screenshot der Startseite für den Teams IW-Test.](media/iw-trial-start-screen.png)

Alle Testversionen innerhalb Ihrer Organisation haben das gleiche Start- und Enddatum, d. h. das Datum, an dem sich der erste Benutzer für die Testversion registriert hat. Wenn Benutzer A beispielsweise am 25. Januar 2019 die erste Testversion startet und Benutzer B am 3. Juni 2019, läuft die Testversion beider Benutzer am 25. Januar 2020 ab.

## <a name="manage-the-trial"></a><a name="manage-the-trial"></a>Verwalten der Testversion

Die Testversion von Microsoft Teams ist für die Initialisierung durch einzelne Endbenutzer bestimmt, und Sie sind nicht berechtigt, das Microsoft Teams-Testangebot im Namen von Endbenutzern oder Angestellten zu initiieren.

Administratoren können die Option für Endbenutzer deaktivieren, Test-Apps und -dienste in der Organisation in Anspruch zu nehmen. Derzeit ist die in diesem Artikel beschriebene Testversion die einzige in dieser Kategorie, aber die Angaben können in Zukunft auch für andere ähnliche Programme gelten. 

### <a name="prevent-users-from-installing-trial-apps-and-services"></a>Verhindern, dass Benutzer Test-Apps und -dienste installieren

Sie können die Option zum Installieren von Test-Apps und -diensten für Benutzer deaktivieren.

1. Navigieren Sie im [Microsoft 365 Admin Center](https://portal.office.com/adminportal/home) zu **Einstellungen** > **Einstellungen**, wählen Sie **Dienste** und dann **Apps und Dienste im Besitz des Benutzers** aus.

    ![Screenshot der Seite "Dienste" im Admin Center](media/iw-trial-services.png)

2. Deaktivieren Sie das Kontrollkästchen **Benutzer Test-Apps und -dienste installieren lassen**.

    ![Screenshot der Seite "Apps und Dienste im Besitz des Benutzers" im Admin Center.](media/iw-trial-user-owned-apps-services.png)


### <a name="manage-trial-availability-for-a-user-with-a-license-that-includes-teams"></a>Verwalten der Verfügbarkeit von Testversionen für einen Benutzer mit einer Lizenz, die Microsoft Teams umfasst

Ein Benutzer, dem eine Lizenz zugewiesen wurde, die Microsoft Teams bereits umfasst, ist nicht berechtigt, die Testversion in Anspruch zu nehmen. Wenn der Microsoft Teams-Serviceplan aktiviert ist, kann sich der Benutzer anmelden und Microsoft Teams verwenden. Wenn dem Serviceplan deaktiviert ist, kann sich der Benutzer nicht anmelden und ihm wird auch keine Option für die Testversion angezeigt.

So deaktivieren Sie den Zugriff auf Teams:

1. Wählen Sie im Microsoft 365 Admin Center, **Benutzer** > **Aktive Benutzer** aus.

2. Aktivieren Sie das Kontrollkästchen neben dem Namen des Benutzers.

3. Wählen Sie rechts in der Zeile **Produktlizenzen** die Option **Bearbeiten** aus.

4. Wechseln Sie im Bereich **Produktlizenzen** die Umschaltfläche auf **Aus**.

    ![Screenshot der Seite „Produktlizenzen“ im Admin Center.](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-already-claimed-the-trial"></a>Verwalten der Verfügbarkeit von Testversionen für Benutzer, die bereits eine Testversion von Microsoft Teams in Anspruch genommen haben

Wenn ein Benutzer eine Testlizenz von Microsoft Teams in Anspruch genommen hat, können Sie diese entfernen, indem Sie ihm die Lizenz oder den Serviceplan entziehen.

So deaktivieren Sie die Testlizenz:

1. Wählen Sie im Microsoft 365 Admin Center, **Benutzer** > **Aktive Benutzer** aus.

2. Aktivieren Sie das Kontrollkästchen neben dem Namen des Benutzers.

3. Wählen Sie rechts in der Zeile **Produktlizenzen** die Option **Bearbeiten** aus.

4. Wechseln Sie im Bereich **Produktlizenzen** die Umschaltfläche auf **Aus**.

    ![Screenshot der Einstellung "Microsoft Teams-Testlizenz" auf im Bereich „Lizenzen“](media/iW-trial-enable-4.png)
    
    >[!Note]
    >Der Umschalter „Microsoft Teams-Testversion“ wird angezeigt, sobald der erste Benutzer in der Organisation sich für die Testversion registriert.

### <a name="manage-teams-for-users-who-have-the-trial-license"></a>Verwalten von Microsoft Teams für Benutzer, die über die Testlizenz verfügen

Sie können Benutzer mit einer Testlizenz genauso verwalten wie Benutzer mit einer regulären kostenpflichtigen Lizenz. Weitere Informationen finden Sie unter [Verwalten von Microsoft Teams-Einstellungen in Ihrer Organisation](enable-features-office-365.md).

### <a name="upgrade-users-from-the-trial-license"></a>Upgraden von Benutzern mit Testlizenz

Um Benutzer mit Testlizenz zu upgraden, gehen Sie wie folgt vor:

1. Kaufen Sie ein Abonnement, das Microsoft Teams enthält.

2. Entfernen Sie das Microsoft Teams-Testabonnement des Benutzers.

3. Weisen Sie die neu erworbene Lizenz zu.

Weitere Informationen finden Sie unter [Office 365-Lizenzen für Microsoft Teams](Office-365-licensing.md).

> [!NOTE]
> Wenn die Testversion abläuft und kein unmittelbares Upgrade auf ein Abonnement mit Teams für einen Benutzer erfolgt, werden die Benutzerdaten nicht entfernt. Der Benutzer bleibt weiterhin in Azure Active Directory und alle Daten innerhalb von Teams werden beibehalten. Sobald dem Benutzer eine neue Lizenz zugewiesen ist, die Teams-Funktionen aktiviert, sind die Inhalte weiterhin vorhanden. 

### <a name="remove-a-legacy-microsoft-teams-trial-license"></a>Entfernen einer veralteten Microsoft Teams-Testlizenz

Ab dem 22. April 2019 können Benutzer damit beginnen, die neueste Microsoft Teams Commercial Cloud-Testlizenz anzufordern. Wenn Sie mit Benutzern in Ihrer Organisation von der Legacy-Testlizenz auf die neueste Testversion umsteigen möchten, müssen Sie zuerst die alte Microsoft Teams-Testlizenz für jeden Benutzer entfernen. Nach dem Entfernen der Legacy-Lizenz kann jeder betroffene Benutzer die aktualisierte Microsoft Teams Commercial Cloud-Testlizenz anfordern.

- Wenn Sie diese Lizenz über PowerShell entfernen möchten, ziehen Sie [Entfernen von Lizenzen von Benutzerkonten mit Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell) zurate.

- Wenn Sie diese Lizenz über das Verwaltungsportal entfernen möchten, lesen Sie [Entfernen von Lizenzen von Benutzern in Office 365 Business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/remove-licenses-from-users?view=o365-worldwide).
