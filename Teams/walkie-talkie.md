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
ms.openlocfilehash: 776f0f31d54788fbffd86bbcbedd44e30ada28a3
ms.sourcegitcommit: ad8447b683381bc07f993bf843a93a4bdb77d840
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2022
ms.locfileid: "65186971"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a>Walkie Talkie-App in Microsoft Teams

Die Walkie Talkie-App in Teams bietet sofortige Push-to-Talk (PTT)-Kommunikation für Ihr Team und ist jetzt unter Android & iOS verfügbar. Walkie Talkie ermöglicht Benutzern die Verbindung mit ihrem Team über die gleichen zugrunde liegenden Kanäle, in denen sie Mitglieder sind. Nur Benutzer, die sich in einem Kanal mit Walkie Talkie verbinden, werden Zu Teilnehmern und können mithilfe von Push-to-Talk nacheinander miteinander kommunizieren.

Mit Walkie Talkie in Teams können Mitarbeiter in Service und Produktion jetzt sicher mit einer vertrauten PTT-Erfahrung kommunizieren, ohne sperrige Radios mit sich führen zu müssen, und Walkie Talkie arbeitet überall mit WLAN oder Mobilfunk-Internetverbindung.

## <a name="getting-started"></a>Erste Schritte

### <a name="deploying-walkie-talkie"></a>Bereitstellen von Walkie-Talkie

Walkie Talkie wird auf Android-Geräten mit Google Mobile Services (GMS) und iOS-Geräten unterstützt.

### <a name="pin-walkie-talkie-to-teams"></a>Anheften von Walkie-Talkie an Teams

#### <a name="use-the-tailored-frontline-app-experience-to-pin-walkie-talkie-and-other-apps-to-teams"></a>Verwenden Sie die maßgeschneiderte Frontline-App-Erfahrung, um Walkie Talkie und andere Apps an Teams

Die maßgeschneiderte Frontline-App-Erfahrung in Teams heftet die relevantesten Apps in Teams für Benutzer an, die über eine [F-Lizenz verfügen](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt). Angeheftete Apps umfassen Walkie-Talkie, Schichten, Aufgaben und Genehmigungen. Standardmäßig ist dieses Feature aktiviert, sodass Ihre Mitarbeiter in Service und Produktion eine out-of-the-box-Erfahrung erhalten, die auf ihre Anforderungen zugeschnitten ist.

Die Apps werden an die App-Leiste angeheftet – die Leiste auf der Seite des Teams Desktopclients und am unteren Rand der Teams mobilen Clients, auf die Benutzer schnell und einfach zugreifen können.

Weitere Informationen, einschließlich der Funktionsweise der Umgebung mit von Ihnen festgelegten App-Richtlinien, finden Sie unter ["Anpassen Teams Apps für Mitarbeiter in Service und Produktion](pin-teams-apps-based-on-license.md)".

#### <a name="use-an-app-setup-policy-to-pin-walkie-talkie-to-teams"></a>Verwenden einer App-Setuprichtlinie zum Anheften von Walkie Talkie an Teams

Mit App-Setuprichtlinien können Sie Teams anpassen, um Apps anzuheften, die für Ihre Benutzer in Ihren Benutzern am wichtigsten sind.

Um die Walkie Talkie-App für Ihre Benutzer anzuheften, können Sie die globale Richtlinie (organisationsweite Standardrichtlinie) bearbeiten oder eine benutzerdefinierte App-Setuprichtlinie erstellen und zuweisen. Weitere Informationen finden Sie unter [Verwalten von App-Einrichtungsrichtlinien in Microsoft Teams](teams-app-setup-policies.md).

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="Screenshot, der zeigt, wie Walkie-Talkie zur Liste angehefteter Apps im Bereich &quot;Angeheftete Apps hinzufügen&quot; hinzugefügt wird." lightbox="media/deploy-walkie-talkie-2.png":::

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
