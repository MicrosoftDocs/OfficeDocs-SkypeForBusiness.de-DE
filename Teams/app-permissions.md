---
title: Berechtigungen für Microsoft Teams-Apps und Überlegungen dazu
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
search.appverid: MET150
ms.reviewer: rowille
description: Administratoren können ermitteln, welche Daten und Berechtigungen Microsoft Teams-Apps von ihrer Organisation anfordern.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2f4809d615d97aa46ecad3b46c2b723c33b4619e
ms.sourcegitcommit: 46dbff43eec9631863b74b2b49c9a29c6497d8e8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/20/2022
ms.locfileid: "67396866"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a>Berechtigungen für Microsoft Teams-Apps und Überlegungen dazu

Microsoft Teams-Apps stellen eine Möglichkeit dar, eine oder mehrere Funktionen in Apps zu aggregieren, die installiert, aktualisiert und deinstalliert werden können. Zu den Funktionen von Apps gehören:

* Bots
* Messaging-Erweiterungen
* Registerkarten
* Connectors

Als Administrator verwalten Sie Apps nur. Der Schwerpunkt des Artikels liegt jedoch auf Berechtigungen und Überlegungen auf Funktionsebene, da sich die Funktionen einer App auf die erforderlichen Berechtigungen und Risikoprofile der App auswirken. Für die Nutzung werden den Apps von den Benutzern Genehmigungen erteilt, während sie aus richtlinienpolitischer Sicht von IT-Fachleuten verwaltet werden.

Die unten in Großbuchstaben aufgeführten Berechtigungen (etwa `RECEIVE_MESSAGE` und `REPLYTO_MESSAGE`) dienen nur zur Veranschaulichung und Erläuterung. Diese Zeichenfolgen oder Berechtigungen sind weder in der [Microsoft Teams-Entwicklerdokumentation](/microsoftteams/platform/overview) noch in den [Berechtigungen für Microsoft Graph](/graph/permissions-reference) enthalten.

## <a name="global-app-permissions-and-considerations"></a>Berechtigungen für globale Apps und Überlegungen dazu

### <a name="required-permissions"></a>Erforderliche Berechtigungen

Keine

### <a name="optional-permissions"></a>Optionale Berechtigungen

Keine

### <a name="considerations"></a>Erwägungen

* Eine App muss in ihren Links zu Nutzungsbedingungen und Datenschutzerklärungen offenlegen, welche Daten sie verwendet und wofür diese verwendet werden.

* Über die [ressourcenspezifische Zustimmung](resource-specific-consent.md) wird einer App eine Reihe von Berechtigungen erteilt, die auf dem Installationsbildschirm der App angefordert werden. Weitere Informationen zu ressourcenspezifischen Zustimmungsberechtigungen finden Sie in der [Referenz zu Graph-Berechtigungen](/graph/permissions-reference#teams-resource-specific-consent-permissions).

* Apps benötigen u. U. auch andere Berechtigungen als ressourcenspezifische Zustimmungsberechtigungen. Nachdem eine App installiert wurde, kann sie über eine Zustimmungsaufforderung Graph-Berechtigungen anfordern. Weitere Informationen finden Sie unter [Grundlegendes zur Zustimmung für Anwendungen in Azure AD](/azure/active-directory/develop/application-consent-experience). Sie können API-Berechtigungen und Zustimmung im Azure-Portal konfigurieren. Weitere Informationen finden Sie im [Azure Active Directory-Zustimmungsframework](/azure/active-directory/develop/consent-framework).

## <a name="bots-and-messaging-extensions"></a>Bots und Messaging-Erweiterungen

### <a name="required-permissions"></a>Erforderliche Berechtigungen

* RECEIVE_MESSAGE, REPLYTO_MESSAGE: Der Bot kann Nachrichten von Benutzern empfangen und ihnen antworten. <sup>1</sup>

* POST_MESSAGE_USER: Nachdem ein Benutzer eine Nachricht an einen Bot gesendet hat, kann der Bot dem Benutzer jederzeit direkte Nachrichten senden (auch als *proaktive Nachrichten* bezeichnet).

* GET_CHANNEL_LIST: Bots, die Teams hinzugefügt wurden, können eine Liste der Namen und IDs der Kanäle in einem Team abrufen.

### <a name="optional-permissions"></a>Optionale Berechtigungen

* IDENTITY: Wenn sie in einem Kanal verwendet wird, können die Bots der App auf grundlegende Identitätsdaten von Teammitgliedern (Vorname, Nachname, Benutzerprinzipalname [UPN], E-Mail-Adresse) zugreifen. Wenn sie in einem persönlichen Chat oder Gruppenchat verwendet wird, kann der Bot auf dieselben Informationen der entsprechenden Benutzer zugreifen.

* POST_MESSAGE_TEAM: Ermöglicht es den Bots einer App, jederzeit direkte (proaktive) Nachrichten an ein Teammitglied zu senden, selbst wenn der Benutzer noch nie mit dem Bot interagiert hat.

* Die folgenden sind keine expliziten Berechtigungen, sondern sind durch RECEIVE_MESSAGE und REPLYTO_MESSAGE sowie die Bereiche impliziert, in denen die Bots verwendet werden können wie im Manifest deklariert:

  * RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL
  * RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT
  * RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM

* Die folgenden sind keine expliziten Berechtigungen, sondern sind durch RECEIVE_MESSAGE und REPLYTO_MESSAGE sowie die Bereiche impliziert, in denen die Bots verwendet werden können wie im Manifest deklariert:

  * RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL
  * RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT
  * RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM

* SEND_FILES, RECEIVE_FILES:<sup>2</sup> Steuert, ob ein Bot Dateien in persönlichen Chats senden und empfangen kann (wird für Gruppenchats oder Kanäle noch nicht unterstützt).

### <a name="considerations"></a>Erwägungen

* Bots haben nur Zugriff auf Teams, zu denen sie hinzugefügt wurden, oder auf Benutzer, bei denen sie installiert sind.

* Bots erhalten nur Nachrichten, in denen sie von Benutzern explizit erwähnt werden. Diese Daten verlassen das Unternehmensnetzwerk.

* Bots können nur auf Unterhaltungen antworten, in denen sie erwähnt werden.

* Wenn sich ein Benutzer mit einem Bot unterhält und der Bot die ID des Benutzers speichert, kann er dem Benutzer jederzeit Direktnachrichten senden.

* Theoretisch können Bot-Nachrichten Links zu Phishing- oder Schadsoftwarewebsites enthalten. Bots können jedoch vom Benutzer, dem Mandantenadministrator oder global von Microsoft blockiert werden. [Überprüfungen der App-Überprüfung und -Überprüfung](overview-of-app-validation.md) stellen sicher, dass alle unrichtigen Apps nicht im Teams Store verfügbar sind.

* Ein Bot kann grundlegende Identitätsdaten von Teammitgliedern, denen die App hinzugefügt wurde, oder einzelner Benutzer in persönlichen Chats oder Gruppenchats abrufen (und u. U. speichern). Um weitere Informationen zu diesen Benutzern zu erhalten, muss der Bot verlangen, dass sie sich bei Azure Active Directory (Azure AD) anmelden.

* Bots können die Liste der Kanäle in einem Team abrufen (und u. U. speichern). Diese Daten verlassen das Unternehmensnetzwerk.

* Standardmäßig können Bots nicht im Namen des Benutzers handeln, aber sie können Benutzer zur Anmeldung auffordern. Nachdem sich der Benutzer angemeldet hat, verfügt der Bot über ein Zugriffstoken, mit dem er zusätzliche Aktionen ausführen kann. Welche anderen Aktionen das sind, hängt vom Bot ab und davon, wo sich der Benutzer anmeldet: Ein Bot ist eine Azure AD-App, die bei https://apps.dev.microsoft.com/ registriert ist und über eigene Berechtigungen verfügen kann.

* Wenn eine Datei an einen Bot gesendet wird, verlässt sie das Unternehmensnetzwerk. Das Senden und Empfangen von Dateien erfordert eine Benutzergenehmigung für jede Datei.

* Bots werden jedes Mal informiert, wenn Benutzer zu einem Team hinzugefügt oder daraus gelöscht werden.

* Bots sehen weder die IP-Adressen der Benutzer noch andere Referrer-Informationen ein. Alle Informationen stammen von Microsoft. (Es gibt eine Ausnahme: Wenn ein Bot seine eigene Anmeldeumgebung implementiert, werden die IP-Adressen und Referrer-Informationen der Benutzer von der Anmeldebenutzeroberfläche eingesehen.)

* Messaging-Erweiterungen sehen dagegen die IP-Adressen und Referrer-Informationen der Benutzer ein.

* App-Richtlinien (und unser AppSource-Überprüfungsprozess) erfordern Diskretion bei der Veröffentlichung persönlicher Chatnachrichten an Benutzer (über die POST_MESSAGE_TEAM-Berechtigung) für zulässige Zwecke. Im Falle eines Missbrauchs können Benutzer den Bot blockieren, Mandantenadministratoren können die App blockieren, und Microsoft kann Bots bei Bedarf zentral blockieren.

<sup>1</sup> Einige Bots senden nur Nachrichten (POST_MESSAGE_USER). Sie werden als "reine Benachrichtigungs-Bots" bezeichnet, der Begriff bezieht sich jedoch nicht auf das, was ein Bot tun oder nicht tun darf. Er bedeutet, dass der Bot keine Unterhaltungsmöglichkeit bietet. Teams verwendet dieses Feld, um Funktionen auf der Benutzeroberfläche zu deaktivieren, die normalerweise aktiviert würden. Der Bot ist im Vergleich zu solchen, die eine Unterhaltungsmöglichkeit bieten, nicht eingeschränkt was zulässige Aktionen angeht.

<sup>2</sup> Wird von der booleschen Eigenschaft "supportsFiles" für das Bot-Objekt in der `manifest.json`-Datei für die App gesteuert.

> [!NOTE]
> Wenn ein Bot über eine eigene Anmeldemöglichkeit verfügt, gibt es einen zweiten – anderen – Zustimmungsablauf, wenn sich der Benutzer zum ersten Mal anmeldet.
>
>Derzeit sind die Azure AD-Berechtigungen, die einer der Funktionen in einer Microsoft Teams-App (Bot, Registerkarte, Connector oder Messaging-Erweiterung) zugeordnet sind, vollständig von den hier aufgeführten Microsoft Teams-Berechtigungen getrennt.

## <a name="tabs"></a>Registerkarten

Eine Registerkarte ist eine Website, die in Microsoft Teams ausgeführt wird.

### <a name="required-permissions"></a>Erforderliche Berechtigungen

SEND_AND_RECEIVE_WEB_DATA

### <a name="optional-permissions"></a>Optionale Berechtigungen

Keine (derzeit)

### <a name="considerations"></a>Erwägungen

* Das Risikoprofil einer Registerkarte ist fast identisch mit jenem derselben Website, wenn sie in einem Browsertab angezeigt wird.

* Eine Registerkarte ruft auch den Kontext ab, in dem sie ausgeführt wird, einschließlich des Anmeldenamens und des Benutzerprinzipalnamens des aktuellen Benutzers, der Azure AD-Objekt-ID für den aktuellen Benutzer, der ID der Microsoft 365-Gruppe, in der sie sich befindet (wenn es sich um ein Team handelt), der Mandanten-ID und des aktuellen Gebietsschemas des Benutzers. Um diese IDs jedoch den Informationen eines Benutzers zuzuordnen, müsste sich der Benutzer auf der Registerkarte bei Azure AD anmelden.

## <a name="connectors"></a>Connectors

Ein Connector sendet Nachrichten an einen Kanal, wenn Ereignisse in einem externen System auftreten.

### <a name="required-permissions"></a>Erforderliche Berechtigungen

POST_MESSAGE_CHANNEL

### <a name="optional-permissions"></a>Optionale Berechtigungen

REPLYTO_CONNECTOR_MESSAGE. Bestimmte Connectors unterstützen Aktionen erfordernde Nachrichten, mit denen Benutzer gezielte Antworten auf eine Connectornachricht posten können, z. B. durch Hinzufügen einer Antwort auf ein GitHub-Problem oder Hinzufügen eines Datums zu einer Trello-Karte.

### <a name="considerations"></a>Erwägungen

* Das System, das Connectornachrichten sendet, weiß nicht, bei wem gepostet wird oder wer die Nachrichten erhält: Es werden keine Informationen über den Empfänger offengelegt. (Microsoft ist der tatsächliche Empfänger, nicht der Mandant; das eigentliche Posting erfolgt durch Microsoft.)

* Wenn Connectornachrichten in einem Kanal gepostet werden, verlassen keine Daten das Unternehmensnetzwerk.

* Connectors, die Aktionen erfordernde Nachrichten unterstützen (REPLYTO_CONNECTOR_MESSAGE-Berechtigung), sehen auch keine IP-Adresse und Referrer-Informationen ein. Diese Informationen werden an Microsoft gesendet und dann an HTTP-Endpunkte weitergeleitet, die zuvor bei Microsoft im Connectors-Portal registriert wurden.

* Jedes Mal, wenn ein Connector für einen Kanal konfiguriert wird, wird eine eindeutige URL für diese Connectorinstanz erstellt. Wenn diese Connectorinstanz gelöscht wird, kann die URL nicht mehr verwendet werden.

* Connectornachrichten dürfen keine Dateianlagen enthalten.

* Die Connectorinstanz-URL sollte als geheim/vertraulich behandelt werden: Jede Person, die über diese URL verfügt, kann Posts an sie senden wie an eine E-Mail-Adresse. Daher besteht das Risiko von Spam oder Links zu Phishing- oder Schadsoftwarewebsites. In diesem Fall können Teambesitzer die Connectorinstanz löschen.

* Sollte der Dienst, der Connectornachrichten sendet, kompromittiert werden und mit dem Senden von Spam-/Phishing-/Schadsoftwarelinks beginnen, kann ein Mandantenadministrator verhindern, dass neue Connectorinstanzen erstellt werden, und Microsoft kann sie zentral blockieren.

> [!NOTE]
> Es ist derzeit nicht möglich zu wissen, welche Connectors Aktionen erfordernde Nachrichten unterstützen (REPLYTO_CONNECTOR_MESSAGE-Berechtigung).

## <a name="outgoing-webhooks"></a>Ausgehende Webhooks

_Ausgehende Webhooks_ werden von Teambesitzern oder Teammitgliedern erstellt. Sie sind keine Funktionen von Microsoft Teams-Apps ( diese Information ist der Vollständigkeit halber angegeben).

### <a name="required-permissions"></a>Erforderliche Berechtigungen

RECEIVE_MESSAGE, REPLYTO_MESSAGE. Kann Nachrichten von Benutzern empfangen und ihnen antworten.

### <a name="optional-permissions"></a>Optionale Berechtigungen

Keine

### <a name="considerations"></a>Erwägungen

* Ausgehende Webhooks ähneln Bots, verfügen jedoch über weniger Berechtigungen. Sie müssen explizit erwähnt werden, genau wie Bots.

* Wenn ein ausgehender Webhook registriert wird, wird ein geheimer Schlüssel generiert, mit dem der ausgehende Webhook überprüfen kann, ob es sich bei dem Absender um Microsoft Teams handelt und nicht um einen böswilligen Angreifer. Dieser geheime Schlüssel sollte geheim bleiben: Jeder, der Zugriff darauf hat, kann sich als Microsoft Teams ausgeben. Wenn das Geheimnis kompromittiert wird, löschen Sie den ausgehenden Webhook, und erstellen Sie ihn neu, um ein neues Geheimnis zu generieren.

* Es ist zwar möglich, einen ausgehenden Webhook zu erstellen, der den geheimen Schlüssel nicht überprüft, davon wird jedoch abgeraten.

* Abgesehen vom Empfangen und Beantworten von Nachrichten können ausgehende Webhooks nicht viel tun: Sie können keine Nachrichten proaktiv senden, sie können keine Dateien senden oder empfangen, sie können nichts von dem tun, was Bots möglich ist, außer Nachrichten empfangen und darauf antworten.
