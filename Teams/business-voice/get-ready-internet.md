---
title: Überprüfen Sie Ihre Internetverbindung, um Teams Telefon Anrufplan zu finden
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: ''
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5f28350c2ae0487ed62d55bbd99d6a731a7bfac0
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2022
ms.locfileid: "61766918"
---
# <a name="check-your-internet-connection-for-teams-phone"></a>Überprüfen Sie Ihre Internetverbindung auf Teams Telefon

Teams Telefon ist die Microsoft-Technologie zum Aktivieren von Telefonfunktionen in Microsoft Teams mithilfe der Microsoft 365 Cloud. Jedes Gerät, das Microsoft Teams und Teams Telefon verwendet, benötigt eine Internetverbindung.

Um optimale Ergebnisse Teams Telefon nutzen zu können, benötigen Sie eine Breitband-Internetverbindung, die die maximale Anzahl von Telefonanrufen unterstützt, die Ihre Organisation zu einem beliebigen Zeitpunkt möglicherweise telefoniert. Außerdem müssen Sie sicherstellen, dass die Computer in Ihrem Netzwerk ihre Microsoft 365 können.

Sie benötigen keine Lizenz Teams Telefon, um diese Schritte ausführen zu können.

## <a name="check-your-internet-connection-speed"></a>Überprüfen der Geschwindigkeit Ihrer Internetverbindung

In diesem Artikel wird ermittelt, ob Ihre Internetverbindung für die Anzahl der Personen, die Telefonanrufe anrufen müssen, schnell genug ist. Sie geben Informationen zu Ihrer Organisation an und erhalten einen Bericht zurück, der anschaut, wie viel Ihrer Internetverbindung von Ihrem Unternehmen verwendet Teams und Teams Telefon.

### <a name="gather-information-about-your-internet-connection-and-users"></a>Sammeln von Informationen zu Ihrer Internetverbindung und den Benutzern

Bevor Sie beginnen, benötigen Sie die folgenden Informationen:

* Die Geschwindigkeit Ihrer Internetverbindung
* Wie viele Personen verwenden ihre Teams Telefon hauptsächlich aus Ihrem Büro
* Wie viele Personen die Teams Telefon hauptsächlich von einem Remotestandort, z. B. einem Home Office, verwenden werden

### <a name="enter-your-information-into-the-network-planner"></a>Eingeben Ihrer Informationen in den Netzwerkplaner

Führen Sie die folgenden Schritte aus:

1. Wechseln Sie in einem Browser zu [https://admin.teams.microsoft.com](https://admin.teams.microsoft.com) . Melden Sie sich mit einem Konto an, das über die Berechtigungen eines globalen Administrators verfügt. Das Konto, mit dem Sie sich bei Microsoft 365 oder Office 365 registriert haben, verfügt über diese Berechtigungen.
2. Öffnen Sie **Planung** und dann **Netzwerkplaner** aus.
3. Wählen Sie unter **Netzwerkpläne** die Option **Hinzufügen** aus. Weisen Sie Ihrem Plan einen Namen zu, und wählen Sie dann **Übernehmen** aus.
4. Wählen Sie den Namen Ihres Netzwerkplans aus.
5. Wählen Sie auf der nächsten Seite auf der Registerkarte **Netzwerkstandorte** die Option **Netzwerkstandort hinzufügen** aus.
6. Füllen Sie die **Felder Netzwerkwebsitename,** **Netzwerkbenutzer** und **Internetverknüpfungskapazität** aus, und wählen Sie dann **Speichern aus.** Lassen Sie die anderen Felder auf diesem Bildschirm leer, und wählen Sie weder die Option **ExpressRoute** noch die Option **Verbunden mit WAN** aus.
7. Wählen Sie auf der Registerkarte **Bericht** die Option **Bericht starten** aus.
8. Geben Sie  einen Berichtsnamen und die Anzahl der Netzwerkbenutzer **(**  **Office** und **Remote**) ein, und wählen Sie dann Bericht generieren aus, um einen Bericht zu erstellen, in dem die Bandbreitenanforderungen für das Netzwerk Teams. Wir informieren Sie, wie Sie den Bericht im nächsten Abschnitt lesen können.

### <a name="find-your-minimum-internet-connection-speed"></a>Feststellen der Mindestgeschwindigkeit der Internetverbindung

Wenn Sie Bericht **generieren auswählen, wird** Microsoft 365 oder Office 365 Bericht erstellt.

Unter der **Spalte** Auswirkung und in **der Zeile Office 365** Wird angezeigt, wie viel Ihrer Internetverbindung Teams und Teams Telefon wird. Wir empfehlen, dass diese Zahl nicht mehr als 30 Prozent der gesamten Internetverbindungsgeschwindigkeit beträgt. Wenn Ihre Internetverbindung beispielsweise *60* MBit/s beträgt, Teams und Teams Telefon dürfen nicht mehr als *18 MBit/s verwendet werden.*

Verwenden Sie die folgende Gleichung, um Ihre minimale Internetverbindungsgeschwindigkeit zu ermitteln: <*Auswirkungen> / 0,3*.  

Angenommen, die Anzahl der Auswirkungen beträgt *4,6875 MBit/s.* Die Berechnung für die Ermittlung Ihrer Mindestgeschwindigkeit für Internetverbindungen würde *4,6875 / 0,3 = 15,6 sein.* In diesem Fall sollte die Internetverbindungsgeschwindigkeit mindestens *15,6 MBit/s betragen.*

Wenn Teams und Teams Telefon 30 Prozent Ihrer gesamten Internetverbindungsgeschwindigkeit verwenden,  wird die Zahl der Auswirkungen rot angezeigt. In diesem Fall müssen Sie möglicherweise ein Upgrade Ihrer Internetverbindung durchführen.

![Warnung zur Verbindungsgeschwindigkeit.](../media/network-planner-report-speed-warning.png)

>[!NOTE]
> Die Bandbreitenbelastung, die von Netzwerkplaner bereitgestellt wird, ist nur eine Schätzung. Es wird empfohlen, das [Anrufqualitätsdashboard](../cqd-what-is-call-quality-dashboard.md) zu verwenden, um die Benutzeroberfläche für Audio- und Videoanrufe mit Benutzern innerhalb Microsoft Teams Organisation aktiv zu überwachen.

## <a name="make-sure-the-computers-and-devices-on-your-network-can-reach-microsoft-365"></a>Feststellen, ob Computer und Geräte in Ihrem Netzwerk Microsoft 365 erreichen können

Computer und Geräte, die Teams Telefon verwenden, müssen bestimmte Netzwerkports für die Kommunikation mit den Microsoft 365 verwenden. Diese Ports sind im Wesentlichen Türen, durch die Geräte über ein Netzwerk oder das Internet miteinander sprechen. Ihre Firewall muss zulassen, dass die Geräte in Ihrem Netzwerk Microsoft 365 über die folgenden *ausgehenden* Netzwerkports erreichen können:

* **TCP-Ports** 80 und 443
* **UDP-Ports** 3478, 3479, 3480 und 3481

Die einfachste Möglichkeit, zu überprüfen, ob Ihre Firewall die Kommunikation [](/microsoft-365/enterprise/office-365-network-mac-perf-onboarding-tool) auf diesen Netzwerkports zulässt, besteht im Durchführen eines Verbindungstests mit dem Microsoft 365-Netzwerkkonnektivitätstool von dem Bürostandort aus, den Sie testen möchten. Überprüfen Sie nach Abschluss des Tests die Ergebnisse und Empfehlungen.
