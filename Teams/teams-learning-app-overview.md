---
title: Installieren, Verwalten und Zuweisen von Berechtigungen für Microsoft Viva Learning (private Vorschau)
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
description: Verwenden Sie Microsoft Viva Learning (private Vorschau), um einen zentralen Hub für das Lernen zu erstellen, in dem Mitarbeiter Inhaltsbibliotheken in der gesamten Organisation freigeben, zuweisen und daraus lernen können.
f1.keywords: ''
appliesto:
- Microsoft Teams
ms.custom: ''
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 3b99cdcd49dc35a558d6217e28bf57bbb8563827
ms.sourcegitcommit: b56727299d7ea47e23807114a4f5881e289c0b6a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/17/2021
ms.locfileid: "51880349"
---
# <a name="install-manage-and-assign-permissions-for-microsoft-viva-learning-private-preview"></a>Installieren, Verwalten und Zuweisen von Berechtigungen für Microsoft Viva Learning (private Vorschau)

*Dieser Artikel enthält vorläufige Inhalte für Microsoft Viva Learning in der privaten Vorschau.*

Microsoft Viva Learning (private Vorschau) befähigt Teams und Einzelpersonen in Ihrer Organisation, sich einen natürlichen Teil des Tages zu lernen. Die App erstellt einen zentralen Hub in Teams in dem Mitarbeiter Inhaltsbibliotheken in der gesamten Organisation freigeben, zuweisen und daraus lernen können.

Administratoren legen Berechtigungen für Learning Learning (private Vorschau) und lassen Lerninhaltsquellen zu. Lerninhalte können LinkedIn Learning, Microsoft Learn, Microsoft 365-Schulungen, die eigenen Inhalte Ihrer Organisation, die in SharePoint Online gespeichert sind, sowie Drittanbieter sein, die von Viva Learning (private Vorschau) unterstützt werden.

## <a name="admin-roles"></a>Administratorrollen

Zum Einrichten von Viva Learning (private Vorschau) benötigen Sie die berechtigungen wie folgt:

- Microsoft Teams Administrator
- Microsoft 365 globaler Administrator oder SharePoint administrator
- Knowledge Admin – Dies ist eine neue Rolle im Microsoft 365 Admin Center, die jedem Benutzer in der Organisation zugewiesen werden kann. Diese Rolle verwaltet die Lerninhaltsquellen der Organisation über Microsoft 365 Admin Center. 

> [!TIP]
> Der Wissensadministrator sollte etwas technischer Art sein und über vorhandene SharePoint-Administratoranmeldeinformationen verfügen, vorzugsweise über eine Person, die mit den Ausbildung-, Lern-, Schulungs- oder Mitarbeitererfahrungen in der Organisation vertraut ist.
 
## <a name="manage-viva-learning-private-preview-in-the-teams-admin-center"></a>Verwalten von Learning (private Preview) im Teams Admin Center

Der Teams installiert Viva Learning (private Preview) aus dem App Store und wendet dann Setup-, Verwaltungs- und Berechtigungsrichtlinien über das Teams Admin Center an.

### <a name="manage-settings-for-viva-learning-private-preview"></a>Verwalten der Einstellungen für Viva Learning (private Vorschau)

Sie müssen ein Administrator im Teams Admin Center sein, um diese Aufgaben ausführen zu können.

Führen Sie die folgenden Schritte aus, um Einstellungen für Viva Learning zu verwalten:

1. Navigieren Sie in der linken Navigationsleiste Teams Admin Center zu Apps **Teams**  >  **Apps verwalten**.

   ![Linke Navigationsleiste im Teams Admin Center mit Teams Apps und Abschnitt "Apps verwalten"](media/learning-app-teams-manage-apps-nav.png)

2. Geben Sie **auf der Seite Apps**  verwalten im Suchfeld Lernmodus ein, um nach der Teams Learning-App (private Vorschau) zu suchen.

   ![Seite "Apps verwalten" im Teams Admin Center mit dem Suchfeld](media/learning-app-teams-manage-apps-page.png)

3. Auf der **Seite Lernen:**
   1. Wählen **Sie unter Status** die Option **Zulässig** aus, um die App zu aktivieren.
   2. Wechseln Sie **Einstellungen** Registerkarte Lerninhalte  im Abschnitt App-Einstellungen zum Microsoft 365 Admin Center, um Lerninhaltsquellen zu konfigurieren.

   ![Learning page in the Teams admin center showing Status and App settings section](media/learning-app-teams-learning-page.png)

4. Wechseln **Sie nach** Verwalten von **App-Einstellungen** zu Berechtigungen und Einrichtungsrichtlinien, um Mitarbeitern, die im Rahmen der Beteiligung Ihrer Organisation an der privaten Vorschau Zugriff auf die App erhalten sollen, Berechtigungen zu erteilen.

> [!NOTE]
>  Wenn ihre Organisation im Rahmen des TAP1 Teams 00-Programms Ring 4.0 verwendet, müssen Sie möglicherweise wie folgt vordringen, um genehmigten Benutzern in Ring 3.0 den Zugriff auf Viva Learning (private Preview) zu ermöglichen.

Im Rahmen der privaten Preview wird Learning (private Vorschau) in Ring 3.0 veröffentlicht. Wenn in Ihrer Organisation Ring 4.0 verwendet wird, wird die App nicht im App Store angezeigt. Zum Testen der App müssen Sie eine Benutzerdefinierte App-Berechtigungsrichtlinie erstellen, sie auf Alle Apps zulassen festlegen und sie auf Genehmigte Benutzer der Ring-3.0-Richtlinie zuweisen. 

   ![TAP-AppsPermission-Plcy-Seite mit ausgewählter Option "Alle Apps zulassen"](media/learning-app-tap-appspermission-plcy.png)

## <a name="configure-learning-content-sources-in-the-microsoft-365-admin-center"></a>Konfigurieren von Lerninhaltsquellen im Microsoft 365 Admin Center

Die Administratoren für das Microsoft 365 Admin Center – entweder von sich selbst oder durch Zuweisen der Knowledge Admin-Rolle zu ausgewählten Personen in Ihrer Organisation – können Einstellungen im Zusammenhang mit Viva Learning (private Vorschau) verwalten und die Lerninhaltsquellen konfigurieren.

Der Administrator wählt aus, welche zusätzlichen Inhaltsquellen (z. B. SharePoint oder unterstützte Inhaltsanbieterquellen von Drittanbietern) Benutzern von Viva Learning (private Vorschau) zur Verfügung stehen. Der Administrator konfiguriert dann diese Quellen, um sicherzustellen, dass der Inhalt für die Suche und Ermittlung verfügbar ist und von den Mitarbeitern durchsucht werden kann, die Viva Learning (private Vorschau) verwenden.

> [!NOTE]
>  Benutzer melden sich bei nicht von Microsoft und LinkedIn Learning Pro Lernergebnissen in einem Browser oder eingebetteten Viewer an. Für dieses konfigurierte Lernen gelten die separaten Lizenz-, Datenschutz- und Servicebedingungen zwischen Ihrer Organisation und dem Drittanbieter und nicht die Nutzungsbedingungen von Viva Learning (private Preview). Bevor Sie diese Art von Lernen auswählen, überprüfen Sie, ob für Ihre Organisation und die Benutzer eine Vereinbarung in Übereinstimmung ist.

### <a name="assign-the-knowledge-admin-role-optional"></a>Zuweisen der Administratorrolle "Knowledge Admin" [Optional]

Sie müssen ein globaler Microsoft 365 sein, um diese Aufgaben ausführen zu können.

Führen Sie die folgenden Schritte aus, um einen Knowledge Admin für Viva Learning zuzuordnen:

1.  Navigieren Sie in der linken Navigationsleiste Microsoft 365 Admin Center zu **Rollen**.

2.  Wählen Sie **auf der** Seite Rollen auf der Registerkarte **Azure AD** die Option Knowledge **Admin aus.**
 
3.  Wählen Sie **auf der Seite Knowledge** Admin im Abschnitt Assigned **Admins** die Option **Hinzufügen** aus, und fügen Sie dann die Person hinzu, die Sie für die Rolle ausgewählt haben.

### <a name="configure-settings-for-the-learning-content-sources-for-viva-learning-private-preview"></a>Konfigurieren von Einstellungen für die Lerninhaltsquellen für Learning Learning (private Vorschau)

Sie müssen ein globaler Microsoft 365 oder Knowledge Admin sein, um diese Aufgaben ausführen zu können.

Führen Sie die folgenden Schritte aus, um Einstellungen für Lerninhaltsquellen in Learning zu konfigurieren:

1.  Navigieren Sie in der linken Navigationsleiste Microsoft 365 Admin Center zu Einstellungen  >  **Organisation .**

2.  Wählen Sie **auf der Seite Organisationseinstellungen** auf der Registerkarte **Dienste** die Option **Lern-App (Vorschau) aus.**

     ![Einstellungen seite im Microsoft 365 Admin Center mit der aufgelisteten Lern-App](media/learning-sharepoint-configure1.png)

3.  Wählen Sie **im Bereich Lern-App (Vorschau)** die Lerninhaltsquellen aus, die Sie für die Organisation konfigurieren möchten, und wählen Sie dann Speichern **aus.**

     ![Lernbereich im Microsoft 365 Admin Center mit Optionen für Inhaltsquellen](media/learning-sharepoint-configure2.png)

Unter allen vorhandenen Lernquellen sind einige standardmäßig aktiviert. Hierzu zählen folgende Punkte:

- LinkedIn Learning (kostenloser Inhalt)
- Microsoft Learn
- Microsoft 365 Schulung

> [!NOTE]
> Wenn Ihre Organisation über ein LinkedIn Learning Standard- oder Pro-Abonnement verfügt, wird das Inhaltsrepository für die Mitarbeiter in Ihrer Organisation entsperrt. Nur die Mitarbeiter, die über die Berechtigung verfügen, können das gesamte Inhaltsrepository verwenden. <br>Andere Quellen müssen möglicherweise manuell aktiviert oder konfiguriert werden. Lernquellen, die nicht von Microsoft stammen, werden separat zwischen Ihrer Organisation und dem Drittanbieter lizenziert. Sie müssen überprüfen, ob Sie sich für die Lernergebnisse für Sie und Ihre Benutzer angemeldet haben.

Um eine Lerninhaltsquelle zu aktivieren oder zu deaktivieren, aktivieren Sie das Kontrollkästchen neben der Quelle. Wenn eine Quelle aktiviert ist, wird ein Häkchen angezeigt.

## <a name="configure-sharepoint-as-a-learning-content-source"></a>Konfigurieren SharePoint als Quelle für Lerninhalte

Sie können SharePoint als Quelle für Lerninhalte konfigurieren, um die Inhalte Ihrer Organisation in Viva Learning (private Vorschau) verfügbar zu machen.

### <a name="overview"></a>Übersicht

Der Knowledge Admin (oder globaler Administrator) stellt eine Website-URL für den Speicherort zur Verfügung, an dem der Lerndienst einen leeren zentralen Speicherort – das Inhaltsrepository für Lern-Apps – in Form einer strukturierten Liste SharePoint kann. Diese Liste kann von Ihrer Organisation verwendet werden, um Links zu unternehmensübergreifenden Ordnern SharePoint die Lerninhalte enthalten. Administratoren sind dafür zuständig, eine Liste von URLs für Ordner zu sammeln und zu verwalten. Diese Ordner sollten nur Inhalte enthalten, die in Viva Learning (private Vorschau) zur Verfügung stehen können.

Learning (private Vorschau) unterstützt die folgenden Dokumenttypen:

- Word, PowerPoint, Excel, PDF
- Audio (M4A)
- Video (MOV, .mp4, .avi)

Weitere Informationen finden Sie in der [SharePoint Onlinedokumentation.](https://docs.microsoft.com/sharepoint/introductionlink) 

### <a name="permissions"></a>Berechtigungen

Dokumentbibliotheksordner-URLs können von jeder beliebigen Website SharePoint in der Organisation erfasst werden. Learning (private Vorschau) folgt allen vorhandenen Inhaltsberechtigungen. Daher können innerhalb von Viva Learning (private Vorschau) nur Inhalte durchsucht und angezeigt werden, für die ein Benutzer Über die Zugriffsberechtigung verfügt. Alle Inhalte in diesen Ordnern können durchsucht werden, aber nur Inhalte, für die der einzelne Mitarbeiter Berechtigungen besitzt, können verwendet werden.

Das Löschen von Inhalten aus dem Repository Ihrer Organisation wird derzeit nicht unterstützt.

Führen Sie die folgenden Schritte aus, um unabsichtlich angezeigte Inhalte zu entfernen:

1.  Wenn Sie den Zugriff auf die Dokumentbibliothek einschränken möchten, wählen Sie **die** Option Aktionen anzeigen und dann Zugriff **verwalten aus.**
     
     ![Dokumentbibliotheksseite in SharePoint zeigt die Option "Aktionen anzeigen" mit "Zugriff verwalten" mit "Zugriff verwalten" mit hoher Qualität.](media/learning-sharepoint-permissions2.png)

2.  Löschen Sie das ursprüngliche Dokument in der Dokumentbibliothek.

Weitere Informationen finden Sie unter [Freigabe und Berechtigungen in der modernen SharePoint.](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions) 

### <a name="learning-service"></a>Learning Service

Der Learning Service verwendet die bereitgestellten Ordner-URLs, um Metadaten aus allen In diesen Ordnern gespeicherten Inhalten zu erhalten. Innerhalb von 24 Stunden nach dem Angeben der Ordner-URL im zentralen Repository können Mitarbeiter innerhalb von Viva Learning (private Vorschau) nach den Inhalten Ihrer Organisation suchen und diese verwenden. Alle Änderungen an Inhalten, einschließlich aktualisierter Metadaten und Berechtigungen, werden ebenfalls innerhalb von 24 Stunden im Lerndienst angewendet.

### <a name="configure-sharepoint-as-a-source"></a>Konfigurieren SharePoint als Quelle

Sie müssen ein globaler Microsoft 365, ein SharePoint oder ein Knowledge Admin sein, um diese Aufgaben ausführen zu können.

Führen Sie die SharePoint folgenden Schritte aus, um Einen als Quellen für Lerninhalte in für Viva Learning (private Vorschau) zu konfigurieren:

1.  Navigieren Sie in der linken Navigationsleiste Microsoft 365 Admin Center zu Einstellungen  >  **Organisation .**
 
2.  Wählen Sie **auf der Seite Organisationseinstellungen** auf der Registerkarte **Dienste** die Option **Lern-App (Vorschau) aus.**

     ![Einstellungen Seite im Microsoft 365 Admin Center mit aufgelisteter Liste von Viva Learning.](media/learning-sharepoint-configure1.png)

3.  Geben Sie im Bereich Lern-App **(Vorschau)** unter **SharePoint** die Website-URL der SharePoint-Website an, auf der Viva Learning ein zentrales Repository erstellen soll.

     ![Learning panel in the Microsoft 365 Admin Center showing SharePoint selected.](media/learning-sharepoint-configure2.png)

4.  Eine SharePoint Wird automatisch auf der bereitgestellten Website SharePoint erstellt.

     ![Neu erstellte SharePoint auf der SharePoint-Website.](media/learning-sharepoint-configure3.png)

     Wählen Sie in der linken Navigationsleiste SharePoint Inhaltsrepository der Lern-App die **Option**  >  **Websiteinhalte aus.** 

     ![SharePoint liste mit der Navigation "Websiteinhalte" und dem Abschnitt "Inhaltsrepository für Lern-Apps".](media/learning-sharepoint-configure4.png) 

5. Füllen Sie auf der Seite Lern-App-Inhaltsrepository die Liste SharePoint urLs zu den Lerninhaltsordnern auf. 

   1. Wählen Sie **Neu** aus, um den **Bereich Neues Element** anzeigen. 

       ![Learning Content Repository page in SharePoint showing the New option.](media/learning-sharepoint-configure5.png)
 
   2. Fügen Sie **im Bereich Neues** Element im Feld **Titel** einen Verzeichnisnamen Ihrer Wahl hinzu. Fügen Sie **im Feld Ordner-URL** dem Lerninhaltsordner die URL hinzu. Klicken Sie auf **Speichern**.

       ![Bereich "Neues Element" in SharePoint mit den Feldern "Titel" und "Ordner-URL".](media/learning-sharepoint-configure6.png)

   3. Die **Seite Lern-App-Inhaltsrepository** wird mit den neuen Lerninhalten aktualisiert.

       ![Learning Content Repository page in SharePoint showing the updated information.](media/learning-sharepoint-configure7.png)

> [!NOTE]
> Um einen breiteren Zugriff auf das Inhaltsrepository der Lern-App zu ermöglichen, wird in Kürze ein Link zu der Liste in der Benutzeroberfläche von Learning (private Vorschau) verfügbar sein, wo Benutzer den Zugriff anfordern und letztendlich beim Auffüllen der Liste helfen können. Websitebesitzer und globale Administratoren müssen Zugriff auf die Liste gewähren. Access gilt nur für die Liste und nicht für die Website, auf der die Liste gespeichert ist.

### <a name="folder-url-document-library-curation"></a>Ordner-URL- Dokumentbibliotheks-Curation

Standardmetadaten (z. B. Änderungsdatum, erstellt mit, Dokumentname, Inhaltstyp und Organisationsname) werden von der Microsoft Graph-API automatisch in Viva Learning (private Vorschau) gespeichert.
 
Um die Relevanz der Erkennung und Suche für den Inhalt insgesamt zu verbessern, empfehlen wir, eine Spalte **Beschreibung** hinzufügen.

Führen Sie die folgenden **Schritte** aus, um der Dokumentbibliotheksseite eine Spalte Beschreibung hinzuzufügen:

1.  Wählen Sie **auf der** Seite Dokumente die Option Spalte **hinzufügen aus.**

2. Wählen Sie **die Option Aktionen** anzeigen und dann Eine **Textzeile aus.**

     ![Seite "Dokumente" in SharePoint zeigt die Optionen für "Aktionen anzeigen" mit hervorgehobener Option "Einzelne Textzeile".](media/learning-sharepoint-curation1.png)

3. Fügen Sie **im Bereich Spalte erstellen** im Feld **Name** einen aussagekräftigen Namen für die Spalte hinzu. Klicken Sie auf **Speichern**.

     ![Erstellen Sie einen Spaltenbereich in SharePoint mit dem Namen und anderen Feldern.](media/learning-sharepoint-curation2.png)
 
4. Fügen Sie **auf** der Seite Dokumente in **der Spalte Beschreibung** für jedes Element benutzerdefinierte Beschreibungen hinzu. Wenn keine Beschreibung angegeben wird, stellt Viva Learning (private Vorschau) eine Standardmeldung zur Verfügung, die hervorhebt, dass die Inhalte aus Ihrer SharePoint sind. 

     ![Seite "Dokumente" in SharePoint Beschreibungen in der Spalte Beschreibung.](media/learning-sharepoint-curation3.png)
 
