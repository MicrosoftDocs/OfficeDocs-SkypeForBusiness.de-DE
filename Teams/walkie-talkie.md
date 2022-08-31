---
title: Walkie Talkie-App in Microsoft Teams
author: LanaChin
ms.author: v-lanachin
manager: samanro
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
- m365-frontline
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: e309fa03e73dc13bff8bd1a90708c688bb0f5350
ms.sourcegitcommit: 7a1fb6e15c21368afa34cd212865437781f721e2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/31/2022
ms.locfileid: "67465993"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a>Walkie Talkie-App in Microsoft Teams

Die Walkie Talkie-App in Teams bietet sofortige Push-to-Talk (PTT)-Kommunikation für Ihr Team und ist unter Android und iOS verfügbar. Walkie Talkie ermöglicht Benutzern die Verbindung mit ihrem Team über die gleichen zugrunde liegenden Kanäle, in denen sie Mitglieder sind. Nur Benutzer, die eine Verbindung mit Walkie Talkie in einem Kanal herstellen, werden zu Teilnehmern und können mithilfe von Push-to-Talk nacheinander miteinander kommunizieren.

Mit Walkie Talkie in Teams können Mitarbeiter in Service und Produktion sicher mit einer vertrauten PTT-Erfahrung kommunizieren, ohne sperrige Radios mit sich führen zu müssen, und Walkie Talkie funktioniert überall mit WLAN oder Mobilfunk-Internetverbindung.

> [!NOTE]
> Walkie Talkie ist derzeit in China nicht verfügbar.

## <a name="deploying-walkie-talkie"></a>Bereitstellen von Walkie-Talkie

Walkie Talkie wird auf Android-Geräten mit Google Mobile Services (GMS) und iOS-Geräten unterstützt.

### <a name="enable-or-disable-walkie-talkie-in-your-organization"></a>Aktivieren oder Deaktivieren von Walkie-Talkie in Ihrer Organisation

Walkie Talkie ist standardmäßig für alle Teams-Benutzer in Ihrer Organisation aktiviert. Sie können die App auf Organisationsebene im Microsoft Teams Admin Center auf der Seite [Apps verwalten](manage-apps.md) deaktivieren oder aktivieren.

1. Wechseln Sie in der linken Navigation des Teams Admin Center zu **Teams-Apps** > **Apps verwalten**.
2. Suchen Sie in der Liste der Apps nach der Walkie Talkie-App, wählen Sie sie aus, und schalten Sie dann die Status-Umschaltfläche auf **"Blockiert**" oder "**Zulässig**".

### <a name="enable-or-disable-walkie-talkie-for-specific-users-in-your-organization"></a>Aktivieren oder Deaktivieren von Walkie-Talkie für bestimmte Benutzer in Ihrer Organisation

Um die Verwendung von Walkie-Talkie für bestimmte Benutzer in Ihrer Organisation zuzulassen oder zu blockieren, stellen Sie sicher, dass Walkie Talkie für Ihre Organisation auf der Seite ["Apps verwalten"](manage-apps.md) aktiviert ist. Erstellen Sie dann eine benutzerdefinierte App-Berechtigungsrichtlinie, fügen Sie sie einer App-Setuprichtlinie hinzu, und weisen Sie sie diesen Benutzern zu. Weitere Informationen finden Sie unter [Verwalten von App-Berechtigungsrichtlinien in Teams](teams-app-permission-policies.md) und [Verwalten von App-Setuprichtlinien in Microsoft Teams](teams-app-setup-policies.md).

### <a name="pin-walkie-talkie-to-teams"></a>Anheften von Walkie-Talkie an Teams

#### <a name="use-the-tailored-frontline-app-experience-to-pin-walkie-talkie-and-other-apps-to-teams"></a>Verwenden der benutzerdefinierten Frontline-App-Erfahrung zum Anheften von Walkie Talkie und anderen Apps an Teams

Die maßgeschneiderte Frontline-App-Erfahrung in Teams heftet die relevantesten Apps in Teams für Benutzer an, die über eine [F-Lizenz](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt) verfügen. Angeheftete Apps umfassen Walkie Talkie, Schichten, Aufgaben und Genehmigungen. Standardmäßig ist dieses Feature aktiviert, sodass Ihre Mitarbeiter in Service und Produktion eine out-of-the-box-Erfahrung erhalten, die auf ihre Anforderungen zugeschnitten ist.

Die Apps sind an die App-Leiste angeheftet – die Leiste auf der Seite des Teams-Desktopclients und am unteren Rand der mobilen Teams-Clients, auf die Benutzer schnell und einfach zugreifen können.

Weitere Informationen, einschließlich der Funktionsweise der Umgebung mit von Ihnen festgelegten App-Richtlinien, finden Sie unter ["Anpassen von Teams-Apps für Mitarbeiter in Service und Produktion](/microsoft-365/frontline/pin-teams-apps-based-on-license?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json)".

#### <a name="use-an-app-setup-policy-to-pin-walkie-talkie-to-teams"></a>Verwenden einer App-Setuprichtlinie zum Anheften von Walkie Talkie an Teams

Mit App-Setuprichtlinien können Sie Teams so anpassen, dass Apps angeheftet werden, die für Ihre Benutzer in Ihren Benutzern am wichtigsten sind.

Um die Walkie Talkie-App für Ihre Benutzer anzuheften, können Sie die globale Richtlinie (organisationsweite Standardrichtlinie) bearbeiten oder eine benutzerdefinierte App-Setuprichtlinie erstellen und zuweisen. Weitere Informationen finden Sie unter [Verwalten von App-Einrichtungsrichtlinien in Microsoft Teams](teams-app-setup-policies.md).

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="Screenshot, der zeigt, wie Walkie-Talkie zur Liste angehefteter Apps im Bereich &quot;Angeheftete Apps hinzufügen&quot; hinzugefügt wird." lightbox="media/deploy-walkie-talkie-2.png":::

## <a name="network-documentation"></a>Netzwerkdokumentation

Walkie Talkie in Teams erfordert Eine Internetverbindung. Die folgenden Netzwerkbedingungen sind für eine optimale Erfahrung erforderlich.

|Metrik | Erforderlich |
|---|---|
|Latenz (RTT) | < 300 ms |
|Jitter |< 30 ms |
|Paketverlust |< 1 % |

Wie oben erwähnt, wird die Qualität von Echtzeitmedien über ein IP-Netzwerk stark durch die Qualität der Netzwerkkonnektivität beeinflusst, aber insbesondere durch die Menge an:

- **Latenz :** Die Zeit, die zum Abrufen eines IP-Pakets von Punkt A bis Punkt B im Netzwerk benötigt wird. Diese Netzwerkverteilungsverzögerung ist im Wesentlichen an den physischen Abstand zwischen den beiden Punkten und die Lichtgeschwindigkeit gebunden, einschließlich mehr Overhead, der von den verschiedenen Routern dazwischen eingenommen wird. Die Latenz wird als Roundtripzeit (Roundtrip Time, RTT) gemessen.
- **Jitter zwischen der Ankunft** : Die durchschnittliche Änderung der Verzögerung zwischen aufeinander folgenden Paketen.
- **Paketverlust** : Paketverlust wird häufig als Prozentsatz der Pakete definiert, die in einem bestimmten Zeitfenster verloren gehen. Paketverlust wirkt sich direkt auf die Audioqualität aus – von kleinen, einzelnen verlorenen Paketen, die fast keine Auswirkungen haben, bis hin zu Back-to-Back-Burst-Verlusten, die zu einem vollständigen Audioausschneiden führen.

Die erwartete Datennutzung von Walkie Talkie beträgt etwa 20 KB/s beim Senden oder Empfangen von Audio. Im Leerlauf ist die erwartete Datennutzung von Walkie Talkie vernachlässigbar.

## <a name="walkie-talkie-devices"></a>Walkie Talkie-Geräte

Mitarbeiter in Service und Produktion müssen häufig sprechen und Walkie-Talkie-Anrufe erhalten, auch wenn ihre Telefone gesperrt sind. Diese Erfahrung ist über spezielle Geräte mit einer dedizierten PTT-Taste möglich.

#### <a name="headsets"></a>Headsets

- Drahtlose Headsets (iOS und Android)
  - [BlueParrott](https://www.blueparrott.com/microsoft-teams-walkie-talkie)
- Kabelgebundene Headsets (nur Android)
  - [Klein Electronics](https://www.kleinelectronics.com/poc-accessories/mtwt/)

#### <a name="rugged-android-phones"></a>Robuste Android-Smartphones

- Crosscall [Core-X4](https://www.crosscall.com/en_FR/core-s4-1004010501053.html), [Core-M5](https://www.crosscall.com/en_FR/core-m5-1001011101114.html), [Action-X5](https://www.crosscall.com/en_FR/action-x5-1001020701220.html), [Core-X5](https://www.crosscall.com/en_FR/core-x5-1001010701695.html) und [Core-T5](https://www.crosscall.com/en_FR/core-t5-1003011401749.html)
  - Manuelle Einrichtung: Wenn Teams installiert ist, wechseln Sie zu **"Einstellungsschaltflächen** > **"**. Wählen Sie auf der Schaltfläche "Dediziert" (1 oder 2) die Option **"Lang"** und dann " **PTT-App**" aus. Wählen Sie das blaue Rad neben **"Benutzerdefiniert"** und dann **"Teams**" aus.
- Kyocera [DuraForce Ultra 5G](https://kyoceramobile.com/duraforce-ultra-5g/) und [DuraSport 5G](https://kyoceramobile.com/durasport-5g/)
  - Manuelle Einrichtung: Wenn Teams installiert ist, wechseln **Sie zu "Programmierbare Einstellungen** > **"-Schlüssel**. Wählen Sie **die PTT-Taste** oder **drücken und halten** (je nach Gerät), und wählen Sie **Teams** aus.
- Samsung [Galaxy XCover Pro](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/), [Galaxy XCover 5](https://www.samsung.com/de/smartphones/others/galaxy-xcover-5-black-64gb-sm-g525fzkdeeb/buy), [Galaxy Tab Active 3](https://www.samsung.com/us/business/tablets/galaxy-tab-active/buy/)
  - Manuelle Einrichtung: Wenn Teams installiert ist, wechseln Sie zu **XCover/Active-Schlüssel** für **erweiterte Features** >  für **Einstellungen** > . Aktivieren Sie **die XCover-Taste "Steuern" mit der App** , und wählen Sie **"Teams**" aus.
  - [MDM-Setup](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm)
- Sonim [XP8](https://www.sonimtech.com/products/devices/xp8/)
  - Manuelle Einrichtung: Wenn Teams installiert ist, wechseln **Sie zu "Programmierbare Schlüssel für Einstellungen"** > . Wählen **Sie "PTT Key-App auswählen"** und dann **"Teams**" aus.
- Zebra [TC5x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc52-tc57-series-touch-computer.html), [TC7x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc72-tc77-series-touch-computer.html), [TC2x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc21-tc26.html), [EC5x](https://www.zebra.com/us/en/products/mobile-computers/handheld/ec50-ec55.html), [EC30](https://www.zebra.com/us/en/products/mobile-computers/handheld/ec30.html), [MC3300](https://www.zebra.com/us/en/products/mobile-computers/handheld/mc3300.html), [MC9300](https://www.zebra.com/us/en/products/mobile-computers/handheld/mc9300.html) 
  - Manuelle Einrichtung: Wenn Teams installiert ist, funktioniert die dedizierte PTT-Schaltfläche (LEFT_TRIGGER_2) standardmäßig mit Walkie Talkie.

> [!NOTE]
> Diese Geräte sind nicht teams-zertifiziert. Sie wurden für die Zusammenarbeit mit Teams Walkie Talkie überprüft.

## <a name="license-requirements"></a>Lizenzanforderungen

Die Walkie Talkie-App ist in allen kostenpflichtigen Lizenzen von Teams in [Office 365 Abonnements](/office365/servicedescriptions/teams-service-description) enthalten. Weitere Informationen zum Abrufen von Teams finden Sie [Gewusst wie Zugriff auf Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)?

## <a name="more-information"></a>Weitere Informationen

- Wenn Ihr Mitarbeiter in Service und Produktion mobile Daten für die Kommunikation über Teams verwendet, verwendet Walkie Talkie dieselbe Methode.
- Walkie Talkie sollte in Situationen mit geringer Bandbreite oder in Situationen, in denen Ihr Smartphone verbunden ist und funktioniert, gut funktionieren. Walkie Talkie funktioniert nicht, wenn überhaupt keine Verbindung besteht.

Weitere Informationen zur Endbenutzererfahrung finden Sie unter:

- [Erste Schritte mit Teams Walkie Talkie](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [Kommunizieren mit Ihrem Team mit Walkie Talkie](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
