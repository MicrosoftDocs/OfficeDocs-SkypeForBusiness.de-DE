---
title: Parken und fortsetzen in Microsoft-Teams
ms.author: lolaj
author: lolaj
manager: serdars
ms.date: 12/13/2018
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service:
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Verwenden Sie Parken und fortsetzen, um einen Anruf in der Warteschleife im Dienst Teams in der Cloud.
ms.openlocfilehash: 02ec2b3af52cac65f82f5f0f0fc2b4b54ae61369
ms.sourcegitcommit: 5f7e078125f810a9e9a89052854ef63916afe7d3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/14/2018
ms.locfileid: "27283159"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a>Parken und fortsetzen in Microsoft-Teams

Parken und Fortsetzen von Anrufen ist ein Feature, in dem einen Benutzer einen Anruf in der Warteschleife im Dienst Teams in der Cloud. Wenn Sie ein Anruf geparkt wurde, erstellt der Dienst einen eindeutigen Code für den Abruf von Anrufen. Der Benutzer, der den Anruf oder eine andere Person geparkt kann dann Code und einen unterstützten app oder ein Gerät verwenden, um den Anruf abzurufen. 

Einige häufigen Szenarien für die Verwendung des Parkens von Anrufen werden: 

- Ein Empfangsmitarbeiter parks einen Anruf nach einer Person in einer Factory arbeiten. Die Empfangsmitarbeiter Ankündigung klicken Sie dann den Anruf und die Anzahl von Code über das öffentliche Adresse-System. Klicken Sie dann kann der Benutzer, die der Anruf ist ein Telefon Teams werksseitige aufzunehmen und geben Sie den Code, um den Anruf entgegenzunehmen.
- Ein Benutzer parks ein Anrufs auf einem mobilen Gerät, da die Batterie Gerät nicht mehr genug Power vorhanden ist. Der Benutzer kann dann geben Sie dann code zum Abrufen des Anrufs von einem Telefonapparat Teams.
- Eine repräsentative Parks Unterstützung ein Kunden aufrufen und sendet eine Ankündigung in einem Kanal Teams für einen Experten So rufen Sie den Anruf und helfen Sie dem Kunden. Gibt den Code ein Experte in Teams-Clients, um den Anruf

> [!IMPORTANT]
> Dieses Feature ist nur im Modus nur Teams Bereitstellung zur Verfügung. Weitere Informationen zu Bereitstellungsmethoden Teams finden Sie unter [Grundlegendes zu Microsoft-Teams und Skype für Interoperabilität und Koexistenz Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>Lizenz erforderlich

Um Parken und Anrufe wiederaufnehmen, muss ein Benutzer einen Enterprise-VoIP-Benutzer sein, und ein Administrator muss dem Benutzer eine Anruf Parken Richtlinie erteilen. Weitere Details zur am Lizenzierungsmodell finden Sie unter [Office 365-Lizenzierung für Microsoft-Teams](office-365-licensing.md).

## <a name="call-park-and-retrieve-feature-availability"></a>Parken und Fortsetzen der Verfügbarkeit von Features

Parken und fortsetzen wird durch die folgenden Clients und Geräten derzeit unterstützt. (Unterstützt nur Teams Modus mit oder ohne PSTN-Anbindung.)

| Funktion | Teams Desktop | Teams Mac-App | Teams Web App (Edge) |Mobile-iOS/Android-App-Teams | Teams IP-Telefon | Skype für Business IP-Telefon |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|-----------------------------|
| Parken eines Anrufs | Ja | Ja | Ja | In Kürze verfügbar | In Kürze verfügbar| Nein |
| Abrufen eines geparkten Anrufs | Ja | Ja | Ja | In Kürze verfügbar | In Kürze verfügbar| Nein |
| Wieder aufgehoben abgerufenen Anruf ring | Ja | Ja | Ja | In Kürze verfügbar | In Kürze verfügbar| Nein |

## <a name="configuring-call-park-and-retrieve"></a>Konfigurieren von Parken und fortsetzen

Sie müssen ein Administrator konfigurieren Parken und fortsetzen sein, und das Feature ist standardmäßig deaktiviert. Sie können diese für Benutzer aktivieren und Benutzergruppen mit der Anruf Parken Richtlinie erstellen. Wenn Sie die gleiche Richtlinie auf eine Gruppe von Benutzern anwenden, werden sie Parken und anrufen untereinander abrufen können. Zum Konfigurieren des Parkens von Anrufen für Benutzer, und Anruf Parken Benutzergruppen erstellen, befolgen Sie die folgenden Schritte aus.

Informationen zum Verwenden der Parken und Abrufen von Feature finden Sie unter [Parken eines Anrufs in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).

### <a name="configure-call-park-and-retrieve-with-powershell"></a>Konfigurieren Sie des Parkens von Anrufen, und rufen Sie mit PowerShell

Verwenden Sie das [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) PowerShell-Cmdlet eine Anruf Parken Richtlinie erstellen.

Verwenden Sie das [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) PowerShell-Cmdlet, um eine Anruf Parken Richtlinie zu erteilen.

## <a name="troubleshooting"></a>Problembehandlung

Wenn Benutzer nicht finden Sie unter der Park oder Schaltfläche abzurufen: 

- Überprüfen Sie, dass der Benutzer die Richtlinie zum Parken von Anrufen aktiviert hat. 

Wenn ein Benutzer versucht, einen Anruf abzurufen und nicht erfolgreich ist, überprüfen Sie Folgendes:

- Stellen Sie sicher, dass der Benutzer den Client Teams oder ein Teams-aktivierten Gerät/Telefon verwendet wird
- Gruppierung – ist der Benutzer ein Mitglied der Gruppe der Anruf Parken.
- Island-Modus – Parken und fortsetzen ist im Teams Island Modus nicht verfügbar.
- Der Anruf wurde bereits abgerufen oder beendet wurde.

## <a name="more-information"></a>Weitere Informationen

[Parken eines Anrufs in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).