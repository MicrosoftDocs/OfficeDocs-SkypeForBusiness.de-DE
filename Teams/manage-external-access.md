---
title: Verwaltung des externen Zugriffs (Verbund) in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 01/30/2019
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: karvell
search.appverid: MET150
description: Ihr IT-Administrator kann den externen Zugriff für andere Domänen (Federation) konfigurieren, damit Benutzer aus diesen Domänen an Teams teilnehmen können.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3f6a3dc6016eb52d58e82e9e9022d1bb8575404b
ms.sourcegitcommit: b9e7a11d8332a029a4f1cd4e396787f5a74f0a44
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "34702720"
---
<a name="manage-external-access-federation-in-microsoft-teams"></a>Verwaltung des externen Zugriffs (Verbund) in Microsoft Teams
======================================================

Mit Microsoft Teams externer Zugriff können Benutzer aus anderen Domänen an ihren Chats und anrufen teilnehmen. Sie können auch externen Benutzern, die weiterhin Skype for Business Online oder Skype for Business on-Prem verwenden, die Teilnahme erlauben. 

Der externe Zugriff (Föderation) und Gastzugriff unterscheiden sich von den folgenden:

- Gastzugriff gewährt einer einzelnen Person Zugriffsberechtigungen. Externer Zugriff gewährt einer gesamten Domäne Zugriffsberechtigungen.

- Der Gastzugriff, nachdem er von einem Teambesitzer gewährt wurde, ermöglicht es einem Gast, auf [Ressourcen](guest-experience.md)wie Kanal Diskussionen und Dateien für ein bestimmtes Team zuzugreifen und mit anderen Benutzern in dem Team zu chatten, zu dem Sie eingeladen wurden. Beim externen Zugriff (Federated-Chat) haben die Teilnehmer des externen Chats keinen Zugriff auf die Teams oder Teamressourcen der einladenden Organisation. Sie können nur an einem einzigen Partner-Chat teilnehmen. Mandantenadministratoren können zwischen den beiden Kommunikationsoptionen wählen, je nachdem, welche Ebene der Zusammenarbeit für die externe Partei erwünscht ist. Administratoren können je nach Ihren organisatorischen Anforderungen entweder Ansätze oder beides auswählen, aber wir empfehlen, den Gastzugriff für eine umfassendere, kollaborative Teams-Erfahrung zu aktivieren. 

In der folgenden Tabelle finden Sie eine Übersicht über die Features für den externen und den Gastzugriff.

| Feature | Benutzer für externen Zugriff | Gastzugriff-Benutzer |
|---------|-----------------------|--------------------|
| Der Benutzer kann mit jemandem in einem anderen Unternehmen chatten. | Ja |Ja |
| Der Benutzer kann jemanden in einem anderen Unternehmen anrufen | Ja | Ja |
| Der Benutzer kann sehen, ob jemand aus einem anderen Unternehmen für Anrufe oder Chats zur Verfügung steht. | Ja | Ja<sup>1</sup> |
| Benutzer kann über externe Mandanten nach Benutzern suchen | Ja<sup>2</sup> | Nein |
| Benutzer kann Dateien freigeben | Nein | Ja |
| Benutzer kann auf Teamressourcen zugreifen | Nein | Ja |
| Benutzer kann zu einem Gruppen-Chat hinzugefügt werden | Nein | Ja |
| Benutzer kann zu einer Besprechung hinzugefügt werden | Ja | Ja |
| Zusätzliche Benutzer können einem Chat mit einem externen Benutzer hinzugefügt werden. | Nr.<sup>3</sup> | Nicht zutreffend |
| Der Benutzer wird als externer Partner identifiziert | Ja | Ja |
| Anwesenheit wird angezeigt | Ja | Ja |
| Abwesenheitsnachricht wird angezeigt | Nein | Ja |
| Der einzelne Benutzer kann blockiert werden. | Nein | Ja |
| @Mentions werden unterstützt | Nein | Ja |
| Private Anrufe tätigen | Ja | Ja |
| IP-Video zulassen | Ja | Ja |
| Bildschirmfreigabe Modus | Ja | Ja |
| Sofortbesprechung zulassen | Nein | Ja |
| Bearbeiten von gesendeten Nachrichten | Ja | Ja |
| Kann gesendete Nachrichten löschen | Ja | Ja |
| Verwenden von Giphy in einer Unterhaltung | Ja | Ja |
| Verwenden von Memen in einer Unterhaltung | Ja | Ja |
| Verwenden von Aufklebern in einer Unterhaltung | Ja | Ja |
||||

<sup>1</sup> vorausgesetzt, dass der Benutzer als Gast hinzugefügt wurde und als Gast für den Gast Mandanten angemeldet ist.<br>
<sup>2</sup> nur per e-Mail oder SIP-Adresse (Session Initiation Protocol).<br>
<sup>3</sup> externer Chat (Federated) ist nur 1:1.

> [!NOTE]
> Weitere Informationen zu Gast Features und der Gast Erfahrung finden Sie unter [Aktivieren oder Deaktivieren des Gastzugriffs auf Microsoft Teams](https://docs.microsoft.com/microsoftteams/set-up-guests) und [der Art der Gast Erfahrung](https://docs.microsoft.com/microsoftteams/guest-experience).

## <a name="turn-on-or-turn-off-external-access-users-can-communicate-with-skype-for-business-and-teams-users"></a>Aktivieren oder Deaktivieren des externen Zugriffs (Benutzer können mit Skype for Business-und Teams-Benutzern kommunizieren)

Sie können die Microsoft Teams #a0 Skype for Business Admin Center verwenden, um den externen Zugriff zu verwalten.

1. Wählen Sie im Microsoft Teams #a0 Skype for Business Admin Center die Option **organisationsweite Einstellungen** > **externer Zugriff**aus.

     ![Screenshot der organisationsweiten Einstellungen für externen Zugriff](media/manage-external-access-1.png).

2. Aktivieren oder **Deaktivieren**Sie die **Benutzer können mit Skype for Business und Teams kommunizieren** . ****

     ![Screenshot des aktivierten externen Zugriffs Schalters](media/manage-external-access-2.png).

3. Klicken Sie auf **Speichern**. 

## <a name="add-or-block-a-domain"></a>Hinzufügen oder blockieren einer Domäne

Führen Sie die folgenden Schritte aus, um eine Domäne hinzuzufügen oder den externen Zugriff für eine Domäne zu deaktivieren.

1. Wählen Sie im Microsoft Teams #a0 Skype for Business Admin Center die Option **organisationsweite Einstellungen** > **externer Zugriff**aus.

2. Wählen Sie **Domäne hinzufügen**. 
 
    ![Screenshot der Seite ' externer Zugriff ' mit Link ' Domäne hinzufügen '](media/manage-external-access-3.png).

   Der Bereich **Domäne hinzufügen** wird angezeigt.

    ![Screenshot des Bereichs "Domäne hinzufügen"](media/manage-external-access-4.png).


3. Geben **Sie Unterdomäne hinzufügen**den Namen der Domäne ein. Geben Sie beispielsweise contoso.com ein.

4. Wählen Sie **Zulässig** oder **Blockiert**. Sie können diese Einstellung jederzeit ändern.

2. Wählen Sie **Fertig**aus.

Nachdem Sie eine Domäne hinzugefügt haben, werden der Domänenname und der Status der Liste der Domänen auf der Seite "externer Zugriff" angezeigt.

## <a name="more-information"></a>Weitere Informationen

Informationen zum Gastzugriff in Microsoft Teams finden Sie unter [Verwalten des Gastzugriffs in Microsoft Teams](manage-guests.md).
