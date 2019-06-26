---
title: Berechtigungen für Microsoft Teams-Apps und Überlegungen dazu
author: rmw2890
ms.author: rowille
manager: serdars
ms.date: 10/18/2018
ms.topic: conceptual
ms.service: msteams
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
search.appverid: MET150
ms.reviewer: rowille
description: Hier erfahren Sie, welche Daten und Berechtigungen Apps von Ihrer Organisation anfordern.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 598fd2d9dc8c8942a2d82e136c8367afa4d8495e
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221945"
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

<table>
  <tr>
    <th width="25%">Erforderliche Berechtigungen</th>
    <th width="25%">Optionale Berechtigungen</th>
    <th width="50%">Überlegungen</th>
  </tr>
  <tr>
    <td valign="top">Keine</td>
    <td valign="top">Keine</td>
    <td valign="top">Eine APP muss offen legen, welche Daten Sie verwendet und wofür die Daten in den Nutzungsbedingungen und den Datenschutzrichtlinien Links verwendet werden.</td>
  </tr>
</table>

## <a name="bots-and-messaging-extensions"></a>Bots und Messaging-Erweiterungen

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
    <td valign="top" colspan="2"><ul><li>   RECEIVE_MESSAGE, REPLYTO_MESSAGE. Der Bot kann Nachrichten von Benutzern empfangen und darauf antworten. <sup>1</sup></li><li>POST_MESSAGE_USER. Nachdem ein Nutzer eine Nachricht an einen bot gesendet hat, kann der bot den Nutzern direkte Nachrichten (auch als <em>proaktive Nachrichten</em>bezeichnet) zu einem beliebigen Zeitpunkt senden.</li><li>GET_CHANNEL_LIST. Bots, die zu Teams hinzugefügt wurden, können eine Liste mit Namen und IDs der Kanäle in einem Team erhalten.</li></ul></td>
    <td valign="top"><ul><li>Identität. Wenn&#39;s in einem Kanal verwendet wird, können die APP-&#39;s-Bots auf grundlegende Identitätsinformationen von Teammitgliedern zugreifen (Vorname, Nachname, Benutzerprinzipalname [UPN], e-Mail-Adresse). Wenn es in einem persönlichen oder Gruppen-Chat verwendet&#39;, kann der bot für diese Benutzer auf dieselben Informationen zugreifen.</li><li> POST_MESSAGE_TEAM. Ermöglicht es einem App-&#39;-Bots, direkte (proaktive) Nachrichten an ein beliebiges Teammitglied zu senden, auch wenn der Benutzer noch nie zuvor mit dem bot gesprochen hat.</li><li>Die folgenden sind keine expliziten Berechtigungen, sondern werden von RECEIVE_MESSAGE und REPLYTO_MESSAGE und den Bereichen impliziert, in denen die Bots verwendet werden können, die im Manifest deklariert werden: <ul><li>RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL</li><li>RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT</li><li>RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM</li></ul><li>SEND_FILES, RECEIVE_FILES. <sup>2</sup> steuert, ob ein bot Dateien im persönlichen Chat senden und empfangen kann (noch nicht für Gruppen-Chats oder Kanäle unterstützt).</li></ul></td>
    <td valign="top"><ul><li>Bots haben nur Zugriff auf Teams, denen Sie&#39;ve hinzugefügt wurden, oder an Benutzer, die Sie installiert haben.</li><li>Bots empfangen nur Nachrichten, in denen Sie von Benutzern ausdrücklich erwähnt&#39;. Diese Daten verlassen das Unternehmensnetzwerk.</li><li>    Bots können nur auf Unterhaltungen Antworten, in denen Sie&#39;wieder erwähnt werden.</li><li>Nachdem ein Nutzer sich mit einem bot unterhalten hat, kann er, wenn der bot diesen Nutzer&#39;s-ID speichert, ihm direkt Nachrichten senden. </li><li>Es ist theoretisch möglich, dass bot-Nachrichten Links zu Phishing-oder Malware-Websites enthalten, aber Bots können vom Benutzer, dem mandantenadministrator oder Global von Microsoft blockiert werden. </li><li>Ein Bot kann sehr einfache Identitätsinformationen für die Teammitglieder, denen die app hinzugefügt wurde, oder für einzelne Benutzer in persönlichen oder Gruppen-Chats abrufen (und möglicherweise speichern). Um weitere Informationen zu diesen Benutzern zu erhalten, muss der bot die Anmeldung bei Azure Active Directory (Azure AD) anfordern. </li><li>Bots können die Liste der Kanäle in einem Team abrufen (und möglicherweise speichern). Diese Daten verlassen das Unternehmensnetzwerk. </li><li>Wenn eine Datei an einen bot gesendet wird, verlässt die Datei das Unternehmensnetzwerk. Für das Senden und empfangen von Dateien ist die Benutzergenehmigung für jede Datei erforderlich. </li><li>Standardmäßig haben&#39;Bots keine Möglichkeit, im Namen des Benutzers zu agieren, aber Bots können die Nutzer bitten, sich anzumelden. Sobald sich der Benutzer anmeldet, verfügt der bot über ein Zugriffstoken, mit dem er zusätzliche Aufgaben ausführen kann. Genau das, was diese zusätzlichen Dinge sind, hängt vom bot ab und von der Stelle, an der sich der Benutzer anmeldet: <a href="https://apps.dev.microsoft.com/">https://apps.dev.microsoft.com/</a> ein Bot ist eine Azure AD-App, die bei registriert ist und über einen eigenen Satz von Berechtigungen verfügen kann.</li><li>Bots werden benachrichtigt, wenn Benutzer zu einem Team hinzugefügt oder daraus gelöscht werden.</li><li>Bots Don&#39;t sehen Nutzer&#39; IP-Adressen oder andere Referrer-Informationen. Alle Informationen stammen von Microsoft. (Es gibt eine Ausnahme: Wenn ein bot seine eigene Anmelde Erfahrung implementiert, werden auf der Anmelde-UI Benutzer&#39; IP-Adressen und Verweisinformationen angezeigt.)</li><li>Messaging-Erweiterungen hingegen sehen Benutzer&#39; IP-Adressen und Verweisinformationen.</li><li>App-Richtlinien (und unser AppSource-Überprüfungsprozess) erfordern Diskretion beim Posten persönlicher Chatnachrichten an Benutzer (über die POST_MESSAGE_TEAM-Berechtigung) für gültige Zwecke. Im Fall von Missbrauch können Benutzer den bot blockieren, mandantenadministratoren können die APP blockieren, und Microsoft kann Bots bei Bedarf zentral blockieren.</li></ul></td>
</tr>
</tbody>
<tfoot>
<tr><td align="right"><sup>1</sup></td><td colspan="3">Einige Bots senden nur Nachrichten (POST_MESSAGE_USER). Sie&#39;erneut als &quot;"Benachrichtigungs&quot; -Bots" bezeichnet, aber der Begriff doesn 't&#39;t bezieht sich darauf, was ein bot erlaubt oder nicht erlaubt, bedeutet dies, dass der #d2 bot keine Konversations Erfahrung machen möchte. Teams verwendet dieses Feld, um Funktionen in der UI zu deaktivieren, die normalerweise aktiviert werden. der bot isn&#39;t in dem eingeschränkt, was es&#39;erlaubt ist, im Vergleich zu Bots zu tun, die eine Konversations Erfahrung aufdecken.</td></tr>
<tr><td align="right"><sup>2</sup></td><td colspan="3">Unterliegt der <code>supportsFiles</code> booleschen Eigenschaft des bot-Objekts in der Manifest. JSON-Datei für die app.</td>
</tr>
</tfoot>
</table>

> [!Note]
> <ul><li>Wenn ein bot eine eigene Anmeldung hat, gibt es eine zweite – anders – Zustimmungs Erfahrung, wenn sich der Benutzer zum ersten Mal anmeldet.</li><li>Derzeit sind die Azure AD-Berechtigungen, die einer der Funktionen in einer Teams-app (bot-, Tab-, Connector-oder Messaging-Erweiterung) zugeordnet sind, vollständig von den hier aufgelisteten Teams-Berechtigungen getrennt.</li></ul>


## <a name="tabs"></a>Registerkarten

Eine Registerkarte ist eine Website, die innerhalb von Teams ausgeführt wird.

<table>
  <tr>
    <th width="25%">Erforderliche Berechtigungen</th>
    <th width="25%">Optionale Berechtigungen</th>
    <th width="50%">Überlegungen</th>
  </tr>
  <tr>
    <td valign="top">SEND_AND_RECEIVE_WEB_DATA</td>
    <td valign="top">Keine (derzeit).</td>
    <td valign="top"><ul><li>Das Risikoprofil einer Registerkarte ist nahezu identisch mit der Website, die auf einer Browserregister Karte ausgeführt wird. </li><li>Eine Registerkarte ruft auch den Kontext ab, in dem&#39;Sie ausgeführt wird, einschließlich des Anmeldenamens und des UPN des aktuellen Benutzers, der Azure AD-Objekt-ID für den aktuellen Benutzer, der ID der Office 365-Gruppe, in der Sie sich befindet (sofern es sich um ein Team handelt). , die Mandanten-ID und das aktuelle Gebietsschema des Benutzers. Um diese IDs aber den Informationen eines Benutzers zuzuordnen, muss sich der Benutzer auf der Registerkarte bei Azure AD anmelden&#39;.</li></ul></td>
  </tr>
  </table>

## <a name="connectors"></a>Verbinder

Ein Connector Bucht Nachrichten in einem Kanal, wenn Ereignisse in einem externen System auftreten.

  <table>
  <tr>
    <th width="25%">Erforderliche Berechtigungen</th>
    <th width="25%">Optionale Berechtigungen</th>
    <th width="50%">Überlegungen</th>
  </tr>
  <tr>
    <td valign="top">POST_MESSAGE_CHANNEL</td>
    <td valign="top">REPLYTO_CONNECTOR_MESSAGE. Bestimmte Connectors unterstützen <em>umsetzbare Nachrichten</em>, mit denen Benutzer gezielte Antworten auf die Connector-Nachricht senden können, beispielsweisedurch Hinzufügen einer Antwort auf ein GitHub-Problem oder durch Hinzufügen eines Datums zu einer Trello-Karte.</td>
    <td valign="top"><ul><li>Das System, das Connector-Nachrichten Bucht, weiß nicht&#39;, wem es&#39;, oder wer die Nachrichten erhält: Es werden keine Informationen über den Empfänger veröffentlicht. (Microsoft ist der tatsächliche Empfänger, nicht der Mandant; Microsoft führt den eigentlichen Beitrag für den Kanal aus.)</li><li>Keine Daten verlassen das Unternehmensnetzwerk, wenn Connector-Nachrichten in einem Kanal bereitgestellt werden.</li><li>Connectors, die umsetzbare Nachrichten (REPLYTO_CONNECTOR_MESSAGE-Berechtigung) unterstützen, werden auch&#39;t IP-Adresse und Verweisinformationen angezeigt. Diese Informationen werden an Microsoft gesendet und dann an HTTP-Endpunkte weitergeleitet, die zuvor bei Microsoft im Connectors-Portal registriert wurden.</li><li>Jedes Mal, wenn ein Connector für einen Kanal konfiguriert ist, wird eine eindeutige URL für diese Connector-Instanz erstellt. Wenn diese Connector-Instanz gelöscht wird, kann die URL nicht mehr verwendet werden.</li><li>Connector-Nachrichten können&#39;t Dateianlagen enthalten.</li><li>Die URL der Connector-Instanz sollte als geheim/vertraulich behandelt werden: jede Person, die über diese URL verfügt, kann Sie wie eine e-Mail-Adresse Posten. Daher&#39;ein gewisses Risiko von Spam oder Links zu Phishing-oder Malware-Websites. In diesem Fall können Teambesitzer die Connector-Instanz löschen.</li><li>Wenn der Dienst, der Connector-Nachrichten sendet, kompromittiert wurde und mit dem Senden von Spam/Phishing/Malware-Links beginnt, kann ein mandantenadministrator verhindern, dass neue Connector-Instanzen erstellt werden, und Microsoft kann Sie zentral blockieren.</li></ul></td>
  </tr>
</table>

> [!Note]
> Es ist derzeit nicht möglich zu wissen, welche Connectors umsetzbare Nachrichten (REPLYTO_CONNECTOR_MESSAGE-Berechtigung) unterstützen.


## <a name="outgoing-webhooks"></a>Ausgehende webhooks

_Ausgehende_ webhooks werden von Teambesitzern oder Teammitgliedern dynamisch erstellt, wenn Sideloading für einen Mandanten aktiviert ist. Sie sind keine Funktionen von Teams-apps; Diese Informationen sind zur Vollständigkeit enthalten.

<table>
  <tr>
    <th width="25%">Erforderliche Berechtigungen</th>
    <th width="25%">Optionale Berechtigungen</th>
    <th width="50%">Überlegungen</th>
  </tr>
    <tr>
    <td valign="top">RECEIVE_MESSAGE, REPLYTO_MESSAGE. Kann Nachrichten von Benutzern empfangen und darauf antworten.</td>
    <td valign="top">Keine</td>
    <td valign="top"><ul><li>Ausgehende webhooks ähneln Bots, haben aber weniger Privilegien. Sie müssen ausdrücklich erwähnt werden, genau wie Bots.</li><li>Beim Registrieren eines ausgehenden webhooks wird ein geheimer <em>Schlüssel</em> generiert, der dem ausgehenden webhook ermöglicht, zu überprüfen, ob der Absender Microsoft Teams im Gegensatz zu einem böswilligen Angreifer ist. Dieses Geheimnis sollte geheim bleiben; Jeder Benutzer, der Zugriff darauf hat, kann die Identität von Microsoft Teams einsehen. Wenn das Geheimnis beeinträchtigt wird, kann der ausgehende webhook gelöscht und neu erstellt werden, und es wird ein neuer Schlüssel generiert.</li><li>Obwohl es&#39;möglich ist, einen ausgehenden webhook zu erstellen, der den geheimen Schlüssel nicht überprüft&#39;, empfehlen wir dagegen.</li><li>Anders als das empfangen und beantworten von Nachrichten können ausgehende webhooks&#39;t viel tun: Sie können&#39;t proaktiv Nachrichten senden, Sie können&#39;t Dateien senden oder empfangen, Sie können&#39;t alles andere tun, was Bots tun können, außer empfangen und beantworten von Nachrichten.</li></ul></td>
  </tr>
</table>
