---
title: Übersetzungsregeln in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
description: Erfahren Sie mehr über Übersetzungsregeln und die Normalisierung von Wählzeichenfolgen in Skype for Business Server Enterprise-VoIP.
ms.openlocfilehash: c053ea0244c6b8d0578b9776da9d7ecd40bb8043b0f5884c9d7437b688f5dd65
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54352693"
---
# <a name="translation-rules-in-skype-for-business-server"></a>Übersetzungsregeln in Skype for Business Server

Erfahren Sie mehr über Übersetzungsregeln und die Normalisierung von Wählzeichenfolgen in Skype for Business Server Enterprise-VoIP.

 Enterprise-VoIP erfordert, dass alle Wählzeichenfolgen in das E.164-Format normalisiert werden, um eine umgekehrte Nummernsuche (Reverse Number Lookup, RNL) durchzuführen. Übersetzungsregeln werden sowohl für angerufene Als auch für Anrufnummern unterstützt. Für den Trunkpeer (d. h. das zugeordnete Gateway, die Nebenstellenanlage oder den SIP-Trunk) müssen Nummern möglicherweise ein lokales Wählformat aufweisen. Um Nummern aus dem E.164-Format in ein lokales Wählformat zu übersetzen, können Sie eine oder mehrere Übersetzungsregeln definieren, mit denen der Anforderungs-URI vor dem Routen an den Trunkpeer geändert wird. Sie können beispielsweise eine Übersetzungsregel erstellen, mit der das Präfix +44 aus einer Wählzeichenfolge entfernt und durch 0144 ersetzt wird.

Durch die ausgehende Routenübersetzung auf dem Server können Sie die Konfigurationsanforderungen der einzelnen Trunkpeers für das Übersetzen von Rufnummern in ein lokales Wählformat reduzieren. Wenn Sie planen, welche Gateways und wie viele Gateways einem bestimmten Vermittlungsservercluster zugeordnet werden sollen, kann es hilfreich sein, Trunkpeers mit ähnlichen lokalen Wählanforderungen zu gruppieren. Dies kann die Anzahl von erforderlichen Übersetzungsregeln und den Zeitaufwand für das Schreiben dieser Regeln reduzieren.

> [!IMPORTANT]
> Das Zuordnen einer oder mehrerer Übersetzungsregeln zu einer Enterprise-VoIP Trunkkonfiguration sollte als Alternative zum Konfigurieren von Übersetzungsregeln für den Trunkpeer verwendet werden. Ordnen Sie einer Enterprise-VoIP Trunkkonfiguration keine Übersetzungsregeln zu, wenn Sie Übersetzungsregeln für den Trunkpeer konfiguriert haben, da die beiden Regeln in Konflikt stehen können.

## <a name="example-translation-rules"></a>Beispielübersetzungsregeln

Die folgenden Beispiele für Übersetzungsregeln zeigen, wie Sie Regeln auf dem Server erstellen können, um Nummern aus dem E.164-Format in ein lokales Format für den Trunkpeer zu übersetzen.

Ausführliche Informationen zur Implementierung von Übersetzungsregeln finden Sie unter [Defining Translation Rules](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules) in der Bereitstellungsdokumentation.

|**Beschreibung**|**Anfangsziffern**|**Length**|**Zu entfernende Ziffern**|**Hinzuzufügende Ziffern**|**Vergleichsmuster**|**Übersetzung**|**Beispiel**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Normales Ferngespräch in den USA  <br/> (Entfernen des "+"-Attributs)  <br/> |+1  <br/> |Exakt 12  <br/> |1  <br/> |0  <br/> |^\+(1\d {10} ) $  <br/> |$1  <br/> |+14255551010 wird zu 14255551010  <br/> |
|Internationales Ferngespräch aus den USA  <br/> (Entfernen von "+" und Hinzufügen von 011)  <br/> |+  <br/> |Mindestens 11  <br/> |1  <br/> |011  <br/> |^\+(\d {9} \d+)$  <br/> |011$1  <br/> |+441235551010 wird zu 011441235551010  <br/> |