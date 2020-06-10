---
title: Unterstützung von Microsoft Teams in Ihrer Organisation
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: troubleshooting
ms.service: msteams
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.custom: seo-marvel-mar2020
ms.reviewer: marcl, billkau
audience: admin
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
description: Verwenden Sie diese Ressourcen zur Unterstützung von Microsoft Teams in Ihrer Organisation, unabhängig davon, ob Sie der Teams-Administrator oder der Support-Techniker des Helpdesks sind.
appliesto:
- Microsoft Teams
ms.openlocfilehash: cde06d104f6f61efd981bb87b1503e8f097c5c26
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "44637034"
---
# <a name="support-microsoft-teams-in-your-organization"></a>Unterstützung von Microsoft Teams in Ihrer Organisation

> [!NOTE]
> Dieser Artikel ersetzt den Artikel "Bekannte Probleme bei Teams". 

Verwenden Sie die Ressourcen in diesem Artikel, um Teams in Ihrer Organisation zu unterstützen. 

Beginnen Sie mit der Durchsicht der Liste der am [häufigsten auftretenden Probleme und Lösungen](#common-issues-and-resolutions) weiter unten in diesem Artikel.

Wenn Sie dann nicht finden, was Sie benötigen, gehen Sie zu [Teams-Problembehandlung](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams), und suchen Sie im Inhaltsverzeichnis oder im Feld **Nach Titel filtern** Ihr Problem. 
:::image type="content" source="media/known-issues1.png" alt-text="Screenshot des Inhaltsverzeichnisses und des Filterfelds auf der Problembehandlungsseite von Teams":::

Wenn Sie immer noch nicht weiterkommen, wenden Sie sich an den [Microsoft-Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?toc=/microsoftteams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).


## <a name="common-issues-and-resolutions"></a>Häufige Probleme und Lösungen

> [!NOTE]
> Wenn Sie Hilfe bei der Bereitstellung von Teams benötigen, um Remotearbeitskräfte (WFH) aufgrund von COVID-19 zu unterstützen, lesen Sie [Remotearbeitskräfte mithilfe von Teams unterstützen](support-remote-work-with-teams.md). Außerdem sind Sie möglicherweise durch das Microsoft 365 FastTrack-Programm zu Hilfe bei der Bereitstellung berechtigt – besuchen Sie bitte das [FastTrack Center](https://www.microsoft.com/fasttrack), um eine Anforderung zu übermitteln.

### <a name="for-all-teams-customers"></a>Für alle Teams-Kunden

| |  |
|---------|---------|
|**Neu bei Microsoft Teams?**    |Lesen Sie [Erste Schritte mit Microsoft Teams](get-started-with-teams-quick-start.md).         |
|**Aktivieren des Teams-Gastzugriffs**     |Gehen Sie die [Checkliste für den Teams-Gastzugriff](guest-access-checklist.md) durch, und stellen Sie sicher, dass alle Schritte durchgeführt wurden. Schauen Sie sich die folgenden zusätzlichen Ressourcen an:<ul><li>[Grundlegendes zum Gastzugriff in Microsoft Teams](guest-access.md)</li>[Beitritt eines Gasts zu einem Team](guest-joins.md) <li>[Setup – Checkliste für den Microsoft Teams-Gastzugriff](guest-access-checklist.md)</li></ul>|
|**Teams-Besprechungen und Einwahl**    |Benötigen Sie Hilfe beim Aktivieren oder Einrichten von Audiokonferenzen in Teams? Wurde dieser Nutzer kürzlich erstellt? Wenn dies der Fall ist, müssen Sie 2 bis 24 Stunden warten, **bis die Einstellungen wirksam werden**.<br>So überprüfen Sie, ob der Nutzer für Audiokonferenzen lizenziert ist und über eine gebührenpflichtige Standardnummer verfügt:<br><ol><li>Wählen Sie im Microsoft 365 Admin Center unter **Aktive Benutzer** den gesuchten Benutzer aus.</li><li> Je nach Version des Admin Centers müssen Sie entweder **Lizenzen und Apps** auswählen oder unter **Produktlizenzen** auf **Bearbeiten** klicken.</li><li> Stellen Sie sicher, dass der Nutzer Lizenzen für Audiokonferenzen, Microsoft Teams und Skype for Business Online ausgewählt hat (Plan 2).</li><li>Klicken Sie in **Admin Centers** auf **Alle anzeigen** und dann auf **Teams**.</li><li>Klicken Sie im Microsoft Teams Admin Center auf **Altes Portal**.</li><li>Klicken Sie im Skype for Business Admin Center auf **Audiokonferenzen** und dann auf **Benutzer**.</li><li>Wählen Sie den betreffenden Benutzer aus, und vergewissern Sie sich, dass er über eine gebührenpflichtige Standardnummer verfügt.</li> </ol> Weitere Informationen finden Sie unter [Anrufpläne](calling-plans-for-office-365.md). Sie können sich auch an das Microsoft Commerce-Abrechnungsteam wenden, um Fragen zur Lizenzierung zu beantworten. <br><br>Zusätzliche Ressourcen:<ul><li>[Besprechungen und Konferenzen in Microsoft Teams](deploy-meetings-microsoft-teams-landing-page.md)</li><li>[Audiokonferenz](audio-conferencing-in-office-365.md)</li></ul>       |
|**Explorative Teams-Lizenz**     |Die explorative Microsoft Teams-Umgebung ermöglicht Benutzern in Ihrer Organisation, die über Azure Active Directory (AAD) verfügen und nicht für Teams lizenziert sind, eine explorative Umgebung von Microsoft Teams zu starten. Administratoren können dieses Feature für Benutzer in ihrer Organisation aktivieren oder deaktivieren. Die frühere [Microsoft Commercial Cloud-Testversion](iw-trial-teams.md) wurde durch die explorative Microsoft Teams-Umgebung ersetzt. <br><br>Zusätzliche Ressourcen:<ul><li>[So können Nutzer sich für die explorative Microsoft Teams-Umgebung registrieren](teams-exploratory.md#how-users-sign-up-for-the-teams-exploratory-experience)</li><li>[Verwalten der Teams Exploratory-Umgebung](teams-exploratory.md#manage-the-teams-exploratory-experience)</li></ul>|
|**Private Kanäle**    |Private Kanäle in Microsoft Teams schaffen konzentrierte Räume für die Zusammenarbeit innerhalb Ihrer Teams. Nur die Benutzer im Team, die Besitzer oder Mitglieder des privaten Kanals sind, können auf den Kanal zugreifen. Jeder, auch Gäste, kann als Mitglied zu einem privaten Kanals hinzugefügt werden, solange er bereits Mitglied des Teams ist.<br><br>Sie können einen privaten Kanal verwenden, wenn Sie die Zusammenarbeit auf diejenigen beschränken möchten, die das entsprechende Wissen benötigen, oder wenn Sie die Kommunikation zwischen einer Gruppe von Personen, die einem bestimmten Projekt zugeordnet sind, erleichtern möchten, ohne ein zusätzliches Team zur Verwaltung bilden zu müssen.<br><br>Zusätzliche Ressourcen:<ul><li>[So können Nutzer sich für die explorative Microsoft Teams-Umgebung registrieren](teams-exploratory.md#how-users-sign-up-for-the-teams-exploratory-experience)</li><li>[Verwalten der Teams Exploratory-Umgebung](teams-exploratory.md#manage-the-teams-exploratory-experience)</li><ul>        |
|**Besprechungsrichtlinien**|[Besprechungsrichtlinien](meeting-policies-in-teams.md) werden verwendet, um die Features zu steuern, die Besprechungsteilnehmern für Besprechungen, die von Benutzern in Ihrer Organisation geplant werden, zur Verfügung stehen. Nachdem Sie eine Richtlinie erstellt und die gewünschten Änderungen vorgenommen haben, können Sie der Richtlinie Nutzer zuweisen.         |
||**Ändern oder Erstellen einer Besprechungsrichtlinie**<br><br>Wenn Sie eine Besprechungsrichtlinie ändern oder erstellen möchten, wechseln Sie zum Microsoft Teams Admin Center > **Besprechungen** > ** Besprechungsrichtlinien**. Wählen Sie eine Richtlinie aus der Liste aus oder wählen Sie **Hinzufügen**. Wenn Sie eine neue Richtlinie erstellen, fügen Sie einen Namen und eine Beschreibung hinzu. Der Name darf keine Sonderzeichen enthalten und nicht mehr als 64 Zeichen lang sein. Wählen Sie die gewünschten Einstellungen aus, und klicken Sie dann auf **Speichern**. Nehmen wir beispielsweise an, Sie haben eine Gruppe von Nutzern, und Sie möchten die Bandbreite begrenzen, die für Ihre Besprechung erforderlich ist. Sie erstellen dann eine neue benutzerdefinierte Richtlinie namens „begrenzte Bandbreite“ und deaktivieren die folgenden Einstellungen:<br><br>Unter **Audio & Video**:<ul><li>Deaktivieren Sie Cloud-Aufzeichnung zulassen.</li><li>Deaktivieren Sie IP-Video zulassen.</li></ul>Unter **Inhaltsfreigabe**:<ul><li>Deaktivieren Sie den Bildschirmfreigabemodus.</li><li>Deaktivieren Sie Whiteboard zulassen.</li><li>Deaktivieren Sie Freigegebene Notizen zulassen.</li></ul>Weisen Sie dann die Richtlinie den Nutzern zu.         |
| |**Nutzern eine Besprechungsrichtlinie zuweisen**<br><br>So weisen Sie einem Benutzer eine Besprechungsrichtlinie zu<ol><li>Wechseln Sie in der linken Navigation des Microsoft Teams Admin Centers zu **Nutzer**, und klicken Sie dann den gewünschten Nutzer an.</li><li>Wählen Sie den Nutzer aus, indem Sie links neben den Nutzernamen klicken, und klicken Sie dann auf **Einstellungen bearbeiten**.</li><li>Wählen Sie unter **Besprechungsrichtlinie** die Richtlinie aus, die Sie zuweisen möchten, und klicken Sie dann auf **Übernehmen**.</li></ol> So weisen Sie mehreren Benutzern gleichzeitig eine Richtlinie zu <ol><li>Wechseln Sie in der linken Navigation des Microsoft Teams Admin Center zu **Benutzer**, und suchen Sie dann nach den gewünschten Benutzern, oder filtern Sie die Ansicht, um die gewünschten Benutzer anzuzeigen.</li><li>Wählen Sie in der Spalte **&#x2713;** (Häkchen) die Benutzer aus. Um alle Benutzer auszuwählen, klicken Sie am oberen Rand der Tabelle auf &#x2713; (Häkchen).</li><li>Klicken Sie auf **Einstellungen bearbeiten**, nehmen Sie die gewünschten Änderungen vor, und klicken Sie dann auf **Übernehmen**.</li></ol>Oder Sie können Folgendes tun:<ol><li>Wechseln Sie in der linken Navigation von Microsoft Teams Admin Center zu **Besprechungen > Besprechungsrichtlinien**.</li><li>Wählen Sie die gewünschte Richtlinie aus, indem Sie links neben die Richtlinienbezeichnung klicken.</li><li>Wählen Sie **Nutzer verwalten** aus.</li><li>Suchen Sie im Bereich **Nutzer verwalten** anhand des Anzeigenamens oder des Nutzernamens nach dem Nutzer, wählen Sie den Namen und dann **Hinzufügen** aus. Wiederholen Sie diesen Schritt für jeden Nutzer, den Sie hinzufügen möchten.</li><li>Wenn Sie mit dem Hinzufügen von Nutzern fertig sind, klicken Sie auf **Speichern**.</li></ol> ||**Problembehandlung bei fehlender Wähltastatur**     |Gehen Sie folgendermaßen vor: <ul><li>Stellen Sie sicher, dass dem Benutzer eine [Teams-Lizenz](teams-add-on-licensing/assign-teams-add-on-licenses.md) zugewiesen wurde.</li><li>Stellen Sie sicher, dass dem Benutzer ein [Anrufplan](calling-plan-landing-page.md) zugewiesen wurde.</li><li>Aktivieren Sie den Benutzer für [Enterprise-VoIP](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-enterprise-voice-online-and-phone-system-voicemail#to-enable-your-users-for-phone-system-in-office-365-voice-and-voicemail).</li></ul>      ||**Problembehandlung bei Teams-Anmeldung**   |Stellen Sie zuerst sicher, dass der [Microsoft Teams-Dienst fehlerfrei funktioniert](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/servicehealth). Überprüfen Sie dann, ob häufige Fehlercodes vorhanden sind, und überprüfen Sie [Warum habe ich Probleme beim Anmelden bei Microsoft Teams?](https://support.office.com/article/a02f683b-61a3-4008-9447-ee60c5593b0f)  Möglicherweise müssen Sie auch [Identitätsmodelle und Authentifizierung in Microsoft Teams](identify-models-authentication.md) überprüfen.         |

### <a name="for-education-customers"></a>Für Kunden der Microsoft Teams for Education-Version

|||
|---------|---------|
|Ihren Benutzer wird die Meldung „Sie verpassen etwas!“ angezeigt.   |Stellen Sie sicher, dass Sie [Microsoft Teams für Ihre Schule aktivieren](https://docs.microsoft.com/microsoft-365/education/intune-edu-trial/enable-microsoft-teams). Bei EDU-Mandanten ist Teams standardmäßig nicht aktiviert. Sie müssen es zuerst aktivieren. <br><br>Lesen Sie als Nächstes [Fernstudium (Lehren und Lernen)](https://support.office.com/article/remote-teaching-and-learning-in-office-365-education-f651ccae-7b65-478b-8366-51bb884025c4), um die aktuellste Anleitung zur Organisation Ihrer Bildungseinrichtung, zur Unterrichtsplanung, zu virtuellen Besprechungen und zum Teilen von Inhalten mit den Schülern zu erhalten.<br><br>Schauen Sie sich zum Schluss die Schulungsvideos, Decks und vieles mehr für Microsoft Teams IT-Administratoren unter [Administratorschulungen für Microsoft Teams](itadmin-readiness.md) an.        |


## <a name="related-topics"></a>Verwandte Themen

[Teams-Problembehandlung](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)

[Supportressourcen für Microsoft Teams](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?toc=/microsoftteams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
