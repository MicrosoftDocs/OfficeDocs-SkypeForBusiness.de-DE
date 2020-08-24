---
title: Erstellen eines organisationsweiten Teams in Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: phlouie
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Hier erfahren Sie, wie Sie ein organisationsweites Team in Teams erstellen und verwalten, um jedem in einer kleinen und mittleren Organisation eine automatische Möglichkeit zur Zusammenarbeit zu bieten.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7c1ad054fb12ade67a15d2e8c80c1a68178c1dc9
ms.sourcegitcommit: cd16ff6007e0a798493e2fa469c6681993380420
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/23/2020
ms.locfileid: "46860816"
---
# <a name="create-an-org-wide-team-in-microsoft-teams"></a>Erstellen eines organisationsweiten Teams in Microsoft Teams

Organisationsweite Teams bieten in kleinen und mittelständischen Organisationen eine automatische Möglichkeit für alle Personen, Teil eines gemeinsamen Teams für die Zusammenarbeit zu werden.

Mit organisationsweiten Teams können globale Administratoren ganz einfach ein öffentliches Team erstellen, das alle Benutzer in der Organisation aufnimmt. Mithilfe von Active Directory Domain Services kann die Mitgliedschaft auf dem aktuellen Stand gehalten werden, zum Beispiel wenn Benutzer der Organisation beitreten oder diese verlassen. Nur globale Administratoren können organisationsweite Teams erstellen, und derzeit ist ein organisationsweites Team auf Organisationen mit nicht mehr als 5.000-Benutzern begrenzt. Außerdem gibt es eine Beschränkung auf fünf organisationsweite Teams pro Mandant. Wenn diese Voraussetzungen erfüllt sind, wird globalen Administratoren ** Organisationsweit** als Option angezeigt, wenn sie beim Aufbau eines neuen Teams **Neuerstellen eines Teams** auswählen. 

![Screenshot der Option „Organisationsweit", um ein organisationsweites Team zu erstellen](media/create-org-wide-team.png "Screenshot der Option „Organisationsweit" zum Erstellen eines organisationsweites Teams")

Wenn ein organisationsweites Team erstellt wird, werden alle globalen Administratoren als Teambesitzer und alle aktiven Benutzer als Teammitglieder hinzugefügt. Nicht lizenzierte Benutzer werden dem Team ebenfalls hinzugefügt. Wenn sich ein nicht lizenzierter Benutzer zum ersten Mal bei Teams anmeldet, wird dem Benutzer eine Microsoft Teams-explorative Lizenz zugewiesen. Weitere Informationen zur explorativen Lizenz finden Sie unter [Verwalten der explorativen Lizenz für Microsoft Teams](teams-exploratory.md). 

Diese Arten von Konten werden Ihrem organisationsweiten Team nicht hinzugefügt:

- Konten, die zur Anmeldung gesperrt sind
- Gastbenutzer
- Dienstkonten
- Raum- oder Gerätekonten
- Konten, die durch ein freigegebenes Postfach gesichert sind

Wenn das Verzeichnis Ihrer Organisation aktualisiert wird, um neue aktive Benutzer hinzuzufügen und Konten von Benutzern zu deaktivieren, die in Ihrem Unternehmen nicht mehr arbeiten, werden die Änderungen automatisch synchronisiert, d. h. die Benutzer werden zum Team hinzugefügt bzw. entfernt. Teammitglieder können ein organisationsweites Team nicht verlassen. Als Teambesitzer können Sie bei Bedarf Benutzer manuell hinzufügen oder entfernen.

> [!NOTE]
> - Wenn die Option " **org-Wide** " beim Erstellen eines Teams nicht angezeigt wird und Sie ein globaler Administrator sind, haben Sie möglicherweise die fünf organisationsweite Teams-Grenze erreicht, oder Ihre Organisation verfügt über mehr als die aktuelle Größenbeschränkung von 5.000-Mitgliedern. Wir arbeiten daran, dieses Limit künftig zu erhöhen. Organisationsweite Teams sind für Microsoft Teams for Education derzeit noch nicht verfügbar.
> - Räume, die nicht Teil einer Raumliste sind, Geräte und Ressourcenkonten werden möglicherweise dem organisationsweiten Team hinzugefügt bzw. mit diesem synchronisiert. Teambesitzer können diese Konten ganz einfach wieder aus dem Team entfernen.
> - Alle Aktionen des Systems zum Hinzufügen oder Entfernen von Mitgliedern werden im Kanal "Allgemein" gepostet. Der Kanal wird außerdem im Teams-Client mit „Neue Aktivität“ gekennzeichnet.
> - Wenn Ihre Organisation in Teams neu ist und nicht mehr als 5.000 Benutzer hat wird automatisch ein organisationsweites Team für Ihre Organisation erstellt. Der Teamname spiegelt den Mandantennamen wider verfügt über einen allgemeinen Kanal. Globale Administratoren können dieses Team wie jedes andere Team bearbeiten. 

## <a name="best-practices"></a>Bewährte Methoden

Wenn Teambesitzer Ihr organisationsweites Team optimal nutzen möchten, sollten sie wie folgt vorgehen.

### <a name="allow-only-team-owners-to-post-to-the-general-channel"></a>Gestatten Sie nur Teambesitzern das Versenden von Beiträgen im Kanal „Allgemein“.

Reduzieren Sie die Anzahl der Beiträge, indem Sie nur Teambesitzern gestatten, im Kanal „Allgemein“ Beiträge zu versenden. Wechseln Sie zum Team, und klicken Sie auf**˙˙˙ Weitere Optionen**  >  **Team verwalten**. Klicken Sie auf der Registerkarte **Einstellungen** auf **Mitgliedsberechtigungen**. Wählen Sie nun **Nur Besitzer können Nachrichten senden**.

### <a name="turn-off-team-and-team-name-mentions"></a>Deaktivieren der @Team und @ [Teamname]-Erwähnungen

 Reduzieren Sie @Erwähnungen, um die Anzahl der Nachrichten für die ganze Organisation zu senken. Wechseln Sie zum Team, und klicken Sie auf**˙˙˙ Weitere Optionen**  >  **Team verwalten**. Klicken Sie auf der Registerkarte **Einstellungen** auf <strong>@Erwähnungen</strong> > schalten Sie ** Mitgliedern die Option @Team oder @[Teamname]** aus. 

### <a name="automatically-show-important-channels"></a>Wichtige Kanäle automatisch anzeigen

Wichtige Kanäle anzeigen, um sicherzustellen, dass jeder in Ihrer Organisation sich an bestimmten Unterhaltungen beteiligt. Weitere Informationen finden Sie unter [Automatisches Festlegen von Kanalfavoriten für das gesamte Team](https://support.office.com/article/auto-favorite-channels-for-the-whole-team-a948272c-5aa5-429c-863c-4e1e1cd6b0f6). 

### <a name="set-up-channel-moderation"></a>Richten Sie eine Kanalmoderation ein

Erwägen Sie das Einrichten einer Kanalmoderation und übertragen Sie ausgewählten Teammitgliedern die Moderatorfunktionen. (Wenn die Moderation eingerichtet ist, wird Teambesitzern automatisch die Moderatorfunktion zugewiesen.) Moderatoren können steuern, wer in einem Kanal einen neuen Beitrag erstellen kann. Außerdem können sie Moderatoren hinzufügen und entfernen, entscheiden, ob Teammitglieder auf vorhandene Kanalnachrichten antworten können und steuern, ob Bots und Connectoren Kanalnachrichten senden dürfen. Weitere Informationen finden Sie unter [Einrichten und Verwalten der Kanalmoderation in Microsoft Teams](manage-channel-moderation-in-teams.md).

### <a name="remove-accounts-that-might-not-belong"></a>Entfernen Sie Konten, die möglicherweise nicht dazugehören

Auch wenn Mitglieder kein organisationsübergreifendes Team als Teambesitzer belassen können, können Sie die Team Liste verwalten, indem Sie Konten entfernen, die nicht dazugehören. **Stellen Sie sicher, dass Sie Teams zum Entfernen von Benutzern aus Ihrem organisationsweiten Team verwenden**. Wenn Sie eine andere Möglichkeit zum Entfernen eines Benutzers verwenden, z. B. das Microsoft 365 Admin Center oder das Entfernen aus einer Gruppe in Outlook, wird der Benutzer möglicherweise wieder zum organisationsweiten Team hinzugefügt.

## <a name="faq"></a>Häufig gestellte Fragen

### <a name="is-there-a-way-to-create-an-org-wide-team-other-than-using-the-teams-client"></a>Gibt es eine Möglichkeit zum Erstellen eines organisationsweiten Teams ohne Nutzung des Teams-Clients?

Globale Administratoren können nur mithilfe des Teams-Clients ein organisationsweites Team erstellen. Wenn Ihre Organisation das Erstellen von Teams auf die Verwendung von PowerShell einschränkt, empfiehlt es sich, die globalen Administratoren der Sicherheitsgruppe jener Benutzer hinzuzufügen, die ein Team erstellen können. Weitere Informationen finden Sie unter [Verwalten von Personen, die Gruppen erstellen können](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-creation-of-groups).

Ist dies nicht möglich ist, können Sie mithilfe von PowerShell ein öffentliches Team erstellen und einen globalen Administrator als Teambesitzer hinzufügen. Lassen Sie den globalen Administrator neben dem Teamnamen auf **weitere Optionen** und dann auf **Team bearbeiten** klicken. Ändern Sie nun den Datenschutz auf **organisationsweit – jeder Mitarbeiter in Ihrer Organisation wird automatisch hinzugefügt**. Beachten Sie, dass nur Teambesitzer auf die Option **Team bearbeiten** zugreifen, und nur globale Administratoren die Option **organisationsweit** sehen können.

### <a name="is-there-a-way-to-convert-an-existing-team-to-an-org-wide-team"></a>Gibt es eine Möglichkeit, ein vorhandenes Team in ein organisationsweites Team zu konvertieren?

Globale Administratoren können ein vorhandenes Team in ein organisationsweites Team konvertieren, indem Sie es im Teams-Client bearbeiten. Wechseln Sie zum Teamnamen und klicken Sie dann auf **Weitere Optionen**  >  **Team bearbeiten**.

### <a name="can-i-create-an-org-wide-team-using-a-team-template"></a>Kann ich ein organisationsweites Team mithilfe einer Teamvorlage erstellen?

Teamvorlagen können nicht zum Erstellen eines organisationsweiten Teams verwendet werden. Die Arbeit für dieses Feature wird zurzeit ausgeführt. 

## <a name="see-also"></a>Siehe auch

Schauen Sie sich ein Video zum [Erstellen eines unternehmensweiten Teams in Microsoft Teams an](https://support.office.com/article/037bb27a-bcc9-48fe-8d72-44d9482420a3).
