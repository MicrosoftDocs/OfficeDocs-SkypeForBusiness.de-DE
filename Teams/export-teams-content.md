---
title: Exportieren von Inhalten mit den Export-APIs von Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: vikramju
description: In diesem Artikel erfahren Sie, wie Sie Teams-Inhalte mithilfe der Microsoft Teams-Export-APIs exportieren.
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b508b368629ce716a1269380eb1fffe2137620c8
ms.sourcegitcommit: 90f03a841f8ca33092dce65c543357c7c2f7b82a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2022
ms.locfileid: "66647647"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a>Exportieren von Inhalten mit den Export-APIs von Microsoft Teams

Mithilfe von Teams-Export-APIs können Sie 1:1-, Gruppenchats, Besprechungschats und Kanalnachrichten aus Microsoft Teams exportieren. Wenn Ihre Organisation Microsoft Teams-Nachrichten exportieren muss, können Sie sie mithilfe von Teams-Export-APIs extrahieren. *Chatnachricht* stellt eine einzelne Chatnachricht innerhalb eines [Kanals](/graph/api/resources/channel) oder [Chats](/graph/api/resources/chat) dar. Die Chatnachricht kann eine Chatstammnachricht oder Teil eines Antwortthreads sein, der durch die **eigenschaft "replyToId** " in der Chatnachricht definiert wird.

Hier sind einige Beispiele für die Verwendung dieser Export-APIs:

- **Beispiel 1**: Wenn Sie Microsoft Teams in Ihrer Organisation aktiviert haben und alle Microsoft Teams-Nachrichten programmgesteuert exportieren möchten, indem Sie den Datumsbereich für einen bestimmten Benutzer oder ein bestimmtes Team übergeben.
- **Beispiel 2**: Wenn Sie alle Benutzer- oder Teamnachrichten programmgesteuert täglich exportieren möchten, indem Sie einen Datumsbereich angeben. Export-APIs können alle Nachrichten abrufen, die während des angegebenen Datumsbereichs erstellt oder aktualisiert wurden.

## <a name="what-is-supported-by-the-teams-export-apis"></a>Was wird von den Teams-Export-APIs unterstützt?

- **Massenexport der Teams-Nachricht:** Teams-Export-APIs unterstützen bis zu 200 RPS pro App pro Mandant und 600 RPS für eine Anwendung. Mit diesen Einschränkungen sollten Sie in der Lage sein, Teams-Nachrichten in Massen zu exportieren.
- **Anwendungskontext**: Zum Aufrufen von Microsoft Graph muss Ihre App ein Zugriffstoken von der Microsoft Identity Platform abrufen. Das Zugriffstoken enthält Informationen zu Ihrer App und die Berechtigungen für die Ressourcen und APIs, die über Microsoft Graph verfügbar sind. Um ein Zugriffstoken zu erhalten, muss Ihre App beim Microsoft Identity Platform registriert und entweder von einem Benutzer oder einem Administrator für den Zugriff auf die benötigten Microsoft Graph-Ressourcen autorisiert werden.

    Wenn Sie bereits mit der Integration einer App in die Microsoft Identity Platform zum Abrufen von Token vertraut sind, finden Sie im Abschnitt "[Nächste Schritte](/graph/auth/auth-concepts#next-steps)" Informationen und Beispiele für Microsoft Graph.
- **Hybridumgebung:** Export-APIs unterstützen Nachrichten, die von Benutzern gesendet werden, die in der Hybridumgebung (lokales Exchange und Teams) bereitgestellt werden. Alle Nachrichten, die von Benutzern gesendet werden, die für die Hybridumgebung konfiguriert sind, können mithilfe von Export-APIs aufgerufen werden.
- **Vom Benutzer gelöschte Nachrichten:** Auf Nachrichten, die von Benutzern aus dem Teams-Client gelöscht werden, kann mithilfe von Export-APIs bis zu 21 Tage ab dem Zeitpunkt des Löschens zugegriffen werden.
- **Nachrichtenanlagen:** Export-APIs enthalten die Links zu den Anlagen, die als Teil von Nachrichten gesendet werden. Mithilfe von Export-APIs können Sie die in den Nachrichten angefügten Dateien abrufen.
- **Reaktionen:** Export-APIs unterstützen Reaktionen, die von einem Benutzer in einer Teams-Nachricht ausgelöst werden. Reaktionen, die derzeit unterstützt werden, sind Herz, wütend, wie, traurig, überrascht und lachen.
- **Eigenschaften von Chatnachrichten:** Die vollständige Liste der Eigenschaften, die von Teams-Export-APIs unterstützt werden, finden Sie [hier](/graph/api/resources/chatmessage#properties).


## <a name="how-to-access-teams-export-apis"></a>Zugreifen auf Teams-Export-APIs

- **Beispiel 1** ist eine einfache Abfrage zum Abrufen aller Nachrichten eines Benutzers oder Teams ohne Filter:

  ```HTTP
  GET https://graph.microsoft.com/v1.0/users/{id}/chats/getAllMessages
  ```

  ```HTTP
  GET https://graph.microsoft.com/v1.0/teams/{id}/channels/getAllMessages
  ```

- **Beispiel 2** ist eine Beispielabfrage zum Abrufen aller Nachrichten eines Benutzers oder Teams durch Angeben von Datumszeitfiltern und top 50-Nachrichten:

  ```HTTP
  GET https://graph.microsoft.com/v1.0/users/{id}/chats/getAllMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
  ```

  ```HTTP
  GET https://graph.microsoft.com/v1.0/teams/{id}/channels/getAllMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
  ```

> [!NOTE]
> Die API gibt die Antwort mit dem Link zur nächsten Seite zurück, falls mehrere Ergebnisse vorliegen. Rufen Sie zum Abrufen der nächsten Gruppe von Ergebnissen einfach GET für die URL von @odata.nextlink auf. Wenn @odata.nextlink nicht vorhanden oder null ist, werden alle Nachrichten abgerufen.

## <a name="prerequisites-to-access-teams-export-apis"></a>Voraussetzungen für den Zugriff auf Teams-Export-APIs

- Microsoft Teams-APIs in Microsoft Graph, die auf vertrauliche Daten zugreifen, gelten als geschützte APIs. Export-APIs erfordern eine zusätzliche Überprüfung über Berechtigungen und Zustimmung hinaus, bevor Sie sie verwenden können. Füllen Sie das [Anforderungsformular](https://aka.ms/teamsgraph/requestaccess) aus, um den Zugriff auf diese geschützten APIs anzufordern.
- Anwendungsberechtigungen werden von Apps verwendet, die ohne angemeldeten Benutzer ausgeführt werden. Anwendungsberechtigungen können nur von einem Administrator erteilt werden. Die folgenden Berechtigungen sind erforderlich:
  - *Chat.Read.All*: Ermöglicht den Zugriff auf alle 1:1-, Gruppenchat- und Besprechungschatnachrichten
  - *ChannelMessage.Read.All*: Ermöglicht den Zugriff auf alle Kanalnachrichten
  - *User.Read.All*: Ermöglicht den Zugriff auf die Liste der Benutzer für einen Mandanten

## <a name="license-requirements-for-teams-export-apis"></a>Lizenzanforderungen für Teams-Export-APIs

Die Export-API unterstützt Sicherheits- und Complianceszenarien (S+C) und allgemeine Verwendungsszenarien über einen Modellabfrageparameter. S+C-Szenarien (Modell A) umfassen Seedingkapazität und erfordern ein E5-Abonnement, und allgemeine Nutzungsszenarien (Modell B) sind für alle Abonnements verfügbar und werden nur genutzt. Weitere Informationen zu Seeding-Kapazitäts- und Verbrauchsgebühren finden Sie unter [Lizenzierungs- und Zahlungsanforderungen für Microsoft Graph Teams-APIs](/graph/teams-licenses).

### <a name="scmodel-a-scenarios"></a>S+C/Model A-Szenarien

Benutzer, die auf Anwendungen beschränkt sind, die Sicherheits- und/oder Compliancefunktionen ausführen, müssen über bestimmte E5-Lizenzen verfügen, um diese Funktionalität nutzen und Seeding-Kapazität erhalten zu können. Die Seeding-Kapazität ist pro Benutzer und wird pro Monat berechnet und auf Mandantenebene aggregiert. Für die Nutzung, die über die Seeding-Kapazität hinausgeht, werden App-Besitzern die API-Nutzung in Rechnung gestellt. Modell A kann nur auf Nachrichten von Benutzern mit einer zugewiesenen E5-Lizenz zugreifen.

### <a name="general-usagemodel-b-scenarios"></a>Allgemeine Verwendungs-/Modell-B-Szenarien

Für alle Nicht-S+C-bezogenen Szenarien sind keine Lizenzanforderungen oder Seedingkapazität verfügbar. Wenn Verbrauchszähler verfügbar werden, werden App-Besitzer für alle monatlichen API-Aufrufe in Rechnung gestellt.

### <a name="evaluation-mode-default"></a>Evaluierungsmodus (Standard)

Keine Modelldeklaration ermöglicht den Zugriff auf APIs mit eingeschränkter Nutzung pro anfordernden Anwendung zu Auswertungszwecken.

## <a name="json-representation"></a>JSON-Darstellung

Das folgende Beispiel ist eine JSON-Darstellung der Ressource:

Namespace: microsoft.graph

```JSON
{
"id": "string (identifier)",
"replyToId": "string (identifier)",
"from": {"@odata.type": "microsoft.graph.identitySet"},
"etag": "string",
"messageType": "string",
"createdDateTime": "string (timestamp)",
"lastModifiedDateTime": "string (timestamp)",
"deletedDateTime": "string (timestamp)",
"subject": "string",
"from": {
                "application": null,
                "device": null,
                "conversation": null,
                "user": {

                    "id": \[{"@odata.type": "microsoft.graph.user"}\],
                    "displayName": "User Name",

                    "userIdentityType": "aadUser"                }
            },
"body": {"@odata.type": "microsoft.graph.itemBody"},
"summary": "string",

"chatId": \[{"@odata.type": "microsoft.graph.chat"}\]

"attachments": \[{"@odata.type": "microsoft.graph.chatMessageAttachment"}\],
"mentions": \[{"@odata.type": "microsoft.graph.chatMessageMention"}\],
"importance": "string",
"locale": "string",
}
```

> [!NOTE]
> Weitere Informationen zur chatMessage-Ressource finden Sie im Artikel zum [ChatMessage-Ressourcentyp](/graph/api/resources/chatmessage) .
