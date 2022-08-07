---
title: Bereitstellen von Microsoft Teams-Räume unter Android
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: payurevi
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Devices
ms.custom: ''
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: Lesen Sie diesen Artikel, um mehr über die Bereitstellung von Microsoft Teams-Räume unter Android zu erfahren.
ms.openlocfilehash: f5f49a7e461153d24837d28d7160a475e4992eba
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2022
ms.locfileid: "67267810"
---
# <a name="deploy-microsoft-teams-rooms-on-android"></a>Bereitstellen von Microsoft Teams-Räume unter Android

Die Bereitstellung von Microsoft Teams-Räume unter Android kann in die folgenden Phasen unterteilt werden:

- **Websitebereitschaft** Vergewissern Sie sich, dass Ihre Bereitstellungsspeicherorte (Räume) die Bereitstellungsanforderungen erfüllen.
- **Dienstbereitschaft** Erstellen Sie Ressourcenkonten, und weisen Sie sie den Geräten zu ([siehe Erstellen eines Ressourcenkontos mithilfe der Microsoft 365 Admin Center](resource-account-ui.md)). Während wir empfehlen, eine dedizierte Raumlizenz zu verwenden, kann sich ein ordnungsgemäß lizenziertes Endbenutzerkonto auch bei Teams-Räume unter Android anmelden.
- **Konfiguration und Bereitstellung** Richten Sie Teams-Räume ein und schließen Sie die benötigten Peripheriegeräte an (ausführliche Informationen finden Sie in der Dokumentation des Herstellers).

Um Teams-Räume zu verwalten, müssen Sie ein globaler Administrator, Teams-Dienstadministrator oder Teams-Geräteadministrator sein. Weitere Informationen zu Administratorrollen finden Sie unter [Verwenden von Microsoft Teams-Administratorrollen zum Verwalten von Teams](../using-admin-roles.md).

## <a name="site-readiness"></a>Websitebereitschaft

Während die bestellten Geräte an Ihre Organisation geliefert werden, arbeiten Sie mit Ihren Netzwerken, Einrichtungen und audio-visuellen Teams zusammen, um sicherzustellen, dass die Bereitstellungsanforderungen erfüllt sind und jeder Standort und Raum in Bezug auf Leistung, Netzwerk und Anzeige bereit ist.

Unsere Empfehlungen für Websites für Die Zusammenarbeitsleisten lauten:

- Zimmer mit einer Größe von bis zu 5 Personen
- Dedizierte Ressourcenkonten
- Bildschirme mit Toucheingabe
- Ethernet-Verkabelung
- Quality of Service (QoS) aktiviert im Netzwerk für Microsoft Teams-Medien

Überlegungen zur physischen Installation finden Sie in der Dokumentation des Herstellers, und nutzen Sie bei Bedarf die Erfahrung Ihres audio-visuellen Teams, bevor Sie Bildschirme installieren und einbinden und Verkabelungen ausführen.

> [!TIP]
> Sehen Sie sich unbedingt ["Vorbereiten Ihres Netzwerks für Teams" für](../prepare-network.md) die Bandbreitenplanung und die Bewertung der Eignung Ihres Netzwerks für Echtzeitdatenverkehr an.
>
> Es wird nicht empfohlen, Proxyserver zwischen Teams-Geräten und dem Internet zu platzieren. Weitere Informationen zu Proxyservern und Teams finden Sie unter [Proxyserver für Teams](../proxy-servers-for-skype-for-business-online.md).

|&nbsp;|&nbsp;|
|-----------|------------|
| ![Ein Symbol, das Entscheidungspunkte darstellt.](../media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Vergewissern Sie sich, dass Ihre Websites die Anforderungen an die Websitebereitschaft für Zusammenarbeitsleisten für Microsoft Teams erfüllen.</li><li>Vergewissern Sie sich, dass Sie für jeden Standort ausreichende Bandbreite bereitgestellt haben.</li></ul>|
| ![Ein Symbol, das die nächsten Schritte darstellt.](../media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Beginnen Sie mit der Planung der Bereitstellung und Konfiguration der Zusammenarbeitsleiste.</li></ul>|

## <a name="service-readiness"></a>Bereitschaft für den Dienst

Bevor Sie Teams-Räume bereitstellen, müssen Sie entscheiden, ob diese Microsoft 365-Ressourcenkonten, Endbenutzerkonten oder eine Mischung aus beidem verwenden. Microsoft 365-Ressourcenkonten sind Postfach- und Teams-Konten, die bestimmten Ressourcen zugeordnet sind, z. B. einem Raum, Projektor usw. Diese Ressourcenkonten können automatisch mithilfe von Regeln, die Sie beim Erstellen definieren, auf Besprechungseinladungen reagieren. Sofern Teams-Räume nicht einer bestimmten Person für die private Nutzung gewidmet ist, empfehlen wir, dafür ein Microsoft 365-Ressourcenkonto einzurichten.

### <a name="using-a-resource-account"></a>Verwenden eines Ressourcenkontos

Wenn Sie ein Microsoft 365-Ressourcenkonto einrichten möchten, müssen Sie dafür eine Besprechungsraumlizenz erwerben. Die Besprechungsraumlizenz enthält ein Ressourcenpostfach, mit dem Personen in Ihrer Organisation den Besprechungsraum über Outlook oder Teams buchen können. Die Lizenz ermöglicht auch Video- und Audiokonferenzen sowie die Bildschirmfreigabe unter den Besprechungsteilnehmern.

Wenn Sie Anrufe an oder von einer externen Telefonnummer empfangen oder tätigen müssen, benötigen Sie möglicherweise einen Anrufplan oder Microsoft 365 Business Voice [Add-On-Lizenz](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md?tabs=small-business). Wenn Direct Routing in Ihrer Organisation aktiviert ist, benötigen Sie nur die SKU des Besprechungsraums.

Wenn Sie ein Ressourcenkonto erstellen, können Sie auswählen, ob das Konto Besprechungsanfragen automatisch annehmen oder ablehnen, Besprechungsserien zulassen, angeben, wie weit im Voraus Personen die Ressource buchen können usw.

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

Weitere Informationen zu Microsoft 365-Ressourcenkonten finden Sie unter [Erstellen eines Ressourcenkontos mithilfe der Microsoft 365 Admin Center](resource-account-ui.md).

|&nbsp;|&nbsp;|
|-----------|------------|
| ![Ein Symbol, das Entscheidungspunkte darstellt.](../media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Entscheiden Sie, ob Sie externe Telefonanrufe tätigen oder empfangen möchten, und ermitteln Sie die Lizenzierungsanforderungen für Ihre Ressourcenkonten.</li></ul>|
| ![Ein Symbol, das die nächsten Schritte darstellt.](../media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Vorbereiten von Ressourcenkonten.</li></ul>|

## <a name="configuration-and-deployment"></a>Konfiguration und Bereitstellung

Die Planung der Konfiguration und Bereitstellung umfasst die folgenden Schlüsselbereiche:

- Ressourcenkontobereitstellung
- Gerätebereitstellung
- Teams-Räume Der Anwendungs- und Peripheriegerätekonfiguration
-  Tests
- Ressourcenverwaltung

### <a name="account-provisioning"></a>Kontobereitstellung

Wenn Sie die Verwendung von Microsoft 365-Ressourcenkonten planen, damit Benutzer Zusammenarbeitsleisten buchen können, befolgen Sie die Anweisungen unter [Erstellen eines Ressourcenkontos mithilfe der Microsoft 365 Admin Center](resource-account-ui.md), um ein Microsoft 365-Ressourcenkonto für jede Zusammenarbeitsleiste zu erstellen, die eines benötigt. Hier müssen Sie dem Ressourcenkonto auch eine Besprechungsraumlizenz hinzufügen und, wenn Sie Anrufe an oder von externen Telefonnummern empfangen möchten, einen Anrufplan oder eine Business Voice-Lizenz, wenn Ihre Organisation direct Routing nicht verwendet.

Wenn Sie einzelnen Benutzern für die private Nutzung Teams-Räume zuweisen möchten, müssen Sie keine zusätzlichen Konten einrichten. Benutzer können sich mit ihren persönlichen Konten bei Denkleisten für die Zusammenarbeit anmelden.

> [!TIP]
> Gestalten Sie die Anzeigenamen für Ihre Microsoft 365-Ressourcenkonten beschreibend und leicht verständlich. Dies sind die Namen, die Benutzern angezeigt werden, wenn sie nach Besprechungen suchen und Teams-Räume hinzufügen. Sie könnten eine Konvention wie *"Site*-*Room Name*(*Max Room Capacity*)" verwenden, sodass z. B. Curie, ein 4-Personen-Besprechungsraum in London, den Anzeigenamen LON-CURIE(4) aufweisen könnte.

|&nbsp;|&nbsp;|
|-----------|------------|
| ![Ein Symbol, das Entscheidungspunkte darstellt.](../media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Legen Sie die Benennungskonvention für Ihre dedizierten Ressourcenkonten fest.</li><li>Entscheiden Sie, ob Sie einzelne Konten erstellen oder Massenbereitstellungsskripts verwenden möchten.</li></ul>|
| ![Ein Symbol, das die nächsten Schritte darstellt.](../media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Beginnen Sie mit der Planung der Gerätebereitstellung.</li></ul>|

### <a name="device-deployment"></a>Gerätebereitstellung

Als Nächstes müssen Sie Ihren Plan erstellen, um die Geräte und deren zugewiesene Peripheriegeräte an Ihre Räume zu liefern, und dann mit der Installation und Konfiguration fortfahren.

|&nbsp;|&nbsp;|
|-----------|------------|
| ![Ein Symbol, das Entscheidungspunkte darstellt.](../media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Entscheiden Sie, wer die Bereitstellung von Standort zu Standort verwaltet.</li><li> Identifizieren Sie die Ressourcen, die Teams-Räume vor Ort installieren und die Konfiguration und tests durchführen.</li></ul>|
| ![Ein Symbol, das die nächsten Schritte darstellt.](../media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Starten Sie Gerätetests.</li></ul>|

### <a name="testing"></a> Tests

Nachdem Sie Teams-Räume bereitgestellt haben, sollten Sie sie testen. Melden Sie sich bei Teams-Räume an, und überprüfen Sie, ob die erwarteten Funktionen funktionieren. Es wird dringend empfohlen, dass Sie überprüfen, ob sie im Abschnitt **"Zusammenarbeitsleisten** " auf der Registerkarte " **Teams-Geräte** " im Microsoft Teams Admin Center angezeigt werden. Es ist auch wichtig, dass Sie eine Reihe von Testanrufen und Besprechungen durchführen, um die Qualität und Leistung zu überprüfen.

Es wird empfohlen, dass Sie im Rahmen des allgemeinen Microsoft Teams-Rollouts die Erstellung von Dateien für das Anrufqualitätsdashboard (Call Quality Dashboard, CQD) konfigurieren, Qualitätstrends überwachen und sich an der Überprüfung der Qualität der Erfahrung beteiligen. Weitere Informationen finden Sie im [Leitfaden zur Überprüfung der Qualität der Erfahrung](../quality-of-experience-review-guide.md).

### <a name="asset-management"></a>Ressourcenverwaltung

Im Rahmen der Bereitstellung sollten Sie Ihr Bestandsregister mit dem Raumnamen, dem angemeldeten Ressourcenkonto und den zugewiesenen Peripheriegeräten aktualisieren.

## <a name="related-topics"></a>Verwandte Themen

[Erstellen von Ressourcenkonten für Räume und freigegebene Teams-Geräte](../rooms/with-office-365.md)