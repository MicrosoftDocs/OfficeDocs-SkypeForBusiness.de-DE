---
title: Erwerben, Konfigurieren und Aktivieren von Career Coach für Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: alaina.creager
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Hier erfahren Sie, wie Sie Career Coach für Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9911f880ba817afff10acb2a347a5c8c776d059c
ms.sourcegitcommit: 49cdcf344c63c805bcb6365804c6f5d1393e926a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2021
ms.locfileid: "52130026"
---
# <a name="purchase-configure-and-enable-career-coach-for-microsoft-teams"></a>Erwerben, Konfigurieren und Aktivieren von Career Coach für Microsoft Teams

Career Coach ist eine Microsoft Teams App für Bildungseinrichtungen, die von LinkedIn unterstützt wird und personalisierte Anleitungen für Hochschulstudenten zum Navigieren auf ihrem Karriereweg bietet. Career Coach bietet Bildungseinrichtungen eine einheitliche Karrierelösung für Schüler/ Studenten, die ihren Karrierepfad entdecken, reale Fähigkeiten entwickeln und ihr Netzwerk an einem Ort aufbauen können.

Erfahren Sie mehr über [Career Coach.](https://aka.ms/career-coach)

> [!NOTE]
> Verwenden Sie die bewährten Methoden und hilfreichen Tipps in diesem Leitfaden, um die Funktionen von Career Coach für Studierende, Lehrkräfte und Mitarbeiter zu aktivieren. Lesen Sie [den Artikel Schnellplanungshandbuch.](https://support.microsoft.com/office/c5d0b934-bfcf-4fe7-8a85-ba7bbb1b6ad4)

## <a name="review-the-requirements"></a>Überprüfen der Anforderungen

Wenn Sie Career Coach für Ihre Bildungseinrichtung aktivieren möchten, überprüfen Sie, was Sie benötigen, um die App in Betrieb zu halten.

**Technische Anforderungen**

  - Office 365 Mandant mit Azure Active Directory

  - Microsoft Teams

  - LinkedIn-Kontoverbindungen in Azure Active Directory

**Lizenzen**

  - Lehrpersonal 

  - Schüler/Studenten

> [!NOTE]
> Dem IT-Administrator, der die Konfiguration abgeschlossen hat, muss eine Career Coach Faculty-Lizenz zugewiesen werden.

**Daten und Dateien aus Ihrer Bildungseinrichtung**

  - Kurskatalogdaten

  - Angebotene Studienfelder

  - LinkedIn-Seite der Bildungseinrichtung

  - LinkedIn Learning -Campusabonnement (bevorzugt)

## <a name="purchase-the-career-coach-licenses"></a>Erwerben der Career Coach-Lizenzen

Career Coach steht weltweit (mit Ausnahme von China und Russland) für qualifizierte Hochschulen über Enrollment for Education Solutions (EES), Cloud Service Providers (CSP) und Microsoft 365 Admin Center (Web Direct) zur Verfügung. Als Microsoft Teams-App müssen Kunden über Microsoft 365 A3/A5 oder Office 365 A1/A3/A5 verfügen.

### <a name="assign-app-licenses-to-users"></a>Zuweisen von App-Lizenzen zu Benutzern

Schrittweise Anleitungen finden Sie unter [Zuweisen von Lizenzen zu Benutzern.](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)

### <a name="turn-on-linkedin-account-connections"></a>Aktivieren von LinkedIn-Kontoverbindungen

Career Coach **setzt voraus,** dass die Benutzer Ihrer Bildungseinrichtung über die Möglichkeit verfügen, ihr Microsoft 365-Konto mit ihrem LinkedIn-Konto zu verbinden, das in Career Coach erleichtert wird

1. Melden Sie sich beim [Azure AD Admin Center](https://aad.portal.azure.com/) mit einem Konto an, das ein globaler Administrator für die Azure AD-Organisation ist.

2. Wählen Sie **Benutzer aus.**

3. Wählen Sie **auf der** Seite Benutzer die Option **Benutzereinstellungen aus.**

4. Ermöglichen **Sie Benutzern unter LinkedIn-Kontoverbindungen,** ihre Konten in einigen Microsoft-Apps zu verbinden, um auf ihre LinkedIn-Verbindungen zu zugreifen. Es werden keine Daten freigegeben, bis die Benutzer der Verbindung ihrer Konten zustimmen.

   - Wählen **Sie Ja** aus, um den Dienst für alle Benutzer in Ihrer Bildungseinrichtung zu aktivieren.

   - Wählen **Sie Ausgewählte Gruppe** aus, um den Dienst nur für eine Gruppe ausgewählter Benutzer in Ihrer Bildungseinrichtung zu aktivieren.

   - Wählen **Sie Nein** aus, um die Zustimmung aller Benutzer in Ihrer Bildungseinrichtung zu widerrufen.

Erfahren Sie, wie [Sie LinkedIn-Kontoverbindungen in Azure Active Directory](/azure/active-directory/enterprise-users/linkedin-integration)

## <a name="configure-career-coach-in-the-teams-admin-center"></a>Konfigurieren von Career Coach im Teams Admin Center

Mithilfe der Administratoreinstellungen im Microsoft Teams Admin Center können Sie Career Coach für Ihre Bildungseinrichtung konfigurieren und für Benutzer aktivieren.

## <a name="access-the-career-coach-app-settings"></a>Zugreifen auf die Einstellungen der Career Coach-App

Verwenden Sie die Seite Apps [verwalten,](/microsoftteams/manage-apps) um die Teams im App-Katalog Ihrer Bildungseinrichtung anzeigen.

1. Melden Sie sich beim **Teams Admin Center an.**

2. Wählen Sie im linken Navigationsbereich die **option Teams Apps Verwalten** von Apps  >  **aus.**  

    > [!NOTE]
    > Sie müssen ein globaler Administrator oder Teams dienstadministrator sein, um auf die Seite zugreifen zu können.

3. Suchen oder suchen Sie nach **Career Coach.**  

4. Wählen **Sie Karrierecoach** und dann **Einstellungen.**  

    ![zeigt die ausgewählte Career Coach-App mit der option Einstellungen](media/app-settings.png)

### <a name="configure-the-career-coach-app-settings"></a>Konfigurieren der Einstellungen der Career Coach-App

Career Coach hat fünf Konfigurationskategorien:

- [Marke und Vorlieben](#brand-and-preferences)

- [LinkedIn-Konfiguration](#linkedin-configuration)

- [Kurskatalog](#course-catalog)

- [Studienfelder](#fields-of-study)

- [Anpassung](#customization)

> [!NOTE]
> Marke und Einstellungen, LinkedIn-Konfiguration, Kurskatalog und  Studienfelder sind erforderlich, um die App für Studierende, Lehrkräfte und Mitarbeiter effektiv zu aktivieren.

#### <a name="brand-and-preferences"></a>Marke und Vorlieben

Legen Sie den Namen, das Logo und die Standardsprache Ihrer Bildungseinrichtung auf der Seite mit den Einstellungen für Marke und Einstellungen ein.

![der Brandingbereich von Career Coach im Admin Center](media/brand-preferences.png)

##### <a name="educational-institution-icon"></a>Symbol für Bildungseinrichtung

Das Symbol für Bildungseinrichtungen wird im gesamten Career Coach verwendet, um Inhalte zu identifizieren, die für Ihre Bildungseinrichtung eindeutig sind, Kurskatalogressourcen in der gesamten App und im Abschnitt "Reale Erfahrungen" des Dashboards. Das Symbol ist am besten wie folgt formatiert:

 - Ein transparentes PNG
 - Seitenverhältnis von 1:1
 - Maximale Größe von 64 px x 64 px.

##### <a name="educational-institution-thumbnail"></a>Miniaturansicht der Bildungseinrichtung

Das Symbol für Bildungseinrichtungen wird für Kurskatalogressourcen in der gesamten App verwendet, wenn für einen Kurs kein bestimmtes Bild verfügbar ist. Das Symbol ist am besten wie folgt formatiert:

- EIN PNG
- Seitenverhältnis von 16:9
- Maximale Größe von 360 px x 200 px.

#### <a name="linkedin-configuration"></a>LinkedIn-Konfiguration

Die LinkedIn-Konfiguration verbindet Career Coach mit öffentlichen Alumnidaten von LinkedIn.

> [!NOTE]
> Career Coach kann nicht aktiviert werden, ohne dass die LinkedIn-Seitenverbindung überprüft wurde.

##### <a name="add-and-confirm-the-linkedin-page"></a>Hinzufügen und Bestätigen der LinkedIn-Seite

Bestimmen Sie die LinkedIn-Seite der Bildungseinrichtung. Suchen Sie die LinkedIn-Seite, indem Sie auf LinkedIn suchen oder eine Verbindung mit einem Mitarbeiter des Karrieredienstes herstellen, um die richtige Seite zu ermitteln.  
  
1. Melden Sie sich beim **Teams Admin Center an.**

1. Wählen **sie Teams Apps**  >  **Career** Coach  >    >  **LinkedIn-Verbindung verwalten aus.**

2. Geben Sie die LinkedIn-Seiten-URL Ihrer Bildungseinrichtung ein.  

3. Wählen Sie **Übernehmen aus.**

4. Kopieren Sie die Überprüfungs-URL, und teilen Sie sie mit der LinkedIn-Seite des LinkedIn-Seitenadministrators [der LinkedIn-Seite der Bildungseinrichtung.](https://www.linkedin.com/help/linkedin/answer/4783/linkedin-page-admins-overview?lang=en) Der Überprüfungslink läuft nach 30 Tagen ab.  

   ![Linkedin-Einstellungen für den Karrierecoach](media/linkedin.png)  

#### <a name="course-catalog"></a>Kurskatalog

Der Kurskatalog stellt die Kurse und Kurse dar, die den Kursteilnehmern von Ihrer Bildungseinrichtung angeboten werden. Diese Kurse werden in der App in zwei Bereichen verwendet:

- Kurse werden als Teil der Lernressourcen zurückgegeben.  

- Kurse und Kursmetadaten, z. B. Beschreibungen, werden verwendet, um Kursteilnehmern zu helfen, ihre Fähigkeiten beim Hochladen eines Transkripts zu erkennen.  

Zum Erstellen des Kurskatalogs erstellen Sie eine Liste aller Kurse, die an Ihrer Bildungseinrichtung unterrichtet werden, und laden Sie sie als CSV-Datei hoch. Die App bezieht sich auf den Kurskatalog, um die Fähigkeiten eines Kursteilnehmers aus seiner Transkription zu identifizieren und Kurse zu empfehlen. 

> [!NOTE]
> Informationen [zum Schutz](location-of-data-in-teams.md) von Schülerinformationen finden Sie unter Speicherort von Teams und Sicherheit und Compliance. [](security-compliance-overview.md) 

##### <a name="course-catalog-documents-formatting-and-schema"></a>Kurskatalogdokumente, Formatierung und Schema

Das Dokument muss im CSV-Format mit einer maximalen Größe von 18 MB vorliegen. Das Dokument muss die erforderlichen Felder **Kurstitel,** **Kurs-ID** und **Kurs-URL enthalten.** Durch die Einbeziehung der empfohlenen Felder wird die Benutzererfahrung für Die Kursteilnehmer verbessert, indem sie bessere Suchergebnisse und die Identifizierung von Fähigkeiten zurückgeben.

> [!NOTE]
> Beginnen Sie mit [dem Beispielkatalogdokument für]( https://aka.ms/career-coach/docs/it-admins/sample-catalog) den Kurs, um zu beginnen.

##### <a name="sample-csv-file"></a>Beispieldatei .CSV

```
courseId,title,sourceLink,description,language,format,thumbnailLink,thumbnailAltText,educationLevel,topics
"AA-501","Analytics Foundations","https://example.com/course-id","This course equips the student with the knowledge and skills needed to conduct and present large-scale studies based on advanced analytics.","en-us","In-person","https://via.placeholder.com/360x200","Undergraduate","Alt text for the thumbnail","analytics, data science, data analysis, linear regression"
```

Die folgende Tabelle zeigt die Elemente, die im Kurskatalog enthalten sein müssen:


| Name             | Status      | Typ   | Beschreibung                                                                    |
|------------------|-------------|--------|--------------------------------------------------------------------------------|
| courseId         | Erforderlich    | Zeichenfolge | In der Regel ist die Kurs-ID (in der Regel dem zugeordnet, was in der Transkription generiert wird). |
| Titel            | Erforderlich    | Zeichenfolge | In der Regel der Kurstitel.                                                      |
| sourceLink       | Erforderlich    | URL    | Websitelink zur Kursseite.                                               |
| Beschreibung      | Empfohlen | Zeichenfolge | Einführungstext für den Kurs.                                              |
| Sprache         | Empfohlen | Zeichenfolge | Sprache des Kurses. Verwenden Sie Standardsprachencodes.                           |
| Format           | Empfohlen | Zeichenfolge | Unterrichtsmodus, z. B. Online, Video, persönlich.                              |
| thumbnailLink    | Empfohlen | URL    | Miniaturansichtslink zum Kursbild.                                            |
| thumbnailAltText | Empfohlen | Zeichenfolge | Alternativtext zur Barrierefreiheit für das Bild                                           |
| educationLevel   | Empfohlen | Zeichenfolge | Studienstufe, z. B. Undergraduate/Graduate.                                       |
| Themen           | Empfohlen | Zeichenfolge | Themen oder Kategorien, die mit den Fähigkeiten verknüpft sind, die in den Kursen vermittelt werden.          |

##### <a name="add-the-course-catalog"></a>Hinzufügen des Kurskatalogs

1. Melden Sie sich beim **Teams Admin Center an.**

1. Wählen **Teams apps** Verwalten von &gt; **Apps** Career &gt; **Coach** &gt; **Einstellungen** &gt; **Kurskatalog aus.**  

2. Hochladen Kurse im CSV-Format.

4. Wählen Sie **Übernehmen aus.**

   ![Abschnitt "Kurskatalog" der Karrieretrainer-App](media/course-catalog.png)

#### <a name="fields-of-study"></a>Studienfelder

Die Studienfelder sind synonym für wichtige Interessenbereiche, akademische Haupt- und Abschlussbereiche. Auf diese Titel verweisen die Kursteilnehmer, wenn sie mit der Verwendung der App beginnen und mit dem Einrichten ihres personalisierten Profils beginnen.

Fügen Sie alle Studienbereiche hinzu, die für Studierende verfügbar sind, z. B. "Engineering", "Englisch", "Business" und so weiter. Die Liste der Felder ermöglicht es den Kursteilnehmern, Studienfelder zu entdecken, die sie möglicherweise interessieren, und ihren Fokusbereich zu ihrem Profil hinzuzufügen.

> [!NOTE]
> Beginnen Sie mit [dem Beispielfeld des Studiendokuments.](https://aka.ms/career-coach/docs/it-admins/sample-fieldsofstudy)
##### <a name="add-the-fields-of-study"></a>Hinzufügen der Studienfelder

1. Melden Sie sich beim **Teams Admin Center an.**
1. Wählen **Sie Teams Apps** Verwalten von &gt; **Apps** Career &gt; **Coach** &gt; **Einstellungen** &gt; **Studienfelder aus.**  

2. Hochladen im CSV-Format.

3. Wählen Sie **Übernehmen aus.**

#### <a name="customization"></a>Anpassung

Career Coach kann so angepasst werden, dass er für Ihre Bildungseinrichtung einzigartig ist. Die Anpassung unterstützt das Hinzufügen von Benutzererfahrungen zum Dashboard. Es wird empfohlen, Links zu Jobboards, Veranstaltungen, Karriereservicebüros, Karriereereignissen, Studentenclubs und anderen Ressourcen hinzuzufügen, mit deren Hilfe Schüler/Studenten reale Erfahrungen sammeln können.

##### <a name="add-customized-experiences"></a>Hinzufügen angepasster Benutzererfahrungen

1. Melden Sie sich beim **Teams Admin Center an.**

1. Wählen **Sie Teams Apps Verwalten** von &gt; **Apps** Career &gt; **Coach**  >  **Einstellungen** Customization &gt; **aus.**

2. Fügen Sie jede URL, einen Titel und eine kurze Beschreibung hinzu.  
  
3. Wählen Sie **Übernehmen aus.**

### <a name="enable-the-app"></a>Aktivieren der App

Nachdem Sie die Konfiguration abgeschlossen haben, aktivieren Sie die App für Kursteilnehmer und lizenzierte Benutzer, damit sie Zugriff auf Career Coach haben.  
  
> [!NOTE]
> Sie müssen über berechtigungen für globale Teams Administratorrolle verfügen.

1. Melden Sie sich beim **Teams Admin Center an.**

1. Wählen **Sie Teams Apps** &gt; **Career** &gt; **Coach verwalten aus.**

2. Verschieben sie den Umschalter Status auf **Zulässig.**  

  > [!NOTE]
  > Zulässig bedeutet, dass die App für Benutzer in Ihrer Bildungseinrichtung verfügbar ist. Blockiert bedeutet, dass die App für Kursteilnehmer nicht verfügbar ist.

#### <a name="pin-the-app"></a>Anheften der App

Durch das Anheften von Career Coach wird die App für Schüler und Studenten barrierefreier und sichtbarer.

1. Melden Sie sich beim **Teams Admin Center an.**

1. Wählen **Teams Für Apps** &gt; **Einrichtungsrichtlinien** &gt; *Ihre Richtlinie aus.* 

2. Wählen **Sie unter Angeheftet Apps** die Option Apps hinzufügen **aus.**

1. Suchen Sie **nach Career Coach**, und wählen Sie dann Hinzufügen **aus.**

1. Wählen Sie die Reihenfolge aus, in der die App angezeigt werden soll, und wählen Sie **Speichern aus.**

   Die Kursteilnehmer werden in der Microsoft Teams, dass career coach angeheftet wurde.  

## <a name="resources"></a>Ressourcen

Die folgenden Ressourcen helfen Ihnen bei der Planung Ihrer Career Coach-App.

- [Willkommen bei Microsoft Teams](Teams-overview.md)

- [Bereitstellen von Teams](get-started-with-teams-resources-for-org-wide-rollout.md?tabs=SmallBusiness)

- [Übersicht über Teams und Kanäle in Microsoft Teams](teams-channels-overview.md)

- [Verwalten von Apps im Microsoft Teams Admin Center](manage-apps.md)

- [Sicherheit, Datenschutz und Compliance in Microsoft Teams](security-compliance-overview.md)

- [Online Virtual Orientation Kit](https://www.microsoft.com/education/remote-learning/virtual-orientation) 

- [Grenzwerte und Spezifikation Teams Kanäle](limits-specifications-teams.md)

- [Speicherort von Daten in Microsoft Teams](location-of-data-in-teams.md)

- [Schneller Einstieg mit der Administrator-Schulung für Microsoft Teams](ITAdmin-readiness.md)

- [Teams-Problembehandlung](/microsoftteams/troubleshoot/teams-welcome)

- [Verwalten von Richtlinien für App-Berechtigungen in Microsoft Teams](teams-app-permission-policies.md)
