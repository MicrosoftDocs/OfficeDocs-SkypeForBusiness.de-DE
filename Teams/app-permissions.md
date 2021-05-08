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
description: Der Administrator kann erfahren, welche Daten und Berechtigungen Microsoft Teams Apps von ihrer Organisation anfordern.
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

Microsoft Teams-Apps bieten eine Möglichkeit, eine oder  mehrere Funktionen in einem App-Paket zusammen zu aggregieren, das installiert, aktualisiert und deinstalliert werden kann. Zu den Funktionen gehören:

- Bots
- Messaging-Erweiterungen
- Registerkarten
- Verbinder

Apps werden von Benutzern aus Richtlinienperspektive unterstützt und von der IT verwaltet. Die Berechtigungen und Das Risikoprofil einer App werden jedoch in den meisten Meisten durch die Berechtigungen und Risikoprofile der Funktionen definiert, die die App enthält. Daher konzentriert sich dieser Artikel auf Berechtigungen und Überlegungen auf der Funktionsebene.

Die unten in Großbuchstaben aufgeführten Berechtigungen, z. B. RECEIVE_MESSAGE und REPLYTO_MESSAGE, werden in der Microsoft Teams-Entwicklerdokumentation oder in den Berechtigungen für [Microsoft Graph nicht angezeigt.](/graph/permissions-reference) [](/microsoftteams/platform/overview) Sie sind einfach eine beschreibende Kurzhand für den Zweck dieses Artikels.


| Titel   | Beschreibung    |
|-----------|------------|
| ![Symbol, das einen Entscheidungspunkt darstellt](media/audio_conferencing_image7.png) <br/>Entscheidungspunkt|<ul><li>Verwenden Sie die nachstehenden Tabellen als Leitfaden, um zu verstehen, welche Berechtigungen die von Ihnen untersuchten Apps anfordern.</li></ul> |
| ![Ein Symbol, das den nächsten Schritt darstellt](media/audio_conferencing_image9.png)<br/>Nächster Schritt|<ul><li>Recherchieren Sie über die App oder den Dienst selbst, um zu entscheiden, ob Sie innerhalb Ihrer Organisation zugriffen möchten. Bots senden und empfangen beispielsweise Nachrichten von Benutzern und befinden sich – mit Ausnahme benutzerdefinierter Enterprise-Bots – außerhalb der Compliancegrenze. Daher erfordert jede App, die einen Bot enthält, diese Berechtigungen und mindestens dieses Risikoprofil. </li></ul>|

Siehe auch [Anfordern von Geräteberechtigungen für Microsoft Teams Registerkarte](/microsoftteams/platform/concepts/device-capabilities/native-device-permissions).

## <a name="global-app-permissions-and-considerations"></a>Globale App-Berechtigungen und Überlegungen

### <a name="required-permissions"></a>Erforderliche Berechtigungen

Keine

### <a name="optional-permissions"></a>Optionale Berechtigungen

Keine

### <a name="considerations"></a>Überlegungen

- Eine App muss offenlegen, welche Daten sie verwendet und wofür sie in ihren Nutzungsbedingungen und Links zu den Datenschutzrichtlinien verwendet wird.

- [Ressourcenspezifische Zustimmung bietet](resource-specific-consent.md) eine Reihe von Berechtigungen, die Apps anfordern können, die auf dem Installationsbildschirm der App angezeigt werden. Weitere Informationen zu ressourcenspezifischen Zustimmungsberechtigungen finden Sie unter Graph [zu Berechtigungen.](/graph/permissions-reference#teams-resource-specific-consent-permissions)

- Apps benötigen möglicherweise auch andere Berechtigungen als ressourcenspezifische Zustimmungsberechtigungen. Nach der Installation einer App kann die App die Graph einer Zustimmungsaufforderung anfordern. Weitere Informationen finden Sie unter Grundlegendes zu [Azure AD-Anwendungs-Zustimmungserfahrungen.](/azure/active-directory/develop/application-consent-experience) Sie können IM Azure-Portal API-Berechtigungen und -Zustimmung konfigurieren. Weitere Informationen finden Sie unter [Azure Active Directory-Framework.](/azure/active-directory/develop/consent-framework)

## <a name="bots-and-messaging-extensions"></a>Bots und Messaging-Erweiterungen

### <a name="required-permissions"></a>Erforderliche Berechtigungen

- RECEIVE_MESSAGE, REPLYTO_MESSAGE. Der Bot kann Nachrichten von Benutzern empfangen und auf sie antworten. <sup>1</sup>

- POST_MESSAGE_USER. Nachdem ein Benutzer eine Nachricht an einen Bot gesendet hat, kann  der Bot dem Benutzer Direktnachrichten senden (auch als proaktive Nachrichten bezeichnet).

- GET_CHANNEL_LIST. Bots, die zu Teams hinzugefügt wurden, können eine Liste mit Namen und IDs der Kanäle in einem Team erhalten.

### <a name="optional-permissions"></a>Optionale Berechtigungen

- IDENTITY. Wenn sie in einem Kanal verwendet wird, können die Bots der App auf grundlegende Identitätsinformationen der Teammitglieder zugreifen (Vorname, Nachname, Benutzerprinzipalname [UPN], E-Mail-Adresse); Wenn er in einem persönlichen Chat oder gruppenchat verwendet wird, kann der Bot auf dieselben Informationen für diese Benutzer zugreifen.

- POST_MESSAGE_TEAM. Ermöglicht es den Bots einer App, jederzeit direkte (proaktive) Nachrichten an jedes Teammitglied zu senden, auch wenn der Benutzer noch nie mit dem Bot gesprochen hat.

- Die folgenden sind keine expliziten Berechtigungen, sondern werden durch RECEIVE_MESSAGE und REPLYTO_MESSAGE und die Bereiche impliziert, in denen die Bots verwendet werden können, die im Manifest deklariert werden:
 
    - RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL
    - RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT
    - RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM

- SEND_FILES, RECEIVE_FILES. <sup>2</sup> Steuert, ob ein Bot Dateien in persönlichen Chats senden und empfangen kann (wird für Gruppenchats oder Kanäle noch nicht unterstützt).

### <a name="considerations"></a>Überlegungen

- Bots haben nur Zugriff auf Teams, zu denen sie hinzugefügt wurden, oder auf Benutzer, die sie installiert haben.

- Bots empfangen nur Nachrichten, in denen sie explizit von Benutzern erwähnt werden. Diese Daten werden nicht mehr im Unternehmensnetzwerk gespeichert.

- Bots können nur auf Unterhaltungen antworten, in denen sie erwähnt werden.

- Wenn ein Benutzer sich mit einem Bot unterhalten hat und der Bot die ID des Benutzers speichert, kann er jederzeit Direktnachrichten an den Benutzer senden.

- Botnachrichten können theoretisch Links zu Phishing- oder Schadsoftwarewebsites enthalten, bots können jedoch vom Benutzer, dem Mandantenadministrator oder global von Microsoft blockiert werden.

- Ein Bot kann sehr einfache Identitätsinformationen für die Teammitglieder, zu der die App hinzugefügt wurde, oder für einzelne Benutzer in persönlichen Chats oder Gruppenchats abrufen (und möglicherweise speichern). Um weitere Informationen zu diesen Benutzern zu erhalten, muss der Bot von ihnen die Anmeldung bei Azure Active Directory (Azure AD) verlangen.

- Bots können die Liste der Kanäle in einem Team abrufen (und speichern). diese Daten das Unternehmensnetzwerk verlässt.

- Wenn eine Datei an einen Bot gesendet wird, verlässt die Datei das Unternehmensnetzwerk. Zum Senden und Empfangen von Dateien ist für jede Datei eine Benutzergenehmigung erforderlich. 

- Standardmäßig haben Bots keine Möglichkeit, im Namen des Benutzers zu handeln, aber Bots können Benutzer zur Anmeldung bitten. Sobald sich der Benutzer meldet, hat der Bot ein Zugriffstoken, mit dem er weitere Dinge tun kann. Was genau diese zusätzlichen Dinge sind, hängt vom Bot und davon ab, wo sich der Benutzer angemeldet hat: Ein Bot ist eine azure AD-App, bei der registriert ist und über einen eigenen Satz https://apps.dev.microsoft.com/ von Berechtigungen verfügen kann.

- Bots werden immer dann informiert, wenn Benutzer zu einem Team hinzugefügt oder aus einem Team gelöscht werden.

- Bots werden die IP-Adressen der Benutzer oder andere verweisende Informationen nicht sehen. Alle Informationen stammen von Microsoft. (Es gibt eine Ausnahme: Wenn ein Bot seine eigene Anmeldeoberfläche implementiert, werden auf der Anmeldebenutzeroberfläche die IP-Adressen und Verweisenden Informationen des Benutzer angezeigt.)

- Nachrichtenerweiterungen dagegen sehen die IP-Adressen und Verweisende Informationen der Benutzer.

- App-Richtlinien (und unser AppSource-Überprüfungsprozess) erfordern für das Veröffentlichen persönlicher Chatnachrichten an Benutzer (über die POST_MESSAGE_TEAM-Berechtigung) für gültige Zwecke den eigenen Ermessen. Bei Missbrauch können Benutzer den Bot blockieren, Mandantenadministratoren können die App blockieren, und Microsoft kann Bots bei Bedarf zentral blockieren.

<sup>1</sup> Einige Bots senden nur Nachrichten (POST_MESSAGE_USER). Sie werden als "nur Benachrichtigungs-Bots" bezeichnet, aber der Begriff bezieht sich nicht darauf, was ein Bot tun darf oder was nicht. Dies bedeutet, dass der Bot keine Unterhaltungserfahrung verfügbar machen möchte. Teams verwendet dieses Feld, um Funktionen auf der Benutzeroberfläche zu deaktivieren, die normalerweise aktiviert würden. Der Bot ist im Vergleich zu Bots, die eine Unterhaltungserfahrung bieten, nicht eingeschränkt, was er tun darf.

<sup>2</sup> Richtet sich nach der booleschen Eigenschaft "supportsFiles" für das Bot-Objekt in manifest.jsin der Datei der App.

> [!NOTE]
> Wenn ein Bot über eine eigene Anmeldung verfügt, gibt es eine zweite – andere – Zustimmungserfahrung, wenn sich der Benutzer zum ersten Mal anmeldet.
>
>Derzeit sind die Azure AD-Berechtigungen, die einer der Funktionen in einer Teams-App (Bot, Registerkarte, Connector oder Messagingerweiterung) zugeordnet sind, vollständig getrennt von den hier aufgeführten Teams-Berechtigungen.

## <a name="tabs"></a>Registerkarten

Eine Registerkarte ist eine Website, die innerhalb Teams.

### <a name="required-permissions"></a>Erforderliche Berechtigungen

SEND_AND_RECEIVE_WEB_DATA

### <a name="optional-permissions"></a>Optionale Berechtigungen

Keine (aktuell)

### <a name="considerations"></a>Überlegungen

- Das Risikoprofil für eine Registerkarte ist nahezu identisch mit der Website, die auf einer Browserregisterkarte ausgeführt wird. 

- Eine Registerkarte ruft auch den Kontext ab, in dem sie ausgeführt wird, einschließlich Anmeldename und UPN des aktuellen Benutzers, der Azure AD-Objekt-ID für den aktuellen Benutzer, der ID der Microsoft 365-Gruppe, in der sie sich befindet (wenn es sich um ein Team befindet), die Mandanten-ID und das aktuelle Locale des Benutzers. Um diese IDs jedoch den Informationen eines Benutzers zu zuordnungen, muss sich der Benutzer über die Registerkarte bei Azure AD anmelden.

## <a name="connectors"></a>Verbinder

Ein Connector postet Nachrichten an einen Kanal, wenn Ereignisse in einem externen System auftreten.

### <a name="required-permissions"></a>Erforderliche Berechtigungen

POST_MESSAGE_CHANNEL

### <a name="optional-permissions"></a>Optionale Berechtigungen

REPLYTO_CONNECTOR_MESSAGE. Bestimmte Connectors unterstützen umsetzbare Nachrichten, mit denen Benutzer gezielte Antworten auf die Connectornachricht posten können, z. B. durch Hinzufügen einer Antwort auf ein GitHub-Problem oder durch Hinzufügen eines Datums zu einer Trello-Karte.

### <a name="considerations"></a>Überlegungen

- Das System, das Connectornachrichten postet, weiß nicht, an wen die Nachricht gesendet wird oder wer die Nachrichten empfängt: Es werden keine Informationen über den Empfänger offengelegt. (Microsoft ist der tatsächliche Empfänger, nicht der Mandant; Microsoft führt den aktuellen Beitrag im Kanal aus.)

- Wenn Connectornachrichten in einem Kanal gepostet werden, werden keine Daten aus dem Unternehmensnetzwerk gesendet.

- Connectors, die handlungsbehbare Nachrichten unterstützen (REPLYTO_CONNECTOR_MESSAGE-Berechtigung), sehen ebenfalls keine IP-Adresse und keine verweisende Information. diese Informationen werden an Microsoft gesendet und dann an HTTP-Endpunkte geleitet, die zuvor bei Microsoft im Portal für Connectors registriert wurden.

- Jedes Mal, wenn ein Connector für einen Kanal konfiguriert wird, wird eine eindeutige URL für diese Connectorinstanz erstellt. Wenn diese Connectorinstanz gelöscht wird, kann die URL nicht mehr verwendet werden.

- Connectornachrichten können keine Dateianlagen enthalten.

- Die URL der Connectorinstanz sollte als geheim/vertraulich behandelt werden: Jeder Benutzer, der über diese URL verfügt, kann darauf Posten veröffentlichen, z. B. eine E-Mail-Adresse. Daher besteht ein gewisses Risiko von Spam oder Links zu Phishing- oder Schadsoftwarewebsites. In diesem Fall können Teambesitzer die Connectorinstanz löschen.

- Wenn der Dienst, der Connectornachrichten sendet, gefährdet werden sollte und damit beginnt, Links zu Spam/Phishing/Malware zu senden, kann ein Mandantenadministrator verhindern, dass neue Connectorinstanzen erstellt werden, und Microsoft kann sie zentral blockieren.

> [!NOTE]
> Derzeit ist es nicht möglich zu wissen, welche Connectors handlungsbehbare Nachrichten unterstützen (REPLYTO_CONNECTOR_MESSAGE Berechtigung).

## <a name="outgoing-webhooks"></a>Ausgehende Webhooks

*Ausgehende Webhooks* werden von Teambesitzern oder Teammitgliedern im Web erstellt. Es handelt sich nicht um Funktionen Teams Apps. diese Informationen sind der Vollständigkeit halber enthalten.

### <a name="required-permissions"></a>Erforderliche Berechtigungen

RECEIVE_MESSAGE, REPLYTO_MESSAGE. Kann Nachrichten von Benutzern empfangen und darauf antworten.

### <a name="optional-permissions"></a>Optionale Berechtigungen

Keine

### <a name="considerations"></a>Überlegungen

- Ausgehende Webhooks sind mit Bots vergleichbar, haben aber weniger Berechtigungen. Sie müssen explizit erwähnt werden, genau wie Bots.

- Wenn ein ausgehender Webhook registriert wird, wird ein geheimer Schlüssel generiert, mit dem der ausgehende Webhook überprüfen kann, ob der Absender Microsoft Teams im Gegensatz zu einem böswilligen Angreifer. Dieses Geheimnis sollte geheim bleiben. jeder, der Zugriff darauf hat, kann die Identität Microsoft Teams. Wenn das Geheimnis gefährdet ist, kann der ausgehende Webhook gelöscht und erneut erstellt werden, und es wird ein neuer Geheimer generiert.

- Obwohl es möglich ist, einen ausgehenden Webhook zu erstellen, der das Geheimnis nicht überprüft, empfehlen wir es dagegen.

- Abgesehen vom Empfangen und Beantworten von Nachrichten können ausgehende Webhooks nicht viel tun: Sie können nachrichten nicht proaktiv senden, sie können keine Dateien senden oder empfangen, sie können keine anderen Bots als Nachrichten empfangen und beantworten.