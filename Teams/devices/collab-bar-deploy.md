---
title: Bereitstellen von Zusammenarbeits leisten für Microsoft Teams
ms.author: mitressl
author: flinchbot
manager: serdars
audience: ITPro
ms.reviewer: payurevi
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: In diesem Artikel finden Sie Informationen zum Bereitstellen von Zusammenarbeits leisten für Microsoft Teams.
ms.openlocfilehash: 4593d6b42e61efbd7d57f27fd0a10ed8f97b82f5
ms.sourcegitcommit: f0ccafb7e9c2d382ab4545e085657e8129024f1d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/16/2020
ms.locfileid: "44268055"
---
# <a name="deploy-collaboration-bars-for-microsoft-teams"></a>Bereitstellen von Zusammenarbeits leisten für Microsoft Teams

Die Bereitstellung von Zusammenarbeits leisten für Microsoft Teams kann in die folgenden Phasen aufgeschlüsselt werden:

- **Website Bereitschaft** Vergewissern Sie sich, dass Ihre Bereitstellungs Standorte (Räume) den Bereitstellungsanforderungen entsprechen.
- **Dienstbereitschaft** Erstellen Sie Ressourcenkonten, und weisen Sie diese den Geräten zu ([Siehe Erstellen eines Ressourcenkontos mithilfe des Microsoft 365 admin Centers](resource-account-ui.md)). Zwar empfehlen wir die Verwendung einer dedizierten Raum Lizenz, doch ein ordnungsgemäß lizenziertes Endbenutzerkonto kann sich auch bei den Zusammenarbeits leisten anmelden.
- **Konfiguration und Bereitstellung** Einrichten von Kollaborations leisten in Räumen und Verbinden der benötigten Peripheriegeräte (siehe die Dokumentation des Herstellers für Ihre Zusammenarbeits leisten).

## <a name="site-readiness"></a>Website Bereitschaft

Während die bestellten Geräte an Ihre Organisation übermittelt werden, arbeiten Sie mit Ihren Netzwerk-, Infrastruktur-und audiovisuellen Teams zusammen, um sicherzustellen, dass die Bereitstellungsanforderungen erfüllt sind und jeder Standort und jeder Raum in Bezug auf Leistung, Netzwerk und Anzeige bereit ist.

Unsere Empfehlungen für Websites für die Zusammenarbeit sind:

- Zimmer bis zu 4 Personen in der Größe
- Dedizierte Ressourcenkonten
- Touch-fähige Displays
- Ethernet-Verkabelung
- Quality of Service (QoS), die im Netzwerk für Microsoft Teams-Medien aktiviert ist

Informationen zu physikalischen Installationsüberlegungen finden Sie in der Dokumentation des Herstellers, und wenn Sie eine solche haben, nutzen Sie die Erfahrung ihres audiovisuellen Teams, bevor Sie Bildschirme installieren und bereitstellen und die Verkabelung ausführen.

> [!TIP]
> Stellen Sie sicher, dass Sie [Ihr Netzwerk für Teams](../prepare-network.md) für die Bandbreitenplanung vorbereiten und die Eignung Ihres Netzwerks für die Echtzeitübertragung bewerten.
>
> Es wird nicht empfohlen, Proxy Server zwischen Teams-Geräten und dem Internet zu platzieren. Weitere Informationen zu Proxyservern und Teams finden Sie unter [Proxy Server für Teams](../proxy-servers-for-skype-for-business-online.md).

|    |     |
|-----------|------------|
| ![Ein Symbol mit Entscheidungspunkten](../media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Überprüfen Sie, ob Ihre Websites die Website Readiness-Anforderungen für Zusammenarbeits leisten für Microsoft Teams erfüllen.</li><li>Vergewissern Sie sich, dass Sie für jede Website genügend Bandbreite bereitgestellt haben.</li></ul>|
| ![Ein Symbol, das die nächsten Schritte darstellt](../media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Beginnen Sie mit der Planung der Bereitstellung und Konfiguration der Zusammenarbeits Leiste.</li></ul>|

## <a name="service-readiness"></a>Bereitschaft für den Dienst

Bevor Sie Ihre Zusammenarbeits leisten bereitstellen, müssen Sie entscheiden, ob Sie Microsoft 365-Ressourcenkonten, Endbenutzerkonten oder eine Kombination aus beidem verwenden werden. Microsoft 365-Ressourcenkonten sind Postfach-und Teams-Konten, die für bestimmte Ressourcen dediziert sind, beispielsweise einen Raum, einen Projektor usw. Diese Ressourcenkonten können mithilfe von Regeln, die Sie bei der Erstellung definieren, automatisch auf Besprechungseinladungen Antworten. Sofern eine Zusammenarbeits Leiste nicht für eine bestimmte Person für Ihre private Verwendung reserviert ist, empfehlen wir die Einrichtung eines Microsoft 365-Ressourcenkontos.

### <a name="using-a-resource-account"></a>Verwenden eines Ressourcenkontos

Wenn Sie sich entscheiden, ein Microsoft 365-Ressourcenkonto einzurichten, müssen Sie eine Lizenz für den Besprechungsraum erwerben. Die Lizenz für den Besprechungsraum umfasst ein Ressourcenpostfach, das es Personen in Ihrer Organisation ermöglicht, den Besprechungsraum über Outlook oder Teams zu buchen. Die Lizenz ermöglicht auch die Video-und Audiokonferenzen sowie die Bildschirmübertragung zwischen Besprechungsteilnehmern.

Wenn Sie eine externe Telefonnummer empfangen oder anrufen müssen, benötigen Sie außerdem ein Microsoft 365-Telefon System oder eine Microsoft 365 Business Voice-Lizenz.

Wenn Sie ein Ressourcenkonto erstellen, können Sie auswählen, ob das Konto Besprechungsanfragen automatisch annehmen oder ablehnen, wiederkehrende Besprechungen zulassen, angeben, wie weit im Voraus Personen die Ressource buchen können usw.

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

Weitere Informationen zu den Zusammenarbeits leisten für Microsoft 365-Ressourcenkonten finden Sie unter [Erstellen eines Ressourcenkontos mit dem Microsoft 365 Admin Center](resource-account-ui.md).

|    |     |
|-----------|------------|
| ![Ein Symbol mit Entscheidungspunkten](../media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Entscheiden Sie, ob Sie externe Telefonanrufe tätigen oder empfangen möchten, und ermitteln Sie die Lizenzierungsanforderungen für Ihre Ressourcenkonten.</li></ul>|
| ![Ein Symbol, das die nächsten Schritte darstellt](../media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Vorbereiten von Ressourcenkonten</li></ul>|

## <a name="configuration-and-deployment"></a>Konfiguration und Bereitstellung

Die Planung für Konfiguration und Bereitstellung umfasst die folgenden Hauptbereiche:

- Bereitstellung von Ressourcenkonten
- Gerätebereitstellung
- Zusammenarbeits leisten für Microsoft Teams-Anwendung und Peripheriegeräte Konfiguration
-  Tests
- Ressourcenverwaltung

### <a name="account-provisioning"></a>Kontobereitstellung

Wenn Sie beabsichtigen, Microsoft 365-Ressourcenkonten zu verwenden, um Benutzern das Buchen von Zusammenarbeits leisten zu ermöglichen, folgen Sie den Anweisungen unter [Erstellen eines Ressourcenkontos mithilfe des Microsoft 365 admin Centers](resource-account-ui.md) , um ein Microsoft 365-Ressourcenkonto für jede gewünschte Zusammenarbeits Leiste zu erstellen. Hier müssen Sie auch eine Besprechungsraum-Lizenz zum Ressourcenkonto hinzufügen und, wenn Sie Anrufe an oder von externen Telefonnummern tätigen oder empfangen möchten, eine Telefonanlage oder eine Business-VoIP-Lizenz.

Wenn Sie den einzelnen Benutzern für Ihre private Nutzung Kollaborations Balken zuweisen möchten, müssen Sie keine weiteren Konten einrichten. Benutzer können sich mit ihren privaten Konten bei den Zusammenarbeits leisten anmelden.

> [!TIP]
> Machen Sie die Anzeigenamen für Ihre Microsoft 365-Ressourcenkonten aussagekräftig und verständlich. Dies sind die Namen, die Benutzern bei der Suche nach und Hinzufügen von Zusammenarbeits leisten für Microsoft Teams zu Besprechungen angezeigt werden. Sie können eine Konvention wie *Site* - den Namen des Website*Raums*(*Max. Raumkapazität*) verwenden, sodass beispielsweise Curie, ein 4-Personen-Besprechungsraum in London, den Anzeigenamen Lon-Curie (4) aufweisen kann.

|    |     |
|-----------|------------|
| ![Ein Symbol mit Entscheidungspunkten](../media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Entscheiden Sie sich für die Benennungskonvention für ihre dedizierten Ressourcenkonten.</li><li>Entscheiden Sie, ob Sie einzelne Konten erstellen oder Massen Bereitstellungsskripts verwenden möchten.</li></ul>|
| ![Ein Symbol, das die nächsten Schritte darstellt](../media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Beginnen Sie mit der Planung der Gerätebereitstellung.</li></ul>|

### <a name="device-deployment"></a>Gerätebereitstellung

Als nächstes müssen Sie Ihren Plan erstellen, um die Geräte und die Ihnen zugewiesenen Peripheriegeräte an Ihre Räume zu übermitteln, und dann mit der Installation und Konfiguration fortfahren.

|    |     |
|-----------|------------|
| ![Ein Symbol mit Entscheidungspunkten](../media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Entscheiden Sie, wer die Site-by-Site-Bereitstellung verwalten soll.</li><li> Ermitteln Sie die Ressourcen, die die Zusammenarbeits leisten für Microsoft Teams vor Ort installieren, und führen Sie die Konfiguration und Tests durch.</li></ul>|
| ![Ein Symbol, das die nächsten Schritte darstellt](../media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Starten Sie den Gerätetest.</li></ul>|

### <a name="testing"></a> Tests

Nachdem die Zusammenarbeits leisten für Microsoft Teams bereitgestellt wurden, sollten Sie Sie testen. Melden Sie sich beim Gerät an, und überprüfen Sie, ob die erwarteten Funktionen auf dem bereitgestellten Gerät funktionieren. Wir empfehlen dringend, dass Sie überprüfen, ob die Geräte im Abschnitt " **Zusammenarbeits Balken** " auf der Registerkarte " **Geräte** " des Microsoft Teams admin Centers angezeigt werden. Es ist auch wichtig, dass Sie eine Reihe von Testanrufen und Besprechungen vornehmen, um die Qualität und Leistung zu überprüfen.

Wir empfehlen, dass Sie im Rahmen des allgemeinen Microsoft Teams-Rollouts Bausteine für das Anruf Qualitäts Dashboard (CQD) konfigurieren, qualitätstrends überwachen und sich an der Prüfung der Qualität der Erfahrung beteiligen. Weitere Informationen finden Sie im [Leitfaden zur Überprüfung der Qualität der Benutzerfreundlichkeit](https://aka.ms/qerguide).

### <a name="asset-management"></a>Ressourcenverwaltung

Als Teil der Bereitstellung sollten Sie Ihr Ressourcen Register mit dem Raum Namen, dem Konto für die Anmeldung und den zugewiesenen Peripheriegeräten aktualisieren.

## <a name="related-topics"></a>Verwandte Themen

[Konfigurieren von Konten für Zusammenarbeits leisten für Microsoft Teams mit Microsoft Teams Admin Center](resource-account-ui.md)

<!-- [Configure accounts for collaboration bars for Microsoft Teams using PowerShell](resource-account-ps.md) -->
