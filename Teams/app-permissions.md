---
title: Berechtigungen für Microsoft Teams-Apps und Überlegungen dazu
author: rmw2890
ms.author: rowille
manager: serdars
ms.date: 06/27/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
search.appverid: MET150
ms.reviewer: rowille
description: Hier erfahren Sie, welche Daten und Berechtigungen Apps von Ihrer Organisation anfordern.
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5d7548d4d162310bc239c752e2bce38e725008f9
ms.sourcegitcommit: 8e2fa7b744d0a174b699ae7298d4688b971eeff3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/07/2020
ms.locfileid: "41845226"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a>Berechtigungen für Microsoft Teams-Apps und Überlegungen dazu

Microsoft Teams-Apps stellen eine Möglichkeit dar, eine oder mehrere Funktionen in einem _App-Paket_ zu aggregieren, das installiert, aktualisiert und deinstalliert werden kann. Zu diesen Funktionen gehören folgende:

- Bots
- Messagingerweiterungen
- Registerkarten
- Connectors

Apps benötigen Einwilligungen der Benutzer und werden im Hinblick auf Richtlinien von der IT verwaltet. Die Berechtigungen und das Risikoprofil einer App werden jedoch größtenteils durch die Berechtigungen und Risikoprofile der Funktionen definiert, die in der App enthalten sind. Daher konzentriert sich dieser Artikel auf Berechtigungen und Überlegungen auf Funktionsebene.

Die unten in Großbuchstaben aufgeführten Berechtigungen, zum Beispiel RECEIVE_MESSAGE und REPLYTO_MESSAGE, werden in der [Entwicklerdokumentation für Microsoft Teams](https://aka.ms/teamsdevdocs) oder den [Berechtigungen für Microsoft Graph](https://developer.microsoft.com/graph/docs/concepts/permissions_reference) nicht erwähnt. Es handelt sich einfach um eine nur in diesem Artikel verwendete beschreibende Kurzschreibweise.


|    |     |
|-----------|------------|
| ![Ein Symbol, das einen Entscheidungspunkt darstellt](media/audio_conferencing_image7.png) <br/>Entscheidungspunkt|<ul><li>Verwenden Sie die folgenden Tabellen als Leitfaden, um zu verstehen, welche Berechtigungen die apps, die Sie untersuchen, anfordern.</li></ul> |
| ![Ein Symbol, das den nächsten Schritt darstellt](media/audio_conferencing_image9.png)<br/>Nächster Schritt|<ul><li>Untersuchen Sie die APP oder den Dienst selbst, um zu entscheiden, ob Sie in Ihrer Organisation Zugriff darauf gewähren möchten. So können Bots beispielsweise Nachrichten von Benutzern senden und empfangen und – mit Ausnahme der Enterprise-Unternehmens-Bots – außerhalb der Compliance-Grenze liegen. Daher erfordert jede APP, die einen bot enthält, diese Berechtigungen und weist das Risikoprofil mindestens auf. </li></ul>|

## <a name="global-app-permissions-and-considerations"></a>Globale App-Berechtigungen und-Überlegungen

### <a name="required-permissions"></a>Erforderliche Berechtigungen

Keine

### <a name="optional-permissions"></a>Optionale Berechtigungen

Keine

### <a name="considerations"></a>Überlegungen

Eine APP muss offen legen, welche Daten Sie verwendet und wofür die Daten in den Nutzungsbedingungen und den Datenschutzrichtlinien Links verwendet werden.</td>

## <a name="bots-and-messaging-extensions"></a>Bots und Messaging-Erweiterungen

### <a name="required-permissions"></a>Erforderliche Berechtigungen

- RECEIVE_MESSAGE, REPLYTO_MESSAGE: Der Bot kann Nachrichten von Benutzern empfangen und auf diese antworten.<sup>1</sup>

- POST_MESSAGE_USER: Nachdem ein Nutzer eine Nachricht an einen bot gesendet hat, kann der bot dem Nutzer direkte Nachrichten (auch als *proaktive Nachrichten* bezeichnet) senden.

- GET_CHANNEL_LIST: Bots, die zu Teams hinzugefügt wurden, können eine Liste der Namen und IDs der Kanäle in einem Team abrufen.

### <a name="optional-permissions"></a>Optionale Berechtigungen

- Identität. Wenn Sie in einem Kanal verwendet wird, können die APP-Bots auf grundlegende Identitätsinformationen von Teammitgliedern (Vorname, Nachname, Benutzerprinzipalname [UPN], e-Mail-Adresse) zugreifen. Wenn Sie in einem persönlichen oder Gruppen-Chat verwendet wird, kann der bot für diese Benutzer auf dieselben Informationen zugreifen.

- POST_MESSAGE_TEAM. Ermöglicht es den Bots einer APP, jederzeit direkte (proaktive) Nachrichten an ein beliebiges Teammitglied zu senden, auch wenn der Benutzer noch nie zuvor mit dem bot gesprochen hat.

- Die folgenden sind keine expliziten Berechtigungen, sondern werden von RECEIVE_MESSAGE und REPLYTO_MESSAGE und den Bereichen impliziert, in denen die Bots verwendet werden können, die im Manifest deklariert werden:
 
    - RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL
    - RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT
    - RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM

- SEND_FILES, RECEIVE_FILES. <sup>2</sup> steuert, ob ein bot Dateien im persönlichen Chat senden und empfangen kann (noch nicht für Gruppen-Chats oder Kanäle unterstützt).

### <a name="considerations"></a>Überlegungen

- Bots haben nur Zugriff auf Teams, denen Sie hinzugefügt wurden, oder auf Benutzer, die Sie installiert haben.

- Bots empfangen nur Nachrichten, in denen Sie von den Benutzern ausdrücklich erwähnt werden. Diese Daten verlassen das Unternehmensnetzwerk.

- Bots können nur auf Unterhaltungen Antworten, in denen Sie erwähnt werden.

- Nachdem ein Nutzer sich mit einem bot unterhalten hat, kann er, wenn der bot die ID des Nutzers speichert, diesen Nutzer jederzeit direkt Nachrichten senden.

- Es ist theoretisch möglich, dass bot-Nachrichten Links zu Phishing-oder Malware-Websites enthalten, aber Bots können vom Benutzer, dem mandantenadministrator oder Global von Microsoft blockiert werden.

- Ein Bot kann sehr einfache Identitätsinformationen für die Teammitglieder, denen die app hinzugefügt wurde, oder für einzelne Benutzer in persönlichen oder Gruppen-Chats abrufen (und möglicherweise speichern). Wenn Sie weitere Informationen zu diesen Benutzern erhalten möchten, muss der bot die Anmeldung bei Azure Active Directory (Azure AD) anfordern.

- Bots können die Liste der Kanäle in einem Team abrufen (und möglicherweise speichern). Diese Daten verlassen das Unternehmensnetzwerk.

- Wenn eine Datei an einen bot gesendet wird, verlässt die Datei das Unternehmensnetzwerk. Für das Senden und empfangen von Dateien ist die Benutzergenehmigung für jede Datei erforderlich. 

- Standardmäßig sind Bots nicht in der Lage, im Namen des Benutzers zu agieren, aber Bots können Nutzer bitten, sich anzumelden. Sobald sich der Benutzer anmeldet, verfügt der bot über ein Zugriffstoken, mit dem er zusätzliche Aufgaben ausführen kann. Genau das, was diese zusätzlichen Dinge sind, hängt vom bot ab und von der Stelle, an der sich der Benutzer anmeldet: https://apps.dev.microsoft.com/ ein Bot ist eine Azure AD-App, die bei registriert ist und über einen eigenen Satz von Berechtigungen verfügen kann.

- Bots werden benachrichtigt, wenn Benutzer zu einem Team hinzugefügt oder daraus gelöscht werden.

- Für Bots werden die IP-Adressen der Benutzer oder andere Verweisinformationen nicht angezeigt. Alle Informationen stammen von Microsoft. (Es gibt eine Ausnahme: Wenn ein bot seine eigene Anmelde Erfahrung implementiert, werden die IP-Adressen und Verweisinformationen der Benutzer auf der Anmelde-UI angezeigt.)

- Messaging-Erweiterungen hingegen sehen die IP-Adressen und Verweisinformationen von Benutzern.

- App-Richtlinien (und unser AppSource-Überprüfungsprozess) erfordern Diskretion beim Posten persönlicher Chatnachrichten an Benutzer (über die POST_MESSAGE_TEAM-Berechtigung) für gültige Zwecke. Im Fall von Missbrauch können Benutzer den bot blockieren, mandantenadministratoren können die APP blockieren, und Microsoft kann Bots bei Bedarf zentral blockieren.

<sup>1</sup> einige Bots senden nur Nachrichten (POST_MESSAGE_USER). Sie werden als "Benachrichtigungs-only"-Bots bezeichnet, aber der Ausdruck bezieht sich nicht auf das, was ein bot erlaubt oder nicht erlaubt, was bedeutet, dass der bot keine Konversations Erfahrung machen möchte. Teams verwendet dieses Feld, um Funktionen in der UI zu deaktivieren, die normalerweise aktiviert werden. der Bot ist nicht eingeschränkt in dem, was er zu tun hat, im Vergleich zu Bots, die eine Konversations Erfahrung machen.

<sup>2</sup> unterliegt der supportsFiles-booleschen Eigenschaft für das bot-Objekt in der Manifest. JSON-Datei für die app.

> [!NOTE]
> Wenn ein bot eine eigene Anmeldung hat, gibt es eine zweite – anders – Zustimmungs Erfahrung, wenn sich der Benutzer zum ersten Mal anmeldet.
>
>Derzeit sind die Azure AD-Berechtigungen, die einer der Funktionen in einer Teams-app (bot-, Tab-, Connector-oder Messaging-Erweiterung) zugeordnet sind, vollständig von den hier aufgelisteten Teams-Berechtigungen getrennt.

## <a name="tabs"></a>Registerkarten

Eine Registerkarte ist eine Website, die innerhalb von Teams ausgeführt wird.

### <a name="required-permissions"></a>Erforderliche Berechtigungen

SEND_AND_RECEIVE_WEB_DATA

### <a name="optional-permissions"></a>Optionale Berechtigungen

Keine (derzeit)

### <a name="considerations"></a>Überlegungen

- Das Risikoprofil einer Registerkarte ist nahezu identisch mit der Website, die auf einer Browserregister Karte ausgeführt wird. 

- Eine Registerkarte ruft auch den Kontext ab, in dem Sie ausgeführt wird, einschließlich des Anmeldenamens und des UPN des aktuellen Benutzers, der Azure AD-Objekt-ID für den aktuellen Benutzer, der ID der Office 365-Gruppe, in der Sie sich befindet (sofern es sich um ein Team handelt), der Mandanten-ID. und das aktuelle Gebietsschema des Benutzers. Damit diese IDs jedoch den Informationen eines Benutzers zugeordnet werden können, muss sich der Benutzer bei Azure AD anmelden.

## <a name="connectors"></a>Verbinder

Ein Connector Bucht Nachrichten in einem Kanal, wenn Ereignisse in einem externen System auftreten.

### <a name="required-permissions"></a>Erforderliche Berechtigungen

POST_MESSAGE_CHANNEL

### <a name="optional-permissions"></a>Optionale Berechtigungen

REPLYTO_CONNECTOR_MESSAGE. Bestimmte Connectors unterstützen umsetzbare Nachrichten, mit denen Benutzer gezielte Antworten auf die Connector-Nachricht senden können, beispielsweisedurch Hinzufügen einer Antwort auf ein GitHub-Problem oder durch Hinzufügen eines Datums zu einer Trello-Karte.

### <a name="considerations"></a>Überlegungen

- Das System, in dem Connector-Nachrichten gepostet werden, weiß nicht, wer die Nachricht sendet oder wer die Nachrichten empfängt: Es werden keine Informationen über den Empfänger veröffentlicht. (Microsoft ist der tatsächliche Empfänger, nicht der Mandant; Microsoft führt den eigentlichen Beitrag für den Kanal aus.)

- Keine Daten verlassen das Unternehmensnetzwerk, wenn Connector-Nachrichten in einem Kanal bereitgestellt werden.

- Connectors, die umsetzbare Nachrichten (REPLYTO_CONNECTOR_MESSAGE Berechtigung) unterstützen, sehen auch keine IP-Adressen-und Verweisinformationen; Diese Informationen werden an Microsoft gesendet und dann an HTTP-Endpunkte weitergeleitet, die zuvor bei Microsoft im Connectors-Portal registriert wurden.

- Jedes Mal, wenn ein Connector für einen Kanal konfiguriert ist, wird eine eindeutige URL für diese Connector-Instanz erstellt. Wenn diese Connector-Instanz gelöscht wird, kann die URL nicht mehr verwendet werden.

- Connector-Nachrichten können keine Dateianlagen enthalten.

- Die URL der Connector-Instanz sollte als geheim/vertraulich behandelt werden: jede Person, die über diese URL verfügt, kann Sie wie eine e-Mail-Adresse Posten. Daher besteht ein gewisses Risiko von Spam oder Links zu Phishing-oder Malware-Websites. In diesem Fall können Teambesitzer die Connector-Instanz löschen.

- Wenn der Dienst, der Connector-Nachrichten sendet, kompromittiert wurde und mit dem Senden von Spam/Phishing/Malware-Links beginnt, kann ein mandantenadministrator verhindern, dass neue Connector-Instanzen erstellt werden, und Microsoft kann Sie zentral blockieren.

> [!NOTE]
> Es ist derzeit nicht möglich zu wissen, welche Connectors umsetzbare Nachrichten (REPLYTO_CONNECTOR_MESSAGE Berechtigung) unterstützen.

## <a name="outgoing-webhooks"></a>Ausgehende webhooks

*Ausgehende webhooks* werden von Teambesitzern oder Teammitgliedern im Handumdrehen erstellt. Sie sind keine Funktionen von Teams-apps; Diese Informationen sind zur Vollständigkeit enthalten.

### <a name="required-permissions"></a>Erforderliche Berechtigungen

RECEIVE_MESSAGE, REPLYTO_MESSAGE. Kann Nachrichten von Benutzern empfangen und darauf antworten.

### <a name="optional-permissions"></a>Optionale Berechtigungen

Keine

### <a name="considerations"></a>Überlegungen

- Ausgehende webhooks ähneln Bots, haben aber weniger Privilegien. Sie müssen ausdrücklich erwähnt werden, genau wie Bots.

- Beim Registrieren eines ausgehenden webhooks wird ein geheimer Schlüssel generiert, der dem ausgehenden webhook ermöglicht, zu überprüfen, ob der Absender Microsoft Teams im Gegensatz zu einem böswilligen Angreifer ist. Dieses Geheimnis sollte geheim bleiben; Jeder Benutzer, der Zugriff darauf hat, kann die Identität von Microsoft Teams einsehen. Wenn das Geheimnis beeinträchtigt wird, kann der ausgehende webhook gelöscht und neu erstellt werden, und es wird ein neuer Schlüssel generiert.

- Obwohl es möglich ist, einen ausgehenden webhook zu erstellen, der den geheimen Schlüssel nicht überprüft, empfehlen wir dafür.

- Anders als das empfangen und beantworten von Nachrichten können ausgehende webhooks nicht viel tun: Sie können keine proaktiven Nachrichten senden, Sie können keine Dateien senden oder empfangen, Sie können nichts anderes tun, was Bots tun können, außer zu empfangen und auf Nachrichten zu antworten.
