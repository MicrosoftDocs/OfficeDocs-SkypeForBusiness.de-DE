---
title: Berechtigungen für Microsoft Teams-Apps und Überlegungen dazu
author: Lester-Hewett
ms.author: lehewe
manager: serdars
ms.date: 10/18/2018
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_PracticalGuidance
search.appverid: MET150
ms.reviewer: lehewe
description: Hier erfahren Sie, welche Daten und Berechtigungen Apps von Ihrer Organisation anfordern.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 39c104d10e14e602da21761667312a917d9a9ce0
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295767"
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
<tr><td align="right"><sup>3</sup></td><td colspan="3">Unterliegt den <code>supportsFiles</code> boolesche Eigenschaft für das Bot-Objekt in der Datei manifest.json für die app.</td>
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
    <td valign="top"><ul><li>Das Risikoprofil für eine Registerkarte ist nahezu identisch, die gleichen Website in einer Registerkarte Browser ausgeführt. </li><li>Eine Registerkarte ruft auch den Kontext ab, in dem er & #39; s ausgeführt, den Anmeldenamen und UPN des aktuellen Benutzers, einschließlich der Azure AD-Objekt-ID für den aktuellen Benutzer, die ID der Office 365 Gruppe in der sich befindet (wenn es sich um ein Team ist) , die Mandanten-ID und das aktuelle Gebietsschema des Benutzers. Jedoch müsste zum Zuordnen dieser IDs, die ein Benutzer & #39; s Informationen, die Registerkarte der Benutzer für die Anmeldung bei Azure AD tätigen.</li></ul></td>
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
    <td valign="top">REPLYTO_CONNECTOR_MESSAGE. Bestimmte Connectors unterstützen <em>bearbeitungsfähige Nachrichten</em>, die Benutzer gezielte Antworten auf die Nachricht Connector, beispielsweise durch Hinzufügen einer Antwort auf ein Problem GitHub oder Hinzufügen eines Datums zu einer Karte Trello buchen zulassen.</td>
    <td valign="top"><ul><li>Das System, die Beiträge Connector Nachrichten & #39; t wissen, wer es & #39; s bereitstellen in oder Empfänger der Meldung: ist keine Informationen über den Empfänger anzugeben. (Microsoft ist der eigentliche Empfänger, nicht für den Mandanten. Microsoft ist der tatsächlichen Post an den Kanal.)</li><li>Keine Daten verlässt des Firmennetzwerks befinden, wenn Connector Nachrichten an einen Kanal veröffentlicht wurden.</li><li>Verbinder, die bearbeitungsfähige Nachrichten (REPLYTO_CONNECTOR_MESSAGE Berechtigung) auch Don & #39 unterstützen; t finden Sie unter IP-Adresse "und" Referenz Informationen; Diese Informationen sind an Microsoft gesendet, und klicken Sie dann auf HTTP-Endpunkte, die zuvor mit Microsoft im Portal Connectors registriert wurden weitergeleitet.</li><li>Jedes Mal, wenn ein Connector konfiguriert ist, wird für einen Kanal wird ein eindeutiger URL für diese Connectorinstanz erstellt. Wenn dieser Connector-Instanz gelöscht wird, kann die URL nicht mehr verwendet werden.</li><li>Connector Nachrichten können & #39; t Dateianlagen enthalten.</li><li>Connector-Instanz, die URL als Schlüssel/vertraulich behandelt werden sollte: jeder Benutzer mit, dass die URL, Nachrichten veröffentlichen kann wie eine e-Mail-Adresse. Aus diesem Grund es & #39; s Risiko einer Spam oder Links zu Phishing oder Malware Websites. Würde, die auftreten, können Teams Besitzer die Connector-Instanz löschen.</li><li>Wenn der Dienst, der Connector Nachrichten waren so gefährdet werden, und starten Sie senden von Spam/Phishing/Malware Links sendet, mandantenadministrator kann verhindern, dass neue Connectorinstanzen erstellt wird und Microsoft können sie zentral blockieren.</li></ul></td>
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
    <td valign="top"><ul><li>Ausgehende Webhooks ähneln Bots, aber deshalb mit niedrigeren Berechtigungen haben. Sie müssen explizit, genau wie Bots angegeben werden.</li><li>Wenn eine ausgehende Webhook registriert ist, wird einen <em>geheimen Schlüssel</em> generiert, sodass die ausgehende Webhook überprüfen, ob der Absender Microsoft-Teams, im Gegensatz zu einem Angreifer ist. Dieser Schlüssel sollte einen geheimen Schlüssel bleiben. Jeder Benutzer mit Zugriff auf die Datei kann Microsoft-Teams imitieren. Wenn der geheimen Schlüssel gefährdet ist, die ausgehende Webhook gelöscht und neu erstellt werden kann, und ein neuer geheimen Schlüssel generiert werden.</li><li>Obwohl es & #39; s möglich, erstellen eine ausgehende Webhook, & #39; t den geheimen Schlüssel, es wird empfohlen, ihn zu überprüfen.</li><li>Als empfangen und Beantworten von Nachrichten, ausgehende Webhooks kann & #39; nicht viel t: sie können & #39; t proaktiv Senden von Nachrichten, sie können & #39; t senden oder Empfangen von Dateien, sie können & #39; sonst noch etwas Möglichkeiten, die Bots empfangen und Beantworten von außer können t Nachrichten.</li></ul></td>
  </tr>
</table>
