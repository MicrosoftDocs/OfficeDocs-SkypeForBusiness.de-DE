---
title: Erwerben, Konfigurieren und Aktivieren von Karrierecoach für Microsoft Teams
author: cichur
ms.author: v-mahoffman
ms.reviewer: alaina.creager
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Erfahren Sie, wie Sie E-Karrierecoach erwerben, konfigurieren und Microsoft Teams.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 33286dccf3d54ac694b4d74b736b6d899c035aa8
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60760543"
---
# <a name="purchase-configure-and-enable-career-coach-for-microsoft-teams"></a>Erwerben, Konfigurieren und Aktivieren von Karrierecoach für Microsoft Teams

Karrierecoach ist eine von LinkedIn Microsoft Teams für Education App, die personalisierte Anleitungen für Schüler/Studenten aus höheren Bildungseinrichtungen bietet, um auf ihren Karriereweg zu navigieren. Karrierecoach bietet Bildungseinrichtungen eine einheitliche Karrierelösung für Studenten, um ihren Karrierepfad zu entdecken, ihre echten Fähigkeiten zu erweitern und ihr Netzwerk an einem Ort zusammen aufzubauen.

## <a name="supported-languages"></a>Unterstützte Sprachen

Karrierecoach wird in den folgenden Sprachen lokalisiert:

- Chinesisch (vereinfacht, Kontinental china)
- Chinesisch (traditionell, Taiwan)
- Englisch (USA)
- Englisch (Großbritannien)
- Französisch (Kanada)
- Französisch (Frankreich)
- Deutsch (Deutschland)
- Japanisch (Japan)
- Portugiesisch (Brasilien)
- Spanisch (Spanien)
- Spanisch (Mexiko)

Weitere Informationen zu [Karrierecoach.](https://aka.ms/career-coach)

> [!TIP]
> Verwenden Sie die bewährten Methoden und hilfreichen Tipps in diesem Handbuch, um die Karrierecoach von Studierenden, Lehrkräften und Mitarbeitern zu aktivieren. Weitere Informationen finden [Sie im Artikel zum Schnellplanungshandbuch.](https://support.microsoft.com/office/c5d0b934-bfcf-4fe7-8a85-ba7bbb1b6ad4)

## <a name="review-the-requirements"></a>Überprüfen der Anforderungen

Wenn Sie Karrierecoach Bildungseinrichtung aktivieren möchten, überprüfen Sie, was Sie benötigen, um die App zu starten.

**Technische Anforderungen**

- Office 365-Mandant mit Azure Active Directory.

- Microsoft Teams.

- LinkedIn-Kontoverbindungen in Azure Active Directory.

**Lizenzen**

- Lehrpersonal

- Schüler/Studenten

> [!IMPORTANT]
> Dem KARRIERECOACH muss beim Abschließen der Konfiguration eine Lizenz für Lehrpersonal zugewiesen werden.

**Daten und Dateien von Ihrer Bildungseinrichtung**

- Logo und grafische Objekte der Bildungseinrichtung im erforderlichen Format.

- Kurskatalogdaten.

- Liste der angebotenen Lernfelder.

- LinkedIn-Seite der [Bildungseinrichtung.](https://www.linkedin.com/help/linkedin/answer/40133/differences-between-a-linkedin-page-for-a-school-and-company?lang=en)

- URL der Datenschutzrichtlinien der Bildungseinrichtung.

- Links in Bildungseinrichtungen zu karrierebezogenen Ressourcen wie Karrierediensten und Stellenausschreibungen für Studenten (optional).

- LinkedIn Learning Campus-Abonnement (bevorzugt).

## <a name="purchase-the-career-coach-licenses"></a>Erwerben der Karrierecoach Lizenzen

Karrierecoach ist weltweit (mit Ausnahme von China und Russland) für qualifizierte Hochschulen als Add-On-Lizenz über die Registrierung für Education-Lösungen (Enrollment for Education Solutions, EES), Cloud Service Providers (CSP) und Microsoft 365 Admin Center (Web Direct) verfügbar. Als Microsoft Teams-App müssen Kunden über Microsoft 365 A3/A5 oder Office 365 A1/A3/A5 verfügen, um das Add-On Karrierecoach kaufen zu können.

### <a name="assign-app-licenses-to-users"></a>Zuweisen von App-Lizenzen zu Benutzern

Eine schrittweise Anleitung finden Sie unter [Zuweisen von Lizenzen zu Benutzern.](/microsoft-365/admin/manage/assign-licenses-to-users)

### <a name="turn-on-linkedin-account-connections"></a>Aktivieren von LinkedIn-Kontoverbindungen

Karrierecoach müssen **die** Benutzer Ihrer Bildungseinrichtung in der Lage sein, ihr Microsoft 365-Konto mit ihrem linkedIn-Konto zu verbinden, das innerhalb eines Karrierecoach.

1. Melden Sie sich beim [Azure AD Admin Center mit](https://aad.portal.azure.com/) einem Konto an, das ein globaler Administrator für die Azure AD ist.

2. Wählen Sie **Benutzer aus.**

3. Wählen Sie **auf der** Seite Benutzer die Option **Benutzereinstellungen aus.**

4. **LinkedIn-Kontoverbindungen** müssen  auf Ja oder Ausgewählt **festgelegt sein,** damit Karrierecoach ordnungsgemäß konfiguriert ist.

   ![Integrieren von LinkedIn-Kontoverbindungen in die Organisation](/azure/active-directory/enterprise-users/media/linkedin-integration/linkedin-integration.png)

   > [!NOTE]
   > Es werden keine Daten freigegeben, bis die Benutzer der Verbindung ihrer Konten zustimmen.

   - Wählen **Sie Ja** aus, um den Dienst für alle Benutzer in Ihrer Bildungseinrichtung zu aktivieren.

   - Wählen **Sie Ausgewählte Gruppe** aus, um den Dienst nur für eine Gruppe ausgewählter Benutzer in Ihrer Bildungseinrichtung zu aktivieren.

Weitere Informationen finden Sie unter [LinkedIn-Kontoverbindungen in Azure Active Directory.](/azure/active-directory/enterprise-users/linkedin-integration)

## <a name="access-the-career-coach-app-settings"></a>Zugreifen auf die Karrierecoach-App-Einstellungen

Verwenden Microsoft Teams Admin Center, um Karrierecoach für Ihre Bildungseinrichtung zu konfigurieren und für Benutzer zu aktivieren.

> [!IMPORTANT]
> Sie müssen ein globaler Administrator oder ein Dienstadministrator Teams sein, um auf die Seite zugreifen zu können.

1. Melden Sie sich beim **[Teams Admin Center an.](https://admin.teams.microsoft.com)**

2. Wählen Sie im linken Navigationsbereich die Option **Teams Apps**  >  **[verwalten aus.](https://admin.teams.microsoft.com/policies/manage-apps)**  

3. Suchen Oder suchen Sie **nach Karrierecoach.**  

4. Wählen **Karrierecoach** aus, und wählen Sie **dann** Einstellungen.  

    ![Zeigt die Karrierecoach-App mit ausgewählter Einstellungen-Option an.](media/career-coach-app.png)

## <a name="configure-the-career-coach-app-settings"></a>Konfigurieren der Karrierecoach-App-Einstellungen

Karrierecoach verfügt über fünf Konfigurationskategorien:

- [Marke und Voreinstellungen](#brand-and-preferences) – erforderlich

- [LinkedIn-Verbindung](#linkedin-connection) – erforderlich

- [Kurskatalog](#course-catalog) – erforderlich

- [Studienfelder –](#fields-of-study) erforderlich

- [Anpassung](#customization)

> [!IMPORTANT]
> Marke und Einstellungen, LinkedIn-Konfiguration, Kurskatalog und  Studienfelder sind erforderlich, um die App effektiv für Studierende, Lehrkräfte und Mitarbeiter zu aktivieren.

### <a name="brand-and-preferences"></a>Marke und Voreinstellungen

Passen Karrierecoach an die Marke Ihrer Bildungseinrichtung an. Sie sind für die Einhaltung der Rechte anderer Personen, einschließlich der Urheberrechte und Markenrechte, verantwortlich.

> [!IMPORTANT]
> Dies ist ein erforderlicher Abschnitt– Karrierecoach kann nur aktiviert werden, wenn die Marke und die Einstellungen übermittelt werden.

![der Karrierecoach Brandingbereich des Admin Centers.](media/career-coach-brand.png)

1. Melden Sie sich beim **[Teams Admin Center an.](https://admin.teams.microsoft.com)**

2. Wählen **Teams Apps Apps**  >  **[verwalten](https://admin.teams.microsoft.com/policies/manage-apps)**  >  **Karrierecoach**  >  **und Einstellungen aus.**

3. Hochladen Symbol **für die Bildungseinrichtung aus.** Das Symbol wird überall Karrierecoach zum Identifizieren von Inhalten verwendet, die für Ihre Bildungseinrichtung eindeutig sind, Kurskatalogressourcen in der gesamten App sowie im Abschnitt "Reale Erfahrungen" des Dashboards. Das Symbol ist am besten wie folgt formatiert:

- Eine transparente PNG-Datei
- Seitenverhältnis von 1:1
- Maximale Größe von 64 px x 64 px

4. Hochladen Miniaturansicht **der Bildungseinrichtung aus.** Die Miniaturansicht wird für Kurskatalogressourcen in der gesamten App verwendet, wenn kein bestimmtes Bild für einen Kurs verfügbar ist. Die Miniaturansicht ist am besten wie folgt formatiert:

- PNG-Datei
- Seitenverhältnis von 16:9
- Maximale Größe von 360 px x 200 px

5. Fügen Sie **die URL für die Datenschutzrichtlinien der Bildungseinrichtung hinzu.** Wenn diese Richtlinie hinzugefügt wird, können Schüler/Studierende die Datenschutzrichtlinie in der App Karrierecoach überprüfen.

6. Wählen Sie **Absenden aus.**

### <a name="linkedin-connection"></a>LinkedIn-Verbindung

Die LinkedIn-Konfiguration verbindet Karrierecoach mit öffentlichen Absolventendaten von LinkedIn.

> [!IMPORTANT]
> Dies ist ein erforderlicher Abschnitt– Karrierecoach kann nur aktiviert werden, wenn die LinkedIn-Seitenverbindung überprüft wird.

#### <a name="add-the-linkedin-page"></a>Hinzufügen der LinkedIn-Seite
  
1. Melden Sie sich beim **[Teams Admin Center an.](https://admin.teams.microsoft.com)**

2. Wählen **Teams Apps Apps**  >  **[Karrierecoach](https://admin.teams.microsoft.com/policies/manage-apps)**  >    >  **LinkedIn-Verbindung verwalten aus.**

3. Suchen Sie die LinkedIn-Seite, indem Sie auf LinkedIn suchen und den Filter **School** auswählen. Oder setzen Sie sich mit einem Mitarbeiter aus dem Karrieredienst in Verbindung, um die richtige LinkedIn-Schulseite zu bestimmen. Weitere Informationen finden Sie unter [Identifizieren von LinkedIn-Seiten.](https://www.linkedin.com/help/linkedin/answer/40133/differences-between-a-linkedin-page-for-a-school-and-company?lang=en)

    ![Linkedin suchen Sie nach Schule.](media/career-coach-school-search.png)

4. Fügen Sie die LINKEDIn-Schulseiten-URL hinzu. Die URL muss eine Schulseite und keine Unternehmensseite sein und ist normalerweise als `https://www.linkedin.com/school/willow-university/` formatiert.

   ![Linkedin School-Beispiel.](media/career-coach-linkedin-page-url.png)

5. Wählen Sie **Absenden aus.**
#### <a name="verify-the-linkedin-page"></a>Überprüfen der LinkedIn-Seite 

> [!IMPORTANT]
> Die Überprüfung muss vom Superadministrator der LinkedIn-Seite Ihrer Bildungseinrichtung abgeschlossen werden.

1. Wenn die Bestätigung erfolgreich übermittelt wurde,  wird die Seite aktualisiert, damit der Bestätigungslink und der Ablauf **des Bestätigungslinks angezeigt werden.** Der Bestätigungslink läuft nach 30 Tagen ab.

   ![Linkedin Connections für die Karrieretrainer-App.](media/career-coach-linked-in.png)  

2. Kopieren Sie den Bestätigungslink, und teilen Sie ihn mit dem Superadministrator der LinkedIn-Seite Ihrer Bildungseinrichtung. Weitere Informationen zur Superadministratorrolle auf der LinkedIn-Seite finden Sie in der Dokumentation [für Administratoren der LinkedIn-Seite.](https://www.linkedin.com/help/linkedin/answer/102672)

3. Der Superadministrator der LinkedIn-Seite verwendet den eindeutigen Bestätigungslink, um Karrierecoach Ihrer Schule zuzuordnen. Weitere Informationen finden Sie in der zusätzlichen Dokumentation zur [LinkedIn-Seitenüberprüfung.](https://www.linkedin.com/help/linkedin/answer/102672)

   ![LinkedIn-Seitenüberprüfung im LinkedIn-Entwicklerportal.](media/career-coach-linkedin-verification.png)

### <a name="course-catalog"></a>Kurskatalog

Der Kurskatalog stellt die Kurse und Kurse dar, die Schülern von Ihrer Bildungseinrichtung angeboten werden.

> [!IMPORTANT]
> Dies ist ein erforderlicher Abschnitt Karrierecoach ohne einen Kurskatalog nicht aktiviert werden kann.

Diese Kurse werden innerhalb der App in zwei Bereichen verwendet:

- Kurse werden als Teil von Lernressourcen zurückgegeben.  

- Kurse und Metadaten des Kurses, z. B. Beschreibungen, werden verwendet, um Kursteilnehmern dabei zu helfen, ihre Fähigkeiten beim Hochladen eines Transkripts zu identifizieren.  

Um den Kurskatalog zu erstellen, erstellen Sie eine Liste aller Kurse, die an Ihrer Bildungseinrichtung vermittelt werden, und laden Sie sie als CSV-Datei hoch. Die App zeichnet aus dem Kurskatalog, um die Fähigkeiten eines Kursteilnehmers aus deren Transkription zu identifizieren und Kurse für den Kurs vorschlagen zu können.

#### <a name="add-the-course-catalog"></a>Hinzufügen des Kurskatalogs

1. Melden Sie sich beim **[Teams Admin Center an.](https://admin.teams.microsoft.com)**

1. Wählen **Teams Apps Apps** verwalten &gt; **[Karrierecoach](https://admin.teams.microsoft.com/policies/manage-apps)** &gt;  &gt; **Einstellungen** &gt; **Kurskatalog aus.**  

2. Hochladen Kurse im CSV-Format mit den erforderlichen Spalten: courseId, title und sourceLink. Jede Zeile muss Daten für jede der erforderlichen Spalten enthalten. _Die Einbeziehung der empfohlenen Felder verbessert die Benutzererfahrung für Schüler/Studenten durch die Rückgabe besserer Suchergebnisse und der Fähigkeitserkennung._

4. Wählen Sie **Absenden aus.**

   ![Kurskatalog der Karrieretrainer-App.](media/course-catalog.png)

#### <a name="course-catalog-document-format-and-schema"></a>Format und Schema des Kurskatalogdokuments

Das Dokument muss im CSV-Format mit einer maximalen Größe von 18 MB vorliegen. Das Dokument muss die erforderlichen Felder **(Kurstitel,** **Kurs-ID** und **Kurs-URL) enthalten.** 

> [!TIP]
> Beginnen Sie mit dem [Beispielkurskatalogdokument,]( https://aka.ms/career-coach/docs/it-admins/sample-catalog) um die richtige Formatierung sicherzustellen. _Die Einbeziehung der empfohlenen Felder verbessert die Benutzererfahrung für Schüler/Studenten durch die Rückgabe besserer Suchergebnisse und der Fähigkeitserkennung._

In der folgenden Tabelle sind die Elemente aufgeführt, die in den Kurskatalog enthalten sein müssen:

| Name             | Status      | Typ   | Beschreibung                                                                    |
|------------------|-------------|--------|--------------------------------------------------------------------------------|
| courseId         | Erforderlich    | Zeichenfolge | In der Regel ist die Kurs-ID dem zugeordnet, was in der Aufzeichnung generiert wird. |
| Title            | Erforderlich    | Zeichenfolge | In der Regel der Kurstitel.                                                      |
| sourceLink       | Erforderlich    | URL    | Websitelink zur Kursseite.                                               |
| Beschreibung      | Empfohlen | Zeichenfolge | Einführungstext für den Kurs.                                              |
| language         | Empfohlen | Zeichenfolge | Die Sprache des Kurses. Verwenden Sie Standardsprachcodes.                           |
| Format           | Empfohlen | Zeichenfolge | Unterrichtsmodus (Online, Video, persönlich).                                   |
| thumbnailLink    | Empfohlen | URL    | Link zur Miniaturansicht des Kursbilds.                                            |
| thumbnailAltText | Empfohlen | Zeichenfolge | Alternativtext zur Barrierefreiheit für das Bild                                           |
| educationLevel   | Empfohlen | Zeichenfolge | Lernstufe, z. B. Undergraduate/Graduate.                                       |
| Themen           | Empfohlen | Zeichenfolge | Themen oder Tags, die mit den in den Kursen vermittelten Fähigkeiten verknüpft sind.          |

### <a name="fields-of-study"></a>Studienfelder

Die Studienfelder sind Synonyme für Hauptbereiche von Interesse, akademischer Haupt- und Abschluss abschluss. Auf diese Titel verweisen Kursteilnehmer, wenn sie mit der Nutzung der App beginnen und mit dem Einrichten ihres personalisierten Profils beginnen.

> [!IMPORTANT]
> Dies ist ein Erforderlicher Abschnitt, der Karrierecoach ohne eine Liste von Studienfeldern nicht aktiviert werden kann.

#### <a name="add-the-fields-of-study"></a>Hinzufügen der Lernfelder

1. Melden Sie sich beim **[Teams Admin Center an.](https://admin.teams.microsoft.com)**
1. Wählen **Teams Apps Apps** verwalten &gt; **[Karrierecoach](https://admin.teams.microsoft.com/policies/manage-apps)** &gt;  &gt; **Einstellungen** &gt; **Studienfelder aus.**  

2. Hochladen ein Untersuchungsfeld im CSV-Format.

3. Wählen Sie **Absenden aus.**

#### <a name="fields-of-study-document-format-and-schema"></a>Felder des Studiendokumentformats und -schemas

Fügen Sie alle für Schüler/Studierenden verfügbaren Lernfelder hinzu, z. B. Technik, Englisch, Unternehmen und so weiter. Mit der Feldliste können Schüler/Studenten Lernfelder entdecken, die sie möglicherweise interessieren, und ihren Schwerpunktbereich zu ihrem Profil hinzufügen.

> [!TIP]
> Beginnen Sie mit dem [Beispielfeld des Lerndokuments,](https://aka.ms/career-coach/docs/it-admins/sample-fieldsofstudy) um die richtige Formatierung sicherzustellen.

In der folgenden Tabelle sind die Elemente aufgeführt, die in die Felder der Untersuchung ein-/aus-werden müssen:

| Name          | Status   | Typ   | Beschreibung                    |
|---------------|----------|--------|--------------------------------|
| fieldsOfStudy | Erforderlich | Zeichenfolge | Der Name des Lernfelds |

### <a name="customization"></a>Anpassung

Karrierecoach können so angepasst werden, dass sie für Ihre Bildungseinrichtung eindeutig sind. Die Anpassung unterstützt das Hinzufügen von Erfahrungen zum Dashboard. Es wird empfohlen, Links zu Jobcentern, Veranstaltungen, Karrierediensten, karrierebezogenen Veranstaltungen, Student-Clubs und anderen Ressourcen hinzuzufügen, die Schülern dabei helfen, echte Erfahrungen zu sammeln.

#### <a name="add-customized-experiences"></a>Hinzufügen von benutzerdefinierten Benutzerdefinierten Benutzerdefinierten

1. Melden Sie sich beim **[Teams Admin Center an.](https://admin.teams.microsoft.com)**

1. Wählen **Teams Apps Apps** verwalten &gt; **[Karrierecoach](https://admin.teams.microsoft.com/policies/manage-apps)** &gt;   >  **Einstellungen** &gt; **aus.**

2. Fügen Sie jeden Titel, jede URL und eine kurze Beschreibung hinzu.  
  
3. Wählen Sie **Absenden aus.**

## <a name="making-career-coach-available-to-your-organization"></a>Verfügbar Karrierecoach Daten für Ihre Organisation

Nachdem Karrierecoach für Ihre Organisation konfiguriert wurde. Führen Sie die folgenden Schritte aus, um Karrierecoach Organisation in einem Microsoft Teams.

### <a name="enable-the-app"></a>Aktivieren der App

Nachdem Sie die Konfiguration abgeschlossen haben, aktivieren Sie die App für Schüler/Studierende und lizenzierte Benutzer, damit diese zugriffen können, Karrierecoach.  
  
> [!IMPORTANT]
> Sie müssen über die Berechtigungen "Global Teams Administratorrolle" verfügen.

1. Melden Sie sich beim **[Teams Admin Center an.](https://admin.teams.microsoft.com)**

1. Wählen **Teams Apps Apps** verwalten &gt; **[](https://admin.teams.microsoft.com/policies/manage-apps)** &gt; **Karrierecoach** aus.

2. Verschieben Sie den Umschalter Status auf **Zulässig.**  

  > [!NOTE]
  > **Zulässig** bedeutet, dass die App für Benutzer in Ihrer Bildungseinrichtung verfügbar ist. Blockiert bedeutet, dass die App für Schüler/Studierende nicht verfügbar ist.

### <a name="add-career-coach-as-an-installed-app"></a>Hinzufügen Karrierecoach als installierte App

> [!IMPORTANT]
> Durch diesen Schritt wird sichergestellt, Karrierecoach Für Ihre Organisation ordnungsgemäß konfiguriert ist und die Kursteilnehmer ihre Karrierecoach.

1. Melden Sie sich beim **[Teams Admin Center an.](https://admin.teams.microsoft.com)**

2. Wählen **Teams Die** &gt; **Setuprichtlinien für Apps aus,** und wählen Sie ihre bevorzugte Richtlinie aus.
Wenn Sie nicht sicher sind, welche Richtlinie Sie verwenden sollen, finden [](/microsoftteams/easy-policy-setup-edu?tabs=students%2Cstudent-settings) Sie in der [Microsoft Teams-Dokumentation](/microsoftteams/policy-packages-edu) zur Richtlinienverwaltung weitere Informationen oder verwenden den Assistenten für Bildungsrichtlinien zum Konfigurieren einer Richtlinie für Microsoft Teams.

3. Wählen Sie unter Installierte Apps die **Option Apps hinzufügen aus.**

4. Suchen Sie im Bereich Installierte Apps hinzufügen nach den Apps, die Sie automatisch installieren möchten, wenn Benutzer Teams. Sie können Apps auch nach der App-Berechtigungsrichtlinie filtern. Wenn Sie Ihre App-Liste ausgewählt haben, wählen Sie **Hinzufügen aus.**

5. Klicken Sie auf **Speichern**.

> [!NOTE]
> Es kann einige Stunden dauern, bis Änderungen wirksam werden, wenn Sie eine Richtlinie bearbeiten oder zuweisen. Die Karrierecoach steht in der App erst nach Microsoft Teams Änderungen zur Verfügung.

### <a name="pin-the-app"></a>Anheften der App

Durch das anheften Karrierecoach wird die App für Schüler/Studenten barrierefreier und besser sichtbar.

1. Melden Sie sich beim **[Teams Admin Center an.](https://admin.teams.microsoft.com)**

2. Wählen **Teams Die** &gt; **Setuprichtlinien für Apps aus,** und wählen Sie ihre bevorzugte Richtlinie aus.
Wenn Sie nicht sicher sind, welche Richtlinie Sie verwenden sollen, finden [](/microsoftteams/easy-policy-setup-edu?tabs=students%2Cstudent-settings) Sie in der [Microsoft Teams-Dokumentation](/microsoftteams/policy-packages-edu) zur Richtlinienverwaltung weitere Informationen oder verwenden den Assistenten für Bildungsrichtlinien zum Konfigurieren einer Richtlinie für Microsoft Teams.

3. Wählen **Sie unter Angeheftet Apps** die Option Apps hinzufügen **aus.**

4. Suchen Sie **nach Karrierecoach**, und wählen Sie dann **Hinzufügen aus.**

5. Wählen Sie die Reihenfolge aus, in der die App angezeigt werden soll, und wählen Sie **dann Speichern aus.**

> [!NOTE]
> Die Kursteilnehmer werden in Microsoft Teams benachrichtigt, Karrierecoach angeheftet wurde.

Weitere Details finden Sie unter Verwalten [von App-Setuprichtlinien in Microsoft.](/microsoftteams/teams-app-setup-policies)


## <a name="troubleshooting"></a>Problembehandlung

- Wenn in der Karrierecoach-App die Karrierecoach wird zurzeit für Sie eingerichtet" angezeigt wird, wurden die erforderlichen Abschnitte __nicht abgeschlossen.__ Die folgenden __Abschnitte müssen__ abgeschlossen sein, bevor Karrierecoach verwendet werden kann: [Marke](#brand-and-preferences)und Einstellungen, [LinkedIn-Verbindung,](#linkedin-connection)Kurskatalog und [](#course-catalog) [Studienfelder.](#fields-of-study)

- CSVs für Kurskatalog und Studienbereich haben erforderliche Formate und eine maximale Größe von 18 MB. Verweisen Sie Karrierecoach auf das Schema [des Kurskatalogdokuments,](#course-catalog-document-format-and-schema) und Karrierecoach Lerndokumentschemas, um die richtige Konfiguration zu gewährleisten. [](#fields-of-study-document-format-and-schema)

- Auf Einstellungsseiten mit Pflichtfeldern wird die Seite nicht übermittelt, wenn die Felder nicht ausgefüllt wurden. Es wird keine Warnmeldung angezeigt. die Seite wird einfach nicht übermittelt.

- Beim ersten Konfigurieren Karrierecoach wird möglicherweise ein Fehlerbanner mit der Meldung "Die Einstellungen der App können nicht aktualisiert werden. Versuchen Sie es erneut." Der Grund dafür ist wahrscheinlich, dass der Mandant die Karrierecoach-App bereitgestellt hat, was bis zu 15 Minuten dauern kann. Warten Sie in diesem Fall 15 Minuten, bevor Sie die Übermittlung erneut einreichen.

- Wenn die Karrierecoach in der App nicht angezeigt Microsoft Teams, wurden die Richtlinienänderungen möglicherweise nicht wirksam. Es kann einige Stunden dauern, bis Richtlinienänderungen aktualisiert wurden. Die Karrierecoach steht in der App erst nach Microsoft Teams Änderungen zur Verfügung.

## <a name="removing-your-tenant-data"></a>Entfernen Ihrer Mandantendaten

Ihre Mandantendaten enthalten Informationen, die als Teil der Anwendungskonfiguration hochgeladen oder generiert werden. Um alle Daten innerhalb eines Karrierecoach-Mandanten zu löschen, lassen Sie den globalen Administrator Ihres Mandanten ein [Supportticket](https://edusupport.microsoft.com/support?product_id=career_coach) öffnen, das die endgültige Löschung der Mandantendaten anfordert. Beachten Sie, dass dieser Vorgang nicht rückgängig gemacht werden kann. Nach Abschluss des Entfernens der Daten wird die Karrierecoach-Anwendung wieder in ihren vorkonfigurierten, nicht personalisierten Zustand für alle Benutzer gesetzt, und ein Teams-Administrator muss die Anwendung erneut einrichten, um sie weiterhin verwenden zu können.

Im Folgenden wird das Verfahren zum Löschen erläutert:

- Ein Supportticket muss von einem globalen Mandantenadministrator eingereicht werden und deutlich angeben, dass die Daten Ihres Mandanten dauerhaft gelöscht werden sollen. **Es gibt keine Möglichkeit, den** Satz oder das Zeitfenster des Löschvorgangs zu beschränken.

- Nach der Archivierung wird das Supportticket nach einer Woche an die minimale Aufbewahrungsrichtlinie der Compliance erfüllt. Sie können den Vorgang während dieser Zeit abbrechen.

- Nach einer Woche stellt Karrierecoach Team sicher, dass alle daten im Zusammenhang mit dem Mandanten gelöscht werden. Der Microsoft-Support überwacht das Ticket und benachrichtigt Sie nach Abschluss des Löschvorgangs in nicht mehr als **30 Tagen.**


## <a name="resources"></a>Ressourcen

Die folgenden Ressourcen helfen Ihnen beim Planen Ihrer Karrierecoach App.

- [Willkommen bei Microsoft Teams](Teams-overview.md)

- [Bereitstellen von Teams](get-started-with-teams-resources-for-org-wide-rollout.md?tabs=SmallBusiness)

- [Übersicht über Teams und Kanäle in Microsoft Teams](teams-channels-overview.md)

- [Verwalten von Apps im Microsoft Teams Admin Center](manage-apps.md)

- [Online Virtual Orientation Kit](https://www.microsoft.com/education/remote-learning/virtual-orientation)

- [Beschränkungen und Spezifikation Teams Kanälen](limits-specifications-teams.md)

- [Schneller Einstieg mit der Administrator-Schulung für Microsoft Teams](ITAdmin-readiness.md)

- [Teams-Problembehandlung](/microsoftteams/troubleshoot/teams-welcome)

- [Verwalten von Richtlinien für App-Berechtigungen in Microsoft Teams](teams-app-permission-policies.md)
