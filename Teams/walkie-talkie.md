---
title: Anwendung "Walkie-Talkie" in Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Konfigurieren der Walkie-Talkie-App in Microsoft Teams aus sicht des ITAdmin
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 63cd853b8a068e7acfc5752e3cd94b5d0102bc2f
ms.sourcegitcommit: 04eba352d9e203aa9cd1282c4f4c7158a0469678
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2021
ms.locfileid: "49944590"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a>Walkie-Talkie-App in Microsoft Teams

Die Walkie-Talkie-App in Teams bietet sofortige Push-to-Talk-Kommunikation für Ihr Team und ist jetzt unter Android verfügbar. Mithilfe von "Walkie-Talkie" können Benutzer eine Verbindung mit ihrem Team über die gleichen Kanäle herstellen, deren Mitglieder sie sind. Nur Benutzer, die sich in einem Kanal mit einem Walkie Talkie verbinden, werden Teilnehmer und können miteinander per Push-to-Talk kommunizieren – und das jeweils einmal.

Mit Walkie Talkie in Teams können Mitarbeiter in Frontline jetzt sicher mit einer vertrauten PtT-Erfahrung kommunizieren, ohne sperrige Radiogeräte mit sich führen zu müssen, und Walkie Talkie funktioniert überall mit WLAN oder mobiler Internetverbindung.

## <a name="getting-started"></a>Erste Schritte

### <a name="deploying-walkie-talkie"></a>Bereitstellen von Walkie Talkie

Derzeit ist "Walkie-Talkie" nicht vorinstalliert. Um dieses Feature für Benutzer in Ihrer Organisation zu aktivieren, [](teams-app-setup-policies.md)müssen Sie der App-Setuprichtlinie, die Benutzern zugewiesen ist, aus dem   Teams Admin Center ["Walkie Talkie" hinzufügen.](https://admin.teams.microsoft.com/)

Nach der Aktivierung wird das Talkie von Walkie innerhalb von 48 Stunden in der Android-App verfügbar sein.

### <a name="adding-walkie-talkie-to-your-app-list"></a>Hinzufügen von Walkie Talkie zu Ihrer App-Liste

Im Microsoft Teams Admin Center sollten Sie unter **"Setuprichtlinien** für Teams-Apps" die Einstellung "Benutzerheften zulassen" auf  >  "Ein" **festgelegt haben.**  Klicken Sie dann unter dem Abschnitt "Angeheftet Apps" auf **"Apps hinzufügen".**

:::image type="content" source="media/deploy-walkie-talkie-1.png" alt-text="Zeigt den Abschnitt "Angeheftet Apps" und die Schaltfläche "Apps hinzufügen" an, die ausgewählt werden soll.":::

Verwenden Sie **im bereich "Angeheftet** Apps hinzufügen", der auf der rechten Seite angezeigt wird, das Textfeld "Suchen", um nach "Walkie-Talkie" zu suchen.  Wenn sie als Suchergebnis angezeigt  wird, klicken Sie rechts neben dem Namen auf die Schaltfläche "Hinzufügen", um sie Ihrer Liste hinzuzufügen.

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="Zeigt die Randleiste "Angeheftet Apps hinzufügen" mit Walkie in den Suchbereich und die Walkie-Talkie-App in den Suchergebnissen mit der Schaltfläche "Hinzufügen" daneben.":::

Die Walkie-Talkie-App sollte nun in der Liste "Angeheftet Apps" angezeigt werden und steht zur Verfügung, sobald Sie auf die Schaltfläche **"Speichern"** klicken.

:::image type="content" source="media/deploy-walkie-talkie-3.png" alt-text="Zeigt die Liste "Angeheftet Apps" mit hinzugefügter Walkie-Talkie-App und der Schaltfläche "Speichern" unterhalb der Liste an.":::

### <a name="network-documentation"></a>Netzwerkdokumentation

Walkie Talkie in Teams erfordert Eine Internetverbindung und unter den Netzwerkbedingungen ist eine optimale Erfahrung erforderlich.

|Metrik | Erforderlich |
|---|---|
|Latenz (RTT) | < 300 ms |
|Jitter |< 30 ms |
|Paketverlust |< 1 % |

Wie bereits erwähnt, hat die Qualität der Netzwerkkonnektivität, insbesondere durch die Anzahl der:

- **Latenz (** Latenz) – Dies ist die Zeit, die benötigt wird, um ein IP-Paket von Punkt A zu Punkt B im Netzwerk zu erhalten. Diese Verzögerung der Weitergabe im Netzwerk ist im Wesentlichen mit der physischen Entfernung zwischen den beiden Punkten und der Lichtgeschwindigkeit verknüpft. Dazu gehört auch der Mehraufwand durch die zwischen den Punkten vorhandenen Router. Latenz wird als Round-Trip-Zeit (Round-Trip Time, RTT) gemessen.
- **Paketverlust** – Dies wird häufig als Prozentsatz der Pakete definiert, die in einem bestimmten Zeitfenster verloren gehen. Paketverluste wirken sich direkt auf die Audioqualität aus – von kleinen, einzelnen verlorenen Paketen, die fast keine Auswirkungen haben, bis hin zu Aufbruchverlusten im Hintergrund, die zu einem vollständigen Audioausfall führen.
- **Jitter** – Dies ist die durchschnittliche Änderung der Verzögerung zwischen aufeinander folgenden Paketen.

Die erwartete Datennutzung von Walkie Talkie beträgt ca. 20 KB/s beim Senden oder Empfangen von Audio. Im Leerlauf ist die erwartete Datennutzung von Walkie Talkie unerheblich.

### <a name="walkie-talkie-devices"></a>Walkie-Talkie-Geräte

Frontlinemitarbeiter müssen häufig anrufe sprechen und empfangen, auch wenn ihr Telefon gesperrt ist. Diese Erfahrung ist über spezielle Geräte mit einer dedizierten PTT-Schaltfläche möglich.

- Headsets
  - Verkabelte Headsets[(Klein Electronic)](https://www.kleinelectronics.com/poc-accessories/mtwt/)
  - Drahtlose Headsets[(Jabra BlueParrott)](https://www.blueparrott.com/microsoft-teams-walkie-talkie)
- Zerklüftete Telefone
  - Samsung Galaxy XCover Pro
    - [Weitere Informationen.](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/)
    - [Einrichtungshandbuch.](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm)

> [!NOTE]
> Diese Geräte sind nicht für Teams zertifiziert. Sie wurden für die Zusammenarbeit mit Teams Walkie Talkie überprüft.

### <a name="license-requirements"></a>Lizenzanforderungen

Die Walkie -Talkie-App ist in allen kostenpflichtigen Lizenzen von Teams in [Office 365-Abonnements enthalten.](https://docs.microsoft.com/MicrosoftTeams/office-365-licensing) Weitere Informationen zum Abrufen von Microsoft Teams finden Sie unter ["Wie kann ich auf Microsoft Teams zugreifen?"](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)

> [!NOTE]
> Bestimmte erweiterte Features erfordern möglicherweise eine zusätzliche Lizenzierung. Für die Integration in Samsung Galaxy XCover Pro ist z. B. eine Knox-Lizenz erforderlich.

## <a name="further-information"></a>Weitere Informationen

- ITAdmins können die Kontrolle darüber behalten, wer über die Richtlinien für Apps walkie Talkie verwendet.
- Wenn Ihr Frontline-Mitarbeiter mobile Daten für die Kommunikation über Teams verwendet, verwendet Walkie Talkie die gleiche Methode.
- In Situationen mit geringer Bandbreite oder in Situationen, in denen Ihr Smartphone angeschlossen ist und funktioniert, sollte ein Walkie Talkie gut funktionieren. Walkie Talkie funktioniert nicht, wenn überhaupt keine Verbindung besteht.

Weitere Informationen zur Endbenutzererfahrung finden Sie unter:

- [Erste Schritte mit Teams Walkie Talkie](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [Kommunizieren mit Ihrem Team mit Walkie Talkie](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
