---
title: Grenzwerte und Spezifikationen für Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: siunies
description: In diesem Artikel werden die Grenzwerte, Spezifikationen und anderen Anforderungen für Microsoft Teams beschrieben.
localization_priority: Priority
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- SPO_Content
- m365initiative-deployteams
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b714da86c51072eb7efae846dbeb29b205674751
ms.sourcegitcommit: 330e60ff3549cd5cff5b52ad95dc4259e4e8de13
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52628884"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a>Grenzwerte und Spezifikationen für Microsoft Teams

In diesem Artikel werden einige der Grenzwerte, Spezifikationen und anderen Anforderungen für Teams beschrieben.

## <a name="teams-and-channels"></a>Teams und Kanäle

|Feature    | Obergrenze |
|-----------|---------------|
|Anzahl der Teams, die ein Benutzer erstellen kann | Grenzwert von 250 Objekten&sup1;         |
|Anzahl von Teams, in denen ein Benutzer Mitglied sein kann|1 000&sup2;|
|Anzahl von Mitgliedern in einem Team | 25.000<sup>6</sup>     |
|Anzahl von Besitzern pro Team | 100   |
|Anzahl organisationsweiter Teams, die in einem Mandanten zulässig sind | 5&sup2;     |
|Anzahl der Mitglieder in einem [organisationsweiten Team](create-an-org-wide-team.md) | 10.000       |
|Anzahl der Teams, die ein globaler Administrator erstellen kann        |  500.000   |
|Anzahl von Teams, die eine Microsoft 365- oder Office 365-Organisation haben kann    | 500 000&sup3;     |
|Anzahl der Kanäle pro Team    | 200 (einschließlich gelöschter Kanäle)<sup>4</sup>        |
|Anzahl der privaten Kanäle pro Team    |30 (einschließlich gelöschter Kanäle)<sup>4</sup>        |
|Anzahl der Mitglieder in einem privaten Kanal    |250|
|Maximale Größe einer Verteilerliste, einer Sicherheitsgruppe oder einer Office 365-Gruppe, die in ein Team importiert werden kann.    |3.500|
|Maximale Anzahl von Mitgliedern in einer Office 365-Gruppe, die in ein Team umgewandelt werden kann    |10 000<sup>6</sup>     |
|Größe eines Beitrags in einer Kanalunterhaltung | Ca. 28 KB pro Beitrag<sup>5</sup> |

<sup>1</sup> Jedes Verzeichnisobjekt in Azure Active Directory zählt. Globale Administratoren und Apps, die Microsoft Graph mit [Anwendungsberechtigungen](/graph/permissions-reference) aufrufen, sind von diesem Grenzwert ausgenommen.

<sup>2</sup> Diese Beschränkung umfasst archivierte Teams. 

<sup>3</sup> Um die Anzahl der Teams weiter zu erhöhen, müssen Sie den Microsoft-Support kontaktieren und eine weitere Erhöhung der Anzahl von Azure Active Directory-Objekten in Ihrem Mandanten beantragen. Der Anstieg wird nur für Produktionsszenarien in Echtzeit vorgenommen.

<sup>4</sup> Gelöschte Kanäle können innerhalb von 30 Tagen wiederhergestellt werden. Während dieser 30 Tage wird ein gelöschter Kanal weiterhin in das Limit von 200 Kanälen oder 30 privaten Kanälen pro Team eingerechnet. Nach 30 Tagen wird ein gelöschter Kanal samt seiner Inhalte endgültig gelöscht und der Kanal wird nicht mehr in das Kanallimit pro Team eingerechnet.

<sup>5</sup> 28 KB ist ein ungefährer Grenzwert, da er die Nachricht selbst (Text, Bildlinks usw.), @Erwähnungen, die Anzahl der Connectors und Reaktionen umfasst.

<sup>6</sup> Teams in der GCC können 25 000 Mitglieder aufnehmen, aber Teams in der GCCH/DoD nur 2.500 Mitglieder. Beachten Sie des Weiteren, dass Teams-/Kanal-Erwähnungen in Teams mit mehr 10.000 Mitgliedern geblockt sind.

## <a name="messaging"></a>Messaging

### <a name="chat"></a>Chat

Benutzer, die an Gesprächen teilnehmen, die Teil der Chat-Liste in Microsoft Teams sind, müssen ein Exchange Online-Postfach (cloudbasiert) für einen Administrator haben, um Unterhaltungen im Chat zu durchsuchen. Der Grund hierfür ist, dass Unterhaltungen, die Teil der Chat-Liste sind, in den cloudbasierten Postfächern der Chat-Teilnehmer gespeichert werden. Wenn ein Chat-Teilnehmer nicht über ein Exchange Online-Postfach verfügt, kann der Administrator Chat-Unterhaltungen nicht durchsuchen oder sperren. Beispielsweise können in einer Exchange-Hybridbereitstellung Benutzer mit lokalen Postfächern an Unterhaltungen teilnehmen, die Teil der Chat-Liste in Microsoft Teams sind. Der Inhalt dieser Unterhaltungen ist in diesem Fall jedoch nicht durchsuchbar und kann nicht gesperrt werden, da die Benutzer keine cloudbasierten Postfächer haben. (Weitere Informationen finden Sie unter [Interaktion von Exchange und Microsoft Teams](exchange-teams-interact.md).)

Der Microsoft Teams-Chat funktioniert in einem Microsoft Exchange-Backend, sodass Grenzwerte für das Exchange-Messaging auf die Chat-Funktion in Microsoft Teams angewendet werden.

|Feature  | Obergrenze  |
|---------|---------|
|Anzahl der Personen in einem privaten Chat<sup>1</sup>  | 250<sup>2</sup> |
|Anzahl von Personen in einem Video- oder Audioanruf aus dem Chat | 20 |
|Anzahl der Dateianlagen<sup>3</sup>  |10     |
|Größe des Chats | Ca. 28 KB pro Beitrag<sup>4</sup> |

<sup>1</sup> Wenn mehr als 20 Personen an einem Chat teilnehmen, werden die folgenden Chat-Funktionen deaktiviert: automatische Outlook-Antworten und Teams-Statusmeldungen; Eingabeindikator; Video- und Telefonanrufe; Freigabe; Lesebestätigungen. Die Schaltfläche „Übermittlungsoptionen festlegen“ (!) wird ebenfalls entfernt, wenn private Gruppenchats mehr als 20 Mitglieder umfassen.

<sup>2</sup> Einem Gruppenchat können jeweils nur 200 Mitglieder hinzugefügt werden. [Weitere Informationen finden Sie in diesem Artikel](/microsoftteams/troubleshoot/teams-administration/unable-send-message-group-chat).

<sup>3</sup> Falls die Anzahl der Anlagen dieses Limit überschreitet, wird eine Fehlermeldung angezeigt.

<sup>4</sup> 28 KB ist ein ungefährer Grenzwert, da er die Nachricht selbst (Text, Bildlinks usw.), @Erwähnungen und Reaktionen umfasst.

### <a name="emailing-a-channel"></a>Senden von E-Mails an einen Kanal

 Wenn Benutzer eine E-Mail an einen Kanal in Teams senden möchten, verwenden sie die E-Mail-Adresse des Kanals. Wenn eine E-Mail-Adresse Teil eines Kanals ist, kann jeder darauf antworten, um eine Unterhaltung zu beginnen. Hier sind einige geltende Grenzwerte zum Senden von E-Mails an einen Kanal aufgeführt.

|Feature  | Obergrenze  |
|---------|---------|
|Nachrichtengröße<sup>1<sup> | 24 KB |
|Anzahl der Dateianlagen <sup>2</sup>  |20     |
|Größe der einzelnen Dateianlagen | Kleiner als 10 MB |
|Anzahl von Inlinebildern<sup>2</sup> |50   |

<sup>1</sup> Wenn die Nachricht dieses Limit überschreitet, wird eine Vorschaunachricht generiert und der Benutzer wird aufgefordert, die Original-E-Mail über den bereitgestellten Link herunterzuladen und anzusehen.

<sup>2</sup> Falls die Anzahl der Anlagen oder Bilder dieses Limit überschreitet, wird eine Fehlermeldung angezeigt.

Weitere Informationen finden Sie unter [Exchange Online-Begrenzungen](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits).

> [!NOTE]
> Die Beschränkungen für Nachrichtengröße, Dateianlagen und Inline-Bilder sind für alle Microsoft 365- und Office 365-Lizenzen identisch. Das Senden von E-Mails an einen Kanal ist in Microsoft Teams für Office GCC/GCCH/DOD-Organisationen nicht verfügbar.

## <a name="channel-names"></a>Kanalnamen

Kanalnamen dürfen folgende Zeichen oder Worte nicht enthalten:

|Typ|Beispiel|
|---------|---------|
|Zeichen     | ~ # % & * { } + / \ : < > ? &#124; ' " , ..        |
|Zeichen in diesen Bereichen:    | 0 bis 1F<br>80 bis 9F        |
|Words     | Formulare, CON, CONIN$, CONOUT$, PRN, AUX, NUL, COM1 to COM9, LPT1 to LPT9, desktop.ini,  &#95;vti&#95;|

Kanalnamen dürfen auch nicht mit einem Unterstrich (_) oder Punkt (.) beginnen oder mit einem Punkt (.) enden.

## <a name="meetings-and-calls"></a>Besprechungen und Anrufe

> [!IMPORTANT]
> **Das Limit für Microsoft 365 Liveereignisse wird erhöht**
>
> **Um die Bedürfnisse unserer Kunden weiterhin zu unterstützen, werden wir bis zum 30. Juni 2021 temporäre Limiterhöhungen für Liveereignisse verlängern, beispielsweise**:
>
>- Ereignisunterstützung für bis zu 20.000 Teilnehmer
>- 50 Ereignisse können über einen Mandanten gleichzeitig gehostet werden
>- Ereignisdauer von 16 Stunden pro Übertragung
>
> Außerdem können Live Events mit bis zu 100.000 Teilnehmern über das Microsoft 365-Unterstützungsprogramm geplant werden. Das Team bewertet jede Anfrage und arbeitet mit Ihnen zusammen, um die eventuell verfügbaren Optionen zu bestimmen. [Weitere Informationen](https://aka.ms/Stream/Blog/LiveEventOptions).

|Feature     | Obergrenze |
|------------|---------------|
|Anzahl von Personen in einer Besprechung (können chatten und sich einwählen)  | 1000, umfasst GCC, aber noch nicht für GCC, DoD oder A1 (300). Mit **Nur anzeigen** können bis zu 20.000 Teilnehmer als Zuhörer an einer Besprechung teilnehmen, bei der der Organisator über eine Lizenz für E3/E5/A3/A5-SKU sowie über eine Behördenlizenz (GCC, GCC High, DoD) verfügt. Erfahren Sie mehr über das [Nur anzeigen-Erlebnis](view-only-meeting-experience.md).|
|Anzahl von Personen in einem Video- oder Audioanruf aus dem Chat | 20 |
|Maximale Größe von PowerPoint-Dateien | 2GB|
|Teams hält [Besprechungsaufzeichnungen](cloud-recording.md), die nicht in Microsoft Stream hochgeladen werden, verfügbar für den lokalen Download | 20 Tage |

### <a name="meeting-expiration"></a>Ablauf der Besprechung

> [!NOTE]
> Eine Besprechungs-URL funktioniert immer. Das Ablaufdatum bezieht sich nur auf PSTN-Einwahlnummern und/oder zugrunde liegende Besprechungsrichtlinien und -einstellungen.

|Besprechungstyp  |Besprechung läuft nach diesem Zeitraum ab  |Jedes Mal, wenn Sie eine Besprechung starten oder aktualisieren, verlängert sich der Ablaufzeitpunkt um die entsprechende Zeit  |
|---------|---------|---------|
|Besprechung beginnen     |Startzeitpunkt + 8 Stunden         |Nicht zutreffend         |
|Regulär ohne Endzeitpunkt     |Startzeitpunkt + 60 Tage         | 60 Tage        |
|Regulär mit Endzeitpunkt     |Endzeitpunkt + 60 Tage         |60 Tage         |
|Wiederkehrend ohne Endzeitpunkt     |Startzeitpunkt + 60 Tage         |60 Tage         |
|Wiederkehrend mit Endzeitpunkt     |Endzeitpunkt des letzten Vorkommens + 60 Tage         |60 Tage         |

> [!NOTE]
> Microsoft Teams-Besprechungen haben ein Zeitlimit von 24 Stunden.

## <a name="teams-live-events"></a>Live Events in Teams

|Feature     | Obergrenze |
|------------|---------------|
|Zielgruppengröße | 10.000 Teilnehmer |
|Dauer des Ereignisses | 4 Stunden |
|Gleichzeitige Live Events in einer Microsoft 365- oder Office 365-Organisation<sup>1</sup> | 15 |

<sup>1</sup> Sie können beliebig viele Live Events planen, aber nur 15 gleichzeitig ausführen. Sobald der Produzent einem Live-Ereignis beitritt, wird es als ausgeführt betrachtet. Der Produzent, der versucht, am 16. Live-Ereignis teilzunehmen, erhält eine Fehlermeldung.

Weitere Informationen zu Liveereignissen und eine Gegenüberstellung von Teams-Liveereignissen und Skype Meeting Broadcast finden Sie unter [Teams-Liveereignisse und Skype Meeting Broadcast](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast). Siehe auch [Planen eines Liveereignisses in Teams](https://support.microsoft.com/office/schedule-a-teams-live-event-7a9ce97c-e1cd-470f-acaf-e6dfc179a0e2).

> [!IMPORTANT]
> **Das Limit für Microsoft 365 Live Events wird erhöht**
>
> **Um die Bedürfnisse unserer Kunden weiterhin zu unterstützen, werden wir bis zum 30. Juni 2021 temporäre Limiterhöhungen für Liveereignisse verlängern, beispielsweise**:
>
>- Ereignisunterstützung für bis zu 20.000 Teilnehmer
>- 50 Ereignisse können über einen Mandanten gleichzeitig gehostet werden
>- Ereignisdauer von 16 Stunden pro Übertragung
>
> Außerdem können Live Events mit bis zu 100.000 Teilnehmern über das Microsoft 365-Unterstützungsprogramm geplant werden. Das Team bewertet jede Anfrage und arbeitet mit Ihnen zusammen, um die eventuell verfügbaren Optionen zu bestimmen. [Weitere Informationen](https://aka.ms/Stream/Blog/LiveEventOptions). 

## <a name="presence-in-outlook"></a>Anwesenheit in Outlook

Die Anwesenheit in Teams wird in Outlook ab der Outlook 2013-Desktop-App und höher unterstützt. Wenn Sie mehr über die Anwesenheit in Teams wissen möchten, lesen Sie [Anwesenheit von Benutzern in Teams](presence-admins.md).

## <a name="storage"></a>Speicher

Jedes Team in Microsoft Teams verfügt über eine Teamsite in SharePoint Online, und jeder Kanal in einem Team erhält einen Ordner innerhalb der Dokumentbibliothek der Standardteamsite. In einer Unterhaltung freigegebene Dateien werden automatisch zur Dokumentbibliothek hinzugefügt, und in SharePoint festgelegte Berechtigungen und Dateisicherheitsoptionen werden automatisch in Teams übernommen.

> [!NOTE]
> Jeder [private Kanal](./private-channels.md) hat seine eigene SharePoint-Website (bisher als „Websitesammlung“ bezeichnet).

Wenn Sie SharePoint Online nicht in Ihrem Mandanten aktiviert haben, können Microsoft Teams-Benutzer nicht immer Dateien in Teams freigeben. Benutzer im privaten Chat können Dateien auch nicht freigeben, weil OneDrive for Business (mit der SharePoint-Lizenz verknüpft) für diese Funktionalität erforderlich ist.

Beim Speichern der Dateien in der SharePoint Online-Dokumentbibliothek und OneDrive for Business werden alle auf der Mandantenebene konfigurierten Complianceregeln eingehalten. (Weitere Informationen finden Sie unter [Interaktion von SharePoint Online und OneDrive for Business mit Microsoft Teams](sharepoint-onedrive-interact.md).)

Da Teams in einem SharePoint Online-Backend für die Dateifreigabe ausgeführt wird, gelten die SharePoint-Einschränkungen für den Bereich „Dateien“ innerhalb eines Teams. Hier sind die entsprechenden Speichergrenzwerte für SharePoint Online aufgeführt.

|Feature                 |Microsoft 365 Business Basic  |Microsoft 365 Business Standard   |Office 365 Enterprise E1  |Office 365 Enterprise E3  |Office 365 Enterprise E5  |Office 365 Enterprise F1  |
|------------------------|---------|---------|---------|---------|---------|---------|
|Speicher                 |1 TB pro Organisation plus 10 GB pro erworbener Lizenz  |1 TB pro Organisation plus 10 GB pro erworbener Lizenz  |1 TB pro Organisation plus 10 GB pro erworbener Lizenz   |1 TB pro Organisation plus 10 GB pro erworbener Lizenz |1 TB pro Organisation plus 10 GB pro erworbener Lizenz  |1 TB pro Organisation           |
|Speicher für Teams-Dateien |Bis zu 25 TB pro Website oder Gruppe |Bis zu 25 TB pro Website oder Gruppe |Bis zu 25 TB pro Website oder Gruppe |Bis zu 25 TB pro Website oder Gruppe |Bis zu 25 TB pro Website oder Gruppe |Bis zu 25 TB pro Website oder Gruppe |
|Maximale Größe für Dateiuploads (pro Datei)    |100 GB    |100 GB    |100 GB    |100 GB    |100 GB    |100 GB    |

Kanäle werden durch für das Team erstellte Ordner innerhalb der SharePoint Online-Website (bisher als „Websitesammlung“ bezeichnet) gesichert. Deshalb teilen sich Dateiregisterkarten in Kanälen die Speicherlimits des Teams, zu dem sie gehören.

Weitere Informationen finden Sie unter [SharePoint Online-Beschränkungen](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).

## <a name="class-teams"></a>Kursteams

Microsoft Teams für Bildungseinrichtungen stellt Vorlagen bereit, die für einmalige Schulungsszenarien konzipiert wurden, z. B. Unterricht im Kursraum. Weitere Informationen zu Teamtypen, einschließlich Kursteams, finden Sie in [Auswählen eines Teamtyps für die Zusammenarbeit in Microsoft Teams](https://support.microsoft.com/office/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67).

Ein Kursteam ist ein Vorlagentyp mit zusätzlichen Apps, dessen Grenzwerte unabhängig von der Anzahl der Teammitglieder sind.

> [!NOTE]
> Für die Verwendung von Kursteams ist eine [Office 365 Education-Lizenz](https://www.microsoft.com/education/products/office) erforderlich.

In der nachstehenden Tabelle sind die Grenzwerte für Kursteams aufgelistet:

|Feature  |Obergrenze  |
|---------|---------|
|Anzahl von Mitgliedern in einem Team    | Lesen Sie in diesem Artikel den Abschnitt [Teams und Kanäle](#teams-and-channels).        |
|Anzahl von Mitgliedern, die Aufgaben in einem Kursteam verwenden sollen    | 200        |
|Anzahl von Mitgliedern, die ein OneNote-Kursnotizbuch in einem Kursteam verwenden sollen     |200         |

Ein Kursteam kann mehr als 200 Mitglieder unterstützen. Wenn Sie aber vorhaben, innerhalb Ihres Teams die App „Aufgaben“ oder die App „Kursnotizbuch“ zu verwenden, muss die Anzahl von Mitgliedern unter der vorstehenden Obergrenze bleiben.

## <a name="tags"></a>Tags

|Feature  |Obergrenze  |
|---------|---------|
|Anzahl der Tags pro Team    | 100        |
|Anzahl der vorgeschlagenen Standardtags pro Team    | 25        |
|Anzahl der Teammitglieder, die einem Tag zugeordnet werden    |100         |
|Die Anzahl der Tags, die einem Benutzer per Team zugewiesen werden.    |25         |

## <a name="contacts"></a>Kontakte

Microsoft Teams verwendet die folgenden Kontakte:

- Kontakte in der Active Directory Ihrer Organisation
- Kontakte, die dem Outlook-Standardordner des Benutzers hinzugefügt wurden

Microsoft Teams-Benutzer können mit jeder Person in der Active Directory Ihrer Organisation kommunizieren, und sie können jede Person in der Active Directory Ihrer Organisation als Kontakt bzw. zu ihren Kontaktlisten hinzufügen, indem sie zu **Chat** > **Kontakte** beziehungsweise zu **Anrufe** > **Kontakte** gehen.

Microsoft Teams-Benutzer können außerdem eine Person, die sich nicht in der Active Directory Ihrer Organisation befindet, unter **Anrufe** > **Kontakte** als Kontakt hinzufügen.

## <a name="browsers"></a>Browser

[!INCLUDE [browser-support](includes/browser-support.md)]

## <a name="operating-systems"></a>Betriebssysteme

Informationen zu den Betriebssystemanforderungen finden Sie unter [Beziehen von Clients für Microsoft Teams](get-clients.md).
