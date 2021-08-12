---
title: Überprüfen Ihrer Internetverbindung für Business Voice
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: ''
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0b5aed539e7d32db7650bb1b9778c912d0065b411832337438c251177d88e809
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54286064"
---
# <a name="check-your-internet-connection-for-business-voice"></a>Überprüfen Ihrer Internetverbindung für Business Voice

Business Voice befindet sich in der Cloud mit Microsoft 365. Für jeden Computer und jedes Gerät, auf dem Microsoft Teams und Business Voice verwendet werden, ist eine Verbindung mit dem Internet erforderlich.

Um Business Voice optimal nutzen zu können, benötigen Sie eine Breitband-Internetverbindung, die die maximale Anzahl von gleichzeitig in Ihrer Organisation ausgeführten Telefonanrufen unterstützt. Außerdem müssen Sie sicherstellen, dass die Computer in Ihrem Netzwerk auf Microsoft 365-Server zugreifen können.

Um diese Schritte auszuführen, müssen Sie über einen Mandanten mit einem der folgenden Abonnements verfügen:

* Microsoft 365 Business Basic
* Microsoft 365 Business Standard
* Office 365 E1
* Office 365 E3
* Office 365 F1
* Microsoft 365 A1
* Microsoft 365 A3
* Microsoft 365 E3
* Microsoft 365 Business

Sie benötigen keine Business Voice-Lizenz, um diese Schritte ausführen zu können.

## <a name="check-your-internet-connection-speed"></a>Überprüfen der Geschwindigkeit Ihrer Internetverbindung

Dieser Artikel hilft Ihnen zu ermitteln, ob Ihre Internetverbindung schnell genug für die Anzahl der Personen ist, die in der Lage sein müssen, Telefonanrufe zu tätigen und Videokonferenzen zu hosten. Sie geben bestimmte Informationen zu Ihrer Organisation ein und erhalten einen Bericht, der angibt, welcher Anteil Ihrer Internetverbindung von Microsoft Teams und Business Voice verwendet wird.

### <a name="gather-information-about-your-internet-connection-and-users"></a>Sammeln von Informationen zu Ihrer Internetverbindung und den Benutzern

Bevor Sie beginnen, benötigen Sie die folgenden Informationen:

* Die Geschwindigkeit Ihrer Internetverbindung
* Wie viele Personen Business Voice überwiegend aus Ihrem Büro nutzen werden
* Wie viele Personen Business Voice überwiegend von einem Remotestandort aus verwenden werden, z. B. in einem Home-Office

### <a name="enter-your-information-into-the-network-planner"></a>Eingeben Ihrer Informationen in den Netzwerkplaner

Führen Sie die folgenden Schritte aus:

1. Gehen Sie in einem Browser zu https://admin.teams.microsoft.com. Melden Sie sich mit einem Konto an, das über die Berechtigungen eines globalen Administrators verfügt. Das Konto, mit dem Sie sich bei Microsoft 365 oder Office 365 registriert haben, verfügt über diese Berechtigungen.
2. Öffnen Sie **Planung** und dann **Netzwerkplaner** aus.
3. Wählen Sie unter **Netzwerkpläne** die Option **Hinzufügen** aus. Weisen Sie Ihrem Plan einen Namen zu, und wählen Sie dann **Übernehmen** aus. Ihr Netzwerkplan sollte wie folgt aussehen:

    ![Netzwerkplaner: Hauptbildschirm](../media/network-planner-main.png)
1. Wählen Sie den Namen Ihres Netzwerkplans aus. (Es entspricht **Hauptsitz** im vorhergehenden Bild.)
2. Wählen Sie auf der nächsten Seite auf der Registerkarte **Netzwerkstandorte** die Option **Netzwerkstandort hinzufügen** aus.
3. Füllen Sie nur die im folgenden Screenshot angegebenen Felder aus, und wählen Sie dann **Speichern**. Lassen Sie die anderen Felder auf diesem Bildschirm leer, und wählen Sie weder die Option **ExpressRoute** noch die Option **Verbunden mit WAN** aus.

    ![Netzwerkplaner: Informationen zu Standorten](../media/network-planner-site-info.png)
1. Wählen Sie auf der Registerkarte **Bericht** die Option **Bericht starten** aus.
1. Geben Sie die folgenden Informationen ein, und wählen Sie dann **Bericht erstellen** aus, um einen Bericht mit den Bandbreitenanforderungen für Microsoft Teams zu erstellen. Im nächsten Abschnitt wird beschrieben, wie Sie den Bericht lesen.

    ![Netzwerkplaner: Berichtsinformationen](../media/network-planner-report-info.png)

### <a name="find-your-minimum-internet-connection-speed"></a>Ermitteln der Mindestgeschwindigkeit Ihrer Internetverbindung

Wenn Sie **Bericht generieren** auswählen, erstellt Microsoft 365 bzw. Office 365 einen Bericht, der wie folgt aussieht:

![Netzwerkplaner: Berichtsdetails](../media/network-planner-report.png)

Die hervorgehobene Zahl gibt an, welcher Anteil ihrer Internetverbindung von Teams und Business Voice verwendet wird. Wir empfehlen, dass dieser Wert nicht mehr als 30 % der Gesamtgeschwindigkeit der Internetverbindung ausmacht. Wenn Ihre Internetverbindung z. B. 60 MBit/s beträgt, sollten auf Microsoft Teams und Business Voice nicht mehr als 18 MBit/s entfallen.

Verwenden Sie diese Gleichung zur Ermittlung Ihrer Mindest-Verbindungsgeschwindigkeit: *\<highlighted number> / 0,3*. Mit der im vorherigen Bild hervorgehobenen Zahl lautet die Berechnung *4,6875 / 0,3 = 15,6*. In diesem Fall sollte sich die Geschwindigkeit der Internetverbindung auf mindestens 15,6 MBit/s belaufen.

Wenn auf Teams und Business Voice mehr als 30 % der Gesamtgeschwindigkeit Ihrer Internetverbindung entfallen, wird die hervorgehobene Zahl rot angezeigt. In diesem Fall müssen Sie möglicherweise ein Upgrade Ihrer Internetverbindung durchführen.

![Verbindungsgeschwindigkeitswarnung](../media/network-planner-report-speed-warning.png)

## <a name="make-sure-the-computers-and-devices-on-your-network-can-reach-microsoft-365"></a>Feststellen, ob Computer und Geräte in Ihrem Netzwerk Microsoft 365 erreichen können

Computer und Geräte, die Business Voice verwenden, müssen bestimmte Netzwerkports für die Kommunikation mit Microsoft 365-Servern verwenden. Diese Netzwerkports sind im Wesentlichen Türen, durch die Geräte in einem Netzwerk oder über das Internet miteinander kommunizieren können. Ihre Firewall muss zulassen, dass die Geräte in Ihrem Netzwerk Microsoft 365 über die folgenden *ausgehenden* Netzwerkports erreichen können:

* **TCP-Ports** 80 und 443
* **UDP-Ports** 3478, 3479, 3480 und 3481

Die einfachste Möglichkeit, um zu überprüfen, ob Ihre Firewall die Kommunikation über diese Netzwerkports zulässt, besteht darin, einen Testanruf in Microsoft Teams durchzuführen.

1. Wechseln Sie zu https://aka.ms/getteams auf einem Computer in Ihrem Netzwerk, und installieren Sie Microsoft Teams. Vergewissern Sie sich, dass der Computer über Lautsprecher und ein Mikrofon verfügt.
2. Öffnen Sie Microsoft Teams und melden Sie sich mit einem Microsoft 365-Konto an.
3. Wählen Sie in Teams Ihr Profilbild aus, und gehen Sie dann zu **Einstellungen** > **Geräte**.
4. Wählen Sie unter **Audiogeräte** die Option **Testanruf führen** aus.
5. Führen Sie die Schritte aus, um eine Nachricht zu hinterlassen und diese abzuspielen.

   * Wenn der Anruf eine Verbindung herstellt und Sie Ihre Nachricht hören können, ist Ihre Firewall ordnungsgemäß eingerichtet.
   * Wenn der Anruf eine Verbindung herstellt, Sie aber die Anweisungen nicht hören oder die Nachricht nicht wiedergegeben wird, überprüfen Sie, ob Ihre Lautsprecher und das Mikrofon ordnungsgemäß eingerichtet sind und vom Computer erkannt werden. Versuchen Sie es anschließend erneut.
   * Wenn der Anruf keine Verbindung herstellt oder wenn die Verbindung hergestellt wird, Sie aber die Wiedergabe der Nachricht nicht hören, müssen Sie Ihre Firewall möglicherweise so aktualisieren, dass sie den Zugang zu den oben aufgeführten Netzwerkports zulässt. Sehen Sie in der Dokumentation zu Ihrer Firewall nach, oder wenden Sie sich an einen IT-Spezialisten.

 Wenn Sie ein IT-Experte sind und weitere Informationen zur Vorbereitung größerer oder komplexerer Netzwerke für die Unterstützung von Business Voice benötigen, schauen Sie sich [Bewerten der Umgebung](../3-envision-evaluate-my-environment.md) an. In diesem Artikel finden Sie weitere Informationen zu den Anforderungen für Bandbreite, Proxy und Firewall sowie zum Testen Ihres Netzwerks mithilfe des [Netzwerkbewertungstools](../3-envision-evaluate-my-environment.md#test-the-network).

