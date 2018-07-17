---
title: Verwalten des Angebots Teams kommerziellen Cloud-Testversion von Microsoft
author: ChuckEdmonson
ms.author: chucked
manager: lolaj
ms.date: 07/17/2018
ms.topic: article
audience: Admin
ms.reviewer: alchen
ms.service: msteams
localization_priority: Normal
description: Office 365-Benutzer, die nicht für Microsoft-Teams lizenziert sind, können eine 1 Jahr Testversion von Teams initiieren.
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: ec12fa2687255fb3097d4bbe637389bc643d77cd
ms.sourcegitcommit: b9f33329cbf3352bfe3741717abcf871e7395657
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/17/2018
ms.locfileid: "20412333"
---
<a name="manage-the-microsoft-teams-commercial-cloud-trial-offer"></a>Verwalten des Angebots Teams kommerziellen Cloud-Testversion von Microsoft
=======================================================

Microsoft-Teams, ist ein hervorragendes collaborative Tool für Ihre Organisation. Sie können Personen und Teams zu besprechen und Veränderungen Ideen mithilfe der Vorteile von Office 365. Die Microsoft-Teams kommerziellen Cloud Studien bietet vorhandenen Office 365-Benutzer in Ihrer Organisation, die für Microsoft-Teams zum Initiieren einer 1 Jahr Testversion des Produkts nicht lizenziert sind. Administratoren haben die Möglichkeit zum ein-oder Ausschalten dieses Feature für Benutzer innerhalb ihrer Mandanten.

## <a name="whats-in-the-offer"></a>Was ist in dem Angebot

Die Servicepläne in dieses Angebot enthalten sind:

- Exchange-Foundation
- Datenfluss für Office 365-Plan 1
- Microsoft-Planner
- Microsoft-Teams (Teams1, Teams Information Worker)
- Office Online
- PowerApps für Office 365-Plan 1
- SharePoint Online-Plan 1
- Schlingern
- Yammer Enterprise

## <a name="who-is-eligible"></a>Wer berechtigt ist

Benutzer, die nicht mit eine Office 365-Lizenz verfügen, die Teams können das Angebot Teams kommerziellen Cloud-Testversion von Microsoft initiieren. Wenn ein Benutzer über Office 365 Business Premium (einschließlich Teams) verfügt, und die Teams Dienstplan deaktiviert ist, werden sie beispielsweise nicht für die Testversion berechtigt.

Darüber hinaus Ihres Mandanten ist nicht für die Testversion If: 
- Sie sind ein Syndication Partner-Kunden
- Sie sind Kunden Händlerkanäle Partner
- Sie sind ein Kunde GCC, GOV oder EDU

Darüber hinaus Wenn Ihres Mandanten nicht für die Microsoft-Teams kommerziellen Cloud Testangebot ist, werden Sie nicht die Option **dazu, Benutzern das Installieren Studien apps und Dienste aus** angezeigt.

Auf der Ebene des Mandanten Teams als Dienst muss (in der Verwaltungskonsole des Teams) aktiviert werden soll. Weitere Informationen finden Sie unter [Microsoft-Teams, Verwalten von Features in Office 365-Organisation](enable-features-office-365.md). Darüber hinaus müssen Benutzer für apps und Testversionen (im Office 365 Administrationscenter) anmelden aktiviert werden. Weitere Informationen finden Sie unter [Verwalten der Testversion](#manage-the-trial) weiter unten in diesem Artikel.

## <a name="how-users-sign-up-for-the-trial"></a>Wie Benutzer für die Testversion anmelden

Berechtigte Benutzern können durch Anmeldung bei Teams ([teams.microsoft.com](https://teams.microsoft.com)) für die Testangebot registrieren. Wenn verfügbar sind, sehen sie in der folgenden Bildschirmrand aus, um die Testversion zu starten. 

![Screenshot der Startseite für die Testversion Teams Information Worker.](media/iw-trial-start-screen.png)

Die Information Worker Testversion gewährt eine Testversion 1 Jahr im gesamten Unternehmen. Zusätzliche berechtigte Benutzern in Ihrer Organisation können für Information Worker-Testversion von demselben Prozess durchgehen registrieren.
 
Alle Versuche innerhalb Ihrer Organisation freigeben, die gleiche Start- und Enddaten, welches das Datum ist der erste Benutzer für die Testversion angemeldet. Angenommen, wenn Benutzer A die erste Testversion auf 25 April 2018 und Benutzer B eine Testversion auf 3 Juni 2018 beginnt, läuft beide Benutzer Testversion auf 25 April 2019 ab.

## <a name="manage-the-trial"></a>Verwalten der Testversion

Administratoren können die Möglichkeit für Endbenutzer in trial apps und Dienste innerhalb ihrer Mandanten Anspruch zu deaktivieren. Derzeit die Testversion Teams nur Studien in dieser Kategorie ist, aber dies möglicherweise gelten für andere Programme ähnlich wie in der Zukunft. 

1\. Wechseln zu **Services & -add-ins**im [Office 365 Administrationscenter](https://portal.office.com/adminportal/home) > **Benutzer Apps und Diensten gehören**.

![Screenshot der Seite Dienste & -add-ins im Office 365 Administrationscenter.](media/iw-trial-enable-1.png)

2\. Deaktivieren Sie **dazu, Benutzern das Installieren Studien apps und Dienste aus**.

![Screenshot des Benutzers gehören Apps und Diensten Seite im Office 365 Administrationscenter.](media/iw-trial-enable-2.png)

3\. Sie können Teams für den Mandanten deaktivieren durch das Aufrufen der Verwaltungsportals von Teams. Wenn diese Option deaktiviert ist, können nicht Benutzer beansprucht werden, dass die Teams Testversion anbieten.

4\. Wenn Sie die Teams Dienstplan für einen einzelnen Benutzer, die eine Anspruch Lizenz besitzt deaktiviert haben, kann der Benutzer nicht berechtigt, eine Testlizenz beanspruchen.

5\. Wenn ein Benutzer eine Testlizenz Teams angefordert hat, können Sie ihn durch Entfernen des Lizenz oder Dienst Plans entfernen. 

![Screenshot der Seite Lizenzen Produkt im Office 365 Administrationscenter.](media/iw-trial-enable-3.png)

### <a name="upgrade-users-from-the-trial-license"></a>Aktualisieren Sie die Benutzer aus der Testlizenz

Um Benutzer aus der Testlizenz aktualisiert haben, führen Sie folgende Schritte aus:

1. Erwerben einer SKUs, die Teams enthält.
2. Entfernen der Teams Studien SKUs vom Benutzer.
3. Klicken Sie dann neu erworbene Lizenz zuweisen.

Weitere Informationen finden Sie unter [Office 365-Lizenzierung für Microsoft Teams](Office-365-licensing.md).