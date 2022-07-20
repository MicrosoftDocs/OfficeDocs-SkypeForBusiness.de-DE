---
title: Verwalten von F&A in Teams-Besprechungen
author: wlibebe
ms.author: wlibebe
ms.reviewer: sameer.sitaram
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.localizationpriority: medium
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
description: Erfahren Sie, wie IT-Administratoren Q&A in Teams Q&A einrichten, verwenden und verwalten können, um einen strukturierten Ansatz für das Sammeln von Fragen, das Organisieren von Diskussionen, das Löschen einzelner Nachrichten, die Verwendung verfügbarer Sprachen und das Verständnis des Datenlebenszyklus sowie von Richtlinien für die Datenaufbewahrung und -löschung zu erhalten.
ms.openlocfilehash: 3ffdc4f48c43bef2d1d342983a63612c91bc40a9
ms.sourcegitcommit: 89904ab4116294ad9e4fd407feba8d7e3eefef10
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/19/2022
ms.locfileid: "66880429"
---
# <a name="manage-qa-in-teams-meetings"></a>Verwalten von F&A in Teams-Besprechungen

F&A ermöglicht es Referenten, Fragen von Teilnehmern zu stellen und sie in Echtzeit zu beantworten. Dieses Feature eignet sich am besten für große, strukturierte Besprechungen wie Versammlungen, Webinare, Alle Hände und Schulungen.

In diesem Artikel wird beschrieben, wie Sie Q&A und Richtlinien auf Benutzerebene verwalten, die festlegen, ob ein Organisator Teams Q&A in ihren Besprechungen aktivieren kann.

## <a name="prerequisites"></a>Voraussetzungen

- Stellen Sie sicher, dass Sie den Zugriff auf [die IPs und URLs von Yammer](/microsoft-365/enterprise/urls-and-ip-address-ranges) nicht blockiert haben.
- Damit Benutzer in Ihrer Organisation F&A zu Teams-Besprechungen hinzufügen können, müssen Sie bestätigen, dass Die Anmeldungen für den Office 365 Yammer-Dienst in Azure Active Directory aktiviert sind. Führen Sie die folgenden Schritte aus, um zu bestätigen, dass Die Anmeldungen aktiviert sind:
  - Wechseln Sie zum **Azure AD Admin Center** > **Alle Dienste** > **Enterprise-Anwendungen** >  **Office 365 Yammer** > **Eigenschaften**.
  - Wählen Sie für die Option **"Für Benutzer aktiviert" die** Option " **Ja** " aus, falls erforderlich.

## <a name="who-can-use-qa"></a>Wer kann Q&A verwenden?

F&A kann von den folgenden Benutzertypen verwendet werden:

- Normaler Benutzer – Ein Benutzer mit Microsoft 365-Anmeldeinformationen in Ihrem Mandanten.
- Verbundbenutzer – Ein Benutzer mit Microsoft 365-Anmeldeinformationen für einen anderen Mandanten.
- Gastbenutzer – Alle Gäste, die Sie Zu Ihren Microsoft Teams, SharePoint oder Azure Active Directory hinzufügen.

> [!NOTE]
> F&A steht nicht nur Teilnehmern zur Verfügung, die über die Besprechungskapazität verfügen.

Wenn Administratoren Q&A aktivieren, können Benutzer mit der [Organisatorrolle](https://aka.ms/GetQnA) Q&A beim Erstellen oder Aktualisieren von Besprechungen aktivieren. Über Teams- und Outlook-Besprechungsoptionen können Organisatoren Q&A auch aus Besprechungen entfernen, in denen es zuvor hinzugefügt wurde, um teilnehmer daran zu hindern, das Feature zu verwenden.

## <a name="use-the-teams-admin-center-to-manage-qa"></a>Verwenden des Teams Admin Centers zum Verwalten von F&A

Möglicherweise hat Ihre Organisation Anforderungen, um zu begrenzen, welche Organisatoren Q&A aktivieren können. Sie können das Teams Admin Center verwenden, um zu verwalten, welche Organisatoren Q&A in großen Besprechungen aktivieren können.
Führen Sie die folgenden Schritte aus, um zu steuern, welche Organisatoren Q&A verwenden können:

1. Wechseln Sie im Teams Admin Center zu **Besprechungsbesprechungsrichtlinien** > [](/meeting-policies-participants-and-guests)
2. Wählen Sie eine vorhandene Richtlinie aus, oder erstellen Sie eine neue Richtlinie, und geben Sie ihr einen Namen wie "Keine F&A für diese Organisatoren"
3. Scrollen Sie zum Abschnitt mit dem Namen **"Teilnehmer & Gäste"**, wählen Sie **"Deaktivieren" für die Einstellung "Frage & Benutzeroberfläche"** aus, und speichern Sie die Richtlinie.
4. Zuweisen der Richtlinie zu bestimmten M365-Gruppen, Endbenutzern oder Abonnements, die Sie am Einrichten von F&A hindern möchten

## <a name="use-powershell-to-manage-qa"></a>Verwenden von PowerShell zum Verwalten von Q&A

Möglicherweise hat Ihre Organisation Anforderungen, um zu begrenzen, welche Organisatoren Q&A aktivieren können. Sie können PowerShell verwenden, um zu verwalten, welche Organisatoren Q&A in großen Besprechungen aktivieren können.

PowerShell-Beispielbefehl zum Aktivieren von F&A:

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -QnAEngagementMode Enabled
```

## <a name="delete-an-individual-message-from-qa-in-teams"></a>Löschen einer einzelnen Nachricht aus Q&A in Teams

Führen Sie die folgenden Schritte aus, um eine Frage oder Antwort zu löschen, die in der Anwendung F&A gepostet wurde:

1. Melden Sie sich beim Exchange Admin Center als globaler Administrator an.
2. Wechseln Sie zu "**Empfängerpostfächer**", und suchen Sie nach dem Namen des **Benutzers** > , der die Besprechung organisiert hat.
3. Wählen Sie den Besprechungsorganisator aus, und klicken Sie auf **"Postfachdelegierung verwalten"**. Wählen Sie im Abschnitt **"Lesen und verwalten** " die Option **"Berechtigungen bearbeiten** > **"** aus.
4. Fügen Sie sich selbst als Stellvertretung des Besprechungsorganisators hinzu, und wählen Sie "Speichern" aus.
5. Öffnen Sie Outlook-Kalender im Outlook Web App (nicht auf dem Desktop), und wählen Sie **"Kalender hinzufügen"** und dann "**Aus Verzeichnis hinzufügen" aus**.
6. Suchen Sie nach dem Besprechungsorganisator, und fügen Sie den Kalender zu **"Meine Kalender**" hinzu. Besprechungen für den ausgewählten Benutzer werden jetzt in Ihrem Kalender angezeigt.
7. Suchen Sie in Ihrem Kalender die Besprechung, für die Sie Inhalte löschen möchten, öffnen Sie den Besprechungsdatensatz, und wählen Sie **"Mit Teilnehmern chatten"** aus. Wenn Sie einen Chat mit Teilnehmern auswählen, wird der Besprechungschat in Teams geöffnet.
8. Navigieren Sie in der Teams-App-Leiste zu der Anwendung F&A.
9. Suchen Sie alle Fragen oder Antworten, die Sie löschen möchten, und wählen Sie "Löschen" aus.
10. Nachdem Sie den Inhalt gelöscht haben, kehren Sie zum Exchange Admin Center zurück, und entfernen Sie sich selbst als Stellvertretung des Besprechungsorganisators.

> [!NOTE]
> Wenn Sie eine Frage löschen, bevor Sie die Antworten entfernen, wird die erste Antwort auf die Frage zur Frage.
>
> Um dies zu vermeiden, führen Sie die folgenden Schritte in der folgenden Reihenfolge aus:
>
> 1. Identifizieren der Frage, die Sie löschen möchten
> 2. Löschen der Antworten auf die Frage
> 3. Löschen der Frage

## <a name="available-languages-for-yammer-versus-teams"></a>Verfügbare Sprachen für Yammer im Vergleich zu Teams

Die F-&A wird standardmäßig auf die Sprache des Benutzers für Teams festgelegt. Wenn es einen Unterschied in den für Teams verfügbaren Sprachen im Vergleich zu Yammer gibt, treten die folgenden Sprachstandards auf:

- Nächste Primäre Sprache – Yammer wird standardmäßig auf die nächste Primäre Sprache festgelegt, sofern verfügbar. Beispielsweise bietet Yammer keine französisch-kanadische Version (fr-CA), sodass stattdessen Inhalte in Französisch (fr-FR) angezeigt werden.
- Nicht unterstützte Sprache – Wenn die Sprache überhaupt nicht von Yammer bereitgestellt wird, wird Yammer standardmäßig auf US-Englisch (en-US) festgelegt.

## <a name="ediscovery"></a>eDiscovery

eDiscovery für Q&A funktioniert genauso wie eDiscovery für alle anderen Yammer Inhalte.

- Wenn Sie Teams Q&A in der Teams-Anwendung Ihres Mandanten verwenden, sind diese Inhalte unabhängig von der Konfiguration oder dem Vorhandensein Ihres Yammer Netzwerks in eDiscovery verfügbar. Um eDiscovery für standardmäßige Yammer-Inhalte zu verwenden, muss sich Ihr Yammer-Netzwerk im [nativen Modus befinden](/yammer/configure-your-yammer-network/overview-native-mode).
- Wenn Sie eDiscovery ausführen, können Sie bestimmen, ob Nachrichten in Yammer oder über Q&A in Teams generiert wurden. Im Abschnitt "Dateimetadaten" finden Sie diese Informationen im Feld "Elementklasse".
- Wenn Ihre Organisation die Teams-F-&A verwendet, die von Yammer unterstützt wird, werden die von Q&A generierten Inhalte als Yammer Inhalte betrachtet und sind auffindbar. Weitere Informationen zu eDiscovery in Microsoft 365-Apps finden Sie [unter eDiscovery-Lösungen in Microsoft 365.](/microsoft-365/compliance/ediscovery)
- Wenn der Besprechungsorganisator die anonyme Veröffentlichung aktiviert, werden die Fragen, die Teilnehmer posten, in das Postfach des Organisators für eDiscovery aufgenommen.

## <a name="data-storage"></a>Datenspeicherung

F&A-Nachrichten, die als Teil der Besprechung erstellt wurden, werden als Yammer Nachrichten gespeichert. Diese Nachrichten werden in Yammer gespeichert und für eDiscovery aufgenommen.
Dateien werden immer in SharePoint gespeichert, wodurch alle Daten-Rest-Richtlinien und -Speicherorte behandelt werden.

In den folgenden Anleitungen wird erläutert, wie Nachrichtendaten gespeichert werden:

- F&Ein Inhalt ist über eDiscovery durchsuchbar und Advanced eDiscovery auf Benutzerebene.
- Nachrichtendaten (einschließlich Nachrichteninhalt) werden standardmäßig in Nordamerika oder EU gespeichert (je nach Yammer Netzwerkstandort des Kunden).
- Für Mandanten, die nicht über ein vorhandenes Yammer-Netzwerk verfügen, wird das Q&A Yammer-Netzwerk in der USA Yammer Region erstellt. Die Nachrichten Ihrer Organisation für Q&A werden immer in den USA gespeichert.
- Ähnlich wie bei OneNote-Registerkarten werden beim Entfernen des F-&A aus einer Besprechung die Besprechungsdaten nicht gelöscht. Durch das Entfernen von F&A aus der Besprechung wird nur der Zugriff auf die Daten aus der Besprechung entfernt. Wenn Sie die Registerkarte "F&A" wieder hinzufügen, werden alle Besprechungsunterhaltungen wieder angezeigt.

## <a name="gdpr-for-qa-in-teams"></a>DSGVO für F&A in Teams

Wenn Sie eine Datensubjektanforderung über das Microsoft 365 Admin Center abschließen, werden die Kontaktinformationen der Benutzer automatisch aus allen ihren Inhalten im F-&A entfernt.

## <a name="data-lifecycle-for-qa-in-teams"></a>Datenlebenszyklus für F&A in Teams

Der Lebenszyklus von Daten, die von Q&A in Teams generiert werden, hängt von Ihren Yammer Einstellungen für die Datenaufbewahrung im Compliance Center ab. Wenn Sie alle Benutzer in der Besprechung, die eine Kopie der Q-&A-Nachrichten in ihrem Substratshard über Azure Active Directory erhalten haben, endgültig löschen, löscht Yammer ihre Kopie des Q&A-Inhalts für diese Besprechung innerhalb von 30 Tagen nach dem Löschen des Benutzers.

## <a name="retention-and-deletion"></a>Aufbewahrung und Löschung

Die Aufbewahrung von Inhalten folgt den Aufbewahrungsrichtlinien, die für Yammer festgelegt wurden – unabhängig davon, ob Sie für Yammer und Teams unterschiedliche Richtlinien festgelegt haben.

> [!NOTE]
> Wenn sich Ihr Yammer-Netzwerk nicht im nativen Modus befindet, gelten die hier erstellten Richtlinien nur für Teams Q&A-Daten. Im nativen Modus befinden sich alle Yammer Benutzer in Azure Active Directory (Azure AD), alle Gruppen sind Microsoft 365-Gruppen, und alle Dateien werden in SharePoint Online gespeichert.

## <a name="faq"></a>Häufig gestellte Fragen

**F: Gewusst wie Q&A-Inhalt exportieren?**

**Eine:** F&Ein Inhalt wird in der Microsoft 365 Compliance Center gespeichert und über eDiscovery aufgerufen. Zukünftige Iterationen umfassen einen Bericht zu Besprechungshighlights und Exportfunktionen für Besprechungsorganisatoren.

**F: Unterstützt Q&A die Multi-Geo-Funktionen von Microsoft 365?**

**Eine:** F&A unterstützt derzeit keine Microsoft 365 Multi-Geo-Funktionen. F&A-Daten werden standardmäßig in Nordamerika oder EU gespeichert (je nach Yammer Netzwerkstandort des Kunden).

**F: Wo kann ich mehr über strukturierte Besprechungen erfahren?**

**Eine:** Befolgen Sie diese [bewährten Methoden](/MicrosoftTeams/quick-start-meetings-live-events) zum Hosten erfolgreicher großer Besprechungen in Microsoft Teams.

**F: Was ist der Unterschied zwischen der Einrichtung von F&A über den Teams App Store und der Verwendung von Besprechungsoptionen?**

**Eine:** Wir haben die Aktivierung von Q&A bis Besprechungsoptionen vereinfacht.Ab August 2022 wird die Q&A-App im Teams-App Store nicht mehr unterstützt, sodass Q&A nur über Besprechungsoptionen aktiviert werden darf. Wenn Sie der Organisator für Besprechungen sind, in denen Q&A über den Teams-App Store aktiviert wurde, entfernen Sie die Q&A-App, und aktivieren Sie sie stattdessen nur über die Besprechungsoptionen.

**F: Warum werden zwei Q&A-Symbole in meiner Besprechung angezeigt?**

**Eine:** In Ihrer Besprechung werden zwei Q-&A-Symbole angezeigt, da Q&A auch über Besprechungsoptionen aktiviert wurde. Entfernen Sie die Q&A-App, die über die Teams-App Store hinzugefügt wurde, anhand der nachstehenden Anweisungen. Führen Sie dies für alle Besprechungen aus, in denen Sie zuvor Q&A über den Teams-App Store hinzugefügt haben.

**So entfernen Sie die Q-&Eine App, die aus dem Teams-App Store hinzugefügt wurde.**

1. Nehmen Sie auf Teams Desktop an der Besprechung teil, in der Sie zuvor F&A hinzugefügt haben.

2. Wählen Sie im oberen Bereich das zweite Vorkommen des Symbols "F&A" im Fenster "Teams-Besprechung" aus – dies ist die Q&A-Erfahrung, die über die Teams-App Store hinzugefügt wurde.

3. Klicken Sie bei geöffnetem ausgewählten F-&A-Registerkarte auf die Auslassungszeichen und dann auf "Entfernen". Dadurch wird die Q&A-Erfahrung entfernt, die über den Teams-App Store hinzugefügt wurde.

4. Klicken Sie auf "Entfernen", um die Q&A-Erfahrung, die über den Teams-App Store hinzugefügt wurde, dauerhaft zu entfernen.

> [!NOTE]
> Nur die über den Teams-App Store hinzugefügte Q-&A-App weist einen Auslassungszeichen auf, um die Q&A-App zu entfernen. Die über Besprechungsoptionen aktivierte Q-&A-Erfahrung weist keine Auslassungspunkte auf und kann hier nicht entfernt werden.

Das wars! Jetzt gibt es nur ein Q&A-Erlebnis – unterstützt von Besprechungsoptionen. Die über den Teams-App Store hinzugefügte Q&A-App wird entfernt.
