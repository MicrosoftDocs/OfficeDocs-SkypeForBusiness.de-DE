---
title: Upgrade-Checkliste | Upgrade von Skype for Business zu Teams | Grundlegende Schritte
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Folgen Sie diesem beschleunigten Zehn-Schritt-Aktionsplan für den Übergang von einer einfachen Skype for Business-Einrichtung in die Microsoft Teams-Einrichtung.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- seo-marvel-apr2020
- Teams-upgrade-guidance
- ms.teamsadmincenter.dashboard.widget.upgrade.opt-in
- ms.teamsadmincenter.dashboard.widget.upgrade.opt-out
- ms.teamsadmincenter.dashboard.widget.upgrade.scheduled
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 37cc9f3940eb08a4df092042c016b194b01c64e6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809085"
---
# <a name="upgrade-basic"></a>Upgrade Basic

<a name="about-upgrade-basic"></a>

Die Upgrade Basic-Checkliste ist für kleinere Organisationen oder diejenigen gedacht, die Skype for Business Online für Chats und Besprechungen nutzen, und bietet einen gestrafften Aktionsplan mit den wichtigsten empfohlenen Aktivitäten und den zugehörigen Ressourcen für einen erfolgreichen Wechsel von Skype for Business zu Teams.

Diese zehn einfachen Schritte decken alles ab, was Sie für ein erfolgreiches Upgrade benötigen. Sie sind für den Abschluss in etwa 30 bis 45 Tagen ausgelegt, sie sollten jedoch basierend auf dem Upgradezeitplan Ihrer Organisation angepasst werden.

> [!IMPORTANT]
> Skype for Business Online wird am 31. Juli 2021 eingestellt. Ab diesem Zeitpunkt kann nicht mehr darauf zugegriffen werden, und es wird nicht mehr unterstützt. Um den maximalen Nutzen zu erzielen und sicherzustellen, dass Ihre Organisation genügend Zeit hat, Ihr Upgrade durchzuführen, empfehlen wir Ihnen, den Wechsel zu Microsoft Teams bereits heute zu planen.

Was geschieht mit Skype for Business nach dem Upgrade? Nach dem Upgrade der Benutzer auf Microsoft Teams (Modus **Teams only** (Nur Microsoft Teams)) gilt Folgendes:

- Der Skype for Business-Client der Benutzer ist deaktiviert und kann nicht mehr verwendet werden, alle Chats und Anrufe laufen dann über Microsoft Teams. Beachten Sie, dass der Client dabei nicht von ihren Desktops deinstalliert wird.
- Vor dem Upgrade geplante Skype for Business-Besprechungen funktionieren wie vorgesehen, aber alle neuen Besprechungen werden in Microsoft Teams geplant. Das Skype for Business-Plug-In ist in Outlook nicht mehr verfügbar. 
- Wenn Benutzer versuchen, sich bei Skype for Business anmelden, erhalten sie eine Benachrichtigung von ihrem Client, dass sie auf Teams aktualisiert wurden.
- Auf mobilen Geräten müssen die Benutzer den Skype for Business-Client manuell deinstallieren.

Lesen Sie die diesbezüglichen [häufig gestellten Fragen (FAQ)](https://aka.ms/SkypeToTeams-FAQ), wenn Sie weitere Fragen zu Ihrem Upgrade haben.

Sie sind mit Teams noch nicht vertraut? [Erfahren](https://products.office.com/microsoft-teams/group-chat-software) Sie, wie Teams Unterhaltungen, Besprechungen, Dateien, Office-Apps und Integrationen von Drittanbietern vereint – bereitstellung eines einzigen Hubs für Teamarbeit in Microsoft 365 und Office 365.

<!--ENDOFSECTION-->

<a name="step-1"></a>

## <a name="step-1-notify-your-key-stakeholders"></a>Schritt 1: Benachrichtigung der wichtigsten Projektbeteiligten

*(Ca. vier bis sechs Wochen vor dem Upgrade)*

Leitende Mitarbeiter sind für den Erfolg des Unternehmens verantwortlich. Achten Sie darauf, sie über technologische Änderungen auf dem Laufenden zu halten. Da es möglich ist, dass nicht alle Benutzer die Benachrichtigung über die Berechtigung zum Upgrade erhalten oder gelesen haben, müssen Sie die Projektbeteiligten (z. B. CEO, IT-Profis, Marketing- und Helpdesk-Leads) informieren, bevor Sie mit der Planung des Upgrades beginnen.

**Ressourcen:**

- [Beispiel-E-Mail: Mitteilung an die Projektbeteiligten](upgrade-emails-surveys.md#step-1-email)

[Nach oben](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-2"></a>

## <a name="step-2-prepare-your-organization-for-teams"></a>Schritt 2: Vorbereiten Ihrer Organisation auf Teams

*(Ca. vier bis sechs Wochen vor dem Upgrade)*

Teams bietet mit Skype for Business kompatible Funktionen wie etwa Chat und Meetings, es kann aber noch weitaus mehr. Als echter Hub für die Teamarbeit ermöglicht Teams Arbeitsgruppen die Verwaltung von Projekten, Dateien, Unterhaltungen und Apps an einem Ort. Microsoft Teams ist standardmäßig für alle Organisationen aktiviert. Entscheiden Sie, wie Ihre Organisation Teams verwenden soll, um ideale Rahmenbedingungen für den Erfolg zu schaffen. 

> [!Note]
> Als bestehender Skype for Business-Kunde ist Ihre aktuelle Netzwerkinfrastruktur wahrscheinlich bereits für Teams konfiguriert. Um dies zu bestätigen, können Sie den unten angegebenen Richtlinien zur vollständigen technischen Planung folgen (dies ist optional).

**Ressourcen:**

- [Übersicht über Microsoft Teams](Teams-overview.md)
- [Erste Schritte mit Microsoft Teams](get-started-with-teams-quick-start.md)

[Nach oben](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-3"></a>

## <a name="step-3-know-your-skype-for-business-users"></a>Schritt 3: Lernen Sie Ihre Skype for Business-Benutzer kennen

*(Ca. vier Wochen vor dem Upgrade)*

Benutzer, die Skype for Business intensiv verwendet haben, benötigen möglicherweise etwas mehr Zeit oder Unterstützung beim Übergang zu Teams. Nehmen Sie sich Zeit, um die aktuelle Skype for Business-Nutzung zu überprüfen und jene Benutzer zu ermitteln, die am meisten zusätzlichen Support benötigen, und um eine Verwendungs-Baseline festzulegen, die Sie mit den nach dem Upgrade erfassten Zahlen vergleichen können.

**Ressourcen:**

- [Microsoft 365-Berichte im Admin Center](https://docs.microsoft.com/microsoft-365/admin/activity-reports/activity-reports)

[Nach oben](#about-upgrade-basic)

<a name="step-4"></a>

<!--ENDOFSECTION-->

## <a name="step-4-notify-your-users-that-theyll-be-upgrading-from-skype-for-business-to-teams"></a>Schritt 4: Benachrichtigen der Benutzer über das Upgrade von Skype for Business auf Teams

*(Ca. zwei bis drei Wochen vor dem Upgrade)*

Wenn Sie Ihre Benutzer zeitig darüber informieren, haben diese ausreichend Zeit, sich mit Teams vertraut zu machen, ohne dass sich dies negativ auf ihre Produktivität auswirkt. Auf diese Weise wird eine positivere Benutzererfahrung erzielt. Senden Sie eine Kommunikation, um ihnen zu sagen, was sich ändert, warum sie sich ändert und wie sie sich darauf vorbereiten können.

> [!Note]
> Bei Bedarf können Sie Teams für Ihre Benutzer derzeit über das Microsoft 365 Admin Center aktivieren.

**Ressourcen:**

- [Verwalten von Microsoft Teams-Einstellungen in Ihrer Organisation](enable-features-office-365.md)
- [Beispiel-E-Mail: Benachrichtigung der Benutzer über Skype for Business](upgrade-emails-surveys.md#step-4-email)

[Nach oben](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-5"></a>

## <a name="step-5-activate-the-user-upgrade-notification"></a>Schritt 5: Aktivieren des Upgrade-Hinweises für die Benutzer 

*(Ca. eine Woche vor dem Upgrade)*

Halten Sie die Aufmerksamkeit für das Upgrade aufrecht, indem Sie über das Verwaltungsportal den Upgrade-Hinweis an die Benutzer aktivieren. Dabei handelt es sich um einen visuellen Hinweis innerhalb des Skype vor Business-Clients, der die Anwender daran erinnert, dass ein Upgrade von Skype for Business auf Teams erfolgen wird.

**Ressourcen:**

- [Festlegen Ihrer Einstellungen für Koexistenz und Upgrades](setting-your-coexistence-and-upgrade-settings.md)

[Nach oben](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-6"></a>

## <a name="step-6-remind-your-users-that-theyll-be-upgrading-from-skype-for-business-to-teams"></a>Schritt 6: Erinnern Sie Ihre Benutzer daran, dass sie ein Upgrade von Skype for Business auf Teams durchführen werden.

*(Ca. fünf Tage vor dem Upgrade)*

Die Benutzer sind von ihren täglichen Aufgaben in Anspruch genommen. Durch eine Erinnerung an das bevorstehende Upgrade können Sie sicherstellen, dass sie nicht vergessen, die für die Vorbereitung auf Teams benötigten Schritte zu unternehmen. Dies ist der ideale Zeitpunkt, um die Benutzer an die verfügbaren Schulungen und die ersten Schritte mit Teams zu erinnern.

**Ressourcen:**

- [Beispiel-E-Mail: Benutzer an die ersten Schritte mit Teams erinnern](upgrade-emails-surveys.md#step-6-email)

[Nach oben](#about-upgrade-basic)

<a name="step-7"></a>

<!--ENDOFSECTION-->

## <a name="step-7-upgrade-users-to-teams"></a>Schritt 7: Upgrade der Benutzer auf Teams!

*(Upgradetag)*

Heute führt Ihr Unternehmen offiziell das Upgrade auf Teams als Lösung für Kommunikation und Zusammenarbeit durch. Aktivieren Sie im Microsoft Teams Admin Center den Upgrade-Schalter, indem Sie als Koexistenzmodus **Teams only (Nur Microsoft Teams)** festlegen. (Wechseln Sie im Admin Center zu **"Organisationsweite Einstellungen"**  >  **Upgrade für Teams.)** Benutzer erhalten in ihrem Skype for Business-Client eine Benachrichtigung, dass für sie ein Upgrade auf Teams durchgeführt wurde.

Wir empfehlen, allen Benutzern nach deren Upgrade eine E-Mail zu senden, in der Sie sie in Teams willkommen heißen.

**Ressourcen:**

- [Festlegen Ihrer Einstellungen für Koexistenz und Upgrades](setting-your-coexistence-and-upgrade-settings.md)
- [Beispiel-E-Mail: Benutzer in Teams willkommen heißen](upgrade-emails-surveys.md#step-7-email)

[Nach oben](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-8"></a>

## <a name="step-8-monitor-teams-usage-against-your-baseline"></a>Schritt 8: Überwachen der Team-Nutzung anhand Ihrer Baseline

*(Etwa ein oder zwei Wochen nach dem Upgrade)*

Die Anpassung an eine neue Technologie kann einige Zeit in Anspruch nehmen. Verfolgen Sie die Nutzung, um zu überprüfen, ob die Benutzer Microsoft Teams im selben (oder größeren) Umfang wie Skype for Business verwenden. Suchen Sie nach Benutzern, die Teams nicht auf den erwarteten Ebenen verwenden.

**Ressourcen:**

- [Siehe Nutzungsdaten](https://portal.office.com/AdminPortal/Home#/reportsUsage)

[Nach oben](#about-upgrade-basic)

<a name="step-9"></a>

<!--ENDOFSECTION-->

## <a name="step-9-measure-user-satisfaction"></a>Schritt 9: Messen der Benutzerzufriedenheit

*(Etwa ein oder zwei Wochen nach dem Upgrade)*

Die Mitarbeiterzufriedenheit kann die Produktivität, ihre Bindung an das Unternehmen und letztlich die geschäftlichen Ergebnisse beeinflussen. Befragen Sie Ihre Benutzer, um sich ein Bild von deren Stimmung hinsichtlich des Upgrades und ihrer Zufriedenheit mit Teams machen zu können.

**Ressourcen:**

- [Beispiel-E-Mail: Nachhaken bei Benutzern](upgrade-emails-surveys.md#step-9-email) plus [ Benutzerumfragen](upgrade-emails-surveys.md#step-9-surveys)

[Nach oben](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-10"></a>

## <a name="step-10-maximize-your-roi-with-teams"></a>Schritt 10: Maximieren Sie Ihren ROI mit Teams

*(Laufend)*

Nachdem sich die Benutzer mit Chats und Besprechungen in Teams vertraut gemacht haben, sollten Sie sie dazu anregen, die Nutzung durch die Zusammenarbeit in Teams und die App-Integration zu erweitern, um die neue Lösung optimal einzusetzen und die bestmögliche Rendite für Ihre Investitionen zu erzielen.

**Ressourcen:**

- [Beispiel-E-Mail: Die Benutzer dazu anregen, Teams weiter zu erkunden](upgrade-emails-surveys.md#step-10-email)

[Nach oben](#about-upgrade-basic)
