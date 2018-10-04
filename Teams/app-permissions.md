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
ms.openlocfilehash: f3ea7aaa57f6784487d662174554ec0086a87346
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375748"
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
    <td valign="top" colspan="2"><ul><li>   RECEIVE_MESSAGE, REPLYTO_MESSAGE: Der Bot kann Nachrichten von Benutzern empfangen und auf diese antworten.<sup>1</sup></li><li>POST_MESSAGE_USER: Nachdem ein Benutzer eine Nachricht an einen Bot gesendet hat, kann der Bot jederzeit Direktnachrichten (die auch als <em>proaktive Nachrichten</em> bezeichnet werden) an den Benutzer senden.</li><li>GET_CHANNEL_LIST: Bots, die zu Teams hinzugefügt wurden, können eine Liste der Namen und IDs der Kanäle in einem Team abrufen.</li></ul></td>
    <td valign="top"><ul><li>IDENTITY: Wenn es & #39; s in einem Kanal, der app & #39; verwendete s Bots können grundlegende Identitätsinformationen Teammitglieder (Vorname, Nachname, User principal Name [, UPN], e-Mail-Adresse); zugreifen Wenn es & #39; s in einer persönlichen oder Gruppenchat, den Robot verwendet die gleiche Informationen für die Benutzer zugreifen kann.</li><li> POST_MESSAGE_TEAM: Ermöglicht eine app & #39; s Bots direkte (proaktive) Nachrichten an jedes Teammitglied zu einem beliebigen Zeitpunkt senden, selbst wenn der Benutzer hat den Robot vor nie Sprach.</li><li>Bei den folgenden Berechtigungen handelt es sich nicht um explizite Berechtigungen. Diese Berechtigungen werden durch RECEIVE_MESSAGE und REPLYTO_MESSAGE und durch die im Manifest deklarierten Bereiche, in denen die Bots verwendet werden, impliziert. <ul><li>RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL</li><li>RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT<sup>2</sup> </li><li>RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM</li></ul><li>SEND_FILES, RECEIVE_FILES:<sup>3</sup> Steuert, ob ein Bot in privaten Chats Dateien senden und empfangen kann. (Wird für Gruppen-Chats oder Kanäle noch nicht unterstützt.)</li></ul></td>
    <td valign="top"><ul><li>Bots haben nur Zugriff auf Teams, dem sie & #39; Ve wurden hinzugefügt oder für Benutzer, die sie installiert haben.</li><li>Bots empfangen von Nachrichten nur in dem sie & #39; Re erwähnten explizit durch Benutzer. Diese Daten verlassen das Unternehmensnetzwerk.</li><li>    Bots können nur Antworten auf Unterhaltungen, in dem sie & #39; Re erwähnten.</li><li>Nachdem ein Benutzer mit einem Bot, conversed hat, wenn der Bot diesen Benutzer & #39; speichert s-ID, sie können diesen Benutzer direkte Nachrichten senden können Sie jederzeit. </li><li>Botnachrichten können theoretisch Links zu Phishing- oder Malwarewebsites enthalten, aber Bots können von Benutzern, von Mandantenadministratoren oder global von Microsoft blockiert werden. </li><li>Ein Bot kann sehr einfache Identitätsinformationen der Teammitglieder, für die App hinzugefügt wurde, oder einzelner Benutzer in privaten Chats oder Gruppen-Chats abrufen (und möglicherweise speichern). Um weitere Informationen zu diesen Benutzern abzurufen, muss der Bot sie auffordern, sich bei Azure Active Directory (Azure AD) anzumelden. </li><li>Bots können die Liste der Kanäle in einem Team abrufen (und möglicherweise speichern). Diese Daten verlassen das Unternehmensnetzwerk. </li><li>Wenn eine Datei an einen Bot gesendet wird, verlässt sie das Unternehmensnetzwerk. Das Senden und Empfangen von Dateien muss vom Benutzer für jede einzelne Datei genehmigt werden. </li><li>Standard, Bots Don & #39; haben die Möglichkeit, die im Auftrag des Benutzers fungiert, aber Bots können fordern Sie Benutzer zur Anmeldung bei. Sobald der Benutzer anmeldet, wird der Bot ein Zugriffstoken haben, mit denen sie zusätzliche Aufgaben ausführen kann. Was genau diese weiteren Aktionen umfassen, hängt von dem Bot ab und davon, wo sich der Benutzer anmeldet: Ein Bot ist eine Azure AD-App, die unter <a href="https://apps.dev.microsoft.com/">https://apps.dev.microsoft.com/</a> registriert ist und über einen eigenen Berechtigungssatz verfügen kann.</li><li>Bots werden informiert, wenn Benutzer in einem Team hinzugefügt oder gelöscht werden.</li><li>Bots Don & #39; Siehe Benutzer t & #39; IP-Adressen oder andere Verweisursprungsinformationen. Alle Informationen stammen von Microsoft. (Es gibt eine Ausnahme: Wenn ein Bot eine eigene Anmeldung implementiert wird, sehen die Benutzeroberfläche Anmeldung Benutzer & #39; IP-Adressen und Verweisursprungsinformationen.)</li><li>Messaging-Erweiterungen, sehen andererseits, Benutzer & #39; IP-Adressen und Verweisursprungsinformationen.</li><li>App-Richtlinien (und unser AppSource-Überprüfungsprozess) schreiben Vorsicht beim Bereitstellen privater Chatnachrichten für Benutzer (über die Berechtigung POST_MESSAGE_TEAM) zu legitimen Zwecken vor. Im Fall eines Missbrauchs können Benutzer den Bot blockieren, Mandantenadministratoren können die App blockieren, und Microsoft kann Bots bei Bedarf zentral blockieren.</li></ul></td>
</tr>
</tbody>
<tfoot>
<tr><td align="right"><sup>1</sup></td><td colspan="3">Einige Bots senden nur Nachrichten (POST_MESSAGE_USER). Diese & #39; Re aufgerufen &quot;Benachrichtigung nur&quot; Bots, aber der Begriff & #39; t finden Sie unter welche ein Bot zugelassen oder Aktionen nicht zulässig ist, bedeutet das, dass die Bot & #39; t eine Gesprächs Erfahrung verfügbar machen möchten. Teams verwendet dieses Feld, um die Funktionalität in der Benutzeroberfläche deaktivieren, die normalerweise aktiviert werden; der Bot ist nicht & #39; t eingeschränkt in was es & #39; s dürfen im Vergleich zu Bots, die eine Gesprächs Erfahrung verfügbar machen.</td></tr>
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
    <td valign="top"><ul><li>Das Risikoprofil einer Registerkarte ist fast identisch mit dem der gleichen Website bei Ausführung in einer Browserregisterkarte. </li><li>Eine Registerkarte ruft auch den Kontext ab, in dem es & #39; s ausgeführt, den Anmeldenamen und UPN des aktuellen Benutzers, einschließlich der Azure AD-Objekt-ID für den aktuellen Benutzer, die die Office 365-Gruppe (Team) in der es sich befindet, die Mandanten-ID-ID , und das aktuelle Gebietsschema des Benutzers. Jedoch müsste zum Zuordnen dieser IDs, die ein Benutzer & #39; s Informationen, die Registerkarte der Benutzer für die Anmeldung bei Azure AD tätigen.</li></ul></td>
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
    <td valign="top">REPLYTO_CONNECTOR_MESSAGE: Bestimmte Connectors unterstützen <em>Nachrichten mit ausführbaren Aktionen</em>, bei denen Benutzer gezielte Antworten auf die Connectornachricht bereitstellen können, beispielsweise indem sie eine Antwort zu einem GitHub-Problem oder ein Datum zu einer Trello-Karte hinzufügen.</td>
    <td valign="top"><ul><li>Das System, die Beiträge Connector Nachrichten & #39; t wissen, wer es & #39; s bereitstellen in oder Empfänger der Meldung: ist keine Informationen über den Empfänger anzugeben. (Der eigentliche Empfänger ist Microsoft, nicht der Mandant. Die Nachricht wird tatsächlich von Microsoft im Kanal bereitgestellt.)</li><li>Wenn Connectornachrichten in einem Kanal bereitgestellt werden, verlassen keine Daten das Unternehmensnetzwerk.</li><li>Verbinder, die bearbeitungsfähige Nachrichten (REPLYTO_CONNECTOR_MESSAGE Berechtigung) auch Don & #39 unterstützen; t finden Sie unter IP-Adresse "und" Referenz Informationen; Diese Informationen sind an Microsoft gesendet, und klicken Sie dann auf HTTP-Endpunkte, die zuvor mit Microsoft im Portal Connectors registriert wurden weitergeleitet.</li><li>Immer wenn ein Connector für einen Kanal konfiguriert wird, wird eine eindeutige URL für diese Connectorinstanz erstellt. Wenn diese Connectorinstanz gelöscht wird, kann die URL nicht mehr verwendet werden.</li><li>Connector Nachrichten können & #39; t Dateianlagen enthalten.</li><li>Die URL der Connectorinstanz sollte als geheim/vertraulich behandelt werden: Jeder, der die URL kennt, kann etwas unter der URL bereitstellen (wie bei einer E-Mail-Adresse). Aus diesem Grund es & #39; s Risiko einer Spam oder Links zu Phishing oder Malware Websites. In diesem Fall können Teambesitzer die Connectorinstanz löschen.</li><li>Wenn der Dienst, der Connectornachrichten sendet, kompromittiert wird und Spam oder Phishing- bzw. Malwarelinks sendet, kann ein Mandantenadministrator die Erstellung neuer Connectorinstanzen verhindern. Außerdem kann Microsoft diese Instanzen zentral blockieren.</li></ul></td>
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
    <td valign="top"><ul><li>Ausgehende Webhooks sind mit Bots vergleichbar, verfügen aber über weniger Berechtigungen. Sie müssen, genau wie Bots, explizit erwähnt werden.</li><li>Bei der Registrierung eines ausgehenden Webhooks wird ein <em>Geheimnis</em> generiert, mit dessen Hilfe der ausgehende Webhook verifizieren kann, dass Microsoft Teams und nicht ein böswilliger Angreifer der Absender ist. Dieses Geheimnis sollte geheim bleiben, da jeder, der Zugriff darauf hat, die Identität von Microsoft Teams annehmen kann. Wenn das Geheimnis kompromittiert ist, kann der ausgehende Webhook gelöscht und erneut erstellt werden. Dann wird ein neues Geheimnis generiert.</li><li>Obwohl es & #39; s möglich, erstellen eine ausgehende Webhook, & #39; t den geheimen Schlüssel, es wird empfohlen, ihn zu überprüfen.</li><li>Als empfangen und Beantworten von Nachrichten, ausgehende Webhooks kann & #39; nicht viel t: sie können & #39; t proaktiv Senden von Nachrichten, sie können & #39; t senden oder Empfangen von Dateien, sie können & #39; sonst noch etwas Möglichkeiten, die Bots empfangen und Beantworten von außer können t Nachrichten.</li></ul></td>
  </tr>
</table>