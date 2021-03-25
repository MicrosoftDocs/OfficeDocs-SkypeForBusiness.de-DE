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
description: Administratoren können erfahren, welche Daten und Berechtigungen Microsoft Teams-Apps von ihrer Organisation anfordern.
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ae050080814afe12ce2ba791c6b68058d5e4bc58
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120857"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a>Berechtigungen für Microsoft Teams-Apps und Überlegungen dazu

Microsoft Teams-Apps sind eine Möglichkeit, eine  oder mehrere Funktionen in einem App-Paket zu aggregieren, das installiert, aktualisiert und deinstalliert werden kann. Zu den Funktionen gehören:

- Bots
- Messagingerweiterungen
- Registerkarten
- Connectors

Apps werden von Benutzern unterstützt und von der IT aus richtlinienpolitischer Sicht verwaltet. Die Berechtigungen und das Risikoprofil einer App werden jedoch in den meisten Prozenten durch die Berechtigungen und Risikoprofile der funktionen definiert, die die App enthält. Daher konzentriert sich dieser Artikel auf Berechtigungen und Überlegungen auf Der Fähigkeitsebene.

Die unten in Großbuchstaben aufgeführten Berechtigungen, z. B. RECEIVE_MESSAGE und REPLYTO_MESSAGE, werden nirgendwo in der [Microsoft Teams-Entwicklerdokumentation](/microsoftteams/platform/overview) oder in den Berechtigungen für Microsoft Graph [angezeigt.](/graph/permissions-reference) Sie sind einfach eine beschreibende Kurzhand für den Zweck dieses Artikels.


| Titel   | Beschreibung    |
|-----------|------------|
| ![Symbol, das einen Entscheidungspunkt darstellt](media/audio_conferencing_image7.png) <br/>Entscheidungspunkt|<ul><li>Verwenden Sie die nachstehenden Tabellen als Leitfaden, um zu verstehen, welche Berechtigungen die von Ihnen untersuchten Apps anfordern.</li></ul> |
| ![Ein Symbol, das den nächsten Schritt darstellt](media/audio_conferencing_image9.png)<br/>Nächster Schritt|<ul><li>Recherchieren Sie die App oder den Dienst selbst, um zu entscheiden, ob Sie den Zugriff darauf innerhalb Ihrer Organisation zulassen möchten. Bots senden und empfangen beispielsweise Nachrichten von Benutzern und befinden sich – mit Ausnahme von benutzerdefinierten Enterprise-Bots – außerhalb der Compliancegrenze. Daher erfordert jede App, die einen Bot enthält, diese Berechtigungen und verfügt mindestens über dieses Risikoprofil. </li></ul>|

Siehe auch [Anfordern von Geräteberechtigungen für Ihre Registerkarte Microsoft Teams.](/microsoftteams/platform/concepts/device-capabilities/native-device-permissions)

## <a name="global-app-permissions-and-considerations"></a>Berechtigungen und Überlegungen für globale Apps

### <a name="required-permissions"></a>Erforderliche Berechtigungen

Keine

### <a name="optional-permissions"></a>Optionale Berechtigungen

Keine

### <a name="considerations"></a>Überlegungen

- Eine App muss offenlegen, welche Daten sie verwendet und wofür die Daten in ihren Nutzungsbedingungen und Denkrichtlinienlinks verwendet werden.

- [Die ressourcenspezifische Zustimmung](resource-specific-consent.md) bietet eine Reihe von Berechtigungen, die Apps anfordern können, die auf dem Installationsbildschirm der App angezeigt werden. Weitere Informationen zu ressourcenspezifischen Zustimmungsberechtigungen finden Sie unter [Referenz zu Diagrammberechtigungen.](/graph/permissions-reference#teams-resource-specific-consent-permissions)

- Apps benötigen möglicherweise auch andere Berechtigungen als ressourcenspezifische Zustimmungsberechtigungen. Nach der Installation einer App kann die App graph-Berechtigungen über eine Zustimmungsaufforderung anfordern. Weitere Informationen finden Sie unter [Grundlegendes zu den Zustimmungserfahrungen für Azure AD-Anwendungen.](/azure/active-directory/develop/application-consent-experience) Sie können im Azure-Portal API-Berechtigungen und -Zustimmung konfigurieren. Weitere Informationen finden Sie unter [Azure Active Directory-Zustimmungsframework](/azure/active-directory/develop/consent-framework).

## <a name="bots-and-messaging-extensions"></a>Bots und Messagingerweiterungen

### <a name="required-permissions"></a>Erforderliche Berechtigungen

- RECEIVE_MESSAGE, REPLYTO_MESSAGE. Der Bot kann Nachrichten von Benutzern empfangen und darauf antworten. <sup>1</sup>

- POST_MESSAGE_USER. Nachdem ein Benutzer eine Nachricht an einen Bot gesendet hat, kann  der Bot dem Benutzer jederzeit direkte Nachrichten senden (auch als proaktive Nachrichten bezeichnet).

- GET_CHANNEL_LIST. Bots, die zu Teams hinzugefügt werden, können eine Liste der Namen und IDs der Kanäle in einem Team erhalten.

### <a name="optional-permissions"></a>Optionale Berechtigungen

- IDENTITY. Wenn sie in einem Kanal verwendet wird, können die Bots der App auf grundlegende Identitätsinformationen von Teammitgliedern zugreifen (Vorname, Nachname, Benutzername [UPN], E-Mail-Adresse); Wenn er in einem persönlichen Chat oder in einem Gruppenchat verwendet wird, kann der Bot auf dieselben Informationen für diese Benutzer zugreifen.

- POST_MESSAGE_TEAM. Ermöglicht es den Bots einer App, jederzeit direkte (proaktive) Nachrichten an jedes Teammitglied zu senden, auch wenn der Benutzer noch nie mit dem Bot gesprochen hat.

- Die folgenden Sind keine expliziten Berechtigungen, sondern werden durch RECEIVE_MESSAGE und REPLYTO_MESSAGE und die Bereiche impliziert, in denen die Bots verwendet werden können, die im Manifest deklariert werden:
 
    - RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL
    - RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT
    - RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM

- SEND_FILES, RECEIVE_FILES. <sup>2</sup> Steuert, ob ein Bot Dateien in persönlichen Chats senden und empfangen kann (für Gruppenchats oder Kanäle noch nicht unterstützt).

### <a name="considerations"></a>Überlegungen

- Bots haben nur Zugriff auf Teams, denen sie hinzugefügt wurden, oder auf Benutzer, die sie installiert haben.

- Bots empfangen nur Nachrichten, in denen sie explizit von Benutzern erwähnt werden. Diese Daten verlässt das Unternehmensnetzwerk.

- Bots können nur auf Unterhaltungen antworten, in denen sie erwähnt werden.

- Nachdem sich ein Benutzer mit einem Bot unterhalten hat, kann er, wenn der Bot die ID des Benutzers speichert, jederzeit direkte Nachrichten an den Benutzer senden.

- Botnachrichten können theoretisch Links zu Phishing- oder Schadsoftwarewebsites enthalten, Bots können jedoch vom Benutzer, dem Mandantenadministrator oder global von Microsoft blockiert werden.

- Ein Bot kann sehr grundlegende Identitätsinformationen für die Teammitglieder, zu der die App hinzugefügt wurde, oder für einzelne Benutzer in persönlichen Chats oder Gruppenchats abrufen (und speichern). Um weitere Informationen zu diesen Benutzern zu erhalten, muss der Bot diese zur Anmeldung bei Azure Active Directory (Azure AD) benötigen.

- Bots können die Liste der Kanäle in einem Team abrufen (und möglicherweise speichern). Diese Daten verlässt das Unternehmensnetzwerk.

- Wenn eine Datei an einen Bot gesendet wird, verlässt die Datei das Unternehmensnetzwerk. Das Senden und Empfangen von Dateien erfordert die Zustimmung des Benutzers für jede Datei. 

- Standardmäßig können Bots nicht im Auftrag des Benutzers handeln, bots können benutzer jedoch bitten, sich zu anmelden. Sobald sich der Benutzer meldet, hat der Bot ein Zugriffstoken, mit dem er zusätzliche Dinge tun kann. Was genau diese zusätzlichen Dinge sind, hängt vom Bot und davon ab, wo sich der Benutzer angemeldet hat: Ein Bot ist eine Azure AD-App, die bei registriert ist und über eigene Berechtigungen https://apps.dev.microsoft.com/ verfügen kann.

- Bots werden informiert, wenn Benutzer zu einem Team hinzugefügt oder aus diesem gelöscht werden.

- Bots sehen keine IP-Adressen oder andere Verweisinformationen der Benutzer. Alle Informationen stammen von Microsoft. (Es gibt eine Ausnahme: Wenn ein Bot eine eigene Anmeldeerfahrung implementiert, werden auf der Anmelde-UI die IP-Adressen und Verweisinformationen der Benutzer angezeigt.)

- Nachrichtenerweiterungen sehen dagegen die IP-Adressen und Verweisinformationen der Benutzer.

- App-Richtlinien (und unser AppSource-Überprüfungsprozess) erfordern einen Ermessensspielraum beim Posten persönlicher Chatnachrichten für Benutzer (über die Berechtigung POST_MESSAGE_TEAM) zu gültigen Zwecken. Bei Missbrauch können Benutzer den Bot blockieren, Mandantenadministratoren können die App blockieren, und Microsoft kann Bots bei Bedarf zentral blockieren.

<sup>1</sup> Einige Bots senden nur Nachrichten (POST_MESSAGE_USER). Sie werden als "Benachrichtigungs-only"-Bots bezeichnet, aber der Ausdruck bezieht sich nicht auf die zulässigen oder nicht zulässigen Bots. Dies bedeutet, dass der Bot keine Unterhaltungserfahrung verfügbar machen möchte. Teams verwendet dieses Feld, um Funktionen auf der Benutzeroberfläche zu deaktivieren, die normalerweise aktiviert würden. Der Bot ist im Vergleich zu Bots, die eine Unterhaltungserfahrung verfügbar machen, nicht eingeschränkt.

<sup>2</sup> Unterliegt der booleschen SupportsFiles-Eigenschaft für das Bot-Objekt im manifest.jsfür die App.

> [!NOTE]
> Wenn ein Bot über eine eigene Anmeldung verfügt, gibt es eine zweite – unterschiedliche – Zustimmungserfahrung, wenn sich der Benutzer zum ersten Mal anmeldet.
>
>Derzeit sind die Azure AD-Berechtigungen, die mit einer der Funktionen in einer Teams-App (Bot, Registerkarte, Connector oder Messagingerweiterung) verknüpft sind, vollständig von den hier aufgeführten Teams-Berechtigungen getrennt.

## <a name="tabs"></a>Registerkarten

Eine Registerkarte ist eine Website, die in Teams ausgeführt wird.

### <a name="required-permissions"></a>Erforderliche Berechtigungen

SEND_AND_RECEIVE_WEB_DATA

### <a name="optional-permissions"></a>Optionale Berechtigungen

Keine (aktuell)

### <a name="considerations"></a>Überlegungen

- Das Risikoprofil für eine Registerkarte ist fast identisch mit der Website, die auf einer Browserregisterkarte ausgeführt wird. 

- Eine Registerkarte ruft auch den Kontext ab, in dem sie ausgeführt wird, einschließlich des Anmeldenamens und des UPNs des aktuellen Benutzers, der Azure AD-Objekt-ID für den aktuellen Benutzer, der ID der Microsoft 365-Gruppe, in der sie sich befindet (wenn es sich um ein Team, die Mandanten-ID und das aktuelle Locale des Benutzers) befindet. Um diese IDs jedoch den Informationen eines Benutzers zu zuordnungen, müsste sich der Benutzer auf der Registerkarte bei Azure AD anmelden.

## <a name="connectors"></a>Connectors

Ein Verbinder postet Nachrichten an einen Kanal, wenn Ereignisse in einem externen System auftreten.

### <a name="required-permissions"></a>Erforderliche Berechtigungen

POST_MESSAGE_CHANNEL

### <a name="optional-permissions"></a>Optionale Berechtigungen

REPLYTO_CONNECTOR_MESSAGE. Bestimmte Connectors unterstützen aktionsfähige Nachrichten, die Benutzern das Posten gezielter Antworten auf die Connectornachricht ermöglichen, z. B. durch Hinzufügen einer Antwort auf ein GitHub-Problem oder Hinzufügen eines Datums zu einer Trello-Karte.

### <a name="considerations"></a>Überlegungen

- Das System, das Verbindernachrichten postet, weiß nicht, an wen es beiträget oder wer die Nachrichten empfängt: Es werden keine Informationen über den Empfänger offengelegt. (Microsoft ist der eigentliche Empfänger und nicht der Mandant; Microsoft führt den eigentlichen Beitrag im Kanal aus.)

- Wenn Verbindernachrichten in einem Kanal gepostet werden, werden keine Daten aus dem Unternehmensnetzwerk gesendet.

- Connectors, die aktionsfähige Nachrichten (REPLYTO_CONNECTOR_MESSAGE) unterstützen, sehen auch keine #A0 und Verweisinformationen. Diese Informationen werden an Microsoft gesendet und dann an HTTP-Endpunkte geleitet, die zuvor im Connectorsportal bei Microsoft registriert waren.

- Jedes Mal, wenn ein Connector für einen Kanal konfiguriert wird, wird eine eindeutige URL für diese Connectorinstanz erstellt. Wenn diese Connectorinstanz gelöscht wird, kann die URL nicht mehr verwendet werden.

- Connectornachrichten können keine Dateianlagen enthalten.

- Die URL der Connectorinstanz sollte als geheim/vertraulich behandelt werden: Jeder, der über diese URL verfügt, kann sie posten, z. B. eine E-Mail-Adresse. Daher besteht ein gewisses Risiko von Spam oder Links zu Phishing- oder Schadsoftwarewebsites. In diesem Fall können Teambesitzer die Connectorinstanz löschen.

- Wenn der Dienst, der Connectornachrichten sendet, gefährdet werden und mit dem Senden von Spam-/Phishing-/Schadsoftwarelinks beginnen soll, kann ein Mandantenadministrator verhindern, dass neue Connectorinstanzen erstellt werden, und Microsoft kann sie zentral blockieren.

> [!NOTE]
> Es ist derzeit nicht möglich zu wissen, welche Verbinder aktionsfähige Nachrichten (REPLYTO_CONNECTOR_MESSAGE unterstützen).

## <a name="outgoing-webhooks"></a>Ausgehende Webhooks

*Ausgehende Webhooks* werden von Teambesitzern oder Teammitgliedern im Flug erstellt. Sie sind keine Funktionen von #A0 Diese Informationen sind aus Gründen der Vollständigkeit enthalten.

### <a name="required-permissions"></a>Erforderliche Berechtigungen

RECEIVE_MESSAGE, REPLYTO_MESSAGE. Kann Nachrichten von Benutzern empfangen und darauf antworten.

### <a name="optional-permissions"></a>Optionale Berechtigungen

Keine

### <a name="considerations"></a>Überlegungen

- Ausgehende Webhooks ähneln Bots, verfügen aber über weniger Berechtigungen. Sie müssen explizit erwähnt werden, genau wie Bots.

- Wenn ein ausgehender Webhook registriert ist, wird ein Geheimtipp generiert, mit dem der ausgehende Webhook überprüfen kann, ob es sich bei dem Absender um Microsoft Teams im Gegensatz zu einem böswilligen Angreifer handelt. Dieses Geheimnis sollte geheim bleiben. Jeder, der Darauf zugreifen kann, kann microsoft Teams als Identitätswechsel verwenden. Wenn das Geheimnis gefährdet ist, kann der ausgehende Webhook gelöscht und neu erstellt werden, und ein neuer Geheimtipp wird generiert.

- Obwohl es möglich ist, einen ausgehenden Webhook zu erstellen, der das Geheimnis nicht überprüft, empfehlen wir dagegen.

- Außer dem Empfangen und Beantworten von Nachrichten können ausgehende Webhooks nicht viel tun: Sie können keine Nachrichten proaktiv senden, sie können keine Dateien senden oder empfangen, sie können nichts anderes tun, als Nachrichten zu empfangen und zu beantworten.