---
title: Erwerben, konfigurieren und aktivieren Sie Career Coach für Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: alaina.creager
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Erfahren Sie, wie Sie Career Coach für Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 95272545080559b94faeff42d715b8f57c4d0242
ms.sourcegitcommit: ea9a0119d184179300e51f58ca4fee249c12d00a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/28/2021
ms.locfileid: "52699356"
---
# <a name="purchase-configure-and-enable-career-coach-for-microsoft-teams"></a>Erwerben, konfigurieren und aktivieren Sie Career Coach für Microsoft Teams

Career Coach ist eine Microsoft Teams for Education-App, die von LinkedIn unterstützt wird und personalisierte Anleitungen für Studierende aus höheren Bildungseinrichtungen bietet, um auf ihren Karriereweg zu navigieren. Career Coach bietet Bildungseinrichtungen eine einheitliche Karrierelösung für Studenten, die ihren Karrierepfad entdecken, ihre echten Fähigkeiten erweitern und ihr Netzwerk an einem Ort aufbauen können.

Erfahren Sie mehr über [Career Coach.](https://aka.ms/career-coach)

> [!NOTE]
> Verwenden Sie die bewährten Methoden und hilfreichen Tipps in diesem Handbuch, um die Funktionen von Career Coach für Studierende, Lehrkräfte und Mitarbeiter zu aktivieren. Weitere Informationen finden [Sie im Artikel zum Schnellplanungshandbuch.](https://support.microsoft.com/office/c5d0b934-bfcf-4fe7-8a85-ba7bbb1b6ad4)

## <a name="review-the-requirements"></a>Überprüfen der Anforderungen

Um Career Coach für Ihre Bildungseinrichtung zu aktivieren, überprüfen Sie, was Sie benötigen, um die App zu starten.

**Technische Anforderungen**

  - Office 365-Mandant mit Azure Active Directory

  - Microsoft Teams

  - LinkedIn-Kontoverbindungen in Azure Active Directory

**Lizenzen**

  - Lehrpersonal 

  - Schüler/Studenten

> [!NOTE]
> Dem IT-Administrator muss beim Abschließen der Konfiguration eine Lizenz für Career Coach Faculty zugewiesen werden.

**Daten und Dateien von Ihrer Bildungseinrichtung**

  - Kurskatalogdaten

  - Angebotene Studienfelder

  - LinkedIn-Seite der Bildungseinrichtung

  - LinkedIn Learning Campus-Abonnement (bevorzugt)

## <a name="purchase-the-career-coach-licenses"></a>Erwerben Sie die Career Coach-Lizenzen

Career Coach steht weltweit (mit Ausnahme von China und Russland) für qualifizierte Hochschulen über Enrollment for Education Solutions (EES), Cloud Service Providers (CSP) und Microsoft 365 Admin Center (Web Direct) zur Verfügung. Als Microsoft Teams-App müssen Kunden über Microsoft 365 A3/A5 oder Office 365 A1/A3/A5 verfügen.

### <a name="assign-app-licenses-to-users"></a>Zuweisen von App-Lizenzen zu Benutzern

Eine schrittweise Anleitung finden Sie unter [Zuweisen von Lizenzen zu Benutzern.](/microsoft-365/admin/manage/assign-licenses-to-users)

### <a name="turn-on-linkedin-account-connections"></a>Aktivieren von LinkedIn-Kontoverbindungen

Career Coach **setzt voraus,** dass die Benutzer Ihrer Bildungseinrichtung in der Lage sind, ihr Microsoft 365-Konto mit ihrem LinkedIn-Konto zu verbinden, das innerhalb von Career Coach vereinfacht wird.

1. Melden Sie sich beim [Azure AD Admin Center](https://aad.portal.azure.com/) mit einem Konto an, das ein globaler Administrator für die Azure AD-Organisation ist.

2. Wählen Sie **Benutzer aus.**

3. Wählen Sie **auf der** Seite Benutzer die Option **Benutzereinstellungen aus.**

4. Erlauben **Sie Benutzern unter LinkedIn-Kontoverbindungen,** ihre Konten zu verbinden, um innerhalb einiger Microsoft-Apps auf ihre LinkedIn-Verbindungen zu zugreifen. Es werden keine Daten freigegeben, bis die Benutzer der Verbindung ihrer Konten zustimmen.

   - Wählen **Sie Ja** aus, um den Dienst für alle Benutzer in Ihrer Bildungseinrichtung zu aktivieren.

   - Wählen **Sie Ausgewählte Gruppe** aus, um den Dienst nur für eine Gruppe ausgewählter Benutzer in Ihrer Bildungseinrichtung zu aktivieren.

   - Wählen Sie **Nein aus,** um die Zustimmung aller Benutzer in Ihrer Bildungseinrichtung zu widerrufen.

Erfahren Sie, wie [Sie LinkedIn-Kontoverbindungen in Ihre Azure Active Directory](/azure/active-directory/enterprise-users/linkedin-integration)

## <a name="configure-career-coach-in-the-teams-admin-center"></a>Konfigurieren von Career Coach im Teams Admin Center

Mithilfe der Administratoreinstellungen im Microsoft Teams Admin Center können Sie Career Coach für Ihre Bildungseinrichtung konfigurieren und für Benutzer aktivieren.

## <a name="access-the-career-coach-app-settings"></a>Zugreifen auf die Einstellungen der Career Coach-App

Auf der [Seite "Apps verwalten"](/microsoftteams/manage-apps) können Sie Teams Apps im App-Katalog Ihrer Bildungseinrichtung anzeigen.

1. Melden Sie sich beim **Teams Admin Center an.**

2. Wählen Sie im linken Navigationsbereich die Option **Teams Apps**  >  **verwalten aus.**  

    > [!NOTE]
    > Sie müssen ein globaler Administrator oder ein Teams sein, um auf die Seite zugreifen zu können.

3. Suchen Oder suchen Sie nach **Career Coach.**  

4. Wählen **Sie Career Coach** und dann **Einstellungen.**  

    ![Zeigt die ausgewählte Career Coach-App mit der Einstellungen Option](media/app-settings.png)

### <a name="configure-the-career-coach-app-settings"></a>Konfigurieren der Einstellungen für die Career Coach-App

Career Coach hat fünf Konfigurationskategorien:

- [Marke und Voreinstellungen](#brand-and-preferences)

- [LinkedIn-Konfiguration](#linkedin-configuration)

- [Kurskatalog](#course-catalog)

- [Studienfelder](#fields-of-study)

- [Anpassung](#customization)

> [!NOTE]
> Marke und Einstellungen, LinkedIn-Konfiguration, Kurskatalog und  Studienfelder sind erforderlich, um die App effektiv für Studierende, Lehrkräfte und Mitarbeiter zu aktivieren.

#### <a name="brand-and-preferences"></a>Marke und Voreinstellungen

Legen Sie den Namen, das Logo und die Standardsprache Ihrer Bildungseinrichtung auf der Seite mit den Einstellungen für Marke und Einstellungen festgelegt.

![Der Brandingbereich von Career Coach im Admin Center](media/brand-preferences.png)

##### <a name="educational-institution-icon"></a>Symbol für Bildungseinrichtung

Das Symbol für Bildungseinrichtungen wird überall in Career Coach verwendet, um Inhalte zu identifizieren, die für Ihre Bildungseinrichtung einzigartig sind, Kurskatalogressourcen in der gesamten App sowie im Abschnitt "Reale Erfahrungen" des Dashboards. Das Symbol ist am besten wie folgt formatiert:

 - Eine transparente PNG-Datei
 - Seitenverhältnis von 1:1
 - Maximale Größe von 64 px x 64 px.

##### <a name="educational-institution-thumbnail"></a>Miniaturansicht der Bildungseinrichtung

Das Symbol für die Bildungseinrichtung wird für Kurskatalogressourcen in der gesamten App verwendet, wenn kein bestimmtes Bild für einen Kurs verfügbar ist. Das Symbol ist am besten wie folgt formatiert:

- PNG-Datei
- Seitenverhältnis von 16:9
- Maximale Größe von 360 px x 200 px.

#### <a name="linkedin-configuration"></a>LinkedIn-Konfiguration

Die LinkedIn-Konfiguration verbindet Career Coach mit öffentlichen Absolventendaten von LinkedIn.

> [!NOTE]
> Career Coach kann nur aktiviert werden, wenn die LinkedIn-Seitenverbindung überprüft wurde.

##### <a name="add-and-confirm-the-linkedin-page"></a>Hinzufügen und Bestätigen der LinkedIn-Seite

Ermitteln Sie die LinkedIn-Seite der Bildungseinrichtung. Suchen Sie die LinkedIn-Seite, indem Sie auf LinkedIn suchen oder eine Verbindung mit einem Mitarbeiter für Career Services herstellen, um die richtige Seite zu bestimmen.  
  
1. Melden Sie sich beim **Teams Admin Center an.**

1. Wählen **Teams Apps** Manage  >  **apps** Career  >  **Coach**  >  **LinkedIn connection aus.**

2. Geben Sie die URL der LinkedIn-Seite Ihrer Bildungseinrichtung ein.  

3. Wählen Sie **Übernehmen aus.**

4. Kopieren Sie die Überprüfungs-URL, und teilen Sie sie mit der LinkedIn-Seitendokumentation des [LinkedIn-Seitenadministrators Ihrer Bildungseinrichtung.](https://www.linkedin.com/help/linkedin/answer/4783/linkedin-page-admins-overview?lang=en) Der Bestätigungslink läuft nach 30 Tagen ab.  

   ![Linkedin-Einstellungen für den Karrieretrainer](media/linkedin.png)  

#### <a name="course-catalog"></a>Kurskatalog

Der Kurskatalog stellt die Kurse und Kurse dar, die Schülern von Ihrer Bildungseinrichtung angeboten werden. Diese Kurse werden innerhalb der App in zwei Bereichen verwendet:

- Kurse werden als Teil von Lernressourcen zurückgegeben.  

- Kurse und Metadaten des Kurses, z. B. Beschreibungen, werden verwendet, um Kursteilnehmern dabei zu helfen, ihre Fähigkeiten beim Hochladen eines Transkripts zu identifizieren.  

Um den Kurskatalog zu erstellen, erstellen Sie eine Liste aller Kurse, die an Ihrer Bildungseinrichtung vermittelt werden, und laden Sie sie als CSV-Datei hoch. Die App zeichnet aus dem Kurskatalog, um die Fähigkeiten eines Kursteilnehmers aus deren Transkription zu identifizieren und Kurse für den Kurs vorschlagen zu können. 

##### <a name="course-catalog-documents-formatting-and-schema"></a>Formatieren und Schema von Kurskatalogdokumenten

Das Dokument muss im CSV-Format mit einer maximalen Größe von 18 MB vorliegen. Das Dokument muss die erforderlichen Felder **(Kurstitel,** **Kurs-ID** und **Kurs-URL) enthalten.** Die Einbeziehung der empfohlenen Felder verbessert die Benutzererfahrung für Schüler/Studenten durch die Rückgabe besserer Suchergebnisse und der Fähigkeitserkennung.

> [!NOTE]
> Beginnen Sie mit dem [Beispielkurskatalogdokument,]( https://aka.ms/career-coach/docs/it-admins/sample-catalog) um zu beginnen.

In der folgenden Tabelle sind die Elemente aufgeführt, die in den Kurskatalog enthalten sein müssen:


| Name             | Status      | Typ   | Beschreibung                                                                    |
|------------------|-------------|--------|--------------------------------------------------------------------------------|
| courseId         | Erforderlich    | Zeichenfolge | In der Regel ist die Kurs-ID dem zugeordnet, was in der Aufzeichnung generiert wird. |
| Title            | Erforderlich    | Zeichenfolge | In der Regel der Kurstitel.                                                      |
| sourceLink       | Erforderlich    | URL    | Websitelink zur Kursseite.                                               |
| Beschreibung      | Empfohlen | Zeichenfolge | Einführungstext für den Kurs.                                              |
| Sprache         | Empfohlen | Zeichenfolge | Die Sprache des Kurses. Verwenden Sie Standardsprachcodes.                           |
| Format           | Empfohlen | Zeichenfolge | Unterrichtsmodus, z. B. online, Video, persönlich.                              |
| thumbnailLink    | Empfohlen | URL    | Link zur Miniaturansicht des Kursbilds.                                            |
| thumbnailAltText | Empfohlen | Zeichenfolge | Alternativtext zur Barrierefreiheit für das Bild                                           |
| educationLevel   | Empfohlen | Zeichenfolge | Lernstufe, z. B. Undergraduate/Graduate.                                       |
| Themen           | Empfohlen | Zeichenfolge | Themen oder Tags, die mit den in den Kursen vermittelten Fähigkeiten verknüpft sind.          |

##### <a name="add-the-course-catalog"></a>Hinzufügen des Kurskatalogs

1. Melden Sie sich beim **Teams Admin Center an.**

1. Wählen **Teams Apps** Manage &gt; **apps** Career &gt; **Coach** &gt; **Einstellungen** Course Catalog &gt; **aus.**  

2. Hochladen Kurse im CSV-Format.

4. Wählen Sie **Übernehmen aus.**

   ![Kurskatalogabschnitt der Karrieretrainer-App](media/course-catalog.png)

#### <a name="fields-of-study"></a>Studienfelder

Die Studienfelder sind Synonyme für Hauptbereiche von Interesse, akademischer Haupt- und Abschluss abschluss. Auf diese Titel verweisen Schüler/Studenten, wenn sie mit der Nutzung der App beginnen und mit dem Einrichten ihres personalisierten Profils beginnen.

Fügen Sie alle für Schüler/Studierenden verfügbaren Lernfelder hinzu, z. B. Technik, Englisch, Unternehmen und so weiter. Mit der Feldliste können Schüler/Studenten Lernfelder entdecken, die sie möglicherweise interessieren, und ihren Schwerpunktbereich zu ihrem Profil hinzufügen.

> [!NOTE]
> Beginnen Sie mit [dem Beispielfeld des Lerndokuments.](https://aka.ms/career-coach/docs/it-admins/sample-fieldsofstudy)
##### <a name="add-the-fields-of-study"></a>Hinzufügen der Lernfelder

1. Melden Sie sich beim **Teams Admin Center an.**
1. Wählen **Teams Apps Manage** &gt; **apps** &gt; **Career Coach** &gt; **Einstellungen** Fields of study &gt; **aus.**  

2. Hochladen ein Studienfeld im CSV-Format.

3. Wählen Sie **Übernehmen aus.**

#### <a name="customization"></a>Anpassung

Career Coach kann so angepasst werden, dass er für Ihre Bildungseinrichtung einzigartig ist. Die Anpassung unterstützt das Hinzufügen von Erfahrungen zum Dashboard. Es wird empfohlen, Links zu Job boards, Veranstaltungen, Karrierediensten, karrierebezogenen Veranstaltungen, Student Clubs und anderen Ressourcen hinzuzufügen, die Schülern dabei helfen, echte Erfahrungen zu sammeln.

##### <a name="add-customized-experiences"></a>Hinzufügen von benutzerdefinierten Benutzerdefinierten Benutzerdefinierten

1. Melden Sie sich beim **Teams Admin Center an.**

1. Wählen **Teams Apps Manage** &gt; **apps** &gt; **Career Coach**  >  **Einstellungen** &gt; **Customization aus.**

2. Fügen Sie jede URL, einen Titel und eine kurze Beschreibung hinzu.  
  
3. Wählen Sie **Übernehmen aus.**

## <a name="making-career-coach-available-to-your-organization"></a>So stellen Sie Career Coach für Ihre Organisation zur Verfügung

Jetzt ist Career Coach für Ihre Organisation konfiguriert. Führen Sie die folgenden Schritte aus, um sicherzustellen, dass Career Coach in Unternehmen verfügbar Microsoft Teams.

### <a name="enable-the-app"></a>Aktivieren der App

Nachdem Sie die Konfiguration abgeschlossen haben, aktivieren Sie die App für Kursteilnehmer und lizenzierte Benutzer, damit diese Zugriff auf Career Coach erhalten.  
  
> [!NOTE]
> Sie müssen über globale oder Teams Administratorrolleberechtigungen verfügen.

1. Melden Sie sich beim **Teams Admin Center an.**

1. Wählen **Teams Apps Manage** &gt; **apps** Career Coach &gt; **aus.**

2. Verschieben Sie den Umschalter Status auf **Zulässig.**  

  > [!NOTE]
  > Zulässig bedeutet, dass die App für Benutzer in Ihrer Bildungseinrichtung verfügbar ist. Blockiert bedeutet, dass die App für Schüler/Studierende nicht verfügbar ist.

### <a name="add-career-coach-as-an-installed-app"></a>Career Coach als installierte App hinzufügen

> [!NOTE]
> Durch diesen Schritt wird sichergestellt, dass 1) Career Coach für Ihre Organisation ordnungsgemäß konfiguriert ist (2), dass Kursteilnehmer Career Coach finden.

1. Melden Sie sich beim **Teams Admin Center an.**

2. Wählen Teams **Setuprichtlinien** &gt; **für Apps Ihre** Richtlinie &gt; *aus.* 

3. Wählen Sie unter Installierte Apps die Option Apps hinzufügen aus.

4. Suchen Sie im Bereich Installierte Apps hinzufügen nach den Apps, die Sie automatisch installieren möchten, wenn die App Teams. Sie können Apps auch nach der App-Berechtigungsrichtlinie filtern. Wenn Sie Ihre App-Liste ausgewählt haben, wählen Sie Hinzufügen aus.

### <a name="pin-the-app"></a>Anheften der App

Durch das Anheften von Career Coach wird die App für Kursteilnehmer barrierefreier und besser sichtbar.

1. Melden Sie sich beim **Teams Admin Center an.**

2. Wählen Teams **Setuprichtlinien** &gt; **für Apps Ihre** Richtlinie &gt; *aus.* 

3. Wählen **Sie unter Angeheftet Apps** die Option Apps hinzufügen **aus.**

4. Suchen Sie nach **Career Coach,** und wählen Sie dann **Hinzufügen aus.**

5. Wählen Sie die Reihenfolge aus, in der die App angezeigt werden soll, und wählen Sie **speichern aus.**

> [!NOTE]
> Die Kursteilnehmer werden in Microsoft Teams, dass Career Coach angeheftet wurde.

Weitere Details finden Sie unter Verwalten [von App-Setuprichtlinien in Microsoft.](/microsoftteams/teams-app-setup-policies)

## <a name="resources"></a>Ressourcen

Die folgenden Ressourcen helfen Ihnen bei der Planung Ihrer Career Coach-App.

- [Willkommen bei Microsoft Teams](Teams-overview.md)

- [Bereitstellen von Teams](get-started-with-teams-resources-for-org-wide-rollout.md?tabs=SmallBusiness)

- [Übersicht über Teams und Kanäle in Microsoft Teams](teams-channels-overview.md)

- [Verwalten von Apps im Microsoft Teams Admin Center](manage-apps.md)

- [Online Virtual Orientation Kit](https://www.microsoft.com/education/remote-learning/virtual-orientation) 

- [Beschränkungen und Spezifikation Teams Kanälen](limits-specifications-teams.md)

- [Schneller Einstieg mit der Administrator-Schulung für Microsoft Teams](ITAdmin-readiness.md)

- [Teams-Problembehandlung](/microsoftteams/troubleshoot/teams-welcome)

- [Verwalten von Richtlinien für App-Berechtigungen in Microsoft Teams](teams-app-permission-policies.md)
