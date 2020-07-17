---
title: Walkie Talkie-Anwendung in Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: So konfigurieren Sie die Walkie Talkie-app in Microsoft Teams aus einer ITAdmin Perspektive.
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
ms.openlocfilehash: 9369cf56a32142d6527fcb86271d8d0fa56718ec
ms.sourcegitcommit: 2467ece95e100a3a3cc2be3538d8eb7d878b3663
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2020
ms.locfileid: "45043010"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a>Walkie Talkie-app in Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Die Walkie-Talkie-app in Microsoft Teams bietet eine direkte Push-to-Talk (PTT)-Kommunikation für Ihr Team und wird in Kürze in der öffentlichen Vorschau auf Android zur Verfügung stehen. Walkie Talkie ermöglicht Benutzern die Verbindung mit Ihrem Team unter Verwendung der gleichen zugrunde liegenden Kanäle, in denen Sie Mitglied sind. Nur Benutzer, die eine Verbindung mit Walkie Talkie in einem Kanal herstellen, werden Teilnehmer und können jeweils einzeln über Push-to-Talk miteinander kommunizieren.

Mit Walkie Talkie in Teams können First-Workers nun sicher mit einer vertrauten PTT-Erfahrung kommunizieren, ohne sperrige Radios tragen zu müssen, und Walkie Talkie funktioniert überall mit WiFi-oder Mobilfunk-Internetverbindung.

## <a name="getting-started"></a>Erste Schritte

### <a name="deploying-walkie-talkie"></a>Bereitstellen von Walkie Talkie

Während der öffentlichen Vorschau ist Walkie Talkie nicht vorinstalliert. Um dieses Feature für Benutzer in Ihrer Organisation zu aktivieren, müssen Sie Walkie Talkie der APP- [Setup Richtlinie](teams-app-setup-policies.md)hinzufügen, die   Benutzern aus dem [Team Admin Center](https://admin.teams.microsoft.com/)zugewiesen wurde.

Nach der Aktivierung wird Walkie Talkie innerhalb von 48 Stunden in der Android-App verfügbar sein.

### <a name="adding-walkie-talkie-to-your-app-list"></a>Hinzufügen von Walkie Talkie zu Ihrer APP-Liste

Im Microsoft Teams Admin Center sollten Sie unter **Teams-App**  >  -**Setup Richtlinien**zulassen, dass **Benutzer anheften** auf **ein**festgesetzt ist. Klicken Sie dann im Abschnitt angeheftete apps auf **+ apps hinzufügen**.

:::image type="content" source="media/deploy-walkie-talkie-1.png" alt-text="Zeigt den Abschnitt angeheftete apps und die Schaltfläche apps hinzufügen zur Auswahl an.":::

Verwenden Sie im Fenster **angeheftete apps hinzufügen** , das auf der rechten Seite angezeigt wird, das Textfeld **Suchen** , um nach Walkie Talkie zu suchen. Wenn Sie ein Suchergebnis haben, klicken Sie auf die Schaltfläche **Hinzufügen** rechts neben dem Namen, um es Ihrer Liste hinzuzufügen.

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="Zeigt die Sidebar "angeheftete apps hinzufügen" mit Walkie, das in den Suchbereich eingegeben wurde, und die Walkie Talkie-app in den Suchergebnissen, wobei die Schaltfläche Hinzufügen daneben angezeigt wird.":::

Die Walkie Talkie-app sollte nun in der Liste der angehefteten apps angezeigt werden und für die Verwendung verfügbar sein, sobald Sie auf die Schaltfläche " **Speichern** " klicken.

:::image type="content" source="media/deploy-walkie-talkie-3.png" alt-text="Zeigt die Liste der angehefteten apps mit hinzugefügter Walkie Talkie-APP und die Schaltfläche Speichern unter der Liste an.":::

### <a name="network-documentation"></a>Netzwerkdokumentation

Walkie Talkie in Teams erfordert Internet-Konnektivität und unter den Netzwerkbedingungen sind für eine optimale Nutzung erforderlich.

Latenz (RTT) < 300m | Jitter < 30ms | Paketverlust < 1%

Wie bereits erwähnt, wird die Qualität der Echt Zeit Medien über ein IP-Netzwerk stark von der Qualität der Netzwerkkonnektivität beeinflusst, insbesondere aber von der folgenden Anzahl:

- **Latenz** – Dies ist die Zeit, die zum Abrufen eines IP-Pakets von Punkt a zu Punkt B im Netzwerk erforderlich ist. Diese Verzögerung der Weitergabe im Netzwerk ist im Wesentlichen mit der physischen Entfernung zwischen den beiden Punkten und der Lichtgeschwindigkeit verknüpft. Dazu gehört auch der Mehraufwand durch die zwischen den Punkten vorhandenen Router. Latenz wird als Roundtrip (Round-Trip Time, RTT) gemessen.
- **Paketverlust** – Dies wird häufig als Prozentsatz der Pakete definiert, die in einem bestimmten Zeitfenster verloren gehen. Der Paketverlust wirkt sich direkt auf die Audioqualität aus – von kleinen, einzelnen verlorenen Paketen, die fast keine Auswirkungen haben, bis hin zu Burst Verlusten, die zu einem vollständigen Audioausschnitt führen.
- **Jitter** – Dies ist die durchschnittliche Verzögerungs Änderung zwischen aufeinanderfolgenden Paketen.

Die erwartete Datennutzung von Walkie Talkie beläuft sich auf 20KB/s beim Senden oder empfangen von Audio. Im Leerlauf ist die erwartete Datennutzung von Walkie Talkie vernachlässigbar.

### <a name="walkie-talkie-devices"></a>Walkie-Talkie-Geräte

Mitarbeiter von First-work müssen oft Walkie-Talkie-Anrufe sprechen und empfangen, auch wenn Ihre Telefone gesperrt sind. Diese Erfahrung ist durch spezielle Geräte mit einer speziellen PTT-Taste möglich.

- Vorhandene Telefone
  - Kabelgebundene Headsets ([klein Elektronik](https://www.kleinelectronics.com/))
  - Drahtlose Headsets ([Jabra BlueParrott](https://www.blueparrott.com/))
- Robuste Telefone
  - Samsung Galaxy XCover pro
    - [Weitere Informationen](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/).
    - [Einrichtungsleitfaden](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm).

> [!NOTE]
> Diese Geräte sind nicht zertifizierte Teams. Sie wurden für die Zusammenarbeit mit Teams Walkie Talkie validiert.

### <a name="license-requirements"></a>Lizenzanforderungen

Walkie Talkie-APP ist in allen bezahlten Lizenzen von Teams in [Office 365-Abonnements](https://docs.microsoft.com/MicrosoftTeams/office-365-licensing)enthalten. Weitere Informationen zum Abrufen von Teams finden Sie unter [wie erhalte ich Zugriff auf Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)?

> [!NOTE]
> Bestimmte erweiterte Funktionen erfordern möglicherweise zusätzliche Lizenzierung. Zum Beispiel erfordert die Integration in Samsung Galaxy XCover pro eine Knox-Lizenz.

## <a name="further-information"></a>Weitere Informationen

- ITAdmins kann die Kontrolle über die Nutzung von Walkie Talkie über APP-Richtlinien behalten.
- Wenn Ihr erster Mitarbeiter Mobile Daten für die Kommunikation über Teams verwendet, verwendet Walkie Talkie dieselbe Methode.
- Walkie Talkie sollte in Situationen mit niedriger Bandbreite oder in Situationen, in denen Ihr Smartphone angeschlossen ist und funktioniert, gut funktionieren. Walkie Talkie funktioniert nicht, wenn überhaupt keine Konnektivität vorhanden ist.

Weitere Informationen zur Benutzeroberfläche finden Sie unter:

- [Erste Schritte mit Teams Walkie Talkie](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [Kommunizieren mit Ihrem Team mit Walkie Talkie](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
