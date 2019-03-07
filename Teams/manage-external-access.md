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
description: Ihre IT-Administrator kann den Zugriff durch andere Domänen (Verbund) können Benutzer über diese Domänen Teams teilnehmen konfigurieren.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 97b322969d3975b6f9ca2b2079d46fe95ef45e52
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/07/2019
ms.locfileid: "30459924"
---
<a name="manage-external-access-federation-in-microsoft-teams"></a>Verwaltung des externen Zugriffs (Verbund) in Microsoft Teams
======================================================

Mit Microsoft-Teams, externen Zugriff können Benutzer aus anderen Domänen in Ihrer Chats und Anrufe teilnehmen. Sie können auch externe Benutzer zulassen, die noch Skype für Unternehmen Teilnahme an. 

Externen Zugriff (Verbund) und Gast Access unterscheiden:

- Gast Access erteilt eine einzelne Zugriffsberechtigung. Externer Zugriff erhält die Zugriffsberechtigung, eine gesamte Domäne.

- Einmal durch einen Teambesitzer gewährten Gast-Zugriffs kann Gastsystem auf [Ressourcen zugreifen](guest-experience.md)wie Channel Diskussionen und Dateien, für ein bestimmtes Team und Chat mit anderen Benutzern in das Team aus, dem sie eingeladen wurden. Mit externem Zugriff (federated Chat) haben die Teilnehmer externe Chat keinen Zugriff auf der einladen Organisation Teams oder Teamressourcen. Sie können nur Angebot federated Chat teilnehmen. Mandanten-Admins können zwischen den beiden Optionen, je nachdem, welcher Ebene der Zusammenarbeit mit der externen Partei wünschenswert ist. Administratoren können dann Ansätze oder beides, je nach ihren Anforderungen in der Organisation, aber es wird empfohlen, um zukünftig einen Gastzugriff eine vollständigere, gemeinsame Teams wünschen. 

Finden Sie in der folgenden Tabelle einen Vergleich von externen und Gast-Funktionen zuzugreifen.

| Funktion | Zugriff durch externe Benutzer | Gast Access-Benutzer |
|---------|-----------------------|--------------------|
| Benutzer kann mit einer anderen Person in einem anderen Unternehmen chat. | Ja |Ja  |
| Benutzer kann eine Person in einem anderen Unternehmen aufrufen. | Ja | Ja  |
| Benutzer kann sehen, wenn jemand aus einem anderen Unternehmen für Anruf oder Chat verfügbar ist | Ja | Ja,<sup>1</sup> |
| Benutzer kann externe konstant nach Benutzern suchen. | Ja,<sup>2</sup> | Nein |
| Benutzer kann Dateien freigeben. | Nein | Ja |
| Benutzer kann Teams Ressourcen zugreifen. | Nein | Ja |
| Benutzer kann einen Gruppenchat hinzugefügt werden | Nein | Ja |
| Benutzer kann an einer Besprechung hinzugefügt werden | Ja | Ja  |
| Weitere Benutzer können einen Chat mit einem externen Benutzer hinzugefügt werden | Keine<sup>3</sup> | n/v |
| Benutzer wird als von externer Seite identifiziert. | Ja | Ja  |
| Anwesenheitsinformationen wird angezeigt. | Ja | Ja  |
| Abwesend wird Nachricht angezeigt. | Nein | Ja |
| Einzelner Benutzer kann ausgeschlossen werden | Nein | Ja |
| @mentions werden unterstützt. | Nein | Ja |
||||

<sup>1</sup> bereitgestellt, dass der Benutzer wurde als Gast hinzugefügt und als Gast, die dem Mandanten Gast angemeldet ist.<br>
<sup>2</sup> nur per e-Mail oder Adresse Session Initiation Protocol (SIP).<br>
<sup>3</sup> externe (Verbund) Chat ist 1:1.

## <a name="turn-on-or-turn-off-external-access"></a>Aktivieren Sie oder deaktivieren Sie des externen Zugriffs

Die Microsoft-Teams & Skype für Business Admin Center können Sie um externen Zugriff zu verwalten.

1. Wählen Sie in der Microsoft-Teams & Skype für Business Admin Center **Org geltende Einstellungen** > **externen Zugriff**.

     ![Screenshot des externen Zugriff für die gesamte Org-Einstellungen](media/manage-external-access-1.png).

2. Bringen Sie den **externen Zugriff** Schalter zum **ein-** oder **Ausschalten**.

     ![Screenshot des externen Zugriffs Switch eingeschaltet](media/manage-external-access-2.png).

3. Klicken Sie auf **Speichern**. 

## <a name="add-or-block-a-domain"></a>Hinzufügen oder eine Domäne blockieren

Befolgen Sie diese Schritte zum Hinzufügen einer Domäne oder Deaktivieren des externen Zugriffs für eine Domäne aus.

1. Wählen Sie in der Microsoft-Teams & Skype für Business Admin Center **Org geltende Einstellungen** > **externen Zugriff**.

2. Wählen Sie **eine Domäne hinzufügen**. 
 
    ![Screenshot des externen Zugriffs-Seite mit einen Domäne Link hinzufügen](media/manage-external-access-3.png).

   Der Bereich **Domäne hinzufügen** wird angezeigt.

    ![Screenshot des Hinzufügen einer Domäne-Bereich](media/manage-external-access-4.png).


3. Geben Sie den Namen der Domäne, klicken Sie unter **Hinzufügen einer Domäne**; Geben Sie beispielsweise "contoso.com".

4. Wählen Sie **zugelassen** oder **blockiert**. Sie können diese Einstellung jederzeit ändern.

2. Wählen Sie **Fertig**.

Nachdem Sie eine Domäne hinzugefügt haben, sehen Sie den Domänennamen und den Status der Liste der Domänen auf der Seite externen Zugriff hinzugefügt.

## <a name="more-information"></a>Weitere Informationen

Informationen über Gast in Microsoft-Teams finden Sie unter [Manage Gast Access in Microsoft-Teams](manage-guests.md).