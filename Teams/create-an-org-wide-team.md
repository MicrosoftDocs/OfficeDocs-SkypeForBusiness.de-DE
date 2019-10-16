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
description: Hier erfahren Sie, wie Sie ein organisationsweites Team in Teams erstellen und verwalten.
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: db7caa3879e016b6e8453ad151785578d2391dd1
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "37516650"
---
# <a name="create-an-org-wide-team-in-microsoft-teams"></a>Erstellen eines organisationsweiten Teams in Microsoft Teams

Organisationsweite Teams bieten eine automatische Möglichkeit für alle Personen in einer kleinen bis mittelständischen Organisation, Teil eines einzelnen Teams für die Zusammenarbeit zu sein.

Mit organisationsweiten Teams können globale Administratoren problemlos ein öffentliches Team erstellen, das alle Benutzer in der Organisation anzieht und die Mitgliedschaft mit Active Directory auf dem neuesten Stand hält, während Benutzer teilnehmen und die Organisation verlässt. Nur globale Administratoren können organisationsweite Teams erstellen, und derzeit ist ein organisationsweites Team auf Organisationen mit nicht mehr als 5.000-Benutzern begrenzt. Es gibt auch eine Grenze von fünf organisationsweiten Teams pro Mandant. Wenn diese Voraussetzungen erfüllt sind, sehen globale Administratoren **org-Wide** als Option, wenn Sie beim Erstellen eines Teams ein **Team von Grund auf neu erstellen** auswählen. 

Screenshot der ![Option "org-Wide" zum Erstellen eines organisationsweiten Team]-Screenshot der Option "org-Wide"(media/create-org-wide-team.png "zum Erstellen eines organisationsweiten Teams")

Wenn ein organisationsweites Team erstellt wird, werden alle globalen Administratoren als Teambesitzer hinzugefügt, und alle aktiven Benutzer werden als Teammitglieder hinzugefügt. Nicht lizenzierte Benutzer werden dem Team ebenfalls hinzugefügt. Wenn sich ein nicht lizenzierter Benutzer zum ersten Mal bei Teams anmeldet, wird dem Benutzer eine Microsoft Teams Commercial Cloud-Testlizenz zugewiesen. Wenn Sie mehr über die Testlizenz erfahren möchten, lesen Sie [das Angebot Verwalten des Teams für kommerzielle Cloud-Testversionen](iw-trial-teams.md). 

Diese Kontotypen werden Ihrem organisationsweiten Team nicht hinzugefügt:

- Konten, die von der Anmeldung blockiert werden
- Gastbenutzer
- Dienstkonten
- Raum-oder Geräte Konten
- Konten, die von einem freigegebenen Postfach gesichert werden

Wenn das Verzeichnis Ihrer Organisation aktualisiert wird, um neue aktive Benutzer einzubeziehen, oder wenn Benutzer nicht mehr in Ihrem Unternehmen arbeiten und Ihr Konto deaktiviert ist, werden Änderungen automatisch synchronisiert, und die Benutzer werden dem Team hinzugefügt oder aus ihr entfernt. Teammitglieder können ein organisationsweites Team nicht bestanden haben. Als Teambesitzer können Sie bei Bedarf Benutzer manuell hinzufügen oder entfernen.

> [!NOTE]
> - Wenn die Option " **org-Wide** " beim Erstellen eines Teams nicht angezeigt wird und Sie ein globaler Administrator sind, wird das Feature möglicherweise weiterhin bereitgestellt, Sie haben die fünf organisationsweiten Teams erreicht, oder Ihre Organisation hat mehr als die aktuelle Größenbeschränkung von 5.000-Mitgliedern. Wir möchten diesen Grenzwert in Zukunft erhöhen.
> - Räume, die nicht Teil einer Raumliste, eines Equipments und einer Ressourcenkonten sind, werden möglicherweise dem organisationsweiten Team hinzugefügt oder synchronisiert. Teambesitzer können diese Konten ganz einfach aus dem Team entfernen.
> - Alle Aktionen des Systems zum Hinzufügen oder Entfernen von Mitgliedern werden im Kanal "Allgemein" veröffentlicht. Der Kanal wird auch als neue Aktivität im Team-Client markiert.

## <a name="best-practices"></a>Bewährte Methoden

Um Ihr organisationsweites Team optimal zu nutzen, empfehlen wir Teambesitzern, die folgenden Schritte auszuführen:

### <a name="allow-only-team-owners-to-post-to-the-general-channel"></a>Nur Teambesitzern die Bereitstellung im allgemeinen Kanal gestatten

Reduzieren Sie Kanalrauschen, indem Sie nur Teambesitzer in den Kanal "Allgemein" Posten. Wechseln Sie zum Team, und klicken Sie auf **̇ ̇ ̇ Weitere Optionen** > **Team verwalten**. Klicken Sie auf der Registerkarte **Einstellungen** auf **Mitglieder Berechtigungen** #a0 **nur Besitzer können Nachrichten senden**.

### <a name="turn-off-team-and-team-name-mentions"></a>Deaktivieren von @Team und @ [Teamname]-Erwähnungen

 Reduzieren Sie @Mentions, damit Sie nicht die gesamte Organisation überlasten. Wechseln Sie zum Team, und klicken Sie auf **̇ ̇ ̇ Weitere Optionen** > **Team verwalten**. Klicken Sie auf der Registerkarte **Einstellungen** auf <strong>@Mentions</strong> #a0 deaktivieren Sie **Mitglieder anzeigen die Option @Team oder @ [Teamname]**. 

### <a name="automatically-favorite-important-channels"></a>Automatisch bevorzugten wichtigen Kanälen

Bevorzugte wichtige Kanäle, um sicherzustellen, dass sich jeder in Ihrer Organisation an bestimmten Konversationen beteiligt. Weitere Informationen finden Sie unter [automatisch bevorzugte Kanäle für das gesamte Team](https://support.office.com/article/auto-favorite-channels-for-the-whole-team-a948272c-5aa5-429c-863c-4e1e1cd6b0f6).

### <a name="set-up-channel-moderation"></a>Einrichten der Kanal Moderation

In diesem Fall sollten Sie die Kanal Moderation einrichten und bestimmten Teammitgliedern Moderatorfunktionen zuweisen. (Wenn die Moderation eingerichtet ist, erhalten die Teambesitzer automatisch Moderatorfunktionen.) Moderatoren können steuern, wer einen neuen Beitrag in einem Kanal beginnen kann, Moderatoren hinzufügen und entfernen, Steuern, ob Teammitglieder auf vorhandene Kanal Nachrichten antworten können, und Steuern, ob Bots und Connectors Kanal Nachrichten senden können. Weitere Informationen finden Sie unter [Einrichten und Verwalten der Kanal Moderation in Microsoft Teams](manage-channel-moderation-in-teams.md).

### <a name="remove-accounts-that-might-not-belong"></a>Entfernen von Konten, die möglicherweise nicht dazugehören

Auch wenn Mitglieder kein organisationsübergreifendes Team als Teambesitzer belassen können, können Sie die Team Liste verwalten, indem Sie Konten entfernen, die nicht dazugehören. **Stellen Sie sicher, dass Sie Teams verwenden, um Benutzer aus Ihrem organisationsweiten Team zu entfernen**. Wenn Sie eine andere Möglichkeit zum Entfernen eines Benutzers wie dem Microsoft 365 Admin Center oder einer Gruppe in Outlook verwenden, wird der Benutzer möglicherweise wieder dem organisationsweiten Team hinzugefügt.

## <a name="faq"></a>Häufig gestellte Fragen

### <a name="is-there-a-way-to-create-an-org-wide-team-other-than-using-the-teams-client"></a>Gibt es eine Möglichkeit, ein anderes organisationsübergreifendes Team als die Verwendung des Teams-Clients zu erstellen?

Globale Administratoren können nur mithilfe des Teams-Clients ein organisationsweites Team erstellen. Wenn Ihre Organisation das Erstellen von Teams auf die Verwendung von PowerShell beschränkt, empfiehlt es sich, ihre globalen Administratoren zur Sicherheitsgruppe der Benutzer hinzuzufügen, die ein Team erstellen können. Weitere Informationen finden Sie unter [Verwalten von Personen, die Office 365-Gruppen erstellen können](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups).

Wenn dies nicht möglich ist, können Sie PowerShell verwenden, um ein öffentliches Team zu erstellen und einen globalen Administrator als Teambesitzer hinzuzufügen. Klicken Sie dann auf **Weitere Optionen** des globalen Administrators neben dem Teamnamen, klicken Sie auf **Team bearbeiten**, und ändern Sie dann den Datenschutz in **org-Wide – jeder in Ihrer Organisation wird automatisch hinzugefügt**. Beachten Sie, dass nur Teambesitzer auf die Option **Team bearbeiten** zugreifen können und nur globale Administratoren die Option **org-Wide** sehen können.

### <a name="is-there-a-way-to-convert-an-existing-team-to-an-org-wide-team"></a>Gibt es eine Möglichkeit, ein vorhandenes Team in ein organisationsweites Team umzuwandeln?

Globale Administratoren können ein vorhandenes Team in ein organisationsweites Team umwandeln, indem Sie es im Teams-Client bearbeiten. Wechseln Sie zum Teamnamen, und klicken Sie auf **Weitere Optionen** > **Team bearbeiten**.
