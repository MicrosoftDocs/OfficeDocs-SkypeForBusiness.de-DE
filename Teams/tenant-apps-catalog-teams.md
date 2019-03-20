---
title: Veröffentlichen von Apps im App-Katalog eines Microsoft Teams-Mandanten
author: lolaj
ms.author: lolaj
manager: serdars
ms.date: 03/15/2019
ms.topic: article
ms.service: msteams
ms.reviewer: prem
description: Anleitung zum Veröffentlichen von apps im Microsoft-Teams Mandanten Apps Katalog.
localization_priority: Normal
search.appverid: MET150
f1keywords: ms.teamsadmincenter.apppolicies.publishtenantapps
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 909ed249ea4e408cbddcd52824a7cb0047504613
ms.sourcegitcommit: 28dd9b8ca3de35a73e4d6923eff5546925435b8b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2019
ms.locfileid: "30684072"
---
<a name="publish-apps-to-the-microsoft-teams-tenant-apps-catalog"></a>Veröffentlichen von Apps im App-Katalog eines Microsoft Teams-Mandanten
=======================================================

Der Katalog von Microsoft-Teams Mandanten Apps können zum Testen und Verteilen von Line-of-Business Applications für Ihre Organisation. 

Führen Sie kritischen geschäftlichen Funktionen für die Benutzer, Teams Mandanten App-Katalog können Sie Ihre LOB Anwendung verteilen, die speziell für Ihre Organisation erstellt wurden und dass Sie sich verlassen. 
 
Melden Sie sich an Ihren Teams Client mit Ihren Anmeldeinformationen globaler Administrator und Veröffentlichen von apps für Ihre Organisation. 

## <a name="publish-an-app-to-the-tenant-apps-catalog-from-the-teams-client"></a>Veröffentlichen einer app mit dem Mandanten Apps Katalog vom Client Teams

Hinweis: Sie müssen bei der Microsoft-Teams, Client mit Ihren globaler Administrator-Anmeldeinformationen zum Veröffentlichen von apps für Ihre Organisation angemeldet sein.

### <a name="get-a-teams-app-package"></a>Abrufen eines Teams app-Pakets

Eine app-Paket Teams wird mithilfe von [Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)erstellt. Nachdem Sie das app-Paket haben, können Sie Enterprise-app-Katalog hinzufügen. Während alle Benutzer in den Mandanten kann Ansicht der app-Katalog derzeit nur globale-Admins haben die Möglichkeit, veröffentlichen und verwalten. (Schließlich Teams-Admins kann auch dazu werden.)

### <a name="go-to-the-tenant-apps-catalog"></a>Wechseln Sie zu dem Mandanten Apps Katalog

Starten Sie den Client für Microsoft-Teams, und melden Sie sich mit Ihren Anmeldeinformationen globaler Administrator. Wählen Sie aus dem Microsoft-Teams Store den neuen Abschnitt mit dem Namen für Ihre Organisation bestimmte (in diesem Beispiel wird "Contoso"). Benutzer in Ihrer Organisation können apps im Katalog anzeigen und installieren Sie diese Teams, denen sie Mitglied sind. 

![Screenshot, der von den Teams App Store zeigt den app-Katalog.](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-apps-catalog"></a>Hinzufügen einer app mit dem Mandanten Apps-Katalog

Wählen Sie aus dem Speicher, **eine benutzerdefinierte Anwendung hochladen** > **für Contoso hochladen**.

![Screenshot, der von den Teams App Store zeigt den app-Katalog.](media/private-app-store-teams-image02.png)

(Sie können auch **für ich oder Meine Teams hochladen**, die Sideloading, aufgerufen wird, die die app nur für den oder die ausgewählten Teams verfügbar macht auswählen.) 

Navigieren Sie zu dem app-Paket, und wählen Sie sie aus.

![Screenshot, der von den Teams App Store zeigt den app-Katalog.](media/private-app-store-teams-image03.png)

Wenn Sie zu Ihrem Mandanten Apps Katalog zurückzukehren, wird die neue Enterprise-app vorhanden sein. Beachten Sie, dass nur Sie und Mitglieder Ihrer Organisation haben Zugriff auf diese app-Katalog.

### <a name="update-an-app-in-the-tenant-apps-catalog"></a>Aktualisieren einer app in den Mandanten App-Katalog

1. Wählen Sie aus Ihrem Mandanten Apps Katalog "**...**" Klicken Sie auf oben rechts von der app, die Sie aktualisieren möchten.
2. Navigieren Sie zu dem aktualisierten app-Paket, und wählen Sie sie aus.

![Screenshot, der von den Teams App Store zeigt den app-Katalog.](media/private-app-store-teams-image04.png)

Die app wird auf Version 2.0 überarbeitet werden. Sie werden auch die app für das gesamte Unternehmen aus diesem Menü löschen.

## <a name="use-the-office-365-admin-portal-to-manage-the-tenant-apps-catalog"></a>Mit dem Mandanten-App-Katalog verwalten der Office 365-Verwaltungsportals

Wenn Sie apps verfügen, Fehlerbehebungen erforderlich sind, Sie können vorübergehend apps über das Office 365-Admin-Portal deaktivieren, wählen Sie **Einstellungen** > **Services &-add-ins** > **Microsoft-Teams**. Zusätzlich zur vorherigen Einstellungen ist vorhanden jetzt ein Abschnitt für Ihr Unternehmen apps. Sie können auswählen, welche apps Sie aktivieren oder deaktivieren möchten.

![Screenshot, der von den Teams App Store zeigt den app-Katalog.](media/private-app-store-teams-image05.png)

Dies hindert die Benutzer am Interaktion mit der app, ohne dass die app vollständig gelöscht. Diese Steuerelemente bieten Administratoren zusätzliche Flexibilität und bestimmen, wann die Steuerung von apps im Unternehmen. 


