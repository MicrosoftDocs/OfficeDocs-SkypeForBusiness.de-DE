---
title: Verwalten des Angebots für einen Test der kommerziellen Cloud von Microsoft Teams
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 12/10/2018
ms.topic: article
audience: Admin
ms.reviewer: annikaelias
ms.service: msteams
search.appverid: MET150
localization_priority: Priority
description: Office 365-Benutzer, die nicht für Microsoft Teams lizenziert sind, können eine einjährige Testversion von Teams starten.
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c4fdeba0e4540d64e98eb2853b73e6d1edb5110e
ms.sourcegitcommit: bc2b227b4ac0a9521993f808a1361b4f9bc7faad
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "30569615"
---
<a name="manage-the-microsoft-teams-commercial-cloud-trial-offer"></a>Verwalten des Angebots für einen Test der kommerziellen Cloud von Microsoft Teams
=======================================================

Microsoft Teams ist ein hervorragendes Tool für die Zusammenarbeit in Ihrem Unternehmen. Microsoft Teams ermöglicht Einzelpersonen und Teams Diskussionen, Innovationen und den Austausch von Ideen, und dabei von der Leistungsfähigkeit von Office 365 zu profitieren. Die Testversion der kommerziellen Cloud von Microsoft Teams bietet bestehenden Office 365-Benutzern in Ihrer Organisation, die nicht für Microsoft Teams lizenziert sind, die Möglichkeit, eine einjährige Testversion des Produkts zu starten. Administratoren können dieses Feature für Benutzer in ihrer Organisation aktivieren oder deaktivieren.

## <a name="whats-in-the-offer"></a>Was ist im Angebot enthalten?

Die Servicepläne in diesem Angebot umfassen Folgendes:

- Exchange Foundation
- Microsoft Flow für Office 365 Plan 1
- Microsoft Planner
- Microsoft Teams (Teams1, Teams IW)
- Office Online
- PowerApps für Office 365 Plan 1
- SharePoint Online-Kiosk
- Sway
- Yammer Enterprise

Die Testversion gewährt ein 1-Jahres-Testabonnement für Ihre gesamte Organisation. Die Testversion umfasst 500.000 Lizenzen. Jeder zugewiesenen Lizenz werden im Rahmen der Testversion 2 GB SharePoint Onlinespeicher zur Verfügung gestellt. 

## <a name="who-is-eligible"></a>Wer ist berechtigt?

Benutzern muss (im Office 365 Admin Center) die Möglichkeit bereitgestellt werden, sich für Apps und Testversionen zu registrieren. Weitere Informationen finden Sie weiter unten in diesem Artikel unter [Verwalten der Testversion](#manage-the-trial). 

Benutzer, die keine Office 365-Lizenz besitzen, können das Angebot für einen Test der kommerziellen Cloud von Microsoft Teams in Anspruch nehmen. Wenn ein Benutzer beispielsweise Office 365 Business verwendet (das Microsoft Teams nicht beinhaltet), ist er berechtigt, die Testversion in Anspruch zu nehmen.

## <a name="who-is-not-eligible"></a>Wer ist nicht berechtigt?

Ihre Organisation ist in folgenden Fällen nicht berechtigt, die Testversion in Anspruch zu nehmen: 

- Sie sind ein Syndication-Partner.
- Sie sind ein Einzelhändlerpartner.
- Sie sind eine Behörde oder Bildungseinrichtung.

Wenn Ihre Organisation nicht berechtigt ist, das Angebot für einen Test der kommerziellen Cloud von Microsoft Teams in Anspruch zu nehmen, wird die Option **Benutzer Test-Apps und -dienste installieren lassen** nicht angezeigt.

## <a name="how-users-sign-up-for-the-trial"></a>Wie können Benutzer sich für die Testversion registrieren?

Berechtigte Benutzer können sich für das Testangebot registrieren, indem sie sich bei Microsoft Teams ([teams.microsoft.com](https://teams.microsoft.com)) anmelden. Der folgende Bildschirm wird angezeigt, um die Testversion zu starten. 

![Screenshot der Startseite für den Teams IW-Test.](media/iw-trial-start-screen.png)

Alle Testversionen innerhalb Ihrer Organisation haben das gleiche Start- und Enddatum, d. h. das Datum, an dem sich der erste Benutzer für die Testversion registriert hat. Wenn Benutzer A beispielsweise am 25. Januar 2019 die erste Testversion startet und Benutzer B am 3. Juni 2019, läuft die Testversion beider Benutzer am 25. Januar 2020 ab.

## <a name="manage-the-trial"></a>Verwalten der Testversion

Administratoren können die Lizenzen der registrierten Benutzer verwalten. 

Darüber hinaus können Administratoren die Option für Endbenutzer deaktivieren, Test-Apps und -dienste in der Organisation in Anspruch zu nehmen. Derzeit ist die in diesem Artikel beschriebene Testversion die einzige in dieser Kategorie, aber die Angaben können in Zukunft auch für andere ähnliche Programme gelten. 

### <a name="prevent-users-from-installing-trial-apps-and-services"></a>Verhindern, dass Benutzer Test-Apps und -dienste installieren

Sie können die Option zum Installieren von Test-Apps und -diensten für Benutzer deaktivieren.

1. Navigieren Sie dazu im [Microsoft 365 Admin Center](https://portal.office.com/adminportal/home) zu **Einstellungen** > **Dienste und Add-Ins** > **Apps und Dienste im Besitz des Benutzers**.

    ![Screenshot der Seite "Dienste und Add-Ins" im Office 365 Admin Center.](media/iw-trial-enable-1.png)

2. Deaktivieren Sie **Benutzer Test-Apps und -dienste installieren lassen**.

    ![Screenshot der Seite "Apps und Dienste im Besitz des Benutzers" im Office 365 Admin Center.](media/iw-trial-enable-2.png)


### <a name="manage-trial-availability-for-a-user-with-a-license-that-includes-teams"></a>Verwalten der Verfügbarkeit von Testversionen für einen Benutzer mit einer Lizenz, die Microsoft Teams umfasst

Ein Benutzer, dem eine Lizenz zugewiesen wurde, die Microsoft Teams bereits umfasst, ist nicht berechtigt, die Testversion in Anspruch zu nehmen. Wenn der Microsoft Teams-Serviceplan aktiviert ist, kann sich der Benutzer anmelden und Microsoft Teams verwenden. Wenn dem Serviceplan deaktiviert ist, kann sich der Benutzer nicht anmelden und ihm wird auch keine Option für die Testversion angezeigt.

So deaktivieren Sie den Zugriff auf Teams:

1. Wählen Sie im Microsoft 365 Admin Center, **Benutzer** > **Aktive Benutzer** aus.

2. Aktivieren Sie das Kontrollkästchen neben dem Namen des Benutzers.

3. Wählen Sie rechts in der Zeile **Produktlizenzen** die Option **Bearbeiten** aus.

4. Wechseln Sie im Bereich **Produktlizenzen** die Umschaltfläche auf **Aus**.

    ![Screenshot der Seite "Produktlizenzen" im Office 365 Admin Center.](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-already-claimed-the-trial"></a>Verwalten der Verfügbarkeit von Testversionen für Benutzer, die bereits eine Testversion von Microsoft Teams in Anspruch genommen haben

Wenn ein Benutzer eine Testlizenz von Microsoft Teams in Anspruch genommen hat, können Sie diese entfernen, indem Sie ihm die Lizenz oder den Serviceplan entziehen.

So deaktivieren Sie die Testlizenz:

1. Wählen Sie im Microsoft 365 Admin Center, **Benutzer** > **Aktive Benutzer** aus.

2. Aktivieren Sie das Kontrollkästchen neben dem Namen des Benutzers.

3. Wählen Sie rechts in der Zeile **Produktlizenzen** die Option **Bearbeiten** aus.

4. Wechseln Sie im Bereich **Produktlizenzen** die Umschaltfläche auf **Aus**.

    ![Screenshot der Einstellung "Microsoft Teams-Testlizenz" auf im Bereich "Produktlizenzen"](media/iW-trial-enable-4.png)
    
>[!Note]
>Der Umschalter "Microsoft Teams-Testversion" wird angezeigt, sobald der erste Benutzer in der Organisation sich für die Testversion registriert.

### <a name="manage-teams-for-users-who-have-the-trial-license"></a>Verwalten von Microsoft Teams für Benutzer, die über die Testlizenz verfügen

Sie können Benutzer mit einer Testlizenz genauso verwalten wie Benutzer mit einer regulären kostenpflichtigen Lizenz. Weitere Informationen finden Sie unter [Verwalten von Microsoft Teams-Features in Ihrer Office 365-Organisation](enable-features-office-365.md).

### <a name="upgrade-users-from-the-trial-license"></a>Upgraden von Benutzern mit Testlizenz

Um Benutzer mit Testlizenz zu upgraden, gehen Sie wie folgt vor:

1. Kaufen Sie ein Abonnement, das Microsoft Teams enthält.

2. Entfernen Sie das Microsoft Teams-Testabonnement des Benutzers.

3. Weisen Sie die neu erworbene Lizenz zu.

Weitere Informationen finden Sie unter [Office 365-Lizenzen für Microsoft Teams](Office-365-licensing.md).
