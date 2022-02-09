---
title: Planen der Medienumgehung in Skype for Business
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9ea090b3-f607-46f7-97dd-2510052524e5
description: Entscheidungen, die für die Planung der Medienumgehung in Skype for Business Server Enterprise-VoIP erforderlich sind. Umfasst die Interoperabilität mit der Anrufsteuerung (Call Admission Control, CAC).
ms.openlocfilehash: fe0d4910e2dacba99c066fe3dcdfe6fcd0f27c92
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2022
ms.locfileid: "62402769"
---
# <a name="plan-for-media-bypass-in-skype-for-business"></a>Planen der Medienumgehung in Skype for Business

Entscheidungen, die für die Planung der Medienumgehung in Skype for Business Server Enterprise-VoIP erforderlich sind. Umfasst die Interoperabilität mit der Anrufsteuerung (Call Admission Control, CAC).

Bei der Medienumgehung wird der Vermittlungsserver nach Möglichkeit für Anrufe aus dem Medienpfad entfernt, deren Signaldaten über den Vermittlungsserver verarbeitet werden.

Die Medienumgehung kann die Sprachqualität verbessern, indem die Latenz verringert, eine unnötige Übersetzung und Paketverluste verhindert sowie potenzielle Fehlerstellen minimiert werden. Der Vermittlungsserver muss für Anrufe mit Umgehung keine Mediendatenverarbeitung durchführen, sodass die Vermittlungsserverlast reduziert und die Skalierbarkeit verbessert wird. Diese Reduzierung der Last ergänzt die Fähigkeit des Vermittlungsservers, mehrere Gateways zu steuern.

 Wenn ein Zweigstellenstandort ohne Vermittlungsserver über eine oder mehrere WAN-Verbindungen mit beschränkter Bandbreite mit einem zentralen Standort verbunden ist, verringert die Medienumgehung die Bandbreitenanforderung, indem Medien von einem Client an einem Zweigstellenstandort direkt zu seinem lokalen Gateway fließen können, ohne zuerst über die WAN-Verbindung zu einem Vermittlungsserver am zentralen Standort und zurück fließen zu müssen.

Durch das Entfernen des Vermittlungsservers von der Medienverarbeitung kann die Medienumgehung auch die Anzahl der Vermittlungsserver verringern, die eine Enterprise-VoIP Infrastruktur erfordert. Allgemein gilt, dass die Medienumgehung wenn möglich aktiviert werden sollte.

Die folgende Abbildung zeigt grundlegende Pfade für Medien- und Signaldatenverkehr in Topologien mit und ohne Umgehung.

**Pfade für Medien- und Signaldatenverkehr mit und ohne Medienumgehung**

![Erzwingung der Verbindungserzwingung für die Anrufsteuerungs-Medienumgehung.](../../media/Plan_CS_VoiceCAC_enforcementofconnectionstoPSTN.jpg)

Die Medienumgehung ist nützlich, wenn Sie die Anzahl von bereitgestellten Vermittlungsservern reduzieren möchten. Üblicherweise wird ein Vermittlungsserverpool an einem zentralen Standort bereitgestellt und steuert die Gateways an den Zweigstellenstandorten. Durch Aktivierung der Medienumgehung können Mediendaten für PSTN-Anrufe (Telefonfestnetz) von Clients an Zweigstellenstandorten direkt durch die Gateways an diesen Standorten geleitet werden. Skype for Business Server Routen für ausgehende Anrufe und Enterprise-VoIP Richtlinien müssen ordnungsgemäß konfiguriert sein, damit PSTN-Anrufe von Clients an einem Zweigstellenstandort an das entsprechende Gateway weitergeleitet werden.

In Wi-Fi-Netzwerken treten üblicherweise mehr Paketverluste auf als in verkabelten Netzwerken. Die Wiederherstellung der Daten aus diesen Paketen kann normalerweise nicht mithilfe von Gateways durchgeführt werden. Daher wird empfohlen, die Qualität eines Wi-Fi-Netzwerks auszuwerten, bevor Sie entscheiden, ob die Medienumgehung für ein Funksubnetz aktiviert werden soll. Darüber hinaus muss erwogen werden, ob eine geringere Latenz zu Lasten der Dateiwiederherstellung nach Paketverlusten akzeptabel ist. RTAudio – ein Codec für Anrufe, die den Vermittlungsserver nicht umgehen – eignet sich besser für die Verarbeitung von Paketverlusten.

## <a name="planning-your-media-bypass-deployment"></a>Planen der Bereitstellung der Medienumgehung

Nachdem Ihre Enterprise-VoIP Struktur eingerichtet wurde, ist die Planung für die Medienumgehung einfach.

- Wenn Sie über eine zentralisierte Topologie ohne WAN-Verbindungen mit Zweigstellenstandorten verfügen, können Sie die globale Medienumgehung aktivieren, da eine genaue Steuerung nicht erforderlich ist.

- Wenn Sie dagegen eine verteilte Topologie mit mehreren Netzwerkregionen und zugehörigen Zweigstellenstandorten eingerichtet haben, müssen Sie sich die folgenden Fragen stellen:

  - Können die Vermittlungsserverpeers die für die Medienumgehung erforderlichen Funktionen unterstützen?

  - Welche Standorte in den jeweiligen Netzwerkregionen verfügen über eine gute Verbindung?

  - Welche Kombination aus Medienumgehung und Anrufsteuerung eignet sich für Ihr Netzwerk?

Wenn Sie die Medienumgehung aktivieren, wird automatisch eine eindeutige Umgehungs-ID für eine Netzwerkregion und für alle Netzwerkstandorte ohne Bandbreiteneinschränkungen innerhalb dieser Region generiert. Standorte mit Bandbreiteneinschränkungen innerhalb der Region und Standorte, die über WAN-Verbindungen mit Bandbreiteneinschränkungen mit der Region verbunden sind, erhalten jeweils eine eigene eindeutige Umgehungs-IDs.

Wenn ein Benutzer das PSTN aufruft, vergleicht der Vermittlungsserver die Umgehungs-ID des Clientsubnetzes mit der Umgehungs-ID des Gatewaysubnetzes. Wenn die beiden Umgehungs-IDs übereinstimmen, wird für den Anruf die Medienumgehung verwendet. Wenn die Umgehungs-IDs nicht übereinstimmen, müssen Medien für den Anruf über den Vermittlungsserver fließen.

Wenn ein Benutzer einen Anruf vom PSTN empfängt, vergleicht der Client des Benutzers seine Umgehungs-ID mit der des PSTN-Gateways. Wenn die beiden Umgehungs-IDs übereinstimmen, fließen die Medien direkt vom Gateway zum Client, wodurch der Vermittlungsserver umgangen wird.

Nur Lync 2010- oder neuere Clients und Geräte unterstützen Medienumgehungsinteraktionen mit einem Vermittlungsserver.

> [!IMPORTANT]
> Zusätzlich zur globalen Aktivierung der Medienumgehung müssen Sie die Medienumgehung auf jedem PSTN-Trunk einzeln aktivieren. Wenn die Umgehung zwar global, jedoch für einen bestimmten PSTN-Trunk nicht aktiviert wurde, wird sie für Anrufe über diesen PSTN-Trunk nicht ausgelöst. Darüber hinaus müssen Sie alle routingfähigen Subnetze den Standorten zuordnen, in denen sie sich befinden, wenn die Medienumgehung auf **Informationen zu Standort und Region verwenden** festgelegt ist. Routingfähige Subnetze in einem Standort, für den eine Medienumgehung nicht gewünscht wird, sollten vor Aktivierung der Umgehung in einem neuen Standort gruppiert werden. Auf diese Weise stellen Sie sicher, dass den nicht routingfähigen Subnetzen eine andere Umgehungs-ID zugewiesen wird.

## <a name="media-bypass-modes"></a>Medienumgehungsmodi

Sie müssen die Medienumgehung sowohl global als auch für jeden einzelnen PSTN-Trunk konfigurieren. Wenn Sie die Medienumgehung global aktivieren, haben Sie die Auswahl zwischen zwei Optionen: **Immer umgehen** und **Informationen zu Standort und Region verwenden**.

Wie der Name vermuten lässt, wird die Medienumgehung bei Auswahl von **Immer umgehen** auf alle PSTN-Anrufe angewendet. **Immer umgehen** wird in Bereitstellungen verwendet, in denen weder eine Anrufsteuerung noch die Bereitstellung detaillierter Konfigurationsinformationen für die Medienumgehung erforderlich ist. Darüber hinaus wird die Option **Immer umgehen** verwendet, wenn vollständige Konnektivität zwischen Clients und PSTN-Gateways gegeben ist. In dieser Konfiguration sind alle Subnetze einer einzigen ID für die Umgehung zugeordnet, die durch das System berechnet wird.

Bei Auswahl der Option **Informationen zu Standort und Region verwenden** werden Entscheidungen zur Medienumgehung anhand der ID für die Umgehung und der zugeordneten Standort- und Regionenkonfiguration getroffen. Diese Konfiguration bietet die Flexibilität, die Medienumgehung für die gängigsten Topologien zu konfigurieren, da einerseits genau gesteuert werden kann, wann eine Umgehung stattfindet, und andererseits eine Interaktion mit der Anrufsteuerung unterstützt wird. Das System versucht, diese Aufgabe zu vereinfachen, indem automatisch IDs für die Umgehung zugewiesen werden:

- Das System weist jeder Region eine einzelne, eindeutige ID für die Umgehung zu.

- Jeder Standort, der über eine WAN-Verbindung ohne Bandbreiteneinschränkungen mit einer Region verbunden ist, erbt dieselbe Umgehungs-ID wie die Region.

- Einem Standort, der über eine WAN-Verbindung mit Bandbreiteneinschränkungen mit der Region verbunden ist, wird eine andere ID für die Umgehung zugewiesen als der Region.

- Die jedem Standort zugeordneten Subnetze erben die Umgehungs-ID für diesen Standort.

## <a name="media-bypass-and-call-admission-control"></a>Medienumgehung und Anrufsteuerung

Medienumgehung und Anrufsteuerung (Call Admission Control, CAC) arbeiten zusammen, um eine Bandbreitensteuerung für den Mediendatenverkehr bei Anrufen zu erzielen.  Die Medienumgehung fördert den Mediendatenfluss über Leitungen mit guter Konnektivität; die Anrufsteuerung verwaltet den Datenverkehr für Verbindungen mit Bandbreiteneinschränkungen. Da Medienumgehung und Anrufsteuerung sich gegenseitig ausschließen, müssen Sie bei der Planung die jeweils andere Funktion berücksichtigen. Die folgenden Kombinationen werden unterstützt:

- Sowohl Anrufsteuerung als auch Medienumgehung sind aktiviert. Die Medienumgehung muss auf **Informationen zu Standort und Region verwenden** festgelegt sein. Die Informationen zu Standort und Region sind dieselben wie für die Anrufsteuerung.

    Wenn Sie die Anrufsteuerung aktivieren, können Sie die Option **Immer umgehen** nicht auswählen (und umgekehrt), da die zwei Konfigurationen sich gegenseitig ausschließen. Dies bedeutet, dass jeweils nur eine der zwei Optionen auf einen PSTN-Anruf angewendet wird. Zunächst wird überprüft, ob für den Anruf die Medienumgehung gilt. Ist dies der Fall, wird die Anrufsteuerung nicht verwendet. Dies ist plausibel, da ein für die Medienumgehung aktivierter Anruf per Definition eine Verbindung verwendet, für die eine Anrufsteuerung nicht notwendig ist. Wenn die Umgehung nicht auf den Anruf angewendet werden kann (d. h. wenn die Umgehungs-IDs des Clients und des Gateways nicht übereinstimmen), wird die Anrufsteuerung auf den Anruf angewendet.

- Die Anrufsteuerung ist nicht aktiviert, und die Medienumgehung ist auf **Immer umgehen** festgelegt.

    In dieser Konfiguration sind sowohl Client- als auch Trunksubnetze einer einzigen ID für die Umgehung zugeordnet, die durch das System berechnet wird.

- Die Anrufsteuerung ist nicht aktiviert, und die Medienumgehung ist auf **Informationen zu Standort und Region verwenden** festgelegt.

    Wenn die Option **Informationen zu Standort und Region verwenden** aktiviert ist, funktioniert die Umgehungsermittlung im Prinzip in gleicher Weise – unabhängig davon, ob die Anrufsteuerung aktiviert ist oder nicht. Das heißt, bei einem bestimmten PSTN-Anruf wird das Subnetz des Clients einem bestimmten Standort zugeordnet, und die Umgehungs-ID für dieses Subnetz wird extrahiert. Ebenso wird das Subnetz des Gateways einem bestimmten Standort zugeordnet, und die Umgehungs-ID für dieses Subnetz wird extrahiert. Nur wenn die zwei Umgehungs-IDs identisch sind, findet eine Medienumgehung für den Anruf statt. Unterscheiden sich die IDs, findet keine Medienumgehung statt.

    Selbst wenn die Anrufsteuerung global deaktiviert wurde, müssen Bandbreitenrichtlinien für jeden Standort und jede Verbindung definiert werden, wenn die Konfiguration von Standorten und Regionen für Entscheidungen zur Medienumgehung herangezogen werden soll. Der tatsächliche Wert der Bandbreiteneinschränkung oder die Modalität spielt keine Rolle. Das Ziel besteht darin, dass das System automatisch unterschiedliche Umgehungs-IDs berechnet, die verschiedenen Standorten ohne gute Verbindung zugeordnet sind. Das Definieren einer Bandbreiteneinschränkung bedeutet per Definition, dass eine Verbindung keine gute Konnektivität aufweist.

- Weder die Anrufsteuerung noch die Medienumgehung sind aktiviert. Dieser Fall tritt nur ein, wenn alle Gateways und IP-Nebenstellenanlagen über Leitungen mit geringer Konnektivität verbunden sind oder andere Anforderungen für die Medienumgehung nicht erfüllen. Ausführliche Informationen zu den Anforderungen für die Medienumgehung finden Sie unter [Requirements for Media Bypass](/previous-versions/office/lync-server-2013/lync-server-2013-technical-requirements-for-media-bypass).

## <a name="technical-requirements"></a>Technische Anforderungen

Für jeden Anruf an das PSTN bestimmt der Vermittlungsserver, ob Medien vom Skype for Business Ursprungsendpunkt direkt an einen Vermittlungsserverpeer gesendet werden können, ohne den Vermittlungsserver zu durchlaufen. Der Peer kann ein PSTN-Gateway, eine IP-Nebenstellenanlage oder ein SBC (Session Border Controller) bei einem Anbieter von Internettelefoniediensten sein, der zu der Leitung zwischen dem Vermittlungsserver gehört, bei dem der Anruf weitergeleitet wird.

Die Medienumgehung kann implementiert werden, wenn die folgenden Voraussetzungen erfüllt sind:

- Ein Vermittlungsserverpeer muss die erforderlichen Funktionen für die Medienumgehung unterstützen. Die wichtigste ist die Möglichkeit, mehrere gegabelungene Antworten zu verarbeiten (auch als "frühe Dialogfelder" bezeichnet). Wenden Sie sich an den Hersteller Ihres Gateways, Ihrer Nebenstellenanlage oder Ihres ANBIETERs, um den Wert für die maximale Anzahl von frühzeitigen Dialogfeldern zu erhalten, die das Gateway, die Nebenstellenanlage oder der SBC akzeptieren kann.

- Der Vermittlungsserverpeer muss Mediendatenverkehr direkt von Skype for Business Endpunkten akzeptieren. Viele ITSPs ermöglichen es ihrem SBC, Nur-Datenverkehr vom Vermittlungsserver zu empfangen. Wenden Sie sich an Ihren ItsP, um festzustellen, ob der SBC Mediendatenverkehr direkt von Skype for Business Endpunkten akzeptiert.

- Skype for Business Clients und ein Vermittlungsserverpeer müssen gut verbunden sein, d. h., sie befinden sich entweder in derselben Netzwerkregion oder an Netzwerkstandorten, die über WAN-Verbindungen eine Verbindung mit der Region herstellen, die keine Bandbreiteneinschränkungen aufweisen