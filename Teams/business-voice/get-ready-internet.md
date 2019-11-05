---
title: Überprüfen Ihrer Internetverbindung
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: ''
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4dbfd1bdaec48ebe8c6adbed86da431a6f4ecbfc
ms.sourcegitcommit: 30b4b979e20066253e32ab9e44d79c48a97e6211
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2019
ms.locfileid: "37972276"
---
# <a name="check-your-internet-connection"></a>Überprüfen Ihrer Internetverbindung

Business Voice befindet sich in der Cloud mit Microsoft 365. Auf jedem Computer und Gerät, auf dem Microsoft Teams und Business Voice verwendet werden, ist eine Verbindung mit dem Internet erforderlich. Um Business Voice optimal zu nutzen, benötigen Sie eine Breitband-Internetverbindung, die die erwartete Anzahl von gleichzeitig ausgeführten Telefonanrufen unterstützt. Außerdem müssen Sie sicherstellen, dass Computer in Ihrem Netzwerk auf Microsoft 365-Server zugreifen können.

Um diese Schritte auszuführen, müssen Sie über einen Mandanten mit einem der folgenden Abonnements verfügen:

* Office 365 Business Essentials
* Office 365 Business Premium
* Office 365 E1
* Office 365 E3
* Office 365 F1
* Microsoft 365 A1
* Microsoft 365 A3
* Microsoft 365 E3
* Microsoft 365 Business

Sie benötigen keine Business Voice-Lizenz, um diese Schritte ausführen zu können.

## <a name="check-your-internet-connection-speed"></a>Überprüfen der Geschwindigkeit Ihrer Internetverbindung

Dieser Artikel hilft Ihnen zu ermitteln, ob Ihre Internetverbindung schnell genug für die Anzahl der Personen ist, die in der Lage sein müssen, Telefonanrufe zu tätigen, Videokonferenzen zu hosten und ähnliche Aktionen auszuführen. Sie geben bestimmte Informationen zu Ihrer Organisation ein und erhalten einen Bericht, der zeigt, welcher Anteil Ihrer Internetverbindung von Teams und Business Voice verwendet wird.

### <a name="get-information-about-your-internet-connection-and-users"></a>Abrufen von Informationen zu Ihrer Internetverbindung und den Benutzern

Bevor Sie beginnen, müssen Sie die folgenden Informationen kennen:

* Geschwindigkeit Ihrer Internetverbindung.
* Wie viele Personen Business Voice überwiegend aus Ihrem Büro nutzen.
* Wie viele Personen Business Voice überwiegend von einem Remotestandort aus verwenden, z. B. in einem Home-Office.

### <a name="enter-your-information-into-the-network-planner"></a>Eingeben Ihrer Informationen in den Netzwerkplaner

Nachstehend wird beschrieben, wie Sie vorgehen müssen:

1. Öffnen Sie einen Browser, navigieren Sie zu https://admin.teams.microsoft.com, und melden Sie sich mit einem Konto an, das über die Berechtigungen eines globalen Administrators verfügt. Das Konto, mit dem Sie sich bei Office 365 registriert haben, verfügt über diese Berechtigungen.
1. Öffnen Sie **Organisationsweite Einstellungen**, und wählen Sie dann **Netzwerkplaner** aus.
1. Wählen Sie unter **Netzwerkpläne** die Option **Hinzufügen** aus. Weisen Sie Ihrem Plan einen Namen zu, und wählen Sie dann **Übernehmen** aus. Ihr Netzwerkplan sollte wie folgt aussehen:

    ![Netzwerkplaner: Hauptbildschirm](../media/network-planner-main.png)
1. Klicken Sie auf den Namen Ihres Netzwerkplans (**Hauptbüro** in der obigen Abbildung).
1. Wählen Sie auf der nächsten Seite auf der Registerkarte **Netzwerkstandorte** die Option **Netzwerkstandort hinzufügen** aus.
1. Geben Sie die folgenden Informationen ein, und wählen Sie dann **Speichern** aus.

    ![Netzwerkplaner: Informationen zu Standorten](../media/network-planner-site-info.png)
1. Wählen Sie auf der Registerkarte **Bericht** die Option **Bericht starten** aus.
1. Geben Sie die folgenden Informationen ein, und wählen Sie dann **Bericht generieren** aus.

    ![Netzwerkplaner: Berichtsinformationen](../media/network-planner-report-info.png)

### <a name="find-your-minimum-internet-connection-speed"></a>Ermitteln der Mindestgeschwindigkeit Ihrer Internetverbindung

Wenn Sie **Bericht generieren** auswählen, erstellt Office 365 einen Bericht, der wie folgt aussieht:

![Netzwerkplaner: Berichtsdetails](../media/network-planner-report.png)

Die hervorgehobene Zahl gibt an, welcher Anteil ihrer Internetverbindung von Teams und Business Voice verwendet wird. Wir empfehlen, dass dieser Wert nicht mehr als 30 % der Gesamtgeschwindigkeit der Internetverbindung ausmacht. Wenn Ihre Internetverbindung z. B. 60 MBit/s beträgt, sollten auf Teams und Business Voice nicht mehr als 18 MBit/s entfallen.

Sie können die Mindestgeschwindigkeit Ihrer Internetverbindung ermitteln, indem Sie diese Berechnung ausführen: `<highlighted number> / .3`. Bei Verwendung der hervorgehobenen Zahl in der obigen Abbildung sähe die Berechnung wie folgt aus: `4.6875 / .3 = 15.6`. Dies bedeutet, dass die Mindestgeschwindigkeit Ihrer Internetverbindung mindestens 15,6 MBit/s betragen muss.

Wenn auf Teams und Business Voice mehr als 30 % der Gesamtgeschwindigkeit Ihrer Internetverbindung entfallen, wird die hervorgehobene Zahl rot angezeigt. In diesem Fall müssen Sie möglicherweise ein Upgrade Ihrer Internetverbindung durchführen.

![Verbindungsgeschwindigkeitswarnung](../media/network-planner-report-speed-warning.png)

## <a name="make-sure-computers-and-devices-on-your-network-can-reach-microsoft-365"></a>Sicherstellen, dass Computer und Geräte in Ihrem Netzwerk Microsoft 365 erreichen können

Um einen ordnungsgemäßen Betrieb zu gewährleisten, müssen die Computer und Geräte, die Sie mit Business Voice verwenden möchten, mit Microsoft 365-Servern über bestimmte Netzwerkports kommunizieren können. Netzwerkports sind im wesentlichen Türen, durch die Computer und Geräte in einem Netzwerk oder über das Internet miteinander kommunizieren können. Ihre Firewall muss zulassen, dass Computer und Geräte in Ihrem Netzwerk Microsoft 365 über die folgenden ausgehenden Netzwerkports erreichen können:

* **TCP-Ports** 80 und 443
* **UDP-Ports** 3478, 3479, 3480 und 3481

Die einfachste Möglichkeit, um zu überprüfen, ob Ihre Firewall die Kommunikation über diese Netzwerkports zulässt, besteht darin, einen Testanruf mithilfe von Teams zu führen. Führen Sie die folgenden Schritte aus, um einen Testanruf zu führen:

1. Wechseln Sie zu https://aka.ms/getteams auf einem Computer in Ihrem Netzwerk, um Teams zu installieren. Vergewissern Sie sich, dass mit diesem Computer Lautsprecher und ein Mikrofon verbunden sind.
2. Öffnen von Teams und Anmelden mit einem Microsoft 365-Konto
3. Wählen Sie in Teams Ihr Profilbild aus, und klicken Sie dann auf **Einstellungen** > **Geräte**
4. Wählen Sie unter **Audiogeräte** einen **Testanruf führen** aus.
5. Folgen Sie den Eingabeaufforderungen, um eine Nachricht zu hinterlassen und dieser abzuspielen.

* Wenn der Anruf eine Verbindung herstellt und Sie hören können, dass Ihre Nachricht wiedergegeben wird, ist Ihre Firewall ordnungsgemäß eingerichtet.
* Wenn der Anruf eine Verbindung herstellt, Sie aber die Eingabeaufforderungen nicht hören oder die Nachricht wiedergegeben wird, stellen Sie sicher, dass Ihre Lautsprecher und das Mikrofon ordnungsgemäß eingerichtet sind und vom Computer erkannt werden. Versuchen Sie es erneut.
* Wenn der Anruf keine Verbindung herstellt oder wenn die Verbindung hergestellt wird, Sie aber die Wiedergabe der Nachricht nicht hören, müssen Sie Ihre Firewall möglicherweise so aktualisieren, dass sie die Kommunikation über die oben aufgeführten Netzwerkports zulässt. Lesen Sie in der Dokumentation Ihrer Firewall nach, wie Sie die Kommunikation von Netzwerkports mit dem Internet zulassen können, oder wenden Sie sich an einen IT-Spezialisten, der Sie unterstützt.

Wenn Sie ein IT-Experte sind und weitere Informationen zur Vorbereitung größerer oder komplexerer Netzwerke für die Unterstützung von Business Voice benötigen, schauen Sie sich [Bewerten der Umgebung](../3-envision-evaluate-my-environment.md) an. Im Artikel [Bewerten der Umgebung](../3-envision-evaluate-my-environment.md) finden Sie weitere Informationen zu den Anforderungen für Bandbreite, Proxy und Firewall sowie zum Testen Ihres Netzwerks mithilfe des [Netzwerkbewertungstools](../3-envision-evaluate-my-environment.md#test-the-network).
