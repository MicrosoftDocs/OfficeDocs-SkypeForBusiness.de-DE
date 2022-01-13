---
title: Walkie-Talkie-Anwendung in Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Konfigurieren der Walkie Talkie-App in Microsoft Teams ITAdmin aus Sicht des ITAdmins.
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
ms.openlocfilehash: c19894106dfd06c13ec9936657837aa42fcdade0
ms.sourcegitcommit: d2c76fe7705acf6e53f7673861671b1b018813dd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/13/2022
ms.locfileid: "62015015"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a>Walkie-Talkie-App in Microsoft Teams

Die Walkie-Talkie-App in Teams bietet sofortige Push-to-Talk-Kommunikation für Ihr Team und ist jetzt für Android und iOS & verfügbar. Walkie-Talkie ermöglicht es Benutzern, eine Verbindung mit ihrem Team über die gleichen Kanäle herzustellen, deren Mitglieder sie sind. Nur Benutzer, die in einem Kanal eine Verbindung mit Walkie-Talkie herstellen, werden zu Teilnehmern und können miteinander per Push-to-Talk kommunizieren– jeweils eins nach dem anderen.

Mit Walkie-Talkie in Teams können Frontline-Mitarbeiter jetzt sicher mit einer vertrauten PTT-Erfahrung kommunizieren, ohne sperrige Radiogeräte mit sich führen zu müssen, und Walkie-Talkie funktioniert überall mit WLAN oder mobiler Internetverbindung.

## <a name="getting-started"></a>Erste Schritte

### <a name="deploying-walkie-talkie"></a>Bereitstellen von Walkie-Talkie

Walkie Talkie wird auf Android-Geräten mit Google Mobile Services (GMS) und iOS-Geräten unterstützt. 

Walkie-Talkie ist derzeit nicht vorinstalliert. Um dieses Feature für Benutzer in Ihrer Organisation zu aktivieren, [](teams-app-setup-policies.md)müssen Sie Walkie-Talkie der App-Setuprichtlinie hinzufügen, die Benutzern im Teams   Admin Center zugewiesen [wurde.](https://admin.teams.microsoft.com/) Nach der Aktivierung wird Walkie-Talkie innerhalb von 48 Stunden in der App verfügbar.

### <a name="adding-walkie-talkie-to-your-app-list"></a>Hinzufügen von Walkie-Talkie zu Ihrer App-Liste

Im Microsoft Teams Admin Center sollten Sie unter Teams Richtlinien für die App-Einrichtung die Einstellung Benutzerheften  >  zulassen auf Ein **festgelegt haben.**  Klicken Sie dann im Abschnitt Angeheftet Apps auf **+Apps hinzufügen.**

:::image type="content" source="media/deploy-walkie-talkie-1.png" alt-text="Zeigt den Abschnitt "Angeheftet Apps" und die Schaltfläche "Apps hinzufügen" an, die ausgewählt werden soll.":::

Verwenden Sie im Rechts **angezeigten** Bereich Angeheftet  Apps hinzufügen das Textfeld Suchen, um nach Walkie-Talkie zu suchen. Wenn sie als Suchergebnis angezeigt  wird, wählen Sie die Schaltfläche Hinzufügen rechts neben dem Namen aus, um sie Ihrer Liste hinzuzufügen.

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="Zeigt die Randleiste "Angeheftet Apps hinzufügen" mit Walkie, die in den Suchbereich eingegeben wurde, und die Walkie-Talkie-App in den Suchergebnissen mit der Schaltfläche "Hinzufügen" daneben.":::

Die Walkie-Talkie-App sollte nun in der Liste Angeheftet Apps angezeigt werden und steht zur Verfügung, sobald Sie auf die Schaltfläche **Speichern klicken.**

:::image type="content" source="media/deploy-walkie-talkie-3.png" alt-text="Zeigt die Liste "Angeheftet Apps" mit hinzugefügter Walkie-Talkie-App und der Schaltfläche "Speichern" unterhalb der Liste an.":::

### <a name="network-documentation"></a>Netzwerkdokumentation

Walkie-Talkie in Teams erfordert Eine Internetverbindung und unter den Netzwerkbedingungen ist eine optimale Erfahrung erforderlich.

|Metrik | Erforderlich |
|---|---|
|Latenz (RTT) | < 300 ms |
|Jitter |< 30 ms |
|Paketverlust |< 1 % |

Wie bereits erwähnt, hat die Qualität der Netzwerkkonnektivität großen Einfluss auf die Qualität von Echtzeitmedien über ein IP-Netzwerk, insbesondere durch die Menge der:

- **Latenz –** Dies ist die Zeit, die benötigt wird, um ein IP-Paket von Punkt A zu Punkt B im Netzwerk zu erhalten. Diese Verzögerung bei der Netzwerkverteilung ist im Wesentlichen an den physischen Abstand zwischen den beiden Punkten und die Lichtgeschwindigkeit gebunden, einschließlich des mehr Aufwands, der von den verschiedenen zwischen den Punkten hin und weg genommenen Routern genommen wird. Latenz wird als Round-Trip-Zeit (Round-Trip Time, RTT) gemessen.
- **Jitter zwischen Ankunftszeit** – Dies ist die durchschnittliche Änderung der Verzögerung zwischen aufeinander folgenden Paketen.
- **Paketverlust** – Dies wird häufig als Prozentsatz der Pakete definiert, die in einem bestimmten Zeitfenster verloren gehen. Der Paketverlust wirkt sich direkt auf die Audioqualität aus – von kleinen, einzelnen verlorenen Paketen, die fast keine Auswirkungen haben, bis hin zu Aufbruchsverlusten, die zu einer vollständigen Audioaufnahme führen.

Die erwartete Datennutzung von Walkie-Talkie beträgt ca. 20 KB/s beim Senden oder Empfangen von Audio. Im Leerlauf ist die erwartete Datennutzung aus Walkie-Talkie unerheblich.

### <a name="walkie-talkie-devices"></a>Walkie-Talkie-Geräte

Mitarbeiter in der Frontlinie müssen häufig Walkie-Talkie-Anrufe sprechen und empfangen, auch wenn ihre Telefone gesperrt sind. Diese Erfahrung ist über spezialisierte Geräte mit einer dedizierten PTT-Schaltfläche möglich.

- **Headsets**
  - Drahtlose Headsets (iOS & Android)
    - [BlueParrott](https://www.blueparrott.com/microsoft-teams-walkie-talkie)
  - Verkabelte Headsets (nur Android)
    - [Klein Electronics](https://www.kleinelectronics.com/poc-accessories/mtwt/)
- **Zerklüftete Android-Smartphones**
  - Samsung [Galaxy XCover Pro](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/), Galaxy [XCover 5,](https://www.samsung.com/de/smartphones/others/galaxy-xcover-5-black-64gb-sm-g525fzkdeeb/buy) [Galaxy Tab Active 3](https://www.samsung.com/us/business/tablets/galaxy-tab-active/buy/)
    - Manuelles Setup – Navigieren Teams installation von Zu Einstellungen > erweiterten Features > XCover/Active Key navigieren. Aktivieren Sie "XCover-Taste mit App steuern", und wählen Sie "Teams" aus.
    - [MDM-Setup](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm)
  - [Tc5x,](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc52-tc57-series-touch-computer.html) [TC7x,](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc72-tc77-series-touch-computer.html) [TC2x,](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc21-tc26.html) [EC5x,](https://www.zebra.com/us/en/products/mobile-computers/handheld/ec50-ec55.html) [EC30,](https://www.zebra.com/us/en/products/mobile-computers/handheld/ec30.html) [MC3300,](https://www.zebra.com/us/en/products/mobile-computers/handheld/mc3300.html) [MC9300](https://www.zebra.com/us/en/products/mobile-computers/handheld/mc9300.html) 
    - Manuelle Einrichtung – Teams installiert ist, funktioniert die dedizierte PTT-Schaltfläche (LEFT_TRIGGER_2) standardmäßig mit Walkie-Talkie.
    
> [!NOTE]
> Diese Geräte sind nicht Teams zertifiziert. Sie wurden für die Zusammenarbeit mit Teams Walkie-Talkie überprüft.

### <a name="license-requirements"></a>Lizenzanforderungen

Die Walkie-Talkie-App ist in allen kostenpflichtigen Lizenzen Teams in Office 365 [enthalten.](/office365/servicedescriptions/teams-service-description) Weitere Informationen zum Abrufen von Teams finden Sie unter [Wie kann ich auf meine Microsoft Teams?](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)

## <a name="further-information"></a>Weitere Informationen

- ITAdmins können die Kontrolle darüber behalten, wer Walkie-Talkie über App-Richtlinien verwendet.
- Wenn Ihr Frontline-Worker mobile Daten für die Kommunikation über Teams verwendet, verwendet Walkie-Talkie die gleiche Methode.
- Walkie-Talkie sollte in Situationen mit geringer Bandbreite oder in Situationen, in denen Ihr Smartphone verbunden ist und funktioniert, gut funktionieren. Walkie-Talkie funktioniert nicht, wenn überhaupt keine Verbindung besteht.

Weitere Informationen zur Endbenutzererfahrung finden Sie unter:

- [Erste Schritte mit Teams Walkie-Talkie](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [Kommunizieren mit Ihrem Team mit Walkie-Talkie](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
