---
title: Grenzwerte und Spezifikationen für Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karuanag
description: Erfahren Sie mehr über die Grenzwerte, Spezifikationen und anderen Anforderungen für Microsoft Teams.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 854c6beeccdae6286bc609a226a49b15de1114e6
ms.sourcegitcommit: f2cdb2c1abc2c347d4dbdca659e026a08e60ac11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "36493002"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a>Grenzwerte und Spezifikationen für Microsoft Teams

In diesem Artikel werden einige der Grenzwerte, Spezifikationen und anderen Anforderungen für Teams beschrieben.

## <a name="teams-and-channels"></a>Teams und Kanäle

|Feature    | Obergrenze |
|-----------|---------------|
|Anzahl der Teams, die ein Benutzer erstellen kann | Grenzwert von 250 Objekten&sup1;         |
|Anzahl der Mitglieder in einem Team | 5.000       |
|Anzahl der in einem Mandanten zulässigen organisationsweiten Teams | 5     |
|Anzahl der Mitglieder in einem [organisationsweiten Team](create-an-org-wide-team.md) | 5.000       |
|Anzahl der Teams, die ein globaler Administrator erstellen kann        |  500.000   |
|Anzahl der Teams in einem Office 365-Mandanten    | 500.000&sup2;     |
|Anzahl der Kanäle pro Team    | 200 (enthält gelöschte Kanäle) &sup3;         |

&sup1;Jedes Verzeichnisobjekt in Azure Active Directory zählt. Globale Administratoren und Apps, die Microsoft Graph mit [Anwendungsberechtigungen](https://docs.microsoft.com/graph/permissions-reference) aufrufen, sind von diesem Grenzwert ausgeschlossen.

&sup2; Dieser Grenzwert umfasst Archivierte Teams.

&sup3; gelöschte Kanäle können innerhalb von 30 Tagen wiederhergestellt werden. Während dieser 30 Tage wird ein gelöschter Kanal weiterhin für den 200-Kanal pro Team Grenze gezählt. Nach 30 Tagen werden ein gelöschter Kanal und dessen Inhalt endgültig gelöscht, und der Kanal zählt nicht mehr zu den 200-Kanälen pro Team Grenze.

## <a name="messaging"></a>Messaging

### <a name="chat"></a>Chat

Benutzer, die an Unterhaltungen teilnehmen, die Teil der Chatliste in Teams sind, müssen über ein Exchange Online-Postfach (Cloud-basiert) verfügen, damit ein Administrator Chat Unterhaltungen durchsuchen können. Das liegt daran, dass Konversationen, die Teil der Chatliste sind, in den cloudbasierten Postfächern der Chat-Teilnehmer gespeichert werden. Wenn ein Chat-Teilnehmer nicht über ein Exchange Online-Postfach verfügt, kann der Administrator Chat-Unterhaltungen nicht durchsuchen oder sperren. In einer Exchange-hybridbereitstellung können Benutzer mit lokalen Postfächern möglicherweise an Unterhaltungen teilnehmen, die Teil der Chatliste in Teams sind. Der Inhalt dieser Unterhaltungen ist in diesem Fall jedoch nicht durchsuchbar und kann nicht gesperrt werden, da die Benutzer keine cloudbasierten Postfächer haben. (Weitere Informationen finden Sie unter [Interaktion von Exchange und Microsoft Teams](exchange-teams-interact.md).)

Teams-Chat funktioniert auf einem Microsoft Exchange-Back-End, daher gelten Exchange-Messaging-Grenzwerte für die Chat-Funktion in Teams.

|Feature  | Obergrenze  |
|---------|---------|
|Anzahl der Personen in einem privaten Chat<sup>1</sup>  | 100    |
|Anzahl der Dateianlagen<sup>2</sup>  |10     |

<sup>1</sup> Wenn Sie mehr als 20 Personen in einem Chat haben, sind die folgenden Chat-Funktionen deaktiviert: Automatische Outlook-Antworten und Teams-Statusmeldungen; Eingabe Anzeige; Video-und Audioanrufe; Freigabe Lesebestätigungen

<sup>2</sup> Wenn die Anzahl der Anlagen diesen Grenzwert überschreitet, wird eine Fehlermeldung angezeigt.

### <a name="emailing-a-channel"></a>Senden eines Kanals per e-Mail

 Wenn Benutzer eine E-Mail an einen Kanal in Teams senden möchten, verwenden sie die E-Mail-Adresse des Kanals. Wenn eine e-Mail Teil eines Kanals ist, kann jeder darauf antworten, um eine Unterhaltung zu beginnen. Hier einige geltende Grenzwerte zum Senden von E-Mails an einen Kanal:

|Feature  | Obergrenze  |
|---------|---------|
|Nachrichtengröße<sup>1<sup> | 24 KB |
|Anzahl der Dateianlagen<sup>2</sup>  |20     |
|Größe der einzelnen Dateianlagen | Weniger als 10 MB |
|Anzahl der Inline Bilder<sup>2</sup> |50   |

<sup>1</sup> Wenn die Nachricht diesen Grenzwert überschreitet, wird eine Vorschau Nachricht generiert, und der Benutzer wird aufgefordert, die ursprüngliche e-Mail über den bereitgestellten Link herunterzuladen und anzuzeigen.

<sup>2</sup> Wenn die Anzahl der Anlagen oder Bilder diesen Grenzwert überschreitet, wird eine Fehlermeldung angezeigt.

Weitere Informationen finden Sie unter [Exchange Online-Grenzwerte](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits).

> [!NOTE]
> Die Grenzwerte für Nachrichtengröße, Dateianlagen und Inline Bilder sind für alle Office 365-Lizenzen identisch.

## <a name="channel-names"></a>Kanalnamen

Kanalnamen dürfen die folgenden Zeichen oder Wörter nicht enthalten.

|||
|---------|---------|
|Zeichen     | ~ #% & * {} +/\: #a3? &#124; ""..        |
|Zeichen in diesen Bereichen    | 0 bis 1F<br>80 bis 9F        |
|Wörter     | Formulare, con, konische $, CONOUT $, PRN, AUX, NUL, COM1 zu COM9, LPT1 zu LPT9, Desktop. ini, &#95;VTI&#95;|

Kanalnamen können auch nicht mit einem Unterstrich (_) oder Punkt (.) beginnen oder mit einem Punkt (.) enden.

## <a name="meetings-and-calls"></a>Besprechungen und Anrufe

|Feature     | Obergrenze |
|------------|---------------|
|Anzahl der Personen in einer Besprechung  | 250    |

## <a name="teams-live-events"></a>Live-Events für Teams

|Feature     | Obergrenze |
|------------|---------------|
|Zielgruppengröße | 10.000-Teilnehmer |
|Dauer des Ereignisses | 4 Stunden |
|Gleichzeitige Live Ereignisse in einem Office 365-Mandanten | 15 |

Weitere Informationen zu Live Ereignissen und einem Vergleich der Live-Events von Teams mit Skype-Live Konferenz finden Sie unter [Teams Live-Events und Skype](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast)-Live Konferenz.

## <a name="storage"></a>Speicher

Jedes Team in Microsoft Teams verfügt über eine Teamsite in SharePoint Online, und jeder Kanal in einem Team erhält einen Ordner innerhalb der Dokumentbibliothek der Standardteamsite. In einer Unterhaltung freigegebene Dateien werden automatisch zur Dokumentbibliothek hinzugefügt, und in SharePoint festgelegte Berechtigungen und Dateisicherheitsoptionen werden automatisch in Teams übernommen.

Wenn Sie SharePoint Online nicht in Ihrem Mandanten aktiviert haben, können Microsoft Teams-Benutzer nicht immer Dateien in Teams freigeben. Benutzer im privaten Chat können Dateien auch nicht freigeben, weil OneDrive for Business (mit der SharePoint-Lizenz verknüpft) für diese Funktionalität erforderlich ist.

Beim Speichern der Dateien in der SharePoint Online-Dokumentbibliothek und OneDrive for Business werden alle auf der Mandantenebene konfigurierten Complianceregeln eingehalten. (Weitere Informationen finden Sie unter [Interaktion von SharePoint Online und OneDrive for Business mit Microsoft Teams](sharepoint-onedrive-interact.md).)

Da Teams in einem SharePoint Online-Backend für die Dateifreigabe ausgeführt wird, gelten die SharePoint-Einschränkungen für den Bereich „Dateien“ innerhalb eines Teams. Hier die entsprechenden Speichergrenzwerte für SharePoint Online:

|Feature                 |Office 365 Business Essentials  |Office 365 Business Premium   |Office 365 Enterprise E1  |Office 365 Enterprise E3  |Office 365 Enterprise E5  |Office 365 Enterprise F1  |
|------------------------|---------|---------|---------|---------|---------|---------|
|Speicher                 |1 TB pro Organisation plus 10 GB pro erworbener Lizenz  |1 TB pro Organisation plus 10 GB pro erworbener Lizenz  |1 TB pro Organisation plus 10 GB pro erworbener Lizenz   |1 TB pro Organisation plus 10 GB pro erworbener Lizenz |1 TB pro Organisation plus 10 GB pro erworbener Lizenz  |1 TB pro Organisation           |
|Speicher für Teams-Dateien |Bis zu 25 TB pro Websitesammlung oder Gruppe |Bis zu 25 TB pro Websitesammlung oder Gruppe |Bis zu 25 TB pro Websitesammlung oder Gruppe |Bis zu 25 TB pro Websitesammlung oder Gruppe |Bis zu 25 TB pro Websitesammlung oder Gruppe |Bis zu 25 TB pro Websitesammlung oder Gruppe |
|Beschränkung des Dateiuploads (pro Datei)    |15 GB    |15 GB    |15 GB    |15 GB    |15 GB    |15 GB    |

Kanäle werden durch Ordner in der für das Team erstellten SharePoint Online-Websitesammlung gesichert, sodass Dateiregisterkarten in Kanälen die Speichergrenzwerte des Teams teilen, dem Sie angehören.

Weitere Informationen finden Sie unter [SharePoint Online-Grenzwerte](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).

## <a name="contacts"></a>Kontakte

Teams verwendet diese Kontakte:

- Kontakte im Active Directory Ihrer Organisation
- Kontakte, die zum Outlook-Standardordner des Benutzers hinzugefügt wurden

Benutzer von Teams können mit jeder Person im Active Directory Ihrer Organisation kommunizieren und können beliebige Personen aus dem Active Directory Ihrer Organisation als Kontakt und zu ihren Kontaktlisten hinzufügen, indem Sie zu **Chat** > -**Kontakten** oder **anrufen**  >  wechseln. **Kontakte**.

Benutzer von Teams können auch eine Person, die sich nicht im Active Directory Ihrer Organisation befindet, als Kontakt hinzufügen, indem Sie**Kontakte** **anrufen** > .

## <a name="browsers"></a>Browser

[!INCLUDE [browser-support](includes/browser-support.md)]

## <a name="operating-systems"></a>Betriebssysteme

Informationen zu den Betriebssystemanforderungen finden Sie unter [Beziehen von Clients für Microsoft Teams](get-clients.md).
