---
title: Walkie-Talkie-Anwendung in Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Konfigurieren der Walkie Talkie-App in Microsoft Teams ITAdmin.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 80aedfd0c1bb4f4a20ecdfcd977ce74d667cad43
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58602070"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a>Walkie-Talkie-App in Microsoft Teams

Die Walkie-Talkie-App in Teams bietet sofortige Push-to-Talk-Kommunikation für Ihr Team und ist jetzt für Android verfügbar. Walkie-Talkie ermöglicht es Benutzern, eine Verbindung mit ihrem Team über die gleichen Kanäle herzustellen, deren Mitglieder sie sind. Nur Benutzer, die eine Verbindung mit Walkie-Talkie in einem Kanal herstellen, werden zu Teilnehmern und können miteinander per Push-to-Talk kommunizieren – jeweils eins nach dem anderen.

Mit Walkie-Talkie in Teams können Frontline-Mitarbeiter jetzt mit einer vertrauten PTT-Erfahrung sicher kommunizieren, ohne sperrige Radiogeräte mit sich führen zu müssen, und Walkie-Talkie funktioniert überall mit WLAN oder mobiler Internetverbindung.

## <a name="getting-started"></a>Erste Schritte

### <a name="deploying-walkie-talkie"></a>Bereitstellen von Walkie-Talkie

Derzeit ist Walkie-Talkie für Android-Geräte mit Google Mobile Services (GMS) verfügbar und nicht vorinstalliert. Um dieses Feature für Benutzer in Ihrer Organisation zu aktivieren, [](teams-app-setup-policies.md)müssen Sie Walkie-Talkie der App-Setuprichtlinie, die Benutzern zugewiesen ist, aus dem Teams   Admin Center [hinzufügen.](https://admin.teams.microsoft.com/) Nach der Aktivierung wird Walkie-Talkie innerhalb von 48 Stunden in der Android-App verfügbar.

### <a name="adding-walkie-talkie-to-your-app-list"></a>Hinzufügen von Walkie-Talkie zu Ihrer App-Liste

Im Microsoft Teams Admin Center sollten Sie unter Teams Setuprichtlinien für Apps die Einstellung Benutzer-Anheften  >  zulassen auf Ein **festgelegt haben.**  Klicken Sie dann im Abschnitt Angeheftet Apps auf **+Apps hinzufügen.**

:::image type="content" source="media/deploy-walkie-talkie-1.png" alt-text="Zeigt den Abschnitt Angeheftet Apps und die Schaltfläche Apps hinzufügen an, die ausgewählt werden soll.":::

Verwenden Sie im Rechts **angezeigten** Bereich Angeheftet  Apps hinzufügen das Textfeld Suchen, um nach Walkie-Talkie zu suchen. Wenn sie als Suchergebnis angezeigt  wird, wählen Sie die Schaltfläche Hinzufügen rechts neben dem Namen aus, um sie Ihrer Liste hinzuzufügen.

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="Zeigt die Randleiste Angeheftet Apps hinzufügen mit Walkie, die in den Suchbereich eingegeben wurde, und die Walkie-Talkie-App in den Suchergebnissen mit der Schaltfläche Hinzufügen daneben.":::

Die Walkie-Talkie-App sollte nun in der Liste Angeheftet Apps angezeigt werden und steht zur Verfügung, sobald Sie auf die Schaltfläche **Speichern klicken.**

:::image type="content" source="media/deploy-walkie-talkie-3.png" alt-text="Zeigt die Liste Angeheftet Apps mit hinzugefügter Walkie-Talkie-App und der Schaltfläche Speichern unterhalb der Liste an.":::

### <a name="network-documentation"></a>Netzwerkdokumentation

Walkie-Talkie in Teams erfordert Eine Internetverbindung und unter den Netzwerkbedingungen ist eine optimale Erfahrung erforderlich.

|Metrik | Erforderlich |
|---|---|
|Latenz (RTT) | < 300 ms |
|Jitter |< 30 ms |
|Paketverlust |< 1 % |

Wie bereits erwähnt, wirkt sich die Qualität der Netzwerkkonnektivität stark auf die Qualität von Echtzeitmedien über ein IP-Netzwerk aus, insbesondere durch die Menge der:

- **Latenz –** Dies ist die Zeit, die benötigt wird, um ein IP-Paket von Punkt A zu Punkt B im Netzwerk zu erhalten. Diese Verzögerung bei der Netzwerkverteilung ist im Wesentlichen an den physischen Abstand zwischen den beiden Punkten und die Lichtgeschwindigkeit gebunden, einschließlich des mehr Aufwands, der von den verschiedenen zwischen den Punkten hin und weg genommenen Routern genommen wird. Latenz wird als Round-Trip-Zeit (Round-Trip Time, RTT) gemessen.
- **Jitter zwischen Ankunftszeit** – Dies ist die durchschnittliche Änderung der Verzögerung zwischen aufeinander folgenden Paketen.
- **Paketverlust** – Dies wird häufig als Prozentsatz der Pakete definiert, die in einem bestimmten Zeitfenster verloren gehen. Der Paketverlust wirkt sich direkt auf die Audioqualität aus – von kleinen, einzelnen verlorenen Paketen, die fast keine Auswirkungen haben, bis hin zu Aufbruchsverlusten, die zu einer vollständigen Audioaufnahme führen.

Die erwartete Datennutzung von Walkie-Talkie beträgt ca. 20 KB/s beim Senden oder Empfangen von Audio. Im Leerlauf ist die erwartete Datennutzung aus Walkie-Talkie unerheblich.

### <a name="walkie-talkie-devices"></a>Walkie-Talkie-Geräte

Mitarbeiter in der Frontlinie müssen häufig Walkie-Talkie-Anrufe sprechen und empfangen, auch wenn ihre Telefone gesperrt sind. Diese Erfahrung ist über spezialisierte Geräte mit einer dedizierten PTT-Schaltfläche möglich.

- **Headsets**
  - Drahtlose Headsets 
    - [BlueParrott](https://www.blueparrott.com/microsoft-teams-walkie-talkie)
  - Verkabelte Headsets 
    - [Klein Electronics](https://www.kleinelectronics.com/poc-accessories/mtwt/)
- **Zerklüftete Telefone**
  - Samsung [Galaxy XCover Pro](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/), Galaxy [XCover 5,](https://www.samsung.com/de/smartphones/others/galaxy-xcover-5-black-64gb-sm-g525fzkdeeb/buy) [Galaxy Tab Active 3](https://www.samsung.com/us/business/tablets/galaxy-tab-active/buy/)
    -  Manuelles Setup – Navigieren Teams Installiertem Ordner zu Einstellungen > erweiterte Features > XCover/Active Key. Aktivieren Sie "Control XCover key with app", und wählen Sie "Teams" aus.
    -  [MDM-Setup](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm)

> [!NOTE]
> Diese Geräte sind nicht Teams zertifiziert. Sie wurden für die Zusammenarbeit mit Teams Walkie-Talkie überprüft.

### <a name="license-requirements"></a>Lizenzanforderungen

Die Walkie-Talkie-App ist in allen kostenpflichtigen Lizenzen Teams in Office 365 [enthalten.](/office365/servicedescriptions/teams-service-description) Weitere Informationen zum Abrufen von Teams finden Sie unter [Wie kann ich auf meine Microsoft Teams?](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)

> [!NOTE]
> Bestimmte erweiterte Features erfordern möglicherweise eine zusätzliche Lizenzierung. Für die Integration in Samsung Galaxy XCover Pro z. B. eine Knox-Lizenz erforderlich.

## <a name="further-information"></a>Weitere Informationen

- ITAdmins können die Kontrolle darüber behalten, wer Walkie-Talkie über App-Richtlinien verwendet.
- Wenn Ihr Frontline-Worker mobile Daten für die Kommunikation über Teams verwendet, verwendet Walkie-Talkie die gleiche Methode.
- Walkie-Talkie sollte in Situationen mit geringer Bandbreite oder in Situationen, in denen Ihr Smartphone verbunden ist und funktioniert, gut funktionieren. Walkie-Talkie funktioniert nicht, wenn überhaupt keine Verbindung besteht.

Weitere Informationen zur Endbenutzererfahrung finden Sie unter:

- [Erste Schritte mit Teams Walkie-Talkie](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [Kommunizieren mit Ihrem Team mit Walkie-Talkie](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
