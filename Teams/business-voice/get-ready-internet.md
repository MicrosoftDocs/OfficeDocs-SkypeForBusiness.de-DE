---
title: Überprüfen Der Internetverbindung für das Microsoft Teams-Telefonsystem
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: Überprüfen Sie, ob Ihr Internet für das Microsoft Teams-Telefonsystem bereit ist.
appliesto:
- Microsoft Teams
ms.collection:
- M365-voice
ms.openlocfilehash: 5cbc8613a91e2b776faff922fb9a3a98b3dd545e
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271050"
---
# <a name="check-your-internet-connection-for-teams-phone-system"></a>Überprüfen Der Internetverbindung für das Microsoft Teams-Telefonsystem

Teams Phone System ist die Technologie von Microsoft zum Aktivieren von Telefonfunktionen in Microsoft Teams mithilfe der Microsoft 365-Cloud. Jedes Gerät, das Microsoft Teams und das Telefonsystem verwendet, benötigt eine Internetverbindung.

Um eine optimale Telefonsystemerfahrung zu erzielen, benötigen Sie eine Breitband-Internetverbindung, die die maximale Anzahl von Telefonanrufen unterstützt, die Ihre Organisation möglicherweise gleichzeitig tätigen kann. Sie müssen auch sicherstellen, dass die Computer in Ihrem Netzwerk Microsoft 365-Dienste erreichen können.

## <a name="check-your-internet-connection-speed"></a>Überprüfen der Geschwindigkeit Ihrer Internetverbindung

In diesem Artikel wird ermittelt, ob Ihre Internetverbindung schnell genug für die Anzahl der Personen ist, die Telefonanrufe tätigen müssen. Sie stellen Informationen zu Ihrer Organisation bereit und erhalten einen Bericht, der zeigt, wie viel Ihrer Internetverbindung von Teams und Telefonsystem verwendet wird.

### <a name="gather-information-about-your-internet-connection-and-users"></a>Sammeln von Informationen über Ihre Internetverbindung und Benutzer

Bevor Sie beginnen, benötigen Sie die folgenden Informationen:

* Die Geschwindigkeit Ihrer Internetverbindung
* Wie viele Personen das Telefonsystem hauptsächlich aus Ihrem Büro verwenden
* Wie viele Personen das Telefonsystem hauptsächlich von einem Remotestandort aus verwenden, z. B. ein Home-Office

### <a name="enter-your-information-into-the-network-planner"></a>Eingeben Ihrer Informationen in den Netzwerkplaner

Führen Sie die folgenden Schritte aus:

1. Wechseln Sie in einem Browser zu [https://admin.teams.microsoft.com](https://admin.teams.microsoft.com). Melden Sie sich mit einem Konto an, das über die Berechtigungen eines globalen Administrators verfügt. Das Konto, das Sie für die Registrierung für Microsoft 365 verwendet haben, verfügt über diese Berechtigungen.
2. Öffnen Sie **Planung** und dann **Netzwerkplaner** aus.
3. Wählen Sie unter **Netzwerkpläne** die Option **Hinzufügen** aus. Weisen Sie Ihrem Plan einen Namen zu, und wählen Sie dann **Übernehmen** aus.
4. Wählen Sie den Namen Ihres Netzwerkplans aus.
5. Wählen Sie auf der nächsten Seite auf der Registerkarte **Netzwerkstandorte** die Option **Netzwerkstandort hinzufügen** aus.
6. Geben Sie die Felder **"Netzwerkstandortname**", **"Netzwerkbenutzer**" und " **Internetverknüpfungskapazität** " ein, und wählen Sie " **Speichern"** aus. Lassen Sie die anderen Felder auf diesem Bildschirm leer, und wählen Sie weder die Option **ExpressRoute** noch die Option **Verbunden mit WAN** aus.
7. Wählen Sie auf der Registerkarte **Bericht** die Option **Bericht starten** aus.
8. Geben Sie einen **Berichtsnamen** und die Anzahl der **Netzwerkbenutzer** (**Office** und **Remote**) ein, und wählen Sie dann **"Bericht generieren** " aus, um einen Bericht zu erstellen, in dem die Bandbreitenanforderungen für Teams angezeigt werden. Wie Sie den Bericht lesen, erfahren Sie im nächsten Abschnitt.

### <a name="find-your-minimum-internet-connection-speed"></a>Ermitteln der mindesten Geschwindigkeit der Internetverbindung

Wenn Sie **"Bericht generieren**" auswählen, erstellt Microsoft 365 einen Bericht.

Unter der Spalte **"Auswirkungen"** und in der Zeile **"Office 365**" zeigt diese Nummer an, wie viel Von Ihrer Internetverbindung Teams und Telefonsystem verwendet werden. Wir empfehlen, dass diese Zahl nicht mehr als 30 Prozent ihrer gesamten Internetverbindungsgeschwindigkeit beträgt. Wenn Ihre Internetverbindung beispielsweise *60 MBit/s* beträgt, sollten Teams und Das Telefonsystem nicht mehr als *18 Mbit/s* verwenden.

Verwenden Sie diese Gleichung, um ihre minimale Internetverbindungsgeschwindigkeit zu ermitteln: <*Auswirkungsnummer> / 0,3*.  

Angenommen, die Auswirkungsnummer beträgt *4,6875 Mbit/s*. Die Berechnung, um Ihre minimale Internet-Verbindungsgeschwindigkeit zu finden, wäre *4,6875 / 0,3 = 15,6*. In diesem Fall sollte die Geschwindigkeit der Internetverbindung mindestens *15,6 MBit/s* betragen.

Wenn Teams und Das Telefonsystem mehr als 30 Prozent ihrer gesamten Internetverbindungsgeschwindigkeit verwenden, wird die **Auswirkungsnummer** rot angezeigt. In diesem Fall müssen Sie ihre Internetverbindung möglicherweise aktualisieren.

![Warnung zur Verbindungsgeschwindigkeit.](../media/network-planner-report-speed-warning.png)

>[!NOTE]
> Die vom Netzwerkplaner bereitgestellte Bandbreitenbelastung ist nur eine Schätzung. Es wird empfohlen, das [Anrufqualitätsdashboard](../cqd-what-is-call-quality-dashboard.md) zu verwenden, um die Benutzerfreundlichkeit für Audio- und Videoanrufe mit Microsoft Teams innerhalb Ihrer Organisation proaktiv zu überwachen.

## <a name="make-sure-the-computers-and-devices-on-your-network-can-reach-microsoft-365"></a>Feststellen, ob Computer und Geräte in Ihrem Netzwerk Microsoft 365 erreichen können

Computer und Geräte, die das Telefonsystem verwenden, müssen bestimmte Netzwerkports für die Kommunikation mit Microsoft 365-Diensten verwenden. Diese Ports sind im Wesentlichen Türen, über die Geräte über ein Netzwerk oder das Internet miteinander kommunizieren. Ihre Firewall muss zulassen, dass die Geräte in Ihrem Netzwerk Microsoft 365 über die folgenden *ausgehenden* Netzwerkports erreichen können:

* **TCP-Ports** 80 und 443
* **UDP-Ports** 3478, 3479, 3480 und 3481

Die einfachste Möglichkeit, zu überprüfen, ob Ihre Firewall die Kommunikation über diese Netzwerkports zulässt, besteht darin, einen Konnektivitätstest mit dem [Microsoft 365-Netzwerkverbindungstool](/microsoft-365/enterprise/office-365-network-mac-perf-onboarding-tool) von dem Bürostandort aus durchzuführen, den Sie testen möchten. Überprüfen Sie nach Abschluss des Tests die Ergebnisse und Empfehlungen.
