---
title: Grenzwerte und Spezifikationen für Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Erfahren Sie mehr über die Grenzwerte, Spezifikationen und anderen Anforderungen für Microsoft Teams.
localization_priority: Priority
ms.collection:
- M365-collaboration
- SPO_Content
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: d89c2238e1956c4e51cbef72ce89347cec98a9e4
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40990120"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a>Grenzwerte und Spezifikationen für Microsoft Teams

In diesem Artikel werden einige der Grenzwerte, Spezifikationen und anderen Anforderungen für Teams beschrieben.

## <a name="teams-and-channels"></a>Teams und Kanäle

|Feature    | Obergrenze |
|-----------|---------------|
|Anzahl der Teams, die ein Benutzer erstellen kann | Grenzwert von 250 Objekten&sup1;         |
|Anzahl von Teams, in denen ein Benutzer Mitglied sein kann|1.000|
|Anzahl der Mitglieder in einem Team | 5,000       |
|Anzahl organisationsweiter Teams, die in einem Mandanten zulässig sind | 5     |
|Anzahl der Mitglieder in einem [organisationsweiten Team](create-an-org-wide-team.md) | 5.000       |
|Anzahl der Teams, die ein globaler Administrator erstellen kann        |  500.000   |
|Anzahl der Teams in einem Office 365-Mandanten    | 500.000&sup2;     |
|Anzahl der Kanäle pro Team    | 200 (einschließlich gelöschter Kanäle)&sup3;         |
|Anzahl der privaten Kanäle pro Team    |30|

&sup1; Jedes Verzeichnisobjekt in Azure Active Directory zählt. Globale Administratoren und Apps, die Microsoft Graph mit [Anwendungsberechtigungen](https://docs.microsoft.com/graph/permissions-reference) aufrufen, sind von diesem Grenzwert ausgeschlossen.

&sup2; Diese Beschränkung umfasst archivierte Teams.

&sup3; Gelöschte Kanäle können innerhalb von 30 Tagen wiederhergestellt werden. Während dieser 30 Tage wird ein gelöschter Kanal weiterhin in das 200-Kanallimit pro Team eingerechnet. Nach 30 Tagen wird ein gelöschter Kanal und dessen Inhalte endgültig gelöscht, und der Kanal wird nicht mehr in das 200-Kanallimit pro Team eingerechnet.

## <a name="messaging"></a>Messaging

### <a name="chat"></a>Chat

Benutzer, die an Gesprächen teilnehmen, die Teil der Chat-Liste in Microsoft Teams sind, müssen ein Exchange Online-Postfach (cloudbasiert) für einen Administrator haben, um Unterhaltungen im Chat zu durchsuchen. Der Grund hierfür ist, dass Unterhaltungen, die Teil der Chat-Liste sind, in den cloudbasierten Postfächern der Chat-Teilnehmer gespeichert werden. Wenn ein Chat-Teilnehmer nicht über ein Exchange Online-Postfach verfügt, kann der Administrator Chat-Unterhaltungen nicht durchsuchen oder sperren. Beispielsweise können in einer Exchange-Hybridbereitstellung Benutzer mit lokalen Postfächern an Unterhaltungen teilnehmen, die Teil der Chat-Liste in Microsoft Teams sind. Der Inhalt dieser Unterhaltungen ist in diesem Fall jedoch nicht durchsuchbar und kann nicht gesperrt werden, da die Benutzer keine cloudbasierten Postfächer haben. (Weitere Informationen finden Sie unter [Interaktion von Exchange und Microsoft Teams](exchange-teams-interact.md).)

Der Microsoft Teams-Chat funktioniert in einem Microsoft Exchange-Backend, sodass Grenzwerte für das Exchange-Messaging auf die Chat-Funktion in Microsoft Teams angewendet werden.

|Feature  | Obergrenze  |
|---------|---------|
|Anzahl der Personen in einem privaten Chat<sup>1</sup>  | 100    |
|Anzahl der Dateianlagen <sup>2</sup>  |10     |

<sup>1</sup> Wenn mehr als 20 Personen an einem Chat teilnehmen, werden die folgenden Chat-Funktionen deaktiviert: automatische Outlook-Antworten und Teams-Statusmeldungen; Eingabeindikator; Video- und Telefonanrufe; Freigabe; Lesebestätigungen.

<sup>2</sup> Falls die Anzahl der Anlagen dieses Limit überschreitet, wird eine Fehlermeldung angezeigt.

### <a name="emailing-a-channel"></a>Senden von E-Mails an einen Kanal

 Wenn Benutzer eine E-Mail an einen Kanal in Microsoft Teams senden möchten, verwenden sie dazu die E-Mail-Adresse des Kanals. Wenn eine E-Mail Teil eines Kanals ist, kann jeder darauf antworten, um eine Unterhaltung zu beginnen. Hier einige geltende Grenzwerte zum Senden von E-Mails an einen Kanal:

|Funktion  | Obergrenze  |
|---------|---------|
|Nachrichtengröße<sup>1<sup> | 24 KB |
|Anzahl der Dateianlagen <sup>2</sup>  |20     |
|Größe der einzelnen Dateianlagen | Kleiner als 10 MB |
|Anzahl von Inlinebildern<sup>2</sup> |50   |

<sup>1</sup> Wenn die Nachricht dieses Limit überschreitet, wird eine Vorschaunachricht generiert und der Benutzer wird aufgefordert, die Original-E-Mail über den bereitgestellten Link herunterzuladen und anzusehen.

<sup>2</sup> Falls die Anzahl der Anlagen oder Bilder dieses Limit überschreitet, wird eine Fehlermeldung angezeigt.

Weitere Informationen finden Sie unter [Exchange Online-Begrenzungen](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits).

> [!NOTE]
> Die Beschränkungen für Nachrichtengröße, Dateianlagen und Inline-Bilder sind für alle Office 365-Lizenzen identisch.

## <a name="channel-names"></a>Kanalnamen

Kanalnamen dürfen keine der folgenden Zeichen oder Worte enthalten.

|||
|---------|---------|
|Zeichen     | ~ # % & * { } + / \ : < > ? &#124; ' " ..        |
|Zeichen in diesen Bereichen:    | 0 bis 1F<br>80 bis 9F        |
|Words     | Formulare, CON, CONIN$, CONOUT$, PRN, AUX, NUL, COM1 to COM9, LPT1 to LPT9, desktop.ini,  &#95;vti&#95;|

Kanalnamen dürfen auch nicht mit einem Unterstrich (_) oder Punkt (.) beginnen oder mit einem Punkt (.) enden.

## <a name="meetings-and-calls"></a>Besprechungen und Anrufe

|Feature     | Obergrenze |
|------------|---------------|
|Anzahl der Personen in einer Besprechung  | 250    |
|Maximale Größe von PowerPoint-Dateien | 2GB|

### <a name="meeting-expiration"></a>Ablauf der Besprechung

|Besprechungstyp  |Besprechung läuft nach diesem Zeitraum ab  |Jedes Mal, wenn Sie eine Besprechung starten oder aktualisieren, verlängert sich der Ablaufzeitpunkt um die entsprechende Zeit  |
|---------|---------|---------|
|Besprechung beginnen     |Startzeitpunkt + 8 Stunden         |Nicht zutreffend         |
|Regulär ohne Endzeitpunkt     |Startzeitpunkt + 60 Tage         | 60 Tage        |
|Regulär mit Endzeitpunkt     |Endzeitpunkt + 60 Tage         |60 Tage         |
|Wiederkehrend ohne Endzeitpunkt     |Startzeitpunkt + 60 Tage         |60 Tage         |
|Wiederkehrend mit Endzeitpunkt     |Endzeitpunkt des letzten Vorkommens + 60 Tage         |60 Tage         |



## <a name="teams-live-events"></a>Teams-Liveereignisse

|Funktion     | Obergrenze |
|------------|---------------|
|Zielgruppengröße | 10.000 Teilnehmer |
|Dauer des Ereignisses | 4 Stunden |
|Gleichzeitige Liveereignisse in einem Office 365-Mandanten | 15 |

Weitere Informationen zu Liveereignissen und eine Gegenüberstellung von Team-Liveereignissen und Skype-Livekonferenzen finden Sie unter [Teams-Liveereignisse und Skype-Livekonferenzen](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast).

## <a name="presence-in-outlook"></a>Anwesenheit in Outlook

Die Anwesenheit in Teams wird in Outlook ab der Outlook 2013-Desktop-App und höher unterstützt. Wenn Sie mehr über die Anwesenheit in Teams wissen möchten, lesen Sie [Anwesenheit von Benutzern in Teams](presence-admins.md).

## <a name="storage"></a>Speicher

Jedes Team in Microsoft Teams verfügt über eine Teamsite in SharePoint Online, und jeder Kanal in einem Team erhält einen Ordner innerhalb der Dokumentbibliothek der Standardteamsite. In einer Unterhaltung freigegebene Dateien werden automatisch zur Dokumentbibliothek hinzugefügt, und in SharePoint festgelegte Berechtigungen und Dateisicherheitsoptionen werden automatisch in Teams übernommen.

Wenn Sie SharePoint Online nicht in Ihrem Mandanten aktiviert haben, können Microsoft Teams-Benutzer nicht immer Dateien in Teams freigeben. Benutzer im privaten Chat können Dateien auch nicht freigeben, weil OneDrive for Business (mit der SharePoint-Lizenz verknüpft) für diese Funktionalität erforderlich ist.

Beim Speichern der Dateien in der SharePoint Online-Dokumentbibliothek und OneDrive for Business werden alle auf der Mandantenebene konfigurierten Complianceregeln eingehalten. (Weitere Informationen finden Sie unter [Interaktion von SharePoint Online und OneDrive for Business mit Microsoft Teams](sharepoint-onedrive-interact.md).)

Da Teams in einem SharePoint Online-Backend für die Dateifreigabe ausgeführt wird, gelten die SharePoint-Einschränkungen für den Bereich „Dateien“ innerhalb eines Teams. Hier die entsprechenden Speichergrenzwerte für SharePoint Online:

|Feature                 |Office 365 Business Essentials  |Office 365 Business Premium   |Office 365 Enterprise E1  |Office 365 Enterprise E3  |Office 365 Enterprise E5  |Office 365 Enterprise F1  |
|------------------------|---------|---------|---------|---------|---------|---------|
|Speicher                 |1 TB pro Organisation plus 10 GB pro erworbener Lizenz  |1 TB pro Organisation plus 10 GB pro erworbener Lizenz  |1 TB pro Organisation plus 10 GB pro erworbener Lizenz   |1 TB pro Organisation plus 10 GB pro erworbener Lizenz |1 TB pro Organisation plus 10 GB pro erworbener Lizenz  |1 TB pro Organisation           |
|Speicher für Teams-Dateien |Bis zu 25 TB pro Websitesammlung oder Gruppe |Bis zu 25 TB pro Websitesammlung oder Gruppe |Bis zu 25 TB pro Websitesammlung oder Gruppe |Bis zu 25 TB pro Websitesammlung oder Gruppe |Bis zu 25 TB pro Websitesammlung oder Gruppe |Bis zu 25 TB pro Websitesammlung oder Gruppe |
|Maximale Größe für Dateiuploads (pro Datei)    |15 GB    |15 GB    |15 GB    |15 GB    |15 GB    |15 GB    |

Kanäle werden durch Ordner innerhalb der SharePoint Online-Websitesammlung, die für das Team erstellt wurde, gesichert. Deshalb teilen sich Dateiregisterkarten in Kanälen die Speicherlimits des Teams, zu dem sie gehören.

Weitere Informationen finden Sie unter [SharePoint Online-Beschränkungen](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).

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
