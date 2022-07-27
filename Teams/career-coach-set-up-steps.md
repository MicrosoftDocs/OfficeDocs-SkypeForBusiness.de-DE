---
title: Einrichten und Konfigurieren von Career Coach für Microsoft Teams
author: SerdarSoysal
ms.author: serdars
ms.reviewer: alaina.creager
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Erfahren Sie, wie Sie Career Coach für Microsoft Teams einrichten, konfigurieren und verfügbar machen.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365initiative-edu
ms.custom:
- admindeeplinkTEAMS
- admindeeplinkMAC
appliesto:
- Microsoft Teams
ms.openlocfilehash: f162b4dc15a2c0b776ba3c9c3b0df8ac0ed2ce87
ms.sourcegitcommit: 3266fde54b92a18865d666b98e4e7e8322b9dedc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/26/2022
ms.locfileid: "67024177"
---
# <a name="set-up-and-configure-career-coach-for-microsoft-teams"></a>Einrichten und Konfigurieren von Career Coach für Microsoft Teams

Dieser Artikel richtet sich an IT-Administratoren im Hochschulbereich, um zu erfahren, wie Sie Career Coach für Microsoft Teams einrichten.

Die wichtigsten Schritte zum Einrichten, Konfigurieren und Freigeben von Career Coach sind:

1. [Schritt 1: Bereiten Sie Ihren Mandanten für Career Coach vor](#step-1-prepare-your-microsoft-365-tenant-for-career-coach).
1. [Schritt 2: Erwerben Von Career Coach-Lizenzen](#step-2-purchase-career-coach-licenses).
1. [Schritt 3: Zugreifen auf Einstellungen des Karrierecoachs](#step-3-access-the-career-coach-app-settings).
1. [Schritt 4: Konfigurieren der Einstellungen des Karrierecoachs](#step-4-configure-career-coach-settings).
1. [Schritt 5: Stellen Sie Career Coach für Ihre Institution zur Verfügung](#step-5-make-career-coach-available-to-your-institution).

## <a name="identify-roles-and-permissions"></a>Identifizieren von Rollen und Berechtigungen

Das Einrichten von Career Coach erfordert verschiedene Arten von Administratorrollen. Diese Rollen und Berechtigungen können einer Person zugewiesen werden oder die Zusammenarbeit mit IT-Experten in Ihrer Bildungseinrichtung erfordern. Verwenden Sie die nachstehende Checkliste, um die Personen zu identifizieren, die zum Ausführen der referenzierten Aufgaben erforderlich sind.

Sie können die zugewiesenen Rollen Ihres Kontos überprüfen, indem Sie die [Microsoft 365 Admin Center > Benutzer > Aktive Benutzer besuchen](https://go.microsoft.com/fwlink/p/?linkid=834822) > Ihren Benutzernamen auswählen, um Ihre Rolle zu bestätigen.

Weitere Informationen zu [Administratorrollen in der Microsoft 365 Admin Center](/microsoft-365/admin/add-users/about-admin-roles).

### <a name="microsoft-365-admin-center-tasks"></a>[Microsoft 365 Admin Center Aufgaben](https://go.microsoft.com/fwlink/p/?linkid=2024339)

Rolle: [Globaler Administrator](/azure/active-directory/roles/permissions-reference#global-administrator)

Career Coach Aufgaben:

- [Kaufen Sie Lizenzen](#step-2-purchase-career-coach-licenses).
- [Zuweisen von Lizenzen](#assign-career-coach-licenses-to-users).

### <a name="azure-active-directory-admin-center-tasks"></a>[Aufgaben im Azure Active Directory Admin Center](https://go.microsoft.com/fwlink/p/?linkid=2067268)

Rolle: [Globaler Administrator](/azure/active-directory/roles/permissions-reference#global-administrator)

Karrierecoach-Aufgabe:

- [Aktivieren Sie LinkedIn-Kontoverbindungen](#turn-on-linkedin-account-connections).

### <a name="teams-admin-center-tasks"></a>[Teams Admin Center-Aufgaben](https://admin.teams.microsoft.com/dashboard)

Rolle: [Teams-Administrator](/azure/active-directory/roles/permissions-reference#teams-administrator)

Career Coach Aufgaben:

- [Fügen Sie Career Coach als installierte App hinzu](#add-career-coach-as-an-installed-app).
- [Konfigurieren Sie die Einstellungen der Career Coach-App](#step-4-configure-career-coach-settings).
- [Richten Sie Richtlinien ein](#identify-roles-and-permissions).
- [Heften Sie die App an](#identify-roles-and-permissions).

### <a name="linkedin-developer-portal-tasks"></a>Aufgaben des LinkedIn-Entwicklerportals

Rolle: [LinkedIn School Page Super Admin](https://www.linkedin.com/help/linkedin/answer/a541981)

Karrierecoach-Aufgabe:

- [Überprüfen Sie die LinkedIn-Schulseite](#verify-the-linkedin-school-page).

## <a name="prepare-for-career-coach"></a>Vorbereitung auf Karrierecoach

Führen Sie vor dem Einrichten und Konfigurieren von Career Coach die folgenden Vorbereitungsschritte aus.

1. [Schritt 1: Bereiten Sie Ihren Mandanten für Career Coach vor](#step-1-prepare-your-microsoft-365-tenant-for-career-coach).
1. [Schritt 2: Erwerben Von Career Coach-Lizenzen](#step-2-purchase-career-coach-licenses).

### <a name="step-1-prepare-your-microsoft-365-tenant-for-career-coach"></a>Schritt 1: Vorbereiten Ihres Microsoft 365-Mandanten für Career Coach

#### <a name="turn-on-linkedin-account-connections"></a>Aktivieren von LinkedIn-Kontoverbindungen

Es gibt zwei Möglichkeiten, wie LinkedIn-Kontoverbindungen von Career Coach verwendet werden:

- Damit Studierende, Lehrkräfte und Mitarbeiter ihr Microsoft 365-Konto mit ihrem LinkedIn-Konto verbinden und [LinkedIn-Einladungen vom Career Coach senden](https://support.microsoft.com/topic/career-coach-quick-start-guide-for-students-c419db47-9290-4961-9684-c3f86a9b3708#bkmk_connect_your_linkedin_account) können.
- So aktivieren Sie die Features ["Netzwerk aufbauen"](https://support.microsoft.com/topic/career-coach-quick-start-guide-for-students-c419db47-9290-4961-9684-c3f86a9b3708#bkmk_build_your_network) und " [Karriere erkunden](https://support.microsoft.com/topic/career-coach-quick-start-guide-for-students-c419db47-9290-4961-9684-c3f86a9b3708#bkmk_discover_your_career_path) " mit öffentlichen Alumni-Daten von LinkedIn.

So aktivieren Sie LinkedIn-Kontoverbindungen:

1. Melden Sie sich mit einem [globalen Administratorkonto](#identify-roles-and-permissions) für die Azure [AD-Organisation beim Azure AD Admin Center](https://go.microsoft.com/fwlink/p/?linkid=2067268) an.

2. Wählen Sie **"Benutzer**" aus.

3. Wählen Sie auf der Seite **"Benutzer** " **die Option "Benutzereinstellungen"** aus.

4. **LinkedIn-Kontoverbindungen** müssen auf **"Ja** " oder " **Ausgewählte Gruppe** " festgelegt sein, damit Career Coach ordnungsgemäß konfiguriert ist.

   - Wählen Sie **"Ja** " aus, um den Dienst für alle Benutzer in Ihrer Bildungseinrichtung zu aktivieren.
   - Wählen Sie **"Ausgewählte Gruppe** " aus, um den Dienst nur für eine Gruppe ausgewählter Benutzer in Ihrer Bildungseinrichtung zu aktivieren.

Weitere Informationen finden Sie [unter LinkedIn-Kontoverbindungen in Azure Active Directory](/azure/active-directory/enterprise-users/linkedin-integration).

> [!NOTE]
> Ohne Zustimmung des Benutzers werden keine Daten freigegeben.

#### <a name="allow-microsoft-apps-in-teams"></a>Zulassen von Microsoft-Apps in Teams

Career Coach ist eine Microsoft-Anwendung und muss daher in Den Teams-App-Berechtigungsrichtlinien zulässig sein.

1. Melden Sie sich beim **[Teams Admin Center](https://go.microsoft.com/fwlink/p/?linkid=2066851)** an.

2. Wählen Sie im linken Navigationsbereich die **[Berechtigungsrichtlinien](https://admin.teams.microsoft.com/policies/manage-apps)** für **Teams-Apps** >  aus.

3. Wählen Sie Ihre bevorzugte Richtlinie aus.
    1. Wenn Sie nicht sicher sind, welche Richtlinie sie verwenden soll, lesen Sie die [Microsoft Teams-Richtlinienverwaltungsdokumentation](policy-packages-edu.md) , oder verwenden Sie den Assistenten  für [Education-Richtlinien](easy-policy-setup-edu.md), um eine Richtlinie für Microsoft Teams zu konfigurieren.

Weitere Informationen zum [Konfigurieren von Berechtigungsrichtlinien](teams-app-permission-policies.md).

#### <a name="add-career-coach-as-an-installed-app"></a>Hinzufügen von Career Coach als installierte App

Dieser Schritt stellt sicher, dass Career Coach ordnungsgemäß für Ihre Bildungseinrichtung konfiguriert ist und Studenten Career Coach finden können.

1. Melden Sie sich beim [Teams Admin Center](https://go.microsoft.com/fwlink/p/?linkid=2066851) an.

2. Wählen Sie **Setuprichtlinien** für **Teams-Apps** > und dann Ihre bevorzugte Richtlinie aus.
    1. Wenn Sie nicht sicher sind, welche Richtlinie sie verwenden soll, lesen Sie die [Microsoft Teams-Richtlinienverwaltungsdokumentation](policy-packages-edu.md) , oder verwenden Sie den Assistenten  für [Education-Richtlinien](easy-policy-setup-edu.md), um eine Richtlinie für Microsoft Teams zu konfigurieren.

3. Wählen Sie unter **"Installierte Apps**"  **die Option "Apps hinzufügen"** aus.

4. Suchen Sie im Bereich " **Installierte Apps hinzufügen** " nach den Apps, die Sie automatisch für Benutzer installieren möchten, wenn sie Teams starten. Sie können Apps auch nach App-Berechtigungsrichtlinie filtern.

5. Wenn Sie Ihre Liste der Apps ausgewählt haben, wählen Sie **"Hinzufügen"** aus.

6. Wählen Sie "**Speichern bestätigen"**  **aus** > .

Das Bearbeiten oder Zuweisen einer Richtlinie kann einige Stunden dauern, bis Änderungen wirksam werden. Der Karrierecoach ist erst in Microsoft Teams verfügbar, wenn die Änderungen abgeschlossen sind.

### <a name="step-2-purchase-career-coach-licenses"></a>Schritt 2: Erwerben von Career Coach-Lizenzen

#### <a name="license-types"></a>Lizenztypen

Career Coach benötigt eine Lizenz für den Zugriff auf die Anwendung.

Es sind zwei Lizenztypen verfügbar.

- Die **Student-Lizenz** ist für Schüler/Studenten ausgelegt.
- Die **Lehrpersonallizenz** wurde für Lehrkräfte, Mitarbeiter und IT-Experten entwickelt, die an der Unterstützung von Studierenden mit Career Coach beteiligt sind.
  - Eine Career Coach **Faculty-Lizenz** muss dem IT-Administrator zugewiesen werden, der die Konfiguration abschließt.

#### <a name="purchase-licenses"></a>Lizenzen kaufen

Career Coach ist weltweit (außer China und Russland) für qualifizierte Hochschulen als Add-On-Lizenz über Enrollment for Education Solutions (EES), Cloud Service Providers (CSP) und Microsoft 365 Admin Center (Web Direct) verfügbar.

Als Microsoft Teams-App muss der Mandant über Microsoft 365 A3/A5 oder Office 365 A1/A3/A5 verfügen, um die Lizenz für den Karrierecoach des Add-Ons erwerben zu können. Für Studierende und Lehrkräfte werden separate Lizenzen angeboten.

#### <a name="sign-up-for-a-free-trial"></a>Registrieren für eine kostenlose Testversion

Eine standardmäßige kostenlose Testversion von 90 Tagen ist für 25 Studierende und 25 Lehrpersonallizenzen verfügbar. Pro berechtigter Mandant ist eine Testversion verfügbar. Testlizenzen können von Microsoft 365 Admin Center von Mandanten aktiviert werden, die berechtigt sind, Career Coach-Lizenzen zu erwerben.

Melden Sie sich für die Testaktivierung [bei Microsoft 365 Admin Center > Abrechnung > Dienste kaufen > suchen Sie nach Career Coach](https://go.microsoft.com/fwlink/p/?linkid=868433), um die Testversion der [Studentenlizenz](https://signup.microsoft.com/signup?OfferId=b3a40ff2-3d0d-481e-a0ed-f4de1069f201) und die [Lizenz für Lehrkräfte](https://signup.microsoft.com/signup?OfferId=6f6e7db5-b9ab-4baa-86be-f13d0ae6a2c8) zu finden.

## <a name="set-up-and-configure-career-coach-settings"></a>Einrichten und Konfigurieren von Career Coach-Einstellungen

Führen Sie die folgenden Schritte aus, um Career Coach-Einstellungen für Ihre Bildungseinrichtung einzurichten und zu konfigurieren.

1. [Schritt 3: Zugreifen auf die Einstellungen der Career Coach-App](#step-3-access-the-career-coach-app-settings).
1. [Schritt 4: Konfigurieren der Einstellungen des Karrierecoachs](#step-4-configure-career-coach-settings).

### <a name="step-3-access-the-career-coach-app-settings"></a>Schritt 3: Zugreifen auf die Einstellungen der Career Coach-App

Um Career Coach-Einstellungen zu konfigurieren und für Benutzer zuzulassen, müssen Sie ein globaler Administrator oder Teams-Dienstadministrator sein, um auf die Seite zugreifen zu können.

1. Melden Sie sich beim [Teams Admin Center](https://go.microsoft.com/fwlink/p/?linkid=2066851) an.
2. Wählen Sie im linken Navigationsbereich **die Option "Teams-Apps** > **verwalten**" aus.
3. Suchen oder suchen Sie nach **Career Coach**.
4. Wählen Sie **"Karrierecoach**" und dann **"Einstellungen"** aus.

![Screenshot der ausgewählten Karrierecoach-App mit ausgewählter Registerkarte "Einstellungen".](media/career-coach-app-updated.png)

### <a name="step-4-configure-career-coach-settings"></a>Schritt 4: Konfigurieren von Einstellungen für den Karrierecoach

Um Career Coach für Studierende, Lehrkräfte und Mitarbeiter einzurichten, sind die folgenden Einstellungen erforderlich.

- [Marke und Präferenzen](#brand-and-preferences)
- [LinkedIn-Verbindung](#linkedin-connection)
- [Kurskatalog](#course-catalog)
- [Studiengebiete](#fields-of-study)

Sie können auch optionale [Anpassungseinstellungen](#customization-options) festlegen.

#### <a name="brand-and-preferences"></a>Marke und Präferenzen

Passen Sie Career Coach an die Marke Ihrer Bildungseinrichtung an. Sie sind dafür verantwortlich, die Rechte anderer Personen zu respektieren, einschließlich des Urheberrechts und der Markenrechte.

> [!IMPORTANT]
> Dies ist ein erforderlicher Abschnitt. Career Coach kann nicht aktiviert werden, ohne **Dass Marke und Vorlieben** eingereicht werden.

1. Melden Sie sich beim **[Teams Admin Center](https://go.microsoft.com/fwlink/p/?linkid=2066851)** an.

2. Auswählen von **Teams-Apps** > **Verwalten von Apps** > **Karrierecoacheinstellungen** >  > **Marke und Einstellungen bearbeiten**.

3. Fügen Sie unter **"Branding**" **den Namen der Organisation hinzu**.

4. Laden Sie das **Symbol "Organisation" hoch**. Das Symbol wird im gesamten Career Coach verwendet, um inhalte zu identifizieren, die für Ihre Bildungseinrichtung eindeutig sind, Kurskatalogressourcen in der gesamten App und im Abschnitt "Reale Erfahrungen" des Dashboards.

    Das Symbol ist am besten formatiert als:

    - Ein transparentes PNG
    - Seitenverhältnis von 1:1
    - Maximale Größe von 64 px x 64 px

5. Laden Sie die **Miniaturansicht des Lerninhalts hoch**. Die Miniaturansicht wird für Kurskatalog-Lernressourcen in der gesamten App verwendet, wenn für einen Kurs, der von Ihrer Bildungseinrichtung angeboten wird, kein bestimmtes Bild angegeben wird.

    Die Miniaturansicht ist am besten formatiert als:

    - A PNG
    - Seitenverhältnis von 16:9
    - Maximale Größe von 360 px x 200 px

6. Dies ist ein optionaler Schritt. Fügen Sie die **URL der Datenschutzrichtlinie der Organisation hinzu**. Wenn diese hinzugefügt werden, steht die Datenschutzrichtlinie der Bildungseinrichtung den Kursteilnehmern zur Überprüfung im Career Coach zur Verfügung.

7. Wählen Sie **"Absenden" aus**.

8. Um zu bestätigen, dass die Einstellungen erfolgreich übermittelt wurden, überprüfen Sie den [Konfigurationsstatus des Karrierecoachs](#configuration-status) auf **"Abgeschlossen**".

![Screenshot des Brandingabschnitts "Career Coach" im Admin Center.](media/career-coach-brand-updated.png)

#### <a name="linkedin-connection"></a>LinkedIn-Verbindung

Die LinkedIn-Verbindungseinstellung verbindet Career Coach mit öffentlichen Alumni-Daten von der LinkedIn School Page Ihrer Bildungseinrichtung.

Dieser Schritt kann nur ausgeführt werden, wenn [LinkedIn-Kontoverbindungen in Azure Active Directory aktiviert sind](#turn-on-linkedin-account-connections). Die LinkedIn-Verbindungseinstellung aktiviert die Features ["Netzwerk erstellen"](https://support.microsoft.com/topic/career-coach-quick-start-guide-for-students-c419db47-9290-4961-9684-c3f86a9b3708#bkmk_build_your_network) und " [Karriere erkunden](https://support.microsoft.com/topic/career-coach-quick-start-guide-for-students-c419db47-9290-4961-9684-c3f86a9b3708#bkmk_discover_your_career_path) ".

> [!IMPORTANT]
> Dies ist ein erforderlicher Abschnitt. Career Coach kann nicht aktiviert werden, ohne dass die LinkedIn School Page-Verbindung überprüft wurde.

##### <a name="add-the-linkedin-school-page-url"></a>Hinzufügen der LinkedIn-Schulseiten-URL

Der Vorgang zum Hinzufügen der LinkedIn School Page-URL wird von einem Teams-Administrator behandelt. Der nachfolgende Schritt zur Überprüfung der URL wird vom LinkedIn School Page Super-Administrator Ihrer Bildungseinrichtung abgeschlossen.

1. Melden Sie sich beim **[Teams Admin Center](https://go.microsoft.com/fwlink/p/?linkid=2066851)** an.

2. Auswählen von **Teams-Apps** > **Verwalten von Apps** > **Karrierecoacheinstellungen** >  > **LinkedIn-Verbindung**.

3. Wählen Sie **"Mit LinkedIn verbinden**" aus.

4. Suchen Sie die LinkedIn School Page Ihrer Bildungseinrichtung, indem Sie nach LinkedIn suchen **und den** Schulfilter auswählen. Oder stellen Sie eine Verbindung mit einem Marketingmitarbeiter in Ihrer Einrichtung her, um die richtige LinkedIn-Schulseite zu ermitteln. Weitere Informationen finden Sie unter [Identifizieren von LinkedIn-Seiten](https://www.linkedin.com/help/linkedin/answer/40133/differences-between-a-linkedin-page-for-a-school-and-company?lang=en).

    ![Screenshot, der die LinkedIn-Suche nach Schule zeigt.](media/career-coach-school-search-updated.png)

5. Fügen Sie die **LinkedIn School Page-URL hinzu**. Die URL muss eine *Schulseite* und keine *Unternehmensseite* sein und ist in der Regel als `https://www.linkedin.com/school/willow-university/`formatiert.

   ![Screenshot des LinkedIn School Page-Beispiels.](media/career-coach-linkedin-page-url-updated.png)

6. Wählen Sie **"Absenden" aus**.

7. Nachdem die **LinkedIn School Page-URL** erfolgreich übermittelt wurde, wird die Einstellungsseite aktualisiert, um den  **Überprüfungslink** und den  **Ablauf des Verifizierungslinks** anzuzeigen. Der Überprüfungslink läuft nach 30 Tagen ab.

8. Kopieren Sie den **Link "Überprüfung"** , und teilen Sie ihn mit dem LinkedIn School Page Super-Administrator Ihrer Bildungseinrichtung.

9. Der LinkedIn School Page Super-Administrator verwendet den eindeutigen Überprüfungslink, um [die LinkedIn School-Seite zu überprüfen](#verify-the-linkedin-school-page) und mit Career Coach zu verknüpfen.

10. Um zu bestätigen, dass die Überprüfung und die Einstellungen erfolgreich übermittelt wurden, überprüfen Sie, ob der [Career Coach-Konfigurationsstatus](#configuration-status) als **abgeschlossen** markiert ist.

##### <a name="verify-the-linkedin-school-page"></a>Überprüfen der LinkedIn-Schulseite

Die LinkedIn School Page-Überprüfung muss vom [LinkedIn School Page Super-Administrator](https://www.linkedin.com/help/linkedin/answer/a541981) Ihrer Bildungseinrichtung abgeschlossen werden.

Sie können die Administratorrollen Ihres LinkedIn-Kontos überprüfen, indem Sie sich bei LinkedIn anmelden und die LinkedIn-Schulseite Ihrer Bildungseinrichtung besuchen. Wenn Ihrem Konto eine Superadministratorrolle zugewiesen ist, wird auf der LinkedIn-Seite die **Ansicht "Superadministrator"** neben dem Namen Ihrer Bildungseinrichtung aufgeführt. Wenn das **Ansichtstag "Super-Administrator** " nicht angezeigt wird, sind Sie kein Superadministrator für die Seite Ihrer Schule.

1. Nachdem die **LinkedIn School Page-URL** vom Teams-Administrator übermittelt wurde, wird auf der Seite der **Überprüfungslink** und der **Ablauf des Verifizierungslinks** angezeigt. Der Überprüfungslink läuft nach 30 Tagen ab.

   ![Screnshot, der die LinkedIn-Verbindungen für die Karrierecoach-App zeigt.](media/career-coach-linkedin-updated.png)  

2. Kopieren Sie den Überprüfungslink, und teilen Sie ihn mit Ihrem LinkedIn School Page Super-Administrator.

3. Die LinkedIn-Seite "Super admin" öffnet den Verifizierungslink, um Career Coach der Seite Ihrer Bildungseinrichtung zuzuordnen. Weitere Informationen finden Sie [in der zusätzlichen Dokumentation zur LinkedIn-Seitenüberprüfung](https://www.linkedin.com/help/linkedin/answer/102672).

4. Sobald die Überprüfung abgeschlossen ist, kann der Teams-Administrator anzeigen, ob die Einstellungen erfolgreich übermittelt wurden, indem er überprüft, ob der [Konfigurationsstatus des Karrierecoachs](#configuration-status) als **abgeschlossen** markiert ist.

   ![Screenshot der LinkedIn-Seitenüberprüfung im LinkedIn-Entwicklerportal.](media/career-coach-linkedin-verification-updated.png)

#### <a name="course-catalog"></a>Kurskatalog

Der Kurskatalog zeichnet die Kurse und Kurse auf, die von Ihrer Bildungseinrichtung angeboten werden.

Career Coach verwendet Kurskatalogdaten, um die Fähigkeiten eines Kursteilnehmers anhand seiner Transkription zu identifizieren und Kurse vorzuschlagen, die er belegen soll.

> [!IMPORTANT]
> Dies ist ein erforderlicher Abschnitt. Career Coach kann nicht ohne einen Kurskatalog aktiviert werden.

Diese Kurse werden innerhalb von Career Coach in zwei Bereichen eingesetzt:

- Kurse werden als Teil der [Lernressourcen](https://support.microsoft.com/topic/career-coach-quick-start-guide-for-students-c419db47-9290-4961-9684-c3f86a9b3708#bkmk_grow_real_world_skills) zurückgegeben.  

- Kurse und Kursmetadaten, z. B. Kurstitel und -beschreibungen, werden verwendet, um den Kursteilnehmern zu helfen, ihre Fähigkeiten beim [Hochladen eines Transkripts](https://support.microsoft.com/topic/career-coach-quick-start-guide-for-students-c419db47-9290-4961-9684-c3f86a9b3708#bkmk_Set_up_your_profile) zu identifizieren.

Um den Kurskatalog zu erstellen, erstellen Sie eine Liste aller Kurse, die an Ihrer Bildungseinrichtung unterrichtet werden, und laden Sie sie als CSV-Datei mithilfe des [Kurskatalogdokumentformats und -schemas](#course-catalog-document-format-and-schema) hoch.

Beginnen Sie mit dem [Beispielkurskatalogdokument](https://aka.ms/career-coach/docs/it-admins/sample-catalog) , um die richtige Formatierung sicherzustellen.Sie können auch auf das [Dokumentformat und die Schemaabschnitte des Kurskatalogs](#course-catalog-document-format-and-schema) verweisen, um Details zu erforderlichen und empfohlenen Feldern zu erhalten.

##### <a name="add-the-course-catalog"></a>Hinzufügen des Kurskatalogs

1. Melden Sie sich beim **[Teams Admin Center](https://go.microsoft.com/fwlink/p/?linkid=2066851)** an.

2. Auswählen von **Teams-Apps** > **Verwalten von Apps** >**Suchkatalog** für **Karrierecoacheinstellungen** >  > .

3. Wählen Sie **Kurskatalog hochladen** > Kurse im CSV-Format mit den erforderlichen Spalten hochladen: courseId, title und sourceLink.
    1. Jede Zeile muss Daten für jede der erforderlichen Spalten enthalten.
    1. *Die Einbeziehung der empfohlenen Felder verbessert die Erfahrung für Schüler und Studenten, indem bessere Suchergebnisse und die Identifizierung von Fähigkeiten zurückgegeben werden.*

4. Als Referenz wird eine Vorschau eines Abschnitts des hochgeladenen Kurskatalogs angezeigt.

5. Wählen Sie **"Absenden** " aus, wenn Sie bereit sind.

6. Der [Status des hochgeladenen Dokuments](#course-catalog-status) wird auf der Einstellungsseite angezeigt.

7. Überprüfen Sie, ob der [Konfigurationsstatus des Karrierecoachs](#configuration-status) als **abgeschlossen** markiert ist, um zu bestätigen, dass die Einstellungen erfolgreich übermittelt wurden.

Um eine neue Datei hochzuladen, stellen Sie sicher, dass die letzte Datei gelöscht wird, indem Sie (X) auswählen, um die Dokumentvorschau zu schließen. Mit dieser Aktion kann die Schaltfläche " **Hochladen** " erneut angezeigt werden.

![Screenshot, der den Abschnitt "Kurskatalog" der Karrierecoach-App zeigt.](media/course-catalog-updated.png)

##### <a name="course-catalog-document-format-and-schema"></a>Format und Schema des Kurskatalogdokuments

Das Dokument muss im CSV-Format mit einer maximalen Größe von 18 MB vorliegen. Große Dateien sollten für eine erfolgreiche Verarbeitung in mehrere kleinere Dateien aufgeteilt werden, die maximal 15.000 Zeilen enthalten.

Das Dokument muss die erforderlichen Kursmetadaten enthalten: **Kurstitel**,  **Kurs-ID** und  **Kurs-URL**.

Beginnen Sie mit dem [Beispielkurskatalogdokument]( https://aka.ms/career-coach/docs/it-admins/sample-catalog) , um die richtige Formatierung sicherzustellen. *Die Einbeziehung der empfohlenen Felder verbessert die Erfahrung für Schüler und Studenten, indem bessere Suchergebnisse und die Identifizierung von Fähigkeiten zurückgegeben werden.*

In der folgenden Tabelle sind die Elemente aufgeführt, die in den Kurskatalog aufgenommen werden sollen.

| Name             | Status      | Typ   | Beschreibung                                                                    |
|------------------|-------------|--------|--------------------------------------------------------------------------------|
| courseId         | Erforderlich    | Schnur | Die courseId entspricht dem, was in der Transkription der Kursteilnehmer generiert wird.             |
| Titel            | Erforderlich    | Schnur | Der Kurstitel.                                                              |
| sourceLink       | Erforderlich    | URL    | Websitelink zur Kursseite, um mehr über den Kurs und den Lehrplan zu erfahren.   |
| Beschreibung      | Empfohlen | Schnur | Einführungstext für den Kurs, der die Lernziele beschreibt.       |
| language         | Empfohlen | Schnur | Sprache des Kurses. Verwenden Sie Standardsprachcodes.                           |
| Format           | Empfohlen | Schnur | Unterrichtsmodus (online, Video, persönlich).                                   |
| thumbnailLink    | Empfohlen | URL    | Miniaturansichtenlink zum Kursbild.                                            |
| thumbnailAltText | Empfohlen | Schnur | Barrierefreiheits-Alternativtext für das Bild                                           |
| educationLevel   | Empfohlen | Schnur | Studienstufe, z. B. Bachelor/Absolvent.                                       |
| Themen           | Empfohlen | Schnur | Themen oder Tags, die mit den Fähigkeiten verknüpft sind, die in den Kursen vermittelt werden.          |

##### <a name="course-catalog-status"></a>Kurskatalogstatus

Der Kurskatalogstatus wird auf der Seite "Einstellungen des Kurskatalogs" angezeigt, sobald ein Dokument hochgeladen wurde, und es werden Details zum Dokumentupload und zum Verarbeitungsstatus bereitgestellt.

Während der Verarbeitung analysiert Career Coach Ihr Dokument auf Duplikate, normalisiert und bereichert Ihren Katalog, indem er Fähigkeiten aus Titeln und Beschreibungen extrahiert und für die Verwendung auf der Seite "Lernen" und während der Uploads von Studententranskripten zur Identifizierung von Fähigkeiten speichert.

![Screenshot, der den Uploadstatus des Kurskatalogs der Karrierecoach-App zeigt.](media/career-coach-course-catalog-status-updated.png)

| Spalte           | Wert     | Beschreibung                                                                                        |
| ---------------- | --------- | -------------------------------------------------------------------------------------------------- |
| Hochgeladene Zeit    | Timestamp | Datum und Uhrzeit, zu der ein IT-Administrator ein Dokument hochgeladen hat.                                                     |
| Abgeschlossene Zeit   | Timestamp | Datum und Uhrzeit der vollständigen Verarbeitung des Dokuments.                                               |
| Hochgeladene Kurse | Ganze Zahl   | Anzahl der Im Dokument gefundenen Kurse.                                                           |
| Aufnahmestatus | Ausstehend   | Dokument in der Warteschlange für die Verarbeitung.                                                                  |
| Aufnahmestatus | Ausgeführte   | Das Dokument wird zurzeit verarbeitet. Dieser Vorgang kann je nach Größe Ihres Dokuments bis zu 6 Stunden dauern. |
| Aufnahmestatus | Erfolg   | Der Aufnahmeprozess ist abgeschlossen, und die Kurse sind im Career Coach verfügbar, sobald alle erforderlichen Einstellungen konfiguriert sind. |
| Aufnahmestatus | Fehlgeschlagen    | Überprüfen Sie das Dokumentformat, und laden Sie es erneut.                                                           |
| Duplikate       | Ganze Zahl   | Anzahl der doppelten Kurse, die im Dokument gefunden wurden.                                                 |

Wenn eine Spalte im Kurskatalogstatus leer ist, wird das Dokument zurzeit verarbeitet, und diese Werte sind nicht verfügbar. Dieser Vorgang kann je nach Größe Ihres Katalogs bis zu 6 Stunden dauern. Nachdem das Dokument verarbeitet wurde, werden die Werte aufgefüllt. Sie können die Seite aktualisieren, um nach Updates zu suchen.

#### <a name="fields-of-study"></a>Studiengebiete

Die Studienfelder sind gleichbedeutend mit wichtigen Interessengebieten, akademischen Haupt- und Studiengängen. Auf diese Studienfelder wird von den Studierenden verwiesen, wenn sie mit der Nutzung von Career Coach beginnen und mit der Einrichtung ihres personalisierten Profils beginnen.

Die Liste der Felder ermöglicht es Studierenden, Studienfelder zu entdecken, die sie interessieren können, und ihren geplanten akademischen Schwerpunkt zu ihrem Profil im Career Coach hinzuzufügen.

> [!IMPORTANT]
> Dies ist ein erforderlicher Abschnitt. Karrierecoach kann nicht ohne eine Liste von Studienfeldern aktiviert werden.
>
> Fügen Sie alle Studienfelder hinzu, die für Studierende verfügbar sind, z. B. Engineering, Englisch, Business usw.

##### <a name="add-the-fields-of-study"></a>Hinzufügen der Studienfelder

1. Melden Sie sich beim **[Teams Admin Center](https://go.microsoft.com/fwlink/p/?linkid=2066851)** an.

2. **Teams-Apps** >  auswählen **Apps verwalten** > **Karrierecoacheinstellungen** >  >  **durchsuchen Studienfelder**.

3. Wählen Sie **"Hochladen** " aus, um die Felder der Studiendatei im CSV-Format hochzuladen. Eine Vorschau der Felder des Studiendokuments wird angezeigt.

4. Wählen Sie **"Absenden" aus**.

5. Um zu bestätigen, dass die Einstellungen erfolgreich übermittelt wurden, überprüfen Sie, ob der [Konfigurationsstatus des Karrierecoachs](#configuration-status) als **abgeschlossen** markiert ist.

##### <a name="fields-of-study-document-format-and-schema"></a>Studiendokumentformat und -schema

Das Dokument muss im CSV-Format mit einer maximalen Größe von 18 MB vorliegen. Das Dokument muss die erforderlichen Metadaten enthalten: **Feld des Studiennamens**.

In der folgenden Tabelle sind die Elemente aufgeführt, die in die Studienfelder aufgenommen werden sollen:

| Name          | Status   | Typ   | Beschreibung                    |
|---------------|----------|--------|--------------------------------|
| fieldsOfStudy | Erforderlich | Schnur | Der Name des Studienfachs |

#### <a name="customization-options"></a>Anpassungsoptionen

Die Einstellung "Anpassung" unterstützt das Hinzufügen von Möglichkeiten, um dem Dashboard, das Ihre Bildungseinrichtung Kursteilnehmern bietet, praktische Erfahrungen zu bieten.

Die empfohlenen Links sollten schülern/studenten helfen, praktische Erfahrungen zu sammeln, z. B. Jobboards, Veranstaltungen, Büro für Karrieredienstleistungen, karrierebezogene Veranstaltungen und Studentenclubs.

1. Melden Sie sich beim **[Teams Admin Center](https://go.microsoft.com/fwlink/p/?linkid=2066851)** an.

2. Wählen Sie **Teams-Apps** > **"Apps verwalten**" > "**Karrierecoacheinstellungen** >  durchsuchen **"** aus.

3. Wählen Sie **"Benutzeroberfläche** >  anpassen **+ Hinzufügen"** aus.

4. Fügen Sie jeden **Titel**, jede **URL** und jede **Info-Tippbeschreibung** hinzu, > Wählen Sie **"Übernehmen"** aus.

5. Eine Vorschau der hinzugefügten Informationen wird angezeigt.

6. Wählen Sie **"Absenden" aus**.

### <a name="career-coach-settings-status"></a>Einstellungsstatus des Karrierecoachs

Die Einstellungsseite des Karrierecoachs im Teams Admin Center enthält eine Statuszusammenfassung unvollständiger, ausstehender, abgeschlossener und fehlgeschlagener Schritte zum Konfigurieren von Career Coach.

Mithilfe der Statusmeldung können Sie ermitteln, ob Career Coach ordnungsgemäß konfiguriert und bereit für die Freigabe für Ihren Mandanten ist.

#### <a name="configuration-status"></a>Konfigurationsstatus

Im Abschnitt "Konfigurationsstatus" der Seite "App-Einstellungen" wird der Echtzeitstatus mithilfe der folgenden Legende angezeigt.

![Screenshot des Konfigurationsstatusabschnitts der Karrierecoach-App.](media/career-coach-config-status-updated.png)

| Kategorie                    | Status                                        | Beschreibung                                                 |
| --------------------------- | --------------------------------------------- | ----------------------------------------------------------- |
| Dienstbereitstellungsstatus | Career Coach initialisiert Ihren Mandanten.     | Die Dienstbereitstellung erfolgt automatisch beim Zugriff auf die Einstellungsseite des Career Coach. Konfigurationsänderungen werden erst akzeptiert, wenn die erste Einrichtung abgeschlossen ist. Die geschätzte Zeit für die Dienstbereitstellung beträgt bis zu 15 Minuten. |
| Dienstbereitstellungsstatus | Career Coach ist bereit, konfiguriert zu werden.       | Die Einstellungsseite des Karrierecoachs ist für IT-Administratoren bereit, Einstellungen zu übermitteln. |
| Marke und Präferenzen       | Nicht gestartet                                   | Einstellungen müssen übermittelt werden. |
| Marke und Präferenzen       | Fehlt: Symbol "Lernen"                        | Laden Sie die Miniaturansicht fehlender Lerninhalte hoch. |
| Marke und Präferenzen       | Fehlt: Logo                                 | Laden Sie das Symbol "Fehlende Institution" hoch. |
| Marke und Präferenzen       | Fehlender Name: Name der Institution                     | Laden Sie den Namen der fehlenden Institution hoch. |
| Marke und Präferenzen       | Vollständig                                      | Weitere Maßnahmen sind nicht erforderlich. Die Einstellung ist abgeschlossen. |
| Kurskatalog hochladen       | Nicht gestartet                                   | Die CSV-Datei des Kurskatalogs muss übermittelt werden. |
| Kurskatalog hochladen       | Fehlt: ein erfolgreicher Kurskatalogupload   | Überprüfen Sie den Kurskatalogstatus, um Details zur Kurskatalogverarbeitung zu erhalten. |
| Kurskatalog hochladen       | Vollständig                                      | Weitere Maßnahmen sind nicht erforderlich. Die Einstellung ist abgeschlossen. |
| LinkedIn-Schulverbindung  | Nicht gestartet                                   | Die LinkedIn School Page-URL muss übermittelt werden. |
| LinkedIn-Schulverbindung  | Fehlt: eine genehmigte LinkedIn-Schulseiten-URL | Warten auf die Genehmigung der Überprüfung durch den Superadministrator von LinkedIn School Page. |
| LinkedIn-Schulverbindung  | Vollständig                                      | Weitere Maßnahmen sind nicht erforderlich. Die Einstellung ist abgeschlossen. |
| Studienfelder hochladen      | Nicht gestartet                                   | Das Studienfeld CSV muss eingereicht werden. |
| Studienfelder hochladen      | Fehlende: Interessante Bereiche                    | Überprüfen Sie, ob das Studienfeld erfolgreich hochgeladen wurde. |
| Studienfelder hochladen      | Vollständig                                      | Weitere Maßnahmen sind nicht erforderlich. Die Einstellung ist abgeschlossen. |

Sobald alle erforderlichen Schritte als abgeschlossen gekennzeichnet sind, kann Career Coach erfolgreich für Ihren Mandanten freigegeben werden.

## <a name="step-5-make-career-coach-available-to-your-institution"></a>Schritt 5: Stellen Sie Karrierecoach für Ihre Einrichtung zur Verfügung

An diesem Punkt wurde Career Coach für Ihre Einrichtung konfiguriert.

Führen Sie als Nächstes die folgenden Schritte aus, um sicherzustellen, dass Career Coach für Ihre Einrichtung in Microsoft Teams verfügbar ist.

### <a name="assign-career-coach-licenses-to-users"></a>Zuweisen von Career Coach-Lizenzen zu Benutzern

Eine schrittweise Anleitung finden Sie unter [Zuweisen von Lizenzen zu Benutzern](/microsoft-365/admin/manage/assign-licenses-to-users).

### <a name="set-up-policies-and-pin-the-app"></a>Einrichten von Richtlinien und Anheften der App

Das Anheften des Karrierecoachs fügt es an der linken Leiste des Microsoft Teams-Fensters hinzu, um es für Schüler und Studenten zugänglicher und sichtbarer zu machen. Wenn Sie Career Coach für eine Teilmenge Ihrer Benutzer anheften möchten, müssen Sie eine [Setuprichtlinie](teams-app-setup-policies.md) mit dieser Gruppe implementieren.

1. Melden Sie sich beim **[Teams Admin Center](https://go.microsoft.com/fwlink/p/?linkid=2066851)** an.

2. Wählen Sie **Setuprichtlinien** für **Teams-Apps** >  und dann Ihre bevorzugte Richtlinie aus.

    Wenn Sie nicht sicher sind, welche Richtlinie sie verwenden soll, lesen Sie die [Microsoft Teams-Richtlinienverwaltungsdokumentation](policy-packages-edu.md) , oder verwenden Sie den [Assistenten für Education-Richtlinien](easy-policy-setup-edu.md) , um eine Richtlinie für Microsoft Teams zu konfigurieren.

3. Wählen Sie unter **"Angeheftete Apps**" die Option **"Apps hinzufügen"** aus.

4. Wählen Sie ihre bevorzugte Richtlinie unter **"Suchen" basierend auf dieser App-Berechtigungsrichtlinie** aus.

5. Suchen Sie unter **"Nach Namen suchen**" nach **Karrierecoach**, und wählen Sie dann  **"Hinzufügen"** >  aus, um den Bereich zu schließen.

6. Wählen Sie die Reihenfolge aus, in der die App angezeigt werden soll, und wählen Sie **"Bestätigen"** aus.

Die Kursteilnehmer werden in Microsoft Teams benachrichtigt, dass der Karrierecoach angeheftet wurde.
