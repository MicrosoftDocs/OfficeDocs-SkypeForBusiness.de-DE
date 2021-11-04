---
title: Verwenden des Microsoft Teams-Besprechungs-Add-Ins in Outlook
author: cichur
ms.author: v-mahoffman
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
ms.localizationpriority: high
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
ms.openlocfilehash: 687bd993eb972a1d459812a54f81e364b9d64a22
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60749111"
---
# <a name="use-the-teams-meeting-add-in-in-outlook"></a>Verwenden des Microsoft Teams-Besprechungs-Add-Ins in Outlook

Mit dem Microsoft Teams-Besprechungs-Add-Ins können Benutzer eine Teambesprechung von Outlook aus planen. Das Add-in ist für Outlook unter Windows, Mac, im Web und Mobile verfügbar.

## <a name="teams-meeting-add-in-in-outlook-for-windows"></a>Microsoft Teams-Besprechungs-Add-In in Outlook für Windows

Das Microsoft Teams-Besprechungs-Add-In wird für Benutzer, auf deren Windows-PC Microsoft Teams und entweder Office 2013, Office 2016 oder Office 2019 installiert ist, automatisch installiert. Die Benutzer sehen auf dem Menüband „Kalender“ in Outlook das Microsoft Teams-Besprechungs-Add-In.

![Screenshot des Teams-Besprechungs-Add-Ins auf dem Outlook-Menüband.](media/Teams-add-in-for-Outlook.png)

> [!NOTE]
> - Es gibt **keine direkte URL**, die auf das Microsoft Teams-Add-In verweist.
> - Wenn in Ihrer Organisation sowohl Microsoft Teams als auch Skype for Business ausgeführt werden, sind ein paar zusätzliche Dinge zu bedenken. Unter bestimmten Umständen ist das Microsoft Teams-Add in Outlook nicht verfügbar. Einzelheiten hierzu finden Sie unter [Upgrade von Skype for Business auf Microsoft Teams](upgrade-to-Teams-on-prem-tools.md).
> - Benutzerberechtigungen zum Ausführen der Datei „Regsvr32.exe“ sind eine Mindestanforderung, damit das Add-In für „Teams Meeting“ auf dem Computer installiert wird.
> - Wenn Benutzer das Microsoft Teams-Besprechungs-Add-In nicht sehen, weisen Sie sie an, Outlook und Microsoft Teams zu schließen, den Microsoft Teams-Client neu zu starten, sich bei Microsoft Teams anzumelden und den Outlook-Client zu starten (in dieser Reihenfolge).
> - Wenn Sie eine Office Outlook-Installation aus dem Microsoft Store verwenden, wird das Add-In für „Teams Meeting“ nicht unterstützt. Benutzern, die dieses Add-In benötigen, wird empfohlen, die Klick-und-Los-Version von Office zu installieren, wie im Artikel [Office unter Windows 10 im S-Modus](https://support.office.com/article/faq-office-on-windows-10-in-s-mode-717193b5-ff9f-4388-84c0-277ddf07fe3f) beschrieben.

## <a name="teams-meeting-add-in-in-outlook-for-mac"></a>Teams Meeting-Add-In in Outlook für Mac

Die Schaltfläche "Teams-Besprechung" in Outlook für Mac wird im Menüband von Outlook für Mac angezeigt, wenn Outlook im Produktions-Build 16.24.414.0 und höher ausgeführt und mit einem Microsoft 365- oder Office 365-Kundenabonnement aktiviert wird.

Die Besprechungskoordinaten (der Link zum Beitreten zu einer Teams-Besprechung und die Einwahlnummern) werden der Besprechungseinladung hinzugefügt, nachdem der Benutzer auf **Senden** geklickt hat.  

## <a name="teams-meeting-add-in-in-outlook-web-app"></a>Microsoft Teams-Besprechungs-Add-In in Outlook Web App

Die Schaltfläche „Teams-Besprechungen“ in Outlook Web App wird als Teil der neuen Ereigniserstellung angezeigt, wenn der Benutzer eine frühe Version des neuen Outlook im Web verwendet. Informationen dazu, wie Benutzer die frühe Version des neuen Outlook im Web testen können, finden Sie im [Outlook-Blog](https://techcommunity.microsoft.com/t5/Outlook-Blog/Designed-to-be-fast-The-Outlook-on-the-web-user-experience-gets/ba-p/234909?utm_source=t.co&utm_medium=referral).

![Screenshot des Teams-Besprechungs-Add-Ins in Outlook Web App.](media/teams-meeting-add-in-web.png)

Die Besprechungskoordinaten (der Link zum Beitreten zur Teams-Besprechung und Einwahlnummern) werden der Besprechungseinladung hinzugefügt, nachdem der Benutzer auf **Senden** geklickt hat.  

## <a name="teams-meeting-add-in-in-outlook-mobile-ios-and-android"></a>Microsoft Teams-Besprechungs-Add-in in Outlook Mobile (iOS und Android)

Die Schaltfläche „Teams-Besprechung“ wird in den neuesten Builds der Outlook-App für iOS-und Android angezeigt.

![Screenshot des Teams-Besprechungs-Add-Ins in Outlook Mobile.](media/teams-meeting-add-in-mobile.png)

Die Besprechungskoordinaten (der Link zum Beitreten zur Teams-Besprechung und Einwahlnummern) werden der Besprechungseinladung hinzugefügt, nachdem der Benutzer auf **Senden** geklickt hat.  

## <a name="teams-meeting-add-in-and-findtime-for-outlook"></a>Microsoft Teams-Besprechungs-Add-In und "Uhrzeit finden" für Outlook

"Uhrzeit finden" ist ein Add-In für Outlook, das Benutzern dabei hilft, sich hinsichtlich des Besprechungszeitpunkts in Unternehmen zu einigen. Sobald die Besprechungsteilnehmer ihren bevorzugten Zeitpunkt angegeben haben, sendet Uhrzeit finden die Besprechungseinladung im Namen des Benutzers. Wenn die Option **Onlinebesprechung** in Uhrzeit finden ausgewählt ist, plant Uhrzeit finden eine Skype for Business- oder eine Microsoft Teams-Besprechung. (Die von Uhrzeit finden verwendete Option hängt von dem standardmäßigen Onlinebesprechungskanal ab, der von Ihrer Organisation festgelegt wurde.)

> [!NOTE]  
> Wenn Sie eine Skype for Business-Einstellung in Ihrem [Uhrzeit finden-Dashboard](https://findtime.microsoft.com/UserDashboard) gespeichert haben, wird diese anstelle von Microsoft Teams von Uhrzeit finden verwendet. Wenn Sie Microsoft Teams verwenden möchten, löschen Sie die Skype for Business-Einstellung in Ihrem Dashboard.

Weitere Informationen finden Sie unter [Planen von Besprechungen mit "Uhrzeit finden"](https://support.office.com/article/scheduling-meetings-with-findtime-4dc806ed-fde3-4ea7-8c5e-b5d1fddab4a6).

## <a name="authentication-requirements"></a>Authentifizierungsanforderungen

Benutzer des Microsoft Teams-Besprechungs-Add-Ins müssen sich mit moderner Authentifizierung bei Microsoft Teams anmelden. Wenn sich Benutzer nicht mit dieser Methode anmelden, können sie zwar den Microsoft Teams-Client verwenden, aber sie können keine [Microsoft Teams-Onlinebesprechungen](https://www.microsoft.com/microsoft-teams/online-meetings) mithilfe des Outlook-Add-In planen. Dies können Sie mit einer der folgenden Methoden korrigieren:

- Wenn die moderne Authentifizierung für Ihre Organisation nicht konfiguriert ist, sollten Sie sie konfigurieren.
- Wenn die moderne Authentifizierung konfiguriert ist, aber die Benutzer den Vorgang im Dialogfeld abgebrochen haben, weisen Sie die Benutzer an, sich mit mehrstufiger Authentifizierung erneut anzumelden.

Weitere Informationen zum Konfigurieren der Authentifizierung finden Sie unter [Identitätsmodelle und Authentifizierung in Microsoft Teams](identify-models-authentication.md).

## <a name="enable-private-meetings"></a>Aktivieren von privaten Besprechungen

Die Option **Zeitplanung für private Besprechungen zulassen** muss im Microsoft Teams Admin Center aktiviert sein, damit das Add-In bereitgestellt wird. Wechseln Sie im Admin Center zu **Besprechungen** > **Besprechungsrichtlinien**, und legen Sie im Abschnitt **Allgemein** **Zeitplanung für private Besprechungen zulassen** auf „Aktiviert“ fest.)

![Screenshot der Einstellungen im Microsoft Teams Admin Center.](media/teams-add-in-for-outlook-image1.png)

Der Microsoft Teams-Client ermittelt, ob die Benutzer die 32-Bit- oder 64-Bit-Version benötigen, und installiert dann das richtige Add-In.

> [!NOTE]
> Möglicherweise müssen die Benutzer Outlook nach einer Installation oder einem Upgrade von Microsoft Teams neu starten, um das aktuelle Add-In zu erhalten.

## <a name="teams-upgrade-policy-and-the-teams-meeting-add-in-for-outlook"></a>Microsoft Teams-Upgrade-Richtlinie und das Microsoft Teams-Besprechungs-Add-In für Outlook

Kunden können [von Skype for Business auf Microsoft Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md) umsteigen. Mandantenadministratoren können den Teams-Modus „Koexistenz“ verwenden, um diesen Umstieg für ihre Benutzer zu definieren. Mandantenadministratoren haben die Möglichkeit, die Nutzung von Teams zusammen mit Skype for Business (Inselmodus) zu ermöglichen.

Wenn Benutzer im Inselmodus eine Besprechung in Outlook planen, erwarten sie in der Regel, dass sie auswählen können, ob Sie eine Skype for Business- oder eine Microsoft Teams-Besprechung planen. In Outlook im Web, Outlook für Windows und Outlook für Mac werden Benutzern standardmäßig sowohl Skype for Business- als auch Microsoft Teams-Add-Ins angezeigt, wenn sie den Inselmodus verwenden. Sie können eine Richtlinieneinstellung für Microsoft Teams-Besprechungen konfigurieren, um zu steuern, ob Benutzer im Inselmodus nur das Microsoft Teams-Besprechungs-Add-In oder sowohl dieses als auch das Skype for Business-Besprechungs-Add-In verwenden können.

Aufgrund bestimmter Einschränkungen in der ersten Version kann Outlook Mobile nur das Erstellen von Besprechungen in Skype for Business **oder** Microsoft Teams unterstützen. Details finden Sie in der folgenden Tabelle.

| Koexistenzmodus im Microsoft Teams Admin Center | Standardmäßiger Besprechungsanbieter in Outlook Mobile |
| --------------------------------------|---------------------------------------------|
| Inselmodus | Skype for Business |
| Nur Skype for Business | Skype for Business |
| Skype for Business mit Zusammenarbeit in Microsoft Teams | Skype for Business |
| Skype for Business mit Zusammenarbeit und Besprechungen in Microsoft Teams | Microsoft Teams |
| Nur Microsoft Teams | Microsoft Teams |

### <a name="set-whether-users-in-islands-mode-can-only-use-the-teams-meeting-add-in-or-both-the-teams-meeting-and-skype-for-business-meeting-add-ins"></a>Legen Sie fest, ob Benutzer im Inselmodus nur das Microsoft Teams-Besprechungs-Add-In oder sowohl dieses als auch das Skype for Business-Besprechungs-Add-In verwenden können.

Als Administrator können Sie eine Richtlinieneinstellung für Microsoft Teams-Besprechungen konfigurieren, um zu steuern, welches Outlook-Besprechungs-Add-in für *Benutzern im Inselmodus* verwendet wird. Sie können festlegen, ob Benutzer nur das Add-In für Microsoft Teams-Besprechungen oder sowohl das Add-In für Microsoft Teams-Besprechungen als auch jenes für Skype for Business-Besprechungen verwenden können, um Besprechungen in Outlook zu planen.

Sie können diese Richtlinie nur für Benutzer im Inselmodus anwenden und für die der Parameter **AllowOutlookAddIn** in ihrer Microsoft Teams-Richtlinie auf **True** festgelegt ist. Die Schritte zum Einrichten dieser Richtlinie finden Sie unter [Einstellungen für Besprechungsrichtlinien – Allgemein](meeting-policies-in-teams-general.md#meeting-provider-for-islands-mode).

## <a name="other-considerations"></a>Andere Überlegungen

Die Funktionen des Microsoft Teams-Besprechungs-Add-Ins werden noch weiterentwickelt. Beachten Sie daher Folgendes:

- Für das Microsoft Teams-Besprechungs-Add-In ist ein Exchange-Postfach für den primären Benutzer erforderlich, der die Besprechung plant. Stellen Sie sicher, dass Sie in Ihrem Outlook-Profil über mindestens ein konfiguriertes Exchange-Postfach verfügen, und verwenden Sie es, um Microsoft Teams-Besprechungen mit dem Add-In zu planen. Informationen zu den Exchange-Anforderungen finden Sie unter [, Wie Exchange und Microsoft Teams interagieren](./exchange-teams-interact.md).
- Das Add-In ist für geplante Besprechungen mit bestimmten Teilnehmern gedacht, nicht für Besprechungen in einem Kanal. Kanalbesprechungen müssen in Microsoft Teams geplant werden.
- Das Add-In funktioniert nicht, wenn sich im Netzwerkpfad zwischen dem PC des Benutzers und den Microsoft Teams-Diensten ein Authentifizierungsproxy befindet.
- Benutzer können keine Liveereignisse von Outlook aus planen. Wechseln Sie zu Microsoft Teams, um Liveereignisse zu planen. Weitere Informationen finden Sie unter [Was sind Microsoft Teams-Liveereignisse?](teams-live-events/what-are-teams-live-events.md).

Erfahren Sie mehr über [Besprechungen und Anrufen in Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).

## <a name="troubleshooting"></a>Problembehandlung

Führen Sie die folgenden Schritte aus, um Probleme mit dem Microsoft Teams-Besprechungs-Add-In zu beheben.

### <a name="teams-meeting-add-in-in-outlook-for-windows-does-not-show"></a>Das Microsoft Teams-Besprechungs-Add-In wird in Outlook für Windows nicht angezeigt

Wenn Sie das Add-In für Microsoft Teams-Besprechungen für Outlook nicht installieren können, versuchen Sie diese Schritte zur Problembehandlung.

[Laden Sie](https://aka.ms/SaRA-TeamsAddInScenario) den [Microsoft Support-Wiederherstellungsassistenten](https://aka.ms/SaRA_Home) herunter und führen Sie ihn aus, um automatisierte Problembehandlungsmaßnahmen und Fixes durchzuführen.

Sie können aber auch die folgenden Schritte manuell ausführen:

- Benutzer von Windows 7 müssen das [Update für Universal C Runtime in Windows](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows) installieren, damit das Add-In für Microsoft Teams-Besprechung funktioniert.
- Überprüfen Sie, ob der Benutzer über eine Upgrade-Richtlinie für Microsoft Teams verfügt, die das Planen von Besprechungen in Microsoft Teams ermöglicht. Weitere Informationen hierzu finden Sie unter [Upgrade von Skype for Business auf Microsoft Teams](/microsoftteams/upgrade-to-teams-on-prem-overview#meetings).
- Überprüfen Sie, ob der Benutzer über eine Microsoft Teams-Besprechungsrichtlinie verfügt, die das Outlook-Add-In zulässt. Weitere Details finden Sie unter [Einstellungen für Besprechungsrichtlinien – Allgemein](./meeting-policies-in-teams-general.md#allow-the-outlook-add-in).
- Stellen Sie sicher, dass der Benutzer den Microsoft Teams-Desktopclient installiert hat. Das Besprechungs-Add-In wird nicht installiert, wenn nur der Microsoft Teams-Webclient verwendet wird.
- Stellen Sie sicher, dass der Benutzer Outlook 2013 oder höher installiert hat.
- Stellen Sie sicher, dass der Benutzer über die Berechtigung zum Ausführen von "regsvr32.exe" verfügt.
- Stellen Sie sicher, dass alle verfügbaren Updates für den Outlook-Desktopclient angewendet wurden.
- Führen Sie die folgenden Schritte aus:
  - Starten Sie den Teams-Desktopclient neu.
  - Melden Sie sich ab, und melden Sie sich dann wieder beim Teams-Desktopclient an.
  - Starten Sie den Outlook-Desktopclient neu. (Stellen Sie sicher, dass Outlook nicht im Admin-Modus ausgeführt wird.)

Wenn das Add-In immer noch nicht angezeigt wird, stellen Sie sicher, dass es in Outlook nicht deaktiviert ist.

- Wählen Sie in Outlook **Datei** und dann **Optionen** aus.
- Wählen Sie im Dialogfeld **Outlook-Optionen** die Registerkarte **Add-Ins** aus.
- Vergewissern Sie sich, dass das **Microsoft Teams-Besprechungs-Add-In für Microsoft Office** in der Liste **Aktive Anwendungs-Add-Ins** aufgeführt ist.
- Wenn das Add-In in der Liste **Deaktivierte Anwendung-Add-Ins** aufgeführt ist, wählen Sie unter **Verwalten** die Option **COM-Add-Ins** und dann **Los ...** aus.
- Aktivieren Sie das Kontrollkästchen neben **Microsoft Teams-Besprechungs-Add-in für Microsoft Office**.
- Wählen Sie in allen Dialogfeldern **OK** aus, und starten Sie Outlook erneut.

Eine allgemeine Anleitung zum Verwalten von Add-Ins finden Sie unter [Anzeigen, Verwalten und Installieren von Add-Ins in Office-Programmen](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).

Wenn das Add-In noch immer nicht angezeigt wird, führen Sie die folgenden Schritte aus, um die Registrierungseinstellungen zu überprüfen.

> [!NOTE]
> Durch eine fehlerhafte Bearbeitung der Registrierung können schwerwiegende Schäden am System verursacht werden. Bevor Sie Änderungen an der Registrierung vornehmen, sollten Sie alle wichtigen Computerdaten sichern.
- Starten Sie RegEdit.exe.
- Wechseln Sie zu "HKEY_CURRENT_USER\Software\Microsoft\Office\Outlook\Addins".
- Überprüfen Sie, ob "TeamsAddin.FastConnect" vorhanden ist.
- Vergewissern Sie sich, dass in"TeamsAddin.FastConnect" "LoadBehavior" vorhanden ist und auf "3" festgelegt ist.
  - Wenn "LoadBehavior" einen anderen Wert als 3 aufweist, ändern Sie diesen auf 3, und starten Sie Outlook erneut.

### <a name="delegate-scheduling-does-not-work"></a>Das Delegieren der Planung funktioniert nicht

Wenn Ihr Administrator Microsoft Exchange so konfiguriert hat, [dass der Zugriff auf Exchange Web Server (EWS)](/exchange/client-developer/exchange-web-services/how-to-control-access-to-ews-in-exchange) gesteuert wird, ist ein Stellvertreter nicht in der Lage, eine Microsoft Teams-Besprechung im Namen des Vorgesetzten zu planen. Die Lösung für diese Konfiguration befindet sich noch in der Entwicklung und wird demnächst veröffentlicht. Zur Problemumgehung kann Ihr Administrator die folgende Zeichenfolge zur EWS-Zulassungsliste hinzufügen: "*SchedulingService*". 


## <a name="related-topics"></a>Verwandte Themen

- [Teams-Problembehandlung](/MicrosoftTeams/troubleshoot/teams)

- [Planen Sie eine Microsoft Teams-Besprechung über Outlook](https://support.microsoft.com/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f)
