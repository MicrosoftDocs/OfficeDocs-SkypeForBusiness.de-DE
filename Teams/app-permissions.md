---
title: Berechtigungen für Microsoft Teams-Apps und Überlegungen dazu
author: Lester-Hewett
ms.author: lehewe
manager: serdars
ms.date: 08/20/2018
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_PracticalGuidance
search.appverid: MET150
ms.reviewer: lehewe
description: Hier erfahren Sie, welche Daten und Berechtigungen Apps von Ihrer Organisation anfordern.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 960f54f27b7019d15d287c637c7c58f73dfdef0f
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "25014187"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a>Berechtigungen für Microsoft Teams-Apps und Überlegungen dazu

Microsoft-Teams, apps bieten eine Möglichkeit, eine oder mehrere Funktionen in einer _app-Paket_ zusammenfassen, das installiert, aktualisiert und deinstalliert werden kann. Die Funktionen umfassen:

-   Bots
-   Messagingerweiterungen
-   Registerkarten
-   Connectors

Apps werden von Benutzern zu zugestimmt und von verwalteten IT aus Sicht der Richtlinie. Allerdings werden in den meisten Fällen einer app Berechtigungen und Risikoprofil definiert die Berechtigungen und das Risikoprofile der darin enthaltenen Funktionen. Deshalb liegt der Schwerpunkt in diesem Artikel auf Berechtigungen und Aspekten finden Sie unter Capability-Ebene.

Die in Großbuchstaben, beispielsweise RECEIVE_MESSAGE und REPLYTO_MESSAGE, nachfolgend aufgeführten Berechtigungen werden nicht an einer beliebigen Stelle in der [Entwicklerdokumentation zu Microsoft-Teams,](https://aka.ms/teamsdevdocs) oder die [Berechtigungen für Microsoft Graph](https://developer.microsoft.com/graph/docs/concepts/permissions_reference)angezeigt. Sie sind nur die eine beschreibende Kurzform im Sinne dieses Artikels.


|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>Entscheidungspunkt|<ul><li>Verwenden Sie die folgenden Tabellen als Verständnishilfe für die Berechtigungen, die von Ihnen untersuchten Apps anfordern.</li></ul> |
| ![](media/audio_conferencing_image9.png)<br/>Nächster Schritt|<ul><li>Untersuchen Sie die app oder die Dienst selbst, um zu entscheiden, ob Sie Zugriff darauf innerhalb Ihrer Organisation zulassen möchten. Beispielsweise Bots senden und Empfangen von Nachrichten von Benutzern, und – außer Enterprise Line-of-Business-Programmen – sie außerhalb der Begrenzung für die Einhaltung von Bestimmungen gespeichert sind. Daher alle app, die ein Bot enthält erfordert diese Berechtigungen und weist diesem Risikoprofil mindestens. </li></ul>|

## <a name="global-app-permissions-and-considerations"></a>Globale App-Berechtigungen und Überlegungen dazu

<table>
  <tr>
    <th width="25%">Erforderliche Berechtigungen</th>
    <th width="25%">Optionale Berechtigungen</th>
    <th width="50%">Überlegungen</th>
  </tr>
  <tr>
    <td valign="top">Keine</td>
    <td valign="top">Keine</td>
    <td valign="top">In den Links zu den Nutzungsbedingungen und Datenschutzrichtlinien einer App muss offengelegt werden, welche Daten die App verwendet und zu welchen Zwecken dies geschieht.</td>
  </tr>
</table>

## <a name="bots-and-messaging-extensions"></a>Bots und Messagingerweiterungen

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
    <td valign="top"><ul><li>IDENTITÄT. Wenn sie in einem Kanal verwendet wird, können die app Bots grundlegende Identitätsinformationen Teammitglieder (Vorname, Nachname, User principal Name [, UPN], e-Mail-Adresse); zugreifen. Wenn sie in eine persönliche oder Group Chat verwendet wird, können den Robot dieselbe Informationen für diese Benutzer zugreifen.</li><li> POST_MESSAGE_TEAM. Ermöglicht eine app Bots direkte (proaktive) Nachrichten an jedes Teammitglied zu einem beliebigen Zeitpunkt zu senden, auch wenn der Benutzer auf den Robot vor nie gesprochen hat.</li><li>Bei den folgenden Berechtigungen handelt es sich nicht um explizite Berechtigungen. Diese Berechtigungen werden durch RECEIVE_MESSAGE und REPLYTO_MESSAGE und durch die im Manifest deklarierten Bereiche, in denen die Bots verwendet werden, impliziert. <ul><li>RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL</li><li>RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT<sup>2</sup> </li><li>RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM</li></ul><li>SEND_FILES, RECEIVE_FILES:<sup>3</sup> Steuert, ob ein Bot in privaten Chats Dateien senden und empfangen kann. (Wird für Gruppen-Chats oder Kanäle noch nicht unterstützt.)</li></ul></td>
    <td valign="top"><ul><li>Bots haben nur Zugriff auf Teams, zu denen sie hinzugefügt wurden, oder auf Benutzer, von denen sie installiert wurden.</li><li>Bots, erhalten nur dann Nachrichten, in denen sie explizit durch Benutzer erwähnt sind. Diese Daten verlässt des Firmennetzwerks befinden.</li><li>    Bots können nur in Unterhaltungen antworten, in denen sie erwähnt wurden.</li><li>Wenn sich ein Benutzer mit einem Bot unterhalten hat und der Bot die ID des Benutzers gespeichert hat, kann der Bot jederzeit Direktnachrichten an diesen Benutzer senden. </li><li>Botnachrichten können theoretisch Links zu Phishing- oder Malwarewebsites enthalten, aber Bots können von Benutzern, von Mandantenadministratoren oder global von Microsoft blockiert werden. </li><li>Ein Bot kann abrufen (und möglicherweise speichern) elementare Identitätsinformationen für die Teammitglieder, die, denen die app hinzugefügt wurde, oder für einzelne Benutzer in Gruppen- oder persönliche Chats. Um weitere Informationen zu diesen Benutzern zu erhalten, müssen den Robot Azure Active Directory (AD Azure) anmelden müssen. </li><li>Bots können die Liste der Kanäle in einem Team abrufen (und möglicherweise speichern). Diese Daten verlassen das Unternehmensnetzwerk. </li><li>Wenn eine Datei in einen Bot gesendet wird, verbleibt die Datei des Firmennetzwerks befinden. Senden und Empfangen von Dateien erfordert Benutzer Genehmigung für jede Datei. </li><li>Standardmäßig Bots haben nicht die Möglichkeit, die im Auftrag des Benutzers fungiert, aber Bots können Benutzer zur Anmeldung bei Fragen. Sobald der Benutzer anmeldet, wird der Bot ein Zugriffstoken haben, mit denen sie zusätzliche Aufgaben ausführen kann. Genau wie zusätzliche Dinge sind, hängt davon ab, den Robot und, in dem der Benutzer meldet sich: ein Bot ist eine Azure AD-app unter registriert <a href="https://apps.dev.microsoft.com/">https://apps.dev.microsoft.com/</a> und kann über einen eigenen Satz von Berechtigungen verfügen.</li><li>Bots werden informiert, wenn Benutzer in einem Team hinzugefügt oder gelöscht werden.</li><li>Bots werden keine IP-Adressen von Benutzern oder andere Verweisursprungsinformationen angezeigt. Alle Informationen stammen von Microsoft. (Es gibt eine Ausnahme: Wenn ein Bot eine eigene Anmeldung implementiert wird, sehen die Benutzeroberfläche Anmeldung Verweisursprungsinformationen und IP Adressen Benutzer.)</li><li>Messagingerweiterungen dagegen sehen die IP-Adressen der Benutzer und die Verweiserinformationen.</li><li>App-Richtlinien (und unsere Überprüfungsprozess Elemente verwenden) erfordern Ermessen Buchen der persönlichen Chatnachrichten für Benutzer (über die Berechtigung POST_MESSAGE_TEAM) für gültige Zwecke. Bei einem Missbrauch können Benutzer den Robot blockieren, Mandanten-Administratoren können die app blockieren und kann Microsoft Bots zentral blockieren, falls erforderlich.</li></ul></td>
</tr>
</tbody>
<tfoot>
<tr><td align="right"><sup>1</sup></td><td colspan="3">Einige Bots senden nur Nachrichten (POST_MESSAGE_USER). Sind sie "nur Benachrichtigung" Bots aufgerufen, aber der Begriff bezieht sich nicht auf welche ein Bot zugelassen oder Aktionen nicht zulässig ist, bedeutet dies, dass der Bot keine Gesprächs Erfahrung verfügbar machen möchten. Teams verwendet dieses Feld, um die Funktionalität in der Benutzeroberfläche deaktivieren, die normalerweise aktiviert werden; der Bot ist nicht eingeschränkt in was es dürfen hat im Vergleich zu Bots, die eine Gesprächs Erfahrung verfügbar machen.</td></tr>
<tr><td align="right"><sup>2</sup></td><td colspan="3">Zurzeit als Developer Preview verfügbar.</td></tr>
<tr><td align="right"><sup>3</sup></td><td colspan="3">Derzeit in der Vorschau für Entwickler. Unterliegt den <code>supportsFiles</code> boolesche Eigenschaft für das Bot-Objekt in der Datei manifest.json für die app.</td>
</tr>
</tfoot>
</table>

> [!Note]
> <ul><li>Wenn ein Bot über eine eigene Anmeldung verfügt, wird bei der ersten Anmeldung des Benutzers eine zweite – andere – Benutzeroberfläche für die Einwilligung verwendet.</li><li>Zurzeit sind die Azure AD-Berechtigungen, die den Funktionen innerhalb einer Microsoft Teams-App (Bot, Registerkarte, Connector oder Messagingerweiterung) zugeordnet sind, vollständig von den hier aufgeführten Microsoft Teams-Berechtigungen getrennt.</li></ul>


## <a name="tabs"></a>Registerkarten

Bei einer Registerkarte handelt es sich um eine in Microsoft Teams ausgeführte Website.

<table>
  <tr>
    <th width="25%">Erforderliche Berechtigungen</th>
    <th width="25%">Optionale Berechtigungen</th>
    <th width="50%">Überlegungen</th>
  </tr>
  <tr>
    <td valign="top">SEND_AND_RECEIVE_WEB_DATA</td>
    <td valign="top">Keine (zurzeit)</td>
    <td valign="top"><ul><li>Das Risikoprofil einer Registerkarte ist fast identisch mit dem der gleichen Website bei Ausführung in einer Browserregisterkarte. </li><li>Eine Registerkarte ruft auch den Kontext, in denen er ausgeführt wird, einschließlich des Namens der Anmeldung und UPN des aktuellen Benutzers, Azure AD-Objekt-ID für den aktuellen Benutzer, die ID des Office 365 Gruppe (Team), in dem es sich befindet, die Mandanten-ID und das aktuelle Gebietsschema des Benutzers, ab. Jedoch, um diese IDs Informationen eines Benutzers zuzuordnen, die Registerkarte müssten der Benutzer für die Anmeldung bei Azure AD tätigen.</li></ul></td>
  </tr>
  </table>

## <a name="connectors"></a>Connectors

Ein Connector stellt in einem Kanal Nachrichten bereit, wenn in einem externen System Ereignisse auftreten.

  <table>
  <tr>
    <th width="25%">Erforderliche Berechtigungen</th>
    <th width="25%">Optionale Berechtigungen</th>
    <th width="50%">Überlegungen</th>
  </tr>
  <tr>
    <td valign="top">POST_MESSAGE_CHANNEL</td>
    <td valign="top">REPLYTO_CONNECTOR_MESSAGE. Bestimmte Connectors unterstützen _bearbeitungsfähige Nachrichten_, die Benutzer gezielte Antworten auf die Nachricht Connector, beispielsweise durch Hinzufügen einer Antwort auf ein Problem GitHub oder Hinzufügen eines Datums zu einer Karte Trello buchen zulassen.</td>
    <td valign="top"><ul><li>Das System, das Connector Nachrichten übermittelt, die es buchen oder empfängt, die die Nachrichten weiß nicht: ist keine Informationen über den Empfänger anzugeben. (Microsoft ist der eigentliche Empfänger, nicht für den Mandanten. Microsoft ist der tatsächlichen Post an den Kanal.)</li><li>Wenn Connectornachrichten in einem Kanal bereitgestellt werden, verlassen keine Daten das Unternehmensnetzwerk.</li><li>Connectors, die Nachrichten mit ausführbaren Aktionen unterstützen (Berechtigung REPLYTO_CONNECTOR_MESSAGE), sehen auch keine IP-Adressen und Verweiserinformationen. Diese Informationen werden an Microsoft gesendet und dann an HTTP-Endpunkte weitergeleitet, die zuvor im Connectorportal bei Microsoft registriert wurden.</li><li>Jedes Mal, wenn ein Connector konfiguriert ist, wird für einen Kanal wird ein eindeutiger URL für diese Connectorinstanz erstellt. Wenn dieser Connector-Instanz gelöscht wird, kann die URL nicht mehr verwendet werden.</li><li>Connectornachrichten können keine Dateianlagen enthalten.</li><li>Connector-Instanz, die URL als Schlüssel/vertraulich behandelt werden sollte: jeder Benutzer mit, dass die URL, Nachrichten veröffentlichen kann wie eine e-Mail-Adresse. Aus diesem Grund besteht einige Risiko Spam oder Links zu Phishing oder Malware Websites. Würde, die auftreten, können Teams Besitzer die Connector-Instanz löschen.</li><li>Wenn der Dienst, der Connectornachrichten sendet, kompromittiert wird und Spam oder Phishing- bzw. Malwarelinks sendet, kann ein Mandantenadministrator die Erstellung neuer Connectorinstanzen verhindern. Außerdem kann Microsoft diese Instanzen zentral blockieren.</li></ul></td>
  </tr>
</table>

> [!Note]
> Zurzeit können Sie nicht wissen, welche Connectors Nachrichten mit ausführbaren Aktionen unterstützen (Berechtigung REPLYTO_CONNECTOR_MESSAGE).


## <a name="outgoing-webhooks"></a>Ausgehende Webhooks

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
    <td valign="top"><ul><li>Ausgehende Webhooks ähneln Bots, aber deshalb mit niedrigeren Berechtigungen haben. Sie müssen explizit, genau wie Bots angegeben werden.</li><li>Wenn eine ausgehende Webhook registriert ist, wird einen _geheimen Schlüssel_ generiert, sodass die ausgehende Webhook überprüfen, ob der Absender Microsoft-Teams, im Gegensatz zu einem Angreifer ist. Dieser Schlüssel sollte einen geheimen Schlüssel bleiben. Jeder Benutzer mit Zugriff auf die Datei kann Microsoft-Teams imitieren. Wenn der geheimen Schlüssel gefährdet ist, die ausgehende Webhook gelöscht und neu erstellt werden kann, und ein neuer geheimen Schlüssel generiert werden.</li><li>Es ist zwar möglich, einen ausgehenden Webhook zu erstellen, der das Geheimnis nicht validiert, aber wir raten davon ab.</li><li>Abgesehen vom Empfangen von Nachrichten und Antworten auf Nachrichten haben ausgehende Webhooks wenige Möglichkeiten: Sie können keine proaktiven Nachrichten senden und keine Dateien senden oder empfangen. Sie können keine anderen Aktionen ausführen, die Bots ausführen können, sondern nur Nachrichten empfangen und auf sie antworten.</li></ul></td>
  </tr>
</table>