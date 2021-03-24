---
title: Walkie Talkie-Anwendung in Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Konfigurieren der Walkie Talkie-App in Microsoft Teams aus itAdmin-Perspektive
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
ms.openlocfilehash: 90d5135196de9ecf62085e88053d80299b6e5a58
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097461"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a>Walkie Talkie-App in Microsoft Teams

Die Walkie Talkie-App in Teams bietet sofortige Push-to-Talk(PTT)-Kommunikation für Ihr Team und ist jetzt unter Android verfügbar. Walkie Talkie ermöglicht Benutzern die Verbindung mit ihrem Team über die gleichen zugrunde liegenden Kanäle, deren Mitglieder sie sind. Nur Benutzer, die eine Verbindung mit Walkie Talkie in einem Kanal herstellen, werden Teilnehmer und können jeweils per Push-to-Talk miteinander kommunizieren.

Mit Walkie Talkie in Teams können Mitarbeiter von Frontline jetzt sicher mit einer vertrauten PTT-Erfahrung kommunizieren, ohne sperrige Radios mit sich führen zu müssen, und Walkie Talkie funktioniert überall mit WLAN oder mobiler Internetverbindung.

## <a name="getting-started"></a>Erste Schritte

### <a name="deploying-walkie-talkie"></a>Bereitstellen von Walkie Talkie

Derzeit ist Walkie Talkie nicht vorinstalliert. Um dieses Feature für Benutzer in Ihrer Organisation zu aktivieren, müssen Sie Walkie Talkie zur [App-Setuprichtlinie](teams-app-setup-policies.md)hinzufügen, die Benutzern aus dem   Teams Admin Center zugewiesen [ist.](https://admin.teams.microsoft.com/)

Nach der Aktivierung wird Walkie Talkie innerhalb von 48 Stunden in der Android-App verfügbar sein.

### <a name="adding-walkie-talkie-to-your-app-list"></a>Hinzufügen von Walkie Talkie zu Ihrer App-Liste

Im Microsoft Teams Admin Center sollten Sie unter Richtlinien für das Einrichten von **Teams-Apps** benutzerfreundliche  >   **Einstellungen** auf **Ein festlegen.** Klicken Sie dann unter dem Abschnitt Angeheftet Apps **auf +Apps hinzufügen.**

:::image type="content" source="media/deploy-walkie-talkie-1.png" alt-text="Zeigt den Abschnitt Angeheftet Apps und die Schaltfläche Apps hinzufügen an, die ausgewählt werden soll.":::

Verwenden Sie im Bereich **Angeheftet Apps** hinzufügen  auf der rechten Seite das Textfeld Suchen, um nach Walkie Talkie zu suchen. Wenn Sie es als Suchergebnis  haben, wählen Sie die Schaltfläche Hinzufügen rechts neben dem Namen aus, um sie ihrer Liste hinzuzufügen.

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="Zeigt die Randleiste "Angeheftet Apps hinzufügen" mit Walkie, die in den Suchbereich eingegeben wurde, und die Walkie Talkie-App in den Suchergebnissen mit der Schaltfläche Hinzufügen daneben.":::

Die Walkie Talkie-App sollte nun in der Liste Angeheftet Apps angezeigt werden und steht zur Verwendung zur Verfügung, sobald Sie auf die Schaltfläche **Speichern** klicken.

:::image type="content" source="media/deploy-walkie-talkie-3.png" alt-text="Zeigt die Liste angeheftet apps mit der hinzugefügten Walkie Talkie-App und die Schaltfläche Speichern unter der Liste an.":::

### <a name="network-documentation"></a>Netzwerkdokumentation

Walkie Talkie in Teams erfordert Internetverbindung und unterhalb der Netzwerkbedingungen sind für optimale Benutzererfahrung erforderlich.

|Metrik | Erforderlich |
|---|---|
|Latenz (RTT) | < 300 ms |
|Jitter |< 30 ms |
|Paketverlust |< 1 % |

Wie bereits erwähnt, hat die Qualität von Echtzeitmedien über ein IP-Netzwerk erhebliche Auswirkungen auf die Qualität der Netzwerkkonnektivität, vor allem aber durch die Menge von:

- **Latenz :** Dies ist die Zeit, die zum Empfangen eines IP-Pakets von Punkt A bis Punkt B im Netzwerk benötigt wird. Diese Verzögerung der Netzwerkweiterleitung ist im Wesentlichen an den physischen Abstand zwischen den beiden Punkten und die Lichtgeschwindigkeit gebunden, einschließlich des mehr Aufwands, der von den verschiedenen Routern dazwischen genommen wird. Die Latenz wird als Roundtripzeit (Round-Trip Time, RTT) gemessen.
- **Paketverlust** – Dies ist häufig als Prozentsatz der Pakete definiert, die in einem bestimmten Zeitfenster verloren gehen. Der Paketverlust wirkt sich direkt auf die Audioqualität aus – von kleinen, einzelnen verlorenen Paketen, die fast keine Auswirkungen haben, bis hin zu Back-to-Back-Burstverlusten, die einen vollständigen Audioausschnitt verursachen.
- **Jitter** – Dies ist die durchschnittliche Änderung der Verzögerung zwischen aufeinander folgenden Paketen.

Die erwartete Datennutzung von Walkie Talkie beträgt etwa 20 KB/s beim Senden oder Empfangen von Audio. Im Leerlauf ist die erwartete Datennutzung von Walkie Talkie vernachlässigbar.

### <a name="walkie-talkie-devices"></a>Walkie Talkie-Geräte

Frontlinemitarbeiter müssen häufig auch dann sprechen und Empfangen von Walkie Talkie-Anrufen, wenn ihre Telefone gesperrt sind. Diese Erfahrung ist über spezielle Geräte mit einer dedizierten PTT-Schaltfläche möglich.

- Headsets
  - Kabelgebundene Headsets ([Klein Electronics](https://www.kleinelectronics.com/poc-accessories/mtwt/))
  - Drahtlose Headsets ([Jabra BlueParrott](https://www.blueparrott.com/microsoft-teams-walkie-talkie))
- Robuste Telefone
  - Samsung Galaxy XCover Pro
    - [Weitere Informationen](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/).
    - [Einrichtungshandbuch](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm).

> [!NOTE]
> Diese Geräte sind nicht von Teams zertifiziert. Sie wurden für die Zusammenarbeit mit Teams Walkie Talkie überprüft.

### <a name="license-requirements"></a>Lizenzanforderungen

Die Walkie Talkie-App ist in allen kostenpflichtigen Lizenzen von Teams in [Office 365-Abonnements enthalten.](/office365/servicedescriptions/teams-service-description) Weitere Informationen zum Abrufen von Teams finden Sie unter [Wie kann ich auf Microsoft Teams zugreifen?](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)

> [!NOTE]
> Bestimmte erweiterte Features erfordern möglicherweise zusätzliche Lizenzierung. Für die Integration in Samsung Galaxy XCover Pro ist beispielsweise eine Knox-Lizenz erforderlich.

## <a name="further-information"></a>Weitere Informationen

- ITAdmins können die Kontrolle darüber behalten, wer Walkie Talkie über App-Richtlinien verwendet.
- Wenn Ihr Frontline-Mitarbeiter mobile Daten verwendet, um über Teams zu kommunizieren, verwendet Walkie Talkie dieselbe Methode.
- Walkie Talkie sollte in Situationen mit geringer Bandbreite oder in Situationen, in denen Ihr Smartphone verbunden ist und funktioniert, gut funktionieren. Walkie Talkie funktioniert nicht, wenn keine Verbindung besteht.

Weitere Informationen zur Endbenutzererfahrung finden Sie unter:

- [Erste Schritte mit Teams Walkie Talkie](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [Kommunizieren mit Ihrem Team mit Walkie Talkie](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)