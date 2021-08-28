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
description: Hier erfahren Sie, wie Sie in Teams ein organisationsweites Team erstellen und verwalten, um für jeden in einer kleinen bis mittelgroßen Organisation eine automatische Zusammenarbeit zu ermöglichen.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a6faac9e0c04f71bddb69b0a8bd7748072699edb
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58589749"
---
# <a name="create-an-organization-wide-team-in-microsoft-teams"></a>Erstellen eines organisationsweiten Teams in Microsoft Teams

Organisationsweite Teams bieten eine automatische Möglichkeit für jeden in einer kleinen bis mittelgroßen Organisation, einem einzelnen Team und einem Team für zusammenarbeiten bei der Zusammenarbeit bei zu sein.

Mit organisationsweiten Teams können globale Administratoren problemlos ein öffentliches Team mit den folgenden Merkmalen erstellen:
- Zieht jeden Benutzer in der Organisation ein. 
- Hält die Mitgliedschaft in Active Directory auf dem neuesten Stand, während Benutzer der Organisation beitreten und sie verlassen.

Nur globale Administratoren können organisationsweite Teams erstellen. Derzeit ist ein organisationsweites Team auf Organisationen mit nicht mehr als 10.000 Benutzern beschränkt. Es gibt auch einen Grenzwert von fünf organisationsweiten Teams pro Mandant. Wenn diese Anforderungen erfüllt sind, sehen globale Administratoren  beim Erstellen eines Teams die Option Organisationsweit als Option, wenn sie Team **ganz neu erstellen auswählen.** 

![Screenshot der Organisationsweiten Option zum Erstellen eines organisationsweiten Teams](media/create-org-wide-team.png "Screenshot der Organisationsweiten Option zum Erstellen eines organisationsweiten Teams")

Wenn ein organisationsweites Team erstellt wird, werden alle globalen Administratoren und Teams-Dienstadministratoren als Teambesitzer und alle aktiven Benutzer als Teammitglieder hinzugefügt. Nicht lizenzierte Benutzer werden dem Team ebenfalls hinzugefügt. Wenn ein nicht lizenzierter Benutzer sich zum ersten Mal bei Teams anmeldet, wird dem Benutzer eine Microsoft Teams Exploratory-Lizenz zugewiesen. Um mehr über die Exploratory-Lizenz zu erfahren, lesen Sie [Verwalten der Microsoft Teams Exploratory-Lizenz](teams-exploratory.md). 

Die folgenden Kontotypen werden Ihrem organisationsweiten Team nicht hinzugefügt:

- Konten, die zur Anmeldung gesperrt sind
- Gastbenutzer
- Ressourcen- oder Dienstkonten (z. B. Konten, die mit automatischen Telefonzentralen und Anrufwarteschleifen verbunden sind)
- Raum- oder Gerätekonten
- Konten, die durch ein freigegebenes Postfach gesichert sind

Wenn das Verzeichnis Ihrer Organisation so aktualisiert wird, dass es neue aktive Benutzer umfasst oder Konten von Benutzern deaktiviert, die nicht mehr in Ihrem Unternehmen arbeiten, werden Änderungen automatisch synchronisiert, und die Benutzer werden dem Team hinzugefügt oder aus dem Team entfernt. Teammitglieder können kein organisationsweites Team verlassen. Als Teambesitzer können Sie bei Bedarf Benutzer manuell hinzufügen oder entfernen.

> [!NOTE]
> - Wenn die Option Organisationsweit beim Erstellen eines Teams nicht angezeigt wird und Sie ein globaler Administrator sind, haben Sie möglicherweise das Limit von fünf organisationsweiten Teams erreicht, oder Ihre Organisation hat mehr als die aktuelle Größenbeschränkung von 10.000 Mitgliedern.  Wir arbeiten daran, dieses Limit künftig zu erhöhen. Organisationsweite Teams sind für Microsoft Teams for Education derzeit noch nicht verfügbar.
> - Räume, die nicht Teil einer Raumliste sind, Geräte- und Ressourcenkonten werden möglicherweise dem organisationsweiten Team hinzugefügt oder synchronisiert. Teambesitzer können diese Konten ganz einfach wieder aus dem Team entfernen.
> - Alle Aktionen des Systems zum Hinzufügen oder Entfernen von Mitgliedern werden im Kanal "Allgemein" gepostet. Der Kanal wird außerdem im Teams-Client mit „Neue Aktivität“ gekennzeichnet.
> - Wir erstellen automatisch ein organisationsweites Team für Ihre Organisation, wenn Ihre Organisation Teams und nicht mehr als 5.000 Benutzer hat. Der Teamname spiegelt den Mandantennamen wider verfügt über einen allgemeinen Kanal. Globale Administratoren können dieses Team wie jedes andere Team bearbeiten.

## <a name="best-practices"></a>Bewährte Methoden

Wir empfehlen Teambesitzern, die folgenden Aufgaben auszuführen, um Ihr organisationsweites Team bestens zu verwenden:

### <a name="allow-only-team-owners-to-post-to-the-general-channel"></a>Gestatten Sie nur Teambesitzern das Versenden von Beiträgen im Kanal „Allgemein“.

Reduzieren Sie die Anzahl der Beiträge, indem Sie nur Teambesitzern gestatten, im Kanal „Allgemein“ Beiträge zu versenden. 

1. Wechseln Sie zum Team, suchen Sie den Kanal „Allgemein“, und wählen Sie dann **˙˙˙ Weitere Optionen** > **Kanal verwalten** aus. 
2. Klicken Sie auf der Registerkarte **Kanaleinstellungen** auf **Berechtigungen**, und wählen Sie dann **Nur Besitzer können Nachrichten senden** aus.

### <a name="turn-off-team-and-team-name-mentions"></a>Deaktivieren der @Team und @ [Teamname]-Erwähnungen

Reduzieren Sie @Erwähnungen, um die Anzahl der Nachrichten für die ganze Organisation zu senken. 

1. Wechseln Sie zum Team, und klicken Sie auf **˙˙˙ Weitere Optionen**  >  **Team verwalten**. 
2. Klicken Sie auf der Registerkarte **Einstellungen** auf <strong>@Erwähnungen</strong> > schalten Sie **Mitgliedern die Option @Team oder @[Teamname]** aus. 

### <a name="automatically-show-important-channels"></a>Wichtige Kanäle automatisch anzeigen

Wichtige Kanäle anzeigen, um sicherzustellen, dass jeder in Ihrer Organisation sich an bestimmten Unterhaltungen beteiligt. Weitere Informationen finden Sie unter [Automatisches Festlegen von Kanalfavoriten für das gesamte Team](https://support.office.com/article/auto-favorite-channels-for-the-whole-team-a948272c-5aa5-429c-863c-4e1e1cd6b0f6). 

### <a name="set-up-channel-moderation"></a>Richten Sie eine Kanalmoderation ein

Erwägen Sie das Einrichten einer Kanalmoderation und übertragen Sie ausgewählten Teammitgliedern die Moderatorfunktionen. (Wenn die Moderation eingerichtet ist, erhalten Teambesitzer automatisch Moderatorenfunktionen.) Moderatoren können:

- Steuern, wer einen neuen Beitrag in einem Kanal starten kann
- Hinzufügen und Entfernen von Moderatoren
- Steuern, ob Teammitglieder auf vorhandene Kanalnachrichten antworten können
- Steuern, ob Bots und Connectors Kanalnachrichten senden können.

Weitere Informationen finden Sie unter [Einrichten und Verwalten der Kanalmoderation in Microsoft Teams](manage-channel-moderation-in-teams.md).

### <a name="remove-accounts-that-might-not-belong"></a>Entfernen Sie Konten, die möglicherweise nicht dazugehören

Obwohl Mitglieder ein organisationsweites Team nicht verlassen können, können Sie als Teambesitzer die Teamliste verwalten, indem Sie Konten entfernen, die nicht mitglied sind. **Stellen Sie sicher, dass Sie Teams zum Entfernen von Benutzern aus Ihrem organisationsweiten Team verwenden**. Wenn Sie eine andere Möglichkeit zum Entfernen eines Benutzers verwenden, z. B. der Microsoft 365 Admin Center oder aus einer Gruppe in Outlook, wird der Benutzer möglicherweise wieder zum organisationsweiten Team hinzugefügt.

## <a name="faq"></a>Häufig gestellte Fragen

### <a name="is-there-a-way-to-create-an-organization-wide-team-other-than-using-the-teams-client"></a>Gibt es eine Möglichkeit, ein organisationsweites Team zu erstellen, bei dem es sich nicht um die Verwendung des Teams handelt?

Globale Administratoren können ein organisationsweites Team nur mithilfe des Teams erstellen. Wenn Ihre Organisation das Erstellen von Teams auf die Verwendung von PowerShell einschränkt, empfiehlt es sich, die globalen Administratoren der Sicherheitsgruppe jener Benutzer hinzuzufügen, die ein Team erstellen können.

Weitere Informationen finden Sie unter [Verwalten von Personen, die Gruppen erstellen können](/microsoft-365/admin/create-groups/manage-creation-of-groups).

Wenn diese Problemumgehung keine Option ist, können Sie mithilfe von PowerShell ein öffentliches Team erstellen und einen globalen Administrator als Teambesitzer hinzufügen. Lassen Sie den globalen Administrator neben dem Teamnamen auf **weitere Optionen** und dann auf **Team bearbeiten** klicken. Ändern Sie nun den Datenschutz auf **organisationsweit – jeder Mitarbeiter in Ihrer Organisation wird automatisch hinzugefügt**. 

> [!NOTE]
> Nur Teambesitzer können auf die Option **Team bearbeiten** zugreifen, und nur globale Administratoren können die **Option Organisationsweit** anzeigen.

### <a name="is-there-a-way-to-convert-an-existing-team-to-an-organization-wide-team"></a>Gibt es eine Möglichkeit, ein vorhandenes Team in ein organisationsweites Team zu konvertieren?

Globale Administratoren können ein vorhandenes Team in ein organisationsweites Team konvertieren, indem sie es in einem Teams bearbeiten. Wechseln Sie zum Teamnamen und klicken Sie dann auf **Weitere Optionen**  >  **Team bearbeiten**.

### <a name="can-i-create-an-organization-wide-team-using-a-team-template"></a>Kann ich mithilfe einer Teamvorlage ein organisationsweites Team erstellen?

Teamvorlagen können nicht zum Erstellen eines organisationsweiten Teams verwendet werden. An diesem Feature wird zur Zeit noch gearbeitet. 

## <a name="see-also"></a>Mehr dazu

Sehen Sie sich ein Video zum Thema [Erstellen eines unternehmensweiten Teams in Microsoft Teams](https://support.office.com/article/037bb27a-bcc9-48fe-8d72-44d9482420a3) an.
