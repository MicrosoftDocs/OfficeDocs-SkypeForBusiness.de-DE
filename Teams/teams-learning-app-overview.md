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
description: Verwenden Sie Microsoft Viva Learning (private Vorschau), um einen zentralen Hub für das Lernen zu erstellen, in dem Mitarbeiter Inhaltsbibliotheken in einer Organisation freigeben, zuweisen und lernen können.
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

*Dieser Artikel enthält vorläufige Inhalte für Microsoft Viva Learning, das sich in der privaten Vorschau befindet.*

Microsoft Viva Learning (private Vorschau) ermöglicht Es Teams und Einzelpersonen in Ihrer Organisation, das Lernen zu einem natürlichen Bestandteil ihres Tages zu machen. Die App erstellt einen zentralen Hub in Teams, in dem Mitarbeiter Inhaltsbibliotheken in Ihrer Organisation freigeben, zuweisen und lernen können.

Administratoren legen Berechtigungen und Lerninhaltsquellen für Viva Learning (private Vorschau) zu. Lerninhalte können LinkedIn Learning, Microsoft Learn, Microsoft 365-Schulungen, in SharePoint online gespeicherte eigene Inhalte Ihrer Organisation und Drittanbieter umfassen, die von Viva Learning unterstützt werden (private Vorschau).

## <a name="admin-roles"></a>Administratorrollen

Zum Einrichten von Viva Learning (private Vorschau) benötigen Sie Berechtigungen wie folgt:

- Microsoft Teams-Administrator
- Globaler Microsoft 365-Administrator oder SharePoint-Administrator
- Knowledge Admin – Dies ist eine neue Rolle im Microsoft 365 Admin Center, die jedem Benutzer in der Organisation zugewiesen werden kann. Diese Rolle verwaltet die Lerninhaltsquellen der Organisation über das Microsoft 365 Admin Center. 

> [!TIP]
> Der Wissensadministrator sollte moderat technisch sein und über vorhandene SharePoint-Administratoranmeldeinformationen verfügen, vorzugsweise eine Person, die sich mit dem Bildungs-, Lern-, Schulungs- oder Mitarbeitererfahrungsteil der Organisation auskennt.
 
## <a name="manage-viva-learning-private-preview-in-the-teams-admin-center"></a>Verwalten von Viva Learning (private Vorschau) im Teams Admin Center

Der Teams-Administrator installiert Viva Learning (private Vorschau) aus dem App Store und wendet dann Setup-, Verwaltungs- und Berechtigungsrichtlinien über das Teams Admin Center an.

### <a name="manage-settings-for-viva-learning-private-preview"></a>Verwalten von Einstellungen für Viva Learning (private Vorschau)

Sie müssen ein Administrator im Teams Admin Center sein, um diese Aufgaben ausführen zu können.

Führen Sie die folgenden Schritte aus, um Einstellungen für Viva Learning zu verwalten:

1. Wechseln Sie in der linken Navigationsleiste des Teams Admin Centers zu **Teams-Apps**  >  **Apps verwalten.**

   ![Linke Navigation im Teams Admin Center mit Teams-Apps und Abschnitt "Apps verwalten"](media/learning-app-teams-manage-apps-nav.png)

2. Geben Sie **auf der** Seite Apps  verwalten im Suchfeld Die Suche nach der Teams Learning-App (private Vorschau) ein.

   ![Seite "Apps verwalten" im Teams Admin Center mit dem Suchfeld](media/learning-app-teams-manage-apps-page.png)

3. Auf der **Seite Lernen:**
   1. Wählen **Sie unter Status** die Option **Zum** Aktivieren der App zulässig aus.
   2. Wechseln Sie **auf der** Registerkarte Einstellungen im Abschnitt **App-Einstellungen** zum Microsoft 365 Admin Center, um Lerninhaltsquellen zu konfigurieren.

   ![Lernseite im Teams Admin Center mit dem Abschnitt Status- und App-Einstellungen](media/learning-app-teams-learning-page.png)

4. Wechseln **Sie nach** Verwalten von **App-Einstellungen** zu Berechtigungen und Einrichtungsrichtlinien, um Mitarbeitern, die im Rahmen der Teilnahme Ihrer Organisation an der privaten Vorschau Zugriff auf die App haben sollen, die Berechtigung zu erteilen.

> [!NOTE]
>  Wenn Sich Ihre Organisation im Rahmen des Teams TAP100-Programms in Ring 4.0 befindet, müssen Sie möglicherweise die folgenden Schritte unternehmen, um genehmigten Benutzern in Ring 3.0 den Zugriff auf Viva Learning (private Vorschau) zu ermöglichen.

Im Rahmen der privaten Vorschau wird Viva Learning (private Vorschau) in Ring 3.0 veröffentlicht. Wenn Sich Ihre Organisation in Ring 4.0 befindet, wird die App im App Store nicht angezeigt. Zum Testen der App müssen Sie eine Berechtigungsrichtlinie für benutzerdefinierte Apps erstellen, sie auf Alle Apps zulassen festlegen und sie genehmigten Benutzern von Ring 3.0 zuweisen.

   ![TAP-AppsPermission-Plcy-Seite mit Ausgewählter Option "Alle Apps zulassen"](media/learning-app-tap-appspermission-plcy.png)

## <a name="configure-learning-content-sources-in-the-microsoft-365-admin-center"></a>Konfigurieren von Lerninhaltsquellen im Microsoft 365 Admin Center

Die Administratoren für das Microsoft 365 Admin Center können Einstellungen im Zusammenhang mit Viva Learning verwalten (private Vorschau) und die Lerninhaltsquellen konfigurieren.

Der Administrator wählt aus, welche zusätzlichen Lerninhaltsquellen (z. B. SharePoint oder unterstützte Inhaltsanbieterquellen von Drittanbietern) benutzern von Viva Learning zur Verfügung stehen (private Vorschau). Der Administrator konfiguriert dann diese Quellen, um sicherzustellen, dass der Inhalt für die Suche und Ermittlung verfügbar ist und von den Mitarbeitern durchsucht werden kann, die Viva Learning verwenden (private Vorschau).

> [!NOTE]
>  Benutzer melden sich bei Nicht-Microsoft- und LinkedIn Learning Pro-Lernergebnissen in einem Browser oder eingebettetem Viewer an. Dieses konfigurierte Lernen unterliegt den separaten Lizenz-, Datenschutz- und Dienstbedingungen zwischen Ihrer Organisation und dem Drittanbieter und nicht den Bedingungen für Viva Learning (private Vorschau). Bevor Sie diese Art von Lernen auswählen, vergewissern Sie sich, dass eine Vereinbarung für Ihre Organisation und Ihre Benutzer vor ort ist.

### <a name="assign-the-knowledge-admin-role-optional"></a>Zuweisen der Rolle des Wissensadministrators [Optional]

Sie müssen ein globaler Microsoft 365-Administrator sein, um diese Aufgaben ausführen zu können.

Führen Sie die folgenden Schritte aus, um einen Wissensadministrator für Viva Learning zuzuordnen:

1.  Wechseln Sie in der linken Navigationsleiste des Microsoft 365 Admin Centers zu **Rollen.**

2.  Wählen Sie **auf der** Seite Rollen auf der Registerkarte **Azure AD** die Option Knowledge **Admin aus.**
 
3.  Wählen Sie **auf der** Seite Knowledge Admin im Abschnitt **Zugewiesene Administratoren** die Option **Hinzufügen** aus, und fügen Sie dann die Person hinzu, die Sie für die Rolle auswählen.

### <a name="configure-settings-for-the-learning-content-sources-for-viva-learning-private-preview"></a>Konfigurieren von Einstellungen für die Lerninhaltsquellen für Viva Learning (private Vorschau)

Sie müssen ein globaler Microsoft 365-Administrator oder Wissensadministrator sein, um diese Aufgaben ausführen zu können.

Führen Sie die folgenden Schritte aus, um Einstellungen für Lerninhaltsquellen in Viva Learning zu konfigurieren:

1.  Wechseln Sie im linken Navigationsbereich des Microsoft 365 Admin Centers zu **Einstellungen**  >  **für Organisationseinstellungen.**

2.  Wählen Sie auf der Seite **Organisationseinstellungen** auf der Registerkarte **Dienste** die Option **Lern-App (Vorschau) aus.**

     ![Seite "Einstellungen" im Microsoft 365 Admin Center mit der aufgelisteten Lern-App](media/learning-sharepoint-configure1.png)

3.  Wählen Sie **im Bereich Lern-App (Vorschau)** die Lerninhaltsquellen aus, die Sie für die Organisation konfigurieren möchten, und wählen Sie dann **Speichern aus.**

     ![Lernbereich im Microsoft 365 Admin Center mit Optionen für Inhaltsquellen](media/learning-sharepoint-configure2.png)

Unter allen vorhandenen Lernquellen sind einige standardmäßig aktiviert. Hierzu zählen folgende Punkte:

- LinkedIn Learning (kostenloser Inhalt)
- Microsoft Learn
- Microsoft 365-Schulung

> [!NOTE]
> Wenn Ihre Organisation über ein LinkedIn Learning Standard- oder Pro-Abonnement verfügt, wird das Inhaltsrepository für die Mitarbeiter in Ihrer Organisation entsperrt. Nur die Mitarbeiter, die über die Berechtigung verfügen, können das gesamte Inhaltsrepository verwenden. <br>Andere Quellen müssen möglicherweise manuell aktiviert oder konfiguriert werden. Lernquellen, die nicht von Microsoft stammen, werden zwischen Ihrer Organisation und dem Drittanbieter separat lizenziert. Sie müssen überprüfen, ob Sie sich für ihr Lernen für Sie und Ihre Benutzer angemeldet haben.

Um eine Lerninhaltsquelle zu aktivieren oder zu deaktivieren, aktivieren Sie das Kontrollkästchen neben der Quelle. Wenn eine Quelle aktiviert ist, wird ein Häkchen angezeigt.

## <a name="configure-sharepoint-as-a-learning-content-source"></a>Konfigurieren von SharePoint als Lerninhaltsquelle

Sie können SharePoint als Lerninhaltsquelle konfigurieren, um die eigenen Inhalte Ihrer Organisation in Viva Learning (private Vorschau) verfügbar zu machen.

### <a name="overview"></a>Übersicht

Der Wissensadministrator (oder globaler Administrator) stellt eine Website-URL zur Verfügung, zu der der Lerndienst einen leeren zentralen Speicherort – das Inhaltsrepository für Lern-Apps – in Form einer strukturierten SharePoint-Liste erstellen kann. Diese Liste kann von Ihrer Organisation verwendet werden, um Links zu unternehmensübergreifenden SharePoint-Ordnern mit Lerninhalten zu erstellen. Administratoren sind für das Sammeln und Kurieren einer Liste von URLs für Ordner verantwortlich. Diese Ordner sollten nur Inhalte enthalten, die in Viva Learning (private Vorschau) verfügbar gemacht werden können.

Viva Learning (private Vorschau) unterstützt die folgenden Dokumenttypen:

- Word, PowerPoint, Excel, PDF
- Audio (M4A)
- Video (MOV, MP4, AVI)

Weitere Informationen finden Sie in der [SharePoint Online-Dokumentation.](https://docs.microsoft.com/sharepoint/introductionlink) 

### <a name="permissions"></a>Berechtigungen

UrLs für Dokumentbibliotheksordner können von jeder beliebigen SharePoint-Website in der Organisation gesammelt werden. Viva Learning (private Vorschau) folgt allen vorhandenen Inhaltsberechtigungen. Daher sind nur Inhalte, für die ein Benutzer über die Berechtigung zum Zugriff verfügt, in Viva Learning (private Vorschau) durchsuchbar und sichtbar. Alle Inhalte in diesen Ordnern sind durchsuchbar, aber nur Inhalte, für die der einzelne Mitarbeiter Berechtigungen besitzt, können verwendet werden.

Das Löschen von Inhalten aus dem Repository Ihrer Organisation wird derzeit nicht unterstützt.

Führen Sie die folgenden Schritte aus, um unbeabsichtigt angezeigte Inhalte zu entfernen:

1.  Um den Zugriff auf die Dokumentbibliothek einzuschränken, wählen Sie **die** Option Aktionen anzeigen und dann Zugriff **verwalten aus.**
     
     ![Dokumentbibliotheksseite in SharePoint mit Option "Aktionen anzeigen" mit Hoher Zugriff verwalten.](media/learning-sharepoint-permissions2.png)

2.  Löschen Sie das ursprüngliche Dokument in der Dokumentbibliothek.

Weitere Informationen finden Sie unter [Freigeben und Berechtigungen in der modernen SharePoint-Benutzererfahrung.](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions) 

### <a name="learning-service"></a>Lerndienst

Der Lerndienst verwendet die bereitgestellten Ordner-URLs, um Metadaten aus allen Inhalten zu erhalten, die in diesen Ordnern gespeichert sind. Innerhalb von 24 Stunden nach der Bereitstellung der Ordner-URL im zentralen Repository können Mitarbeiter innerhalb von Viva Learning (private Vorschau) nach den Inhalten Ihrer Organisation suchen und diese verwenden. Alle Änderungen an Inhalten, einschließlich aktualisierter Metadaten und Berechtigungen, werden auch innerhalb von 24 Stunden im Lerndienst angewendet.

### <a name="configure-sharepoint-as-a-source"></a>Konfigurieren von SharePoint als Quelle

Sie müssen globaler Microsoft 365-Administrator, SharePoint-Administrator oder Wissensadministrator sein, um diese Aufgaben ausführen zu können.

Führen Sie die folgenden Schritte aus, um SharePoint als Lerninhaltsquellen in für Viva Learning (private Vorschau) zu konfigurieren:

1.  Wechseln Sie im linken Navigationsbereich des Microsoft 365 Admin Centers zu **Einstellungen**  >  **für Organisationseinstellungen.**
 
2.  Wählen Sie auf der Seite **Organisationseinstellungen** auf der Registerkarte **Dienste** die Option **Lern-App (Vorschau) aus.**

     ![Einstellungsseite im Microsoft 365 Admin Center mit aufgelisteter Liste von Viva Learning.](media/learning-sharepoint-configure1.png)

3.  Geben Sie im Bereich Lern-App **(Vorschau)** unter **SharePoint** die Website-URL der SharePoint-Website an, auf der Sie ein zentrales Repository von Viva Learning erstellen möchten.

     ![Lernbereich im Microsoft 365 Admin Center mit ausgewähltem SharePoint.](media/learning-sharepoint-configure2.png)

4.  Eine SharePoint-Liste wird automatisch auf der bereitgestellten SharePoint-Website erstellt.

     ![Neu erstellte SharePoint-Liste auf der SharePoint-Website.](media/learning-sharepoint-configure3.png)

     Wählen Sie in der linken Navigationsleiste der SharePoint-Website die Option **Websiteinhalte**  >  **Lern-App-Inhaltsrepository aus.** 

     ![SharePoint-Liste mit der Websiteinhaltsnavigation und dem Abschnitt Lern-App-Inhaltsrepository.](media/learning-sharepoint-configure4.png) 

5. Füllen Sie **auf der Seite Lern-App-Inhaltsrepository** die SharePoint-Liste mit URLs in die Lerninhaltsordner auf.

   1. Wählen **Sie Neu aus,** um den **Bereich Neues Element zu** sehen. 

       ![Seite "Lerninhaltsrepository" in SharePoint mit der Option Neu.](media/learning-sharepoint-configure5.png)
 
   2. Fügen Sie **im Bereich** Neues Element im Feld **Titel** einen Verzeichnisnamen Ihrer Wahl hinzu. Fügen Sie **im Feld Ordner-URL** die URL zum Lerninhaltsordner hinzu. Klicken Sie auf **Speichern**.

       ![Bereich "Neues Element" in SharePoint mit den Feldern "Titel" und "Ordner-URL".](media/learning-sharepoint-configure6.png)

   3. Die **Seite Lern-App-Inhaltsrepository** wird mit den neuen Lerninhalten aktualisiert.

       ![Seite "Lerninhaltsrepository" in SharePoint mit den aktualisierten Informationen.](media/learning-sharepoint-configure7.png)

> [!NOTE]
> Um einen breiteren Zugriff auf das Inhaltsrepository der Lern-App zu ermöglichen, wird in Kürze ein Link zur Liste in der Benutzeroberfläche von Viva Learning (private Vorschau) verfügbar sein, in der Benutzer Zugriff anfordern und letztendlich beim Auffüllen der Liste helfen können. Websitebesitzer und globale Administratoren müssen zugriff auf die Liste gewähren. Access ist nur für die Liste spezifisch und gilt nicht für die Website, auf der die Liste gespeichert ist.

### <a name="folder-url-document-library-curation"></a>Dokumentbibliothekskurierung der Ordner-URL

Standardmetadaten (z. B. geändertes Datum, erstellt von, Dokumentname, Inhaltstyp und Organisationsname) werden automatisch von der Microsoft Graph-API in Viva Learning (private Vorschau) gezogen.
 
Um die Allgemeine Ermittlung und Suchrelevanz des Inhalts zu verbessern, empfehlen wir das Hinzufügen einer **Spalte Beschreibung.**

Führen Sie die folgenden **Schritte** aus, um der Dokumentbibliotheksseite eine Spalte Beschreibung hinzuzufügen:

1.  Wählen Sie **auf der** Seite Dokumente die Option Spalte **hinzufügen aus.**

2. Wählen Sie **die Option Aktionen** anzeigen und dann Einzelne **Textzeile aus.**

     ![Seite "Dokumente" in SharePoint mit den Optionen "Aktionen anzeigen" mit hervorgehobener Textzeile](media/learning-sharepoint-curation1.png)

3. Fügen Sie **im Bereich** Spalte erstellen im Feld **Name** einen beschreibenden Namen für die Spalte hinzu. Klicken Sie auf **Speichern**.

     ![Erstellen Sie in SharePoint einen Spaltenbereich mit dem Namen und anderen Feldern.](media/learning-sharepoint-curation2.png)
 
4. Fügen Sie **auf der** Seite Dokumente in der Spalte **Beschreibung** benutzerdefinierte Beschreibungen für jedes Element hinzu. Wenn keine Beschreibung angegeben wird, stellt Viva Learning (private Vorschau) eine Standardmeldung zur Hervorhebung des Inhalts aus Ihrer eigenen SharePoint-Bibliothek zur Verfügung. 

     ![Seite "Dokumente" in SharePoint mit den Beschreibungen in der Spalte Beschreibung.](media/learning-sharepoint-curation3.png)
 
