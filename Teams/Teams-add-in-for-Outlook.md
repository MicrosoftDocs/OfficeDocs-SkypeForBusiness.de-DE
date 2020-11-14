---
title: Verwenden des Microsoft Teams-Besprechungs-Add-Ins in Outlook
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams installiert in Outlook ein Add-In, mit dem Benutzer Microsoft Teams-Besprechungen über Outlook planen können.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 574e770eb1756a2c83758b830c26e6adbac24183
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031761"
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a>Verwenden des Microsoft Teams-Besprechungs-Add-Ins in Outlook
=======================================

Mit dem Microsoft Teams-Besprechungs-Add-Ins können Benutzer eine Teambesprechung von Outlook aus planen. Das Add-in ist für Outlook unter Windows, Mac, im Web und Mobile verfügbar.

## <a name="teams-meeting-add-in-in-outlook-for-windows"></a>Microsoft Teams-Besprechungs-Add-In in Outlook für Windows

Das Team Besprechungs-Add-in wird automatisch für Benutzer installiert, die Microsoft Teams und entweder Office 2013, Office 2016 oder Office 2019 auf Ihrem Windows-PC installiert haben. Die Benutzer sehen auf dem Menüband „Kalender“ in Outlook das Microsoft Teams-Besprechungs-Add-In.

![Screenshot des Microsoft Teams-Add-Ins auf dem Outlook-Menüband](media/Teams-add-in-for-Outlook.png)

> [!NOTE]
> - Es gibt **keine direkte URL** , die mit dem Add-in "Teams" verknüpft ist.
> - Es gibt weitere Überlegungen, ob Ihre Organisation beide Teams und Skype for Business ausführt. Unter bestimmten Umständen steht das Team-Add-in in Outlook nicht zur Verfügung. Weitere Informationen finden Sie unter [Upgrade von Skype for Business in Teams](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-on-prem-overview#meetings) .
> - Benutzerberechtigungen zum Ausführen der Datei „Regsvr32.exe“ sind eine Mindestanforderung, damit das Add-In für „Teams Meeting“ auf dem Computer installiert wird.
> - Wenn Benutzer das Microsoft Teams-Besprechungs-Add-In nicht sehen, weisen Sie sie an, Outlook und Microsoft Teams zu schließen, den Microsoft Teams-Client neu zu starten, sich bei Microsoft Teams anzumelden und den Outlook-Client zu starten (in dieser Reihenfolge).
> - Wenn Sie eine Office Outlook-Installation aus dem Microsoft Store verwenden, wird das Add-In für „Teams Meeting“ nicht unterstützt. Benutzern, die dieses Add-In benötigen, wird empfohlen, die Klick-und-Los-Version von Office zu installieren, wie im Artikel [Office unter Windows 10 im S-Modus](https://support.office.com/article/faq-office-on-windows-10-in-s-mode-717193b5-ff9f-4388-84c0-277ddf07fe3f) beschrieben.

## <a name="teams-meeting-add-in-in-outlook-for-mac"></a>Teams Meeting-Add-In in Outlook für Mac

Die Schaltfläche "Teams-Besprechung" in Outlook für Mac wird im Menüband von Outlook für Mac angezeigt, wenn Outlook den Produktions-Build 16.24.414.0 und höher ausführt und mit einem Microsoft 365-oder Office 365-Clientabonnement aktiviert ist.

Die Besprechungskoordinaten (der Link zum Beitreten zu einer Teams-Besprechung und die Einwahlnummern) werden der Besprechungseinladung hinzugefügt, nachdem der Benutzer auf **Senden** geklickt hat.  

## <a name="teams-meeting-add-in-in-outlook-web-app"></a>Microsoft Teams-Besprechungs-Add-In in Outlook Web App

Die Schaltfläche „Teams-Besprechungen“ in Outlook Web App wird als Teil der neuen Ereigniserstellung angezeigt, wenn der Benutzer eine frühe Version des neuen Outlook im Web verwendet. Informationen dazu, wie Benutzer die frühe Version des neuen Outlook im Web testen können, finden Sie im [Outlook-Blog](https://techcommunity.microsoft.com/t5/Outlook-Blog/Designed-to-be-fast-The-Outlook-on-the-web-user-experience-gets/ba-p/234909?utm_source=t.co&utm_medium=referral).

![Screenshot des Microsoft Teams-Add-Ins in Outlook Web App](media/teams-meeting-add-in-web.png)

Die Besprechungskoordinaten (der Link zum Beitreten zur Teams-Besprechung und Einwahlnummern) werden der Besprechungseinladung hinzugefügt, nachdem der Benutzer auf **Senden** geklickt hat.  

## <a name="teams-meeting-add-in-in-outlook-mobile-ios-and-android"></a>Microsoft Teams-Besprechungs-Add-in in Outlook Mobile (iOS und Android)

Die Schaltfläche „Teams-Besprechung“ wird in den neuesten Builds der Outlook-App für iOS-und Android angezeigt.

![Screenshot des Microsoft Teams-Add-Ins in Outlook Mobile](media/teams-meeting-add-in-mobile.png)

Die Besprechungskoordinaten (der Link zum Beitreten zur Teams-Besprechung und Einwahlnummern) werden der Besprechungseinladung hinzugefügt, nachdem der Benutzer auf **Senden** geklickt hat.  

## <a name="teams-meeting-add-in-and-findtime-for-outlook"></a>Teambesprechung-Add-in und Suchzeit für Outlook

Find Time ist ein Add-in für Outlook, das Benutzern hilft, sich über eine Besprechungszeit in Unternehmen zu einigen. Sobald die Besprechungsteilnehmer ihren bevorzugten Zeitpunkt angegeben haben, sendet Uhrzeit finden die Besprechungseinladung im Namen des Benutzers. Wenn die Option **Onlinebesprechung** in Uhrzeit finden ausgewählt ist, plant Uhrzeit finden eine Skype for Business- oder eine Microsoft Teams-Besprechung. (Die von Uhrzeit finden verwendete Option hängt von dem standardmäßigen Onlinebesprechungskanal ab, der von Ihrer Organisation festgelegt wurde.)

> [!NOTE]  
> Wenn Sie eine Skype for Business-Einstellung in Ihrem [Uhrzeit finden-Dashboard](https://findtime.microsoft.com/UserDashboard) gespeichert haben, wird diese anstelle von Microsoft Teams von Uhrzeit finden verwendet. Wenn Sie Microsoft Teams verwenden möchten, löschen Sie die Skype for Business-Einstellung in Ihrem Dashboard.

Weitere Informationen finden Sie unter [Planen von Besprechungen mit Suchzeiten](https://support.office.com/article/scheduling-meetings-with-findtime-4dc806ed-fde3-4ea7-8c5e-b5d1fddab4a6).

## <a name="authentication-requirements"></a>Authentifizierungsanforderungen

Benutzer des Microsoft Teams-Besprechungs-Add-Ins müssen sich mit moderner Authentifizierung bei Microsoft Teams anmelden. Wenn Benutzer diese Methode nicht zur Anmeldung verwenden, können Sie weiterhin den Team-Client verwenden, können jedoch keine Teams-Onlinebesprechungen mit dem Outlook-Add-in planen. Dies können Sie mit einer der folgenden Methoden korrigieren:

- Wenn die moderne Authentifizierung für Ihre Organisation nicht konfiguriert ist, sollten Sie sie konfigurieren.
- Wenn die moderne Authentifizierung konfiguriert ist, aber die Benutzer den Vorgang im Dialogfeld abgebrochen haben, weisen Sie die Benutzer an, sich mit mehrstufiger Authentifizierung erneut anzumelden.

Weitere Informationen zum Konfigurieren der Authentifizierung finden Sie unter [Identitätsmodelle und Authentifizierung in Microsoft Teams](identify-models-authentication.md).

## <a name="enable-private-meetings"></a>Aktivieren von privaten Besprechungen

Die Option **Zeitplanung für private Besprechungen zulassen** muss im Microsoft Teams Admin Center aktiviert sein, damit das Add-In bereitgestellt wird. Wechseln Sie im Admin Center zu **Besprechungen** > **Besprechungsrichtlinien** , und legen Sie im Abschnitt **Allgemein** **Zeitplanung für private Besprechungen zulassen** auf „Aktiviert“ fest.)

![Screenshot der Einstellungen im Microsoft Teams Admin Center.](media/teams-add-in-for-outlook-image1.png)

Der Microsoft Teams-Client ermittelt, ob die Benutzer die 32-Bit- oder 64-Bit-Version benötigen, und installiert dann das richtige Add-In.

> [!NOTE]
> Möglicherweise müssen die Benutzer Outlook nach einer Installation oder einem Upgrade von Microsoft Teams neu starten, um das aktuelle Add-In zu erhalten.

## <a name="teams-upgrade-policy-and-the-teams-meeting-add-in-for-outlook"></a>Microsoft Teams-Upgrade-Richtlinie und das Microsoft Teams-Besprechungs-Add-In für Outlook

Kunden können [von Skype for Business auf Microsoft Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md) umsteigen. Mandantenadministratoren können den Teams-Modus „Koexistenz“ verwenden, um diesen Umstieg für ihre Benutzer zu definieren. Mandantenadministratoren haben die Möglichkeit, die Nutzung von Teams zusammen mit Skype for Business (Inselmodus) zu ermöglichen. 

Wenn Benutzer im Inselmodus eine Besprechung in Outlook planen, erwarten sie in der Regel, dass sie auswählen können, ob Sie eine Skype for Business- oder eine Microsoft Teams-Besprechung planen. In Outlook im Web, Outlook Windows und Outlook Mac sehen Benutzer standardmäßig sowohl Skype for Business-als auch Teams-Add-Ins, wenn Sie sich im Modus "Inseln" befinden. Sie können eine Gruppen-Besprechungsrichtlinien Einstellung konfigurieren, um zu steuern, ob Benutzer im Modus "Inseln" nur das Add-in "Teams-Besprechung" oder sowohl die Teambesprechung als auch die Add-Ins für Skype for Business-Besprechungen verwenden können.

Aufgrund bestimmter Einschränkungen in der ersten Version kann Outlook Mobile nur das Erstellen von Besprechungen in Skype for Business **oder** Microsoft Teams unterstützen. Details finden Sie in der folgenden Tabelle.

| Koexistenzmodus im Microsoft Teams Admin Center | Standardmäßiger Besprechungsanbieter in Outlook Mobile |
| --------------------------------------|---------------------------------------------|
| Inselmodus | Skype for Business |
| Nur Skype for Business | Skype for Business |
| Skype for Business mit Zusammenarbeit in Microsoft Teams | Skype for Business |
| Skype for Business mit Zusammenarbeit und Besprechungen in Microsoft Teams | Microsoft Teams |
| Nur Microsoft Teams | Microsoft Teams |

### <a name="set-whether-users-in-islands-mode-can-only-use-the-teams-meeting-add-in-or-both-the-teams-meeting-and-skype-for-business-meeting-add-ins"></a>Festlegen, ob Benutzer im Inseln-Modus nur das Team Besprechungs-Add-in oder sowohl die Teambesprechung als auch die Skype for Business-Besprechungs-Add-Ins verwenden können

Als Administrator können Sie eine Team-Besprechungsrichtlinien Einstellung konfigurieren, um zu steuern, welches Outlook-Besprechungs-Add-in für Benutzer verwendet wird *, die sich im Inseln-Modus befinden*. Sie können angeben, ob Benutzer das Team Besprechungs-Add-in oder sowohl die Teambesprechung als auch die Skype for Business-Besprechungs-Add-Ins verwenden können, um Besprechungen in Outlook zu planen.

Sie können diese Richtlinie nur auf Benutzer anwenden, die sich im Modus "Inseln" befinden, und den **AllowOutlookAddIn** -Parameter in den Team-Besprechungsrichtlinien auf " **true** " festlegen. Eine schrittweise Anleitung zum Festlegen dieser Richtlinie finden Sie unter [Festlegen des Besprechungs Anbieters für Benutzer im Modus "Inseln"](meeting-policies-in-teams.md#meeting-policy-settings---meeting-provider-for-islands-mode).

## <a name="other-considerations"></a>Andere Überlegungen

Die Funktionen des Microsoft Teams-Besprechungs-Add-Ins werden noch weiterentwickelt. Beachten Sie daher Folgendes:

- Das Add-in "Teams-Besprechung" erfordert ein Exchange-Postfach für den primären Benutzer, der die Besprechung plant. Stellen Sie sicher, dass in Ihrem Outlook-Profil mindestens ein Exchange-Postfach konfiguriert ist, und verwenden Sie es, um Teams-Besprechungen mit dem Add-in zu planen. Informationen zu Exchange-Anforderungen finden Sie unter [Interaktion zwischen Exchange und Teams](https://docs.microsoft.com/microsoftteams/exchange-teams-interact).
- Das Add-In ist für geplante Besprechungen mit bestimmten Teilnehmern gedacht, nicht für Besprechungen in einem Kanal. Kanalbesprechungen müssen in Microsoft Teams geplant werden.
- Das Add-in funktioniert nicht, wenn sich ein Authentifizierungs Proxy im Netzwerkpfad der PC-und Team Dienste des Benutzers befindet.
- Benutzer können keine Liveereignisse von Outlook aus planen. Wechseln Sie zu Microsoft Teams, um Liveereignisse zu planen. Weitere Informationen finden Sie unter [Was sind Microsoft Teams-Liveereignisse?](teams-live-events/what-are-teams-live-events.md).

Weitere Informationen zu [Besprechungen und Anrufen in Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8)

## <a name="troubleshooting"></a>Problembehandlung

Führen Sie die folgenden Schritte aus, um Probleme mit dem Add-in "Teams-Besprechung" zu beheben.

### <a name="teams-meeting-add-in-in-outlook-for-windows-does-not-show"></a>Teambesprechung-Add-in in Outlook für Windows wird nicht angezeigt

Wenn Sie das Add-In für Teams-Besprechungen für Outlook nicht installieren können, versuchen Sie diese Schritte zur Problembehandlung.

[Laden](https://aka.ms/SaRA-TeamsAddInScenario) Sie den [Microsoft Support Recovery Assistant](https://aka.ms/SaRA_Home) herunter, und führen Sie ihn aus, um automatisierte Schritte zur Problembehandlung und Korrekturen auszuführen.

Alternativ können Sie die folgenden Schritte manuell ausführen:

- Benutzer von Windows 7 müssen das [Update für Universal C Runtime in Windows](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows) installieren, damit das Add-In für die Teams-Besprechung funktioniert.
- Überprüfen Sie, ob der Benutzer über eine Upgrade-Richtlinie für Teams verfügt, die das Planen von Besprechungen in Teams ermöglicht. Weitere Informationen finden Sie unter [Upgrade von Skype for Business in Teams](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-on-prem-overview#meetings) .
- Überprüfen Sie, ob der Benutzer über eine Team-Besprechungsrichtlinie verfügt, die das Outlook-Add-in zulässt. Weitere Informationen finden Sie unter [Verwalten von Besprechungsrichtlinien in Teams](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#allow-the-outlook-add-in) .
- Stellen Sie sicher, dass der Benutzer den Desktop Client von Teams installiert hat. Das Besprechungs-Add-in wird nicht installiert, wenn nur der Team-WebClient verwendet wird.
- Stellen Sie sicher, dass der Benutzer Outlook 2013 oder höher installiert hat.
- Stellen Sie sicher, dass der Benutzer die Berechtigung zum Ausführen regsvr32.exe hat.
- Stellen Sie sicher, dass alle verfügbaren Updates für Outlook-Desktop Client angewendet wurden.
- Führen Sie die folgenden Schritte aus:
  - Starten Sie den Teams-Desktopclient neu.
  - Melden Sie sich ab, und melden Sie sich dann wieder beim Teams-Desktopclient an.
  - Starten Sie den Outlook-Desktopclient neu. (Stellen Sie sicher, dass Outlook nicht im Administratormodus ausgeführt wird.)

Wenn das Add-in immer noch nicht angezeigt wird, stellen Sie sicher, dass es in Outlook nicht deaktiviert ist.

- Wählen Sie in Outlook **Datei** und dann **Optionen** aus.
- Wählen Sie im Dialogfeld Outlook- **Optionen** die Registerkarte **Add-ins** aus.
- Bestätigen Sie, dass das **Microsoft Teams-Besprechungs-Add-in für Microsoft Office** in der Liste der **aktiven Anwendungs-Add-ins** aufgeführt ist.
- Wenn das Team Besprechungs-Add-in in der Liste **Deaktivierte Anwendungs-Add-ins** aufgeführt ist, wählen Sie **com-Add-ins** in **Verwalten** aus, und wählen Sie dann **go aus.**
- Aktivieren Sie das Kontrollkästchen neben **Microsoft Teams-Besprechungs-Add-in für Microsoft Office**.
- Wählen Sie in allen Dialogfeldern **OK** aus, und starten Sie Outlook neu.

Allgemeine Anleitungen zum Verwalten von Add-Ins finden Sie unter [anzeigen, verwalten und Installieren von Add-Ins in Office-Programmen](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).

Wenn das Add-in immer noch nicht angezeigt wird, führen Sie die folgenden Schritte aus, um die Registrierungseinstellungen zu überprüfen.

> [!NOTE]
> Durch unsachgemäßes Bearbeiten der Registrierung kann Ihr System schwer beschädigt werden. Bevor Sie Änderungen an der Registrierung vornehmen, sollten Sie alle wichtigen Daten auf dem Computer sichern.
- Starten RegEdit.exe
- Navigieren zu HKEY_CURRENT_USER\Software\Microsoft\Office\Outlook\Addins
- Überprüfen Sie, ob TeamsAddin. FastConnect vorhanden ist.
- Überprüfen Sie in TeamsAddin. FastConnect, ob LoadBehavior vorhanden ist, und ist auf 3 festzulegen.
  - Wenn LoadBehavior einen anderen Wert als 3 aufweist, ändern Sie es in 3, und starten Sie Outlook neu.

### <a name="delegate-scheduling-does-not-work"></a>Das Delegieren der Terminplanung funktioniert nicht

Wenn Ihr Administrator Microsoft Exchange so konfiguriert hat, [dass der Zugriff auf Exchange Web Server (EWS)](https://docs.microsoft.com/exchange/client-developer/exchange-web-services/how-to-control-access-to-ews-in-exchange) gesteuert wird, ist ein Stellvertreter nicht in der Lage, eine Microsoft Teams-Besprechung im Namen des Vorgesetzten zu planen. Die Lösung für diese Konfiguration befindet sich noch in der Entwicklung und wird demnächst veröffentlicht. Um dieses Problem zu umgehen, kann Ihr Administrator die folgende Zeichenfolge zur Zulassungsliste für EWS hinzufügen: " *SchedulingService* ". 


## <a name="related-topics"></a>Verwandte Themen

[Teams-Problembehandlung](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
