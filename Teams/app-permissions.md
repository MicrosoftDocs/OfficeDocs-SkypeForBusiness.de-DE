---
title: Berechtigungen für Microsoft Teams-Apps und Überlegungen dazu
author: Lester-Hewett
ms.author: lehewe
manager: serdars
ms.date: 08/20/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: lehewe
description: Hier erfahren Sie, welche Daten und Berechtigungen Apps von Ihrer Organisation anfordern.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: eb8a6b6785e3cc4bcbf65bceeb51bf650b63a830
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23883066"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a>Berechtigungen für Microsoft Teams-Apps und Überlegungen dazu

Microsoft Teams-Apps stellen eine Möglichkeit dar, eine oder mehrere Funktionen in einem _App-Paket_ zu aggregieren, das installiert, aktualisiert und deinstalliert werden kann. Zu diesen Funktionen gehören folgende:

-   Bots
-   Messagingerweiterungen
-   Registerkarten
-   Connectors

Apps benötigen Einwilligungen der Benutzer und werden im Hinblick auf Richtlinien von der IT verwaltet. Größtenteils werden die Berechtigungen und Risikoprofile von Apps jedoch durch die Berechtigungen und Risikoprofile der jeweils enthaltenen Funktionen definiert. Daher konzentriert sich dieser Artikel auf Berechtigungen und Überlegungen auf Funktionsebene.

Die unten in Großbuchstaben aufgeführten Berechtigungen, zum Beispiel RECEIVE_MESSAGE und REPLYTO_MESSAGE, werden in der [Entwicklerdokumentation für Microsoft Teams](https://aka.ms/teamsdevdocs) oder den [Berechtigungen für Microsoft Graph](https://developer.microsoft.com/graph/docs/concepts/permissions_reference) nicht erwähnt. Es handelt sich einfach um eine nur in diesem Artikel verwendete beschreibende Kurzschreibweise.


|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>Entscheidungspunkt|<ul><li>Verwenden Sie die folgenden Tabellen als Verständnishilfe für die Berechtigungen, die von Ihnen untersuchten Apps anfordern.</li></ul> |
| ![](media/audio_conferencing_image9.png)<br/>Nächster Schritt|<ul><li>Untersuchen Sie die App oder den Dienst selbst, um zu entscheiden, ob Sie den Zugriff innerhalb der Organisation zulassen möchten. Bots zum Beispiel senden Nachrichten an Benutzer und empfangen Nachrichten von diesen. Sie befinden sich – mit Ausnahme von branchenspezifischen Bots in Unternehmen – jenseits der Compliancegrenze. Daher benötigen alle Apps, die Bots enthalten, mindestens die jeweiligen Berechtigungen, und sie weisen ein entsprechendes Risikoprofil auf. </li></ul>|

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
    <td valign="top" colspan="2"><ul><li>   RECEIVE_MESSAGE, REPLYTO_MESSAGE: Der Bot kann Nachrichten von Benutzern empfangen und auf diese antworten.<sup>1</sup></li><li>POST_MESSAGE_USER: Nachdem ein Benutzer eine Nachricht an einen Bot gesendet hat, kann der Bot jederzeit Direktnachrichten (die auch als _proaktive Nachrichten_ bezeichnet werden) an den Benutzer senden.</li><li>GET_CHANNEL_LIST: Bots, die zu Teams hinzugefügt wurden, können eine Liste der Namen und IDs der Kanäle in einem Team abrufen.</li></ul></td>
    <td valign="top"><ul><li>IDENTITY: Wenn diese Berechtigung in einem Kanal verwendet wird, können die Bots der App auf grundlegende Identitätsinformationen von Teammitgliedern zugreifen (Vorname, Nachname, Benutzerprinzipalname (User Principal Name, UPN), E-Mail-Adresse). Wenn die Berechtigung in einem privaten Chat oder Gruppen-Chat verwendet wird, kann der Bot auf die gleichen Informationen dieser Benutzer zugreifen.</li><li> POST_MESSAGE_TEAM: Ermöglicht den Bots einer App jederzeit das Senden von Direktnachrichten (proaktiven Nachrichten) an Teammitglieder, auch wenn sich der jeweilige Benutzer noch nie mit dem Bot unterhalten hat.</li><li>Bei den folgenden Berechtigungen handelt es sich nicht um explizite Berechtigungen. Diese Berechtigungen werden durch RECEIVE_MESSAGE und REPLYTO_MESSAGE und durch die im Manifest deklarierten Bereiche, in denen die Bots verwendet werden, impliziert. <ul><li>RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL</li><li>RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT<sup>2</sup> </li><li>RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM</li></ul><li>SEND_FILES, RECEIVE_FILES:<sup>3</sup> Steuert, ob ein Bot in privaten Chats Dateien senden und empfangen kann. (Wird für Gruppen-Chats oder Kanäle noch nicht unterstützt.)</li></ul></td>
    <td valign="top"><ul><li>Bots haben nur Zugriff auf Teams, zu denen sie hinzugefügt wurden, oder auf Benutzer, von denen sie installiert wurden.</li><li>Bots empfangen nur Nachrichten, in denen sie explizit von Benutzern erwähnt wurden. Diese Daten verlassen das Unternehmensnetzwerk.</li><li>    Bots können nur in Unterhaltungen antworten, in denen sie erwähnt wurden.</li><li>Wenn sich ein Benutzer mit einem Bot unterhalten hat und der Bot die ID des Benutzers gespeichert hat, kann der Bot jederzeit Direktnachrichten an diesen Benutzer senden. </li><li>Botnachrichten können theoretisch Links zu Phishing- oder Malwarewebsites enthalten, aber Bots können von Benutzern, von Mandantenadministratoren oder global von Microsoft blockiert werden. </li><li>Ein Bot kann sehr einfache Identitätsinformationen der Teammitglieder, für die App hinzugefügt wurde, oder einzelner Benutzer in privaten Chats oder Gruppen-Chats abrufen (und möglicherweise speichern). Um weitere Informationen zu diesen Benutzern abzurufen, muss der Bot sie auffordern, sich bei Azure Active Directory (Azure AD) anzumelden. </li><li>Bots können die Liste der Kanäle in einem Team abrufen (und möglicherweise speichern). Diese Daten verlassen das Unternehmensnetzwerk. </li><li>Wenn eine Datei an einen Bot gesendet wird, verlässt sie das Unternehmensnetzwerk. Das Senden und Empfangen von Dateien muss vom Benutzer für jede einzelne Datei genehmigt werden. </li><li>Bots können standardmäßig keine Aktionen im Namen von Benutzern ausführen, aber sie können Benutzer auffordern, sich anzumelden. Sobald sich der Benutzer angemeldet hat, verfügt der Bot über ein Zugriffstoken, das ihm weitere Aktionen ermöglicht. Was genau diese weiteren Aktionen umfassen, hängt von dem Bot ab und davon, wo sich der Benutzer anmeldet: Ein Bot ist eine Azure AD-App, die unter <a href="https://apps.dev.microsoft.com/">https://apps.dev.microsoft.com/</a> registriert ist und über einen eigenen Berechtigungssatz verfügen kann.</li><li>Bots werden informiert, wenn Benutzer in einem Team hinzugefügt oder gelöscht werden.</li><li>Bots sehen weder IP-Adressen von Benutzern noch andere Verweiserinformationen. Alle Informationen stammen von Microsoft. (Dabei gibt es eine Ausnahme: Wenn ein Bot eine eigene Benutzeroberfläche für Anmeldungen implementiert, sieht diese Benutzeroberfläche die IP-Adressen der Benutzer und die Verweiserinformationen.)</li><li>Messagingerweiterungen dagegen sehen die IP-Adressen der Benutzer und die Verweiserinformationen.</li><li>App-Richtlinien (und unser AppSource-Überprüfungsprozess) schreiben Vorsicht beim Bereitstellen privater Chatnachrichten für Benutzer (über die Berechtigung POST_MESSAGE_TEAM) zu legitimen Zwecken vor. Im Fall eines Missbrauchs können Benutzer den Bot blockieren, Mandantenadministratoren können die App blockieren, und Microsoft kann Bots bei Bedarf zentral blockieren.</li></ul></td>
</tr>
</tbody>
<tfoot>
<tr><td align="right"><sup>1</sup></td><td colspan="3">Einige Bots senden nur Nachrichten (POST_MESSAGE_USER). Sie werden als „reine Benachrichtigungsbots“ bezeichnet. Aus diesem Begriff geht jedoch nicht hervor, welche Aktionen ein Bot ausführen bzw. nicht ausführen darf. Er bedeutet, dass der Bot keine Unterhaltungsfunktionen verfügbar macht. Microsoft Teams verwendet dieses Feld, um Funktionen auf der Benutzeroberfläche zu deaktivieren, die normalerweise aktiviert wären. Die Aktionen des Bots werden gegenüber denen von Bots mit Unterhaltungsfunktionen nicht eingeschränkt.</td></tr>
<tr><td align="right"><sup>2</sup></td><td colspan="3">Zurzeit als Developer Preview verfügbar.</td></tr>
<tr><td align="right"><sup>3</sup></td><td colspan="3">Zurzeit als Developer Preview verfügbar. Wird gesteuert durch die boolesche Eigenschaft <code>supportsFiles</code> des Botobjekts in der Datei „manifest.json“ für die App.</td>
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
    <td valign="top"><ul><li>Das Risikoprofil einer Registerkarte ist fast identisch mit dem der gleichen Website bei Ausführung in einer Browserregisterkarte. </li><li>Eine Registerkarte ruft außerdem den Kontext ab, in dem sie ausgeführt wird, unter anderem den Anmeldenamen und den UPN des aktuellen Benutzers, die Objekt-ID von Azure AD für den aktuellen Benutzer, die ID der Office 365-Gruppe (Team), in der sich die Registerkarte befindet, die Mandanten-ID und das aktuelle Gebietsschema des Benutzers. Um diese IDs jedoch den Informationen eines Benutzers zuzuordnen, müsste die Registerkarte den Benutzer zur Anmeldung bei Azure AD veranlassen.</li></ul></td>
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
    <td valign="top">REPLYTO_CONNECTOR_MESSAGE: Bestimmte Connectors unterstützen _Nachrichten mit ausführbaren Aktionen_, bei denen Benutzer gezielte Antworten auf die Connectornachricht bereitstellen können, beispielsweise indem sie eine Antwort zu einem GitHub-Problem oder ein Datum zu einer Trello-Karte hinzufügen.</td>
    <td valign="top"><ul><li>Das System, das Connectornachrichten bereitstellt, weiß nicht, für wen die Nachricht bereitgestellt wird oder wer die Nachrichten empfängt: Es werden keine Informationen zum Empfänger offengelegt. (Der eigentliche Empfänger ist Microsoft, nicht der Mandant. Die Nachricht wird tatsächlich von Microsoft im Kanal bereitgestellt.)</li><li>Wenn Connectornachrichten in einem Kanal bereitgestellt werden, verlassen keine Daten das Unternehmensnetzwerk.</li><li>Connectors, die Nachrichten mit ausführbaren Aktionen unterstützen (Berechtigung REPLYTO_CONNECTOR_MESSAGE), sehen auch keine IP-Adressen und Verweiserinformationen. Diese Informationen werden an Microsoft gesendet und dann an HTTP-Endpunkte weitergeleitet, die zuvor im Connectorportal bei Microsoft registriert wurden.</li><li>Immer wenn ein Connector für einen Kanal konfiguriert wird, wird eine eindeutige URL für diese Connectorinstanz erstellt. Wenn diese Connectorinstanz gelöscht wird, kann die URL nicht mehr verwendet werden.</li><li>Connectornachrichten können keine Dateianlagen enthalten.</li><li>Die URL der Connectorinstanz sollte als geheim/vertraulich behandelt werden: Jeder, der die URL kennt, kann etwas unter der URL bereitstellen (wie bei einer E-Mail-Adresse). Daher besteht ein gewisses Risiko durch Spam oder Links zu Phishing- oder Malwarewebsites. In diesem Fall können Teambesitzer die Connectorinstanz löschen.</li><li>Wenn der Dienst, der Connectornachrichten sendet, kompromittiert wird und Spam oder Phishing- bzw. Malwarelinks sendet, kann ein Mandantenadministrator die Erstellung neuer Connectorinstanzen verhindern. Außerdem kann Microsoft diese Instanzen zentral blockieren.</li></ul></td>
  </tr>
</table>

> [!Note]
> Zurzeit können Sie nicht wissen, welche Connectors Nachrichten mit ausführbaren Aktionen unterstützen (Berechtigung REPLYTO_CONNECTOR_MESSAGE).


## <a name="outgoing-webhooks"></a>Ausgehende Webhooks

_Ausgehende Webhooks_ werden von Teambesitzern oder Teammitgliedern spontan erstellt, wenn Querladen für einen Mandanten aktiviert ist. Es handelt sich dabei nicht um Funktionen von Microsoft Teams-Apps. Diese Informationen sind der Vollständigkeit halber enthalten.

<table>
  <tr>
    <th width="25%">Erforderliche Berechtigungen</th>
    <th width="25%">Optionale Berechtigungen</th>
    <th width="50%">Überlegungen</th>
  </tr>
    <tr>
    <td valign="top">RECEIVE_MESSAGE, REPLYTO_MESSAGE: Der ausgehende Webhook kann Nachrichten von Benutzern empfangen und auf diese antworten.</td>
    <td valign="top">Keine</td>
    <td valign="top"><ul><li>Ausgehende Webhooks sind mit Bots vergleichbar, verfügen aber über weniger Berechtigungen. Sie müssen, genau wie Bots, explizit erwähnt werden.</li><li>Bei der Registrierung eines ausgehenden Webhooks wird ein _Geheimnis_ generiert, mit dessen Hilfe der ausgehende Webhook verifizieren kann, dass Microsoft Teams und nicht ein böswilliger Angreifer der Absender ist. Dieses Geheimnis sollte geheim bleiben, da jeder, der Zugriff darauf hat, die Identität von Microsoft Teams annehmen kann. Wenn das Geheimnis kompromittiert ist, kann der ausgehende Webhook gelöscht und erneut erstellt werden. Dann wird ein neues Geheimnis generiert.</li><li>Es ist zwar möglich, einen ausgehenden Webhook zu erstellen, der das Geheimnis nicht validiert, aber wir raten davon ab.</li><li>Abgesehen vom Empfangen von Nachrichten und Antworten auf Nachrichten haben ausgehende Webhooks wenige Möglichkeiten: Sie können keine proaktiven Nachrichten senden und keine Dateien senden oder empfangen. Sie können keine anderen Aktionen ausführen, die Bots ausführen können, sondern nur Nachrichten empfangen und auf sie antworten.</li></ul></td>
  </tr>
</table>