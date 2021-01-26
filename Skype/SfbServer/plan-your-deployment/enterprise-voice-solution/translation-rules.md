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
description: Erfahren Sie mehr über Übersetzungsregeln und die Wählzeichenfolgennormalisierung in Skype for Business Server Enterprise-VoIP.
ms.openlocfilehash: 0c00776dae502bfd28bbe27e90012fabb6e25c93
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802685"
---
# <a name="translation-rules-in-skype-for-business-server"></a>Übersetzungsregeln in Skype for Business Server

Erfahren Sie mehr über Übersetzungsregeln und die Wählzeichenfolgennormalisierung in Skype for Business Server Enterprise-VoIP.

 Enterprise-VoIP erfordert, dass alle Wählzeichenfolgen in das E.164-Format normalisiert werden, um eine umgekehrte Nummernumschlage (Reverse Number Lookup, RNL) durchführen zu können. Übersetzungsregeln werden sowohl für angerufene als auch für Anrufnummern unterstützt. Für den Trunk-Peer (d. h. das zugeordnete Gateway, die Nebenstellenanlage (Private Branch Exchange, PBX) oder den SIP-Trunk) müssen die Nummern möglicherweise ein lokales Wählformat haben. Um Nummern aus dem E.164-Format in ein lokales Wählformat zu übersetzen, können Sie eine oder mehrere Übersetzungsregeln definieren, mit denen der Anforderungs-URI vor dem Routen an den Trunkpeer geändert wird. Sie können beispielsweise eine Übersetzungsregel erstellen, mit der das Präfix +44 aus einer Wählzeichenfolge entfernt und durch 0144 ersetzt wird.

Durch die ausgehende Routenübersetzung auf dem Server können Sie die Konfigurationsanforderungen der einzelnen Trunkpeers für das Übersetzen von Rufnummern in ein lokales Wählformat reduzieren. Wenn Sie planen, welche und wie viele Gateways einem bestimmten Vermittlungsservercluster zugeordnet werden sollen, kann es hilfreich sein, Trunk peers mit ähnlichen lokalen Wählanforderungen zu gruppieren. Dies kann die Anzahl von erforderlichen Übersetzungsregeln und den Zeitaufwand für das Schreiben dieser Regeln reduzieren.

> [!IMPORTANT]
> Das Zuordnen einer oder Enterprise-VoIP übersetzungsregeln zu einer Trunkkonfiguration sollte als Alternative zum Konfigurieren von Übersetzungsregeln für den Trunk-Peer verwendet werden. Ordnen Sie übersetzungsregeln nicht einer Enterprise-VoIP Trunkkonfiguration zu, wenn Sie Übersetzungsregeln für den Trunk peer konfiguriert haben, da die beiden Regeln in Konflikt stehen können.

## <a name="example-translation-rules"></a>Beispielübersetzungsregeln

Die folgenden Beispiele für Übersetzungsregeln zeigen, wie Sie Regeln auf dem Server erstellen können, um Nummern aus dem E.164-Format in ein lokales Format für den Trunkpeer zu übersetzen.

Ausführliche Informationen zur Implementierung von Übersetzungsregeln finden Sie unter [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) in der Bereitstellungsdokumentation.

|**Beschreibung**|**Anfangsziffern**|**Length**|**Zu entfernende Ziffern**|**Hinzuzufügende Ziffern**|**Vergleichsmuster**|**Übersetzung**|**Beispiel**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Normales Ferngespräch in den USA  <br/> (Strip out the '+')  <br/> |+1  <br/> |Exakt 12  <br/> |1   <br/> |0  <br/> |^\+(1\d {10} ) $  <br/> |$1  <br/> |+14255551010 wird zu 14255551010  <br/> |
|Internationales Ferngespräch aus den USA  <br/> (Strip out '+' and add 011)  <br/> |+  <br/> |Mindestens 11  <br/> |1   <br/> |011  <br/> |^\+(\d {9} \d+)$  <br/> |011$1  <br/> |+441235551010 wird zu 011441235551010  <br/> |


