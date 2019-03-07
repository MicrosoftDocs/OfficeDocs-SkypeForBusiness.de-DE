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
localization_priority: Normal
description: Office 365-Benutzer, die nicht für Microsoft-Teams lizenziert sind, können eine 1 Jahr Testversion von Teams initiieren.
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5101cc8f54d41aaf63b24fea1d9092b1465a81d7
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/07/2019
ms.locfileid: "30462372"
---
<a name="manage-the-microsoft-teams-commercial-cloud-trial-offer"></a>Verwalten des Angebots für einen Test der kommerziellen Cloud von Microsoft Teams
=======================================================

Microsoft-Teams, ist ein hervorragendes collaborative Tool für Ihre Organisation. Sie können Personen und Teams zu besprechen und Veränderungen Ideen mithilfe der Vorteile von Office 365. Die Microsoft-Teams kommerziellen Cloud Studien bietet vorhandenen Office 365-Benutzer in Ihrer Organisation, die für Microsoft-Teams zum Initiieren einer 1 Jahr Testversion des Produkts nicht lizenziert sind. Administratoren können dieses Feature aktiviert oder deaktiviert für Benutzer in ihrer Organisation wechseln.

## <a name="whats-in-the-offer"></a>Was ist in dem Angebot

Die Servicepläne in dieses Angebot enthalten sind:

- Exchange-Foundation
- Datenfluss für Office 365-Plan 1
- Microsoft-Planner
- Microsoft-Teams (Teams1, Teams Information Worker)
- Office Online
- PowerApps für Office 365-Plan 1
- SharePoint Online-Kiosk
- Schlingern
- Yammer Enterprise

Die Testversion gewährt ein einjährige Studien Abonnement für die gesamte Organisation. Die Testversion macht 500.000 Lizenzen zugewiesen. Für jede Lizenz zugewiesen ist weist die Testversion 2 GB an Speicher SharePoint Online. 

## <a name="who-is-eligible"></a>Wer berechtigt ist

Benutzer müssen für apps und Testversionen (im Office 365 Administrationscenter) anmelden aktiviert sein. Weitere Informationen finden Sie unter [Verwalten der Testversion](#manage-the-trial) weiter unten in diesem Artikel. 

Benutzer, die nicht mit eine Office 365-Lizenz verfügen, die Teams können das Angebot Teams kommerziellen Cloud-Testversion von Microsoft initiieren. Verfügt ein Benutzer für Office 365 Business (die Teams umfassen nicht), werden sie beispielsweise für die Testversion berechtigt.

## <a name="who-is-not-eligible"></a>Wer kann nicht verwendet werden

Ihre Organisation kann nicht für die Testversion If verwendet werden: 

- Sie sind ein Syndication Partner-Kunden
- Sie sind Kunden Händlerkanäle Partner
- Sie sind ein Kunde Behörden oder EDU

Wenn Ihre Organisation nicht für die Microsoft-Teams kommerziellen Cloud Testangebot ist, sehen Sie nicht die Option **Benutzer Studien apps und Diensten installieren können** .

## <a name="how-users-sign-up-for-the-trial"></a>Wie Benutzer für die Testversion anmelden

Berechtigte Benutzern können durch Anmeldung bei Teams ([teams.microsoft.com](https://teams.microsoft.com)) für die Testangebot registrieren. Der folgende Bildschirm zum Starten der Testversion sehen. 

![Screenshot der Startseite für die Testversion Teams Information Worker.](media/iw-trial-start-screen.png)

Alle Versuche innerhalb Ihrer Organisation freigeben der gleichen Anfangs- und Enddaten, welches das Datum ist der erste Benutzer für die Testversion angemeldet. Wenn Benutzer A die erste Testversion auf 25 Januar 2019 und Benutzer B eine Testversion auf 3 Juni 2019 beginnt wird beider Benutzer Testversion auf 25 Januar 2020 ablaufen.

## <a name="manage-the-trial"></a>Verwalten der Testversion

Administratoren können die Lizenzen für Benutzer verwalten, die angemeldet haben. 

Darüber hinaus können Administratoren die Möglichkeit für Endbenutzer in Anspruch Studien apps und Diensten innerhalb ihrer Organisation zu deaktivieren. Aktuell, die in diesem Artikel beschriebenen Testversion nur Studien in dieser Kategorie ist, aber es möglicherweise gelten für andere Programme ähnlich wie in der Zukunft. 

### <a name="prevent-users-from-installing-trial-apps-and-services"></a>Verhindern, dass Benutzer an der Installation von Studien apps und Diensten

Sie können die Fähigkeit eines Benutzers Studien apps und Diensten installieren deaktivieren.

1. Das [Microsoft 365 Administrationscenter](https://portal.office.com/adminportal/home), wechseln Sie zu **Einstellungen** > **Services &-add-ins** > **Benutzer Apps und Diensten gehören**.

    ![Screenshot der Seite Dienste &-add-ins im Office 365 Administrationscenter.](media/iw-trial-enable-1.png)

2. Deaktivieren Sie **dazu, Benutzern das Installieren Studien apps und Dienste aus**.

    ![Screenshot des Benutzers gehören Apps und Diensten Seite im Office 365 Administrationscenter.](media/iw-trial-enable-2.png)


### <a name="manage-trial-availability-for-a-user-with-a-license-that-includes-teams"></a>Verwalten von Studien Verfügbarkeit für einen Benutzer mit einer Lizenz, die Teams

Ein Benutzer, der eine Lizenz zugewiesen ist, die Teams enthalten, ist, kann nicht für die Testversion verwendet. Wenn die Teams Dienstplan aktiviert ist, kann der Benutzer anmelden und Teams verwenden. Wenn die Dienstplan deaktiviert ist, wird der Benutzer nicht anmelden kann und wird nicht angezeigt und der Testversion Option entweder.

So deaktivieren Sie Zugriff auf Teams

1. Wählen Sie im Microsoft 365 Administrationscenter **Benutzer** > **aktive Benutzer**.

2. Aktivieren Sie das Kontrollkästchen neben den Namen des Benutzers an.

3. Auf der rechten Seite in der Zeile **Lizenzen** wählen Sie **Bearbeiten**.

4. Klicken Sie im Bereich **Lizenzen** wechseln Sie die Umschaltfläche zu **Deaktivieren**.

    ![Screenshot der Seite Lizenzen Produkt im Office 365 Administrationscenter.](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-already-claimed-the-trial"></a>Verwalten von Teams Verfügbarkeit für Benutzer, die bereits die Testversion beansprucht

Wenn ein Benutzer eine Testlizenz Teams angefordert hat, können Sie ihn durch Entfernen des Lizenz oder Dienst Plans entfernen.

So deaktivieren Sie die Testlizenz

1. Wählen Sie im Microsoft 365 Administrationscenter **Benutzer** > **aktive Benutzer**.

2. Aktivieren Sie das Kontrollkästchen neben den Namen des Benutzers an.

3. Auf der rechten Seite in der Zeile **Lizenzen** wählen Sie **Bearbeiten**.

4. Klicken Sie im Bereich **Lizenzen** wechseln Sie die Umschaltfläche zu **Deaktivieren**.

    ![Screenshot der Teams Testlizenz Einstellung im Bereich der Produkt-Lizenzen](media/iW-trial-enable-4.png)

### <a name="manage-teams-for-users-who-have-the-trial-license"></a>Verwalten von Teams für Benutzer mit der Testlizenz

Sie können Benutzer verwalten, die über eine Testlizenz verfügen genau wie Verwalten von Benutzern, die über eine normale kostenpflichtigen Lizenz verfügen. Weitere Informationen finden Sie unter [Microsoft-Teams, Verwalten von Features in Office 365-Organisation](enable-features-office-365.md).

### <a name="upgrade-users-from-the-trial-license"></a>Aktualisieren Sie die Benutzer aus der Testlizenz

Um Benutzer aus der Testlizenz aktualisiert haben, führen Sie folgende Schritte aus:

1. Erwerben eines Abonnements, das Teams enthält.

2. Entfernen Sie das Test-Abonnement von Teams aus der Benutzer.

3. Neu erworbene Lizenz zuweisen.

Weitere Informationen finden Sie unter [Office 365-Lizenzierung für Microsoft Teams](Office-365-licensing.md).