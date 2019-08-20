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
description: Erfahren Sie, wie sie ein organisationsweites Team in Microsoft Teams erstellen und verwalten.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 881996d5f8acbc7458a775e02adfad9b38a231a9
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36241235"
---
# <a name="create-an-org-wide-team-in-microsoft-teams"></a>Erstellen eines organisationsweiten Teams in Microsoft Teams

Organisationsweite Teams bieten in kleinen und mittelständischen Organisationen eine automatische Möglichkeit für alle Personen, Teil eines gemeinsamen Teams für die Zusammenarbeit zu werden.

Mit organisationsweiten Teams können globale Administratoren ganz einfach ein öffentliches Team erstellen, das alle Benutzer in der Organisation aufnimmt. Mithilfe von Active Directory Domain Services kann die Mitgliedschaft auf dem aktuellen Stand gehalten werden, zum Beispiel wenn Benutzer der Organisation beitreten oder diese verlassen. Nur globale Administratoren können organisationsweite Teams erstellen, und derzeit ist ein organisationsweites Team auf maximal 5.000 Benutzer beschränkt. Außerdem gibt es eine Beschränkung auf fünf organisationsweite Teams pro Mandant. Wenn diese Voraussetzungen erfüllt sind, wird globalen Administratoren **organisationsweit** als Option angezeigt, wenn sie beim Aufbau eines neuen Teams **Neuerstellen eines Teams** auswählen. 

![Screenshot der Option „organisationsweit“ zum Erstellen eines organisationsweiten Teams](media/create-org-wide-team.png " Screenshot der Option „organisationsweit“ zum Erstellen eines organisationsweiten Teams")

Wenn ein organisationsweites Team erstellt wird, werden alle globalen Administratoren als Teambesitzer und alle aktiven Benutzer als Teammitglieder hinzugefügt. Nicht lizenzierte Benutzer werden dem Team ebenfalls hinzugefügt. Wenn ein nicht lizenzierter Benutzer sich zum ersten Mal bei Teams anmeldet, wird dem Benutzer eine Testlizenz für die kommerzielle Cloud von Microsoft Teams zugewiesen. Weiter Informationen über die Testlizenz finden Sie unter [Verwalten der professionellen Cloud-Testangebots von Teams ](iw-trial-teams.md). 

Diese Arten von Konten werden Ihrem organisationsweiten Team nicht hinzugefügt:

- Konten, die zur Anmeldung gesperrt sind
- Gastbenutzer
- Dienstkonten
- Raum- oder Gerätekonten
- Konten, die durch ein freigegebenes Postfach gesichert sind

Wenn das Verzeichnis Ihrer Organisation aktualisiert wird, um neue aktive Benutzer hinzuzufügen und Teams-Lizenzen von Benutzern zu deaktivieren, die in Ihrem Unternehmen nicht mehr arbeiten, werden die Änderungen automatisch synchronisiert, d. h. die Benutzer werden zum Team hinzugefügt bzw. entfernt. Teammitglieder können ein organisationsweites Team nicht verlassen. Als Teambesitzer können Sie bei Bedarf Benutzer manuell hinzufügen oder entfernen.

> [!NOTE]
> - Wenn die Option **organisationsweit** beim Erstellen eines Teams nicht angezeigt wird, obwohl Sie ein globaler Administrator sind, kann es sein, dass das Feature erst noch bereitgestellt wird, oder dass Ihre Organisation mehr als 5.000 Mitglieder hat und damit das derzeit gültige Größenlimit überschreitet. Wir arbeiten daran, dieses Limit künftig zu erhöhen.
> - Räume, die nicht Teil einer Raumliste sind, Geräte und Ressourcenkonten werden möglicherweise dem organisationsweiten Team hinzugefügt bzw. mit ihm synchronisiert. Teambesitzer können diese Konten ganz einfach wieder aus dem Team entfernen.

## <a name="best-practices"></a>Bewährte Methoden

Wenn Teambesitzer Ihr organisationsweites Team optimal nutzen möchten, sollten sie wie folgt vorgehen.

### <a name="allow-only-team-owners-to-post-to-the-general-channel"></a>Gestatten Sie nur Teambesitzern das Versenden von Beiträgen im Kanal „Allgemein“.

Reduzieren Sie die Anzahl der Beiträge, indem Sie nur Teambesitzern gestatten, im Kanal „Allgemein“ Beiträge zu versenden. Wechseln Sie zum Team, und klicken Sie auf**˙˙˙ Weitere Optionen**  >  **Team verwalten**. Klicken Sie auf der Registerkarte **Einstellungen** auf **Mitgliedsberechtigungen**. Wählen Sie nun **Nur Besitzer können Nachrichten senden**.

### <a name="turn-off-team-and-team-name-mentions"></a>Deaktivieren der @Team und @ [Teamname]-Erwähnungen

 Reduzieren Sie @Erwähnungen, um die Anzahl der Nachrichten für die ganze Organisation zu senken. Wechseln Sie zum Team, und klicken Sie auf**˙˙˙ Weitere Optionen**  >  **Team verwalten**. Klicken Sie auf der Registerkarte **Einstellungen** auf <strong>@erwähnen</strong>. Deaktivieren Sie die Option **Mitglieder die Option @Team oder @[Teamname] anzeigen**. 

### <a name="automatically-favorite-important-channels"></a>Speichern Sie wichtige Kanäle automatisch als Favoriten

Speichern Sie wichtige Kanäle als Favoriten, um sicherzustellen, dass jeder in Ihrer Organisation sich an bestimmten Unterhaltungen beteiligt. Weitere Informationen finden Sie unter [Automatisches Festlegen von Kanalfavoriten für das gesamte Team](https://support.office.com/article/auto-favorite-channels-for-the-whole-team-a948272c-5aa5-429c-863c-4e1e1cd6b0f6).

### <a name="set-up-channel-moderation"></a>Richten Sie eine Kanalmoderation ein

Erwägen Sie das Einrichten einer Kanalmoderation und übertragen Sie ausgewählten Teammitgliedern die Moderatorfunktionen. (Wenn die Moderation eingerichtet ist, wird Teambesitzern automatisch die Moderatorfunktion zugewiesen.) Moderatoren können steuern, wer in einem Kanal einen neuen Beitrag erstellen kann. Außerdem können sie Moderatoren hinzufügen und entfernen, entscheiden, ob Teammitglieder auf vorhandene Kanalnachrichten antworten können und steuern, ob Bots und Connectoren Kanalnachrichten senden dürfen. Weitere Informationen finden Sie unter [Einrichten und Verwalten der Kanalmoderation in Microsoft Teams](manage-channel-moderation-in-teams.md).

### <a name="remove-accounts-that-might-not-belong"></a>Entfernen Sie Konten, die möglicherweise nicht dazugehören

Auch wenn Mitglieder ein organisationsweites Team nicht verlassen können, kann ein Teambesitzer die Teamliste verwalten, indem er Konten entfernt, die nicht dazugehören. Stellen Sie sicher, dass Sie Teams zum Entfernen von Benutzern aus Ihrem organisationsweiten Team verwenden. Wenn Sie eine andere Möglichkeit zum Entfernen eines Benutzers verwenden, z. b. das Microsoft 365 Admin Center oder das Entfernen aus einer Gruppe in Outlook, wird der Benutzer möglicherweise wieder zum organisationsweiten Team hinzugefügt.

## <a name="faq"></a>Häufig gestellte Fragen

### <a name="is-there-a-way-to-create-an-org-wide-team-other-than-using-the-teams-client"></a>Gibt es eine Möglichkeit zum Erstellen eines organisationsweiten Teams ohne Nutzung des Teams-Clients?

Globale Administratoren können nur mithilfe des Teams-Clients ein organisationsweites Team erstellen. Wenn Ihre Organisation das Erstellen von Teams auf die Verwendung von PowerShell einschränkt, empfiehlt es sich, die globalen Administratoren der Sicherheitsgruppe jener Benutzer hinzuzufügen, die ein Team erstellen können. Weitere Informationen finden Sie unter [Verwalten von Personen, die Office 365-Gruppen erstellen können](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups).

Ist dies nicht möglich ist, können Sie mithilfe von PowerShell ein öffentliches Team erstellen und einen globalen Administrator als Teambesitzer hinzufügen. Lassen Sie den globalen Administrator neben dem Teamnamen auf **weitere Optionen** und dann auf **Team bearbeiten** klicken. Ändern Sie nun den Datenschutz auf **organisationsweit – jeder Mitarbeiter in Ihrer Organisation wird automatisch hinzugefügt**. Beachten Sie, dass nur Teambesitzer auf die Option **Team bearbeiten** zugreifen, und nur globale Administratoren die Option **organisationsweit** sehen können.

### <a name="is-there-a-way-to-convert-an-existing-team-to-an-org-wide-team"></a>Gibt es eine Möglichkeit, ein vorhandenes Team in ein organisationsweites Team zu konvertieren?

Globale Administratoren können ein vorhandenes Team in ein organisationsweites Team konvertieren, indem Sie es im Teams-Client bearbeiten. Wechseln Sie zum Teamnamen, und klicken Sie dann auf **weitere Optionen**  >  **Team bearbeiten**.
