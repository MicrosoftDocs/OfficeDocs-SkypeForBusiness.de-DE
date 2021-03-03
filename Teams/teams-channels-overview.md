---
title: Übersicht über Teams und Kanäle in Microsoft Teams
author: MikePlumleyMSFT
ms.author: mikeplum
ms.reviewer: ''
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
description: Hier erhalten Sie Informationen zu den verschiedenen verfügbaren Teams, Kanälen und Apps für die verschiedensten Anforderungen wie zum Beispiel Finanzen, Planung von Veranstaltungen, Vertrieb und vieles mehr.
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.msteamsfiles
- ms.teamsadmincenter.dashboard.helparticle.teamsandchannels
- ms.teamsadmincenter.teamschannel.overview
- ms.teamsadmincenter.teamssettings.overview
- okr_smb
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c6f6b3cbb80fb209c519593c28077b03e4a13ed9
ms.sourcegitcommit: ab566ddab9d26440bac1716a975f30e075d0c7b5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "49865169"
---
# <a name="overview-of-teams-and-channels-in-microsoft-teams"></a>Übersicht über Teams und Kanäle in Microsoft Teams

> [!NOTE]
> Lesen Sie bitte die folgenden Informationen, um sich einen besseren Überblick über Chat, Teams, Kanäle und Apps in Teams zu verschaffen. Gehen Sie anschließend zu [Chat, Teams, Kanäle und Apps in Teams](deploy-chat-teams-channels-microsoft-teams-landing-page.md), um eine Liste von Entscheidungen durchzugehen, die für Ihre Implementierung von Teams wichtig sind.

Betrachten wir zunächst, wie sich einzelne Teams mit Microsoft Teams selbst organisieren und in verschiedenen Geschäftsszenarien zusammenarbeiten können:

- **Teams** sind Sammlungen von Personen, Inhalten und Tools für unterschiedliche Projekte und Ergebnisse innerhalb einer Organisation.

    - Teams können so aufgesetzt werden, dass nur eingeladene Benutzer Zugriff erhalten.
    - Teams können auch als öffentliche und offene Teams erstellt werden, an denen alle in der Organisation teilnehmen können (maximal 10.000 Mitglieder).
    
    Teams sollen Gruppen von Personen zusammenbringen, die eng zusammenarbeiten, um ihre Produktivität zu verbessern. Möglich sind dynamische Teams für projektbasierte Aufgaben (zum Beispiel Einführung eines Produkts oder Einrichtung eines gemeinsamen digitalen Arbeitsraums). Eine weitere Möglichkeit sind ständige Teams, die die interne Struktur Ihrer Organisation widerspiegeln (z. B. Abteilungen und Bürostandorte). Unterhaltungen, Dateien und Notizen in Teamkanälen sind nur für Mitglieder des Teams sichtbar.

- **Kanäle** sind spezielle Abschnitte innerhalb eines Teams, mit denen Unterhaltungen nach bestimmten Themen, Projekten, Fachrichtungen oder anderen für Ihr Team wichtigen Aspekten organisiert werden. Dateien, die Sie in einem Kanal (auf der Registerkarte „Dateien“) freigeben, werden in SharePoint gespeichert. Weitere Informationen finden Sie unter [Interaktion von SharePoint Online und OneDrive for Business mit Teams](SharePoint-OneDrive-interact.md).

    - Kanäle sind Orte, an denen Unterhaltungen stattfinden und wo die Arbeit tatsächlich erledigt wird. Kanäle können für alle Teammitglieder entweder offen oder – sofern Sie ein ausgewähltes Publikum benötigen – privat sein. Standardkanäle sind für Unterhaltungen, an denen jeder in einem Team teilnehmen kann, wohingegen [private Kanäle](private-channels.md) die Kommunikation auf eine Teilmenge von Personen in einem Team einschränken.
    - Die Vorteile von Kanälen werden am deutlichsten, wenn Sie sie mit Apps erweitern, die Registerkarten, Connectors und Bots enthalten und damit den Nutzen für die Teammitglieder steigern. Weitere Informationen hierzu finden Sie unter [Apps, Bots und Connectors in Teams](deploy-apps-microsoft-teams-landing-page.md).
    
Wenn Sie Hilfe bei der Verwendung von Teams und Kanälen benötigen, lesen Sie bitte unter [Teams und Kanäle](https://support.office.com/article/teams-and-channels-df38ae23-8f85-46d3-b071-cb11b9de5499) nach.

Sehen Sie sich dieses kurze Video an und erfahren Sie mehr über bewährte Methoden zum Erstellen von Teams und Kanälen.

   > [!VIDEO https://www.youtube.com/embed/WkAVgNKn0hs]

<a name="membership-roles-and-settings"></a>Mitgliedschaft, Rollen und Einstellungen
------------------------------

**Teammitgliedschaft**

Wenn Microsoft Teams für Ihre gesamte Organisation aktiviert ist, können festgelegte Teambesitzer alle Mitarbeiter, mit denen sie zusammenarbeiten, einladen, ihrem Team beizutreten. Teambesitzer können in Microsoft Teams ganz leicht Personen aus der Organisation anhand ihres Namens hinzufügen. Je nach den Einstellungen Ihrer Organisation können auch Gäste, die zwar Teammitglieder sind, aber nicht der Organisation angehören, zu Ihren Teams hinzugefügt werden. Weitere Informationen finden Sie unter [Gastzugriff in Microsoft Teams](guest-access.md). 

Darüber hinaus können Teambesitzer ein Team auf der Grundlage einer vorhandenen Microsoft 365-Gruppe erstellen. Alle an der Gruppe vorgenommenen Änderungen werden automatisch mit Microsoft Teams synchronisiert. Durch die Erstellung eines Teams auf der Grundlage einer vorhandenen Microsoft 365-Gruppe wird nicht nur das Einladen und Verwalten von Mitgliedern vereinfacht, sondern es werden auch Gruppendateien in Microsoft Teams synchronisiert.

**Teamrollen**

In Microsoft Teams gibt es zwei Hauptrollen: 

- **Teambesitzer** – Die Person, die das Team erstellt. Teambesitzer können jedes Mitglied ihres Teams zum Mitbesitzer ernennen – entweder dann, wenn sie das Mitglied in das Team einladen, oder auch jederzeit später, nachdem die Person dem Team beigetreten ist. Mit mehreren Teambesitzern können Sie sich die Zuständigkeit für das Verwalten der Einstellungen und der Mitgliedschaft, einschließlich Einladungen, teilen.
- **Teammitglieder** – Personen, die von den Teambesitzern eingeladen werden, dem Team beizutreten.

Wenn die Moderation eingerichtet ist, können Teambesitzer und Teammitglieder auch über Moderatorfunktionen für einen Kanal verfügen. Moderatoren können neue Beiträge im Kanal starten und steuern, ob Teammitglieder auf vorhandene Kanalnachrichten antworten können. Teambesitzer können Moderatoren in einem Kanal zuweisen. (Teambesitzer verfügen standardmäßig über Moderatorfunktionen.) Moderatoren in einem Kanal können andere Moderatoren innerhalb dieses Kanals hinzufügen oder entfernen. Weitere Informationen finden Sie unter [Einrichten und Verwalten der Kanalmoderation in Microsoft Teams](manage-channel-moderation-in-teams.md).

**Teameinstellungen** 

Teambesitzer können teamweite Einstellungen direkt in Microsoft Teams verwalten. Es gibt unter anderem Einstellungen für die folgenden Möglichkeiten: ein Teambild hinzufügen, Berechtigungen zum Erstellen von Standard- und [Privat-Kanälen](private-channels.md) für Teammitglieder festlegen, Registerkarten und Connectors hinzufügen, das gesamte Team oder einen Kanal @erwähnen und GIF-Dateien, Aufkleber und Memes verwenden.

Nehmen Sie sich drei Minuten Zeit, um sich dieses Handbuch für Teambesitzer anzusehen:

   > [!VIDEO https://www.youtube.com/embed/kalV4dG-oFo]

Wenn Sie in Microsoft 365 oder Office 365 als Administrator für Microsoft Teams festgelegt wurden, haben Sie im Microsoft Teams Admin Center Zugriff auf systemweite Einstellungen. Diese Einstellungen können sich auf die Optionen und Standardeinstellungen auswirken, die Teambesitzer unter „Teameinstellungen“ sehen. Sie können zum Beispiel einen Standardkanal („Allgemein“) für teamweite Ankündigungen, Diskussionen und Ressourcen aktivieren, der für alle Teams angezeigt wird.

Standardmäßig verfügen alle Benutzer über die Berechtigung, ein Team in Microsoft Teams zu erstellen (wie Sie dies ändern, erfahren Sie unter [Zuweisen von Rollen und Berechtigungen in Microsoft Teams](assign-roles-permissions.md)). Benutzer einer vorhandenen Microsoft 365-Gruppe können ihre Berechtigungen mit Microsoft Teams-Funktionen erweitern.

Eine wichtige frühe Planungsaktivität, mit der Benutzer in Microsoft Teams eingebunden werden sollen, besteht darin, ihnen zu vermitteln, wie sie mit Microsoft Teams im Arbeitsalltag besser zusammenarbeiten können. Sprechen Sie mit den Benutzern, und helfen Sie ihnen, Geschäftsszenarien auszuwählen, in denen sie zurzeit bruchstückweise zusammenarbeiten. Bringen Sie alle in einem Kanal zusammen, der relevante Registerkarten enthält, mit deren Hilfe sie produktiv arbeiten können. Die überzeugendsten Anwendungsfälle für Microsoft Teams sind alle organisationsübergreifenden Prozesse. 

<a name="example-teams"></a>Beispiele für Teams
--------------

Nachstehend finden Sie einige Funktionsbeispiele dafür, wie unterschiedliche Benutzertypen beim Einrichten von Teams, Kanälen und Apps (Registerkarten/Connectors/Bots) vorgehen können. Dies kann beim Starten einer Unterhaltung zu Microsoft Teams mit Ihrer Benutzercommunity hilfreich sein. Wenn Sie eine Implementierung von Microsoft Teams in Ihrer Organisation planen, denken Sie daran, dass Sie Anleitungen zum Strukturieren Ihrer Teams bereitstellen können. Benutzer haben jedoch die Kontrolle darüber, wie sie sich organisieren. Die folgenden Beispiele dienen der Veranschaulichung und sollen Teams dabei helfen, die Möglichkeiten zu durchdenken.

Microsoft Teams ist gut dafür geeignet, organisatorische Silos aufzubrechen und funktionsübergreifende Teams zu fördern. Ermutigen Sie also die Benutzer, die organisatorischen Grenzen zu überwinden und eher in funktionalen Teams zu denken.

|Teamtypen  |Mögliche Kanäle  |Apps (Registerkarten ![Ein Symbol eines Ordners mit einer Registerkarte](media/Overview_of_teams_and_channels_in_Microsoft_Teams_image2.png)/Connectors ![Ein Symbol für Verbindungsblöcke](media/Overview_of_teams_and_channels_in_Microsoft_Teams_image3.png)/Bots ![Ein Symbol mit einem kleinen Robot](media/Overview_of_teams_and_channels_in_Microsoft_Teams_image4.png))  |
|---------|---------|---------|
|Vertrieb     |Jährliche Vertriebsbesprechung<br></br> Vierteljährlicher Geschäftsbericht<br></br> Monatlicher Vertriebspipelinebericht<br></br> Vertriebsleitfaden |Power BI<br></br>Trello<br></br>CRM<br></br>Zusammenfassungsbot         |
|Öffentlichkeitsarbeit     |Pressemitteilungen<br></br>Neuigkeiten und Updates<br></br>Überprüfung der Fakten         |RSS-Feed<br></br>Twitter         |
|Event Planning (Veranstaltungsplanung)     |Marketing<br></br>Logistik und Planung<br></br>Veranstaltungsort<br></br>Budget         |Twitter<br></br>Facebook<br></br>Planner<br></br>PDF         |
|Marketing/Markteinführung   |Marktforschung<br></br>Säulen des Messaging<br></br>Kommunikationsplan<br></br>Marketingstückliste        |YouTube<br></br>Microsoft Stream<br></br>Twitter<br></br>MailChimp         |
|Technischer Betrieb    |Incident Management<br></br>Sprintplanung<br></br>Arbeitselemente<br></br>Infrastruktur und Betrieb         |Teamdienste<br></br>Jira<br></br>AzureBot         |
|Produktteam      |Strategie<br></br>Marketing<br></br>Vertrieb<br></br>Vorgänge<br></br>Insights<br></br>Dienste und Support         |Power BI<br></br>Team Services         |
|Finanzen    |Aktuelles Geschäftsjahr<br></br>Geschäftsjahresplanung<br></br>Prognose<br></br>Forderungen<br></br>Verbindlichkeiten         |Power BI<br></br>Google Analytics         |
|Logistik     |Lagerbetrieb<br></br>Fahrzeugwartung<br></br>Fahrerdienstpläne         |Wetterdienst<br></br>Verkehrsstörungen<br></br>Planner<br></br>Tubot<br></br>UPS-Bot         |
|HR     |Talentmanagement<br></br>Personalsuche<br></br>Leistungsbewertungsplanung<br></br>Arbeitsmoral         |Tools für das Personalwesen<br></br>Externe Websites für Stellenausschreibungen<br></br>Growbot         |
|Organisationsübergreifendes <br></br>virtuelles Team |Strategie<br></br>Mitarbeiterentwicklung<br></br>Wettbewerb und Forschung         |Power BI<br></br>Microsoft Stream         |

Sie können Teams erstellen, die die Organisationsstruktur widerspiegeln. Diese Vorgehensweise eignet sich am besten für Führungskräfte, die die Motivation steigern, teamspezifische Überprüfungen durchführen, für Klarheit bezüglich der Onboardingprozesse für die Mitarbeiter sorgen, Personalpläne besprechen und die Transparenz für die Mitarbeiter in den verschiedenen Bereichen erhöhen möchten.  

![Hierachiediagramm der Organisation von Teams und Kanälen in Microsoft Teams](media/overview-of-teams-and-channels-image1.png)

## <a name="org-wide-teams"></a>Organisationsweite Teams

Wenn Ihre Organisation aus nicht mehr als 5 000 Benutzern besteht, können Sie ein organisationsweites Team erstellen. Organisationsweite Teams bieten eine automatische Möglichkeit für alle Personen in einer Organisation, Teil eines einzelnen Teams für die Zusammenarbeit zu sein. Weitere Informationen, einschließlich bewährter Methoden zum Erstellen und Verwalten eines organisationsweiten Teams, finden Sie unter [Erstellen eines organisationsweiten Teams in Microsoft Teams](create-an-org-wide-team.md).
