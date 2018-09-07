---
title: Microsoft-Teams, apps Berechtigungen und Aspekte
author: Lester-Hewett
ms.author: lehewe
manager: serdars
ms.date: 08/20/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: lehewe
description: Hier erfahren Sie, was von Ihrer Organisation, die apps Daten und Berechtigungen anfordert.
localization_priority: Priority
appliesto:
- Microsoft Teams
ms.openlocfilehash: f35620c1778bbe12f7d98f1a326e47a58804680b
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23870173"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a>Microsoft-Teams, apps Berechtigungen und Aspekte

Microsoft-Teams, apps bieten eine Möglichkeit, eine oder mehrere Funktionen in einer _app-Paket_ zusammenfassen, das installiert, aktualisiert und deinstalliert werden kann. Die Funktionen umfassen:

-   Bots
-   Messaging-Erweiterungen
-   Registerkarten
-   Connectors

Apps werden von Benutzern zu zugestimmt und von verwalteten IT aus Sicht der Richtlinie. Allerdings werden in den meisten Fällen einer app Berechtigungen und Risikoprofil definiert die Berechtigungen und das Risikoprofile der darin enthaltenen Funktionen. Deshalb liegt der Schwerpunkt in diesem Artikel auf Berechtigungen und Aspekten finden Sie unter Capability-Ebene.

Die in Großbuchstaben, beispielsweise RECEIVE_MESSAGE und REPLYTO_MESSAGE, nachfolgend aufgeführten Berechtigungen werden nicht an einer beliebigen Stelle in der [Entwicklerdokumentation zu Microsoft-Teams,](https://aka.ms/teamsdevdocs) oder die [Berechtigungen für Microsoft Graph](https://developer.microsoft.com/graph/docs/concepts/permissions_reference)angezeigt. Sie sind nur die eine beschreibende Kurzform im Sinne dieses Artikels.


|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>Entscheidungspunkt|<ul><li>Verwenden Sie die Tabellen unten als Leitfaden um zu verstehen, welche Berechtigungen anfordern der apps, die Sie untersuchen möchten.</li></ul> |
| ![](media/audio_conferencing_image9.png)<br/>Als Nächstes|<ul><li>Untersuchen Sie die app oder die Dienst selbst, um zu entscheiden, ob Sie Zugriff darauf innerhalb Ihrer Organisation zulassen möchten. Beispielsweise Bots senden und Empfangen von Nachrichten von Benutzern, und – außer Enterprise Line-of-Business-Programmen – sie außerhalb der Begrenzung für die Einhaltung von Bestimmungen gespeichert sind. Daher alle app, die ein Bot enthält erfordert diese Berechtigungen und weist diesem Risikoprofil mindestens. </li></ul>|

## <a name="global-app-permissions-and-considerations"></a>Globale app-Berechtigungen und Überlegungen

<table>
  <tr>
    <th width="25%">Erforderliche Berechtigungen</th>
    <th width="25%">Optionale Berechtigungen</th>
    <th width="50%">Überlegungen</th>
  </tr>
  <tr>
    <td valign="top">Keine</td>
    <td valign="top">Keine</td>
    <td valign="top">Eine app muss anzugeben, welche Daten verwendet und welche die Daten für seine hinsichtlich der Verwendung und den Datenschutz Gruppenrichtlinien Links verwendet werden.</td>
  </tr>
</table>

## <a name="bots-and-messaging-extensions"></a>Bots und messaging-Erweiterungen

<table>
 <thead>
  <tr>
    <th width="0.5%"></th>
    <th width="24.5%">Erforderliche Berechtigungen</th>
    <th width="25%">Optionale Berechtigungen</th>
    <th width="50%">Überlegungen</th>
  </tr>
</thead>
<tbody>
   <tr>
    <td valign="top" colspan="2"><ul><li>   RECEIVE_MESSAGE, REPLYTO_MESSAGE. Der Bot können empfangen von Nachrichten von Benutzern und darauf antworten. <sup>1</sup></li><li>POST_MESSAGE_USER. Nachdem ein Benutzer eine Nachricht in einen Bot gesendet hat, können den Robot der Benutzer senden direkte Nachrichten (auch als _proaktiven Nachrichten_bezeichnet) können Sie jederzeit.</li><li>GET_CHANNEL_LIST. Bots, Teams hinzugefügt wurde, kann eine Liste der Namen und IDs der Kanäle in ein Team abrufen.</li></ul></td>
    <td valign="top"><ul><li>IDENTITÄT. Wenn sie in einem Kanal verwendet wird, können die app Bots grundlegende Identitätsinformationen Teammitglieder (Vorname, Nachname, User principal Name [, UPN], e-Mail-Adresse); zugreifen. Wenn sie in eine persönliche oder Group Chat verwendet wird, können den Robot dieselbe Informationen für diese Benutzer zugreifen.</li><li> POST_MESSAGE_TEAM. Ermöglicht eine app Bots direkte (proaktive) Nachrichten an jedes Teammitglied zu einem beliebigen Zeitpunkt zu senden, auch wenn der Benutzer auf den Robot vor nie gesprochen hat.</li><li>Die folgenden sind nicht ausdrückliche Berechtigungen, jedoch werden durch RECEIVE_MESSAGE und REPLYTO_MESSAGE sowie die Bereiche, in denen die Bots kann im Manifest deklariert verwendet werden, KONKLUDENT: <ul><li>RECEIVE_MESSAGE_PERSONAL REPLYTO_MESSAGE_PERSONAL</li><li>RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT<sup>2</sup> </li><li>RECEIVE_MESSAGE_TEAM REPLYTO_MESSAGE_TEAM</li></ul><li>SEND_FILES, RECEIVE_FILES. <sup>3</sup> -Steuerelemente, Dateien, ob ein Bot senden und empfangen kann im persönlichen Chat (für Gruppenchat oder Kanäle noch nicht unterstützt).</li></ul></td>
    <td valign="top"><ul><li>Bots haben nur Zugriff auf Teams, die sie hinzugefügt wurden, oder für Benutzer, die sie installiert haben.</li><li>Bots, erhalten nur dann Nachrichten, in denen sie explizit durch Benutzer erwähnt sind. Diese Daten verlässt des Firmennetzwerks befinden.</li><li>    Bots können nur auf Unterhaltungen Antworten, in denen sie erwähnten sind.</li><li>Nach ein Benutzer mit einem Bot, und der Bot-ID des Benutzers gespeichert sind conversed hat, können sie diesen Benutzer direkte Nachrichten können Sie jederzeit senden. </li><li>Es ist theoretisch möglich, dass Bot-Nachrichten enthalten Links zu Phishing oder Malware Websites, aber Bots durch den Benutzer, der Administrator des Mandanten oder global von Microsoft blockiert werden. </li><li>Ein Bot kann abrufen (und möglicherweise speichern) elementare Identitätsinformationen für die Teammitglieder, die, denen die app hinzugefügt wurde, oder für einzelne Benutzer in Gruppen- oder persönliche Chats. Um weitere Informationen zu diesen Benutzern zu erhalten, müssen den Robot Azure Active Directory (AD Azure) anmelden müssen. </li><li>Bots können abrufen (und möglicherweise speichern) die Liste der Kanäle in einem Team; Diese Daten verlässt des Firmennetzwerks befinden. </li><li>Wenn eine Datei in einen Bot gesendet wird, verbleibt die Datei des Firmennetzwerks befinden. Senden und Empfangen von Dateien erfordert Benutzer Genehmigung für jede Datei. </li><li>Standardmäßig Bots haben nicht die Möglichkeit, die im Auftrag des Benutzers fungiert, aber Bots können Benutzer zur Anmeldung bei Fragen. Sobald der Benutzer anmeldet, wird der Bot ein Zugriffstoken haben, mit denen sie zusätzliche Aufgaben ausführen kann. Genau wie zusätzliche Dinge sind, hängt davon ab, den Robot und, in dem der Benutzer meldet sich: ein Bot ist eine Azure AD-app unter registriert <a href="https://apps.dev.microsoft.com/">https://apps.dev.microsoft.com/</a> und kann über einen eigenen Satz von Berechtigungen verfügen.</li><li>Bots werden informiert, wenn Benutzer hinzugefügt oder aus einem Team gelöscht werden.</li><li>Bots werden keine IP-Adressen von Benutzern oder andere Verweisursprungsinformationen angezeigt. Alle Informationen stammen von Microsoft. (Es gibt eine Ausnahme: Wenn ein Bot eine eigene Anmeldung implementiert wird, sehen die Benutzeroberfläche Anmeldung Verweisursprungsinformationen und IP Adressen Benutzer.)</li><li>Messaging-Erweiterungen, führen Sie andererseits, IP-Adressen von Benutzern und Verweisursprungsinformationen finden Sie unter.</li><li>App-Richtlinien (und unsere Überprüfungsprozess Elemente verwenden) erfordern Ermessen Buchen der persönlichen Chatnachrichten für Benutzer (über die Berechtigung POST_MESSAGE_TEAM) für gültige Zwecke. Bei einem Missbrauch können Benutzer den Robot blockieren, Mandanten-Administratoren können die app blockieren und kann Microsoft Bots zentral blockieren, falls erforderlich.</li></ul></td>
</tr>
</tbody>
<tfoot>
<tr><td align="right"><sup>1</sup></td><td colspan="3">Einige Bots senden nur Nachrichten (POST_MESSAGE_USER). Sind sie "nur Benachrichtigung" Bots aufgerufen, aber der Begriff bezieht sich nicht auf welche ein Bot zugelassen oder Aktionen nicht zulässig ist, bedeutet dies, dass der Bot keine Gesprächs Erfahrung verfügbar machen möchten. Teams verwendet dieses Feld, um die Funktionalität in der Benutzeroberfläche deaktivieren, die normalerweise aktiviert werden; der Bot ist nicht eingeschränkt in was es dürfen hat im Vergleich zu Bots, die eine Gesprächs Erfahrung verfügbar machen.</td></tr>
<tr><td align="right"><sup>2</sup></td><td colspan="3">Derzeit in der Vorschau für Entwickler.</td></tr>
<tr><td align="right"><sup>3</sup></td><td colspan="3">Derzeit in der Vorschau für Entwickler. Unterliegt den <code>supportsFiles</code> boolesche Eigenschaft für das Bot-Objekt in der Datei manifest.json für die app.</td>
</tr>
</tfoot>
</table>

> [!Note]
> <ul><li>Verfügt ein Bot eine eigene Anmeldung, es gibt eine zweite – verschiedene – Zustimmung Erfahrung beim ersten der Benutzer anmeldet.</li><li>Derzeit sind die Azure AD-Berechtigungen für jede der Funktionen innerhalb einer app Teams (Robot, Registerkarte, Verbinder oder messaging Erweiterung) völlig unabhängig von den hier aufgelisteten Teams Berechtigungen.</li></ul>


## <a name="tabs"></a>Registerkarten

Eine Registerkarte ist eine Website innerhalb Teams ausgeführt.

<table>
  <tr>
    <th width="25%">Erforderliche Berechtigungen</th>
    <th width="25%">Optionale Berechtigungen</th>
    <th width="50%">Überlegungen</th>
  </tr>
  <tr>
    <td valign="top">SEND_AND_RECEIVE_WEB_DATA</td>
    <td valign="top">Keine (aktuell).</td>
    <td valign="top"><ul><li>Das Risikoprofil für eine Registerkarte ist nahezu identisch, die gleichen Website in einer Registerkarte Browser ausgeführt. </li><li>Eine Registerkarte ruft auch den Kontext, in denen er ausgeführt wird, einschließlich des Namens der Anmeldung und UPN des aktuellen Benutzers, Azure AD-Objekt-ID für den aktuellen Benutzer, die ID des Office 365 Gruppe (Team), in dem es sich befindet, die Mandanten-ID und das aktuelle Gebietsschema des Benutzers, ab. Jedoch, um diese IDs Informationen eines Benutzers zuzuordnen, die Registerkarte müssten der Benutzer für die Anmeldung bei Azure AD tätigen.</li></ul></td>
  </tr>
  </table>

## <a name="connectors"></a>Connectors

Ein Connector sendet Nachrichten an einen Kanal beim Auftreten von Ereignissen in einem externen System.

  <table>
  <tr>
    <th width="25%">Erforderliche Berechtigungen</th>
    <th width="25%">Optionale Berechtigungen</th>
    <th width="50%">Überlegungen</th>
  </tr>
  <tr>
    <td valign="top">POST_MESSAGE_CHANNEL</td>
    <td valign="top">REPLYTO_CONNECTOR_MESSAGE. Bestimmte Connectors unterstützen _bearbeitungsfähige Nachrichten_, die Benutzer gezielte Antworten auf die Nachricht Connector, beispielsweise durch Hinzufügen einer Antwort auf ein Problem GitHub oder Hinzufügen eines Datums zu einer Karte Trello buchen zulassen.</td>
    <td valign="top"><ul><li>Das System, das Connector Nachrichten übermittelt, die es buchen oder empfängt, die die Nachrichten weiß nicht: ist keine Informationen über den Empfänger anzugeben. (Microsoft ist der eigentliche Empfänger, nicht für den Mandanten. Microsoft ist der tatsächlichen Post an den Kanal.)</li><li>Keine Daten verlässt des Firmennetzwerks befinden, wenn Connector Nachrichten an einen Kanal veröffentlicht wurden.</li><li>Verbinder, die bearbeitungsfähige Nachrichten (REPLYTO_CONNECTOR_MESSAGE Berechtigung) unterstützt nicht auch IP-Adresse "und" Referenz Informationen finden Sie unter; Diese Informationen sind an Microsoft gesendet, und klicken Sie dann auf HTTP-Endpunkte, die zuvor mit Microsoft im Portal Connectors registriert wurden weitergeleitet.</li><li>Jedes Mal, wenn ein Connector konfiguriert ist, wird für einen Kanal wird ein eindeutiger URL für diese Connectorinstanz erstellt. Wenn dieser Connector-Instanz gelöscht wird, kann die URL nicht mehr verwendet werden.</li><li>Connector Nachrichten können nicht Dateianlagen enthalten.</li><li>Connector-Instanz, die URL als Schlüssel/vertraulich behandelt werden sollte: jeder Benutzer mit, dass die URL, Nachrichten veröffentlichen kann wie eine e-Mail-Adresse. Aus diesem Grund besteht einige Risiko Spam oder Links zu Phishing oder Malware Websites. Würde, die auftreten, können Teams Besitzer die Connector-Instanz löschen.</li><li>Wenn der Dienst, der Connector Nachrichten waren so gefährdet werden, und starten Sie senden von Spam/Phishing/Malware Links sendet, mandantenadministrator kann verhindern, dass neue Connectorinstanzen erstellt wird und Microsoft können sie zentral blockieren.</li></ul></td>
  </tr>
</table>

> [!Note]
> Es ist nicht wissen, welche Konnektoren bearbeitungsfähige Nachrichten (REPLYTO_CONNECTOR_MESSAGE Berechtigung) unterstützt derzeit möglich.


## <a name="outgoing-webhooks"></a>Ausgehende webhooks

_Ausgehende Webhooks_ werden während der Bearbeitung durch Team Besitzer oder Teammitglieder erstellt, wenn Sideloading für einen Mandanten aktiviert ist. Sie werden nicht die Funktionen des Teams apps. Diese Informationen sind Vollständigkeit.

<table>
  <tr>
    <th width="25%">Erforderliche Berechtigungen</th>
    <th width="25%">Optionale Berechtigungen</th>
    <th width="50%">Überlegungen</th>
  </tr>
    <tr>
    <td valign="top">RECEIVE_MESSAGE, REPLYTO_MESSAGE. Empfangen von Nachrichten von Benutzern und darauf antworten können.</td>
    <td valign="top">Keine</td>
    <td valign="top"><ul><li>Ausgehende Webhooks ähneln Bots, aber deshalb mit niedrigeren Berechtigungen haben. Sie müssen explizit, genau wie Bots angegeben werden.</li><li>Wenn eine ausgehende Webhook registriert ist, wird einen _geheimen Schlüssel_ generiert, sodass die ausgehende Webhook überprüfen, ob der Absender Microsoft-Teams, im Gegensatz zu einem Angreifer ist. Dieser Schlüssel sollte einen geheimen Schlüssel bleiben. Jeder Benutzer mit Zugriff auf die Datei kann Microsoft-Teams imitieren. Wenn der geheimen Schlüssel gefährdet ist, die ausgehende Webhook gelöscht und neu erstellt werden kann, und ein neuer geheimen Schlüssel generiert werden.</li><li>Es ist, zwar möglich, eine ausgehende Webhook zu erstellen, die den geheime Schlüssel überprüfen nicht raten wir von einer es.</li><li>Außer empfangen und Beantworten von Nachrichten, ausgehende Webhooks kann nicht viel: proaktiv keine Nachrichten senden, nicht senden oder Empfangen von Dateien, sie können keine weiteren Schritte durchführen, die Bots empfangen und auf Nachrichten antworten, außer können.</li></ul></td>
  </tr>
</table>