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
description: Verwenden Sie parken und abrufen, um einen Anruf im Teams-Dienst in der Cloud zu halten.
ms.openlocfilehash: b4b5200f139f5610ff1109b97742607d3b633ff6
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824593"
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

Zum Parken und Abrufen von Anrufen muss ein Benutzer ein Enterprise-VoIP-Benutzer sein, und ein Administrator muss dem Benutzer eine Anruf Park Richtlinie erteilen. Weitere Informationen zum Lizenzierungsmodell finden Sie unter [Office 365-Lizenzierung für Microsoft Teams](office-365-licensing.md).

## <a name="call-park-and-retrieve-feature-availability"></a>Parken anrufen und Verfügbarkeit von Funktionen abrufen

Anruf parken und Abrufen wird derzeit von den folgenden Clients und Geräten unterstützt. (Wird im Modus "nur für Teams" mit oder ohne PSTN-Konnektivität unterstützt.)

| Funktion | Teams-Desktop | Mac-app für Teams | Teams Web App (Edge) |Teams Mobile IOS/Android-App | IP-Telefon für Teams | Skype for Business-IP-Telefon |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|-----------------------------|
| Parken eines Anrufs | Ja | Ja | Ja | Ja | In Kürze verfügbar| Nein |
| Abrufen eines geparkten Anrufs | Ja | Ja | Ja | Ja | In Kürze verfügbar| Nein |
| Nicht abgerufener Anruf Ring zurück | Ja | Ja | Ja | Ja | In Kürze verfügbar| Nein |

## <a name="configuring-call-park-and-retrieve"></a>Konfigurieren des Anruf Parks und Abrufen

Sie müssen ein Administrator sein, um den Anruf Park zu konfigurieren und abzurufen, und das Feature ist standardmäßig deaktiviert. Sie können es für Benutzer aktivieren und Benutzergruppen mithilfe der Anruf Park Richtlinie erstellen. Wenn Sie die gleiche Richtlinie auf eine Reihe von Benutzern anwenden, können Sie Anrufe unter sich selbst Parken und abrufen. Zum Konfigurieren des Anruf Parks für Benutzer und zum Erstellen von Benutzergruppen für den Anruf Park befolgen Sie die nachstehenden Schritte zum [Zuweisen einer Anruf Park Richtlinie](#assign-a-call-park-policy) .

Informationen zum Verwenden der Funktion "Parken und abrufen" finden Sie unter [Parken eines Anrufs in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).

### <a name="enable-a-call-park-policy"></a>Aktivieren einer Anruf Park Richtlinie

Führen Sie die folgenden Schritte aus, um eine Anruf Park Richtlinie zu aktivieren:

1. Wechseln Sie zu den Richtlinien für**VoIP** > -**Anruf Park des** **Microsoft Teams Admin Center** > .
2. Wählen Sie **neue Richtlinie**aus.
3. Geben Sie der Richtlinie einen Namen, und wählen Sie dann "Parken **von** **anrufen zulassen** " auf ein.
4. Wählen Sie **Speichern**aus.

### <a name="assign-a-call-park-policy"></a>Zuweisen einer Anruf Park Richtlinie

Führen Sie die folgenden Schritte aus, um einem oder mehreren Benutzern eine Anruf Park Richtlinie zuzuweisen:

1. Wechseln Sie zu den Richtlinien für**VoIP** > -**Anruf Park des** **Microsoft Teams Admin Center** > .
2. Wählen Sie die gewünschte Richtlinie aus, indem Sie links neben die Richtlinienbezeichnung klicken.
3. Wählen Sie **Benutzer verwalten** aus.
4. Suchen Sie im Bereich **Benutzer verwalten** anhand des Anzeigenamens oder des Benutzernamens nach dem Benutzer, wählen Sie den Namen aus, und klicken Sie auf **Hinzufügen**. Wiederholen Sie diesen Schritt für jeden Benutzer, den Sie hinzufügen wollen.
5. Wenn Sie fertig sind, klicken Sie auf **Speichern**.
 
### <a name="configure-call-park-and-retrieve-with-powershell"></a>Konfigurieren des Anruf Parks und Abrufen mit PowerShell

Verwenden Sie das PowerShell [-Cmdlet New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) , um eine Anruf Park Richtlinie zu erstellen.

Verwenden Sie das PowerShell [-Cmdlet Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) , um eine Anruf Park Richtlinie zu erteilen.

Sie können die Standardeinstellung mithilfe von [CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps) wie folgt ändern:

`Set-CsTeamsCallParkPolicy -Identity Global -AllowCallPark $true`


## <a name="troubleshooting"></a>Problembehandlung

Wenn Benutzer die Schaltfläche "Parken" oder "abrufen" nicht sehen können: 

- Überprüfen Sie, ob der Benutzer die Anruf Park Richtlinie aktiviert hat. 

Wenn ein Benutzer versucht, einen Anruf abzurufen und nicht erfolgreich ist, überprüfen Sie Folgendes:

- Überprüfen, ob der Benutzer den Teams-Client oder ein Team fähiges Gerät/Telefon verwendet
- Gruppieren – ist der Benutzer ein Mitglied der Gruppe "Anruf parken", die darauf basiert, dass dieselbe Teams-Anruf Park Richtlinie zugewiesen ist. 
- Island-Modus – Parken und Abrufen von anrufen ist im Modus "Teams Island" nicht verfügbar.
- Der Anruf wurde bereits abgerufen oder beendet.

## <a name="more-information"></a>Weitere Informationen

[Parken eines Anrufs in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).
