---
title: Übersetzungsregeln in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
description: Hier finden Sie Informationen zu Übersetzungsregeln und zur Normalisierung der Wählzeichenfolge in Skype for Business Server Enterprise-VoIP.
ms.openlocfilehash: 1f435db01b5b15c97ae577565e4ba43f5de554ea
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297365"
---
# <a name="translation-rules-in-skype-for-business-server"></a>Übersetzungsregeln in Skype for Business Server

Hier finden Sie Informationen zu Übersetzungsregeln und zur Normalisierung der Wählzeichenfolge in Skype for Business Server Enterprise-VoIP.

 Enterprise-VoIP setzt voraus, dass alle Wählzeichenfolgen im E. 164-Format normalisiert werden, um RNL (Reverse Number Lookup) durchzuführen. Übersetzungsregeln werden sowohl für angerufene Nummern als auch für Rufnummern unterstützt. Thetrunk Peer (also das zugeordnete Gateway, die Private Branch Exchange (PBX) oder der SIP-Stamm) erfordert möglicherweise, dass die Nummern in einem lokalen Wählformat vorliegen. Um Nummern aus dem E.164-Format in ein lokales Wählformat zu übersetzen, können Sie eine oder mehrere Übersetzungsregeln definieren, mit denen der Anforderungs-URI vor dem Routen an den Trunkpeer geändert wird. Sie können beispielsweise eine Übersetzungsregel erstellen, mit der die Vorwahl +44 aus einer Wählzeichenfolge entfernt und durch 0144 ersetzt wird.

Durch die ausgehende Routenübersetzung auf dem Server können Sie die Konfigurationsanforderungen der einzelnen Trunkpeers für das Übersetzen von Rufnummern in ein lokales Wählformat reduzieren. Wenn Sie planen, welche Gateways und wie viele Gateways einem bestimmten Vermittlungs Server Cluster zugeordnet werden sollen, kann es hilfreich sein, trunk-Peers mit ähnlichen lokalen wählanforderungen zu gruppieren. Dies kann die Anzahl von erforderlichen Übersetzungsregeln und den Zeitaufwand für das Schreiben dieser Regeln reduzieren.

> [!IMPORTANT]
> Das Zuordnen einer oder mehrerer Übersetzungsregeln zu einer Enterprise Voice trunk-Konfiguration sollte als Alternative zum Konfigurieren von Übersetzungsregeln für den trunk-Peer verwendet werden. Ordnen Sie Übersetzungsregeln keiner Enterprise-VoIP-trunk-Konfiguration zu, wenn Sie Übersetzungsregeln für den trunk-Peer konfiguriert haben, da die beiden Regeln möglicherweise in Konflikt stehen.

## <a name="example-translation-rules"></a>Beispielübersetzungsregeln

Die folgenden Beispiele für Übersetzungsregeln zeigen, wie Sie Regeln auf dem Server erstellen können, um Nummern aus dem E.164-Format in ein lokales Format für den Trunkpeer zu übersetzen.

Ausführliche Informationen zur Implementierung von Übersetzungsregeln finden Sie unter [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) in der Bereitstellungsdokumentation.

|**Beschreibung**|**Anfangsziffern**|**Länge**|**Zu entfernende Ziffern**|**Hinzuzufügende Ziffern**|**Vergleichsmuster**|**Übersetzung**|**Beispiel**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Normales Ferngespräch in den USA  <br/> ("+" entfernen)  <br/> |+1  <br/> |Exakt 12  <br/> |1  <br/> |0  <br/> |^\+(1 \ d{10}) $  <br/> |$1  <br/> |+14255551010 wird zu 14255551010  <br/> |
|Internationales Ferngespräch aus den USA  <br/> ("+" abstreifen und 011 hinzufügen)  <br/> |+  <br/> |Mindestens 11  <br/> |1  <br/> |011  <br/> |^\+(\d{9}\d +) $  <br/> |011$1  <br/> |+441235551010 wird zu 011441235551010  <br/> |


