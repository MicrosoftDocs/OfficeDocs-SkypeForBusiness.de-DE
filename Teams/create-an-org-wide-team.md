---
title: Erstellen eines organisationsweiten Teams in Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: phlouie
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Erfahren Sie, wie Sie ein organisationsweites Teams in Teams erstellen und verwalten, um in kleinen und mittelständischen Organisationen für alle Personen eine automatische Möglichkeit für die Zusammenarbeit bereitzustellen.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 28a03f045aa6db2567feb8990b9b9267706c7e8d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111161"
---
# <a name="create-an-org-wide-team-in-microsoft-teams"></a>Erstellen eines organisationsweiten Teams in Microsoft Teams

Organisationsweite Teams bieten in kleinen und mittelständischen Organisationen eine automatische Möglichkeit für alle Personen, Teil eines gemeinsamen Teams für die Zusammenarbeit zu werden.

Mit organisationsweiten Teams können globale Administratoren ganz einfach ein öffentliches Team erstellen, das alle Benutzer in der Organisation aufnimmt. Mithilfe von Active Directory Domain Services kann die Mitgliedschaft auf dem aktuellen Stand gehalten werden, zum Beispiel wenn Benutzer der Organisation beitreten oder diese verlassen. Nur globale Administratoren können organisationsweite Teams erstellen, und derzeit ist ein organisationsweites Team auf maximal 10.000 Benutzer beschränkt. Außerdem gibt es eine Beschränkung auf fünf organisationsweite Teams pro Mandant. Wenn diese Voraussetzungen erfüllt sind, wird globalen Administratoren **Organisationsweit** als Option angezeigt, wenn sie beim Aufbau eines neuen Teams **Neuerstellen eines Teams** auswählen. 

![Screenshot der Option „Organisationsweit", um ein organisationsweites Team zu erstellen](media/create-org-wide-team.png "Screenshot der Option „Organisationsweit&quot; zum Erstellen eines organisationsweites Teams")

Wenn ein organisationsweites Team erstellt wird, werden alle globalen Administratoren und Teams-Dienstadministratoren als Teambesitzer und alle aktiven Benutzer als Teammitglieder hinzugefügt. Nicht lizenzierte Benutzer werden dem Team ebenfalls hinzugefügt. Wenn ein nicht lizenzierter Benutzer sich zum ersten Mal bei Teams anmeldet, wird dem Benutzer eine Microsoft Teams Exploratory-Lizenz zugewiesen. Um mehr über die Exploratory-Lizenz zu erfahren, lesen Sie [Verwalten der Microsoft Teams Exploratory-Lizenz](teams-exploratory.md). 

Diese Arten von Konten werden Ihrem organisationsweiten Team nicht hinzugefügt:

- Konten, die zur Anmeldung gesperrt sind
- Gastbenutzer
- Ressourcen- oder Dienstkonten (z. B. Konten, die mit automatischen Telefonzentralen und Anrufwarteschleifen verbunden sind)
- Raum- oder Gerätekonten
- Konten, die durch ein freigegebenes Postfach gesichert sind

Wenn das Verzeichnis Ihrer Organisation aktualisiert wird, um neue aktive Benutzer hinzuzufügen und Konten von Benutzern zu deaktivieren, die in Ihrem Unternehmen nicht mehr arbeiten, werden die Änderungen automatisch synchronisiert, d. h. die Benutzer werden zum Team hinzugefügt bzw. entfernt. Teammitglieder können ein organisationsweites Team nicht verlassen. Als Teambesitzer können Sie bei Bedarf Benutzer manuell hinzufügen oder entfernen.

> [!NOTE]
> - Wenn die Option **Organisationsweit** beim Erstellen eines Teams nicht angezeigt wird, obwohl Sie ein globaler Administrator sind, kann es sein, dass Sie das Limit der maximal fünf organisationsweiten Teams erreicht haben oder dass Ihre Organisation mehr als 10.000 Mitglieder hat und damit das derzeit gültige Größenlimit überschreitet. Wir arbeiten daran, dieses Limit künftig zu erhöhen. Organisationsweite Teams sind für Microsoft Teams for Education derzeit noch nicht verfügbar.
> - Räume, die nicht Teil einer Raumliste sind, Geräte und Ressourcenkonten werden möglicherweise dem organisationsweiten Team hinzugefügt bzw. mit diesem synchronisiert. Teambesitzer können diese Konten ganz einfach wieder aus dem Team entfernen.
> - Alle Aktionen des Systems zum Hinzufügen oder Entfernen von Mitgliedern werden im Kanal "Allgemein" gepostet. Der Kanal wird außerdem im Teams-Client mit „Neue Aktivität“ gekennzeichnet.
> - Wenn Ihre Organisation in Teams neu ist und nicht mehr als 10.000 Benutzer hat wird automatisch ein organisationsweites Team für Ihre Organisation erstellt. Der Teamname spiegelt den Mandantennamen wider verfügt über einen allgemeinen Kanal. Globale Administratoren können dieses Team wie jedes andere Team bearbeiten. 

## <a name="best-practices"></a>Bewährte Methoden

Wenn Teambesitzer Ihr organisationsweites Team optimal nutzen möchten, sollten sie wie folgt vorgehen.

### <a name="allow-only-team-owners-to-post-to-the-general-channel"></a>Gestatten Sie nur Teambesitzern das Versenden von Beiträgen im Kanal „Allgemein“.

Reduzieren Sie die Anzahl der Beiträge, indem Sie nur Teambesitzern gestatten, im Kanal „Allgemein“ Beiträge zu versenden. Wechseln Sie zum Team, suchen Sie den Kanal „Allgemein“, und wählen Sie dann **˙˙˙ Weitere Optionen** > **Kanal verwalten** aus. Klicken Sie auf der Registerkarte **Kanaleinstellungen** auf **Berechtigungen**, und wählen Sie dann **Nur Besitzer können Nachrichten senden** aus.

### <a name="turn-off-team-and-team-name-mentions"></a>Deaktivieren der @Team und @ [Teamname]-Erwähnungen

 Reduzieren Sie @Erwähnungen, um die Anzahl der Nachrichten für die ganze Organisation zu senken. Wechseln Sie zum Team, und klicken Sie auf **˙˙˙ Weitere Optionen**  >  **Team verwalten**. Klicken Sie auf der Registerkarte **Einstellungen** auf <strong>@Erwähnungen</strong> > schalten Sie **Mitgliedern die Option @Team oder @[Teamname]** aus. 

### <a name="automatically-show-important-channels"></a>Wichtige Kanäle automatisch anzeigen

Wichtige Kanäle anzeigen, um sicherzustellen, dass jeder in Ihrer Organisation sich an bestimmten Unterhaltungen beteiligt. Weitere Informationen finden Sie unter [Automatisches Festlegen von Kanalfavoriten für das gesamte Team](https://support.office.com/article/auto-favorite-channels-for-the-whole-team-a948272c-5aa5-429c-863c-4e1e1cd6b0f6). 

### <a name="set-up-channel-moderation"></a>Richten Sie eine Kanalmoderation ein

Erwägen Sie das Einrichten einer Kanalmoderation und übertragen Sie ausgewählten Teammitgliedern die Moderatorfunktionen. (Wenn die Moderation eingerichtet ist, wird Teambesitzern automatisch die Moderatorfunktion zugewiesen.) Moderatoren können steuern, wer in einem Kanal einen neuen Beitrag erstellen kann. Außerdem können sie Moderatoren hinzufügen und entfernen, entscheiden, ob Teammitglieder auf vorhandene Kanalnachrichten antworten können und steuern, ob Bots und Connectoren Kanalnachrichten senden dürfen. Weitere Informationen finden Sie unter [Einrichten und Verwalten der Kanalmoderation in Microsoft Teams](manage-channel-moderation-in-teams.md).

### <a name="remove-accounts-that-might-not-belong"></a>Entfernen Sie Konten, die möglicherweise nicht dazugehören

Auch wenn Mitglieder ein organisationsweites Team nicht verlassen können, kann ein Teambesitzer die Teamliste verwalten, indem er Konten entfernt, die nicht dazugehören. **Stellen Sie sicher, dass Sie Teams zum Entfernen von Benutzern aus Ihrem organisationsweiten Team verwenden**. Wenn Sie eine andere Möglichkeit zum Entfernen eines Benutzers verwenden, z. B. das Microsoft 365 Admin Center oder das Entfernen aus einer Gruppe in Outlook, wird der Benutzer möglicherweise wieder zum organisationsweiten Team hinzugefügt.

## <a name="faq"></a>Häufig gestellte Fragen

### <a name="is-there-a-way-to-create-an-org-wide-team-other-than-using-the-teams-client"></a>Gibt es eine Möglichkeit zum Erstellen eines organisationsweiten Teams ohne Nutzung des Teams-Clients?

Globale Administratoren können nur mithilfe des Teams-Clients ein organisationsweites Team erstellen. Wenn Ihre Organisation das Erstellen von Teams auf die Verwendung von PowerShell einschränkt, empfiehlt es sich, die globalen Administratoren der Sicherheitsgruppe jener Benutzer hinzuzufügen, die ein Team erstellen können. Weitere Informationen finden Sie unter [Verwalten von Personen, die Gruppen erstellen können](/microsoft-365/admin/create-groups/manage-creation-of-groups).

Ist dies nicht möglich ist, können Sie mithilfe von PowerShell ein öffentliches Team erstellen und einen globalen Administrator als Teambesitzer hinzufügen. Lassen Sie den globalen Administrator neben dem Teamnamen auf **weitere Optionen** und dann auf **Team bearbeiten** klicken. Ändern Sie nun den Datenschutz auf **organisationsweit – jeder Mitarbeiter in Ihrer Organisation wird automatisch hinzugefügt**. Beachten Sie, dass nur Teambesitzer auf die Option **Team bearbeiten** zugreifen, und nur globale Administratoren die Option **organisationsweit** sehen können.

### <a name="is-there-a-way-to-convert-an-existing-team-to-an-org-wide-team"></a>Gibt es eine Möglichkeit, ein vorhandenes Team in ein organisationsweites Team zu konvertieren?

Globale Administratoren können ein vorhandenes Team in ein organisationsweites Team konvertieren, indem Sie es im Teams-Client bearbeiten. Wechseln Sie zum Teamnamen und klicken Sie dann auf **Weitere Optionen**  >  **Team bearbeiten**.

### <a name="can-i-create-an-org-wide-team-using-a-team-template"></a>Kann ich ein organisationsweites Team mit einer Teamvorlage erstellen?

Teamvorlagen können nicht verwendet werden, um ein organisationsweites Team zu erstellen. An diesem Feature wird zur Zeit noch gearbeitet. 

## <a name="see-also"></a>Mehr dazu

Sehen Sie sich ein Video zum Thema [Erstellen eines unternehmensweiten Teams in Microsoft Teams](https://support.office.com/article/037bb27a-bcc9-48fe-8d72-44d9482420a3) an.