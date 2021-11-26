---
title: Verwalten allgemeiner Besprechungsrichtlinien
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.general
- seo-marvel-apr2020
description: Erfahren Sie, wie Sie allgemeine Besprechungsrichtlinieneinstellungen in ihrer Teams.
ms.openlocfilehash: b7c08799ee9e7c2b1e6239b17abaa66b7d1e3d47
ms.sourcegitcommit: 7cc7e237b0da270c9cf4a3e535db16dd113e4300
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2021
ms.locfileid: "61177936"
---
# <a name="meeting-policy-settings---general"></a>Besprechungsrichtlinien – Allgemeine Einstellungen

<a name="bkgeneral"> </a>

In diesem Artikel werden die folgenden allgemeinen Richtlinieneinstellungen für Besprechungen Teams beschrieben:

- [Jetzt in Kanälen treffen](#meet-now-in-channels)
- [Outlook-Add-In](#outlook-add-in)
- [Planen von Kanal-Besprechungen](#channel-meeting-scheduling)
- [Private Besprechungsplanung](#private-meeting-scheduling)
- [Sofortbesprechungen in privaten Besprechungen](#meet-now-in-private-meetings)
- [Designierter Presenter-Rollenmodus](#designated-presenter-role-mode)
- [Einsatzbericht](#engagement-report)
- [Besprechungsregistrierung](#meeting-registration)
- [Wer kann registriert werden](#who-can-register)
- [Besprechungsanbieter für den Islands-Modus](#meeting-provider-for-islands-mode)

## <a name="meet-now-in-channels"></a>Jetzt in Kanälen treffen

Hierbei handelt es sich um eine benutzerspezifische Richtlinie, die angewendet wird, bevor eine Besprechung beginnt. Mit dieser Einstellung wird festgelegt, ob ein Benutzer eine Ad-hoc-Besprechung in einem Teams starten kann. Wenn Sie dies aktivieren,  können die Benutzer auf die Schaltfläche Besprechung klicken, um eine Ad-hoc-Besprechung zu starten oder eine Besprechung im Kanal zu planen. Der Standardwert lautet "True".

[![Screenshot des Symbols "Jetzt treffen" unter einer Nachricht ](media/meeting-policies-meet-now.png) ](media/meeting-policies-meet-now.png#lightbox)

## <a name="outlook-add-in"></a>Outlook-Add-In

Hierbei handelt es sich um eine benutzerspezifische Richtlinie, die angewendet wird, bevor eine Besprechung beginnt. Über diese Einstellung wird gesteuert, ob Microsoft Teams-Besprechungen in Outlook (Windows, Mac, Web und Mobile) geplant werden können.

![Screenshot zeigt die Funktion zur Planung einer neuen Besprechung.](media/meeting-policies-outlook-add-in.png)

Wenn Sie dies deaktivieren, können die Benutzer keine Besprechungen Teams planen, wenn sie eine neue Besprechung in einem Outlook. In Outlook unter Windows wird beispielsweise die Option **Neue Teams-Besprechung** nicht im Menüband angezeigt.

## <a name="channel-meeting-scheduling"></a>Planen von Kanal-Besprechungen

Verwenden Sie die vorhandene "AllowChannelMeetingScheduling"-Richtlinie, um zu steuern, welche Arten von Ereignissen in den Kalendern des Team-Kanals erstellt werden können. Hierbei handelt es sich um eine benutzerspezifische Richtlinie, die angewendet wird, bevor eine Besprechung beginnt. Über diese Einstellung wird gesteuert, ob Benutzer eine Besprechung in einem Microsoft Teams-Kanal planen können. Diese Einstellung ist standardmäßig aktiviert. 

Wenn diese Richtlinie deaktiviert ist, können die Benutzer keine neuen Kanalbesprechungen erstellen. Bereits vorhandene Kanalbesprechungen können jedoch vom Organisator der Veranstaltung bearbeitet werden.

Die Option zum Planen von Besprechungen ist dann deaktiviert.

![Screenshot der Option "Besprechung planen" in Teams.](media/schedule-meeting-option.png)

Die Option zum Auswählen eines Kanals ist deaktiviert.

[![Screenshot mit der Kalenderoption zum Auswählen eines Kanals, in dem Sie eine Besprechung planen möchten. ](media/meeting-policies-select-a-channel-to-meet-in.png) ](media/meeting-policies-select-a-channel-to-meet-in.png#lightbox)

Auf der Seite Beiträge des Kanals wird Folgendes deaktiviert:

- Die Schaltfläche **Besprechung planen** im Feld zum Verfassen von Kanalantworten
  ![Screenshot mit der Kalenderoption zum Auswählen eines Kanals, in dem Sie eine Besprechung planen möchten.](media/schedule-meeting-disabled-in-chat2.png)
  
- Die Schaltfläche **Besprechung planen** im Kanal-Header.
  ![Screenshot mit der Kalenderoption zum Auswählen eines Kanals, über den Sie eine Besprechung planen möchten.](media/schedule-now-in-header.png)

Im Kanal-Kalender:

- Die Schaltfläche **Neues Ereignis hinzufügen** im Header des Kanalkalenders ist deaktiviert.
  ![Screenshot mit der Kalenderoption zum Auswählen eines Kanals, der es Ihnen ermöglicht, eine Besprechung zu planen.](media/add-new-event-disabled.png)

- Benutzer können einen Zeitblock im Kanalkalender nicht ziehen und auswählen, um eine Kanal-Besprechung zu erstellen.

- Benutzer können keine Tastenkombinationen verwenden, um eine Besprechung im Kanalkalender zu erstellen.

Im Admin Center:

Die Kanalkalender-App wird auf der Seite der App-Berechtigungsrichtlinien im Abschnitt **Microsoft-Apps** angezeigt.

![Screenshot der App-Berechtigungsrichtlinie im Teams Admin Center.](media/manage-microsoft-apps-policy.png)

## <a name="private-meeting-scheduling"></a>Private Besprechungsplanung

Hierbei handelt es sich um eine benutzerspezifische Richtlinie, die angewendet wird, bevor eine Besprechung beginnt. Mit dieser Einstellung wird gesteuert, ob ein Benutzer private Besprechungen in einem Teams-Kanal planen kann. Eine Besprechung ist privat, wenn sie nicht in einem Kanal in einem Team veröffentlicht wird.

Beachten Sie, dass durch das Deaktivieren von **Planung privater Besprechungen zulassen** und **Planung von Kanalbesprechungen zulassen** die Optionen **Erforderliche Teilnehmer hinzufügen** und **Kanal hinzufügen** für Benutzer in Microsoft Teams deaktiviert werden. Diese Einstellung ist standardmäßig aktiviert.

## <a name="meet-now-in-private-meetings"></a>Sofortbesprechungen in privaten Besprechungen

Hierbei handelt es sich um eine benutzerspezifische Richtlinie, die angewendet wird, bevor eine Besprechung beginnt. Mit dieser Einstellung wird festgelegt, ob ein Benutzer eine private Ad-hoc-Besprechung starten kann.  Diese Einstellung ist standardmäßig aktiviert.

## <a name="designated-presenter-role-mode"></a>Designierter Presenter-Rollenmodus

Hierbei handelt es sich um eine benutzerspezifische Richtlinie. Diese Einstellung ermöglicht es Ihnen, den Standardwert für **Wer kann präsentieren?** in den **Besprechungsoptionen** im Microsoft Teams-Client zu ändern. Diese Richtlinieneinstellung wirkt sich auf alle Besprechungen aus, einschließlich Sofortbesprechungen.

Über die Einstellung **Wer kann präsentieren?** können Besprechungsorganisatoren die Referenten innerhalb einer Besprechung festlegen. Weitere Informationen finden Sie unter [Ändern der Teilnehmereinstellungen für eine Microsoft Teams-Besprechung](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e) und [Rollen in einer Microsoft Teams-Besprechung](https://support.microsoft.com/article/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019).

Derzeit können Sie diese Richtlinieneinstellung nur mithilfe von PowerShell konfigurieren. Sie können eine vorhandene Microsoft Teams-Besprechungsrichtlinie mithilfe des Cmdlets [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) bearbeiten. Sie können aber auch eine neue Besprechungsrichtlinie für Microsoft Teams mithilfe des Cmdlets [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) erstellen und sie Benutzern zuweisen.

Um den Standardwert für die Einstellung **Wer kann präsentieren?** in Microsoft Teams anzugeben, legen Sie den Parameter **DesignatedPresenterRoleMode** auf einen der folgenden Werte fest:

- **EveryoneUserOverride**: alle Besprechungsteilnehmer können Referenten sein. Dies ist der Standardwert. Dieser Parameter entspricht der Einstellung **Jeder** in Microsoft Teams.
- **EveryoneInCompanyUserOverride**: authentifizierte Benutzer in der Organisation, einschließlich Gastbenutzer, können Referenten sein. Dieser Parameter entspricht der Einstellung **Personen in meiner Organisation** in Microsoft Teams.
- **OrganizerOnlyUserOverride**: Nur der Besprechungsorganisator kann präsentieren, alle anderen Besprechungsteilnehmer sind lediglich als Teilnehmer angegeben. Dieser Parameter entspricht der Einstellung **Nur ich** in Microsoft Teams.

Bedenken Sie, dass, nachdem Sie den Standardwert festgelegt haben, Besprechungsorganisatoren diese Einstellung in Microsoft Teams weiterhin ändern und auswählen können, wer in den von ihnen geplanten Besprechungen präsentieren kann.

## <a name="engagement-report"></a>Einsatzbericht

Hierbei handelt es sich um eine benutzerspezifische Richtlinie. Über diese Einstellung wird gesteuert, ob Besprechungsorganisatoren den [Teilnahmebericht zu einer Besprechung](teams-analytics-and-reports/meeting-attendance-report.md) herunterladen können.

Diese Richtlinie ist standardmäßig deaktiviert und ermöglicht Es Ihren Organisatoren zu sehen, wer sich registriert hat und an den von ihnen eingerichteten Besprechungen und Webinaren teilgenommen hat. Um dies im Teams Admin Center zu aktivieren, wechseln Sie zu Besprechungsbesprechungsrichtlinien , und  >  legen Sie die Richtlinie auf **Aktiviert .**

Sie können eine vorhandene Microsoft Teams-Besprechungsrichtlinie mithilfe des Cmdlets [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) bearbeiten. Sie können aber auch eine neue Besprechungsrichtlinie für Microsoft Teams mithilfe des Cmdlets [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) erstellen und sie Benutzern zuweisen.

Damit ein Besprechungsorganisator den Bericht zur Besprechungsteilnahme herunterladen kann, legen Sie den Parameter **AllowEngagementReport** auf **Enabled (Aktiviert) festgelegt.** Wenn diese Option aktiviert ist, wird die Option zum Herunterladen des Berichts im Bereich **Teilnehmer** angezeigt. Diese Einstellung ist standardmäßig nicht aktiviert.

Um zu verhindern, dass der Bericht vom Besprechungsorganisator heruntergeladen wird, legen Sie den Parameter auf **Deaktiviert** (disabled) fest.

## <a name="meeting-registration"></a>Besprechungsregistrierung

Hierbei handelt es sich um eine benutzerspezifische Richtlinie. Wenn Sie dies aktivieren, können die Benutzer in Ihrer Organisation Webinare einrichten. Diese Richtlinie ist standardmäßig aktiviert.

Wenn Sie diese Richtlinie im Teams Admin Center bearbeiten möchten, wechseln Sie zu **Besprechungsbesprechungsrichtlinien**  >  . Um die Besprechungsregistrierung zu deaktivieren, legen Sie die Richtlinie auf **Aus .**

Sie können eine vorhandene Microsoft Teams-Besprechungsrichtlinie mithilfe des Cmdlets [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) bearbeiten. Sie können aber auch eine neue Besprechungsrichtlinie für Microsoft Teams mithilfe des Cmdlets [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) erstellen und sie Benutzern zuweisen.

Um die Besprechungsregistrierung zu aktivieren, legen Sie den **Parameter MeetingRegistration** auf **True (Wahr) festgelegt.** Diese ist standardmäßig **auf True** festgelegt.

Um die Besprechungsregistrierung zu deaktivieren und zu verhindern, dass Benutzer Webinare planen, legen Sie den Parameter auf **False ..**

## <a name="who-can-register"></a>Wer kann registriert werden

Diese Richtlinie steuert, welche Benutzer Webinare registrieren und teilnehmen können. Diese Richtlinie bietet zwei Optionen, die nur verfügbar sind, wenn **die** Besprechungsregistrierung aktiviert ist.

- Legen **Wer** kann sich  für Jeder registrieren, wenn Sie zulassen möchten, dass jeder , auch anonyme Benutzer, Webinare registriert und daran teilnehmen kann, die von Benutzern in Ihrer Organisation eingerichtet werden.
- Legen **Wer kann sich** für Jeden **in** der Organisation registrieren, wenn Sie zulassen möchten, dass nur die Benutzer in Ihrer Organisation Webinare registrieren und teilnehmen können.

Standardmäßig ist Wer **registriert** werden auf **Jeder festgelegt.** Wenn Sie diese Richtlinie im Teams Admin Center bearbeiten möchten, wechseln Sie zu **Besprechungsbesprechungsrichtlinien**  >  .

Sie können eine vorhandene Microsoft Teams-Besprechungsrichtlinie mithilfe des Cmdlets [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) bearbeiten. Sie können aber auch eine neue Besprechungsrichtlinie für Microsoft Teams mithilfe des Cmdlets [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) erstellen und sie Benutzern zuweisen.

Damit jeder, auch anonyme Benutzer, Webinare registrieren und teilnehmen kann, legen Sie den **Parameter WhoCanRegister** auf **Jeder .** Diese ist standardmäßig **auf Jeder** festgelegt.

Damit nur Benutzer in Ihrer Organisation Webinare registrieren und teilnehmen können, legen Sie den Parameter auf **EveryoneInCompany .**

## <a name="meeting-provider-for-islands-mode"></a>Besprechungsanbieter für den Islands-Modus

Hierbei handelt es sich um eine benutzerspezifische Richtlinie. Über diese Einstellung wird gesteuert, welches Add-In für Outlook-Besprechungen für *Benutzer im Inselmodus* verwendet wird. Sie können festlegen, ob Benutzer nur das Add-In für Microsoft Teams-Besprechungen oder sowohl das Add-In für Microsoft Teams-Besprechungen als auch jenes für Skype for Business-Besprechungen verwenden können, um Besprechungen in Outlook zu planen.

Sie können diese Richtlinie nur für Benutzer im Inselmodus anwenden und für die der Parameter **AllowOutlookAddIn** in ihrer Microsoft Teams-Richtlinie auf **True** festgelegt ist.

Derzeit können Sie diese Richtlinie nur mithilfe von PowerShell festlegen. Sie können eine vorhandene Microsoft Teams-Besprechungsrichtlinie mithilfe des Cmdlets [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) bearbeiten. Sie können aber auch eine neue Besprechungsrichtlinie für Microsoft Teams mithilfe des Cmdlets [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) erstellen und sie Benutzern zuweisen.

Wenn Sie angeben möchten, welches Besprechungs-Add-In für Benutzer zur Verfügung stehen soll, legen Sie den Parameter **PreferredMeetingProviderForIslandsMode** wie folgt fest:

- Legen Sie den Parameter auf **TeamsAndSfB** fest, um sowohl das Add-In für Microsoft Teams-Besprechungen als auch das Skype for Business-Add-In in Outlook zu aktivieren. Dies ist der Standardwert.
- Legen Sie den Parameter auf **Teams** fest, um nur das Add-in für Microsoft Teams-Besprechungen in Outlook zu aktivieren. Diese Richtlinieneinstellung stellt sicher, dass in allen zukünftigen Besprechungen ein Link zur Teilnahme an Microsoft Teams-Besprechungen verfügbar ist. Es werden keine bestehenden Skype for Business-Besprechungslinks nach Microsoft Teams übertragen. Diese Richtlinieneinstellung wirkt sich nicht auf Anwesenheit, Chat, PSTN-Anrufe oder andere Funktionen in Skype for Business aus, was bedeutet, dass die Benutzer Skype for Business weiterhin für diese Funktionen verwenden können.

  Wenn Sie den Parameter auf **Teams** festlegen und dann zurück zu **TeamsAndSfB** ändern, werden beide Besprechungs-Add-Ins aktiviert. Beachten Sie jedoch, dass bestehende Links für die Teilnahme an Microsoft Teams-Besprechungen nicht nach Skype for Business übertragen werden. Nur in Skype for Business-Besprechungen, die nach der Änderung geplant wurden, wird es einen Link zur Teilnahme an Skype for Business-Besprechungen geben.

## <a name="meeting-reactions"></a>Besprechungsreaktionen

Die Einstellung "AllowMeetingReactions" kann nur mithilfe von PowerShell angewendet werden. Es gibt keine Option zum Aktivieren oder Deaktivieren von AllowMeetingReactions im Microsoft Teams Admin Center.

Besprechungsreaktionen sind standardmäßig deaktiviert. Das Deaktivieren der Reaktionen für einen Benutzer bedeutet nicht, dass er in von ihm geplanten Besprechungen keine Reaktionen verwenden kann. Unabhängig von der Standardeinstellung kann ein Besprechungsorganisator weiterhin Reaktionen über die Besprechungsoptionsseite aktivieren.


## <a name="related-topics"></a>Verwandte Themen

- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
- [Zuweisen von Richtlinien in Teams](policy-assignment-overview.md)
- [Entfernen der Microsoft Teams-Besprechungsrichtlinie "RestrictedAnonymousAccess" von Benutzern](meeting-policies-restricted-anonymous-access.md)
