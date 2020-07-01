---
title: Parken und Fortsetzen von Anrufen in Microsoft Teams
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 04/12/2019
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.callparkpolicies.overview
- seo-marvel-apr2020
description: Hier erfahren Sie, wie Sie den Anruf Park verwenden und abrufen, um einen Anruf im Teams-Dienst in der Cloud zu halten.
ms.openlocfilehash: a9518705cd5edff3834be21732f78dd47352cd63
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938534"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a>Parken und Fortsetzen von Anrufen in Microsoft Teams

Parken und Abrufen ist eine Funktion, mit der Benutzer einen Anruf im Teams-Dienst in der Cloud halten können. Wenn ein Anruf abgestellt wird, generiert der Dienst einen eindeutigen Code für den Abruf des Anrufs. Der Benutzer, der den Anruf abgestellt hat, oder eine andere Person kann diesen Code und eine unterstützte APP oder ein unterstütztes Gerät verwenden, um den Anruf abzurufen. 

Einige häufige Szenarien für die Verwendung von Call Park sind: 

- Eine Empfangsdame parkt einen Anruf für jemanden, der in einer Fabrik arbeitet. Der Rezeptionist kündigt dann den Anruf und die Codenummer über das öffentliche adresssystem an. Der Benutzer, für den der Anruf ansteht, kann dann in der Factory-Etage ein Team Telefon aufnehmen und den Code zum Abrufen des Anrufs eingeben.
- Ein Benutzer parkt einen Anruf auf einem mobilen Gerät, da der Akku des Geräts knapp wird. Der Benutzer kann dann den Code eingeben, um den Anruf von einem Team-Tischtelefon abzurufen.
- Ein Supportmitarbeiter parkt einen Kundenanruf und sendet eine Ankündigung in einem Teams-Kanal, damit ein Experte den Anruf abruft und dem Kunden hilft. Ein Experte gibt den Code in Teams-Clients ein, um den Anruf abzurufen.

> [!IMPORTANT]
> Dieses Feature steht nur im Bereitstellungsmodus für Teams zur Verfügung. Weitere Informationen zu den Bereitstellungsmodi für Teams finden Sie Untergrund [Legendes zu Microsoft Teams und Skype for Business-Koexistenz und-Interoperabilität](teams-and-skypeforbusiness-coexistence-and-interoperability.md) .

## <a name="license-required"></a>Lizenz erforderlich

Zum Parken und Abrufen von Anrufen muss ein Benutzer ein Enterprise-VoIP-Benutzer sein, und ein Administrator muss dem Benutzer eine Anruf Park Richtlinie erteilen. Weitere Informationen zum Lizenzierungsmodell finden Sie in der [Microsoft Teams-Dienstbeschreibung](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).

## <a name="call-park-and-retrieve-feature-availability"></a>Parken anrufen und Verfügbarkeit von Funktionen abrufen

Anruf parken und Abrufen wird derzeit von den folgenden Clients und Geräten unterstützt. (Wird im Modus "nur für Teams" mit oder ohne PSTN-Konnektivität unterstützt.)

| Funktion | Teams-Desktop | Mac-app für Teams | Teams Web App (Edge) |Teams Mobile IOS/Android-App | IP-Telefon für Teams | Skype for Business-IP-Telefon |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|-----------------------------|
| Parken eines Anrufs | Ja  | Ja  | Ja  | Ja  | Ja | Nein |
| Abrufen eines geparkten Anrufs | Ja  | Ja  | Ja  | Ja  | Ja | Nein |
| Nicht abgerufener Anruf Ring zurück | Ja  | Ja  | Ja  | Ja  | Ja | Nein |

## <a name="configure-call-park-and-retrieve"></a>Konfigurieren des Anruf Parks und Abrufen

Sie müssen ein Administrator sein, um den Anruf Park zu konfigurieren und abzurufen, und das Feature ist standardmäßig deaktiviert. Sie können es für Benutzer aktivieren und Benutzergruppen mithilfe der Anruf Park Richtlinie erstellen. Wenn Sie die gleiche Richtlinie auf eine Reihe von Benutzern anwenden, können Sie Anrufe unter sich selbst Parken und abrufen. Zum Konfigurieren des Anruf Parks für Benutzer und zum Erstellen von Benutzergruppen für den Anruf Park befolgen Sie die nachstehenden Schritte zum [Zuweisen einer Anruf Park Richtlinie](#assign-a-call-park-policy) .

Informationen zum Verwenden der Funktion "Parken und abrufen" finden Sie unter [Parken eines Anrufs in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).

### <a name="enable-a-call-park-policy"></a>Aktivieren einer Anruf Park Richtlinie

1. Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu den Richtlinien für den **VoIP**-  >  **Anruf Park**.
2. Wählen Sie **Hinzufügen**aus.
3. Geben Sie der Richtlinie einen Namen, und wählen Sie dann "Parken **von** **anrufen zulassen** " auf ein.
4. Wählen Sie **Speichern**aus.

#### <a name="using-powershell"></a>Verwendung von PowerShell

Weitere Informationen finden Sie unter [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps).

### <a name="edit-a-call-park-policy"></a>Bearbeiten einer Anruf Park Richtlinie

1. Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu den Richtlinien für den **VoIP**-  >  **Anruf Park**.
2. Wählen Sie die Richtlinie aus, indem Sie zunächst links neben die Richtlinienbezeichnung und dann auf **Bearbeiten** klicken.
3. Schalten Sie den **Anruf Park** auf **aus** oder **ein**.
4. Klicken Sie auf **Speichern**.

#### <a name="using-powershell"></a>Verwendung von PowerShell

Weitere Informationen finden Sie unter [Satz-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps). Wenn Sie beispielsweise die Standardeinstellung ändern möchten, führen Sie die folgenden Aktionen aus:

  ```PowerShell
  Set-CsTeamsCallParkPolicy -Identity Global -AllowCallPark $true
  ```

### <a name="assign-a-call-park-policy"></a>Zuweisen einer Anruf Park Richtlinie

[!INCLUDE [assign-policy](includes/assign-policy.md)]
 
Siehe auch [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps).

## <a name="troubleshooting"></a>Problembehandlung

Wenn Benutzer die Schaltfläche "Parken" oder "abrufen" nicht sehen können: 

- Überprüfen Sie, ob der Benutzer die Anruf Park Richtlinie aktiviert hat. 

Wenn ein Benutzer versucht, einen Anruf abzurufen und nicht erfolgreich ist, überprüfen Sie Folgendes:

- Überprüfen, ob der Benutzer den Teams-Client oder ein Team fähiges Gerät/Telefon verwendet
- Gruppieren – ist der Benutzer ein Mitglied der Gruppe "Anruf parken", die darauf basiert, dass dieselbe Teams-Anruf Park Richtlinie zugewiesen ist. 
- Island-Modus – Parken und Abrufen von anrufen ist im Modus "Teams Island" nicht verfügbar.
- Der Anruf wurde bereits abgerufen oder beendet.

## <a name="related-topics"></a>Verwandte Themen

[Parken eines Anrufs in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[Zuweisen von Richtlinien zu Ihren Benutzern in Microsoft Teams](assign-policies.md)
