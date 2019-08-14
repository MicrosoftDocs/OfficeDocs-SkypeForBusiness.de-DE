---
title: Verwenden des Microsoft Teams-Besprechungs-Add-Ins in Outlook
author: ChuckEdmonson
ms.author: chucked
manager: serdars
audience: Admin
ms.date: 06/25/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams installiert in Outlook ein Add-In, mit dem Benutzer Microsoft Teams-Besprechungen über Outlook planen können.
ms.custom:
- NewAdminCenter_Update
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8e2c7bae819037d0140fab1fed3625e250b8a4c1
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36241788"
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a>Verwenden des Microsoft Teams-Besprechungs-Add-Ins in Outlook
=======================================

Mit dem Microsoft Teams-Besprechungs-Add-Ins können Benutzer eine Teambesprechung von Outlook aus planen. Das Add-in ist für Outlook unter Windows, Mac, im Web und Mobile verfügbar.

## <a name="teams-meeting-add-in-in-outlook-for-windows"></a>Microsoft Teams-Besprechungs-Add-In in Outlook für Windows

Das Microsoft Teams-Besprechungs-Add-In wird für Benutzer, auf deren Windows-PC Microsoft Teams und entweder Office 2010, Office 2013 oder Office 2016 installiert ist, automatisch installiert. Die Benutzer sehen auf dem Menüband „Kalender“ in Outlook das Microsoft Teams-Besprechungs-Add-In.

![Screenshot des Microsoft Teams-Add-Ins auf dem Outlook-Menüband](media/Teams-add-in-for-Outlook.png)

> [!NOTE]
> - Wenn Benutzer das Microsoft Teams-Besprechungs-Add-In nicht sehen, weisen Sie sie an, Outlook und Microsoft Teams zu schließen, den Microsoft Teams-Client neu zu starten, sich bei Microsoft Teams anzumelden und den Outlook-Client zu starten (in dieser Reihenfolge).
> - Benutzer von Windows 7 müssen das [Update für Universal C Runtime in Windows](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows) installieren, damit das Add-In für die Teams-Besprechung funktioniert.

## <a name="teams-meeting-add-in-in-outlook-for-mac"></a>Microsoft Teams-Besprechungs-Add-In in Outlook für Mac

Die Schaltfläche „Teams-Besprechung“ wird im Menüband von Outlook für Mac angezeigt, wenn Outlook in Produktions-Build 16.24.414.0 und höher ausgeführt wird.

Die Besprechungskoordinaten (der Link zum Beitreten zur Teams-Besprechung und Einwahlnummern) werden der Besprechungseinladung hinzugefügt, nachdem der Benutzer auf **Senden** geklickt hat.  

## <a name="teams-meeting-add-in-in-outlook-web-app"></a>Microsoft Teams-Besprechungs-Add-In in Outlook Web App

Die Schaltfläche „Teams-Besprechungen“ in Outlook Web App wird als Teil der neuen Ereigniserstellung angezeigt, wenn der Benutzer eine frühe Version des neuen Outlook im Web verwendet. Informationen dazu, wie Benutzer die frühe Version des neuen Outlook im Web testen können, finden Sie im [Outlook-Blog](https://techcommunity.microsoft.com/t5/Outlook-Blog/Designed-to-be-fast-The-Outlook-on-the-web-user-experience-gets/ba-p/234909?utm_source=t.co&utm_medium=referral).

![Screenshot des Microsoft Teams-Add-Ins in Outlook Web App](media/teams-meeting-add-in-web.png)

Die Besprechungskoordinaten (der Link zum Beitreten zur Teams-Besprechung und Einwahlnummern) werden der Besprechungseinladung hinzugefügt, nachdem der Benutzer auf **Senden** geklickt hat.  

## <a name="teams-meeting-add-in-in-outlook-mobile-ios-and-android"></a>Microsoft Teams-Besprechungs-Add-in in Outlook Mobile (iOS und Android)

Die Schaltfläche „Teams-Besprechung“ wird in den neuesten Builds der Outlook-App für iOS-und Android angezeigt.

![Screenshot des Microsoft Teams-Add-Ins in Outlook Mobile](media/teams-meeting-add-in-mobile.png)

Die Besprechungskoordinaten (der Link zum Beitreten zur Teams-Besprechung und Einwahlnummern) werden der Besprechungseinladung hinzugefügt, nachdem der Benutzer auf **Senden** geklickt hat.  

## <a name="teams-meeting-add-in-in-and-findtime-for-outlook"></a>Microsoft Teams-Besprechungs-Add-In und Uhrzeit finden für Outlook
Uhrzeit finden ist ein Add-In für Outlook, das Benutzern dabei hilft, sich hinsichtlich des Besprechungszeitpunkts in Unternehmen zu einigen. Sobald die Besprechungsteilnehmer ihren bevorzugten Zeitpunkt angegeben haben, sendet Uhrzeit finden die Besprechungseinladung im Namen des Benutzers. Wenn die Option **Onlinebesprechung** in Uhrzeit finden ausgewählt ist, plant Uhrzeit finden eine Skype for Business- oder eine Microsoft Teams-Besprechung. (Die von Uhrzeit finden verwendete Option hängt von dem standardmäßigen Onlinebesprechungskanal ab, der von Ihrer Organisation festgelegt wurde.)

> [!NOTE]  
> Wenn Sie eine Skype for Business-Einstellung in Ihrem [Uhrzeit finden-Dashboard](https://findtime.microsoft.com/UserDashboard) gespeichert haben, wird diese anstelle von Microsoft Teams von Uhrzeit finden verwendet. Wenn Sie Microsoft Teams verwenden möchten, löschen Sie die Skype for Business-Einstellung in Ihrem Dashboard.

Weitere Informationen finden Sie unter [Planen von Besprechungen mit Uhrzeit finden](https://support.office.com/article/scheduling-meetings-with-findtime-4dc806ed-fde3-4ea7-8c5e-b5d1fddab4a6).

## <a name="authentication-requirements"></a>Authentifizierungsanforderungen

Benutzer des Microsoft Teams-Besprechungs-Add-Ins müssen sich mit moderner Authentifizierung bei Microsoft Teams anmelden. Wenn sich Benutzer nicht mit dieser Methode anmelden, können sie zwar den Microsoft Teams-Client verwenden, aber sie können keine Microsoft Teams-Onlinebesprechungen mit dem Outlook-Add-In planen. Dies können Sie mit einer der folgenden Methoden korrigieren:

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

Wenn Benutzer im Inselmodus eine Besprechung in Outlook planen, erwarten sie in der Regel, dass sie auswählen können, ob Sie eine Skype for Business- oder eine Microsoft Teams-Besprechung planen. In Outlook im Web, Outlook für Windows und Outlook für Mac werden Benutzern sowohl Skype for Business- als auch Microsoft Teams-Add-Ins angezeigt, wenn sie den Inselmodus verwenden. Aufgrund bestimmter Einschränkungen in der ersten Version kann Outlook Mobile nur das Erstellen von Besprechungen in Skype for Business **oder** Microsoft Teams unterstützen. Details finden Sie in der folgenden Tabelle.

| Koexistenzmodus im Microsoft Teams Admin Center | Standardmäßiger Besprechungsanbieter in Outlook Mobile |
| --------------------------------------|---------------------------------------------|
| Inselmodus | Skype for Business |
| Nur Skype for Business | Skype for Business |
| Skype for Business mit Zusammenarbeit in Microsoft Teams | Skype for Business |
| Skype for Business mit Zusammenarbeit und Besprechungen in Microsoft Teams | Microsoft Teams |
| Nur Microsoft Teams | Microsoft Teams |

## <a name="other-considerations"></a>Andere Überlegungen

Die Funktionen des Microsoft Teams-Besprechungs-Add-Ins werden noch weiterentwickelt. Beachten Sie daher Folgendes:

- Das Add-In ist für geplante Besprechungen mit bestimmten Teilnehmern gedacht, nicht für Besprechungen in einem Kanal. Kanalbesprechungen müssen in Microsoft Teams geplant werden.
- Das Add-In funktioniert nicht, wenn sich im Netzwerkpfad zwischen dem PC des Benutzers und den Microsoft Teams-Diensten ein Authentifizierungsproxy befindet.
- Benutzer können keine Liveereignisse von Outlook aus planen. Wechseln Sie zu Microsoft Teams, um Liveereignisse zu planen. Weitere Informationen finden Sie unter [Was sind Microsoft Teams-Liveereignisse?](teams-live-events/what-are-teams-live-events.md).

## <a name="troubleshooting"></a>Problembehandlung

Wenn Sie das Add-In für Teams-Besprechungen für Outlook nicht installieren können, versuchen Sie diese Schritte zur Problembehandlung.

- Stellen Sie sicher, dass alle verfügbaren Updates für den Outlook-Desktopclient angewendet wurden.
- Starten Sie den Teams-Desktopclient neu.
- Melden Sie sich ab, und melden Sie sich dann wieder beim Teams-Desktopclient an.
- Starten Sie den Outlook-Desktopclient neu. (Stellen Sie sicher, dass Outlook nicht im Admin-Modus ausgeführt wird.)
- Stellen Sie sicher, dass der Name des angemeldeten Benutzerkontos keine Leerzeichen enthält. (Dies ist ein bekanntes Problem, das in einem zukünftigen Update behoben wird.)
- Stellen Sie sicher, dass Single Sign-On (SSO) aktiviert ist.

Wenn Ihr Administrator Microsoft Exchange so konfiguriert hat, [dass der Zugriff auf Exchange Web Server (EWS)](https://docs.microsoft.com/de-DE/exchange/client-developer/exchange-web-services/how-to-control-access-to-ews-in-exchange) gesteuert wird, ist ein Stellvertreter nicht in der Lage, eine Microsoft Teams-Besprechung im Namen des Vorgesetzten zu planen. Die Lösung für diese Konfiguration befindet sich noch in der Entwicklung und wird demnächst veröffentlicht. 

Eine allgemeine Anleitung zum Deaktivieren von Add-Ins finden Sie unter [Anzeigen, Verwalten und Installieren von Add-Ins in Office-Programmen](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).

Weitere Informationen zu [Besprechungen und Anrufen in Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8)
