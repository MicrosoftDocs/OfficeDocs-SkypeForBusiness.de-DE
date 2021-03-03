---
title: Installieren, Verwalten und Zuweisen von Berechtigungen für die Teams -Lern-App (private Vorschau)
author: ChuckEdmonson
ms.author: chucked
manager: pamgreenMSFT
ms.date: ''
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ChrisArnoldMSFT, LearningDocs2020
localization_priority: Normal
search.appverid: ''
ms.collection: ''
description: Verwenden Sie die Microsoft Teams-Lern-App, um einen zentralen Hub für das Lernen zu erstellen, in dem Mitarbeiter Inhaltsbibliotheken in der gesamten Organisation freigeben, zuweisen und lernen können.
f1.keywords: ''
appliesto:
- Microsoft Teams
ms.custom: ''
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 6dd82c786c30fb4f2ac2ae70f2df6810cfe5d6ad
ms.sourcegitcommit: 75d710e3858f79ef601cd92e435a4a29dae0aba0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50285619"
---
# <a name="install-manage-and-assign-permissions-for-the-teams-learning-app-private-preview"></a>Installieren, Verwalten und Zuweisen von Berechtigungen für die Teams -Lern-App (private Vorschau)

*Dieser Artikel enthält vorläufige Inhalte für die Teams Learning-App, die sich in der privaten Vorschau befindet.*

Die Microsoft Teams -Lern-App (private Vorschau) versetzt Teams und Einzelpersonen in Ihrer Organisation in die Lage, das Lernen zu einem natürlichen Teil ihres Tages zu machen. Die App erstellt einen zentralen Hub in Teams, in dem Mitarbeiter Inhaltsbibliotheken in Ihrer Organisation freigeben, zuweisen und daraus lernen können. Administratoren legen Berechtigungen und lassen Lerninhaltsquellen für die App zu. Lerninhalte können LinkedIn Learning, Microsoft Learn, Microsoft 365-Schulungen, in SharePoint Online gespeicherte inhalte Ihrer Organisation und von der App unterstützte Drittanbieter umfassen.

Um die Teams -Lern-App (private Vorschau) einrichten zu können, müssen Sie:

-   Teams Admin Center Admin
-   Microsoft 365 Admin Center Admin Admin (ein globaler Administrator)

## <a name="manage-the-teams-learning-app-private-preview-in-the-teams-admin-center"></a>Verwalten der Teams -Learning-App (private Vorschau) im Teams Admin Center

Der Administrator von Teams installiert die Teams -Lern-App (private Vorschau) aus dem App Store und wendet Richtlinien für das Einrichten, Verwalten und Berechtigungen von Apps über das Teams Admin Center an.

### <a name="manage-the-teams-learning-app-private-preview"></a>Verwalten der Teams -Lern-App (private Vorschau)

Führen Sie die folgenden Schritte aus, um Einstellungen für die App zu verwalten:

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **"Apps**  >  **verwalten".**

   ![Linke Navigationsleiste im Teams Admin Center mit angezeigten Abschnitten "Teams-Apps" und "Apps verwalten"](media/learning-app-teams-manage-apps-nav.png)

2. Geben Sie **auf der Seite "Apps** verwalten" im Suchfeld "Lernen" ein, um nach der Teams -Lern-App zu suchen (private Vorschau). 

   ![Seite "Apps verwalten" im Teams Admin Center mit dem Suchfeld](media/learning-app-teams-manage-apps-page.png)

3. Auf der **Lernseite:**
   1. Wählen **Sie unter "Status"** die **Option "Zum** Aktivieren der App zulässig" aus.
   2. Wechseln Sie **auf der** Registerkarte "Einstellungen" im Abschnitt **"App-Einstellungen"** zum Microsoft 365 Admin Center, um Lerninhaltsquellen zu konfigurieren.

   ![Lernseite im Teams Admin Center mit Abschnitt "Status" und "App-Einstellungen"](media/learning-app-teams-learning-page.png)

4. Wechseln **Sie nach dem** Verwalten von **App-Einstellungen** zu "Berechtigungen" und "Richtlinien einrichten", um Mitarbeitern, die im Rahmen der Teilnahme Ihrer Organisation an der privaten Vorschau Zugriff auf die App erhalten sollen, Berechtigungen zu erteilen.

> [!NOTE]
>  Wenn Sich Ihre Organisation im Rahmen des Teams TAP100-Programms in Ring 4.0 befindet, müssen Sie möglicherweise die folgenden Schritte unternehmen, um genehmigten Benutzern in Ring 3.0 den Zugriff auf die Teams -Learning-App (private Vorschau) zu ermöglichen.

Im Rahmen der privaten Vorschau wird die Teams -Learning-App (private Vorschau) in Ring 3.0 veröffentlicht. Wenn sich Ihre Organisation in Ring 4.0 befindet, wird die App nicht im App Store angezeigt. Zum Testen der App müssen Sie eine Berechtigungsrichtlinie für benutzerdefinierte Apps erstellen, sie auf "Alle Apps zulassen" festlegen und sie benutzern mit Ring 3.0 zuweisen.

   ![Tap-AppsPermission-Plcy page showing Allow all apps selected](media/learning-app-tap-appspermission-plcy.png)

## <a name="configure-learning-content-sources-in-the-microsoft-365-admin-center"></a>Konfigurieren von Lerninhaltsquellen im Microsoft 365 Admin Center

Die Administratoren für das Microsoft 365 Admin Center können Einstellungen im Zusammenhang mit der Teams -Lern-App (private Vorschau) verwalten und die Lerninhaltsquellen konfigurieren.

Der Administrator kann auswählen, welche zusätzlichen Inhaltsquellen für Lerninhalte (z. B. SharePoint oder unterstützte Inhaltsanbieterquellen von Drittanbietern) den Benutzern der App zur Verfügung stehen sollen. Der Administrator konfiguriert dann diese Quellen, um sicherzustellen, dass der Inhalt für die Suche und Ermittlung verfügbar ist und von den Mitarbeitern durchsucht werden kann, die die App verwenden.

> [!NOTE]
>  Benutzer melden sich bei Nicht-Microsoft- und LinkedIn Learning Pro-Lernergebnissen in einem Browser oder eingebetteten Viewer an. Für dieses konfigurierte Lernen gelten die separaten Lizenz-, Datenschutz- und Dienstbedingungen zwischen Ihrer Organisation und dem Drittanbieter und nicht die Lernbedingungen (Vorschau). Bevor Sie dieses Lernvideo im Lernbereich (Vorschau) auswählen, vergewissern Sie sich, dass für Ihre Organisation und Ihre Benutzer eine Vereinbarung verfügbar ist.

### <a name="configure-settings-for-the-learning-content-sources-for-the-app"></a>Konfigurieren von Einstellungen für die Lerninhaltsquellen für die App

Diese Schritte müssen vom Microsoft 365-Administrator ausgeführt werden.

1.  Wechseln Sie in der linken Navigationsleiste des Microsoft 365 Admin Centers zu den **Einstellungen für**  >  **die Organisation.**

2.  Wählen Sie **auf der** Seite "Einstellungen" auf der & **"Dienste"** die Option **"Lern-App" aus.**

   ![Seite "Einstellungen" im Microsoft 365 Admin Center mit aufgelisteter Lern-App](media/learning-app-365-settings-page.png)

3.  Wählen Sie **im Bereich der Lern-App** die Lerninhaltsquellen aus, die Sie für die Organisation konfigurieren möchten, und wählen Sie dann "Speichern" **aus.**

   ![Bereich "Lern-App" im Microsoft 365 Admin Center mit Optionen für Inhaltsquellen](media/learning-app-365-settings-learning-app-panel.png)

Unter allen vorhandenen Lernquellen sind einige standardmäßig aktiviert. Hierzu zählen folgende Punkte:

- LinkedIn Learning (kostenloser Inhalt)
- Microsoft Learn
- Microsoft 365-Schulung

> [!NOTE]
> Wenn Ihre Organisation über ein LinkedIn Learning Standard- oder Pro-Abonnement verfügt, wird das Inhaltsrepository für die Mitarbeiter in Ihrer Organisation entsperrt. Nur die Mitarbeiter, die über die Berechtigung verfügen, können das gesamte Inhaltsrepository verwenden.

Andere Quellen müssen möglicherweise aktiviert oder manuell konfiguriert werden. Lernquellen, die nicht von Microsoft stammen, werden zwischen Ihrer Organisation und dem Drittanbieter separat lizenziert. Sie müssen überprüfen, ob Sie sich für deren Lernerfolge für Sie und Ihre Benutzer angemeldet haben.

Um eine Lerninhaltsquelle zu aktivieren oder zu deaktivieren, aktivieren Sie das Kontrollkästchen neben der Quelle. Wenn eine Quelle aktiviert ist, wird ein Häkchen angezeigt.

## <a name="configure-sharepoint-as-a-learning-content-source-coming-soon"></a>Konfigurieren von SharePoint als Quelle für Lerninhalte (in Kürze folgen)

Sie konfigurieren SharePoint als Lerninhaltsquelle für die Teams -Learning-App (private Vorschau) im Microsoft 365 Admin Center.

### <a name="overview"></a>Übersicht

Der Administrator stellt eine Website-URL für die Stelle zur Verfügung, an der der Lerndienst ein leeres zentrales Lerninhaltsrepository in Form einer strukturierten SharePoint-Liste erstellen kann. Diese Liste kann von der Organisation verwendet werden, um Links zu unternehmensübergreifenden SharePoint-Ordnern zu erstellen, die Lerninhalte enthalten. Administratoren sind für das Sammeln und Erstellen einer Liste von URLs für Ordner zuständig. Diese Ordner sollten nur Inhalte enthalten, die in der Teams -Lern-App (private Vorschau) verfügbar gemacht werden können.

### <a name="permissions"></a>Berechtigungen

Ordner-URLs können von jeder beliebigen SharePoint-Website in der Organisation erfasst werden. Alle Inhalte in diesen Ordnern können durchsucht werden, aber nur Inhalte, für die der einzelne Mitarbeiter Berechtigungen besitzt, können verwendet werden.
 
### <a name="learning-service"></a>Lerndienst

Der Lerndienst verwendet die bereitgestellten Ordner-URLs, um Metadaten aus allen Inhalten zu erhalten, die in diesen Ordnern gespeichert sind. Innerhalb von 24 Stunden nach dem Angeben der Ordner-URL im zentralen Repository können Die Mitarbeiter innerhalb der App nach Unternehmensinhalten suchen und diese verwenden. Das Löschen von Inhalten aus dem Repository wird an diesem Punkt nicht unterstützt. Unbeabsichtigt angezeigte Inhalte können nur entfernt werden, indem im Microsoft 365 Admin Center eine neue URL für die SharePoint-Website angegeben wird.

### <a name="configure-sharepoint-as-a-source"></a>Konfigurieren von SharePoint als Quelle

Diese Schritte müssen vom Microsoft 365-Administrator ausgeführt werden.

1.  Wechseln Sie in der linken Navigationsleiste des Microsoft 365 Admin Centers zu **"Einstellungen".**
 
2.  Wählen Sie **auf der** Seite "Einstellungen" auf der & **"Dienste"** die Option **"Lern-App" aus.**

   ![Seite "Einstellungen" im Microsoft 365 Admin Center mit aufgelisteter Lern-App](media/learning-app-365-settings-page.png)

3.  Geben Sie **im Bereich der** Lern-App die Website-URL der SharePoint-Website an, auf der die App ein zentrales Repository erstellen soll.

   ![Bereich "Lern-App" im Microsoft 365 Admin Center, in dem SharePoint ausgewählt ist](media/learning-app-365-panel-sharepoint-selected.png)

4.  Eine SharePoint-Liste wird automatisch auf der bereitgestellten Website der Organisation erstellt. Wählen Sie im linken Navigationsbereich der SharePoint-Website die Option **"Inhaltsrepository für Lern-Apps" aus.** 

   ![Linke Navigation in SharePoint mit dem Abschnitt "Inhaltsrepository der Lern-App"](media/learning-app-content-repository-nav.png)

 
5. Füllen Sie **auf der Seite "Inhaltsrepository** der Lern-App" die SharePoint-Liste mit URLs für die Lerninhaltsordner aus.

   1.   Wählen Sie **"Neu"** aus, um den **Bereich "Neues Element"** anzeigen. 

   ![Seite "Inhaltsrepository für Lern-Apps" in SharePoint mit der Option "Neu"](media/learning-app-content-repository-new.png)
 
   2.   Fügen Sie **im Bereich "Neues** Element" im Feld **"Titel"** einen Verzeichnisnamen Ihrer Wahl hinzu. Fügen Sie **im Feld "Ordner-URL"** die URL dem Lerninhaltsordner hinzu. Klicken Sie auf **Speichern**.

   ![Bereich "Neues Element" in SharePoint mit den Feldern "Titel" und "Ordner-URL"](media/learning-app-new-item-panel.png)

   3. Die Seite "Inhaltsrepository der Lern-App" wird mit den neuen Lerninhalten aktualisiert.

   ![Learning App Content Repository page in SharePoint showing the updated information](media/learning-app-content-repository-populated.png)


 


