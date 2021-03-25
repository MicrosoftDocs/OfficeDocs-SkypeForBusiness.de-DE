---
title: Bereitstellen von Microsoft Teams Rooms unter Android
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
description: In diesem Artikel erfahren Sie mehr über die Bereitstellung von Microsoft Teams Rooms unter Android.
ms.openlocfilehash: 3da0192ee3676f5ff7294ba719c778ea7b1cc7b2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120797"
---
# <a name="deploy-microsoft-teams-rooms-on-android"></a>Bereitstellen von Microsoft Teams Rooms unter Android

Die Bereitstellung von Microsoft Teams Rooms unter Android kann in die folgenden Phasen aufschlüsselt werden:

- **Websitebereitschaft** Vergewissern Sie sich, dass Ihre Bereitstellungsstandorte (Räume) die Bereitstellungsanforderungen erfüllen.
- **Dienstbereitschaft** Erstellen Sie Ressourcenkonten, und weisen Sie sie den Geräten zu (siehe Erstellen eines [Ressourcenkontos im Microsoft 365 Admin Center](resource-account-ui.md)). Während wir die Verwendung einer dedizierten Raumlizenz empfehlen, kann sich ein ordnungsgemäß lizenziertes Endbenutzerkonto auch bei Teams Rooms unter Android anmelden.
- **Konfiguration und Bereitstellung** Richten Sie Teams Rooms ein, und schließen Sie die benötigten Peripheriegeräte an (ausführliche Informationen finden Sie in der Dokumentation des Herstellers).

Zum Verwalten von Teams Rooms müssen Sie globaler Administrator, Teamdienstadministrator oder Teamgeräteadministrator sein. Weitere Informationen zu Administratorrollen finden Sie unter [Verwenden von Microsoft Teams-Administratorrollen zum Verwalten von Teams.](../using-admin-roles.md)

## <a name="site-readiness"></a>Websitebereitschaft

Während die bestellten Geräte an Ihre Organisation geliefert werden, arbeiten Sie mit Ihren Netzwerken, Einrichtungen und audiovisuellen Teams zusammen, um sicherzustellen, dass die Bereitstellungsanforderungen erfüllt sind und jede Website und jeder Raum hinsichtlich Leistung, Netzwerk und Anzeige bereit ist.

Unsere Empfehlungen für Websites für Die Zusammenarbeitsleisten sind:

- Räume mit einer Größe von bis zu 5 Personen
- Dedizierte Ressourcenkonten
- Bildschirme mit Touch-Aktiviert
- Ethernetverkabelung
- Quality of Service (QoS) im Netzwerk für Microsoft Teams-Medien aktiviert

Überlegungen zur physischen Installation finden Sie in der Dokumentation des Herstellers, und nutzen Sie, falls vorhanden, die Erfahrung Ihres audio-visuellen Teams, bevor Sie Bildschirme installieren und installieren und kabeln.

> [!TIP]
> Achten Sie darauf, ihr Netzwerk für [Teams](../prepare-network.md) für die Bandbreitenplanung vorzubereiten und die Eignung Ihres Netzwerks für den Echtzeitdatenverkehr zu bewerten.
>
> Es wird nicht empfohlen, Proxyserver zwischen Teams-Geräten und dem Internet zu platzieren. Weitere Informationen zu Proxyservern und Teams finden Sie unter [Proxyserver für Teams.](../proxy-servers-for-skype-for-business-online.md)

|    |     |
|-----------|------------|
| ![Ein Symbol mit Entscheidungspunkten](../media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Vergewissern Sie sich, dass Ihre Websites die Anforderungen an die Websitebereitschaft für Die Zusammenarbeitsbalken für Microsoft Teams erfüllen.</li><li>Vergewissern Sie sich, dass Sie für jede Website eine ausreichende Bandbreite bereitgestellt haben.</li></ul>|
| ![Ein Symbol mit den nächsten Schritten](../media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Beginnen Sie mit der Planung der Bereitstellung und Konfiguration der Zusammenarbeitsleiste.</li></ul>|

## <a name="service-readiness"></a>Bereitschaft für den Dienst

Bevor Sie Teams Rooms bereitstellen, müssen Sie entscheiden, ob sie Microsoft 365-Ressourcenkonten, Endbenutzerkonten oder eine Mischung aus beidem verwenden. Microsoft 365-Ressourcenkonten sind Postfach- und Teams-Konten, die bestimmten Ressourcen zugeordnet sind, z. B. einem Raum, einem Projektor und so weiter. Diese Ressourcenkonten können mithilfe von Regeln, die Sie beim Erstellen definieren, automatisch auf Besprechungs einladen reagieren. Es sei denn, Teams Rooms ist einer bestimmten Person für die private Verwendung gewidmet, wir empfehlen die Einrichtung eines Microsoft 365-Ressourcenkontos dafür.

### <a name="using-a-resource-account"></a>Verwenden eines Ressourcenkontos

Wenn Sie sich für die Einrichtung eines Microsoft 365-Ressourcenkontos entscheiden, müssen Sie eine Lizenz für den Besprechungsraum erwerben. Die Lizenz für den Besprechungsraum enthält ein Ressourcenpostfach, mit dem Personen in Ihrer Organisation den Besprechungsraum über Outlook oder Teams buchen können. Die Lizenz ermöglicht auch Video- und Audiokonferenzen sowie die Bildschirmfreigabe zwischen Besprechungsteilnehmern.

Wenn Sie Anrufe an eine externe Telefonnummer oder von einer externen Telefonnummer empfangen oder anrufen müssen, benötigen Sie möglicherweise eine Anrufplan- oder Microsoft 365 Business [Voice-Add-On-Lizenz.](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md?tabs=small-business) Wenn Sie direct routing in Ihrer Organisation aktiviert haben, benötigen Sie nur die Besprechungsraum-SKU.

Wenn Sie ein Ressourcenkonto erstellen, können Sie auswählen, ob das Konto Besprechungsanfragen automatisch annehmen oder ablehnen, besprechungsserien zulassen, angeben soll, wie weit im Voraus Personen die Ressource buchen können, und so weiter.

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

Weitere Informationen zu Microsoft 365-Ressourcenkonten finden Sie unter Erstellen eines Ressourcenkontos mit [dem Microsoft 365 Admin Center.](resource-account-ui.md)

|    |     |
|-----------|------------|
| ![Ein Symbol mit Entscheidungspunkten](../media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Entscheiden Sie, ob Sie externe Telefonanrufe machen oder empfangen möchten, und ermitteln Sie die Lizenzierungsanforderungen für Ihre Ressourcenkonten.</li></ul>|
| ![Ein Symbol mit den nächsten Schritten](../media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Vorbereiten von Ressourcenkonten</li></ul>|

## <a name="configuration-and-deployment"></a>Konfiguration und Bereitstellung

Die Planung der Konfiguration und Bereitstellung umfasst die folgenden Schlüsselbereiche:

- Ressourcenkontobereitstellung
- Gerätebereitstellung
- Konfiguration von Anwendungen und Peripheriegeräten in Teams Rooms
-  Tests
- Ressourcenverwaltung

### <a name="account-provisioning"></a>Kontobereitstellung

Wenn Sie microsoft 365-Ressourcenkonten verwenden möchten, um Benutzern das Buchen von Zusammenarbeitsbalken zu ermöglichen, folgen Sie den Anweisungen unter Erstellen eines Ressourcenkontos im [Microsoft 365 Admin Center,](resource-account-ui.md) um ein Microsoft 365-Ressourcenkonto für jede Zusammenarbeitsleiste zu erstellen, die eins benötigt. Hier müssen Sie dem Ressourcenkonto auch eine Lizenz für den Besprechungsraum hinzufügen und, wenn Sie Anrufe an oder von externen Telefonnummern empfangen möchten, eine Anrufplan- oder Business Voice-Lizenz, wenn Ihre Organisation kein Direktes Routing verwendet.

Wenn Sie teams rooms einzelnen Benutzern zur privaten Nutzung zuweisen möchten, müssen Sie keine zusätzlichen Konten einrichten. Benutzer können sich mit ihren persönlichen Konten bei Denkleisten anmelden.

> [!TIP]
> Machen Sie die Anzeigenamen für Ihre Microsoft 365-Ressourcenkonten beschreibend und leicht verständlich. Dies sind die Namen, die Benutzern beim Suchen nach und Hinzufügen von Teams-Räumen zu Besprechungen angezeigt werden. Sie können eine Konvention wie Websiteraumname ( Max. Raumkapazität) verwenden, sodass z. B. - Curie, ein 4-Personen-Besprechungsraum in London, den Anzeigenamen LON-CURIE(4) haben könnte.

|    |     |
|-----------|------------|
| ![Ein Symbol mit Entscheidungspunkten](../media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Entscheiden Sie die Benennungskonvention für Ihre dedizierten Ressourcenkonten.</li><li>Entscheiden Sie, ob Sie einzelne Konten erstellen oder Massenbereitstellungsskripts verwenden.</li></ul>|
| ![Ein Symbol mit den nächsten Schritten](../media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Beginnen Sie mit der Planung der Gerätebereitstellung.</li></ul>|

### <a name="device-deployment"></a>Gerätebereitstellung

Als Nächstes müssen Sie Ihren Plan erstellen, um die Geräte und die zugewiesenen Peripheriegeräte in Ihre Räume zu liefern, und dann mit der Installation und Konfiguration fortfahren.

|    |     |
|-----------|------------|
| ![Ein Symbol mit Entscheidungspunkten](../media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Entscheiden Sie, wer die Bereitstellung von Website zu Website verwaltet.</li><li> Ermitteln Sie die Ressourcen, die Teams Rooms auf der Website installieren und die Konfiguration und tests durchführen.</li></ul>|
| ![Ein Symbol mit den nächsten Schritten](../media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Starten Sie den Gerätetest.</li></ul>|

### <a name="testing"></a> Tests

Nachdem Sie Teams Rooms bereitgestellt haben, sollten Sie sie testen. Melden Sie sich bei Teams Rooms an, und überprüfen Sie, ob die erwarteten Funktionen funktionieren. Es wird dringend empfohlen, zu überprüfen,  ob sie  im Abschnitt Zusammenarbeitsbalken unter der Registerkarte Geräte im Microsoft Teams Admin Center angezeigt werden. Außerdem ist es wichtig, dass Sie eine Reihe von Testanrufen und Besprechungen führen, um die Qualität und Leistung zu überprüfen.

Es wird empfohlen, im Rahmen des allgemeinen Microsoft Teams-Rollouts Die Gebäudedateien für das Anrufqualitätsdashboard (CQD) zu konfigurieren, Qualitätstrends zu überwachen und sich am Überprüfungsprozess für die Qualität der Benutzererfahrung zu beteiligen. Weitere Informationen finden Sie im Handbuch zur Überprüfung der [Qualität der Benutzererfahrung](../quality-of-experience-review-guide.md).

### <a name="asset-management"></a>Ressourcenverwaltung

Im Rahmen der Bereitstellung möchten Sie Ihr Ressourcenregister mit dem Raumnamen, dem angemeldeten Ressourcenkonto und den zugewiesenen Peripheriegeräten aktualisieren.

## <a name="related-topics"></a>Verwandte Themen

[Konfigurieren von Konten für Microsoft Teams Rooms mithilfe des Microsoft Teams Admin Centers](resource-account-ui.md)

<!-- [Configure accounts for collaboration bars for Microsoft Teams using PowerShell](resource-account-ps.md) -->