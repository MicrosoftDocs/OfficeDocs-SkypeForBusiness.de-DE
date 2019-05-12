---
title: Planen der medienumgehung in Skype für Unternehmen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9ea090b3-f607-46f7-97dd-2510052524e5
description: Umgehen der Entscheidungen zur Planung für Medien in Skype für Business Server Enterprise-VoIP. Hierzu gehört die Interoperationalität mit Anrufsteuerung (CAC, call admission control).
ms.openlocfilehash: 11631fb92d8e1763bb4e7d090caf54385527c984
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924157"
---
# <a name="plan-for-media-bypass-in-skype-for-business"></a>Planen der medienumgehung in Skype für Unternehmen

Umgehen der Entscheidungen zur Planung für Medien in Skype für Business Server Enterprise-VoIP. Hierzu gehört die Interoperationalität mit Anrufsteuerung (CAC, call admission control).

Die medienumgehung wird der Vermittlungsserver aus dem Medienpfad nach Möglichkeit für Anrufe, deren Signaldaten über den Vermittlungsserver durchläuft.

Die Medienumgehung kann die Sprachqualität verbessern, indem die Latenz verringert, eine unnötige Übersetzung und Paketverluste verhindert sowie potenzielle Fehlerstellen minimiert werden. Skalierbarkeit kann verbessert werden, da die Last auf dem Vermittlungsserver verringert die Vermeidung von Medien für umgangener Anrufe verarbeiten. Diese Verringerung der Last ergänzt die Steuerung des Vermittlungsservers mehrere Gateways.

 Bei einem Zweigstellenstandort ohne einen Vermittlungsserver über eine oder mehrere WAN-Verbindungen mit bandbreiteneinschränkungen mit einem zentralen Standort verbunden ist, senkt die medienumgehung Bandbreite durch Medien von einem Client an einem Zweigstellenstandort direkt an die lokalen Gateway ohne Fluss zulassen Zuerst müssen über das WAN flow link zu einem Vermittlungsserver am zentralen Standort und dann wieder.

Mediendaten Verarbeiten der Vermittlungsserver, kann die medienumgehung auch die Anzahl der Vermittlungsserver reduziert, die eine Enterprise-VoIP-Infrastruktur erforderlich sind. Generell gilt, dass die Medienumgehung möglichst immer aktiviert werden sollte.

Die folgende Abbildung zeigt grundlegende Pfade für Medien- und Signaldatenverkehr in Topologien mit und ohne Umgehung.

**Pfade für Medien- und Signaldatenverkehr mit und ohne Medienumgehung**

![VoIP CAC Medienumgehung – Verbindungserzwingung](../../media/Plan_CS_VoiceCAC_enforcementofconnectionstoPSTN.jpg)

Die medienumgehung ist nützlich, wenn minimieren Sie die Anzahl der Vermittlungsserver bereitgestellt werden soll. In der Regel wird ein vermittlungsserverpool an einem zentralen Standort bereitgestellt werden, und es wird Gateways an Zweigniederlassungen steuern. Durch Aktivierung der Medienumgehung können Mediendaten für PSTN-Anrufe (Telefonfestnetz) von Clients an Zweigstellenstandorten direkt durch die Gateways an diesen Standorten geleitet werden. Skype für Enterprise-VoIP-Richtlinien und Routen für ausgehende Anrufe Business Server muss ordnungsgemäß konfiguriert sein, damit die PSTN-Anrufe von Clients an einem Zweigstellenstandort an das entsprechende Gateway weitergeleitet werden.

In Wi-Fi-Netzwerken treten üblicherweise mehr Paketverluste auf als in verkabelten Netzwerken. Die Wiederherstellung der Daten aus diesen Paketen kann normalerweise nicht mithilfe von Gateways durchgeführt werden. Daher wird empfohlen, die Qualität eines Wi-Fi-Netzwerks auszuwerten, bevor Sie entscheiden, ob die Medienumgehung für ein Funksubnetz aktiviert werden soll. Darüber hinaus muss erwogen werden, ob eine geringere Latenz zu Lasten der Dateiwiederherstellung nach Paketverlusten akzeptabel ist. RTAudio - ein Codec für Anrufe, die den Vermittlungsserver nicht umgehen - eignet sich besser für die Verarbeitung von Paketverlusten.

## <a name="planning-your-media-bypass-deployment"></a>Planen der Bereitstellung des Media bypass

Nachdem die Enterprise-VoIP-Struktur eingerichtet ist, ist für die medienumgehung die Planung recht einfach.

- Wenn Sie über eine zentralisierte Topologie ohne WAN-Verbindungen mit Zweigstellenstandorten verfügen, können Sie die globale Medienumgehung aktivieren, da eine genaue Steuerung nicht erforderlich ist.

- Wenn Sie dagegen eine verteilte Topologie mit mehreren Netzwerkregionen und zugehörigen Zweigstellenstandorten eingerichtet haben, müssen Sie sich die folgenden Fragen stellen:

  - Können die Vermittlungsserverpeers die für die Medienumgehung erforderlichen Funktionen unterstützen?

  - Welche Standorte in den jeweiligen Netzwerkregionen verfügen über eine gute Verbindung?

  - Welche Kombination aus Medienumgehung und Anrufsteuerung eignet sich für Ihr Netzwerk?

Wenn Sie die Medienumgehung aktivieren, wird automatisch eine eindeutige Umgehungs-ID für eine Netzwerkregion und für alle Netzwerkstandorte ohne Bandbreiteneinschränkungen innerhalb dieser Region generiert. Standorte mit Bandbreiteneinschränkungen innerhalb der Region und Standorte, die über WAN-Verbindungen mit Bandbreiteneinschränkungen mit der Region verbunden sind, erhalten jeweils eine eigene eindeutige Umgehungs-IDs.

Wenn ein Benutzer einen Anruf an das Telefonfestnetz ernannt werden, werden der Vermittlungsserver die umgehungs-ID des Clientsubnetzes mit dem umgehungs-ID des Subnetzes Gateway verglichen. Wenn die beiden Umgehungs-IDs übereinstimmen, wird für den Anruf die Medienumgehung verwendet. Wenn die Umgehung IDs nicht übereinstimmen, muss das medienfluss für den Anruf über den Vermittlungsserver.

Wenn ein Benutzer einen Anruf über das PSTN empfängt, vergleicht der Client des Benutzers die umgehungs-ID an der PSTN-Gateway. Wenn die beiden IDs Übereinstimmung umgehen, fließt Medien direkt vom Gateway an den Client, der Vermittlungsserver umgangen.

Nur Lync 2010 oder neuere Clients und Geräten unterstützen Media Bypass Interaktionen mit einem Vermittlungsserver.

> [!IMPORTANT]
> Zusätzlich zur globalen Aktivierung der Medienumgehung müssen Sie die Medienumgehung auf jedem PSTN-Trunk einzeln aktivieren. Wenn die Umgehung zwar global, jedoch für einen bestimmten PSTN-Trunk nicht aktiviert wurde, wird sie für Anrufe über diesen PSTN-Trunk nicht ausgelöst. Darüber hinaus müssen Sie alle routingfähigen Subnetze den Standorten zuordnen, in denen sie sich befinden, wenn die Medienumgehung auf **Informationen zu Standort und Region verwenden** festgelegt ist. Routingfähige Subnetze in einem Standort, für den eine Medienumgehung nicht gewünscht wird, sollten vor Aktivierung der Umgehung in einem neuen Standort gruppiert werden. Auf diese Weise stellen Sie sicher, dass den nicht routingfähigen Subnetzen eine andere Umgehungs-ID zugewiesen wird.

## <a name="media-bypass-modes"></a>Modi für die Medienumgehung

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

    Wenn Sie die Anrufsteuerung aktivieren, können Sie die Option **Immer umgehen** nicht auswählen (und umgekehrt), da die zwei Konfigurationen sich gegenseitig ausschließen. Dies bedeutet, dass jeweils nur eine der zwei Optionen auf einen PSTN-Anruf angewendet wird. Zunächst wird überprüft, ob für den Anruf die Medienumgehung gilt. Ist dies der Fall, wird die Anrufsteuerung nicht verwendet. Dies ist plausibel, da ein für die Medienumgehung aktivierter Anruf per Definition eine Verbindung verwendet, für die eine Anrufsteuerung nicht notwendig ist. Wenn Umgehung für den Aufruf der angewendet werden kann (d. h., wenn die des Clients und des Gateways Umgehung IDs nicht übereinstimmen), und klicken Sie dann auf den Anruf CAC angewendet wird.

- Die Anrufsteuerung ist nicht aktiviert, und die Medienumgehung ist auf **Immer umgehen** festgelegt.

    In dieser Konfiguration sind sowohl Client- als auch Trunksubnetze einer einzigen ID für die Umgehung zugeordnet, die durch das System berechnet wird.

- Die Anrufsteuerung ist nicht aktiviert, und die Medienumgehung ist auf **Informationen zu Standort und Region verwenden** festgelegt.

    Wenn die Option **Informationen zu Standort und Region verwenden** aktiviert ist, funktioniert die Umgehungsermittlung im Prinzip in gleicher Weise - unabhängig davon, ob die Anrufsteuerung aktiviert ist oder nicht. D. h., für jeden PSTN Aufruf, der Client-Subnetz einem bestimmten Standort zugeordnet ist, und die umgehungs-ID für dieses Subnetz extrahiert wird. In ähnlicher Weise das Gateway Subnetz einem bestimmten Standort zugeordnet ist, und die umgehungs-ID für dieses Subnetz extrahiert wird. Nur wenn die zwei Umgehungs-IDs identisch sind, findet eine Medienumgehung für den Anruf statt. Unterscheiden sich die IDs, findet keine Medienumgehung statt.

    Selbst wenn die Anrufsteuerung global deaktiviert wurde, müssen Bandbreitenrichtlinien für jeden Standort und jede Verbindung definiert werden, wenn die Konfiguration von Standorten und Regionen für Entscheidungen zur Medienumgehung herangezogen werden soll. Der tatsächliche Wert der Einschränkung Bandbreite oder seine Modalität spielt keine Rolle. Das Ziel besteht darin, dass das System automatisch unterschiedliche Umgehungs-IDs berechnet, die verschiedenen Standorten ohne gute Verbindung zugeordnet sind. Das Definieren einer Bandbreiteneinschränkung bedeutet per Definition, dass eine Verbindung keine gute Konnektivität aufweist.

- Weder die Anrufsteuerung noch die Medienumgehung sind aktiviert. Dieser Fall tritt nur ein, wenn alle Gateways und IP-Nebenstellenanlagen über Leitungen mit geringer Konnektivität verbunden sind oder andere Anforderungen für die Medienumgehung nicht erfüllen. Ausführliche Informationen zu den Anforderungen für die Medienumgehung finden Sie unter [Requirements for Media Bypass](https://technet.microsoft.com/library/6162a204-0e7c-460a-8eb2-e592c6590a8a.aspx).

## <a name="technical-requirements"></a>Technische Anforderungen

Für jeden Anruf an das Telefonfestnetz bestimmt der Vermittlungsserver, ob Medien aus der Skype für Business Endpunkt Ursprungs direkt an einen Vermittlungsserver Peer gesendet werden können, ohne den Vermittlungsserver durchlaufen. Der Peer kann ein PSTN-Gateway, eine IP-Nebenstellenanlage oder ein SBC (Session Border Controller) bei einem Anbieter von Internettelefoniediensten sein, der zu der Leitung zwischen dem Vermittlungsserver gehört, bei dem der Anruf weitergeleitet wird.

Die Medienumgehung kann implementiert werden, wenn die folgenden Voraussetzungen erfüllt sind:

- Ein Vermittlungsserver Peer muss die erforderlichen Funktionen für die medienumgehung, die wichtigsten wird die Möglichkeit zum Verarbeiten von mehreren gegabelten Antworten (als "frühe Dialoge" bezeichnet) unterstützen. Wenden Sie sich an den Hersteller Ihres Gateways oder PBX-Anlage oder Ihr itsp Unterstützung, um den Wert für die maximale Anzahl von frühe Dialoge abzurufen, die das Gateway, der Nebenstellenanlage oder der SBC akzeptieren kann.

- Der Vermittlungsserver Peer muss Mediendatenverkehr direkt von Skype für Business-Endpunkte akzeptieren. Viele ITSPs können ihren SBC Datenverkehr nur aus der Vermittlungsserver empfangen. Wenden Sie sich an Ihrem ITSP, um festzustellen, ob die SBC Mediendatenverkehr direkt von Skype für Business-Endpunkte akzeptiert.

- Skype für Business-Clients und einem Vermittlungsserver Peer eine gute Verbindung sein muss, was bedeutet, dass sie entweder sich in demselben netzwerkregion befinden oder am Netzwerk Websites, die mit der Region verbunden, über WAN-links, die haben keine bandbreiteneinschränkungen


