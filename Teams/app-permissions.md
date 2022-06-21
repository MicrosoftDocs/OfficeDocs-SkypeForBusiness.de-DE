---
title: Berechtigungen für Microsoft Teams-Apps und Überlegungen dazu
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.date: 06/27/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
search.appverid: MET150
ms.reviewer: rowille
description: Admin können erfahren, welche Daten und Berechtigungen Microsoft Teams Apps von ihrer Organisation anfordern.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 925136660ef6adda6374fab1acccf10a2b9f1722
ms.sourcegitcommit: 9946c6c1faa78617ccd7bdf115457090ebce5619
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/21/2022
ms.locfileid: "66190285"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a>Berechtigungen für Microsoft Teams-Apps und Überlegungen dazu

Microsoft Teams Apps sind eine Möglichkeit, eine oder mehrere Funktionen in Apps zu aggregieren, die installiert, aktualisiert und deinstalliert werden können. Zu den Funktionen von Apps gehören:

* Bots
* Messaging-Erweiterungen
* Registerkarten
* Steckverbinder

Als Administrator verwalten Sie nur Apps. Der Artikel konzentriert sich jedoch auf Berechtigungen und Überlegungen auf der Funktionsebene, da sich Die Funktionen in einer App auf die erforderlichen Berechtigungen und Risikoprofile der App auswirken. Für die Nutzung werden Apps von Benutzern zugestimmt und von IT-Experten aus richtlinienpolitischer Sicht verwaltet.

Die unten in Großbuchstaben aufgeführten Berechtigungen dienen beispielsweise `RECEIVE_MESSAGE` `REPLYTO_MESSAGE` nur zur Veranschaulichung und Erläuterung. Diese Zeichenfolgen oder Berechtigungen werden weder in der [Microsoft Teams-Entwicklerdokumentation](/microsoftteams/platform/overview) noch in den [Berechtigungen für Microsoft Graph](/graph/permissions-reference) angezeigt.

## <a name="global-app-permissions-and-considerations"></a>Berechtigungen und Überlegungen für globale Apps

### <a name="required-permissions"></a>Erforderliche Berechtigungen

Keine

### <a name="optional-permissions"></a>Optionale Berechtigungen

Keine

### <a name="considerations"></a>Erwägungen

* Eine App muss offenlegen, welche Daten sie verwendet und wofür die Daten in ihren Nutzungsbedingungen und Datenschutzrichtlinienlinks verwendet werden.

* [Die ressourcenspezifische Zustimmung](resource-specific-consent.md) stellt eine Reihe von Berechtigungen bereit, die Apps anfordern können, die auf dem Installationsbildschirm der App angezeigt werden. Weitere Informationen zu ressourcenspezifischen Zustimmungsberechtigungen finden Sie [unter Graph Berechtigungsreferenz](/graph/permissions-reference#teams-resource-specific-consent-permissions).

* Apps benötigen möglicherweise auch andere Berechtigungen als ressourcenspezifische Zustimmungsberechtigungen. Nachdem eine App installiert wurde, kann die App über eine Zustimmungsaufforderung Graph Berechtigungen anfordern. Weitere Informationen finden Sie unter [Grundlegendes zur Zustimmung der Azure AD-Anwendung](/azure/active-directory/develop/application-consent-experience). Sie können API-Berechtigungen und Die Zustimmung in der Azure-Portal konfigurieren. Weitere Informationen finden Sie [unter Azure Active Directory Zustimmungsframework](/azure/active-directory/develop/consent-framework).

## <a name="bots-and-messaging-extensions"></a>Bots und Messaging-Erweiterungen

### <a name="required-permissions"></a>Erforderliche Berechtigungen

* RECEIVE_MESSAGE REPLYTO_MESSAGE: Der Bot kann Nachrichten von Benutzern empfangen und ihnen antworten. <sup>1</sup>

* POST_MESSAGE_USER: Nachdem ein Benutzer eine Nachricht an einen Bot gesendet hat, kann der Bot dem Benutzer jederzeit direkte Nachrichten senden (auch als *proaktive Nachrichten* bezeichnet).

* GET_CHANNEL_LIST: Bots, die Teams hinzugefügt wurden, können eine Liste der Namen und IDs der Kanäle in einem Team abrufen.

### <a name="optional-permissions"></a>Optionale Berechtigungen

* IDENTITÄT: Wenn sie in einem Kanal verwendet wird, können die Bots der App auf grundlegende Identitätsinformationen von Teammitgliedern (Vorname, Nachname, Benutzerprinzipalname [UPN], E-Mail-Adresse) zugreifen. Wenn er in einem persönlichen Chat oder Gruppenchat verwendet wird, kann der Bot auf dieselben Informationen für diese Benutzer zugreifen.

* POST_MESSAGE_TEAM: Ermöglicht es den Bots einer App, jederzeit direkte (proaktive) Nachrichten an das Teammitglied zu senden, auch wenn der Benutzer noch nie mit dem Bot interagiert hat.

* Es folgen keine expliziten Berechtigungen, sondern werden durch RECEIVE_MESSAGE und REPLYTO_MESSAGE und die Bereiche impliziert, in denen die Bots verwendet werden können, die im Manifest deklariert sind:

  * RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL
  * RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT
  * RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM

* Es folgen keine expliziten Berechtigungen, sondern werden durch RECEIVE_MESSAGE und REPLYTO_MESSAGE und die Bereiche impliziert, in denen die Bots verwendet werden können, die im Manifest deklariert sind:

  * RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL
  * RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT
  * RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM

* SEND_FILES RECEIVE_FILES:<sup>2</sup> steuert, ob ein Bot Dateien im persönlichen Chat senden und empfangen kann (wird für Gruppenchats oder Kanäle noch nicht unterstützt).

### <a name="considerations"></a>Erwägungen

* Bots haben nur Zugriff auf Teams, zu denen sie hinzugefügt wurden, oder auf Benutzer, die sie installiert haben.

* Bots erhalten nur Nachrichten, in denen sie von Benutzern explizit erwähnt werden. Diese Daten verlassen das Unternehmensnetzwerk.

* Bots können nur auf Unterhaltungen antworten, in denen sie erwähnt werden.

* Wenn sich ein Benutzer mit einem Bot unterhält und der Bot die ID des Benutzers speichert, kann er dem Benutzer jederzeit Direktnachrichten senden.

* Theoretisch ist es möglich, dass Bot-Nachrichten Links zu Phishing- oder Schadsoftwarewebsites enthalten. Bots können jedoch vom Benutzer, dem Mandantenadministrator oder global von Microsoft blockiert werden. [Überprüfungen der App-Überprüfung und -Überprüfung](overview-of-app-validation.md) stellen sicher, dass alle unrichtigen Apps nicht in Teams Store verfügbar sind.

* Ein Bot kann grundlegende Identitätsinformationen für die Teammitglieder, denen die App hinzugefügt wurde, oder für einzelne Benutzer in persönlichen Chats oder Gruppenchats abrufen (und möglicherweise speichern). Um weitere Informationen zu diesen Benutzern zu erhalten, muss der Bot verlangen, dass sie sich bei Azure Active Directory (Azure AD) anmelden.

* Bots können die Liste der Kanäle in einem Team abrufen (und möglicherweise speichern). diese Daten verlassen das Unternehmensnetzwerk.

* Standardmäßig haben Bots nicht die Möglichkeit, im Namen des Benutzers zu handeln, aber Bots können Benutzer zur Anmeldung auffordern. sobald sich der Benutzer anmeldet, verfügt der Bot über ein Zugriffstoken, mit dem er zusätzliche Aktionen ausführen kann. Was genau diese anderen Dinge sind, hängt vom Bot ab und wo sich der Benutzer anmeldet: Ein Bot ist eine Azure AD-App, bei https://apps.dev.microsoft.com/ der er registriert ist und über eigene Berechtigungen verfügen kann.

* Wenn eine Datei an einen Bot gesendet wird, verlässt die Datei das Unternehmensnetzwerk. Das Senden und Empfangen von Dateien erfordert eine Benutzergenehmigung für jede Datei.

* Standardmäßig haben Bots nicht die Möglichkeit, im Namen des Benutzers zu handeln, aber Bots können Benutzer zur Anmeldung auffordern. sobald sich der Benutzer anmeldet, verfügt der Bot über ein Zugriffstoken, mit dem er zusätzliche Aktionen ausführen kann. Was genau diese zusätzlichen Dinge sind, hängt vom Bot ab und davon, wo sich der Benutzer anmeldet: Ein Bot ist eine Azure AD-App, die im [Anwendungsregistrierungsportal](https://apps.dev.microsoft.com/?referrer=https:%2f%2fdocs.microsoft.com%2f#/appList) registriert ist und über eigene Berechtigungen verfügen kann.

* Bots werden immer dann informiert, wenn Benutzer zu einem Team hinzugefügt oder daraus gelöscht werden.

* Bots sehen weder die IP-Adressen der Benutzer noch andere Referrer-Informationen. Alle Informationen stammen von Microsoft. (Es gibt eine Ausnahme: Wenn ein Bot seine eigene Anmeldeumgebung implementiert, werden auf der Anmeldebenutzeroberfläche die IP-Adressen und Referrer-Informationen der Benutzer angezeigt.)

* Messaging-Erweiterungen sehen dagegen die IP-Adressen und Referrer-Informationen der Benutzer.

* App-Richtlinien (und unser AppSource-Überprüfungsprozess) erfordern Diskretion bei der Veröffentlichung persönlicher Chatnachrichten an Benutzer (über die POST_MESSAGE_TEAM Berechtigung) für gültige Zwecke. Im Falle eines Missbrauchs können Benutzer den Bot blockieren, Mandantenadministratoren können die App blockieren, und Microsoft kann Bots bei Bedarf zentral blockieren.

<sup>1</sup> Einige Bots senden nur Nachrichten (POST_MESSAGE_USER). Sie werden als "Nur-Benachrichtigungs-Bots" bezeichnet, aber der Begriff bezieht sich nicht auf das, was ein Bot tun darf oder nicht, was bedeutet, dass der Bot keine Unterhaltungserfahrung verfügbar machen möchte. Teams verwendet dieses Feld, um Funktionen auf der Benutzeroberfläche zu deaktivieren, die normalerweise aktiviert würden. Der Bot ist nicht in dem eingeschränkt, was er tun darf, im Vergleich zu Bots, die eine Unterhaltungserfahrung verfügbar machen.

<sup>2</sup> Wird von der booleschen Eigenschaft supportsFiles für das Bot-Objekt in der `manifest.json` Datei für die App gesteuert.

> [!NOTE]
> Wenn ein Bot über eine eigene Anmeldung verfügt, gibt es eine zweite – andere – Zustimmungserfahrung, wenn sich der Benutzer zum ersten Mal anmeldet.
>
>Derzeit sind die Azure AD-Berechtigungen, die einer der Funktionen in einer Teams-App (Bot, Registerkarte, Connector oder Messaging-Erweiterung) zugeordnet sind, vollständig von den hier aufgeführten Teams Berechtigungen getrennt.

## <a name="tabs"></a>Registerkarten

Eine Registerkarte ist eine Website, die in Teams ausgeführt wird.

### <a name="required-permissions"></a>Erforderliche Berechtigungen

SEND_AND_RECEIVE_WEB_DATA

### <a name="optional-permissions"></a>Optionale Berechtigungen

Keine (derzeit)

### <a name="considerations"></a>Erwägungen

* Das Risikoprofil für eine Registerkarte ist fast identisch mit derselben Website, die auf einer Browserregisterkarte ausgeführt wird.

* Eine Registerkarte ruft auch den Kontext ab, in dem sie ausgeführt wird, einschließlich des Anmeldenamens und des UPN des aktuellen Benutzers, der Azure AD-Objekt-ID für den aktuellen Benutzer, der ID der Microsoft 365 Gruppe, in der sie sich befindet (wenn es sich um ein Team handelt), der Mandanten-ID und dem aktuellen Gebietsschema des Benutzers. Um diese IDs jedoch den Informationen eines Benutzers zuzuordnen, müsste sich der Benutzer auf der Registerkarte bei Azure AD anmelden.

## <a name="connectors"></a>Steckverbinder

Ein Connector sendet Nachrichten an einen Kanal, wenn Ereignisse in einem externen System auftreten.

### <a name="required-permissions"></a>Erforderliche Berechtigungen

POST_MESSAGE_CHANNEL

### <a name="optional-permissions"></a>Optionale Berechtigungen

REPLYTO_CONNECTOR_MESSAGE. Bestimmte Connectors unterstützen Nachrichten mit Aktionen, mit denen Benutzer gezielte Antworten auf die Connectornachricht posten können, z. B. durch Hinzufügen einer Antwort auf ein GitHub-Problem oder Hinzufügen eines Datums zu einer Trello-Karte.

### <a name="considerations"></a>Erwägungen

* Das System, das Connectornachrichten sendet, weiß nicht, bei wem es gepostet wird oder wer die Nachrichten empfängt: Es werden keine Informationen über den Empfänger offengelegt. (Microsoft ist der tatsächliche Empfänger, nicht der Mandant; Microsoft führt den tatsächlichen Beitrag im Kanal aus.)

* Wenn Connectornachrichten in einem Kanal gepostet werden, verlassen keine Daten das Unternehmensnetzwerk.

* Connectors, die Nachrichten mit Aktionen unterstützen (REPLYTO_CONNECTOR_MESSAGE Berechtigung), sehen auch keine IP-Adresse und Verweiserinformationen; Diese Informationen werden an Microsoft gesendet und dann an HTTP-Endpunkte weitergeleitet, die zuvor bei Microsoft im Connectors-Portal registriert wurden.

* Jedes Mal, wenn ein Connector für einen Kanal konfiguriert wird, wird eine eindeutige URL für diese Connectorinstanz erstellt. Wenn diese Connectorinstanz gelöscht wird, kann die URL nicht mehr verwendet werden.

* Connectornachrichten dürfen keine Dateianlagen enthalten.

* Die Connectorinstanz-URL sollte als geheim/vertraulich behandelt werden: Jede Person, die über diese URL verfügt, kann sie posten, z. B. eine E-Mail-Adresse. Daher besteht das Risiko von Spam oder Links zu Phishing- oder Schadsoftwarewebsites. In diesem Fall können Teambesitzer die Connectorinstanz löschen.

* Sollte der Dienst, der Connectornachrichten sendet, kompromittiert werden und mit dem Senden von Spam-/Phishing-/Schadsoftwarelinks beginnen, kann ein Mandantenadministrator verhindern, dass neue Connectorinstanzen erstellt werden, und Microsoft kann sie zentral blockieren.

> [!NOTE]
> Es ist derzeit nicht möglich zu wissen, welche Connectors Nachrichten mit Aktionen unterstützen (REPLYTO_CONNECTOR_MESSAGE Berechtigung).

## <a name="outgoing-webhooks"></a>Ausgehende Webhooks

_Ausgehende Webhooks_ werden von Teambesitzern oder Teammitgliedern erstellt. Sie sind keine Funktionen von Teams-Apps. Diese Informationen sind aus Gründen der Vollständigkeit enthalten.

### <a name="required-permissions"></a>Erforderliche Berechtigungen

RECEIVE_MESSAGE, REPLYTO_MESSAGE. Kann Nachrichten von Benutzern empfangen und ihnen antworten.

### <a name="optional-permissions"></a>Optionale Berechtigungen

Keine

### <a name="considerations"></a>Erwägungen

* Ausgehende Webhooks ähneln Bots, verfügen jedoch über weniger Berechtigungen. Sie müssen explizit erwähnt werden, genau wie Bots.

* Wenn ein ausgehender Webhook registriert wird, wird ein geheimer Schlüssel generiert, der es dem ausgehenden Webhook ermöglicht zu überprüfen, ob der Absender Microsoft Teams ist, im Gegensatz zu einem böswilligen Angreifer. Dieses Geheimnis sollte ein Geheimnis bleiben; Jeder, der Zugriff darauf hat, kann sich Microsoft Teams imitieren. Wenn der geheime Schlüssel kompromittiert ist, kann der ausgehende Webhook gelöscht und neu erstellt werden, und ein neuer geheimer Schlüssel wird generiert.

* Obwohl es möglich ist, einen ausgehenden Webhook zu erstellen, der das Geheimnis nicht überprüft, wird davon abgeraten.

* Neben dem Empfangen und Beantworten von Nachrichten können ausgehende Webhooks nicht viel tun: Sie können nachrichten nicht proaktiv senden, sie können keine Dateien senden oder empfangen, sie können nichts anderes tun, was Bots außer dem Empfangen und Beantworten von Nachrichten tun können.
