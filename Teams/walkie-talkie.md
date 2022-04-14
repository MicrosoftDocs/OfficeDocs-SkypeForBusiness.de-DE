---
title: Walkie Talkie-Anwendung in Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Konfigurieren der Walkie Talkie-App in Microsoft Teams aus sicht des ITAdmin.
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
ms.sourcegitcommit: 480046a53dfb6e6cf867e1920f8fb43dda9d3774
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2022
ms.locfileid: "62015015"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a>Walkie Talkie-App in Microsoft Teams

Die Walkie Talkie-App in Teams bietet sofortige Push-to-Talk (PTT)-Kommunikation für Ihr Team und ist jetzt unter Android & iOS verfügbar. Walkie Talkie ermöglicht Benutzern die Verbindung mit ihrem Team über die gleichen zugrunde liegenden Kanäle, in denen sie Mitglieder sind. Nur Benutzer, die sich in einem Kanal mit Walkie Talkie verbinden, werden Zu Teilnehmern und können mithilfe von Push-to-Talk nacheinander miteinander kommunizieren.

Mit Walkie Talkie in Teams können Mitarbeiter in Service und Produktion jetzt sicher mit einer vertrauten PTT-Erfahrung kommunizieren, ohne sperrige Radios mit sich führen zu müssen, und Walkie Talkie arbeitet überall mit WLAN oder Mobilfunk-Internetverbindung.

## <a name="getting-started"></a>Erste Schritte

### <a name="deploying-walkie-talkie"></a>Bereitstellen von Walkie-Talkie

Walkie Talkie wird auf Android-Geräten mit Google Mobile Services (GMS) und iOS-Geräten unterstützt. 

Walkie Talkie ist derzeit nicht vorinstalliert. Um dieses Feature für Benutzer in Ihrer Organisation zu aktivieren, müssen Sie Walkie Talkie zur  [App-Setuprichtlinie](teams-app-setup-policies.md)  hinzufügen, die Benutzern aus dem [Teams Admin Center](https://admin.teams.microsoft.com/) zugewiesen ist. Nach der Aktivierung wird Walkie Talkie innerhalb von 48 Stunden in der App verfügbar sein.

### <a name="adding-walkie-talkie-to-your-app-list"></a>Hinzufügen von Walkie-Talkie zur App-Liste

Im Microsoft Teams Admin Center sollten Sie unter **Teams** **appSetup-Richtlinien** >  "**Benutzer-Anheften zulassen**" auf "**Ein**" festlegen. Klicken Sie dann unter dem Abschnitt "Angeheftete Apps" auf **"+Apps hinzufügen"**.

:::image type="content" source="media/deploy-walkie-talkie-1.png" alt-text="Zeigt den Abschnitt &quot;Angeheftete Apps&quot; und die Schaltfläche &quot;Apps hinzufügen&quot;, die ausgewählt werden soll.":::

Verwenden Sie im Bereich **"Angeheftete Apps hinzufügen** ", der auf der rechten Seite angezeigt wird, das Textfeld **"Suchen** ", um nach Walkie Talkie zu suchen. Wenn sie als Suchergebnis angezeigt wird, wählen Sie rechts neben dem Namen die Schaltfläche " **Hinzufügen** " aus, um sie ihrer Liste hinzuzufügen.

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="Zeigt die Randleiste &quot;Angeheftete Apps hinzufügen&quot;, in der Walkie in den Suchbereich eingegeben wurde, und die Walkie Talkie-App in den Suchergebnissen mit der Schaltfläche &quot;Hinzufügen&quot; daneben.":::

Die Walkie Talkie-App sollte jetzt in der Liste der angehefteten Apps angezeigt werden und nach dem Klicken auf die Schaltfläche " **Speichern** " zur Verfügung stehen.

:::image type="content" source="media/deploy-walkie-talkie-3.png" alt-text="Zeigt die Liste der angehefteten Apps mit hinzugefügter Walkie Talkie-App und der Schaltfläche &quot;Speichern&quot; unter der Liste an.":::

### <a name="network-documentation"></a>Netzwerkdokumentation

Walkie Talkie in Teams erfordert Eine Internetverbindung und unter den Netzwerkbedingungen sind für eine optimale Erfahrung erforderlich.

|Metrik | Erforderlich |
|---|---|
|Latenz (RTT) | < 300ms |
|Jitter |< 30ms |
|Paketverlust |< 1 % |

Wie oben erwähnt, wird die Qualität von Echtzeitmedien über ein IP-Netzwerk stark durch die Qualität der Netzwerkkonnektivität beeinflusst, aber insbesondere durch die Menge an:

- **Latenz** : Dies ist die Zeit, die zum Abrufen eines IP-Pakets von Punkt A bis Punkt B im Netzwerk benötigt wird. Diese Netzwerkverteilungsverzögerung ist im Wesentlichen an den physischen Abstand zwischen den beiden Punkten und die Lichtgeschwindigkeit gebunden, einschließlich mehr Overhead, der von den verschiedenen Routern dazwischen eingenommen wird. Die Latenz wird als Roundtripzeit (Roundtrip Time, RTT) gemessen.
- **Inter-Arrival Jitter** - Dies ist die durchschnittliche Änderung der Verzögerung zwischen aufeinander folgenden Paketen.
- **Paketverlust** – Dies wird häufig als Prozentsatz der Pakete definiert, die in einem bestimmten Zeitfenster verloren gehen. Paketverlust wirkt sich direkt auf die Audioqualität aus – von kleinen, einzelnen verlorenen Paketen, die fast keine Auswirkungen haben, bis hin zu Back-to-Back-Burst-Verlusten, die zu einem vollständigen Audioausschneiden führen.

Die erwartete Datennutzung von Walkie Talkie beträgt etwa 20 KB/s beim Senden oder Empfangen von Audio. Im Leerlauf ist die erwartete Datennutzung von Walkie Talkie vernachlässigbar.

### <a name="walkie-talkie-devices"></a>Walkie Talkie-Geräte

Mitarbeiter in Service und Produktion müssen häufig sprechen und Walkie-Talkie-Anrufe erhalten, auch wenn ihre Telefone gesperrt sind. Diese Erfahrung ist über spezielle Geräte mit einer dedizierten PTT-Taste möglich.

- **Headsets**
  - Drahtlose Headsets (iOS & Android)
    - [BlueParrott](https://www.blueparrott.com/microsoft-teams-walkie-talkie)
  - Kabelgebundene Headsets (nur Android)
    - [Klein Electronics](https://www.kleinelectronics.com/poc-accessories/mtwt/)
- **Robuste Android-Smartphones**
  - Samsung [Galaxy XCover Pro](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/), [Galaxy XCover 5](https://www.samsung.com/de/smartphones/others/galaxy-xcover-5-black-64gb-sm-g525fzkdeeb/buy), [Galaxy Tab Active 3](https://www.samsung.com/us/business/tablets/galaxy-tab-active/buy/)
    - Manuelles Setup – Navigieren Sie bei installiertem Teams zu Einstellungen > Erweiterten Features > XCover/Active-Taste. Aktivieren Sie "XCover-Taste mit App steuern", und wählen Sie "Teams" aus.
    - [MDM-Setup](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm)
  - Zebra [TC5x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc52-tc57-series-touch-computer.html), [TC7x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc72-tc77-series-touch-computer.html), [TC2x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc21-tc26.html), [EC5x](https://www.zebra.com/us/en/products/mobile-computers/handheld/ec50-ec55.html), [EC30](https://www.zebra.com/us/en/products/mobile-computers/handheld/ec30.html), [MC3300](https://www.zebra.com/us/en/products/mobile-computers/handheld/mc3300.html), [MC9300](https://www.zebra.com/us/en/products/mobile-computers/handheld/mc9300.html) 
    - Manuelle Einrichtung – Bei installiertem Teams funktioniert die dedizierte PTT-Schaltfläche (LEFT_TRIGGER_2) standardmäßig mit Walkie Talkie
    
> [!NOTE]
> Diese Geräte sind nicht Teams zertifiziert. Sie wurden für die Zusammenarbeit mit Teams Walkie Talkie überprüft.

### <a name="license-requirements"></a>Lizenzanforderungen

Die Walkie Talkie-App ist in allen kostenpflichtigen Lizenzen von Teams in [Office 365-Abonnements](/office365/servicedescriptions/teams-service-description) enthalten. Weitere Informationen zum Abrufen von Teams finden Sie Gewusst wie  [Zugriff auf Microsoft Teams erhalten](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)?

## <a name="further-information"></a>Weitere Informationen

- ITAdmins können die Kontrolle darüber behalten, wer Walkie Talkie über App-Richtlinien verwendet.
- Wenn Ihre Mitarbeiter in Service und Produktion mobile Daten für die Kommunikation über Teams verwenden, verwendet Walkie Talkie dieselbe Methode.
- Walkie Talkie sollte in Situationen mit geringer Bandbreite oder in Situationen, in denen Ihr Smartphone verbunden ist und funktioniert, gut funktionieren. Walkie Talkie funktioniert nicht, wenn überhaupt keine Verbindung besteht.

Weitere Informationen zur Endbenutzererfahrung finden Sie unter:

- [Erste Schritte mit Teams Walkie Talkie](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [Kommunizieren mit Ihrem Team mit Walkie Talkie](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
